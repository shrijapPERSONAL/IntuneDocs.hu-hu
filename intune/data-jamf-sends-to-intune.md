---
title: Az Intune-nak küld adatokat a JAMF Pro
titleSuffix: Microsoft Intune
description: A Microsoft Intune-bA küldi a Jamf Pro által adatok listája
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 452d6fafccc2d53d2f6940197ef4a1aa19febfc2
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61509534"
---
# <a name="data-jamf-pro-sends-to-intune"></a>A Jamf Pro által az Intune-ba küldött adatok

Ha használ [a Jamf Pro](https://www.jamf.com) kezelheti a végfelhasználók Mac számítógépek az Intune-nal, a Jamf Pro rögzíti a felügyelt macOS-eszközök eszközkészletadatait. A Jamf Pro a következő információkat továbbítja az Intune-nak:

* Azure AD-eszközazonosító
* JAMF eszközkészlet-állapot (a Jamf Pro szolgáltatásba az elmúlt 24 órán belül bejelentkezett számítógép eszközkészlet-állapota)
* Operációs rendszer verziója
* Azure AD-felhasználói azonosító
* Titkosított (FileVault 2)
* Forgalomirányító állapota
* Jelszó: Karakterkészletek minimális száma
* Jelszó lejárata (nap)
* Jelszó típusa – egyszerű, alfanumerikus, vagy ismeretlen
* Automatikus bejelentkezés tiltása
* PIN-kód minimális hossza
* Jelszó: az újrafelhasználásból kizárt korábbi jelszavak száma
* Rendszer sértetlenségének védelme
* Legutóbbi bejelentkezés
* Architektúra típusa
* Rendelkezésre álló RAM-tárhelyek
* Akkumulátor kapacitása
* Rendszerindító ROM
* Busz sebessége
* Gyorsítótár mérete
* Eszköz neve
* Csatlakozás tartományhoz
* Jamf-azonosító
* MAC-cím
* Fordítás
* Modell
* Modellazonosító
* Hálózati adapter sebessége
* Magok száma
* Processzorok száma
* Operációs rendszer
* Platform
* Processzor sebessége
* Processzor típusa
* Másodlagos MAC-cím
* Sorozatszám
* SMC verziója
* Teljes memória
* UDID
* Felhasználó e-mail-címe


A Jamf által felügyelt eszközöknek az Intune-konzolról történő eltávolításához a **Minden eszköz** nézetben kattintson a **Törlés** elemre. Az eszközök csoportos törlésére is van lehetőség: jelöljön ki több eszközt, és kattintson a **Törlés** elemre.

[A Jamf által felügyelt eszköz eltávolításáról a Jamf Pro dokumentációjában](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information) olvashat részletesebben. Ha további segítségre van szüksége, támogatási jegyet is küldhet a [Jamf támogatási szolgálatának](https://www.jamf.com/support/). 

