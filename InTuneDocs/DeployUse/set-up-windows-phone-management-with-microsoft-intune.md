---
title: "Windows 10 Mobile és Windows Phone rendszerű telefonok felügyeletének beállítása | Microsoft Intune"
description: "Mobileszközök felügyeletének (MDM) engedélyezése, Microsoft Intune-nal rendelkező Windows 10 Mobile- vagy Windows Phone-eszközökhöz."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 06d6c8ce97ba6a259055e94f0eba87f7c5a96531
ms.openlocfilehash: 344f1cf4367deb12288f9c361e043d345f9846bb


---


# Windows Phone és Windows 10 Mobile rendszerű telefonok Microsoft Intune-beli felügyeletének beállítása
A Windows-eszközök beállításához [itt](../enduser/using-your-windows-device-with-intune.md) talál segítséget.

A Windows 10 Mobile- vagy Windows Phone-eszközök Microsoft Intune-beli kezeléséhez az eszközöknek képesnek kell lenniük az Intune-nal való kommunikációra. A folyamat leegyszerűsítése érdekében létrehozhat egy DNS-rekordot, így a felhasználóknak nem kell megadniuk a kiszolgáló címét. Az alábbi lépések azt ismertetik, hogyan tudja leegyszerűsíteni a regisztrációt a felhasználók számára.  

A legtöbb esetben a felhasználók a Windows Áruházból telepíthetik a Vállalati portál alkalmazást. Ha Windows Phone 8.0 rendszerű eszközöket kezel, vagy a Vállalati portált Windows Phone-eszközökre kell telepítenie, le is kell töltenie a Vállalati portál alkalmazást, és be kell jelentkeznie. Lásd: [Windows Phone 8.0 rendszerű telefonok kezelésének beállítása](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Az Intune beállítása** – Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** állítja be a [mobileszköz-kezelő szolgáltatóként](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority), valamint beállítja a mobileszköz-kezelést.

2.  **A regisztrációs kiszolgáló címéhez tartozó DNS-alias beállítása** (nem kötelező)

    DNS-aliasok (CNAME rekordtípus) létrehozása megkönnyíti a felhasználóknak az eszközeik regisztrálását. Bár a CNAME DNS rekord választható a Windows-eszközök regisztrálásakor, azt javasoljuk, hogy szükség esetén hozzon létre egy vagy több rekordot a Windows-eszköz regisztrációs folyamatának egyszerűbbé tételéhez. Ha nem található CNAME rekord, az MDM-kiszolgáló nevének manuális megadása szükséges.

  1.  Hozza létre a megfelelő **CNAME** DNS-erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat a manage.microsoft.com webhelyre. Több ellenőrzött tartomány esetén minden tartományhoz külön CNAME rekordot kell létrehozni. A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

      |TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 óra|

      A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

      **EnterpriseEnrollment-s.manage.microsoft.com** – A levelezési tartomány nevéből felismert tartománynév használatával irányítja át a felhasználókat az Intune-ba.

      **EnterpriseRegistration.windows.net** – Azokat a Windows 8.1 és Windows 10 Mobile- eszközöket támogatja, amelyeket a munkahelyi vagy iskolai fiókkal az Azure Active Directoryban fognak regisztrálni.

    2.  Az [Intune felügyeleti konzoljában](http://manage.microsoft.com) válassza a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows Phone** lehetőséget.

      ![Windows mobileszköz-felügyeletének beállítása párbeszédpanel](../media/windows-device-enrollment.png)

    3.  Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

    4.  A felhasználóknak tudniuk kell, hogy miként regisztrálhatják az eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-kezelésbe bevont eszközeiken.
        - [Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](what-to-tell-your-end-users-about-using-microsoft-intune.md)
        - [Végfelhasználói útmutató Windows-eszközökhöz](../enduser/using-your-windows-device-with-intune.md)



Nincs további feladata, kivéve, ha az eszközökre telepíti a Vállalati portált.  A felügyeleti konzol 2. és 3. lépése biztonsággal figyelmen kívül hagyható.



<!--HONumber=Aug16_HO1-->


