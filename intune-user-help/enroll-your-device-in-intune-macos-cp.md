---
title: "macOS-eszköz Céges portálon való regisztrálása az Intune-ban | Microsoft Docs"
description: "A cikk azt mutatja be, hogyan regisztrálhatók macOS-eszközök az Intune-ban a Céges portál alkalmazással"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: b40801633a130ac79b0ae5b4e1669320c70909e2
ms.sourcegitcommit: db7a7bbead3a3fa78c4d643607f709a2909eb608
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/28/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>A macOS-eszköz Céges portál alkalmazással való regisztrálása az Intune-ban

[!INCLUDE[macos-preview-1708](./includes/macos-preview-1708.md)]

A szervezet alkalmazásaihoz, adataihoz és erőforrásaihoz való hozzáférés megkönnyíti a munkavégzést. A szervezet az Intune-t [azon erőforrásokhoz való hozzáférés kezelésére](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md) használja, amelyekhez a macOS-hez készült Céges portál alkalmazás letöltése szükséges. Ezek az utasítások az OS X El Capitan 10.11 vagy újabb rendszerű macOS-eszközök esetében működnek.

  > [!NOTE]
  > Ha iOS-eszközt (iPhone-t vagy iPadet) szeretne regisztrálni, [ezt az útmutatást kövesse inkább](enroll-your-device-in-intune-ios.md).

1.  A __Dock__ menüben keresse meg a __Safarit__, majd nyissa meg az [aka.ms/macoscompanyportal](https://aka.ms/macoscompanyportal) címet. 

2. Töltse le az alkalmazást. A Mac-eszköz ellenőrzi, hogy a letöltött **CompanyPortal.dmg** fájl megnyitása biztonságos-e. Miután megnyitotta a fájlt a **Letöltések** mappában, húzza át a **CompanyPortal** alkalmazást az **Alkalmazások** mappába.

3. Nyissa meg az **Alkalmazások** mappát vagy a **Kezdőpanelt**, majd a **Céges portált**.

4. A Mac-eszköz ekkor az alábbi szövegű üzenetet jeleníti meg: **A „CompanyPortal” az internetről letöltött alkalmazás. Biztosan megnyitja?** Kattintson a **Megnyitás** gombra.

  > [!NOTE]
  > Az Intune-nak hozzá kell férnie a számítógépéhez, enélkül nem tud meggyőződni arról, hogy elég biztonságos-e az eszköz a vállalat erőforrásainak eléréséhez. Ha a számítógép elutasítja a Céges portál alkalmazás megnyitását, próbálja meg [kikapcsolni a forgalomirányítót](https://support.apple.com/HT202491), majd ezután megnyitni az alkalmazást.

6. A Céges portál alkalmazás elsőként megjelenő képernyője arra kéri, hogy ugyanazzal a munkahelyi vagy iskolai fiókkal **jelentkezzen be**, amelyet a Céges portál webhelyére való bejelentkezéshez is használt.

7. A Céges portál megerősíti a fiókadatokat, majd megjeleníti az **Eszközök beléptetése** és az **Eszközmegfelelőség** állapotát. A megjelenő sárga háromszögek arról tájékoztatják, hogy bizonyos műveletek elvégzése válik szükségessé annak biztosítása érdekében, hogy Mac-eszköze biztonságosan használható legyen a munkahelyen. A **Kezdés** gombra kattintva elkezdheti az [eszköz felügyeletre való regisztrálását](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

8. A Mac-eszköz ekkor elkezdi a felügyeletre való regisztrálást. Előfordulhat, hogy a művelet időtartama alatt a rendszer a számítógépre vonatkozó bejelentkezési adatok megadására kéri. A regisztrációs folyamat igénybe vehet néhány percet. Ezalatt végezhet egyéb műveleteket a számítógépen. A Vállalati hozzáférés beállításának befejezése után megjelenő üzenet a folyamat lezárulásáról tájékoztat.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. A kapcsolatfelvételi adatait megtalálja a [Munkahelyi portál webhelyén](https://portal.manage.microsoft.com).
