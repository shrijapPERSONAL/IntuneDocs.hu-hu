---
title: "Windowsos eszközök kezelésének beállítása a Microsoft Intune-ban | Microsoft Intune"
description: "Mobileszközök felügyeletének (MDM) engedélyezése a Microsoft Intune-nal windowsos számítógépek esetén, beleértve a Windows 10-eszközöket is."
keywords: 
author: staciebarker
manager: stabar
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f28cce75626df1115283dc98547adcb97ee1cb4
ms.openlocfilehash: 9929294dd93e7bad47e6674ccafab0c036a1f89c


---

# <a name="set-up-windows-device-management"></a>Windowsos eszközök kezelésének beállítása

Intune-rendszergazdaként kétféleképpen engedélyezheti a Windows rendszerű számítógépek regisztrációját és felügyeletét:

- **[Automatikus regisztrálás az Azure AD-vel](#azure-active-directory-enrollment)** - a Windows 10- és Windows 10 Mobile-felhasználók a regisztrálni kívánt eszközhöz hozzáadnak egy munkahelyi vagy iskolai fiókot
- **[Regisztráció a Vállalati portállal](#company-portal-app-enrollment)** - a Windows 8.1-es és újabb verziójú eszközök regisztrálása úgy történik, hogy a felhasználók letöltik és telepítik a Vállalati portál alkalmazást, majd abban megadják a munkahelyi vagy iskolai fiókjuk hitelesítő adatait.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>A Vállalati portál alkalmazással való regisztráció beállítása
Engedélyezheti a felhasználók számára, hogy telepítsék és regisztrálják eszközeiket az Intune Vállalati portál alkalmazás használatával. DNS CNAME erőforrásrekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá.

1. **Az Intune beállítása**<br>
Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként (MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority), valamint beállítja a mobileszköz-kezelést.

2. **CNAME rekordok létrehozása** (nem kötelező)<br>Hozza létre a megfelelő **CNAME** DNS-erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az enterpriseenrollment-s.manage.microsoft.com webhelyre.

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

  ![Windowsos eszközök kezelése párbeszédpanel](../media/enroll-intune-winenr.png)

4.  **Nem kötelező lépések**<br>A **Tesztcélú telepítés kulcsainak hozzáadása** lépésre nincs szükség Windows 10 esetén. A **Kódaláíró tanúsítvány feltöltése** lépésre csak akkor van szükség, ha a Windows Áruházból nem elérhető üzletági (LOB) alkalmazásokat kíván terjeszteni.

6.  **Tájékoztatnia kell a felhasználókat arról, hogy miként regisztrálhatják az eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-kezelésbe bevont eszközeiken.**

    A végfelhasználói regisztrációra vonatkozó utasításokért lásd: [Windows-eszköz regisztrálása az Intune-ban](../enduser/enroll-your-device-in-intune-windows.md).

    A végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:
      - [Információk végfelhasználóknak a Microsoft Intune használatáról](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Végfelhasználói útmutató Windows-eszközökhöz](../enduser/using-your-windows-device-with-intune.md)

### <a name="see-also"></a>További információ
[A Microsoft Intune-beli eszközregisztráció előfeltételei](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO3-->


