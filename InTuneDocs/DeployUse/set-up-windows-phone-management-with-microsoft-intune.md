---
title: "Windows 10 Mobile és Windows Phone rendszerű telefonok felügyeletének beállítása | Microsoft Intune"
description: "Mobileszközök felügyeletének (MDM) engedélyezése, Microsoft Intune-nal rendelkező Windows 10 Mobile- vagy Windows Phone-eszközökhöz."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0b4bf6aa6fa9d693c0458562e7fcb71fc8000bb4
ms.openlocfilehash: 46bd457af51d3fac513cfc36af1766e1e37222cd


---


# Windows Phone és Windows 10 Mobile rendszerű telefonok Microsoft Intune-beli felügyeletének beállítása

Intune-rendszergazdaként kétféleképpen engedélyezheti a Windows 10 Mobile és Windows Phone rendszerű eszközök regisztrációját és felügyeletét:

- **[Automatikus regisztrálás az Azure Active Directoryval](#azure-active-directory-enrollment)** - a Windows 10- és Windows 10 Mobile-felhasználók a regisztrálni kívánt eszközhöz hozzáadnak egy munkahelyi vagy iskolai fiókot
- **[Regisztráció a Vállalati portállal](#company-portal-app-enrollment)** - a Windows Phone 8.1-es és újabb verziójú eszközök regisztrálása úgy történik, hogy a felhasználók letöltik és telepítik a Vállalati portál alkalmazást, majd abban megadják a munkahelyi vagy iskolai fiókjuk hitelesítő adatait.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Regisztráció a Vállalati portál alkalmazással
Engedélyezheti a felhasználók számára, hogy az Intune Vállalati portál alkalmazás használatával telepítsék és regisztrálják az eszközeiket. DNS CNAME erőforrásrekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá. Ha Windows Phone 8.0 rendszerű eszközöket kezel, vagy a Vállalati portált Windows Phone-eszközökre kell telepítenie, le is kell töltenie a Vállalati portál alkalmazást, és be kell jelentkeznie. Lásd: [Windows Phone 8.0 rendszerű telefonok kezelésének beállítása](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Az Intune beállítása**<br>Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként (MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority), valamint beállítja a mobileszköz-kezelést.

2.  **CNAME rekordok létrehozása** (nem kötelező)<br>Hozza létre a megfelelő **CNAME** DNS-erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat a manage.microsoft.com webhelyre. Több ellenőrzött tartomány esetén minden tartományhoz külön CNAME rekordot kell létrehozni. A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

  |TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 óra|

  `EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynév használatával irányítja át a felhasználókat az Intune-ba.

  `EnterpriseRegistration.windows.net` – Azokat a Windows 8.1 és Windows 10 Mobile rendszerű eszközöket támogatja, amelyeket a munkahelyi vagy iskolai fiókkal az Azure Active Directoryban fognak regisztrálni

  Ha a vállalat több tartományt használ a felhasználók hitelesítő adataihoz, akkor minden egyes tartományhoz hozzon létre CNAME rekordot.

  Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az EnterpriseEnrollment-s.manage.microsoft.com webhelyre. A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

3.  **A CNAME ellenőrzése**<br>Az[Intune felügyeleti konzoljában](http://manage.microsoft.com) válassza a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows Phone** lehetőséget. Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

    ![Windows mobileszköz-felügyeletének beállítása párbeszédpanel](../media/windows-phone-enrollment.png)

4.  **Nem kötelező lépések**<br>A **Tesztcélú telepítés kulcsainak hozzáadása** lépésre nincs szükség Windows 10 esetén. A **Kódaláíró tanúsítvány feltöltése** lépésre csak akkor van szükség, ha a Windows Áruházból nem elérhető üzletági (LOB) alkalmazásokat kíván terjeszteni. [További információ](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

5.  **A felhasználók tájékoztatása**<br>A felhasználóknak tudniuk kell, hogy miként regisztrálhatják az eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-kezelésbe bevont eszközeiken.
    - [Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Végfelhasználói útmutató Windows-eszközökhöz](../enduser/using-your-windows-device-with-intune.md)

Nincs további feladata, kivéve, ha az eszközökre telepíti a Vállalati portált.  A felügyeleti konzol 2. és 3. lépése biztonsággal figyelmen kívül hagyható.



<!--HONumber=Oct16_HO3-->


