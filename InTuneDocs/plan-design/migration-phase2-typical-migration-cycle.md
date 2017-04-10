---
title: "Egy tipikus Intune-os migrálási ciklus működése |Microsoft Docs"
description: "Ez a cikk bemutatja az Intune-os migrálási ciklusok működését, és példákkal szemlélteti, hogy miként kezeli az ügyfél a migrálási ciklusokat."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: aa8fb215772b6e8d3a913d929c030d68e363970b
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-typical-migration-cycle"></a>2. fázis: Szokásos migrálási ciklus

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

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

További információk [az Intune-migrációk figyeléséről](https://docs.microsoft.com/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports).

## <a name="post-migration"></a>Áttelepítés után

Az Intune-ba való migráció után vonja ki az előző MDM-szolgáltatót és/vagy mondja le a szolgáltatást. Ezenfelül az MDM-szolgáltató utasításait követve el kell távolítania az infrastruktúrával kapcsolatos felesleges követelményeket.

