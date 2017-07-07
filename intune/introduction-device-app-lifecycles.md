---
title: "Az eszközök és alkalmazások életciklusának áttekintése"
description: "Az eszközök és alkalmazások életciklusának áttekintése az Intune-nal."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38e08253-14a0-4cc4-87be-7b110c12a523
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc02af1e0813580ed70f181ff401d0408f6dd082
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="overview-of-device-and-app-lifecycles"></a>Az eszközök és alkalmazások életciklusának áttekintése

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Habár az egyes szervezetek igényei eltérőek lehetnek, vannak olyan közös lépések, melyeket minden szervezetnek folyamatosan végre kell hajtania, egyéb működési igényeiktől függetlenül. Ezek két fő kategóriába sorolhatók, melyeket **életciklusoknak** nevezünk. A követendő telepítési életciklus attól függ, hogy milyen helyzet kezelési feltételeit próbálja megteremteni. Előfordulhat például, hogy csak az eszközéletciklusra vagy csak az alkalmazás-életciklusra van szüksége, illetve az is, hogy mindkettőre.

![Az MDM és az alkalmazás-életciklus](./media/device-app-lifecycle.png "mobileszköz és alkalmazás-életciklus")

Felügyeleti szempontból minden eszköz rendelkezik életciklussal. Ez az eszköz regisztrálásakor kezdődik, és annak kivonásáig tart. Az [eszközfelügyeleti életciklus](device-lifecycle.md) végigvezeti Önt az eszköz regisztrálásán, annak konfigurálásán és védelmén, majd felügyeletének megszüntetésén.

Hasonlóképpen, a használt alkalmazásoknak is megvan a saját [alkalmazás-életciklusuk](app-lifecycle.md). Ennek lépcsőfokai az alkalmazásnak az Intune-ba való felvételétől az eltávolításáig, vagyis szükségtelenné válásáig tartanak.
