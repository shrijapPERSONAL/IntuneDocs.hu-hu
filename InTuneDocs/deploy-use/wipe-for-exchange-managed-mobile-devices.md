---
title: "Exchange-felügyelet alatt álló mobileszközök törlése | Microsoft Docs"
description: "A Microsoft Intune lehetővé teszi az Exchange ActiveSync (EAS) által felügyelt mobileszközök tartalmának törlését vagy alaphelyzetbe állítását az Intune Exchange Connector segítségével"
keywords: 
author: staciebarker
ms.author: staciebarker
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
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 5f8da4e28f3b680d7b5b42c1c54fac4c9c43fbe2
ms.lasthandoff: 12/10/2016


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune lehetővé teszi az Exchange ActiveSync (EAS) által felügyelt mobileszközök tartalmának törlését vagy alaphelyzetbe állítását az Intune Exchange Connector segítségével. A következő táblázat az Exchange ActiveSync törlési képességeit ismerteti:

|Törlés típusa|Windows 8.1 és Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Teljes törlés|Eltávolítja az e-mail fiókot és a gyorsítótárazott e-maileket.|Gyári beállítások visszaállítása|Gyári beállítások visszaállítása.|
|Szelektív törlés/e-mail|Eltávolítja az e-mail-fiókot.|Nem támogatott.|Nem támogatott.|
|Szelektív törlés/szabályzatok|Eltávolítja a házirendek betartatását, de a beállítások nem változnak|Eltávolítja a szabályzatok betartatását, de a beállítások nem változnak.|Eltávolítja a szabályzatok betartatását, de a beállítások nem változnak.|

