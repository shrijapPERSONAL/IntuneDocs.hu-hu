---
title: A Windows Holographic Business beállításai – Microsoft Intune – Azure |} A Microsoft Docs
description: Az Azure-ban elolvashatja és konfigurálhatja a Microsoft Intune a Windows Holographic for Business-eszközökre vonatkozó eszközkorlátozási beállításait, így a regisztrációtörléssel, a földrajzi hellyel, a jelszavakkal, az áruházból telepített alkalmazásokkal, a Microsoft Edge sütijeivel és felugró ablakaival, a Windows Defenderrel, a kereséssel, a felhőtárhellyel, a Bluetooth-kapcsolattal, a rendszeridővel és a használati adatokkal kapcsolatos beállításokat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f93ad05decb3cb4bf1fd6db87e9fb08f17280fcf
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237605"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Windows Holographic for Business eszközbeállítások engedélyezett vagy korlátozott funkciók az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk és szabályozhatja a különböző beállításokat ismerteti a Windows Holographic for Business-eszközök, például a Microsoft Hololens. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat engedélyezi vagy letiltja a szolgáltatások, a biztonság szabályozásához és egyéb.

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Általános

- **Regisztráció manuális törlésének**: Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.
- **Cortana**: A Cortana beszédfelismerési asszisztens engedélyezése vagy letiltása.
- **Földrajzi hely meghatározásának**: Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.

## <a name="password"></a>Windows 10

- **Jelszó**: Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
- **Jelszó kérése, ha az eszköz visszatér inaktív állapotból**: Itt adhatja meg, hogy a felhasználónak meg kell adnia egy jelszót az eszköz zárolásának feloldásához.

## <a name="app-store"></a>Alkalmazásáruház

- **Áruházból származó alkalmazások automatikus frissítése**: Lehetővé teszi, hogy a Microsoft Store automatikusan frissíteni kell a telepített alkalmazások.
- **Megbízható alkalmazás telepítése**: Lehetővé teszi az alkalmazások közvetlen telepítését a megbízható tanúsítvánnyal aláírt.
- **Fejlesztői zárolás feloldása**: Lehetővé teszi a Windows fejlesztői beállításait, például lehetővé teszi a végfelhasználók által módosítható a közvetlenül telepített alkalmazások.

## <a name="microsoft-edge-browser"></a>Microsoft Edge böngésző

- **A cookie-k**: Lehetővé teszi, hogy a böngésző cookie-k mentse az eszközön.
- **Előugró ablakok**: Blokkolja az előugró ablakokat a böngészőben (csak Windows 10 asztali verzióra vonatkozik).
- **Keresési javaslatok**: Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.
- **Jelszókezelő**: Engedélyezi vagy letiltja a Microsoft Edge böngésző jelszókezelő szolgáltatását.
- **"Do not track" fejlécek küldése**: Konfigurálja a Microsoft Edge böngésző küldése tiltó fejlécek felhasználók által meglátogatott webhelyeknek.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **A Microsoft Edge SmartScreen**: Engedélyezze a Microsoft Edge SmartScreen webhely- és fájlletöltésekhez eléréséhez.

## <a name="search"></a>Keresés

- **Helyadatok kereséshez** – Annak megadása, hogy a keresési funkció használhatja-e a helyadatokat. információ

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Microsoft-fiók**: Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

- **Bluetooth**: Azt szabályozza, hogy a felhasználó engedélyezése és az eszköz Bluetooth konfigurálásához.
- **Bluetooth-észlelhetőség**: Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök által.
- **Bluetooth-hirdetés**: Lehetővé teszi az eszközök hirdetéseket fogadjanak Bluetooth-on keresztül.

## <a name="control-panel-and-settings"></a>Vezérlőpult és Gépház

- **Rendszeridő módosítása**: Megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz rendszeridejét.

## <a name="kiosk---obsolete"></a>Kioszkmód – elavult

Ezek a beállítások csak olvashatók, és nem módosíthatók. A kioszkmód konfigurálásáról a [Kioszkbeállítások](kiosk-settings-holographic.md) című cikkből tájékozódhat.

A kioszkeszközök jellemzően egy adott alkalmazást futtatnak. A rendszer a felhasználóknak csak a kioszkalkalmazáshoz ad hozzáférést, és meggátolja az eszköz más funkcióinak és szolgáltatásainak elérését.

- **Teljes képernyős mód**: A szabályzat által támogatott teljes képernyős mód típusát jelöli. A lehetőségek a következők:

  - **Nincs konfigurálva** (alapértelmezett): A házirend nem engedélyezi a teljes képernyős módot. 
  - **Egyalkalmazásos kioszk**: A profil engedélyezi az eszköznek csak egyetlen alkalmazás futtatását. Amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
  - **Többalkalmazásos kioszk**: A profil engedélyezi több alkalmazás futtatását az eszköz. Csak a hozzáadott alkalmazások lesznek elérhetők a felhasználónak. A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználónak, amelyben csak a szükséges alkalmazások érhetőek el. Azokat az alkalmazásokat pedig, amelyekre nincsen szükség, elrejti a rendszer. 
  
    Amikor egy többalkalmazásos kioszkhoz alkalmazásokat ad hozzá, egy fájlt is meg kell adnia a Start menü elrendezéséhez. A [Start menü elrendezési fájlját](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) bemutató cikk tartalmaz egy minta XML-fájlt is, amelyet használhat az Intune-ban. 

#### <a name="single-app-kiosks"></a>Egyalkalmazásos kioszk

Adja meg a következő beállításokat:

- **Felhasználói fiók**: Adja meg a helyi (eszközön létező) felhasználói fiók vagy az Azure AD-fiókot a teljes képernyős alkalmazáshoz társított bejelentkezési. Azure AD-tartományhoz csatlakozó fiókot a következő formában tud megadni: `domain\username@tenant.org`. 

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `AzureAD\user@contoso.com` formátumot.

- **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID) alkalmazás**: Adja meg a teljes képernyős alkalmazás alkalmazásfelhasználói modellben használt AZONOSÍTÓJÁT. További információkat a [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése) című témakörben találhat.

## <a name="reporting-and-telemetry"></a>Jelentéskészítés és telemetria

- **Használati adatok megosztása**: Válassza ki a diagnosztikai adatok küldésének szintjét.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
