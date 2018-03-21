---
title: "Az iOS-frissítési szabályzatok konfigurálása a Microsoft Intune-ban"
titlesuffix: 
description: "Az iOS-frissítési szabályzatok konfigurálásával kikényszeríti a felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Az iOS-frissítési szabályzatok konfigurálása a Microsoft Intune-ban
Az iOS-frissítési szabályzatokkal kikényszerítheti a felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését. Konfigurálhatja, hogy mely napokon vagy időszakokban ne települjenek frissítések az eszközökön.

## <a name="configure-the-ios-update-policy"></a>Az iOS-frissítési szabályzatok konfigurálása
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
2. Az **Intune** panelen válassza a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** lehetőséget.
4. A szabályzatok panelen válassza a **Létrehozás** lehetőséget, majd adja meg a szabályzat nevét és leírását.
5. Válassza a **Beállítások** > **Konfigurálás** lehetőséget, majd adja meg, hogy mikor ne kerüljön sor az iOS-eszközökön a legújabb elérhető frissítés kényszerített telepítésére.
6. A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Frissítési szabályzat létrehozása** panelre. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.

Ekkor létrejön a profil, és megjelenik az iOS-frissítési szabályzatok listáját tartalmazó panelen.

## <a name="assign-an-ios-update-policy-to-users"></a>iOS-frissítési szabályzat hozzárendelése felhasználókhoz
Egy iOS-frissítési szabályzat felhasználókhoz történő hozzárendeléséhez válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** panelen találhatók.
1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt Azure Active Directory-biztonsági csoportokat, és hozzárendelheti azokat a szabályzathoz.
2. A **Kiválasztott csoportok** elemre kattintva nyissa meg az Azure AD-biztonsági csoportokat megjelenítő panelt.
3. Válassza a **Mentés** elemet, hogy telepítse a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök frissítési megfelelőségét.

## <a name="change-the-restricted-days-for-the-policy"></a>A korlátozott napok módosítása a szabályzatban
1. A **Szoftverfrissítések** panelen válassza az **iOS-frissítési szabályzatok** lehetőséget.
2. Válassza ki a frissíteni kívánt iOS-frissítési szabályzatot.
3. Válassza a **Tulajdonságok** > **Beállítások** lehetőséget a korlátozott napokra vonatkozó információ frissítéséhez.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Régebbi iOS-verziót futtató iOS-eszközök figyelése
<!-- 1352223 -->
Az **Elavult iOS-eszközök** jelentést a **Szoftverfrissítések** > **iOS-frissítési szabályzat** panelen lehet elérni. A jelentésben megtekintheti az iOS-frissítési szabályzatok által megcélzott felügyelt, és nem frissíthető iOS-eszközök listáját. Minden eszköz mellett látható lesz egy állapotleírás is, amelyből kiderül, hogy az adott eszköz miért nem frissült automatikusan.
