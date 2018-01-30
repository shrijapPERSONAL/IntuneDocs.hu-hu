---
title: "Mik azok az eszközprofilok a Microsoft Intune-ban?"
titlesuffix: Azure portal
description: "A cikkből megismerheti az Intune-eszközprofilokat, és azt, hogy miképpen segíthetnek a vállalati eszközök kezelésében és védelmében.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c745f9f745802e0de7a58e3dd7570c0e363ab5d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Mik azok a Microsoft Intune-eszközprofilok?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune **Eszközkonfiguráció** munkafolyamatával kezelheti az összes felügyelt eszköz beállításait és funkcióit. Ez a munkafolyamat elsősorban eszközprofilok létrehozására szolgál, amelyekkel különböző lehetőségek és szolgáltatások széles palettáját felügyelheti és szabályozhatja az eszközökön.

A munkafolyamat megnyitásakor az alábbi lehetőségek jelennek meg:

- **Áttekintés** – Ezen az oldalon a felhasználókhoz és az eszközökhöz rendelt eszközkonfigurációk megfigyelésében segítő állapot- és egyéb jelentések láthatók.
- **Profilok kezelése** – Ebben a szakaszban hozhatók létre az eszközkonfigurációs profilok. A létrehozható profiltípusok teljes listája a témakör későbbi részében látható.
- **Hitelesítésszolgáltató beállítása** – Ez a munkafolyamat végigvezet az Intune-tanúsítványprofilok konfigurálásához szükséges lépéseken.

## <a name="getting-started"></a>Első lépések

Az eszközprofilok létrehozásának munkafolyamata a más profilokéhoz hasonló. További információkért lásd:[Microsoft Intune-eszközkonfigurációs profilok létrehozása](device-profile-create.md). Ezután olvassa el az egyes profiltípusok beállításainak létrehozásáról szóló külön cikkeket is.

Az eszközök következő funkcióit kezelheti:

## <a name="device-features"></a>Eszközfunkciók

Az eszközfunkciókkal lehet szabályozni az iOS- és macOS-eszközök funkcióit, például az AirPrintet, az értesítéseket és a megosztott eszközkonfigurációkat.
További információ: [Eszközfunkció-beállítások konfigurálása](device-features-configure.md) Támogatott rendszerek: iOS és macOS.

## <a name="device-restrictions"></a>Eszközkorlátozások
Az eszközkorlátozások segítségével többek között a biztonság, a hardver, és az adatmegosztás beállításait szabályozhatja a felügyelt eszközökön. Létrehozhat például egy olyan eszközkorlátozási profilt, amely megakadályozza, hogy az iOS-eszközök felhasználói hozzáférjenek az eszköz kamerájához.
További információkért lásd: [Eszközkorlátozási beállítások konfigurálása](device-restrictions-configure.md). Támogatott rendszerek: Android, iOS, macOS, Windows 10 és Windows 10 Team.

## <a name="email"></a>E-mail
Az e-mail-profilok segítségével az Exchange ActiveSyncre vonatkozó e-mail-beállításokat hozhatja létre, telepítheti és figyelheti a felügyelt eszközökön. Az e-mail-profilok segítenek biztosítani a konzisztenciát, csökkenthetik a segélykérő hívások számát, valamint saját kötelező beállítások nélkül is lehetővé teszik a végfelhasználók számára, hogy az eszközükön hozzáférjenek a céges postafiókjukhoz.
További információkért lásd: [E-mail-beállítások konfigurálása](email-settings-configure.md). Támogatott rendszerek: Android, iOS, Windows Phone 8.1, Windows 10.

## <a name="wi-fi"></a>Wi-Fi
A Wi-Fi-profilokkal vezeték nélküli hálózati beállításokat rendelhet a szervezet felhasználóihoz és eszközeihez. A Wi-Fi-profil hozzárendelése után a felhasználók anélkül is hozzáférhetnek a céges Wi-Fihez, hogy ők maguk konfigurálnák azt.
További információkért lásd:[Wi-Fi beállítások konfigurálása](wi-fi-settings-configure.md). Támogatott rendszerek: Android, iOS, macOS és Windows 8.1 (csak importálás).

## <a name="vpn"></a>VPN
A virtuális magánhálózatok (VPN) segítségével biztonságos távoli hozzáférést biztosíthat felhasználóinak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. A cégen belüli felhasználókhoz és eszközökhöz VPN-profilokat rendelhet, hogy könnyen és biztosan csatlakozhassanak a hálózathoz.
További tudnivalók: [VPN-beállítások konfigurálása](vpn-settings-configure.md).
Támogatott rendszerek: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 és Windows 10.

## <a name="education"></a>Oktatás
Itt lehet konfigurálni a Windows Vizsga alkalmazás beállításait. A beállítások konfigurálásakor az eszközön a vizsga befejezéséig nem futhat másik alkalmazás.
További tudnivalók: [Oktatási beállítások konfigurálása](education-settings-configure.md)

## <a name="certificates"></a>Tanúsítványok
Ez a profiltípus olyan, az eszközökhöz hozzárendelhető megbízható SCEP- és PKCS- tanúsítványok konfigurálását teszi lehetővé, amelyek a Wi-Fi-, VPN- és e-mail-profilok hitelesítésére használhatók.
További információkért lásd:[Tanúsítványok konfigurálása](certificates-configure.md). Támogatott rendszerek: Android, iOS, Windows Phone 8.1, Windows 8.1 és Windows 10.

## <a name="edition-upgrade"></a>Kiadásfrissítés
Ez a profiltípus lehetővé teszi a Windows 10 egyes verzióit futtató eszközök újabb kiadásra történő automatikus frissítését.
További információkért lásd: [A Windows 10 kiadásfrissítéseinek konfigurálása](edition-upgrade-configure-windows-10.md). Támogatott rendszer: csak a Windows 10.

## <a name="endpoint-protection"></a>Endpoint Protection
Ez a profiltípus BitLocker- és Windows Defender-beállítások konfigurálását teszi lehetővé Windows 10-eszközökön.
További információkért lásd: [Endpoint Protection-beállítások Windows 10 rendszerű eszközökön](endpoint-protection-windows-10.md). Támogatott rendszer: csak a Windows 10.

## <a name="windows-information-protection"></a>Windows Információvédelem
A Windows Információvédelem úgy segít védekezni az adatszivárgások ellen, hogy mindeközben más módon nem avatkozik bele az alkalmazott munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által munkába hozott személyes eszközökön véletlenül kiszivárogjanak, ehhez pedig nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.
További információt a [Windows Információvédelem konfigurálása](windows-information-protection-configure.md) című témakörben talál. Támogatott rendszer: csak Windows 10.

## <a name="custom"></a>Egyéni
Egyéni beállítások segítségével az Intune-ba be nem épített eszközbeállítások alkalmazhatók. Megadhatók például az eszközt konfiguráló OMA-URI értékek Android-eszközökhöz. iOS-eszközökön importálható egy, az Apple Configuratorban létrehozott konfigurációs fájl.
További információkért lásd: [Egyéni beállítások konfigurálása](custom-settings-configure.md). Támogatott rendszerek: Android, iOS, macOS és Windows Phone 8.1.

## <a name="next-steps"></a>További lépések
Válasszon egy profiltípust a listáról az eszközkonfiguráció elkezdéséhez.
