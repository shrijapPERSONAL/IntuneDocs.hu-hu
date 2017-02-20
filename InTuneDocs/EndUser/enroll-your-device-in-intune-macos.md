---
title: "macOS-eszköz regisztrálása az Intune-ban | Microsoft Docs"
description: "A cikk bemutatja, hogyan lehet regisztrálni a macOS rendszerű eszközöket az Intune-ban."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 9530eb45bf027c66c4a36e4cea1ec05c5f15a6e5
ms.openlocfilehash: 60879acf553934d246c662060e3d57ec50c51658


---

# <a name="enroll-your-macos-device-in-intune"></a>macOS-eszköz regisztrálása az Intune-ban

Munkájának elvégzéséhez hozzá kell férnie munkahelyének alkalmazásaihoz, adataihoz és erőforrásaihoz. Ha macOS-eszközt használ a munkahelyén, akkor ez egy __felügyeleti profil__ telepítését követeli meg. Ez egyszerűen egy olyan fájl, amelyet a cég rendszergazdája állított össze, és betölti a beállításokat és a hozzáférési adatokat a Mac gépre. Szeretne még többet megtudni? Ebben a cikkben elolvashatja, [mi történik a Céges portál alkalmazás telepítésekor és az eszköz Intune-beli regisztrálásakor](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

  > [!NOTE]
  > Ha valójában egy iOS-eszközt (iPhone-t vagy iPadet) szeretne regisztrálni, [ezt az útmutatást kövesse](enroll-your-device-in-intune-ios.md).

1. A __Dock__ területén keresse meg a __Safari__ böngészőt, nyisson meg egy új ablakot, majd keresse fel a [Munkahelyi portál webhelyét](http://portal.manage.microsoft.com).
2. Jelentkezzen be a Munkahelyi portál webhelyre a munkahelyi vagy az iskolai fiókjával.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Amikor bejelentkezik, láthat minden elérhető __alkalmazást__, a __saját eszközeit__ és munkahelye informatikusainak __kapcsolatfelvételi adatait__, ha rendelkezésre állnak. A lap tetején megjelenik a következő figyelmeztetés: **Either this device isn't enrolled, or the Company Portal can't identify it. (Ez az eszköz nincs regisztrálva, vagy a Munkahelyi portál nem ismeri fel.) <u>Tap Here</u> to select a different device.** (Másik eszköz kiválasztásához koppintson ide.) Kattintson a __Tap Here__ (Koppintson ide) elemre.

 ![A Munkahelyi portál macOS rendszer esetén megjelenő lapja](./media/macOS_enroll_001_landing_page.png)

4. Megjelenik egy másik előugró ablak, amely röviden elmagyarázza, hogy miért kell __azonosítania vagy regisztrálnia ezt az eszközt__. Olvassa el, majd lépjen tovább a __Regisztrálás__ gombra kattintva.

 ![Eszköz azonosítása vagy regisztrálása macOS](./media/macOS_enroll_002_IDenroll_popup.png)

5. Megjelenik egy másik előugró ablak, amely röviden elmagyarázza, hogy mi fog történni, ha Ön __regisztrálja ezt az eszközt__. Olvassa el a tudnivalókat, majd lépjen tovább az __Install__ (Telepítés) gombra kattintva.

 ![Az eszköz regisztrálása macOS](./media/macOS_enroll_003_enroll_popup.png)

  > [!NOTE]
  > Az Intune-nak hozzá kell férnie a számítógépéhez, enélkül nem tud meggyőződni arról, hogy elég biztonságos-e az eszköz a vállalat erőforrásainak eléréséhez. Ebből a cikkből megtudhatja, [mi történik, ha regisztrálja az eszközt az Intune-ban](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

6. Megnyílik a __System Preferences__ (Rendszerbeállítások) terület. A rendszer rákérdez, hogy __telepíteni szeretné-e a felügyeleti profilt?__ A továbblépéshez kattintson az __Install__ (Telepítés) gombra. Ha további részleteket szeretne, kattintson a __Show Profile__ (Profil megjelenítése) gombra.

 ![A felügyeleti profil telepítése](./media/macOS_enroll_004_sysprefs_mgmt_profile.png)

7. Megjelenik a macOS egy előugró ablaka. Erősítse meg, hogy valóban el szeretné végezni a módosításokat. Ehhez adja meg a számítógép __felhasználónevét__ és __jelszavát__, majd kattintson az __OK__ gombra. Ennek hatására a felügyeleti profil települ a Mac gépre.

 ![A macOS profiltelepítési előugró ablaka](./media/macOS_enroll_005_sysprefs_admin_login.png)

8. A Mac további üzeneteket is megjeleníthet a profil részleteiről, illetve arról, hogy biztosan __telepíti__-e. Lépjen tovább az üzenetek __Continue__ (Folytatás) és __Install__ (Telepítés) gombjára kattintva. A telepítés befejeződése után láthatja az újonnan telepített __felügyeleti profilt__ az __eszközprofilok__ listájában.

 ![A telepített macOS-profil](./media/macOS_enroll_006_sysprefs_installed_profile.png)

További segítségre van szüksége? Érdeklődjön munkahelye rendszergazdájától. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Feb17_HO2-->


