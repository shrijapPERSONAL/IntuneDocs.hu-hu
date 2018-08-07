---
title: Eszközprofilok az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A különféle Microsoft Intune-eszközprofilok áttekintése a funkciók, korlátozások, e-mail, Wi-Fi, VPN, oktatás, tanúsítványok, Windows 10-frissítés, BitLocker és Windows Defender, Windows Információvédelem és az Azure Portal-beli egyéni eszközkonfigurációs beállítások ismertetésével. Ezeket a profilokat vállalati adatai és eszközei kezelésére és védelmére használhatja.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8bb03becae1f28a3f5490a53576d5183c0b3ffaa
ms.sourcegitcommit: 0d08daa162212e6cdd8a6ee3ad7ed42c6e6824e4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39335826"
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Mik azok a Microsoft Intune-eszközprofilok?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune olyan beállításokat és funkciókat kínál, amelyeket Ön engedélyezhet vagy letilthat a vállalatához tartozó különböző eszközökön. Ezek a beállítások és funkciók profilok használatával kezelhetők. Néhány példa profilok használatára: 

- A vállalati Wi-Fi-hez különböző eszközöknek hozzáférést biztosító Wi-Fi-profil
- A vállalati hálózaton belüli VPN-kiszolgálóhoz különböző eszközöknek hozzáférést biztosító VPN-profil

Ez a cikk áttekintést nyújt az eszközeihez létrehozható különféle profilokról. Ezeket a profilokat az eszközök egyes funkcióinak engedélyezésére vagy letiltására használhatja.

## <a name="before-you-begin"></a>Előkészületek
A rendelkezésre álló funkciók megismeréséhez nyissa meg az [Azure Portalt](https://portal.azure.com), majd saját Intune-forrását. 

Az **Eszközkonfiguráció** a következő lehetőségeket foglalja magában:

- **Áttekintés**: Listázza a profilok állapotát, és további részleteket ad meg a felhasználókhoz és eszközökhöz rendelt profilokról
- **Kezelés**: Eszközprofilok létrehozása és a profilon belül futtatandó egyéni [PowerShell-parancsfájlok](intune-management-extension.md) feltöltése
- **Figyelés**: Sikeres végrehajtás vagy hiba feltárása a profil állapotában és a profilhoz tartozó naplók megtekintése
- **Beállítás**: Hitelesítésszolgáltató (SCEP vagy PFX) megadása, vagy távközlésiköltség-kezelés engedélyezése a profilban

## <a name="create-the-profile"></a>A profil létrehozása

Az [Eszközprofilok létrehozása](device-profile-create.md) című útmutató lépésenként ismerteti egy profil létrehozásának menetét. 

## <a name="device-features---ios-and-macos"></a>Eszközfunkciók – iOS és macOS

Az [eszközfunkciókkal](device-features-configure.md) szabályozhatók az iOS- és macOS-eszközök funkciói, például az AirPrint, az értesítések és a megosztott eszközkonfigurációk.

Ez a funkció a következőket támogatja:
- iOS 
- macOS

## <a name="device-restrictions"></a>Eszközkorlátozások
Az [eszközkorlátozásokkal](device-restrictions-configure.md) kezelhető a biztonság, a hardver, az adatmegosztás és az eszközök több beállítása. Létrehozható például egy olyan eszközkorlátozási profil, amely megakadályozza, hogy az iOS-eszközök felhasználói használják az eszköz kameráját. 

Ez a funkció a következőket támogatja:

- Android
- iOS
- macOS
- Windows 10
- Windows 10 Team

## <a name="endpoint-protection"></a>Endpoint Protection
A [Végpontvédelmi beállítások Windows 10-hez](endpoint-protection-windows-10.md) a BitLocker és a Windows Defender beállításait konfigurálja Windows 10 rendszerű eszközökön.

A Windows Defender Komplex veszélyforrások elleni védelem (WDATP) Microsoft Intune-ban való előkészítéséhez lásd: [Configure endpoints using Mobile Device Management (MDM) tools (Végpontok konfigurálása Mobile Device Management (MDM) eszközök használatával)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Ez a funkció a következőket támogatja:
- Windows 10 és újabb

## <a name="kiosk"></a>Kioszkmód

A [Kioszkmód-beállítások](kiosk-settings.md) profil egy vagy több alkalmazás futtatására konfigurálja az eszközt. A teljes képernyőn más funkciókat, többek között start menüt és webböngészőt is testre szabhat.

Ez a funkció a következőket támogatja:
- Windows 10 és újabb

## <a name="email"></a>E-mail
Az [E-mail-beállítások](email-settings-configure.md) profil Exchange ActiveSync e-mail-beállítások létrehozását, hozzárendelését és figyelését végzi az eszközökön. Az e-mail-profilok segítenek biztosítani a konzisztenciát, csökkenthetik a segélykérő hívások számát, valamint saját kötelező beállítások nélkül is lehetővé teszik a végfelhasználók számára, hogy az eszközükön hozzáférjenek a céges postafiókjukhoz. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="vpn"></a>VPN
A [VPN-beállítások](vpn-settings-configure.md) használatával a VPN-profilokat a vállalati felhasználókhoz és eszközökhöz rendelheti hozzá, így azok könnyen és biztonságosan kapcsolódhatnak a hálózathoz. 

A virtuális magánhálózatok (VPN) biztonságos távoli hozzáférést biztosítanak a felhasználóknak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="wi-fi"></a>Wi-Fi
A [Wi-Fi-beállítások](wi-fi-settings-configure.md) a vezeték nélküli hálózat beállításait rendeli hozzá felhasználókhoz és eszközökhöz. A Wi-Fi-profil hozzárendelése után a felhasználók anélkül is hozzáférhetnek a céges Wi-Fihez, hogy ők maguk konfigurálnák azt. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- macOS
- Windows 8.1 (csak importálás)

## <a name="esim-cellular---public-preview"></a>eSIM-kártya – Nyilvános előzetes verzió

Az [eSIM mobilhálózati profilok](esim-device-configuration.md) lehetővé teszik a mobilhálózati díjcsomagok konfigurálását a felügyelt eszközökön az internet és az adatok eléréséhez.  Miután megkapta az aktiváló kódokat a mobilszolgáltatótól, az Intune segítségével importálhatja, majd hozzárendelheti azokat az eSIM-kompatibilis eszközökhöz.

Ez a funkció a következőket támogatja:
- Windows 10 őszi alkotói frissítés, vagy későbbi verzió

## <a name="education"></a>Oktatás
Az [Oktatási beállítások – Windows 10](education-settings-configure.md) segítségével konfigurálhatja a [Windows Vizsga alkalmazás](https://education.microsoft.com/gettrained/win10takeatest) beállításait. A beállítások konfigurálásakor az eszközön a vizsga befejezéséig nem futhat másik alkalmazás.

Az [Oktatási beállítások – iOS](education-settings-configure-ios-shared.md) az iOS-es Osztályterem alkalmazás segítségével lehetővé teszi az oktatási folyamat és a diákok eszközeinek irányítását az osztályteremben. Az iPad-eszközöket úgy is konfigurálhatja, hogy több diák oszthassa meg ugyanazt az eszközt.

## <a name="edition-upgrade"></a>Kiadásfrissítés
A [Windows 10 kiadásfrissítések](edition-upgrade-configure-windows-10.md) lehetővé teszi a Windows 10 egyes verzióit futtató eszközök újabb kiadásra történő automatikus frissítését.

Ez a funkció a következőket támogatja: 
- Windows 10 és újabb

## <a name="update-policies"></a>Frissítési szabályzatok
Az [iOS-es frissítési szabályzatok](software-updates-ios.md) az iOS-eszközökön telepítendő szoftverfrissítésekre vonatkozó iOS-es szabályzatok létrehozását és hozzárendelését mutatják be. A telepítés állapotát is áttekintheti.

Ez a funkció a következőket támogatja:
- iOS

## <a name="certificates"></a>Tanúsítványok
A [Tanúsítványok](certificates-configure.md) olyan, az eszközökhöz hozzárendelhető megbízható SCEP- és PKCS- tanúsítványok konfigurálását teszi lehetővé, amelyek a Wi-Fi-, VPN- és e-mail-profilok hitelesítésére használhatók.

Ez a funkció a következőket támogatja: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="windows-information-protection-profile"></a>Windows információvédelem profil
A [Windows Információvédelem](windows-information-protection-configure.md) úgy segít védekezni az adatszivárgások ellen, hogy mindeközben nem avatkozik bele az alkalmazottak munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által a munkahelyen használt személyes eszközökön véletlenül kiszivárogjanak. Ehhez nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.

Ez a funkció a következőket támogatja:
- Windows 10 és újabb

## <a name="custom-profile"></a>Egyéni profil
Az [Egyéni beállítások](custom-settings-configure.md) segítségével egyebek mellett az Intune-ba be nem épített eszközbeállítások alkalmazhatók. Például OMA-URI értékek adhatók meg Android-eszközökön. iOS-eszközökön importálható egy, az Apple Configuratorban létrehozott konfigurációs fájl. 

Ez a funkció a következőket támogatja:

- Android
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Felügyelet és hibaelhárítás

[A profilok kezelésével](device-profile-monitor.md) ellenőrizheti az eszközök állapotát és a hozzárendelt profilokat. Az ütközéseket okozó beállítások és az ezeket a beállításokat tartalmazó profilok azonosításával egyszerűbben lehet az ütközéseket elhárítani. A [gyakori problémák és megoldásaik](device-profile-troubleshoot.md) olyan kérdések és válaszok listáját tartalmazza, amelyek segítenek a profilok kezelésében, többek között megtudható belőlük, mi történik egy profil törlésekor, mi okozza az eszközökre küldött értesítéseket és így tovább.