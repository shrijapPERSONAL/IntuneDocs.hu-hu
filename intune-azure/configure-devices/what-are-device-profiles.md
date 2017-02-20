---
title: "Mik azok az eszközprofilok a Microsoft Intune-ban? | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikkből megismerheti az Intune-eszközprofilokat, és azt, hogy miképpen segíthetnek a vállalati eszközök kezelésében és védelmében."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 0e126c067b5c212ae5bfe1cf69e01128a00b1c8e


---

# <a name="what-are-device-profiles"></a>Mik azok az eszközprofilok?
<!--- This topic doesn't really answer the topic title: What are device profiles?" It needs to answer that question, then it can go on to discuss what profiles are in Intune and how to use them. Linda--->

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune **Eszközök konfigurálása** munkafolyamatával kezelheti az összes felügyelt eszköz beállításait és funkcióit.

A munkafolyamat megnyitásakor a következő lehetőségek jelennek meg:

- **Áttekintés** – Ezen az oldalon a felhasználókhoz és az eszközökhöz rendelt eszközkonfigurációk megfigyelésében segítő állapot- és egyéb jelentések láthatók.
- **Profilok kezelése** – Ebben a szakaszban hozhatók létre eszközkonfigurációs profilok. Alább megtalálható a létrehozható profiltípusok teljes listája.
- **Hitelesítésszolgáltató beállítása** – Ez a munkafolyamat végigvezet a tanúsítványok konfigurálásához szükséges lépéseken. Ez elengedhetetlen, ha Intune-tanúsítványokkal kíván dolgozni.

## <a name="getting-started"></a>Első lépések

Az eszközprofilok létrehozásának munkafolyamata a más profilokéhoz hasonló. A profilok létrehozásának módját megismerheti a [Microsoft Intune-eszközkonfigurációs profilok létrehozását ismertető](/intune-azure/configure-devices/how-to-create-device-profiles) cikkből. Ezután olvassa el az egyes profiltípusok beállításainak létrehozásáról szóló külön cikkeket is.

Az eszközök következő funkcióit kezelheti:

## <a name="device-restrictions"></a>Eszközkorlátozások
Az eszközkorlátozások révén számos, Ön által kezelt kategóriában válik lehetővé a beállítások és funkciók széles körének szabályozása, például a biztonságra, a böngészőre, a hardverre és az adatmegosztásra vonatkozó beállítások esetében. Létrehozhat például egy olyan eszközkorlátozási profilt, amely megakadályozza, hogy az iOS-eszközök felhasználói hozzáférjenek az eszköz kamerájához.
További információt az [Eszközkorlátozási beállítások konfigurálása](how-to-configure-device-restrictions.md) című témakörben talál. Támogatott rendszerek: Android, iOS, macOS, Windows 10 és Windows 10 Team.

## <a name="email"></a>E-mail
Az e-mail-profilokkal az Exchange ActiveSync-re vonatkozó e-mail-beállításokat hozhat létre, telepíthet és figyelhet az Ön által kezelt eszközökön. A beállítások létrehozásával gondoskodhat az egységességről, csökken a segélyszolgálatra beérkező hívások száma, és a végfelhasználók úgy érhetik el a vállalati e-maileket a személyes eszközeiken, hogy semmit sem kell beállítaniuk.
További információt talál az [E-mail beállítások konfigurálása](how-to-configure-email-settings.md) című témakörben. Támogatott rendszerek: Android, iOS, Windows Phone 8.1 és Windows 10.

## <a name="wi-fi"></a>Wi-Fi
A Wi-Fi-profilokkal vezeték nélküli hálózati beállításokat adhat meg a szervezet felhasználói és eszközei számára. Wi-Fi profil központi telepítése esetén a felhasználók anélkül csatlakozhatnak a vállalati Wi-Fi hálózathoz, hogy azt maguknak kellene konfigurálniuk.
További információt a [Wi-Fi beállítások konfigurálása](how-to-configure-wi-fi-settings.md) című témakörben talál. Támogatott rendszerek: Android, iOS, macOS és Windows 8.1 (csak importálás).

## <a name="vpn"></a>VPN
A virtuális magánhálózatok (VPN) segítségével biztonságos távoli hozzáférést biztosíthat felhasználóinak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. VPN-profilok beállításával a szervezet felhasználóira és eszközeire alkalmazhatja a VPN-beállításokat, így könnyen és biztonságosan kapcsolódhatnak a hálózathoz.
További tudnivalók: [VPN-beállítások konfigurálása](how-to-configure-vpn-settings.md).
Támogatott rendszerek: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 és Windows 10.

## <a name="certificates"></a>Tanúsítványok
Ez a profiltípus olyan, az eszközökhöz hozzárendelhető megbízható SCEP- és PKCS- tanúsítványok konfigurálását teszi lehetővé, amelyek a Wi-Fi-, VPN- és e-mail-profilok hitelesítésére használhatók.
További információt a [Tanúsítványok konfigurálása](how-to-configure-certificates.md) című témakörben talál. Támogatott rendszerek: Android, iOS, Windows Phone 8.1 Windows 8.1 és Windows 10.

## <a name="education"></a>Oktatás
Segít abban, hogy oktatási környezetben megadja az iOS-eszközökön használandó megfelelő tanúsítványokat.
További információt [Az Intune oktatási beállításainak konfigurálása iOS-eszközökhöz](education-settings-for-ios.md) című témakörben talál. Támogatott rendszer: csak iOS.

## <a name="edition-upgrade"></a>Kiadásfrissítés
Ez a profiltípus lehetővé teszi a Windows 10 valamelyik verzióját futtató eszközök automatikus frissítését egy újabb kiadásra. További információt [A Windows 10 kiadásfrissítéseinek konfigurálása](how-to-configure-windows-10-edition-upgrade.md) című témakörben talál. Támogatott rendszer: csak Windows 10.

## <a name="windows-information-protection"></a>Windows Információvédelem
A Windows Információvédelem úgy segít védekezni az adatszivárgások ellen, hogy mindeközben más módon nem avatkozik bele az alkalmazott munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által munkába hozott személyes eszközökön véletlenül kiszivárogjanak, ehhez pedig nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.
További információt a [Windows Információvédelem konfigurálása](how-to-configure-windows-information-protection.md) című témakörben talál. Támogatott rendszer: csak Windows 10.

## <a name="custom"></a>Egyéni
Egyéni beállítások segítségével az Intune-ba be nem épített eszközbeállítások alkalmazhatók. Megadhatók például az eszközt konfiguráló OMA-URI értékek Android-eszközökhöz. iOS-eszközökön importálható egy, az Apple Configuratorban létrehozott konfigurációs fájl.
További információt az [Egyéni beállítások konfigurálása](how-to-configure-custom-settings.md) című témakörben talál. Támogatott rendszerek: Android, iOS, macOS és Windows Phone 8.1.



<!--HONumber=Feb17_HO1-->


