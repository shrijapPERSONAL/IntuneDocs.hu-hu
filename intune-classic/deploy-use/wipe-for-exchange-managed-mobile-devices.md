---
title: "Exchange-felügyelet alatt álló mobileszközök törlése | Microsoft Docs"
description: "A Microsoft Intune lehetővé teszi az Exchange ActiveSync (EAS) által felügyelt mobileszközök tartalmának törlését vagy alaphelyzetbe állítását az Intune Exchange Connector segítségével"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4b0914ab12456fd3ad5f957d68a59df9de539176
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune lehetővé teszi az Exchange ActiveSync (EAS) által felügyelt mobileszközök tartalmának törlését vagy alaphelyzetbe állítását az Intune Exchange Connector segítségével. A következő táblázat az Exchange ActiveSync törlési képességeit ismerteti:

|Törlés típusa|Windows 8.1 és Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Teljes törlés|Eltávolítja az e-mail fiókot és a gyorsítótárazott e-maileket.|Gyári beállítások visszaállítása|Gyári beállítások visszaállítása.|
|Szelektív törlés/e-mail|Eltávolítja az e-mail-fiókot.|Nem támogatott.|Nem támogatott.|
|Szelektív törlés/szabályzatok|Eltávolítja a házirendek betartatását, de a beállítások nem változnak|Eltávolítja a szabályzatok betartatását, de a beállítások nem változnak.|Eltávolítja a szabályzatok betartatását, de a beállítások nem változnak.|

