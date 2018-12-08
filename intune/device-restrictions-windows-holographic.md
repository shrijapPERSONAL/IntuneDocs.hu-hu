---
title: A Windows Holographic Business beállításai – Microsoft Intune – Azure |} A Microsoft Docs
description: Az Azure-ban elolvashatja és konfigurálhatja a Microsoft Intune a Windows Holographic for Business-eszközökre vonatkozó eszközkorlátozási beállításait, így a regisztrációtörléssel, a földrajzi hellyel, a jelszavakkal, az áruházból telepített alkalmazásokkal, a Microsoft Edge sütijeivel és felugró ablakaival, a Windows Defenderrel, a kereséssel, a felhőtárhellyel, a Bluetooth-kapcsolattal, a rendszeridővel és a használati adatokkal kapcsolatos beállításokat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: cdac4623c6c5c9e7258897e1536856e6b24492ea
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032010"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Windows Holographic for Business eszközbeállítások engedélyezett vagy korlátozott funkciók az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk és szabályozhatja a különböző beállításokat ismerteti a Windows Holographic for Business-eszközök, például a Microsoft Hololens. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat engedélyezi vagy letiltja a szolgáltatások, a biztonság szabályozásához és egyéb.

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](device-restrictions-configure.md).

## <a name="general"></a>Általános

- **Regisztráció manuális törlésének**: lehetővé teszi, hogy a felhasználó a munkahelyi fiók manuális törlését az eszközről.
- **Cortana**: engedélyezi vagy letiltja a Cortana beszédfelismerési asszisztens.
- **Földrajzi hely meghatározásának**: Itt adhatja meg, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.

## <a name="password"></a>Jelszó

- **Jelszó**: megköveteli a végfelhasználótól, adjon meg egy jelszót az eszköz elérésére.
- **Jelszó kérése, ha az eszköz visszatér inaktív állapotból**: Itt adhatja meg, hogy a felhasználónak meg kell adnia egy jelszót az eszköz zárolásának feloldásához.

## <a name="app-store"></a>Alkalmazásáruház

- **Áruházból származó alkalmazások automatikus frissítése**: lehetővé teszi, hogy a Microsoft Store automatikusan frissíteni kell a telepített alkalmazások.
- **Megbízható alkalmazás telepítése**: lehetővé teszi az alkalmazások közvetlen telepítését a megbízható tanúsítvánnyal aláírt.
- **Fejlesztői zárolás feloldása**: lehetővé teszi a Windows fejlesztői beállításait, például lehetővé teszi a végfelhasználók által módosítható a közvetlenül telepített alkalmazások.

## <a name="microsoft-edge-browser"></a>Microsoft Edge böngésző

- **A cookie-k**: lehetővé teszi, hogy a böngésző cookie-k mentse az eszközön.
- **Előugró ablakok**: blokkolja az előugró ablakokat a böngészőben (csak Windows 10 asztali verzióra vonatkozik).
- **Keresési javaslatok**: lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása.
- **Jelszókezelő**: engedélyezése vagy letiltása a Microsoft Edge böngésző jelszókezelő szolgáltatását.
- **"Do not track" fejlécek küldése**: konfigurálja a Microsoft Edge böngésző küldése tiltó fejlécek felhasználók által meglátogatott webhelyeknek.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **A Microsoft Edge SmartScreen**: engedélyezze a Microsoft Edge SmartScreen webhely- és fájlletöltésekhez eléréséhez.

## <a name="search"></a>Keresés

- **Helyadatok kereséshez** – Annak megadása, hogy a keresési funkció használhatja-e a helyadatokat. információ

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Microsoft-fiók**: lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

- **Bluetooth**: meghatározza, hogy a felhasználó engedélyezése és az eszköz Bluetooth konfigurálásához.
- **Bluetooth-észlelhetőség**: észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök által.
- **Bluetooth-hirdetés**: lehetővé teszi, hogy az eszközök hirdetéseket fogadjanak Bluetooth-on keresztül.

## <a name="control-panel-and-settings"></a>Vezérlőpult és Gépház

- **Rendszeridő módosítása**: megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz dátum és idő.

## <a name="kiosk---obsolete"></a>Kioszkmód – elavult

Ezek a beállítások csak olvashatók, és nem módosíthatók. A kioszkmód konfigurálásáról a [Kioszkbeállítások](kiosk-settings.md#windows-holographic-for-business) című cikkből tájékozódhat.

A kioszkeszközök jellemzően egy adott alkalmazást futtatnak. A rendszer a felhasználóknak csak a kioszkalkalmazáshoz ad hozzáférést, és meggátolja az eszköz más funkcióinak és szolgáltatásainak elérését.

- **Teljes képernyős mód**: azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

  - **Nincs konfigurálva** (alapértelmezés): A szabályzat nem engedélyezi a teljes képernyős módot. 
  - **Egyalkalmazásos kioszk**: A profil engedélyezi az eszköznek csak egyetlen alkalmazás futtatását. Amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
  - **Többalkalmazásos kioszk**: A profil engedélyezi több alkalmazás futtatását az eszköz. Csak a hozzáadott alkalmazások lesznek elérhetők a felhasználónak. A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználónak, amelyben csak a szükséges alkalmazások érhetőek el. Azokat az alkalmazásokat pedig, amelyekre nincsen szükség, elrejti a rendszer. 
  
    Amikor egy többalkalmazásos kioszkhoz alkalmazásokat ad hozzá, egy fájlt is meg kell adnia a Start menü elrendezéséhez. A [Start menü elrendezési fájlját](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) bemutató cikk tartalmaz egy minta XML-fájlt is, amelyet használhat az Intune-ban. 

#### <a name="single-app-kiosks"></a>Egyalkalmazásos kioszk

Adja meg a következő beállításokat:

- **Felhasználói fiók**: Adja meg a helyi (eszközön létező) felhasználói fiók vagy az Azure AD-fiókot a teljes képernyős alkalmazáshoz társított bejelentkezési. Azure AD-tartományhoz csatlakozó fiókot a következő formában tud megadni: `domain\username@tenant.org`. 

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `AzureAD\user@contoso.com` formátumot.

- **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID) alkalmazás**: Adja meg a teljes képernyős alkalmazás alkalmazásfelhasználói modellben használt AZONOSÍTÓJÁT. További információkat a [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése) című témakörben találhat.

## <a name="reporting-and-telemetry"></a>Jelentéskészítés és telemetria

- **Használati adatok megosztása**: Itt adhatja meg a diagnosztikai adatok küldésének szintjét.
