---
title: "Windowsos eszközök regisztrálása"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: az Intune mobileszköz-felügyelet (MDM) engedélyezése windowsos eszközökre."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 03/21/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 609656c2831c09c67e911c8150d31f38faad020b
ms.lasthandoff: 03/22/2017


---

# <a name="enroll-windows-devices"></a>Windowsos eszközök regisztrálása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A windowsos eszközök regisztrációját az alábbi módszerek egyikével állíthatja be:

- [**A Windows 10-es és a Windows 10 Mobile rendszerű eszközök automatikus regisztrációja az Azure Active Directory Premium szolgáltatással**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Ez a módszer Windows 10-es és Windows 10 Mobile-eszközök esetén alkalmazható.
 -  A módszer alkalmazásához Azure Active Directory Premium szolgáltatás szükséges. A szolgáltatás híján a Windows 8.1-es és a Windows Phone 8.1-es eszközökhöz használatos regisztrációs eljárást kell alkalmaznia.
 -  Ha nem szeretné engedélyezni az automatikus regisztrációt, a Windows 8.1-es és a Windows Phone 8.1-es eszközök regisztrációs módszerét kell alkalmaznia.

- [**Regisztráció az Prémium szintű Azure AD automatikus regisztrációja nélkül**](#enable-windows-enrollment-without-azure-ad-premium)
 - Windows 8.1-es és Windows Phone 8.1-es eszközök regisztrációjához ezt a módszert kell alkalmaznia.
 - Windows 8.1-esnél újabb eszközökhöz is használhatja, ha nem szeretne Prémium szintű Azure Active Directory (AD) szolgáltatásra előfizetni.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Windowsos regisztráció engedélyezése Prémium szintű Azure AD nélkül

Lehetővé teszi a felhasználóknak az eszközök telepítését és regisztrációját a Premium szintű Azure AD automatikus regisztrációja nélkül. DNS CNAME erőforrásrekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá.

1. **CNAME rekordok létrehozása** (nem kötelező)<br>
 Hozza létre a megfelelő **CNAME** DNS-erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre.

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

2.  **A CNAME ellenőrzése**<br>Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Az Intune-beli panelen válassza az **Eszközök regisztrálása** > **Windows-regisztráció** lehetőséget. Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

3.  **Tájékoztatnia kell a felhasználókat arról, hogy miként regisztrálhatják az eszközeiket, és mire kell számítsanak, ha eszközeiket bevonták a mobileszköz-felügyelet alá.**

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). A felhasználók a [Milyen adatokhoz jut hozzá a rendszergazda, ha regisztrálom az eszközömet az Intune-ban?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) című témakörből is tájékozódhatnak.

    A végfelhasználói feladatokkal kapcsolatban lásd: [Információk végfelhasználóknak a Microsoft Intune használatáról](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

Nincs további feladata, kivéve, ha az eszközökre telepíti a Vállalati portált.  A felügyeleti konzol 2. és 3. lépése biztonsággal figyelmen kívül hagyható.

