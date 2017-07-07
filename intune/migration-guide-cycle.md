---
title: "Egy tipikus Intune-os migrálási ciklus működése"
description: "Ez a cikk bemutatja az Intune-os migrálási ciklusok működését, és példákkal szemlélteti, hogy miként kezeli az ügyfél a migrálási ciklusokat."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70aa7155e050450a2d786a1f16e42ce2a3c77f9e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="typical-migration-cycle"></a>A szokásos migrációs ciklus

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Szokásos próbaként a szervezet informatikai részlegénél a felhasználók egy kis csoportjával kezdeni az Intune-migrálást. Emellett a szervezetnél a migrálás időkeretének meghatározásakor figyelembe kell venni olyan tényezőket, mint a csoport változásra való hajlandósága, felhasználóinak száma, bonyolultsága, követelményei, helye és az üzleti kockázat.

Az itt található példa a célcsoportok ütemezésének módját szemlélteti:

  | **A migrálás megcélzott csoportjai** | **1. időszak** | **2. időszak** | **3. időszak** | **4. időszak** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Korlátozott próbaüzemi IT-részleg (50 felhasználó) | Terv bejelentése | Utasítás a regisztrálásra | Határidő megadása | Feltételes hozzáférés kényszerítése |  |                                                        
| Bővített próbaüzemi IT-részleg (200 felhasználó) |  | Terv bejelentése | Utasítás a regisztrálásra | Határidő megadása | Feltételes hozzáférés kényszerítése | 
| 1. migrációs fázis – hozzáértő felhasználókkal (2000) |  |  | Terv bejelentése | Utasítás a regisztrálásra | Határidő megadása | 
| 2. migrációs fázis – kelet-USA |  |  |  | Terv bejelentése | Utasítás a regisztrálásra | 
| Összes régió |  |  |  |  | Terv bejelentése | 

## <a name="customer-migration-case-study"></a>Ügyfélmigrációs esettanulmány

### <a name="adatum-corporation"></a>Adatum Corporation

- Nézze meg, [hogyan hajtotta végre az Adatum Corporation a migrációs folyamatot egy külső MDM-szolgáltatótól az Intune-ba](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Áttelepítés figyelése

A Microsoft Intune számos módot biztosít a migrálás figyelésére:

1.  Intune-beli felhasználóicsoport-nézetek

2.  Beépített jelentések és

3.  konzolon belüli riasztások készlete.

Kövesse nyomon, hogy hány felhasználó regisztrálta eszközeit az egyes fázisok után:

-   Értékelje a kommunikációs terv hatékonyságát.

-   Becsülje fel a feltételes hozzáférés kényszerítésének hatását.


## <a name="post-migration"></a>Áttelepítés után

Az Intune-ba való migrálás után vonja ki az előző MDM-szolgáltatót és mondja le a szolgáltatást. Ezenfelül az MDM-szolgáltató utasításait követve el kell távolítania az infrastruktúrával kapcsolatos felesleges követelményeket.
