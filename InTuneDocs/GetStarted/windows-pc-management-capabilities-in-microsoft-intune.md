---
title: "Windows-számítógépek felügyeletére szolgáló funkciók | Microsoft Intune"
description: "Tudjon meg többet az Intune funkcióiról, amelyek akkor érhetők el, ha a Windows-számítógépeit az Intune-ügyfélszoftver használatával felügyeli."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 49a236359692a5bbccf9ee0bb263094434049a91
ms.openlocfilehash: f5ade985900e2387b19b4ed2786f22d8a216d8d8


---

# Windows-számítógépek felügyeletére szolgáló képességek a számítógépes Microsoft Intune ügyfélszoftverben
A legtöbb esetben célszerű regisztrálni az eszközöket az Intune-ban, ez ugyanis több funkciót biztosít, mint a számítógépes Intune ügyfélszoftver. Az Intune számítógépes ügyfélszoftverrel azonban számítógépeket is felügyelhet, és a következő funkciókat veheti igénybe:

-   **Szoftverfrissítések kezelése** – Naprakészen tarthatja a számítógépeit, és beállíthatja, hogy a rendszer mikor telepítse a frissítéseket.

-   **Windows tűzfal házirendje** – Ezzel biztosíthatja, hogy a vállalat által használt számítógépeken ne legyen inaktív vagy nem megfelelően beállított Windows tűzfal.

-   **Kártevők elleni védelem** – Az Intune Endpoint Protection védelmet használ, amely segít a számítógépek kártevők elleni védelmében.

-   **Távsegítség** – Az Intune lehetővé teszi a felhasználóknak, hogy az Intune-hoz tartozó távoli asztal szolgáltatás segítségével kapcsolatba lépjenek az informatikai támogatási csapattal (ehhez a TeamViewer szoftver szükséges).

-   **Szoftverlicenc-gazdálkodás** – Nyomon követheti az elérhető és a használatban lévő szoftverlicencek számát.
-   **Alkalmazások központi telepítése** – Szoftvereket telepíthet a felügyelt számítógépekre. A számítógépek ügyfélszoftverrel történő felügyelete esetén egyes alkalmazásfelügyeleti funkciók nem érhetők el.


Az Intune a PC-s ügyfélprogram akár 7000 Windows-eszközre való telepítését is támogatja.

## Rendszerkövetelmények
Az Intune a Windows következő verzióival rendelkező számítógépek felügyeletére alkalmas (az x86-os és az x64-es verziók felügyeletére egyaránt):


-   **Windows Vista** – Business, Enterprise és Ultimate verziók.

-   **Windows 7** – Pro, Enterprise és Ultimate verziók (szervizcsomag nélkül vagy SP1-gyel).

-   **Windows 8** – Pro és Enterprise verziók.

-   **Windows 8.1** – Pro és Enterprise verziók.

- **Windows 10** - Pro, Education és Enterprise verziók.


## Minimális hardverkövetelmények
A számítógépes Intune ügyfélszoftver a következő minimális hardverkövetelményekkel telepíthető:

|Követelmény|Részletek|
|---------------|--------------------|
|Hálózat|Az ügyfél használatához a számítógépnek internetkapcsolattal kell rendelkeznie.|
|Processzor és memória|A processzorra és a RAM-ra vonatkozó követelményeket a számítógép operációs rendszere határozza meg.|
|Lemezterület|200 MB szabad lemezterület az ügyfélszoftver telepítése előtt.|

## További követelmények
A számítógépes Intune ügyfélszoftver telepítésének szoftverkövetelményei a következők:

|Követelmény|Részletek|
|---------------|--------------------|
|Rendszergazdai engedélyek|Az ügyfélszoftvert telepítő fióknak helyi rendszergazdai engedélyekkel kell rendelkeznie a számítógépen.|
|Windows Installer 3.1|A számítógépnek legalább a Windows Installer 3.1-es verziójával kell rendelkeznie.|
|Nem kompatibilis ügyfélszoftver eltávolítása|A számítógépes Intune ügyfélszoftver telepítése előtt távolítsa el a következő ügyfélszoftvereket a számítógépről:<br /><br />- A Configuration Manager bármely verziója<br />- A Microsoft Systems Management Server (SMS) bármely verziója|

### További információ
[A Microsoft Intune mobileszköz-kezelési képességei](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


