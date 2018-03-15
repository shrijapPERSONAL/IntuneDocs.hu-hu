---
title: "Az iOS-frissítési szabályzatok konfigurálása a Microsoft Intune-ban"
titlesuffix: 
description: "Az iOS-frissítési szabályzatok konfigurálásával kikényszeríti a felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 2062f9cd551ec6d7f42449041e6c8de837221631
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Az iOS-frissítési szabályzatok konfigurálása a Microsoft Intune-ban
Az iOS-frissítési szabályzatokkal kikényszerítheti a felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését. Konfigurálhatja, hogy mely napokon vagy időszakokban ne települjenek frissítések az eszközökön.

## <a name="configure-the-ios-update-policy"></a>Az iOS-frissítési szabályzatok konfigurálása
1. Nyissa meg az Intune lapot az Azure Portalon.
2. Az **Intune** lapon válassza a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** lehetőséget.
4. A szabályzatok lapon válassza a **Létrehozás** lehetőséget, majd adja meg a szabályzat nevét és leírását.
5. Válassza a **Beállítások** > **Konfigurálás** lehetőséget, majd adja meg, hogy mikor ne kerüljön sor az iOS-eszközökön a legújabb elérhető frissítés kényszerített telepítésére.
6. A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Frissítési szabályzat létrehozása** lapra. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.

Ekkor létrejön a profil, és megjelenik az iOS-frissítési szabályzatok listáját tartalmazó lapon.

## <a name="assign-an-ios-update-policy-to-users"></a>iOS-frissítési szabályzat hozzárendelése felhasználókhoz
Egy iOS-frissítési szabályzat felhasználókhoz történő hozzárendeléséhez válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** lapon találhatók.
1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a lap, amelyen kiválaszthatja a kívánt Azure Active Directory-biztonsági csoportokat, és hozzárendelheti azokat a szabályzathoz.
2. Válassza a **Csoportok kiválasztása** lehetőséget az Azure AD biztonsági csoportjait megjelenítő lap megnyitásához. Válassza a **Kiválasztás** elemet, hogy telepítse a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök frissítési megfelelőségét.

## <a name="change-the-restricted-days-for-the-policy"></a>A korlátozott napok módosítása a szabályzatban
1. A **Szoftverfrissítések** lapon válassza az **iOS-frissítési szabályzatok** lehetőséget.
2. Válassza ki a frissíteni kívánt iOS-frissítési szabályzatot.
3. Válassza a **Tulajdonságok** lehetőséget, majd frissítse a korlátozott napokra vonatkozó információt.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Régebbi iOS-verziót futtató iOS-eszközök figyelése 
<!-- 1352223 -->
Az **Elavult iOS-eszközök** jelentést a **Szoftverfrissítések** > **iOS-frissítési szabályzat** lapról lehet elérni. A jelentésben megtekintheti az iOS-frissítési szabályzatok által megcélzott felügyelt, és nem frissíthető iOS-eszközök listáját. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan.