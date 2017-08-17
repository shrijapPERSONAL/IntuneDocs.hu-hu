---
title: "iOS-frissítési szabályzatok konfigurálása"
titleSuffix: Intune on Azure
description: "Az iOS-frissítési szabályzatok konfigurálásával kikényszeríti a felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: d4af2d58ec21c54362cf451eac1a33b2088885d5
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2017
---
# <a name="configure-ios-update-policies"></a>iOS-frissítési szabályzatok konfigurálása
Az iOS-frissítési szabályzatokkal kikényszerítheti a felügyelt iOS-eszközökön a legújabb elérhető szoftverfrissítések automatikus telepítését. Konfigurálhatja, hogy mely napokon vagy időszakokban ne települjenek frissítések az eszközökön.

## <a name="configure-the-ios-update-policy"></a>Az iOS-frissítési szabályzatok konfigurálása
1. Nyissa meg az Intune panelt az Azure Portalon.
2. Az **Intune** panelen válassza a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** lehetőséget.
4. A szabályzatok panelen válassza a **Létrehozás** lehetőséget, majd adja meg a szabályzat nevét és leírását.
5. Válassza a **Beállítások** > **Konfigurálás** lehetőséget, majd adja meg, hogy mikor ne kerüljön sor az iOS-eszközökön a legújabb elérhető frissítés kényszerített telepítésére.
6. A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Frissítési szabályzat létrehozása** panelre. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.

Ekkor létrejön a profil, és megjelenik az iOS-frissítési szabályzatok listáját tartalmazó panelen.

## <a name="assign-an-ios-update-policy-to-users"></a>iOS-frissítési szabályzat hozzárendelése felhasználókhoz
Egy iOS-frissítési szabályzat felhasználókhoz történő hozzárendeléséhez válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok a **Szoftverfrissítések** > **iOS-frissítési szabályzatok** panelen találhatók.
1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt Azure Active Directory-biztonsági csoportokat, és hozzárendelheti azokat a szabályzathoz.
2. Válassza a **Csoportok kiválasztása** lehetőséget az Azure AD biztonsági csoportjait megjelenítő panel megnyitásához. Válassza a **Kiválasztás** elemet, hogy telepítse a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök frissítési megfelelőségét.

## <a name="change-the-restricted-days-for-the-policy"></a>A korlátozott napok módosítása a szabályzatban
1. A **Szoftverfrissítések** panelen válassza az **iOS-frissítési szabályzatok** lehetőséget.
2. Válassza ki a frissíteni kívánt iOS-frissítési szabályzatot.
3. Válassza a **Tulajdonságok** lehetőséget, majd frissítse a korlátozott napokra vonatkozó információt.
