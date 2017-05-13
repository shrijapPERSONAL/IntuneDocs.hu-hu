---
title: "Mik azok az eszközprofilok a Microsoft Intune-ban? | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikkből megismerheti az Intune-eszközprofilokat, és azt, hogy miképpen segíthetnek a vállalati eszközök kezelésében és védelmében."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: b33d8ec48c057ce1e67487d5772ca203793d8a79
ms.contentlocale: hu-hu
ms.lasthandoff: 05/10/2017


---

# <a name="what-are-microsoft-intune-device-profiles"></a>Mik azok a Microsoft Intune-eszközprofilok?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune **Eszközkonfiguráció** munkafolyamatával kezelheti az összes felügyelt eszköz beállításait és funkcióit. Ezt a munkafolyamatot leginkább a felügyelt eszközökön számtalan különféle funkció és szolgáltatás kezelését és szabályozását lehetővé tevő eszközprofilok létrehozására fogja használni.

A munkafolyamat megnyitásakor a következő lehetőségek jelennek meg:

- **Áttekintés** – Ezen az oldalon a felhasználókhoz és az eszközökhöz rendelt eszközkonfigurációk megfigyelésében segítő állapot- és egyéb jelentések láthatók.
- **Profilok kezelése** – Ebben a szakaszban hozhatók létre eszközkonfigurációs profilok. Alább megtalálható a létrehozható profiltípusok teljes listája.
- **Hitelesítésszolgáltató beállítása** – Ez a munkafolyamat végigvezet a tanúsítványok konfigurálásához szükséges lépéseken. Ez elengedhetetlen, ha Intune-tanúsítványokkal kíván dolgozni.

## <a name="getting-started"></a>Első lépések

Az eszközprofilok létrehozásának munkafolyamata a más profilokéhoz hasonló. A profilok létrehozásának módját megismerheti a [Microsoft Intune-eszközkonfigurációs profilok létrehozását ismertető](how-to-create-device-profiles.md) cikkből. Ezután olvassa el az egyes profiltípusok beállításainak létrehozásáról szóló külön cikkeket is.

Az eszközök következő funkcióit kezelheti:

## <a name="device-features"></a>Eszközfunkciók

Az eszközfunkciókkal lehet szabályozni az iOS- és macOS-eszközök funkcióit, például az AirPrintet, az értesítéseket és a megosztott eszközkonfigurációkat.
További információ: [Eszközfunkció-beállítások konfigurálása](how-to-configure-device-features.md) Támogatott rendszerek: iOS és macOS.

## <a name="device-restrictions"></a>Eszközkorlátozások
Az eszközkorlátozások révén számos kategóriában (például biztonsági, böngésző-, hardver- és adatmegosztási beállítások) szabályozhatja a felügyelt eszközökön a beállítások széles körét. Létrehozhat például egy olyan eszközkorlátozási profilt, amely megakadályozza, hogy az iOS-eszközök felhasználói hozzáférjenek az eszköz kamerájához.
További információt az [Eszközkorlátozási beállítások konfigurálása](how-to-configure-device-restrictions.md) című témakörben talál. Támogatott rendszerek: Android, iOS, macOS, Windows 10 és Windows 10 Team.

## <a name="email"></a>E-mail
Az e-mail-profilok segítségével az Exchange ActiveSyncre vonatkozó e-mail-beállításokat hozhatja létre, telepítheti és figyelheti a felügyelt eszközökön. A beállítások hozzárendelésével gondoskodhat a konzisztenciáról, csökkentheti a segélyszolgálatra beérkező hívások számát, és lehetővé teheti, hogy a végfelhasználók úgy érhessék el a céges e-maileket a személyes eszközeiken, hogy semmit sem kell beállítaniuk.
További információt talál az [E-mail beállítások konfigurálása](how-to-configure-email-settings.md) című témakörben. Támogatott rendszerek: Android, iOS, Windows Phone 8.1 és Windows 10.

## <a name="wi-fi"></a>Wi-Fi
A Wi-Fi-profilokkal vezeték nélküli hálózati beállításokat rendelhet a szervezet felhasználóihoz és eszközeihez. Wi-Fi profil hozzárendelésével a felhasználók anélkül csatlakozhatnak a vállalat Wi-Fi hálózatához, hogy azt maguknak kellene konfigurálniuk.
További információt a [Wi-Fi beállítások konfigurálása](how-to-configure-wi-fi-settings.md) című témakörben talál. Támogatott rendszerek: Android, iOS, macOS és Windows 8.1 (csak importálás).

## <a name="vpn"></a>VPN
A virtuális magánhálózatok (VPN) segítségével biztonságos távoli hozzáférést biztosíthat felhasználóinak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. VPN-profilok használatával a VPN-beállításokat a szervezet felhasználóihoz és eszközeihez rendelheti hozzá, így könnyen és biztonságosan kapcsolódhatnak a hálózathoz.
További tudnivalók: [VPN-beállítások konfigurálása](how-to-configure-vpn-settings.md).
Támogatott rendszerek: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 és Windows 10.

## <a name="education"></a>Oktatás
Itt lehet konfigurálni a Windows Vizsga alkalmazás beállításait. A beállítások konfigurálásakor az eszközön a vizsga befejezéséig nem futhat másik alkalmazás.
További tudnivalók: [Oktatási beállítások konfigurálása](how-to-configure-education-settings.md)

## <a name="certificates"></a>Tanúsítványok
Ez a profiltípus olyan, az eszközökhöz hozzárendelhető megbízható SCEP- és PKCS- tanúsítványok konfigurálását teszi lehetővé, amelyek a Wi-Fi-, VPN- és e-mail-profilok hitelesítésére használhatók.
További információt a [Tanúsítványok konfigurálása](how-to-configure-certificates.md) című témakörben talál. Támogatott rendszerek: Android, iOS, Windows Phone 8.1 Windows 8.1 és Windows 10.

## <a name="edition-upgrade"></a>Kiadásfrissítés
Ez a profiltípus lehetővé teszi a Windows 10 valamelyik verzióját futtató eszközök automatikus frissítését egy újabb kiadásra. További információt [A Windows 10 kiadásfrissítéseinek konfigurálása](how-to-configure-windows-10-edition-upgrade.md) című témakörben talál. Támogatott rendszer: csak Windows 10.

## <a name="windows-information-protection"></a>Windows Információvédelem
A Windows Információvédelem úgy segít védekezni az adatszivárgások ellen, hogy mindeközben más módon nem avatkozik bele az alkalmazott munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által munkába hozott személyes eszközökön véletlenül kiszivárogjanak, ehhez pedig nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.
További információt a [Windows Információvédelem konfigurálása](how-to-configure-windows-information-protection.md) című témakörben talál. Támogatott rendszer: csak Windows 10.

## <a name="custom"></a>Egyéni
Egyéni beállítások segítségével az Intune-ba be nem épített eszközbeállítások alkalmazhatók. Megadhatók például az eszközt konfiguráló OMA-URI értékek Android-eszközökhöz. iOS-eszközökön importálható egy, az Apple Configuratorban létrehozott konfigurációs fájl.
További információt az [Egyéni beállítások konfigurálása](how-to-configure-custom-settings.md) című témakörben talál. Támogatott rendszerek: Android, iOS, macOS és Windows Phone 8.1.

