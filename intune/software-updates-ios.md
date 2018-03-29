---
title: Az iOS-szoftverfrissítési szabályzatok konfigurálása a Microsoft Intune-ban
titlesuffix: ''
description: Az iOS-frissítési szabályzatok konfigurálásával kikényszeríti a felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: 39432d09bea822c25ca9e11181a11a1e2298dfef
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Az iOS-frissítési szabályzatok konfigurálása a Microsoft Intune-ban

Szoftverfrissítési szabályzatokkal kikényszerítheti az iOS 10.3 vagy újabb verziójú rendszer futtató felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését. Ez a funkció csak felügyelt eszközök esetén használható. Konfigurálhatja, hogy mely napokon vagy időszakokban ne települjenek frissítések az eszközökön. 

Ha van rendelkezésre álló frissítés, amikor az eszköz kb. 8 óránként bejelentkezik, és ez nem korlátozás alá eső időpontban következik be, akkor az eszköz meg fogja próbálni letölteni és telepíteni a legújabb OS-frissítést. Az eszköz frissítéséhez nincs szükség felhasználói beavatkozásra. A szabályzat nem akadályozza meg, hogy a felhasználó frissítse az operációs rendszert.

## <a name="configure-the-ios-update-policy"></a>Az iOS-frissítési szabályzatok konfigurálása
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** lehetőséget.
4. A szabályzatok panelen válassza a **Létrehozás** lehetőséget, majd adja meg a szabályzat nevét és leírását.
5. Válassza a **Beállítások** > **Konfigurálás** lehetőséget, majd adja meg, hogy mikor ne kerüljön sor az iOS-eszközökön a legújabb elérhető frissítés kényszerített telepítésére. Beállíthatja a hét napjait, az időzónát, a kezdési időt és a befejezési időt.
6. A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Frissítési szabályzat létrehozása** panelre. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.

Ekkor létrejön a profil, és megjelenik az iOS-frissítési szabályzatok listáját tartalmazó panelen. Az Apple MDM nem teszi lehetővé annak kényszerítését, hogy az eszköz egy bizonyos időpontig vagy dátumig telepítse a frissítést. 

## <a name="change-the-restricted-times-for-the-policy"></a>A korlátozott időtartamok módosítása a szabályzatban

1.  A **Szoftverfrissítések** panelen válassza az **iOS-frissítési szabályzatok** lehetőséget.
2.  Válassza ki a frissíteni kívánt iOS-frissítési szabályzatot.
3.  Válassza a **Tulajdonságok** lehetőséget, majd frissítse a korlátozott időpontokra vonatkozó információt.
4.  Válassza ki a hét napjait
5.  Időzóna, amelyben ez a szabályzatot alkalmazza
6.  Kezdési és befejezési idő a feketelistára tett órákhoz

## <a name="assign-an-ios-update-policy-to-users"></a>iOS-frissítési szabályzat hozzárendelése felhasználókhoz

Egy iOS-frissítési szabályzat felhasználókhoz történő hozzárendeléséhez válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** panelen találhatók.

1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt Azure Active Directory-biztonsági csoportokat, és hozzárendelheti azokat a szabályzathoz.
2. A **Kiválasztott csoportok** elemre kattintva nyissa meg az Azure AD-biztonsági csoportokat megjelenítő panelt. Határozza meg, ki férhet hozzá a szabályzathoz, a belefoglalni és a kizárni kívánt csoportok hozzárendelésével.
3. Válassza a **Mentés** elemet, hogy telepítse a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók vagy az eszközök számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök frissítési megfelelőségét. Ez a szabályzat a felhasználó nélküli eszközöket is támogatja.

## <a name="monitor-ios-device-installation-failures"></a>IOS-eszközök telepítési hibáinak figyelése
<!-- 1352223 -->
Az **iOS-eszközök telepítési hibái** jelentést a **Szoftverfrissítések** ablaktáblán lehet elérni. A jelentésben megtekintheti azoknak a felügyelt iOS-eszközöknek a listáját, amelyekre iOS-frissítési szabályzat vonatkozik, frissítéssel próbálkoztak, és nem lehetett frissíteni őket. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan. A kifogástalan, naprakész eszközök nem jelennek meg a listában. Naprakésznek számít az a legújabb frissítés, amelyet maga az eszköz támogatni képes.
