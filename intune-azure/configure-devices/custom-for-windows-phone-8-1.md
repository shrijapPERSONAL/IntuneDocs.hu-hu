---
title: "Egyéni beállítások Windows Phone 8.1-es eszközökhöz az Intune-ban | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Az egyéni Windows Phone 8.1-es profilokban használható beállítások ismertetése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: ab1ad9852b8f9145f405bb71cf52bfcb00e078f6
ms.lasthandoff: 02/16/2017


---

# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Windows Phone 8.1-es eszközökre vonatkozó egyéni beállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune Windows Phone 8.1-es **Egyéni** profiljával olyan OMA-URI beállításokat léptethet érvénybe, melyekkel szabályozhatók a Windows Phone 8.1-es eszközök funkciói. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan beállításokat telepíthet, amelyek más Intune-szabályzatokkal nem konfigurálhatók.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Egyéni profilbeállítások Windows Phone 8.1-es eszközökhöz

1. Az első lépésekhez kövesse az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](how-to-configure-custom-settings.md) című témakör utasításait.
2. OMA-URI beállításokat a **Profil létrehozása** panel **Beállítások** elemét választva adhat meg.
3. A **Sor hozzáadása** panelen az alábbi értékeket konfigurálja az egyes beállításokhoz:
    - **Név** – Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
    - **Leírás** – Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.
    - **OMA-URI** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
    - **Adattípus** – Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc**, a **Dátum és idő**, az **Egész szám**, a **Lebegőpontos szám** és a **Logikai** lehetőség közül választhat.
    - **Érték** – Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket.

4. Ha elkészült, kattintson az **OK** gombra, és folytassa, ha újabb beállításokat kíván megadni.

