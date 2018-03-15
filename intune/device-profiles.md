---
title: "Eszközprofilok az Azure-beli Microsoft Intune-ban | Microsoft Docs"
description: "A különféle Microsoft Intune-eszközprofilok áttekintése a funkciók, korlátozások, e-mail, Wi-Fi, VPN, oktatás, tanúsítványok, Windows 10-frissítés, BitLocker és Windows Defender, Windows Információvédelem és az Azure Portal-beli egyéni eszközkonfigurációs beállítások ismertetésével. Ezeket a profilokat vállalati adatai és eszközei kezelésére és védelmére használhatja."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 79ca6eaf22233dd6d024a28e456e57a8a74d02aa
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Mik azok a Microsoft Intune-eszközprofilok?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune olyan beállításokat és funkciókat kínál, amelyeket Ön engedélyezhet vagy letilthat a vállalatához tartozó különböző eszközökön. Ezek a beállítások és funkciók profilok használatával kezelhetők. Néhány példa profilok használatára: 

- A vállalati Wi-Fi-hez különböző eszközöknek hozzáférést biztosító Wi-Fi-profil
- A vállalati hálózaton belüli VPN-kiszolgálóhoz különböző eszközöknek hozzáférést biztosító VPN-profil

Ez a témakör áttekintést nyújt az eszközeihez létrehozható különféle profilokról. Ezeket a profilokat az eszközök egyes funkcióinak engedélyezésére vagy letiltására használhatja.

## <a name="before-you-begin"></a>Előkészületek
A rendelkezésre álló funkciók megismeréséhez nyissa meg az [Azure Portalt](https://portal.azure.com), majd saját Intune-forrását. 

Az **Eszközkonfiguráció** a következő lehetőségeket foglalja magában:

- **Áttekintés**: Listázza a profilok állapotát, és további részleteket ad meg a felhasználókhoz és eszközökhöz rendelt profilokról
- **Kezelés**: Eszközprofilok létrehozása és a profilon belül futtatandó egyéni [PowerShell-parancsfájlok](intune-management-extension.md) feltöltése
- **Figyelés**: Sikeres végrehajtás vagy hiba feltárása a profil állapotában és a profilhoz tartozó naplók megtekintése
- **Beállítás**: Hitelesítésszolgáltató (SCEP vagy PFX) megadása, vagy távközlésiköltség-kezelés engedélyezése a profilban

## <a name="create-the-profile"></a>A profil létrehozása

Az [Eszközprofilok létrehozása](device-profile-create.md) című útmutató lépésenként ismerteti egy profil létrehozásának menetét. 

## <a name="device-features-profile"></a>Eszközfunkciók profil

Az [eszközfunkciókkal](device-features-configure.md) szabályozhatók az iOS- és macOS-eszközök funkciói, például az AirPrint, az értesítések és a megosztott eszközkonfigurációk.

Ez a funkció a következőket támogatja:  
- iOS 
- macOS

## <a name="device-restrictions-profile"></a>Eszközkorlátozások profil
Az [eszközkorlátozásokkal](device-restrictions-configure.md) kezelhető a biztonság, a hardver, az adatmegosztás és az eszközök több beállítása. Létrehozható például egy olyan eszközkorlátozási profil, amely megakadályozza, hogy az iOS-eszközök felhasználói használják az eszköz kameráját. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- macOS
- Windows 10
- Windows 10 Team

## <a name="email-profile"></a>E-mail-profil
Az [E-mail-beállítások](email-settings-configure.md) profil Exchange ActiveSync e-mail-beállítások létrehozását, hozzárendelését és figyelését végzi az eszközökön. Az e-mail-profilok segítenek biztosítani a konzisztenciát, csökkenthetik a segélykérő hívások számát, valamint saját kötelező beállítások nélkül is lehetővé teszik a végfelhasználók számára, hogy az eszközükön hozzáférjenek a céges postafiókjukhoz. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="wi-fi-profile"></a>Wi-Fi profil
A [Wi-Fi-beállítások](wi-fi-settings-configure.md) a vezeték nélküli hálózat beállításait rendeli hozzá felhasználókhoz és eszközökhöz. A Wi-Fi-profil hozzárendelése után a felhasználók anélkül is hozzáférhetnek a céges Wi-Fihez, hogy ők maguk konfigurálnák azt. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- macOS
- Windows 8.1 (csak importálás)

## <a name="vpn-profile"></a>VPN-profil
A [VPN-beállítások](vpn-settings-configure.md) használatával a VPN-profilokat a vállalati felhasználókhoz és eszközökhöz rendelheti hozzá, így azok könnyen és biztonságosan kapcsolódhatnak a hálózathoz. 

A virtuális magánhálózatok (VPN) biztonságos távoli hozzáférést biztosítanak a felhasználóknak a vállalati hálózathoz. Az eszközök egy VPN-csatlakozási profil használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="education-profile"></a>Oktatási profil
Az [Oktatási beállítások](education-settings-configure.md) segítségével lehet konfigurálni a [Windows Vizsga alkalmazás](https://education.microsoft.com/gettrained/win10takeatest) beállításait. A beállítások konfigurálásakor az eszközön a vizsga befejezéséig nem futhat másik alkalmazás.

## <a name="certificates-profile"></a>Tanúsítványok profil
A [Tanúsítványok](certificates-configure.md) olyan, az eszközökhöz hozzárendelhető megbízható SCEP- és PKCS- tanúsítványok konfigurálását teszi lehetővé, amelyek a Wi-Fi-, VPN- és e-mail-profilok hitelesítésére használhatók.

Ez a funkció a következőket támogatja: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="edition-upgrade-profile"></a>Kiadásfrissítési profil
A [Windows 10 kiadásfrissítések](edition-upgrade-configure-windows-10.md) lehetővé teszi a Windows 10 egyes verzióit futtató eszközök újabb kiadásra történő automatikus frissítését.

Ez a funkció csak a Windows 10 rendszert támogatja

## <a name="endpoint-protection-profile"></a>Végpontvédelmi profil
A [Végpontvédelmi beállítások Windows 10-hez](endpoint-protection-windows-10.md) a BitLocker és a Windows Defender beállításait konfigurálja Windows 10 rendszerű eszközökön.

Ez a funkció csak a Windows 10 rendszert támogatja

## <a name="windows-information-protection-profile"></a>Windows információvédelem profil
A [Windows Információvédelem](windows-information-protection-configure.md) úgy segít védekezni az adatszivárgások ellen, hogy mindeközben nem avatkozik bele az alkalmazottak munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által a munkahelyen használt személyes eszközökön véletlenül kiszivárogjanak. Ehhez nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.

Ez a funkció csak a Windows 10 rendszert támogatja

## <a name="custom-profile"></a>Egyéni profil
Az [Egyéni beállítások](custom-settings-configure.md) segítségével egyebek mellett az Intune-ba be nem épített eszközbeállítások alkalmazhatók. Például OMA-URI értékek adhatók meg Android-eszközökön. iOS-eszközökön importálható egy, az Apple Configuratorban létrehozott konfigurációs fájl. 

Ez a funkció a következőket támogatja: 

- Android
- iOS
- macOS
- Windows Phone 8.1