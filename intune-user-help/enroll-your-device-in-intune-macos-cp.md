---
title: macOS-eszköz Céges portálon való regisztrálása az Intune-ban | Microsoft Docs
description: A cikk azt mutatja be, hogyan regisztrálhatók macOS-eszközök az Intune-ban a Céges portál alkalmazással
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 3dac9446d7a1097f5be4d0851cd78e8cbb86cc4e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831797"
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>A macOS-eszköz Céges portál alkalmazással való regisztrálása az Intune-ban

A szervezet alkalmazásaihoz, adataihoz és erőforrásaihoz való hozzáférés megkönnyíti a munkavégzést. A szervezet az Intune-t [azon erőforrásokhoz való hozzáférés kezelésére](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md) használja, amelyekhez a macOS-hez készült Céges portál alkalmazás letöltése szükséges. Ezek az utasítások az OS X El Capitan 10.11 vagy újabb rendszerű macOS-eszközök esetében működnek.


1. A __Dock__ területén keresse meg a __Safari__ böngészőt, nyisson meg egy új ablakot, majd keresse fel a [Munkahelyi portál webhelyét](https://portal.manage.microsoft.com).

2. Jelentkezzen be a Munkahelyi portál webhelyre a munkahelyi vagy az iskolai fiókjával.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. Bejelentkezés után kattintson az oldal jobb felső sarkában található **Menü**re, és válassza a **Saját eszközök** elemet.

   ![Képernyőkép a webes portál kezdőlapjáról, amelyen látható, hogy még nincsenek telepíthető alkalmazások. Alul a Saját eszközök gomb jelenik meg.](./media/macOS_enroll_001_landing_page.png)

4. A __Saját eszközök__ lapon a regisztrált eszközök listája vagy egy szalagcím látható. A megjelenített tartalom attól függ, hogy Önnek van-e már macOS vagy egyéb rendszerű regisztrált eszköze. A listán nem szereplő eszközök regisztrálásához válassza a következő feliratú szalagcímet: __Ha az eszköz szerepel a listán, koppintson ide az azonosításhoz. Akkor is koppintson ide, ha a listán nem szereplő eszközt szeretne regisztrálni__. Ha nincs regisztrált eszköze, a szalagcímen ez a szöveg lesz látható: **Önnek nincsenek regisztrált eszközei. Ezt az eszközt ide kattintva regisztrálhatja.**

    ![Képernyőkép a Saját eszköz lapról, amelyen különböző azonosítatlan eszközök láthatók a listán nem szereplő eszközök regisztrálását vagy az azonosítatlan eszközök azonosítását felajánló szalagcím felett.](./media/macOS_enroll_002_tap_here_banner.png)

5. A regisztráció folytatásához töltse le macOS-eszközére a Céges portál alkalmazást.

    ![Ez az értesítés szólítja fel a felhasználót a macOS rendszerhez készült Céges portál alkalmazás letöltésére. Az értesítés szövege a jobb alsó sarokban lévő „Letöltés” feliratú gomb felett jelenik meg.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. A Mac-eszköz ellenőrzi, hogy a letöltött **CompanyPortal.pkg** fájl megnyitása biztonságos-e. Indítsa el a telepítőt és végezze el a telepítés lépéseit.

7. Miután a telepítés befejeződött, nyissa meg az **Alkalmazások** mappát vagy a **Kezdőpanelt**, majd a **Céges portált**.

8. A Mac-eszköz ekkor az alábbi szövegű üzenetet jeleníti meg: **A „CompanyPortal” az internetről letöltött alkalmazás. Biztosan megnyitja?** Kattintson a **Megnyitás** gombra.

   > [!NOTE]
   > Az Intune-nak hozzá kell férnie a számítógépéhez, enélkül nem tud meggyőződni arról, hogy elég biztonságos-e az eszköz a vállalat erőforrásainak eléréséhez. Ha a számítógép elutasítja a Céges portál alkalmazás megnyitását, próbálja meg [kikapcsolni a forgalomirányítót](https://support.apple.com/HT202491), majd ezután megnyitni az alkalmazást.

9. A Céges portál alkalmazás elsőként megjelenő képernyője arra kéri, hogy ugyanazzal a munkahelyi vagy iskolai fiókkal **jelentkezzen be**, amelyet a Céges portál webhelyére való bejelentkezéshez is használt.

10. A Céges portál megerősíti a fiókadatokat, majd megjeleníti az **Eszközök beléptetése** és az **Eszközmegfelelőség** állapotát. A megjelenő sárga háromszögek arról tájékoztatják, hogy bizonyos műveletek elvégzése válik szükségessé annak biztosítása érdekében, hogy Mac-eszköze biztonságosan használható legyen a munkahelyen. A **Kezdés** gombra kattintva elkezdheti az [eszköz felügyeletre való regisztrálását](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

11. A Mac-eszköz ekkor elkezdi a felügyeletre való regisztrálást. Előfordulhat, hogy a művelet időtartama alatt a rendszer a számítógépre vonatkozó bejelentkezési adatok megadására kéri. A regisztrációs folyamat igénybe vehet néhány percet. Ezalatt végezhet egyéb műveleteket a számítógépen. A Vállalati hozzáférés beállításának befejezése után megjelenő üzenet a folyamat lezárulásáról tájékoztat.

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog).
