---
title: "Windows 10 Mobile és Windows Phone rendszerű telefonok felügyeletének beállítása | Microsoft Intune"
description: "Mobileszközök felügyeletének (MDM) engedélyezése, Microsoft Intune-nal rendelkező Windows 10 Mobile- vagy Windows Phone-eszközökhöz."
keywords: 
author: staciebarker
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 66d533d094a12239ca4ed1a30f9ce3a06e5cece1


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Windows Phone és Windows 10 Mobile rendszerű telefonok Microsoft Intune-beli felügyeletének beállítása

Intune-rendszergazdaként kétféleképpen engedélyezheti a Windows 10 Mobile és Windows Phone rendszerű eszközök regisztrációját és felügyeletét:

- **[Automatikus regisztrálás az Azure Active Directoryval](#azure-active-directory-enrollment)** - a Windows 10- és Windows 10 Mobile-felhasználók a regisztrálni kívánt eszközhöz hozzáadnak egy munkahelyi vagy iskolai fiókot
- **[Regisztráció a Vállalati portállal](#company-portal-app-enrollment)** - a Windows Phone 8.1-es és újabb verziójú eszközök regisztrálása úgy történik, hogy a felhasználók letöltik és telepítik a Vállalati portál alkalmazást, majd abban megadják a munkahelyi vagy iskolai fiókjuk hitelesítő adatait.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Regisztráció a Vállalati portál alkalmazással
Engedélyezheti a felhasználók számára, hogy az Intune Vállalati portál alkalmazás használatával telepítsék és regisztrálják az eszközeiket. DNS CNAME erőforrásrekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá.

1.  **Az Intune beállítása**<br>Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként (MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority), valamint beállítja a mobileszköz-kezelést.

2.  **CNAME rekordok létrehozása** (nem kötelező)<br>Hozza létre a megfelelő **CNAME** DNS-erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre. 

    Amennyiben jelenleg a DNS rendszerben található olyan CNAME rekord, amelyik átirányítja az EnterpriseEnrollment.contoso.com címet a manage.microsoft.com címre, javasolt azt lecserélni egy olyan CNAME rekordra, amelyik az enterpriseenrollment-s.manage.microsoft.com címre irányítja át az EnterpriseEnrollment.contoso.com címet. Ez a módosítás azért ajánlott, mert a regisztrációkhoz használt manage.microsoft.com végpontot egy későbbi kiadásban kivezetjük.

    Több ellenőrzött tartomány esetén minden tartományhoz külön CNAME rekordot kell létrehozni. A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

  |TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.munkahelyi_tartomány.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
  |CNAME|EnterpriseRegistration.munkahelyi_tartomány.com|EnterpriseRegistration.windows.net|1 óra|

  `EnterpriseEnrollment-s.manage.microsoft.com` – A levelezési tartomány nevéből felismert tartománynévvel irányítja át a felhasználókat az Intune-ba.

  `EnterpriseRegistration.windows.net` – Azokat a Windows 8.1 és Windows 10 Mobile rendszerű eszközöket támogatja, amelyeket a munkahelyi vagy iskolai fiókkal az Azure Active Directoryban fognak regisztrálni.

  Ha a vállalat több tartományt használ a felhasználók hitelesítő adataihoz, akkor minden egyes tartományhoz hozzon létre CNAME rekordot.

  Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az EnterpriseEnrollment-s.manage.microsoft.com webhelyre. A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

3.  **A CNAME ellenőrzése**<br>Az[Intune felügyeleti konzoljában](http://manage.microsoft.com) válassza a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows Phone** lehetőséget. Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

    ![Windows mobileszköz-felügyeletének beállítása párbeszédpanel](../media/windows-phone-enrollment.png)

4.  **Nem kötelező lépések**<br>A **Tesztcélú telepítés kulcsainak hozzáadása** lépésre nincs szükség Windows 10 esetén. A **Kódaláíró tanúsítvány feltöltése** lépésre csak akkor van szükség, ha a Windows Áruházból nem elérhető üzletági (LOB) alkalmazásokat kíván terjeszteni.

5.  **Mondja el a felhasználóknak, miként regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez.**

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](../enduser/enroll-your-device-in-intune-windows.md). Emellett a következő helyre is küldheti a felhasználókat: [Milyen adatokhoz jut hozzá a rendszergazda, ha regisztrálom az eszközömet az Intune-ban?](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

    Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:
    - [Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Végfelhasználó útmutató Windows-eszközökhöz](../enduser/using-your-windows-device-with-intune.md)

Nincs további feladata, kivéve, ha az eszközökre telepíti a Vállalati portált.  A felügyeleti konzol 2. és 3. lépése biztonsággal figyelmen kívül hagyható.



<!--HONumber=Nov16_HO2-->


