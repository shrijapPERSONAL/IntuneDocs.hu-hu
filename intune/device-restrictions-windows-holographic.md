---
title: Eszközkorlátozásokra vonatkozó beállítások a Microsoft Intune-ban Windows Holographic for Business esetén – Azure | Microsoft Docs
description: Az Azure-ban elolvashatja és konfigurálhatja a Microsoft Intune a Windows Holographic for Business-eszközökre vonatkozó eszközkorlátozási beállításait, így a regisztrációtörléssel, a földrajzi hellyel, a jelszavakkal, az áruházból telepített alkalmazásokkal, az Edge sütijeivel és felugró ablakaival, a Windows Defenderrel, a kereséssel, a felhőtárhellyel, a Bluetooth-kapcsolattal, a rendszeridővel és a használati adatokkal kapcsolatos beállításokat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e8a1abb4229b3e6b4c91cfd49b4f66dbe739ea7d
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2018
---
# <a name="device-restriction-settings-for-windows-holographic-for-business-in-intune"></a>Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Windows Holographic for Business esetén

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az alábbi eszközkorlátozási beállítások a Windows Holographic for Businesst futtató eszközökön, például a Microsoft Hololensen vannak támogatva.

## <a name="general"></a>Általános

- **Regisztráció manuális törlése** – Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.
- **Cortana** – Engedélyezi vagy letiltja a Cortana beszédfelismerési asszisztenst.
- **Földrajzi hely** – Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.

## <a name="password"></a>Jelszó
-   **Jelszó** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
    -   **Jelszó kérése, ha az eszköz visszatér az inaktív állapotból** – Azt adja meg, hogy köteles-e a felhasználó jelszót megadni az eszköz feloldásához.

## <a name="app-store"></a>Alkalmazásáruház

-   **Áruházból származó alkalmazások automatikus frissítése** – Engedélyezi a Microsoft Áruházból származó alkalmazások automatikus frissítését.
-   **Megbízható alkalmazás telepítése** – Engedélyezi a megbízható tanúsítvánnyal aláírt alkalmazások közvetlen telepítését.
-   **Fejlesztői zárolás feloldása** – Engedélyezi, hogy a Windows fejlesztői beállításait (például alkalmazások közvetlen telepítését) a végfelhasználók megváltoztassák.

## <a name="edge-browser"></a>Microsoft Edge böngésző

-   **Cookie-k** – Engedélyezi a böngészőnek, hogy mentse az internetről érkező cookie-kat az eszközre.
-   **Előugró ablakok** – Blokkolja az előugró ablakokat a böngészőben (csak a Windows 10 asztali verzióra vonatkozik).
-   **Keresési javaslatok** – Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.
-   **Jelszókezelő** – Engedélyezi vagy letiltja a Microsoft Edge böngésző Jelszókezelő szolgáltatását.
- **„Do Not Track” fejlécek küldése** – Arra konfigurálja az Microsoft Edge böngészőt, hogy Do Not Track (Követés letiltása) fejléceket küldhessen a felhasználók által meglátogatott webhelyeknek.

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

## <a name="kiosk"></a>Kioszkmód

A kioszkeszközök jellemzően egy adott alkalmazást futtatnak. A rendszer a felhasználóknak csak a kioszkalkalmazáshoz ad hozzáférést, és meggátolja az eszköz más funkcióinak és szolgáltatásainak elérését.

- **Kioszkmód** – Azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

  - **Nincs konfigurálva** (alapértelmezés) – A szabályzat nem engedélyezi a teljes képernyős módot. 
  - **Egyalkalmazásos kioszk** – A profil csak egyetlen alkalmazás futtatását engedélyezi az eszköznek. Amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
  - **Többalkalmazásos kioszk** – A profil engedélyezi több alkalmazás futtatását az eszköznek. Csak a hozzáadott alkalmazások lesznek elérhetők a felhasználónak. A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználónak, amelyben csak a szükséges alkalmazások érhetőek el. Azokat az alkalmazásokat pedig, amelyekre nincsen szükség, elrejti a rendszer. 
  
    Amikor egy többalkalmazásos kioszkhoz alkalmazásokat ad hozzá, egy fájlt is meg kell adnia a Start menü elrendezéséhez. A [Start menü elrendezési fájlját](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) bemutató cikk tartalmaz egy minta XML-fájlt is, amelyet használhat az Intune-ban. 

#### <a name="single-app-kiosks"></a>Egyalkalmazásos kioszk
Adja meg a következő beállításokat:

- **Felhasználói fiók** – Adja meg a kioszkalkalmazáshoz társított helyi (eszközön létező) felhasználói fiókot, vagy az Azure AD-fiókot. Azure AD-tartományhoz csatlakozó fiókot a következő formában tud megadni: `domain\username@tenant.org`. 

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `AzureAD\user@contoso.com` formátumot.

- **Az alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)** – Adja meg a kioszkalkalmazás alkalmazásfelhasználói modellben használt azonosítóját. További információkat a [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése) című témakörben találhat.

## <a name="reporting-and-telemetry"></a>Jelentéskészítés és telemetria

- **Használati adatok megosztása** – Itt adhatja meg a diagnosztikai adatok küldésének szintjét.
