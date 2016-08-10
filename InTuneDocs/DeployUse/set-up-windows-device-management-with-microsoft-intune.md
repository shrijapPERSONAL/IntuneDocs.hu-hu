---
title: "Windowsos eszközök kezelésének beállítása a Microsoft Intune-ban | Microsoft Intune"
description: "Mobileszközök felügyeletének (MDM) engedélyezése a Microsoft Intune-nal windowsos számítógépek esetén, beleértve a Windows 10-eszközöket is."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 06d6c8ce97ba6a259055e94f0eba87f7c5a96531
ms.openlocfilehash: fae2aa496ec38d9ddc2cb6800bed10ccb32fd154


---

# Windowsos eszközök kezelésének beállítása
Windows-eszköz beállításához [itt](../enduser/using-your-windows-device-with-intune.md) talál segítséget.

Az Intune-nal megteremthetők a saját eszközök használatának (BYOD) feltételei a Windows-eszközök regisztrálásával, ezáltal gondoskodva a vállalati levelezés és erőforrások eléréséről. Az Azure Active Directoryval együtt használva ezzel gyorsan, az eszköz megérintése nélkül vonhatja felügyelet alá az új, Windows 10 rendszerű eszközöket, és szerezhet hozzáférést a vállalati erőforrásokhoz anélkül, hogy új lemezképet kellene telepíteni a számítógépre. A regisztráció után a felhasználók bejelentkezhetnek, és az Intune felügyeleti konzol segítségével eszközeiket szabályzatokkal, alkalmazásokkal és beállításokkal célozhatják. Dönthet a [Windows Phone-telefonok Microsoft Intune-beli kezelésének beállítása](set-up-windows-phone-management-with-microsoft-intune.md) mellett is, vagy [kezelheti az Intune ügyfélszoftverrel rendelkező gépeit](manage-windows-pcs-with-microsoft-intune.md) az Intune ügyfél használatával.

DNS CNAME rekord létrehozásával a felhasználók kiszolgálónév beírása nélkül tudnak csatlakozni az Intune-hoz, és regisztrálni rá.

### Windowsos eszközök kezelésének beállítása

  1.  Hozza létre a megfelelő **CNAME** DNS erőforrásrekordokat a munkahelyi tartományhoz. Ha a munkahelyi webhely címe például contoso.com, akkor olyan CNAME rekordot kell létrehoznia a DNS-ben, amely az EnterpriseEnrollment.contoso.com webhelyről átirányítja a felhasználókat az EnterpriseEnrollment-s.manage.microsoft.com webhelyre. Bár a CNAME DNS rekord választható a Windows-eszközök regisztrálásakor, azt javasoljuk, hogy szükség esetén hozzon létre egy vagy több rekordot a Windows-eszköz regisztrációs folyamatának egyszerűbbé tételéhez. Ha nem található CNAME rekord, az MDM-kiszolgáló nevének manuális megadása szükséges.

  Több ellenőrzött tartomány esetén minden tartományhoz külön CNAME rekordot kell létrehozni. A CNAME erőforrásrekordoknak a következő adatokat kell tartalmazniuk:

  |TÍPUS|Gazdagép neve|A következő helyre mutat|Élettartam|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 óra|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 óra|

  A DNS-rekord módosításának terjesztése akár 72 órát is igénybe vehet. Az Intune-ban nem ellenőrizhető a DNS-módosítás, amíg a DNS-rekord propagálása zajlik.

  **EnterpriseEnrollment-s.manage.microsoft.com** – A levelezési tartomány nevéből felismert tartománynév használatával irányítja át a felhasználókat az Intune-ba.

  **EnterpriseRegistration.windows.net** – Azokat a Windows 8.1 és Windows 10 Mobile- eszközöket támogatja, amelyeket a munkahelyi vagy iskolai fiókkal az Azure Active Directoryban fognak regisztrálni.

  2.  Az [Intune felügyeleti konzolon](http://manage.microsoft.com) kattintson a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows** lehetőségre.
  ![Windowsos eszközök kezelése párbeszédpanel](../media/enroll-intune-winenr.png)

  3.  Írja be a munkahelyi webhely ellenőrzött tartományának URL-címét az **Adja meg egy ellenőrzött tartomány nevét** mezőbe, majd kattintson az **Automatikus észlelés tesztelése** elemre.

  4.  A felhasználóknak tudniuk kell, hogy miként regisztrálhatják az eszközeiket, és milyen szolgáltatásokat vehetnek majd igénybe a mobileszköz-kezelésbe bevont eszközeiken.
      - [Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Végfelhasználó útmutató Windows-eszközökhöz](../enduser/using-your-windows-device-with-intune.md)

### További információ
[Felkészülés az eszközök regisztrálására a Microsoft Intune-ban](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


