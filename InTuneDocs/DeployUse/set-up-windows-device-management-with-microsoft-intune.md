---
title: "Windowsos eszközök kezelésének beállítása a Microsoft Intune-ban | Microsoft Intune"
description: "Mobileszközök felügyeletének (MDM) engedélyezése a Microsoft Intune-nal windowsos számítógépek esetén, beleértve a Windows 10-eszközöket is."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 9b063c1e6b1ff5dcab16fce958ede49303284b18


---

# Windowsos eszközök kezelésének beállítása

Intune-rendszergazdaként kétféleképpen engedélyezheti a Windows rendszerű számítógépek regisztrációját és felügyeletét:

- **[Automatikus regisztrálás az Azure AD-vel](#azure-active-directory-enrollment)** - a Windows 10- és Windows 10 Mobile-felhasználók a regisztrálni kívánt eszközhöz hozzáadnak egy munkahely vagy iskolai fiókot
- **[Regisztráció a Vállalati portállal](#company-portal-app-enrollment)** - a Windows 8.1-es és újabb verziójú eszközök regisztrálása úgy történik, hogy a felhasználók letöltik és telepítik a Vállalati portál alkalmazást, majd abban megadják a munkahelyi vagy iskolai fiókjuk hitelesítő adatait.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## A Vállalati portál alkalmazással történő regisztráció konfigurálása
Engedélyezheti a felhasználók számára, hogy telepítsék az Intune Vállalati portál alkalmazást és eszközeiket azzal regisztrálják. DNS CNAME rekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá.

1. **Az Intune beállítása**<br>
Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority), valamint beállítja a mobileszköz-kezelést.

2. **CNAME rekordok létrehozása** (nem kötelező)<br>A regisztráció megkönnyítése érdekében hozza létre a megfelelő **CNAME** DNS-erőforrásrekordokat a munkahelyi tartományhoz. A CNAME DNS-bejegyzések létrehozása nem kötelező, viszont a CNAME rekordok létrehozása egyszerűbbé teszi a regisztrációt a felhasználók számára. Ha nem található CNAME rekord, akkor a rendszer kéri a felhasználókat, hogy írják be az MDM-kiszolgáló nevét: `https://manage.microsoft.com`.  A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

  |TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 óra|

  `EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynév használatával irányítja át a felhasználókat az Intune-ba.

  `EnterpriseRegistration.windows.net` – Azokat a Windows 8.1 és Windows 10 Mobile rendszerű eszközöket támogatja, amelyeket a munkahelyi vagy iskolai fiókkal az Azure Active Directoryban fognak regisztrálni

  Ha a vállalat több tartományt használ a felhasználók hitelesítő adataihoz, akkor minden egyes tartományhoz hozzon létre CNAME rekordot.

  Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az EnterpriseEnrollment-s.manage.microsoft.com webhelyre. A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

3.  **A CNAME ellenőrzése**<br>Az [Intune felügyeleti konzolon](http://manage.microsoft.com) kattintson a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows** lehetőségre. Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

  ![Windowsos eszközök kezelése párbeszédpanel](../media/enroll-intune-winenr.png)

4.  **Nem kötelező lépések**<br>A **Tesztcélú telepítés kulcsainak hozzáadása** lépésre nincs szükség Windows 10 esetén. A **Kódaláíró tanúsítvány feltöltése** lépésre csak akkor van szükség, ha a Windows Áruházból nem elérhető üzletági (LOB) alkalmazásokat kíván terjeszteni. [További információ](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **A felhasználók tájékoztatása**<br>Tájékoztatnia kell a felhasználókat arról, hogy miként regisztrálhatják az eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-kezelésbe bevont eszközeiken:
      - [Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Végfelhasználó útmutató Windows-eszközökhöz](../enduser/using-your-windows-device-with-intune.md)

### További információ
[Felkészülés az eszközök regisztrálására a Microsoft Intune-ban](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


