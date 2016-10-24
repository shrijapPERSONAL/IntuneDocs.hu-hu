---
title: "Windows 10-es házirend-beállítások | Microsoft Intune"
description: "Az ebben a témakörben ismertetett szabályzatbeállítások segítségével konfigurálhatja a regisztrált asztali Windows 10- és Windows 10 Mobile-eszközök beépített és egyéni beállításait."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8522406a3c73746b09616c3ec917464cf751312
ms.openlocfilehash: 6e482beb5e2edce648ecb6f1821baa6214fa0f2f


---

# A Microsoft Intune-ban regisztrált Windows 10-eszközökre vonatkozó Intune-házirendbeállítások

Ez a témakör ismerteti azokat az Intune-házirendbeállításokat, amelyeket Windows 10-eszközök felügyeletére használhat. A témakört a [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) című témakörben ismertetett eljárásokkal együtt olvassa el a Windows 10 asztali verziójú és Windows 10 Mobile rendszerű eszközök beépített és egyéni beállításainak konfigurálásához. E szabályzatok nem használhatók olyan számítógépeken, amelyeken az [Intune PC-ügyfélszoftvert](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune) fut.

Két szabályzattípus közül választhat:

- **Egyéni szabályzat** – A Microsoft Intune a Windows 10 és a Windows 10 Mobile rendszerhez készült **egyéni szabályzatával** OMA-URI (Open Mobile Alliance egységes erőforrás-azonosító) beállítások telepíthetők, amelyek segítségével szabályozhatók az eszközök funkciói. A Windows 10 számos beállítást tesz elérhetővé a [Szabályzat-konfigurációszolgáltatón (Policy Configuration Service Provider, Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) keresztül.
- **Általános konfigurációs szabályzat** – Ezt a szabályzattípust használja, ha a Microsoft Intune-hoz biztosított beépített listából szeretne beállításokat választani.

## Egyéni szabályzatbeállítások

Egyéni szabályzatokban adja meg a következő beállításokat:

## &nbsp;&nbsp;&nbsp;Általános

Adja meg a szabályzat nevét és – szükség esetén – a leírását, hogy könnyebben megtalálja az Intune-konzolon.

## &nbsp;&nbsp;&nbsp;OMA-URI-beállítások

Minden egyes hozzáadni kívánt OMA-URI-beállításhoz adja meg a következő információkat. A rendelkezésre álló beállítások áttekintését a jelen témakör [Windows 10 URI-beállítások](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) című részében találja: 

- **Beállítás neve** – Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.
- **Beállítás leírása** – Itt adhatja meg a beállítás leírását (nem kötelező).
- **Adattípus** – Válasszon egyet a következő lehetőségek közül:
    - **Karakterlánc**
    - **Karakterlánc (XML)**
    - **Dátum és időpont**
    - **Egész szám**
    - **Lebegőpontos szám**
    - **Logikai**
- **OMA-URI (megkülönbözteti a kis- és nagybetűket)** – Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.
- **Érték** – Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket.

### Példa
Az alábbi képernyőképen a **Connectivity/AllowVPNOverCellular** beállítást engedélyezték. Ez lehetővé teszi, hogy a Windows 10-es eszköz VPN-kapcsolatot nyisson meg mobilhálózaton keresztül.

> ![VPN-beállításokat tartalmazó egyéni szabályzat – példa](./media/custom-policy-example.png)

## Windows 10 URI-beállítások
Ebben a szakaszban az **egyéni Windows 10-szabályzatokkal** konfigurálható OMA-URI beállításokat ismerheti meg.

## &nbsp;&nbsp;&nbsp;Házirend

|Házirend neve és URI azonosítója|Részletek|
|---------------|------------|-----------|
|**Automatikus frissítés engedélyezése**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Csak asztali verziók<br>**Adattípus:** Egész szám<br />**Értékek:** **0** - **5** (alapértelmezett: **1**)|
|**Telepítés napjának ütemezése**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Csak mobil verziók<br>**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – minden nap (alapértelmezés)<br>**1** – vasárnap<br>**2** – hétfő<br>**3** – kedd<br>**4** – szerda<br>**5** – csütörtök<br>**6** – péntek<br>**7** – szombat|
|**Telepítés időpontjának ütemezése**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – **23** óra (**0** óra az éjfél) (alapértelmezett: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – a felhasználó nem állíthatja be a jelszó türelmi idejének időzítőjét; az érték „minden alkalommal” lesz<br>**1** – a felhasználó beállíthatja a jelszó türelmi idejének időzítőjét (alapértelmezés)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Nem engedélyezi a **Wi-Fi kapcsolat használatát**.<br>**1** – **Engedélyezi a Wi-Fi kapcsolat használatát** (alapértelmezés).|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Asztali és mobil verziók<br>**Adattípus:** Egész szám<br />**Értékek:** **0** – Internetmegosztás tiltása, **1** – Internetmegosztás engedélyezése (alapértelmezett)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Az MDM által kiépítettektől eltérő Wi-Fi kapcsolatok nem engedélyezettek.<br>**1** – Az MDM által kiépítettektől eltérő hálózati SSID-k hozzáadása engedélyezett (alapértelmezés).|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Asztali és mobil verziók<br>**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Nem engedélyezett (csak Enterprise rendszerekre vonatkozó beállítás)<br>**1** – Korlátozott<br>**2** – Teljes (alapértelmezés)<br>**3** – Teljes és diagnosztikai információk|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Nem engedélyezett<br>**1** – Csak beállítások (alapértelmezés)<br>**2** – Beállítások és kísérletezés|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Lopásgátló üzemmód tiltása<br>**1** – Felhasználói beállítás szerint (alapértelmezés)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – VPN tiltása mobileszközökön<br>**1** – A VPN bármilyen kapcsolatot használhat, beleértve a mobilkapcsolatot is (alapértelmezés)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Nem engedélyezi a felhasználónak a Bluetooth aktiválását.<br>**1** – Fenntartva. A Bluetooth bekapcsolásának és konfigurálásának engedélyezése a felhasználónak (nem támogatott Windows Phone 8.1 MDM, EAS, a Windows 10 asztali verziója és Windows 10 Mobile esetén).<br>**2** – Engedélyezett. A Bluetooth bekapcsolásának és konfigurálásának engedélyezése a felhasználónak (alapértelmezés)|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – Barangolás tiltása, **1** – Barangolás engedélyezése (alapértelmezett)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** (alapértelmezett), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0**, **1** (alapértelmezett)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** (alapértelmezett), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** (alapértelmezett), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** (alapértelmezett), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0**, **1** (alapértelmezett)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** (alapértelmezett), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** (alapértelmezett), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Nem engedélyezett<br>A nyílt kiterjesztett szótár ki van kapcsolva.<br>A felhasználók nem tehetik a következőket:<br>- Új nyílt bővített szótár felvétele<br />- Új keresésintegrációs konfigurációs fájl felvétele<br>- A felhőben való használatra jelölt szolgáltatás használata<br>- Felhasználó által regisztrált szó küldése.<br>**1** – Engedélyezés<br>A nyílt kiterjesztett könyvtár alapértelmezés szerint felvehető és használható. A keresésintegráció funkció is alapértelmezés szerint használható.<br>A felhasználó a következőket teheti:<br>A felhőben való használatra jelölt szolgáltatás használata.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – A helytelen átalakítások naplózása ki van kapcsolva.<br>**1** – A helytelen átalakítások naplózása be van kapcsolva (alapértelmezett)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Egyetlen karakter sincs szűrve (alapértelmezés)<br>**1** – A Shift JIS-karakterek kivételével minden karaktert szűr a rendszer|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br />**0** – Egyetlen karakter sincs szűrve (alapértelmezés)<br>**1** – A JIS0208-karakterek kivételével minden karaktert szűr a rendszer|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Egyetlen karakter sincs szűrve (alapértelmezés)<br>**1** – A JIS0208- és az EUDC-karakterek kivételével minden karaktert szűr a rendszer|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Felnőtt tartalom szigorú, legmagasabb fokú szűrése<br>**1** – Felnőtt tartalom mérsékelt, közepes szintű szűrése (az érvényes keresési eredményeket nem szűri a rendszer – alapértelmezés)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**Kezdőméret kényszerítése**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – méretmódosítás engedélyezése a felhasználó számára (alapértelmezés)<br>**1** – nem teljes képernyő kényszerítése<br>**2** – teljes képernyő kényszerítése|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0**: A frissítés késleltetésének mellőzése (maradás az aktuális fejlesztési ágban (CB) – alapértelmezés)<br>**1**: A frissítések késleltetésének engedélyezése (az eszköz az aktuális üzleti ág (CBB) szabályait követi)<br />A részletekért lásd:<br>[Bevezetés a Windows 10 karbantartásába](https://technet.microsoft.com/library/mt598226.aspx)<br>[Felkészülés a Windows 10 központi telepítésére](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Asztali és mobil verziók<br>**Leírás:** A szoftverfrissítéseket 4 héttel késleltető házirend.<br />**Adattípus:** Egész szám<br />**Értékek:**<br> **0**: A frissítések azonnali alkalmazása (alapértelmezett)<br>**1**-**4**: a rendszer ennyi héttel késlelteti a szoftverfrissítéseket.<br />A részletekért lásd:<br>[Bevezetés a Windows 10 karbantartásába](https://technet.microsoft.com/library/mt598226.aspx)<br>[Felkészülés a Windows 10 központi telepítésére](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Asztali és mobil verziók<br>**Leírás:** A funkciófrissítéseket 8 hónappal késleltető házirend.<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0**: A frissítések azonnali alkalmazása (alapértelmezett)<br>**1**-**8**: a rendszer ennyi hónappal késlelteti a funkciófrissítéseket.<br />A részletekért lásd:<br>[Bevezetés a Windows 10 karbantartásába](https://technet.microsoft.com/library/mt598226.aspx)<br>[Felkészülés a Windows 10 központi telepítésére](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Asztali és mobil verziók<br>**Leírás:** Lehetővé teszi az eszköznek a frissítések letöltésének leállítását 5 hétre.<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0**: A frissítések azonnali alkalmazása (alapértelmezett)<br>**1**: A frissítések és verziófrissítések szüneteltetése (5 hét után lejár)|

## &nbsp;&nbsp;&nbsp;Windows Defender

|Házirend neve és URI azonosítója|Részletek|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Minden fájl figyelése (alapértelmezett)<br>**1** – Bejövő fájlok figyelése<br>**2** – Kimenő fájlok figyelése|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** - **90** – Megadja, hogy a kártevő szoftvereket mennyi ideig őrizze a rendszer<br>**Alapértelmezett:** **0** – végleg a karantén mappában tartja, automatikusan nem távolítja el|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**1** – Gyorsvizsgálat (alapértelmezés)<br>**2** – Teljes vizsgálat|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Mindennap (alapértelmezés)<br>**1** – hétfő<br>**2** – kedd<br>**3** – szerda<br>**4** – csütörtök<br>**5** – péntek<br>**6** – szombat<br>**7** – vasárnap<br>**8** – Nincs ütemezett vizsgálat|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (alapértelmezés)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Karbantartási időszak|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Csak asztali verziók<br>**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (alapértelmezés)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** - **100** (alapértelmezett: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Csak asztali verziók<br />**Adattípus:** Egész szám<br>**Értékek:** **0** – nem engedélyezett (alapértelmezett), **1** – engedélyezett|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett (alapértelmezett), **1** – engedélyezett|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett, **1** – engedélyezett (alapértelmezett) – Ha az engedélyezett értéket állítja be, akkor is fut, amikor az RTP be van kapcsolva|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Aláírások időközönkénti ellenőrzése kikapcsolva<br>**1** – Aláírások ellenőrzése óránként<br>**2** – Ellenőrzés 2 óránként, stb.<br>**24** – Ellenőrzés naponta<br>**Alapértelmezett érték:** 8 – Ellenőrzés 8 óránként|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett **1** – engedélyezett (alapértelmezett)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Mindig kérdezzen rá (alapértelmezés)<br>**1** – Biztonságos minták automatikus küldése<br>**2** – Soha ne küldjön<br>**3** – Az összes minta automatikus küldése|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Csak asztali verziók<br />**Adattípus:** Karakterlánc<br />**Értékek:**<br>*&lt;a kiterjesztések listája, pontosvesszővel elválasztva&gt;* Például: **obj;lib**<br>**Alapértelmezés:** a bővítmények nincsenek kizárva|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Csak asztali verziók<br />**Adattípus:** Karakterlánc<br />**Értékek:**<br />*&lt;az elérési utak listája pontosvesszővel elválasztva&gt;*<br />Például: **c:\test;c:\test1.exe**<br />**Alapértelmezett érték:** Nincsenek elérési utak kizárva|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Csak asztali verziók<br />**Adattípus:** Karakterlánc<br />**Értékek:**<br>*&lt;az elérési utak listája pontosvesszővel elválasztva&gt;*<br>Például: **c:\test.exe;c:\test1.exe**<br>**Alapértelmezett érték:** Nincs kizárt eljárás|

## &nbsp;&nbsp;&nbsp;Edge böngésző

|Házirend neve és URI azonosítója|Részletek|
|---------------|------------|-----------|
|**Böngésző engedélyezése**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Csak mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0**: böngészés kikapcsolva, **1**: böngészés bekapcsolva (alapértelmezett)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0**: Ne jelenjenek meg javaslatok, **1**: Javaslatok megjelenítése (alapértelmezett)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0**: letiltva (az intranetes helyek megnyitása az Edge böngészőben – alapértelmezés)<br>**1** – Engedélyezve (az intranetes helyek megnyitása az Internet Explorerben).|
|**Követés letiltásának engedélyezése**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|(Asztali és mobil verziók)<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – Letiltva (nem küld követést tiltó fejlécet - alapértelmezett); **1** – Engedélyezve (követést tiltó fejléc küldése)|
|**SmartScreen konfigurálása**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – nem engedélyezett, **1** – engedélyezett (alapértelmezett)|
|**Előugró ablakok engedélyezése**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – Előugró ablakok tiltása (alapértelmezett), **1** – Előugró ablakok engedélyezése|
|**Cookie-k engedélyezése**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Cookie-k engedélyezése az összes webhelyről (alapértelmezett)<br>**1** – Csak a harmadik felektől származó cookie-k letiltása<br>**2** – Az összes cookie letiltása|
|**Jelszó mentésének engedélyezése**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Asztali és mobil verziók<br />**Adattípus:** Egész szám<br />**Értékek:**<br>**0** – Jelszókezelő letiltva <br>**1** – Jelszókezelő engedélyezve (alapértelmezés)|
|**Automatikus kitöltés engedélyezése**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Csak asztali verziók<br />**Adattípus:** Egész szám<br />**Értékek:** **0** – Tiltott (alapértelmezett), **1** – Engedélyezett|
|**Vállalati webhelylista konfigurálása**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Csak asztali verziók<br />**Adattípus:** Karakterlánc<br />**Értékek:<br> **0** – Nincs beállítva<br> **1** – IE vállalati üzemmód webhelylistájának használata, ha be van állítva (alapértelmezett)<br>**2** – A vállalati webhelylista helyének meghatározása|

## Az általános konfigurációs szabályzat beállításai

A Microsoft Intune Windows 10-es eszközökhöz készült **általános konfigurációs szabályzatát** regisztrált asztali Windows 10 és Windows 10 Mobile rendszerű eszközök beépített beállításainak konfigurálásához használhatja. 

## &nbsp;&nbsp;&nbsp;Jelszó

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Jelszó kérése az eszközzárolás feloldásához**|-|
|**Kötelező jelszótípus**|Azt határozza meg, hogy a jelszó csak számokból, vagy számokból és betűkből állhat|
|**Kötelező jelszótípus** - **Karakterkészletek minimális száma**|A következő négy karakterkészlet létezik: kisbetűk, nagybetűk, számok és szimbólumok. Ez a beállítás azt határozza meg, hogy ezen készletek közül hány elemeinek kell szerepelnie a jelszóban.|
|**Jelszó minimális hossza**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|Windows 10 rendszerű eszközök esetében: ha a BitLocker engedélyezett az eszközön, akkor az a megadott számú sikertelen bejelentkezési kísérlet után a BitLocker helyreállítási módjába kerül. Ha az eszközön nem engedélyezett a BitLocker, akkor ez a beállítás nem alkalmazható.<br>Windows 10 Mobile-eszközök esetében: a megadott számú sikertelen bejelentkezési kísérlet után az eszköz törlődik.|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.|
|**Jelszó lejárata (nap)**|Meghatározza, hogy mennyi idő elteltével kell módosítani a jelszót.|
|**Jelszóelőzmények megjegyzése**|Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.|
|**Korábbi jelszavak megjegyzése** - **Korábbi jelszavak újbóli használatának tiltása**|Ez a beállítás az eszköz által megjegyzett korábbi jelszavak számát határozza meg.|
|**Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**|Engedélyezése esetén a felhasználónak meg kell adnia egy jelszót az eszköz zárolásának feloldásához. (csak a Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Titkosítás

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Mobileszköz titkosításának kötelezővé tétele**|Titkosítás engedélyezése a megcélzott eszközökön.<br>(csak a Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Rendszer

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Képernyőfelvétel-készítés használatának engedélyezése**|Engedélyezése esetén a felhasználó rögzítheti képként a képernyőn látható tartalmat. (csak a Windows 10 Mobile)|
|**Regisztráció manuális törlésének engedélyezése**|Lehetővé teszi a felhasználó számára a munkahelyi fiók manuális törlését az eszközről.|
|**Főtanúsítvány manuális telepítésének engedélyezése**|A Windows 10 Mobile verzióra vonatkozik|
|**Diagnosztikai és használati adatok küldésének engedélyezése a Microsoft felé**|Lehetséges értékek:<br><br>**Nem** – Az eszköz nem küld adatokat a Microsoftnak.<br>**Alapszintű** – Az eszköz korlátozott információt küld a Microsoftnak<br>**Bővített** – Az eszköz bővebb diagnosztikai adatokat küld a Microsoftnak<br>**Teljes (ajánlott)** – A **Bővített** beállítással küldött adatok mellett az eszköz állapotával kapcsolatos információkat is küld.|


## &nbsp;&nbsp;&nbsp;Fiók és szinkronizálás

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Microsoft-fiók használatának engedélyezése**|Lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.|
|**Nem Microsoft-fiókok manuális felvételének engedélyezése**|Lehetővé teszi, hogy a felhasználó olyan e-mail fiókokat vegyen fel az eszközön, amelyek nincsenek Microsoft-fiókhoz társítva.|
|**Beállítások szinkronizálásának engedélyezése Microsoft-fiók esetén**|Lehetővé teszi a Microsoft-fiókhoz kapcsolódó eszköz- és alkalmazásbeállítások szinkronizálását az eszközök között.|

## &nbsp;&nbsp;&nbsp;Microsoft Edge

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Webböngésző használatának engedélyezése**|Engedélyezi az Edge webböngésző használatát az eszközön.<br>(csak a Windows 10 Mobile)|
|**Keresési javaslatok engedélyezése a címsorban**|Lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása közben.|
|**Intranetes adatforgalom küldésének engedélyezése az Internet Explorerbe**|Engedélyezi a felhasználók számára az intranetes webhelyek megnyitását az Internet Explorerben.<br>(csak a Windows 10 asztali verzió)|
|**Követés letiltásának engedélyezése**|Lehetővé teszi az Edge böngésző számára a Do Not Track (Követés letiltása) fejlécek küldését a felhasználók által meglátogatott webhelyeknek.|
|**SmartScreen engedélyezése**|-|
|**Active Scripting engedélyezése**|A parancsprogramok, például a JavaScriptek futtatásának engedélyezése az Edge böngészőben.|
|**Előugró ablakok engedélyezése**|Csak a Windows 10 asztali verzióra vonatkozik|
|**Cookie-k engedélyezése**|-|
|**Automatikus kitöltés engedélyezése**|Engedélyezi a felhasználók számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását.<br>(csak a Windows 10 asztali verzió)|
|**Jelszókezelő engedélyezése**|Az Edge böngésző Jelszókezelő szolgáltatásának engedélyezése vagy letiltása.|
|**Vállalati üzemmód webhelylistájának helye**|Megadja, hogy hol található a Vállalati üzemmódban megnyitott webhelyek listája. Ezt a listát a felhasználók nem szerkeszthetik.<br>(csak a Windows 10 asztali verzió)|

## &nbsp;&nbsp;&nbsp;Alkalmazások

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Alkalmazástároló használatának engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|



## &nbsp;&nbsp;&nbsp;Mobil

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Adatroaming engedélyezése**|Hálózatok közötti barangolás engedélyezése adatok elérése közben.|
|**VPN engedélyezése mobilhálózaton**|Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózat használata esetén.|
|**VPN engedélyezése mobilhálózati roaming esetén**|Azt szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózati roaming esetén.|

## &nbsp;&nbsp;&nbsp;Hardver

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|
|**Kamera használatának engedélyezése**|-|
|**Cserélhető tároló használatának engedélyezése**|Meghatározza, hogy az eszközzel használható-e külső tárolóeszköz, például SD-kártya.|
|**Wi-Fi használatának engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**Internetmegosztás engedélyezése**|Az internetmegosztás engedélyezése az eszközön.|
|**Manuális Wi-Fi konfiguráció engedélyezése**|Azt szabályozza, hogy a felhasználó konfigurálhat-e saját Wi-Fi kapcsolatokat, vagy csak a Wi-Fi profillal konfigurált kapcsolatokat használhatja.<br>(csak a Windows 10 Mobile)|
|**Wi-Fi elérési pontokhoz való automatikus csatlakozás engedélyezése**|Az ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozás és a kapcsolódáshoz szükséges használati feltételek automatikus elfogadásának engedélyezése az eszközön.|
|**Földrajzi hely meghatározásának engedélyezése**|Meghatározza, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.|
|**NFC használatának engedélyezése**|Engedélyezi az eszköz kis hatótávolságú kommunikációs (NFC) funkciójának használatát.|
|**Bluetooth használatának engedélyezése**|-|
|**Bluetooth-észlelhetőség engedélyezése**|Észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök által.|
|**Bluetooth-hirdetés engedélyezése**|Engedélyezi, hogy az eszközök hirdetéseket fogadjanak Bluetooth-on keresztül.|
|**Telefon alaphelyzetbe állításának engedélyezése**|Azt szabályozza, hogy a felhasználó visszaállíthatja-e az eszköz gyári beállításait.|
|**USB-kapcsolat engedélyezése**|Azt szabályozza, hogy az eszközök elérhetnek-e külső tárolóeszközöket USB-kapcsolaton keresztül.|
|**Lopásgátló üzemmód engedélyezése**|Annak beállítása, hogy engedélyezve van-e a Windows lopásgátló üzemmódja.|

## &nbsp;&nbsp;&nbsp;Jellemzők

|Beállítás neve|További információ (ha szükséges)|
|----------------|----------------------|---------------------|
|**Másolás és beillesztés használatának engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**Hangrögzítés engedélyezése**|Csak a Windows 10 Mobile verzióra vonatkozik|
|**A Cortana engedélyezése**|A Cortana beszédfelismerési asszisztens engedélyezése vagy letiltása.|
|**Műveletközponti értesítések engedélyezése**|Műveletközponti értesítések engedélyezése vagy letiltása az eszköz zárolási képernyőjén.<br>(csak a Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Windows Defender

Ezek a beállítások csak a Windows 10 asztali verziójában érvényesek.

|Beállítás neve|További információ (ha szükséges)|
|-|-|
|**Valós idejű figyelés engedélyezése**|Engedélyezi a kártevők, kémprogramok és más nemkívánatos szoftverek valós idejű vizsgálatát.|
|**Viselkedésfigyelés engedélyezése**|Engedélyezi, hogy a Defender gyanús tevékenységekre utaló ismert mintákat keressen az eszközökön.|
|**Hálózatfelügyeleti rendszer engedélyezése**|A hálózatvizsgáló rendszer (NIS) a Microsoft Endpoint Protection-központtól származó ismert biztonsági rések aláírásai alapján észleli és blokkolja a kártékony hálózati forgalmat, ezáltal segíti az eszközök védelmét a hálózati támadásokkal szemben.|
|**Minden letöltött fájl vizsgálata**|Meghatározza, hogy a Defender az internetről letöltött összes fájlt megvizsgálja-e.|
|**Szkriptek ellenőrzésének engedélyezése**|Engedélyezi a Defender számára az Internet Explorer által használt parancsfájlok vizsgálatát.|
|**A fájl- és programtevékenység figyelése**|Engedélyezése esetén a Defender megfigyelheti a fájl- és programtevékenységet az eszközökön.|
|**Ártalmatlanított kártevő szoftverek követése (nap)**|A megadott számú napig engedélyezi a Defender számára az ártalmatlanított kártevők további követését a korábban érintett eszközök manuális ellenőrzése céljából. Ha a napok számát **0**-ra állítja, a kártevő a karanténban marad, és a rendszer nem távolítja el automatikusan. |
|**Ügyfél-kezelőfelület elérésének engedélyezése**|Azt szabályozza, hogy a Windows Defender kezelőfelülete rejtett legyen-e a végfelhasználók számára.<br>Módosítás esetén a beállítás a végfelhasználó számítógépének következő újraindításakor lép érvénybe.|
|**Napi gyors vizsgálat ütemezése**|Minden nap a választott időben végzett gyorsvizsgálat beütemezését teszi lehetővé.|
|**Rendszervizsgálat ütemezése**|A választott napokon és időpontban rendszeresen végzett teljes vagy gyors rendszervizsgálat beütemezését teszi lehetővé.|
|**CPU-használatát korlátozása a vizsgálatok alatt**|Lehetővé teszi a vizsgálatok processzorhasználatának korlátozását (**1**%-tól **100**%-ig).|
|**Archív fájlok vizsgálata**|Engedélyezi a Defender számára az archív fájlok – például ZIP- vagy CAB-fájlok – vizsgálatát.|
|**E-mail üzenetek vizsgálata**|Engedélyezi a Defender számára az eszközre érkező e-mailek azonnal vizsgálatát.|
|**Cserélhető adathordozók vizsgálata**|Engedélyezi a Defender számára a cserélhető meghajtók, például a pendrive-ok vizsgálatát.|
|**Csatlakoztatott hálózati meghajtók vizsgálata**|Engedélyezi a Defender számára a csatlakoztatott hálózati meghajtókon tárolt fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.|
|**Hálózati megosztott mappákból megnyitott fájlok vizsgálata**|Engedélyezi a Defender számára a megosztott hálózati meghajtókon található (például az UNC elérési útvonalon megnyitott) fájlok vizsgálatát.<br>Ha a meghajtón található fájlok írásvédettek, a Defender nem képes eltávolítani a bennük talált kártevőket.|
|**Aláírás-frissítési időköz**|Meghatározza, hogy a Defender milyen időközönként keressen új aláírásfájlokat.|
|**Felhővédelem engedélyezése**|Engedélyezi vagy letiltja, hogy a rendszer adatokat küldjön a Microsoft Active Protection Service számára a felügyelt eszközökön észlelt kártevőkről. Ezek az adatok a szolgáltatás további fejlesztésére szolgálnak.|
|**Minták küldésének kérése a felhasználóktól**|Azt szabályozza, hogy a rendszer automatikusan elküldje a Microsoftnak azokat a fájlokat, amelyeken további vizsgálat szükséges annak megállapításához, hogy kártékonyak-e.|
|**Vélhetően nem kívánatos alkalmazások észlelése**|Ezzel a beállítással biztosíthatja a regisztrált Windows rendszerű asztali eszközök védelmét a Windows Defender által a vélhetően nemkívánatos osztályba sorolt szoftverek futtatása ellen. Biztosíthatja a védelmet ezen alkalmazások futtatása ellen, vagy a vizsgálati üzemmóddal jelentést készíthet a vélhetően nemkívánatos alkalmazások telepítéséről.|
|**A vizsgálatok futtatásakor vagy a valós idejű védelem használatakor kizárandó fájlok és mappák**|Vegye fel a kívánt fájlokat és mappákat – például **C:\Elérési_út** vagy **%ProgramFiles%\Elérési_út\fájlnév.exe** – a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a fájlokat és mappákat.|
|**A vizsgálatok futtatásakor vagy a valós idejű védelem használatakor kizárandó fájlkiterjesztések**|Vegye fel a kívánt fájlkiterjesztéseket – például **jpg** vagy **txt** – a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja az ilyen kiterjesztésű fájlokat.|
|**A vizsgálatok futtatásakor vagy a valós idejű védelem használatakor kizárandó folyamatok**|Vegye fel a kívánt típusú folyamatokat – **.exe**, **.com** vagy **.scr** – a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a folyamatokat.| 


## &nbsp;&nbsp;&nbsp;Updates

|Beállítás neve|További információ (ha szükséges)|
|----------------|---------------|
|**Automatikus frissítések engedélyezése**|A beállítás engedélyezésével engedélyezheti az automatikus frissítéseket. Ezt követően a következő lehetőségek egyikének beállításával szabályozhatja a frissítések működését:<br />**Értesítést kérek a letöltésről**<br />**Automatikus telepítés karbantartási időpontban**<br />**Automatikus telepítés és újraindítás karbantartási időpontban**<br />**Automatikus telepítés és újraindítás ütemezett időpontban** **Megjegyzés:** Kiválasztása esetén a következő beállítások konfigurálása is lehetővé válik: **Végfelhasználói értesítések letiltása**, illetve **Adja meg az ütemezett frissítések telepítésének napját**.<br>(csak a Windows 10 asztali verzió)|
|**Előzetes kiadású szolgáltatások engedélyezése**|Lehetővé teszi a Microsoft számára, hogy előzetes verziójú beállításokat és funkciókat telepítsen a Windows 10 rendszerű eszközökre. Meghatározhatja, hogy csak a beállítások telepítését engedélyezi, vagy minden előzetes verziójú beállítás és funkció telepítését is.|

### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)





<!--HONumber=Oct16_HO1-->


