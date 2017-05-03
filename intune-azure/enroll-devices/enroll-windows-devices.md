---
title: "Windowsos eszközök regisztrálása"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: az Intune mobileszköz-felügyelet (MDM) engedélyezése windowsos eszközökre."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 3c764b269916ae1a9b076617842eb26d7fd13bab
ms.lasthandoff: 04/19/2017


---

# <a name="enroll-windows-devices"></a>Windowsos eszközök regisztrálása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ez a témakör a felhasználók windowsos eszközeinek regisztrációját segít megkönnyíteni a rendszergazdáknak.  A windowsos eszközök további lépések nélkül is regisztrálhatók, de a folyamatot meg lehet könnyíteni a felhasználók számára.

A többfelhasználós felügyelet támogatását kiterjesztettük a Windows 10 alkotói frissítését futtató, Azure Active Directory-tartományhoz csatlakozó eszközökre. Az eszközre minden egyes, Azure AD-s hitelesítő adataival bejelentkező általános jogú felhasználó a saját felhasználónevéhez rendelt alkalmazásokat és szabályzatokat kapja meg. A felhasználók jelenleg nem használhatják a Céges portált önkiszolgálói forgatókönyvek esetén (például alkalmazások telepítése).

A Windows-eszközök regisztrálásának egyszerűsítését két tényező határozza meg:

- **Prémium szintű Azure Active Directoryt használnak?** <br>Az [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) az Enterprise Mobility + Security és más licencelési csomagok keretében is elérhető.
- **Milyen Windows-verziókat fognak regisztrálni az ügyfelek?** <br>A Windows 10-es eszközök egy munkahelyi vagy iskolai fiók felvételével automatikusan regisztrálhatók. A korábbi verziók a Céges portál alkalmazással tudnak regisztrálni.

||**Azure AD Premium**|**Egyéb AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatikus regisztráció](#enable-windows-10-automatic-enrollment) |[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|
|**Korábbi Windows-verziók**|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Windowsos regisztráció engedélyezése Prémium szintű Azure AD nélkül
A felhasználói eszközregisztrációt a Prémium szintű Azure AD automatikus regisztrációja nélkül is lehetővé teheti. A licencek hozzárendelése után a felhasználóknak a regisztrálás előtt hozzá kell adniuk munkahelyi fiókjukat a személyes tulajdonban lévő eszközeiken, vagy a céges tulajdonú eszközeiket csatlakoztatniuk kell az Azure AD-hoz. DNS-aliasok (CNAME rekordtípus) létrehozása megkönnyíti a felhasználóknak az eszközeik regisztrálását. DNS CNAME erőforrásrekord létrehozásával a felhasználók Intune-kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz és regisztrálni a szolgáltatásra.

**1. lépés: CNAME rekordok létrehozása** (nem kötelező)<br>
Hozza létre a megfelelő CNAME DNS-erőforrásrekordokat a céges tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre.

A CNAME DNS-bejegyzések létrehozása nem kötelező, viszont a CNAME rekordok létrehozása egyszerűbbé teszi a regisztrációt a felhasználók számára. Ha nem található CNAME rekord, akkor a rendszer kéri a felhasználókat, hogy írják be az MDM-kiszolgáló nevét: enrollment.manage.microsoft.com.

|Típus|Gazdagép neve|A következő helyre mutat|Élettartam|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.munkahelyi_tartomány.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 óra|

Ha több UPN-utótagja is van, akkor mindegyik tartománynévhez külön CNAME-rekordot kell létrehozni, és mindegyiket az EnterpriseEnrollment-s.manage.microsoft.com tartományra irányítani. Ha például a Contoso dolgozóinak a felhasználóneve és e-mail-címe a name@contoso.com formátumot követi, de a name@us.contoso.com és name@eu.constoso.com változatot is használják, a Contoso DNS-adminisztrátorának a következő CNAME-rekordokat kell létrehoznia.

|Típus|Gazdagép neve|A következő helyre mutat|Élettartam|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 óra|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 óra|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 óra|

`EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynévvel irányítja át a felhasználókat az Intune-ba.

A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

**2. lépés: a CNAME ellenőrzése** (nem kötelező)<br>
Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Az Intune-beli panelen válassza az **Eszközök regisztrálása** >  **Windows-regisztráció** lehetőséget. Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

## <a name="tell-users-how-to-enroll-windows-devices"></a>A felhasználók tájékoztatása a windowsos eszközök regisztrálásáról
Tájékoztassa felhasználóit arról, hogy miként regisztrálhatják windowsos eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-felügyelet alá bevont eszközeiken. A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). A felhasználók a [Milyen adatokhoz jut hozzá a rendszergazda, ha regisztrálom az eszközömet?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) című témakörből is tájékozódhatnak.

A végfelhasználói feladatokkal kapcsolatban lásd: [Információk végfelhasználóknak a Microsoft Intune használatáról](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

