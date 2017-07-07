---
title: "Windowsos eszközök Microsoft Intune-beli kezelésének beállítása"
description: "A mobileszközök Microsoft Intune-nal való felügyeletének (MDM) engedélyezése Windows-eszközök esetén."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cf77cb313d5a36c5e7975e70d54bf044aa2d30c8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="set-up-windows-device-management"></a>Windowsos eszközök kezelésének beállítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör a felhasználók windowsos eszközeinek regisztrációját segít megkönnyíteni a rendszergazdáknak.  A windowsos eszközök további lépések nélkül is regisztrálhatók, de a folyamatot meg lehet könnyíteni a felhasználók számára.

A Windows-eszközök regisztrálásának egyszerűsítését két tényező határozza meg:
- **Prémium szintű Azure Active Directoryt használnak?** <br>Az [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) az Enterprise Mobility + Security és más licencelési csomagok keretében is elérhető.
- **Milyen Windows-verziókat fognak regisztrálni az ügyfelek?** <br>A Windows 10-es eszközök egy munkahelyi vagy iskolai fiók felvételével automatikusan regisztrálhatók. A korábbi verziók a Céges portál alkalmazással tudnak regisztrálni.

||**Azure AD Premium**|**Egyéb AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatikus regisztráció](#enable-windows-10-automatic-enrollment) |[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|
|**Korábbi Windows-verziók**|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|[Felhasználói regisztráció](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Windowsos regisztráció engedélyezése automatikus regisztráció nélkül
A felhasználói eszközregisztrációt a Prémium szintű Azure AD automatikus regisztrációja nélkül is lehetővé teheti. A licencek hozzárendelése után a felhasználóknak a regisztrálás előtt hozzá kell adniuk munkahelyi fiókjukat a személyes tulajdonban lévő eszközeiken, vagy a céges tulajdonú eszközeiket csatlakoztatniuk kell az Azure AD-hoz. DNS-aliasok (CNAME rekordtípus) létrehozása megkönnyíti a felhasználóknak az eszközeik regisztrálását. DNS CNAME erőforrásrekord létrehozásával a felhasználók Intune-kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz és regisztrálni a szolgáltatásra.

**1. lépés: CNAME rekordok létrehozása** (nem kötelező)<br>
Hozza létre a megfelelő CNAME DNS-erőforrásrekordokat a céges tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre.

A CNAME DNS-bejegyzések létrehozása nem kötelező, viszont a CNAME rekordok létrehozása egyszerűbbé teszi a regisztrációt a felhasználók számára. Ha nem található CNAME rekord, akkor a rendszer kéri a felhasználókat, hogy írják be az MDM-kiszolgáló nevét: enrollment.manage.microsoft.com.

Több ellenőrzött tartomány esetén minden tartományhoz külön CNAME rekordot kell létrehozni. A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

|TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.munkahelyi_tartomány.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
|CNAME|EnterpriseRegistration.munkahelyi_tartomány.com|EnterpriseRegistration.windows.net|1 óra|

`EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynévvel irányítja át a felhasználókat az Intune-ba.

Ha a vállalat több tartományt használ a felhasználók hitelesítő adataihoz, akkor minden egyes tartományhoz hozzon létre CNAME rekordot.

Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az EnterpriseEnrollment-s.manage.microsoft.com webhelyre. A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

**2. lépés: a CNAME ellenőrzése** (nem kötelező)<br>
Az [Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows** elemre. Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

## <a name="tell-users-how-to-enroll-windows-devices"></a>A felhasználók tájékoztatása a windowsos eszközök regisztrálásáról
Tájékoztassa felhasználóit arról, hogy miként regisztrálhatják windowsos eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-felügyelet alá bevont eszközeiken.
A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). A felhasználók a [Milyen adatokhoz jut hozzá a rendszergazda, ha regisztrálom az eszközömet?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) című témakörből is tájékozódhatnak.

A végfelhasználói feladatokkal kapcsolatban lásd: [Információk végfelhasználóknak a Microsoft Intune használatáról](/intune/end-user-educate).

### <a name="see-also"></a>További információ
[A Microsoft Intune-beli eszközregisztráció előfeltételei](prerequisites-for-enrollment.md)
