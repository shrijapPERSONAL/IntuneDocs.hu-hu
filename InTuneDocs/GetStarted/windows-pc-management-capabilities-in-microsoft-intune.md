---
title: "Az Intune PC-szoftverügyfél képességei | Microsoft Intune"
description: "Ismerje meg az Intune funkcióit, amelyek akkor érhetők el, ha a Windows-számítógépeit az Intune-szoftverügyfél használatával felügyeli."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 12d75bc67fd61a2e807eed2543f21b756a65a900
ms.openlocfilehash: 3066ef98c0a1df6fc0ae455860635e7c12f82c4f


---

# A Windows-számítógépek felügyeletét szolgáló képességek az Intune szoftverügyfél használata esetén
A legtöbb esetben célszerű regisztrálni az eszközöket az Intune-ban, mivel ez több funkciót biztosít. Ugyanakkor az Intune-szoftverügyféllel is felügyelheti a számítógépeket. Ekkor a következő funkciókat érheti el:

-   **Szoftverfrissítések kezelése** – Naprakészen tarthatja a számítógépeit, és beállíthatja, hogy a rendszer mikor telepítse a frissítéseket.

-   **Windows tűzfalházirend** – Ezzel biztosíthatja, hogy a vállalatnál használt számítógépeken ne legyen inaktív vagy nem megfelelően beállított Windows tűzfal.

-   **Kártevők elleni védelem** – Az Intune Endpoint Protection védelmet használ, amely segít a számítógépek kártevők elleni védelmében.

-   **Távsegítség** – Az Intune lehetővé teszi a felhasználóknak, hogy az Intune beépített távoli asztali funkciója segítségével kapcsolatba lépjenek az informatikai támogatási csapattal (ehhez a TeamViewer szoftver szükséges).

-   **Szoftverlicenc-gazdálkodás** – Nyomon követheti az elérhető és a használatban lévő szoftverlicencek számát.
-   **Alkalmazások központi telepítése** – Szoftvereket telepíthet a felügyelt számítógépekre. Ha a szoftverügyféllel felügyeli a számítógépeket, akkor bizonyos alkalmazásfelügyeleti funkciók nem érhetők el.


Az Intune a szoftverügyfél akár 7000 Windows-eszközön való telepítését is támogatja.

## Rendszerkövetelmények
Az Intune a Windows következő verzióival rendelkező számítógépek felügyeletére alkalmas (32 bites és 64 bites verziók egyaránt):


-   **Windows Vista** – Business, Enterprise és Ultimate verziók

-   **Windows 7** – Pro, Enterprise és Ultimate verziók (szervizcsomag nélkül vagy SP1-gyel)

-   **Windows 8** – Pro és Enterprise verziók

-   **Windows 8.1** – Pro és Enterprise verziók

- **Windows 10** - Pro, Education és Enterprise verziók


## Minimális hardverkövetelmények
Az Intune-szoftverügyfél telepítésére vonatkozó minimális hardverkövetelmények a következők:

|Követelmény|Részletek|
|---------------|--------------------|
|Hálózat|Az ügyfél használatához a számítógépnek internetkapcsolattal kell rendelkeznie.|
|Processzor és memória|A processzorra és a RAM-ra vonatkozó követelményeket a számítógép operációs rendszere határozza meg.|
|Lemezterület|200 MB szabad lemezterület az ügyfélszoftver telepítése előtt.|

## További követelmények
Az Intune-szoftverügyfél telepítésére vonatkozó szoftverkövetelmények a következők:

|Követelmény|Részletek|
|---------------|--------------------|
|Rendszergazdai engedélyek|Az ügyfélszoftvert telepítő fióknak helyi rendszergazdai engedélyekkel kell rendelkeznie a számítógépen.|
|Windows Installer 3.1|A számítógépnek legalább a Windows Installer 3.1-es verziójával kell rendelkeznie.|
|Nem kompatibilis ügyfélszoftver eltávolítása|A számítógépes Intune ügyfélszoftver telepítése előtt távolítsa el a következő ügyfélszoftvereket a számítógépről:<br /><br />- A Configuration Manager bármely verziója<br />- A Microsoft Systems Management Server (SMS) bármely verziója|

### További információ
[A Microsoft Intune regisztrált eszközök kezelésével kapcsolatos képességei](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


