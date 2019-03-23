---
title: Eszközök funkcióinak és a beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: A különböző Microsoft Intune-eszközprofilok áttekintése. Az funkciók, korlátozások, e-mail, Wi-Fi, VPN, oktatás, tanúsítványok, Windows 10-frissítés, BitLocker és a Windows defender, Windows Information Protection, felügyeleti sablonok és egyéni eszközkonfigurációs beállítások adatainak beolvasása az Azure Portalon. Ezek a profilok segítségével kezelheti és az adatok és a vállalati eszközök védelme.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: df8cc8c921b685ba7fa0b957685836d059a677e0
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394990"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Az eszközök Microsoft Intune-ban eszközprofilok segítségével szolgáltatásainak és beállításainak alkalmazása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune tartalmazza a beállításokat és funkciókat, engedélyezése vagy letiltása a különböző eszközökön, a szervezeten belül. Ezek a beállítások és funkciók "profilok" kerülnek. A különböző eszközökre és a különböző platformokon, beleértve az iOS, Android és Windows profilokat hozhat létre. Ezután használja az Intune-ban a alkalmazni, vagy "" a profil hozzárendelése az eszközökhöz.

A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a konfigurációs profilokat különböző feladatok végrehajtásához. Néhány példa profilok használatára:

- Windows 10 rendszerű eszközökön használja az Internet Explorerben, amely blokkolja az ActiveX-vezérlők profilsablon.
- Az iOS és MacOS rendszerű eszközökön engedélyezése a felhasználók számára a szervezetében használt AirPrint-nyomtatókra.
- Engedélyezi, vagy az eszköz bluetooth való hozzáférés letiltása.
- A vállalati hálózathoz különböző eszközöknek hozzáférést biztosító Wi-Fi vagy VPN-profil létrehozása.
- Kezelheti a szoftverfrissítéseket, beleértve a vannak telepítve.
- Android-eszközön futtató dedikált teljes képernyős eszköz, amely egyetlen alkalmazás, vagy számos alkalmazás futtatásához.

Ez a cikk áttekintést nyújt a különböző típusú profilokat hozhat létre. Ezek a profilok segítségével engedélyezése vagy letiltása az eszköz egyes funkcióinak.

## <a name="administrative-templates-preview"></a>Felügyeleti sablonok (előzetes verzió)

[Felügyeleti sablonok](administrative-templates-windows.md) több száz, az Internet Explorer, a onedrive vállalati verzió, a távoli asztal, a Word, az Excel és a többi Office-alkalmazásokhoz konfigurálható beállítások közé tartozik.

Ezek a sablonok segítségével a rendszergazdák egy egyszerűsített nézete hasonló csoportházirend beállításokat, de 100 %-os felhőalapú.

Ez a funkció a következőket támogatja:

- Windows 10 és újabb

## <a name="device-features"></a>Eszközfunkciók

[Eszközfunkciók](device-features-configure.md) az iOS és macOS-eszközök, például AirPrint, értesítések és zárolási képernyőjén üzenetek szolgáltatások szabályozza.

Ez a funkció a következőket támogatja:

- iOS 
- macOS

## <a name="device-restrictions"></a>Eszközkorlátozások

Az [eszközkorlátozásokkal](device-restrictions-configure.md) kezelhető a biztonság, a hardver, az adatmegosztás és az eszközök több beállítása. Létrehozható például egy olyan eszközkorlátozási profil, amely megakadályozza, hogy az iOS-eszközök felhasználói használják az eszköz kameráját. 

Ez a funkció a következőket támogatja:

- Android
- Android enterprise
- iOS
- macOS
- Windows 10 és újabb
- Windows 10 Team

## <a name="delivery-optimization"></a>Teljesítésoptimalizálás

[Kézbesítésoptimalizálás](delivery-optimization-windows.md) kézbesítési szoftverfrissítések jobb felhasználói élményt biztosít. Ezek a beállítások cserélni a **szoftverfrissítések** > **Windows 10 frissítési kör** beállításait.

Ezek a beállítások segítségével vezérelheti, hogyan szoftverfrissítések letöltődnek a szervezetnél található eszközökön. Ha például engedélyezheti a felhasználók számára a saját frissítések beszerzése, illetve a kézbesítési optimalizálás cloud services használata az eszközprofil-frissítések.

Ez a funkció a következőket támogatja:

- Windows 10 és újabb

## <a name="endpoint-protection"></a>Endpoint Protection

A [Végpontvédelmi beállítások Windows 10-hez](endpoint-protection-windows-10.md) a BitLocker és a Windows Defender beállításait konfigurálja Windows 10 rendszerű eszközökön.

A Windows Defender Komplex veszélyforrások elleni védelem (WDATP) Microsoft Intune-ban való előkészítéséhez lásd: [Configure endpoints using Mobile Device Management (MDM) tools (Végpontok konfigurálása Mobile Device Management (MDM) eszközök használatával)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Ez a funkció a következőket támogatja:

- Windows 10 és újabb

## <a name="identity-protection"></a>Identitásvédelem

Az [Identity protection](identity-protection-configure.md) vezérli a vállalati Windows Hello felületet Windows 10 vagy Windows 10 Mobile rendszerű eszközökön. Ezeknek a beállításoknak a konfigurálásával teheti elérhetővé a vállalati Windows Hellót a felhasználók és eszközök számára, és így adhatja meg az eszközök PIN-kódjaira és a kézmozdulatokra vonatkozó követelményeket.  

Ez a funkció a következőket támogatja:  

- Windows 10 és újabb
- Windows Holographic for Business  

## <a name="kiosk"></a>Kioszkmód

[A kioszkmód](kiosk-settings.md) profil konfigurálja egy eszközt, egyetlen alkalmazás, vagy számos alkalmazás futtatásához. A teljes képernyőn más funkciókat, többek között start menüt és webböngészőt is testre szabhat.

Ez a funkció a következőket támogatja:

- Windows 10 és újabb

A kioszkmód eszközkorlátozások számára is elérhető [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings), és [ios](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>E-mail

[Az e-mail beállítások](email-settings-configure.md) hoz létre, rendeli hozzá, és figyeli az Exchange Active Sync e-mail beállításait az eszközökön. E-mail-profilok súgó konzisztencia, kevesebbszer igényelnek, és lehetővé teszik a végfelhasználók számára hozzáférést vállalati e-maileket a személyes eszközeiken, semmit sem kell beállítaniuk eszközeiken. 

Ez a funkció a következőket támogatja: 

- Android
- Vállalati Android
- iOS
- Windows Phone 8.1
- Windows 10 és újabb

## <a name="vpn"></a>VPN

A [VPN-beállítások](vpn-settings-configure.md) használatával a VPN-profilokat a vállalati felhasználókhoz és eszközökhöz rendelheti hozzá, így azok könnyen és biztonságosan kapcsolódhatnak a hálózathoz. 

A virtuális magánhálózatok (VPN) biztonságos távoli hozzáférést biztosítanak a felhasználóknak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. 

Ez a funkció a következőket támogatja: 

- Android
- Vállalati Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 és újabb

## <a name="wi-fi"></a>Wi-Fi

A [Wi-Fi-beállítások](wi-fi-settings-configure.md) a vezeték nélküli hálózat beállításait rendeli hozzá felhasználókhoz és eszközökhöz. A Wi-Fi-profil hozzárendelése után a felhasználók anélkül is hozzáférhetnek a céges Wi-Fihez, hogy ők maguk konfigurálnák azt. 

Ez a funkció a következőket támogatja: 

- Android
- Vállalati Android
- iOS
- macOS
- Windows 8.1 (csak importálás)
- Windows 10 és újabb

## <a name="esim-cellular---public-preview"></a>eSIM-kártya – Nyilvános előzetes verzió

[esim-kártya mobilhálózati profilok](esim-device-configuration.md) lehetővé teszi, hogy a rendszergazdák le mobilhálózati adatforgalmat csomagok konfigurálása a felügyelt eszközökön az internetes és az való hozzáférés. Után az aktiváló kód lekérése a mobilszolgáltató, használja ezeket az aktiváló kód importálhatja, és rendelje hozzá az esim-kártya kompatibilis eszközök Intune-ban.

Ez a funkció a következőket támogatja:
- Windows 10 őszi alkotói frissítés, vagy későbbi verzió

## <a name="education"></a>Oktatás

Az [Oktatási beállítások – Windows 10](education-settings-configure.md) segítségével konfigurálhatja a [Windows Vizsga alkalmazás](https://education.microsoft.com/gettrained/win10takeatest) beállításait. A beállítások konfigurálásakor az eszközön a vizsga befejezéséig nem futhat másik alkalmazás.

Az [Oktatási beállítások – iOS](education-settings-configure-ios-shared.md) az iOS-es Osztályterem alkalmazás segítségével lehetővé teszi az oktatási folyamat és a diákok eszközeinek irányítását az osztályteremben. IPad eszköz is beállíthatja, így sok tanulók is egyetlen eszközt.

## <a name="edition-upgrade"></a>Kiadásfrissítés

A [Windows 10 kiadásfrissítések](edition-upgrade-configure-windows-10.md) lehetővé teszi a Windows 10 egyes verzióit futtató eszközök újabb kiadásra történő automatikus frissítését.

Ez a funkció a következőket támogatja: 
- Windows 10 és újabb

## <a name="update-policies"></a>Frissítési szabályzatok

Az [iOS-es frissítési szabályzatok](software-updates-ios.md) az iOS-eszközökön telepítendő szoftverfrissítésekre vonatkozó iOS-es szabályzatok létrehozását és hozzárendelését mutatják be. A telepítés állapotát is áttekintheti.

Frissítési szabályzatok a Windows-eszközökön, lásd: [kézbesítésoptimalizálás](delivery-optimization-windows.md). 

Ez a funkció a következőket támogatja:
- iOS

## <a name="certificates"></a>Tanúsítványok

[Tanúsítványok](certificates-configure.md) konfigurálása megbízható SCEP- és PKCS-tanúsítványokat, amelyeket eszközök vannak hozzárendelve. Ezeket a tanúsítványokat Wi-Fi, VPN, hitelesítést és e-mail-profilok.

Ez a funkció a következőket támogatja: 

- Android
- Vállalati Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 és újabb

## <a name="windows-information-protection-profile"></a>Windows információvédelem profil

A [Windows Információvédelem](windows-information-protection-configure.md) úgy segít védekezni az adatszivárgások ellen, hogy mindeközben nem avatkozik bele az alkalmazottak munkavégzésébe. Emellett segít megvédeni a vállalati alkalmazások és adatok a vállalati tulajdonban lévő eszközök és a által használt alkalmazottak személyes eszközökön véletlenül kiszivárogjanak. Windows Information Protection használatával nincs szükség a környezet és más alkalmazások módosítását.

Ez a funkció a következőket támogatja:

- Windows 10 és újabb

## <a name="shared-multi-user-device"></a>Többfelhasználós megosztott eszköz

[Windows 10-es](shared-user-device-settings-windows.md) és [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) eszközök kezelése több felhasználóval, más néven megosztott eszközök vagy a megosztott számítógépek beállításokat tartalmaz. Amikor egy felhasználó bejelentkezik az eszközre, az úgy dönt, ha a felhasználó az alvási beállítások módosítása, vagy mentse a fájlt az eszközön. Egy másik példa ezzel helyet, létrehozhat egy profilt, amely törli az inaktív hitelesítő adatokat az Windows HoloLens-eszközök.

Ezek a beállítások megosztott több felhasználó-eszköz lehetővé teszi a rendszergazda szabályozhatja az eszköz funkcióit, és a megosztott eszközök Intune-nal kezelheti.

Ez a funkció a következőket támogatja:

- Windows 10 és újabb
- Windows Holographic for Business

## <a name="zebra-mobility-extensions-mx"></a>Zebra mobilitási Extensions (MX)

[Zebra mobilitási bővítmények MX](android-zebra-mx-overview.md) lehetővé teszi a rendszergazdák használható és felügyelhető Zebra eszközök Intune-ban. A beállításokkal StageNow profilok hozhatók létre, és majd az Intune segítségével hozzárendelni, és ezeket a profilokat az eszközökre telepíteni kívánt Zebra. A [StageNow naplók és a gyakori problémák](android-zebra-mx-logs-troubleshoot.md) egy nagyszerű forrás, amely profilok hibaelhárítása, és megtekintheti a potenciális problémákat, StageNow használatakor.

Ez a funkció a következőket támogatja:

- Android

## <a name="custom-profile"></a>Egyéni profil

[Egyéni beállítások](custom-settings-configure.md) lehetővé teszik a rendszergazdák nem beépített eszközbeállítások hozzárendelése az Intune-hoz. OMA-URI értékek Android-eszközön adhat meg. iOS-eszközökön importálható egy, az Apple Configuratorban létrehozott konfigurációs fájl.

Ez a funkció a következőket támogatja:

- Android
- Vállalati Android
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Felügyelet és hibaelhárítás

[A profilok kezelésével](device-profile-monitor.md) ellenőrizheti az eszközök állapotát és a hozzárendelt profilokat. Tekintse meg a beállításokat, amelyek ütközést, és ezeket a beállításokat tartalmazó profilok ütközések feloldása is segítenek. [Gyakori problémák és megoldásuk](device-profile-troubleshoot.md) segítségével a munkahelyi profilokkal rendelkező rendszergazdák. Leírja, mi történik, ha töröl egy profilt, hogy mi okozza az eszközöket, és egyéb küldendő értesítések.

## <a name="next-steps"></a>További lépések

Válassza ki a platformot, és a kezdéshez.
