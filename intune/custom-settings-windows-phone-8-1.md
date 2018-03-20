---
title: "Egyéni Microsoft Intune-beállítások Windows Phone 8.1 rendszert futtató eszközökhöz"
titleSuffix: 
description: "Az egyéni Windows Phone 8.1-es profilokban használható beállítások ismertetése."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f45b2dd9cab0ccfd912d1f1348d90264bf8906b8
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Egyéni Microsoft Intune-eszközbeállítások Windows Phone 8.1 rendszert futtató eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune Windows Phone 8.1-es **Egyéni** profiljával olyan OMA-URI beállításokat rendelhet hozzá, melyekkel szabályozhatók a Windows Phone 8.1-es eszközök funkciói. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan beállításokat rendelhet hozzá, amelyek más Intune-szabályzatokkal nem konfigurálhatók.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Egyéni profilbeállítások Windows Phone 8.1-es eszközökhöz

1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című témakör utasításait.
2. Az **Egyéni OMA-URI-beállítások** panelen a **Hozzáadás** elemet választva adhat meg egy vagy több OMA-URI-beállítást.
3. A **Sor hozzáadása** panelen az alábbi értékeket konfigurálja az egyes beállításokhoz:
    - **Név** – Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Leírás** – Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.
    - **OMA-URI** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Adattípus** – Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc**, **Karakterlánc (XML)**, **Dátum és idő**, **Egész szám**, **Lebegőpontos szám**, **Logikai** vagy **Base64** lehetőségek közül választhat.
    - **Érték** – Adja meg a megadott OMA-URI-azonosítóhoz társítandó értéket vagy fájlt.

4. Ha elkészült, kattintson az **OK** gombra, és folytassa, ha újabb beállításokat kíván megadni.
