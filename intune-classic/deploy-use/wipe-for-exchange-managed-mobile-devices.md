---
title: Exchange-felügyelet alatt álló mobileszközök törlése
description: A Microsoft Intune lehetővé teszi az Exchange ActiveSync (EAS) által felügyelt mobileszközök tartalmának törlését vagy alaphelyzetbe állítását az Intune Exchange Connector segítségével
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 753e5e9dac7199dff18d110808524f05aa669036
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

A Microsoft Intune lehetővé teszi az Exchange ActiveSync (EAS) által felügyelt mobileszközök tartalmának törlését vagy alaphelyzetbe állítását az Intune Exchange Connector segítségével. A következő táblázat az Exchange ActiveSync törlési képességeit ismerteti:


|      Törlés típusa       |              Windows 8.1 és Windows RT 8.1              |                            iOS                             |                          Android                          |
|-------------------------|----------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|        Teljes törlés        |          Eltávolítja az e-mail fiókot és a gyorsítótárazott e-maileket.           |                      Gyári beállítások visszaállítása                       |                      Gyári beállítások visszaállítása.                       |
|  Szelektív törlés/e-mail   |                  Eltávolítja az e-mail-fiókot.                  |                       Nem támogatott.                       |                      Nem támogatott.                       |
| Szelektív törlés/szabályzatok | Eltávolítja a házirendek betartatását, de a beállítások nem változnak | Eltávolítja a szabályzatok betartatását, de a beállítások nem változnak. | Eltávolítja a szabályzatok betartatását, de a beállítások nem változnak. |

