---
title: Az eszközök és alkalmazások életciklusának áttekintése
titleSuffix: Microsoft Intune
description: Az eszközök és alkalmazások életciklusának áttekintése a Microsoft Intune-nal.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38e08253-14a0-4cc4-87be-7b110c12a523
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c358fff91744335080a10d45c7753293911430ae
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="overview-of-device-and-app-lifecycles"></a>Az eszközök és alkalmazások életciklusának áttekintése

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Habár az egyes szervezetek igényei eltérőek lehetnek, vannak olyan közös lépések, melyeket minden szervezetnek folyamatosan végre kell hajtania a mobileszközök és mobilalkalmazások kezelésének érdekében. Ezek két fő kategóriába sorolhatók, melyeket **életciklusoknak** nevezünk. A követendő telepítési életciklus attól függ, hogy milyen helyzet kezelési feltételeit próbálja megteremteni. Előfordulhat például, hogy csak az eszközéletciklusra vagy csak az alkalmazás-életciklusra van szüksége, illetve az is, hogy mindkettőre.

![A mobileszköz-kezelési és mobilalkalmazás-kezelési életciklus](./media/device-app-lifecycle.png)

Felügyeleti szempontból minden eszköz rendelkezik életciklussal. Ez az eszköz regisztrálásakor kezdődik, és annak kivonásáig tart. Az [eszközfelügyeleti életciklus](device-lifecycle.md) végigvezeti Önt az eszköz regisztrálásán, annak konfigurálásán és védelmén, majd felügyeletének megszüntetésén.

Hasonlóképpen, a használt alkalmazásoknak is megvan a saját [alkalmazás-életciklusuk](app-lifecycle.md). Ennek lépcsőfokai az alkalmazásnak az Intune-ba való felvételétől az eltávolításáig, vagyis szükségtelenné válásáig tartanak.
