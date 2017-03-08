---
title: "macOS-eszköz regisztrálása az Intune-ban | Microsoft Docs"
description: "A cikk bemutatja, hogyan lehet regisztrálni a macOS rendszerű eszközöket az Intune-ban."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- User help
ROBOTS: 
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: e2a507ff6f803cf022536824ca2f12f6d6a64d75
ms.openlocfilehash: 4b532299070bdb8ddf0e9de1e6b598e8dcd8ffb3
ms.lasthandoff: 02/24/2017


---

# <a name="enroll-your-macos-device-in-intune"></a>macOS-eszköz regisztrálása az Intune-ban

Munkájának elvégzéséhez hozzá kell férnie munkahelyének alkalmazásaihoz, adataihoz és erőforrásaihoz. Ha macOS-eszközt használ a munkahelyén, akkor ez egy __felügyeleti profil__ telepítését követeli meg. Ez egyszerűen egy olyan fájl, amelyet a cég rendszergazdája állított össze, és betölti a beállításokat és a hozzáférési adatokat a Mac gépre. Szeretne még többet megtudni? Ebben a cikkben elolvashatja, [mi történik a Céges portál alkalmazás telepítésekor és az eszköz Intune-beli regisztrálásakor](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

  > [!NOTE]
  > Ha valójában egy iOS-eszközt (iPhone-t vagy iPadet) szeretne regisztrálni, [ezt az útmutatást kövesse](enroll-your-device-in-intune-ios.md).

1. A __Dock__ területén keresse meg a __Safari__ böngészőt, nyisson meg egy új ablakot, majd keresse fel a [Munkahelyi portál webhelyét](http://portal.manage.microsoft.com).
2. Jelentkezzen be a Munkahelyi portál webhelyre a munkahelyi vagy az iskolai fiókjával.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Bejelentkezés után látni fogja az elérhető __Kezdőlap__, __Alkalmazások__ és __Kategóriák__ lapokat. Ezen a lapon jelennek meg a telepítéshez rendelkezésre álló alkalmazások. Ha még nincs regisztrált eszköze, a következő figyelmeztetés jelenik meg: **Nem lehet megjeleníteni alkalmazásokat.** Lépjen tovább a __Saját eszközök__ elem kiválasztásával.

 ![Képernyőkép a webes portál kezdőlapjáról, amelyen látható, hogy még nincsenek telepíthető alkalmazások. Alul a Saját eszközök gomb jelenik meg.](./media/macOS_enroll_001_landing_page.png)

4. A __Saját eszközök__ lapon a regisztrált eszközök listája vagy egy szalagcím látható. A megjelenített tartalom attól függ, hogy Önnek van-e már macOS vagy egyéb rendszerű regisztrált eszköze. A listán nem szereplő eszközök regisztrálásához válassza a következő feliratú szalagcímet: __Ha az eszköz szerepel a listán, koppintson ide az azonosításhoz. Akkor is koppintson ide, ha a listán nem szereplő eszközt szeretne regisztrálni__.

  ![Képernyőkép a Saját eszköz lapról, amelyen különböző azonosítatlan eszközök láthatók a listán nem szereplő eszközök regisztrálását vagy az azonosítatlan eszközök azonosítását felajánló szalagcím felett.](./media/macOS_enroll_002_tap_here_banner.png)

5. Megjelenik egy másik előugró ablak, amely röviden elmagyarázza, hogy miért kell __azonosítania vagy regisztrálnia ezt az eszközt__. Olvassa el, majd lépjen tovább a __Regisztrálás__ gombra kattintva.

 ![Eszköz azonosítása vagy regisztrálása macOS](./media/macOS_enroll_003_IDenroll_popup.png)

6. Megjelenik egy másik előugró ablak, amely röviden elmagyarázza, hogy mi fog történni, ha Ön __regisztrálja ezt az eszközt__. Olvassa el a tudnivalókat, majd lépjen tovább az __Install__ (Telepítés) gombra kattintva.

 ![Az eszköz regisztrálása macOS](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > Az Intune-nak hozzá kell férnie a számítógépéhez, enélkül nem tud meggyőződni arról, hogy elég biztonságos-e az eszköz a vállalat erőforrásainak eléréséhez. Ebből a cikkből megtudhatja, [mi történik, ha regisztrálja az eszközt az Intune-ban](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

7. Megnyílik a __System Preferences__ (Rendszerbeállítások) terület. A rendszer rákérdez, hogy __telepíteni szeretné-e a felügyeleti profilt?__ A továbblépéshez kattintson az __Install__ (Telepítés) gombra. Ha további részleteket szeretne, kattintson a __Show Profile__ (Profil megjelenítése) gombra.

 ![A felügyeleti profil telepítése](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Megjelenik a macOS egy előugró ablaka. Erősítse meg, hogy valóban el szeretné végezni a módosításokat. Ehhez adja meg a számítógép __felhasználónevét__ és __jelszavát__, majd kattintson az __OK__ gombra. Ennek hatására a felügyeleti profil települ a Mac gépre.

 ![A macOS profiltelepítési előugró ablaka](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. A Mac további üzeneteket is megjeleníthet a profil részleteiről, illetve arról, hogy biztosan __telepíti__-e. Lépjen tovább az üzenetek __Continue__ (Folytatás) és __Install__ (Telepítés) gombjára kattintva. A telepítés befejeződése után láthatja az újonnan telepített __felügyeleti profilt__ az __eszközprofilok__ listájában.

 ![A telepített macOS-profil](./media/macOS_enroll_007_sysprefs_installed_profile.png)

További segítségre van szüksége? Érdeklődjön munkahelye rendszergazdájától. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](http://portal.manage.microsoft.com).

