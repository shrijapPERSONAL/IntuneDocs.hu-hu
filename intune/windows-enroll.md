---
title: "Windowsos eszközök regisztrálása"
titlesuffix: Azure portal
description: "Az Intune mobileszköz-felügyeletének (MDM) engedélyezése windowsos eszközökre."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fea5a61da77a3f96e006ee9ceb4ec3d8de645072
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/27/2018
---
# <a name="enroll-windows-devices"></a>Windowsos eszközök regisztrálása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör a felhasználók windowsos eszközeinek regisztrációját segít megkönnyíteni a rendszergazdáknak. Miután [beállította az Intune-t](setup-steps.md), a felhasználók a munkahelyi vagy iskolai fiókjukkal [bejelentkezve](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) tudják regisztrálni a windowsos eszközeiket.  

Intune-rendszergazdaként a következő módokon egyszerűsítheti a regisztrációt:
- [Automatikus regisztráció engedélyezése](#enable-windows-10-automatic-enrollment) (prémium szintű Azure AD-előfizetés szükséges)
- [CNAME-regisztráció](#simplify-windows-enrollment-without-azure-ad-premium)
- [Csoportos regisztráció engedélyezése](windows-bulk-enroll.md) (prémium szintű Azure AD-előfizetés és Windows Configuration Designer szükséges)
- [Egyedi üzenet hozzáadása](windows-enrollment-status.md) a felhasználók köszöntésére, miközben a regisztrációkor nyomon követik a szabályzatbeállítások alkalmazásának előrehaladását.

A Windows-eszközök regisztrálásának egyszerűsítését két tényező határozza meg:

- **Prémium szintű Azure Active Directoryt használnak?** <br>Az [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) az Enterprise Mobility + Security és más licencelési csomagok keretében is elérhető.
- **Milyen Windows-verziókat fognak regisztrálni az felhasználók?** <br>A Windows 10-es eszközök egy munkahelyi vagy iskolai fiók felvételével automatikusan regisztrálhatók. A korábbi verziók a Céges portál alkalmazással tudnak regisztrálni.

||**Azure AD Premium**|**Egyéb AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatikus regisztráció](#enable-windows-10-automatic-enrollment) |[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|
|**Korábbi Windows-verziók**|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|

Azok a cégek, amelyek használhatják az automatikus regisztrációt, a Windows Configuration Designer alkalmazással is konfigurálhatják az [eszközök csoportos regisztrációját](windows-bulk-enroll.md).

**Több felhasználó támogatása**<br>
A többfelhasználós felügyelet támogatását kiterjesztettük a Windows 10 alkotói frissítését futtató, Azure Active Directory-tartományhoz csatlakozó eszközökre. Ha általános jogú felhasználók jelentkeznek be az Azure AD-beli hitelesítő adataikkal, a felhasználónevükhöz hozzárendelt alkalmazásokat és szabályokat kapnak. A felhasználók jelenleg nem használhatják a Céges portált önkiszolgálói forgatókönyvek esetén (például alkalmazások telepítése).

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Windowsos regisztráció egyszerűsítése Prémium szintű Azure AD nélkül
Egyszerűsítheti a felhasználói regisztrációt egy DNS-alias (CNAME rekordtípus) létrehozásával, amely automatikusan átirányítja a regisztrációs kérelmeket az Intune-kiszolgálókra. Ha nem hoz létre DNS CNAME erőforrásrekordot, az Intune-hoz csatlakozni kívánó felhasználóknak a regisztráció során meg kell adniuk az Intune-kiszolgáló nevét.

**1. lépés: CNAME rekordok létrehozása** (nem kötelező)<br>
Hozza létre a megfelelő CNAME DNS-erőforrásrekordokat a céges tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre.

A CNAME DNS-bejegyzések létrehozása nem kötelező, viszont a CNAME rekordok létrehozása egyszerűbbé teszi a regisztrációt a felhasználók számára. Ha nem található CNAME rekord, akkor a rendszer kéri a felhasználókat, hogy írják be az MDM-kiszolgáló nevét: enrollment.manage.microsoft.com.

|Típus|Gazdagép neve|A következő helyre mutat|Élettartam|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.munkahelyi_tartomány.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 óra|
|CNAME|EnterpriseRegistration.munkahelyi_tartomány.com|EnterpriseRegistration.windows.net|1 óra|

Ha több UPN-utótagja is van, akkor mindegyik tartománynévhez külön CNAME-rekordot kell létrehozni, és mindegyiket az EnterpriseEnrollment-s.manage.microsoft.com tartományra irányítani. Ha a Contoso dolgozóinak az egyszerű felhasználóneve és e-mail-címe a name@contoso.com formátumot követi, de a name@us.contoso.com és name@eu.constoso.com változatot is használják, a Contoso DNS-adminisztrátorának a következő CNAME-rekordokat kell létrehoznia:

|Típus|Gazdagép neve|A következő helyre mutat|Élettartam|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 óra|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 óra|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 óra|

`EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynévvel irányítja át a felhasználókat az Intune-ba.

A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

**2. lépés: a CNAME ellenőrzése** (nem kötelező)<br>
Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Az Intune-beli panelen válassza az **Eszközök regisztrálása** >  **Windows-regisztráció** lehetőséget. Írja be a munkahelyi webhely URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

## <a name="tell-users-how-to-enroll-windows-devices"></a>A felhasználók tájékoztatása a windowsos eszközök regisztrálásáról
Tájékoztassa felhasználóit arról, hogy miként regisztrálhatják windowsos eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-felügyelet alá bevont eszközeiken.

> [!NOTE]
> Az adott Windows-verzióhoz Ön által hozzárendelt Windows-alkalmazások megtekintéséhez a végfelhasználóknak Microsoft Edge böngészővel kell hozzáférnie a Munkahelyi portál webhelyhez. Más böngészők, ideértve a Google Chrome, a Mozilla Firefox és az Internet Explorer böngészőt, nem támogatják ezt a szűréstípust.

A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). A felhasználókat megkérheti, hogy nézzék át azt is, [milyen adatokat tekinthet meg a rendszergazda az eszközeiken](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

A végfelhasználói feladatokkal kapcsolatban lásd: [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md).

## <a name="next-steps"></a>További lépések

- [Szempontok a Windows-eszközök Azure-beli Intune-nal történő felügyeletéhez](/intune-classic/deploy-use/intune-on-azure).
