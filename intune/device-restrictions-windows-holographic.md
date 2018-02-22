---
title: "Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Windows Holographic for Business esetén"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre a Windows Holographic for Business rendszerű eszközökön.”"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/19/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 300ddb15f2d7b8f2fc6ab4a0e9e32852e0604e0a
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2018
---
# <a name="windows-holographic-for-business-device-restriction-settings-in-microsoft-intune"></a>A Windows Holographic for Business eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az alábbi eszközkorlátozási beállítások a Windows Holographic for Businesst futtató eszközökön, például a Microsoft Hololensen vannak támogatva.

## <a name="general"></a>Általános

- **Regisztráció manuális törlése** – Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.
- **Cortana** – Engedélyezi vagy letiltja a Cortana beszédfelismerési asszisztenst.
- **Földrajzi hely** – Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.



## <a name="password"></a>Jelszó
-   **Jelszó** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
    -   **Jelszó kérése, ha az eszköz visszatér az inaktív állapotból** – Azt adja meg, hogy köteles-e a felhasználó jelszót megadni az eszköz feloldásához.



## <a name="app-store"></a>Alkalmazásáruház

-   **Alkalmazásáruház** – engedélyezi vagy letiltja az Alkalmazásáruház használatát az eszközön.
-   **Áruházból származó alkalmazások automatikus frissítése** – Engedélyezi a Microsoft Áruházból származó alkalmazások automatikus frissítését.
-   **Megbízható alkalmazás telepítése** – Engedélyezi a megbízható tanúsítvánnyal aláírt alkalmazások közvetlen telepítését.
-   **Fejlesztői zárolás feloldása** – Engedélyezi, hogy a Windows fejlesztői beállításait (például alkalmazások közvetlen telepítését) a végfelhasználók megváltoztassák.

## <a name="edge-browser"></a>Edge böngésző

-   **Microsoft Edge böngésző** – Engedélyezi az Edge böngésző használatát az eszközön.
-   **Cookie-k** – Engedélyezi a böngészőnek, hogy mentse az internetről érkező cookie-kat az eszközre.
-   **Előugró ablakok** – Blokkolja az előugró ablakokat a böngészőben (csak a Windows 10 asztali verzióra vonatkozik).
-   **Keresési javaslatok** – Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.
-   **Jelszókezelő** – Engedélyezi vagy letiltja az Edge böngésző Jelszókezelő szolgáltatását.
- **„Do Not Track” fejlécek küldése** – Arra konfigurálja az Edge böngészőt, hogy Do Not Track (Követés letiltása) fejléceket küldhessen a felhasználók által meglátogatott webhelyeknek.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **SmartScreen a Microsoft Edge böngészőhöz** – Az Edge SmartScreen webhely- és fájlletöltésekhez való hozzáférésének engedélyezése.

## <a name="search"></a>Keresés
- **Helyadatok kereséshez** – Annak megadása, hogy a keresési funkció használhatja-e a helyadatokat. információ


## <a name="cloud-and-storage"></a>Felhő és tárolás
-   **Microsoft-fiók** – Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

-   **Bluetooth** – Azt szabályozza, hogy a felhasználó engedélyezheti és konfigurálhatja-e a Bluetooth-t az eszközön.
-   **Bluetooth-észlelhetőség** – Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök számára.
-   **Bluetooth-hirdetés** – Lehetővé teszi az eszköz számára, hogy hirdetéseket fogadjon a Bluetooth-kapcsolaton.

## <a name="control-panel-and-settings"></a>Vezérlőpult és Gépház

- **Rendszeridő módosítása** – Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz rendszeridejét.

## <a name="reporting-and-telemetry"></a>Jelentéskészítés és telemetria

- **Használati adatok megosztása** – Itt adhatja meg a diagnosztikai adatok küldésének szintjét.