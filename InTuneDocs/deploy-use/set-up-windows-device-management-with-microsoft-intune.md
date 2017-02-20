---
title: "Windowsos eszközök kezelésének beállítása a Microsoft Intune-ban | Microsoft Docs"
description: "A mobileszközök Microsoft Intune-nal való felügyeletének (MDM) engedélyezése Windows-eszközök esetén."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: e020ac2a4f600a94e7409e04c4c48f0c405c56cf


---

# <a name="set-up-windows-device-management"></a>Windowsos eszközök kezelésének beállítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Windows-eszközök regisztrációját az alábbi módszerek egyikével állíthatja be:

- **[A Windows 10-es és a Windows 10 Mobile rendszerű eszközök automatikus regisztrációja az Azure Active Directory Premium szolgáltatással](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)** 
 -  Ez a módszer Windows 10-es és Windows 10 Mobile-eszközök esetén alkalmazható.
 -  A módszer alkalmazásához Azure Active Directory Premium szolgáltatás szükséges. A szolgáltatás híján a Windows 8.1-es és a Windows Phone 8.1-es eszközökhöz használatos regisztrációs eljárást kell alkalmaznia.
 -  Ha nem szeretné engedélyezni az automatikus regisztrációt, a Windows 8.1-es és a Windows Phone 8.1-es eszközök regisztrációs módszerét kell alkalmaznia.


- **[Windows 8.1-es és Windows Phone 8.1-es eszközök regisztrációja a CNAME konfigurálásával](#set-up-windows-8--1-and-windows-phone-8--1-enrollment-by-configuring-cname)** 
 - Windows 8.1-es és Windows Phone 8.1-es eszközök regisztrációjához ezt a módszert kell alkalmaznia.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Windows 8.1-es és Windows Phone 8.1-es eszközök regisztrációjának beállítása a CNAME konfigurálásával
Engedélyezheti a felhasználók számára, hogy telepítsék és regisztrálják eszközeiket az Intune Céges portálon. DNS CNAME erőforrásrekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá.

1. **Az Intune beállítása**<br>
Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority), valamint beállítja a mobileszköz-kezelést.

2. **CNAME rekordok létrehozása** (nem kötelező)<br>
Hozza létre a megfelelő **CNAME** DNS-erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre.

    A CNAME DNS-bejegyzések létrehozása nem kötelező, viszont a CNAME rekordok létrehozása egyszerűbbé teszi a regisztrációt a felhasználók számára. Ha nem található CNAME rekord, akkor a rendszer kéri a felhasználókat, hogy írják be az MDM-kiszolgáló nevét: enrollment.manage.microsoft.com.    

    Amennyiben jelenleg a DNS rendszerben található olyan CNAME rekord, amelyik átirányítja az EnterpriseEnrollment.contoso.com címet a manage.microsoft.com címre, javasolt azt lecserélni egy olyan CNAME rekordra, amelyik az enterpriseenrollment-s.manage.microsoft.com címre irányítja át az EnterpriseEnrollment.contoso.com címet. Ez a módosítás azért ajánlott, mert a regisztrációkhoz használt manage.microsoft.com végpontot egy későbbi kiadásban kivezetjük.

    A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

  |TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.munkahelyi_tartomány.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
  |CNAME|EnterpriseRegistration.munkahelyi_tartomány.com|EnterpriseRegistration.windows.net|1 óra|

  `EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynévvel irányítja át a felhasználókat az Intune-ba.

  `EnterpriseRegistration.windows.net` – Azokat a Windows 8.1 és Windows 10 Mobile rendszerű eszközöket támogatja, amelyeket a munkahelyi vagy iskolai fiókkal az Azure Active Directoryban fognak regisztrálni.

  Ha a vállalat több tartományt használ a felhasználók hitelesítő adataihoz, akkor minden egyes tartományhoz hozzon létre CNAME rekordot.

  Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az EnterpriseEnrollment-s.manage.microsoft.com webhelyre. A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

3.  **A CNAME ellenőrzése**<br>Az [Intune felügyeleti konzolon](http://manage.microsoft.com) kattintson a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows** elemre. Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

4.  **Tájékoztatnia kell a felhasználókat arról, hogy miként regisztrálhatják az eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-kezelésbe bevont eszközeiken.**

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    A végfelhasználói feladatokkal kapcsolatban lásd: [Információk végfelhasználóknak a Microsoft Intune használatáról](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>További információ
[A Microsoft Intune-beli eszközregisztráció előfeltételei](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO2-->


