---
title: Egy tipikus Intune-os migrálási ciklus működése
titleSuffix: Microsoft Intune
description: Ez a cikk bemutatja a Microsoft Intune-os migrálási ciklusok működését, és példákkal szemlélteti, hogy miként kezelheti azokat.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 87e5ac06e93027b577d42b27e7d15b9b18e11020
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67046364"
---
# <a name="typical-migration-cycle"></a>A szokásos migrációs ciklus

Szokásos próbaként a szervezet informatikai részlegénél a felhasználók egy kis csoportjával kezdeni az Intune-migrálást. Emellett a szervezetnél a migrálás időkeretének meghatározásakor figyelembe kell venni olyan tényezőket, mint a csoport változásra való hajlandósága, felhasználóinak száma, bonyolultsága, követelményei, helye és az üzleti kockázat.

Az itt található példa a célcsoportok ütemezésének módját szemlélteti:

  | **A migrálás megcélzott csoportjai** | **1. időszak** | **2. időszak** | **3. időszak** | **4. időszak** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Korlátozott próbaüzemi IT-részleg (50 felhasználó) | Terv bejelentése | Utasítás a regisztrálásra | Határidő megadása | Feltételes hozzáférés kényszerítésére |  |                                                        
| Bővített próbaüzemi IT-részleg (200 felhasználó) |  | Terv bejelentése | Utasítás a regisztrálásra | Határidő megadása | Feltételes hozzáférés kényszerítésére |
| 1. migrációs fázis – hozzáértő felhasználókkal (2000) |  |  | Terv bejelentése | Utasítás a regisztrálásra | Határidő megadása |
| 2. migrációs fázis – kelet-USA |  |  |  | Terv bejelentése | Utasítás a regisztrálásra |
| Összes régió |  |  |  |  | Terv bejelentése |

## <a name="customer-migration-case-study"></a>Ügyfélmigrációs esettanulmány

### <a name="adatum-corporation"></a>Adatum Corporation

Nézze meg, [hogyan hajtotta végre az Adatum Corporation a migrációs folyamatot egy külső MDM-szolgáltatótól az Intune-ba](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Áttelepítés figyelése

Az Intune számos módot biztosít a migrálás figyelésére:

* Intune-beli felhasználóicsoport-nézetek

* Beépített jelentések

* Konzolon belüli riasztások

Kövesse nyomon, hogy hány felhasználó regisztrálta eszközeit az egyes fázisok után:

-   Értékelje a kommunikációs terv hatékonyságát.

-   Becsülje meg a feltételes hozzáférés kényszerítésének hatását.


## <a name="post-migration"></a>Áttelepítés után

Az Intune-ba való migrálás után vonja ki az előző MDM-szolgáltatót és mondja le a szolgáltatást. Ezenfelül az MDM-szolgáltató utasításait követve távolítsa el az infrastruktúrával kapcsolatos felesleges követelményeket.
