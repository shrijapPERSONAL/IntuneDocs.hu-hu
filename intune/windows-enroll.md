---
title: Windows-eszközök regisztrációjának beállítása az Intune-nal
titlesuffix: ''
description: Windowsos eszközök regisztrációjának beállítása.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: efb850e0f08c94cfee7948f50411220216eb8418
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188067"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Windowsos eszközök regisztrációjának beállítása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk a felhasználók Windowsos eszközeinek regisztrációját segít megkönnyíteni a rendszergazdáknak. Miután [beállította az Intune-t](setup-steps.md), a felhasználók a munkahelyi vagy iskolai fiókjukkal [bejelentkezve](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) tudják regisztrálni a windowsos eszközeiket.  

Intune-rendszergazdaként a következő módokon egyszerűsítheti a regisztrációt:
- [Automatikus regisztráció engedélyezése](#enable-windows-10-automatic-enrollment) (prémium szintű Azure AD-előfizetés szükséges)
- [CNAME-regisztráció](#simplify-windows-enrollment-without-azure-ad-premium)
- [Csoportos regisztráció engedélyezése](windows-bulk-enroll.md) (prémium szintű Azure AD-előfizetés és Windows Configuration Designer szükséges)

A Windows-eszközök regisztrálásának egyszerűsítését két tényező határozza meg:

- **Prémium szintű Azure Active Directoryt használnak?** <br>Az [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) az Enterprise Mobility + Security és más licencelési csomagok keretében is elérhető.
- **Milyen Windows-verziókat fognak regisztrálni az felhasználók?** <br>A Windows 10-es eszközök egy munkahelyi vagy iskolai fiók felvételével automatikusan regisztrálhatók. A korábbi verziók a Céges portál alkalmazással tudnak regisztrálni.

||**Azure AD Premium**|**Egyéb AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatikus regisztráció](#enable-windows-10-automatic-enrollment) |[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|
|**Korábbi Windows-verziók**|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|

Azok a cégek, amelyek használhatják az automatikus regisztrációt, a Windows Configuration Designer alkalmazással is konfigurálhatják az [eszközök csoportos regisztrációját](windows-bulk-enroll.md).

## <a name="multi-user-support"></a>Több felhasználó támogatása

Az Intune többfelhasználós felügyeletet támogat a Windows 10 alkotói frissítését futtató, Azure Active Directory-tartományhoz csatlakozó eszközökön. Ha általános jogú felhasználók jelentkeznek be az Azure AD-beli hitelesítő adataikkal, a felhasználónevükhöz hozzárendelt alkalmazásokat és szabályokat kapnak. A felhasználók jelenleg nem használhatják a Céges portált önkiszolgálói forgatókönyvek esetén (például alkalmazások telepítése).

[!INCLUDE [AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Windowsos regisztráció egyszerűsítése Prémium szintű Azure AD nélkül
A regisztráció leegyszerűsítéséhez hozzon létre egy DNS-aliast (CNAME rekordtípust), amely átirányítja a regisztrációs kérelmeket az Intune-kiszolgálókra. Ellenkező esetben az Intune-hoz csatlakozni kívánó felhasználóknak a regisztráció során meg kell adniuk az Intune-kiszolgáló nevét.

**1. lépés: CNAME rekordok létrehozása** (nem kötelező)<br>
Hozza létre a megfelelő CNAME DNS-erőforrásrekordokat a céges tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre.

A CNAME DNS-bejegyzések létrehozása nem kötelező, viszont a CNAME rekordok létrehozása egyszerűbbé teszi a regisztrációt a felhasználók számára. Ha nem található CNAME rekord, akkor a rendszer kéri a felhasználókat, hogy írják be az MDM-kiszolgáló nevét: enrollment.manage.microsoft.com.

|Típus|Gazdagép neve|A következő helyre mutat|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.munkahelyi_tartomány.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 óra|
|CNAME|EnterpriseRegistration.munkahelyi_tartomány.com|EnterpriseRegistration.windows.net|1 óra|

Ha a cégnek több UPN-utótagja is van, akkor mindegyik tartománynévhez külön CNAME-rekordot kell létrehozni, és mindegyiket az EnterpriseEnrollment-s.manage.microsoft.com tartományra irányítani. A Contoso felhasználói például a következő formátumokat használják e-mailként/egyszerű felhasználónévként:

- name@contoso.com
- name@us.contoso.com
- name@eu.constoso.com\

A Contoso DNS-rendszergazdájának a következő CNAME-elemeket kell létrehoznia:

|Típus|Gazdagép neve|A következő helyre mutat|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 óra|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 óra|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 óra|

`EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynévvel irányítja át a felhasználókat az Intune-ba.

A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

**2. lépés: a CNAME ellenőrzése** (nem kötelező)<br>
1. Az [Azure Portalbeli Intune-ban](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Windows-regisztráció** > **CNAME-ellenőrzés** elemet.
2. A **tartomány** mezőben adja meg a céges webhelyet, majd válassza a **Teszt** lehetőséget.

## <a name="tell-users-how-to-enroll-windows-devices"></a>A felhasználók tájékoztatása a windowsos eszközök regisztrálásáról
Tájékoztassa felhasználóit arról, hogy miként regisztrálhatják windowsos eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-felügyelet alá bevont eszközeiken.

> [!NOTE]
> Az adott Windows-verzióhoz Ön által hozzárendelt Windows-alkalmazások megtekintéséhez a végfelhasználóknak Microsoft Edge böngészővel kell hozzáférnie a Munkahelyi portál webhelyhez. Más böngészők, ideértve a Google Chrome, a Mozilla Firefox és az Internet Explorer böngészőt, nem támogatják ezt a szűréstípust.

A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). A felhasználókat megkérheti, hogy nézzék át azt is, [milyen adatokat tekinthet meg a rendszergazda az eszközeiken](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

>[!IMPORTANT]
> Ha nem engedélyezte az automatikus MDM-et, azonban olyan Windows 10-eszközökkel rendelkezik, amelyek az Azure AD-hez csatlakoznak, a regisztráció után két rekord jelenik meg az Intune-konzolban. Ezt megakadályozhatja úgy, ha az Azure AD-hez csatlakozó eszközökkel rendelkező felhasználók a **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** területen **csatlakoznak** ugyanazzal a fiókkal. 

A végfelhasználói feladatokkal kapcsolatban lásd: [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md).

## <a name="next-steps"></a>További lépések

- [Szempontok a Windows-eszközök Azure-beli Intune-nal történő felügyeletéhez](/intune-classic/deploy-use/intune-on-azure).
