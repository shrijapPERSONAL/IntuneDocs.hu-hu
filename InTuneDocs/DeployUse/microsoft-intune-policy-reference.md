---
title: "A konfigurációs szabályzatok ismertetése | Microsoft Intune"
description: "Az ebben a témakörben található információk segítségével eldöntheti, hogy a Microsoft Intune melyik szabályzatát használja eszközeinek felügyeletére."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5a8d2702037b7b96b454078e991dea429143e733
ms.openlocfilehash: aa081dd17c0067082e314ac45d2a52792f66b8d6


---

# A Microsoft Intune szabályzatainak ismertetése

Az ebben a témakörben található információk segítségével eldöntheti, hogy a Microsoft Intune melyik konfigurációs szabályzatát használja eszközeinek felügyeletére.

> [!TIP]
> Részletesebb információ a szabályzatok használatáról: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).


## Konfigurációs szabályzatok Android-alapú eszközökhöz

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Egyéni konfiguráció (Android 4-es és újabb verziók, Samsung KNOX szabvány 4.0-s és újabb verziók)**|Az Open Mobile Alliance egységes erőforrás-azonosítóira (OMA-URI) vonatkozó beállítások, például Wi-Fi-beállítások megadása, amelyek segítségével szabályozhatók az eszközök funkciói. Ez akkor hasznos, ha a szükséges beállítás nem érhető el egy konfigurációs szabályzatban.<br /><br />Részletekért lásd: [Android szabályzatbeállítások a Microsoft Intune-ban](android-policy-settings-in-microsoft-intune.md).|
|**E-mail profil (a Samsung KNOX szabvány 4.0-s és újabb verziói)**|A felügyelt eszközökön létrehozhatja, telepítheti és figyelheti az Exchange Active Sync e-mail-beállításait. A felhasználók így külön beállítások elvégzése nélkül férhetnek hozzá vállalati levelezésükhöz saját eszközeiken.<br /><br />Részletekért lásd: [Vállalati levelezéshez való hozzáférés konfigurálása e-mail profilokkal a Microsoft Intune-ban](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Általános konfiguráció (Android 4-es és újabb verziók, Samsung KNOX szabvány 4.0-s és újabb verziók)**|Mobileszközök biztonsági és működési beállításainak konfigurálása.<br />A szabályozásoknak megfelelő vagy nem megfelelő alkalmazások megadása, és jelentéskészítés a használatukról.<br />Teljes képernyős üzemmód beállítása, amely csak az eszköz bizonyos szolgáltatásainak használatát engedélyezi. Beállíthatja például csak egyetlen alkalmazás használatát vagy a hangerő-szabályozó gombok letiltását.<br /><br />Részletekért lásd: [Android szabályzatbeállítások a Microsoft Intune-ban](android-policy-settings-in-microsoft-intune.md).|
|**PKCS #12 (.PFX) tanúsítványprofil (Android 4 és újabb)**|Ezzel a profillal hozhatja létre és telepítheti az eszköztanúsítvány-igénylések .PFX-beállításait.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**SCEP-tanúsítványprofil (Android 4 és újabb)**|Olyan egyszerű tanúsítványigénylési protokollt (SCEP) konfigurálhat, amely egy megbízható mobileszköz-tanúsítvánnyal együtt feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**Megbízhatótanúsítvány-profil (Android 4 és újabb)**|Olyan megbízható mobileszköz-tanúsítványt konfigurálhat, amely feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**VPN-profil (Android 4 és újabb)**|Olyan beállításokat konfigurálhat és telepíthet, amelyek biztosítják, hogy a felhasználók biztonságosan hozzáférhessenek a vállalati hálózathoz a mobileszközükről. A beállítások telepítésével lehetővé teszi, hogy a végfelhasználók egyszerűbben csatlakozhassanak a munkáikhoz.<br /><br />Részletekért lásd: [VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi profil (Android 4 és újabb)**|Konfigurálhatja és telepítheti a szervezethez tartozó felhasználók vezeték nélküli hálózati beállításait. A beállítások telepítésével lehetővé teszi, hogy a végfelhasználók egyszerűbben csatlakozhassanak a vezeték nélküli hálózathoz.<br /><br />Részletekért lásd: [Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-connections-in-microsoft-intune.md).|

## iOS-t futtató eszközökhöz készült konfigurációs szabályzatok

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Egyéni konfiguráció (iOS 7.1-es és újabb verziók)**|Olyan konfigurációs profilokat telepíthet iOS-eszközökön, amelyeket az Apple Configurator eszközzel hozott létre. Ez akkor hasznos, ha a szükséges beállítás nem érhető el egy konfigurációs szabályzatban.<br /><br />Részletekért lásd: [iOS-szabályzatbeállítások a Microsoft Intune-ban](ios-policy-settings-in-microsoft-intune.md).|
|**E-mail profil (iOS 7.1 és újabb)**|A felügyelt eszközökön létrehozhatja, telepítheti és figyelheti az Exchange Active Sync e-mail-beállításait. A felhasználók így külön beállítások elvégzése nélkül férhetnek hozzá vállalati levelezésükhöz saját eszközeiken.<br /><br />Részletekért lásd: [Vállalati levelezéshez való hozzáférés konfigurálása e-mail profilokkal a Microsoft Intune-ban](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Általános konfiguráció (iOS 7.1-es és újabb verziók)**|Mobileszközök biztonsági és működési beállításainak konfigurálása.<br />A szabályozásoknak megfelelő vagy nem megfelelő alkalmazások megadása, és jelentéskészítés a használatukról.<br />Teljes képernyős üzemmód beállítása, amely csak az eszköz bizonyos szolgáltatásainak használatát engedélyezi. Beállíthatja például csak egyetlen alkalmazás használatát vagy a hangerő-szabályozó gombok letiltását.<br /><br />Részletekért lásd: [iOS-szabályzatbeállítások a Microsoft Intune-ban](ios-policy-settings-in-microsoft-intune.md).|
|**Mobilalkalmazás-konfigurációs szabályzat (iOS 7.1 és újabb verziók)**|A mobilalkalmazás-konfigurációs házirendekkel automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy iOS-alkalmazást futtat.<br /><br />Részletes leírás: [iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs házirendek segítségével a Microsoft Intune-ban](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).|
|**Mobil létesítésiprofil-házirend (iOS 7.1-es és újabb verziók)**|Az Apple iOS-alapú üzletági mobilalkalmazásoknak része egy létesítési profil és a tanúsítvánnyal aláírt kód. Ha az alkalmazás egy iOS-eszközön fut, az iOS ellenőrzi az iOS-alkalmazás integritását, és kikényszeríti a létesítési profil által meghatározott szabályzatokat.<br><br>Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában három évig érvényes. A létesítési profil viszont egy év után lejár. A házirenddel proaktív módon, még a tanúsítvány érvényességi ideje alatt telepíthet új létesítési profilt olyan eszközökre, amelyeken lejáró alkalmazások vannak.<br><br>További részletek: [Az iOS-mobileszközös létesítésiprofil-szabályzatok segítségével megakadályozhatja, hogy az alkalmazásai lejárjanak](ios-mobile-app-provisioning-profiles.md).|
|**PKCS #12 (.PFX) tanúsítványprofil (iOS 7.1 és újabb verziók)**|Ezzel a profillal hozhatja létre és telepítheti az eszköztanúsítvány-igénylések .PFX-beállításait.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**SCEP-tanúsítványprofil (iOS 7.1 és újabb)**|Olyan egyszerű tanúsítványigénylési protokollt (SCEP) konfigurálhat, amely egy megbízható mobileszköz-tanúsítvánnyal együtt feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi- és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**Megbízható tanúsítványprofil (iOS 7.1 és újabb)**|Olyan megbízható mobileszköz-tanúsítványt konfigurálhat, amely feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi- és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**VPN-profil (iOS 7.1 és újabb)**|Olyan beállításokat konfigurálhat és telepíthet, amelyek biztosítják, hogy a felhasználók biztonságosan hozzáférhessenek a vállalati hálózathoz a mobileszközükről. A beállítások telepítésével lehetővé teszi, hogy a végfelhasználók egyszerűbben csatlakozhassanak a munkáikhoz.<br /><br />Részletekért lásd: [VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi profil (iOS 7.1 és újabb)**|Konfigurálhatja és telepítheti a szervezethez tartozó felhasználók vezeték nélküli hálózati beállításait. A beállítások telepítésével lehetővé teszi, hogy a végfelhasználók egyszerűbben csatlakozhassanak a vezeték nélküli hálózathoz.<br /><br />Részletekért lásd: [Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-connections-in-microsoft-intune.md).|


## Mac OS X-t futtató eszközökhöz készült konfigurációs szabályzatok

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Egyéni konfiguráció (Mac OS X 10.9 és újabb verziók)**|Az Apple Configurator eszközzel létrehozott konfigurációs profilokat telepíthet Mac számítógépeken. Ez akkor hasznos, ha a szükséges beállítás nem érhető el egy konfigurációs szabályzatban.<br /><br />Részletekért lásd: [A Mac OS X szabályzatbeállításai a Microsoft Intune-ban](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Általános konfiguráció (Mac OS X 10.9 és újabb verziók)**|Mobileszközök biztonsági és működési beállításainak konfigurálása.<br />A szabályozásoknak megfelelő vagy nem megfelelő alkalmazások megadása, és jelentéskészítés a használatukról.<br /><br />Részletekért lásd: [A Mac OS X szabályzatbeállításai a Microsoft Intune-ban](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**SCEP-tanúsítványprofil (Mac OS X 10.9 és újabb verziók)**|Olyan egyszerű tanúsítványigénylési protokollt (SCEP) konfigurálhat, amely egy megbízható mobileszköz-tanúsítvánnyal együtt feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi- és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**Megbízhatótanúsítvány-profil (Mac OS X 10.9 és újabb verziók)**|Olyan megbízható mobileszköz-tanúsítványt konfigurálhat, amely feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi- és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**VPN-profil (Mac OS X 10.9 és újabb verziók)**|Olyan beállításokat konfigurálhat és telepíthet, amelyek biztosítják, hogy a felhasználók biztonságosan hozzáférhessenek a vállalati hálózathoz a mobileszközükről. A beállítások telepítésével lehetővé teszi, hogy a végfelhasználók egyszerűbben csatlakozhassanak a munkáikhoz.<br /><br />Részletekért lásd: [VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi-profil (Mac OS X 10.9 és újabb verziók)**|Konfigurálhatja és telepítheti a szervezethez tartozó felhasználók vezeték nélküli hálózati beállításait. A beállítások telepítésével lehetővé teszi, hogy a végfelhasználók egyszerűbben csatlakozhassanak a vezeték nélküli hálózathoz.<br /><br />Részletekért lásd: [Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-connections-in-microsoft-intune.md).|

## Windows-t futtató eszközökhöz készült konfigurációs szabályzatok
Csak a Windows Phone-ra és a regisztrált Windows-eszközökre vonatkozik.

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Egyéni konfiguráció (Windows 10 és újabb asztali és mobil rendszerek)**|Az eszközfunkciók szabályzásához használható OMA-URI beállítások megadása. Ez akkor hasznos, ha a szükséges beállítás nem érhető el egy konfigurációs szabályzatban.<br />    Részletekért lásd: [A Windows 10 szabályzatbeállításai a Microsoft Intune-ban](windows-10-policy-settings-in-microsoft-intune.md).|
|**Egyéni konfiguráció (Windows Phone 8.1 és újabb rendszerek)**|Az eszközfunkciók szabályzásához használható OMA-URI beállítások megadása. Ez akkor hasznos, ha a szükséges beállítás nem érhető el egy konfigurációs szabályzatban.<br /><br />Részletekért lásd: [A Windows Phone 8.1 beállításai a Microsoft Intune-ban](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Kiadásfrissítési házirend (Windows 10-es és újabb asztali verziók)**<br><br>**Kiadásfrissítési házirend (Windows 10 Holographic és újabb verziók)**|Konfigurálhatja és telepítheti a licenc- vagy termékkulcsadatokat tartalmazó szabályzatokat, amelyekkel újabb verzióra frissítheti a Windows 10-eszközöket.<br><br>Részletekért lásd: [A kiadásfrissítési házirend beállításai a Microsoft Intune-ban](edition-upgrade-policy-settings-in-microsoft-intune.md).|  
|**E-mail profil (Windows Phone 8 és újabb)**<br /><br />**E-mail profil (Windows 10 és újabb asztali és mobil rendszerek)**|A felügyelt eszközökön létrehozhatja, telepítheti és figyelheti az Exchange Active Sync e-mail-beállításait. A felhasználók így külön beállítások elvégzése nélkül férhetnek hozzá vállalati levelezésükhöz saját eszközeiken.<br /><br />Részletekért lásd: [Vállalati levelezéshez való hozzáférés konfigurálása e-mail profilokkal a Microsoft Intune-ban](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Általános konfiguráció (Windows 10 és újabb asztali és mobil rendszerek)**|Regisztrált Windows 10-alapú asztali és mobileszközök biztonsági és működési beállításainak konfigurálása.<br /><br />Részletekért lásd: [A Windows 10 szabályzatbeállításai a Microsoft Intune-ban](windows-10-policy-settings-in-microsoft-intune.md).|
|**Általános konfiguráció (Windows 10 és újabb rendszerek)**|Eszközvédelmi és funkcionális beállításokat konfigurálhat a regisztrált Windows 10 Team rendszerű eszközökhöz (például Surface Hub eszközhöz).<br /><br />Részletekért lásd: [A Windows Team konfigurációs házirendjének beállításai a Microsoft Intune-ban](windows-team-configuration-policy-settings-in-microsoft-intune.md).|
|**Általános konfiguráció (Windows 8.1 és újabb)**|Regisztrált Windows-alapú mobileszközök biztonsági és működési beállításainak konfigurálása.<br /><br />Részletekért lásd: [A Windows szabályzatbeállításai a Microsoft Intune-ban](windows-configuration-policy-settings-in-microsoft-intune.md).|
|**Általános konfiguráció (Windows Phone 8.1 és újabb)**|Mobileszközök biztonsági és működési beállításainak konfigurálása.<br />Meghatározhatja azokat az alkalmazásokat, amelyek használata engedélyezett vagy tiltott a felhasználók számára, és megakadályozhatja a nem engedélyezett alkalmazások telepítését vagy használatát.<br /><br />Részletekért lásd: [A Windows Phone 8.1 beállításai a Microsoft Intune-ban](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**PKCS #12 (.PFX) tanúsítványprofil (Windows 10 és újabb asztali és mobil rendszerek)**|Ezzel a profillal hozhatja létre és telepítheti az eszköztanúsítvány-igénylések .PFX-beállításait.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**SCEP-tanúsítványprofil (Windows 8.1 és újabb)**<br /><br />**SCEP-tanúsítványprofil (Windows Phone 8.1 és újabb)**|Olyan egyszerű tanúsítványigénylési protokollt (SCEP) konfigurálhat, amely egy megbízható mobileszköz-tanúsítvánnyal együtt feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi- és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**Megbízható tanúsítványprofil (Windows 8.1 és újabb)**<br /><br />**Megbízhatótanúsítvány-profil (Windows Phone 8.1 és újabb)**|Olyan megbízható mobileszköz-tanúsítványt konfigurálhat, amely feljogosíthatja a mobileszközöket arra, hogy hozzáférjenek például Wi-Fi és VPN-profilokkal konfigurált hálózati erőforrásokhoz.<br /><br />Részletekért lásd: [Az erőforrások biztonságos elérése a Microsoft Intune tanúsítványprofiljai segítségével](secure-resource-access-with-certificate-profiles.md).|
|**VPN-profil (Windows 10 és újabb asztali és mobil verzió)**<br /><br />**VPN-profil (Windows 8.1 és újabb verziók)**<br /><br />**VPN-profil (Windows Phone 8.1 és újabb)**|Olyan beállításokat konfigurálhat és telepíthet, amelyek biztosítják, hogy a felhasználók biztonságosan hozzáférhessenek a vállalati hálózathoz a mobileszközükről. A beállítások telepítésével lehetővé teszi, hogy a végfelhasználók egyszerűbben csatlakozhassanak a munkáikhoz.<br /><br />Részletekért lásd: [VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi importálás**|Olyan Windows Wi-Fi beállításokat importálhat és telepíthet, amelyeket korábban egy fájlba exportált.<br /><br />Részletekért lásd: [Wi-Fi-kapcsolatok a Microsoft Intune-ban](wi-fi-connections-in-microsoft-intune.md).|
|**Windows Információvédelem**<br>(korábbi nevén vállalati adatvédelem)|Ahogy a vállalaton belül egyre nő az alkalmazottak tulajdonában álló eszközök száma, úgy nő az adatok véletlen kiszivárgásának kockázata is az olyan alkalmazásokon és szolgáltatásokon keresztül, mint az e-mail, a közösségi média és a nyilvános felhő, amelyek fölött a vállalatnak nincs irányítási lehetősége. Olyan esetekről van szó, mint például amikor egy alkalmazott egy személyes e-mail-fiókból küldi el a legújabb tervrajzokat, termékadatokat másol és illeszt be egy tweetbe, vagy nyilvános felhőben található tárhelyre ment egy aktuális értékesítési jelentést.<br><br>A Windows Információvédelem úgy segít védekezni az ezekhez hasonló esetleges adatszivárgások ellen, hogy mindeközben más módon nem avatkozik bele az alkalmazott munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által munkába hozott személyes eszközökön véletlenül kiszivárogjanak, ehhez pedig nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.<br><br>Ez az Intune-szabályzat látja el a Windows Information Protection által védett alkalmazások, a vállalati hálózati helyek, a védelmi szintek és a titkosítási beállítások kezelését.<br><br>További információk: [Vállalati adatok védelme a Windows információvédelemmel](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-edp).|


## Szoftverszabályzatok

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Felügyelt böngésző házirendje (Android 4 és újabb)**<br /><br />**Managed Browser-szabályzat (iOS 7.1 és újabb verziók)**|Meghatározhatja azokat a webhelyeket, amelyeket a felhasználók elérhetnek vagy nem érhetnek el a felügyelt böngészőalkalmazás használatával.<br /><br />Részletekért lásd: [Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](manage-internet-access-using-managed-browser-policies.md).|
|**Mobilalkalmazás-kezelési házirend (Android 4 és újabb)**<br /><br />**Mobilalkalmazás-felügyeleti szabályzat (iOS 7.1 és újabb verziók)**|Módosíthatja a telepített alkalmazások funkcióit, hogy azok összhangban legyenek a vállalat megfelelőségi és biztonsági házirendjeivel. Korlátozhatja például a kivágási, másolási és beillesztési műveleteket egy alkalmazáson belül, vagy beállíthat úgy egy alkalmazást, hogy az minden webes hivatkozást a felügyelt böngészőben nyisson meg.<br /><br />További részletekért lásd: [Adatok védelme mobilalkalmazás-kezelési házirendekkel a Microsoft Intune segítségével](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).|

## Mobileszközök általános beállításai

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Exchange ActiveSync-házirend**|Az Exchange ActiveSync által kezelt mobileszközök biztonsági és funkcionális beállításainak konfigurálása.<br /><br />Részletekért lásd: [Exchange ActiveSync házirend-beállítások a Microsoft Intune-ban](exchange-activesync-policy-settings-in-microsoft-intune.md).|
|**Mobileszközök biztonsági házirendje**|<ul><li>Többek között a következő mobileszköz-beállítások konfigurálása (platformfüggetlen):<br /><br /><ul><li>Biztonság</li><li>Titkosítás</li><li>Rendszer</li><li>E-mail</li><li>Alkalmazások</li></ul></li></ul>
> [!IMPORTANT]
A Microsoft Intune már külön **konfigurációs szabályzatokat** tartalmaz minden eszközplatformhoz, és ezek a szabályzatok a legfrissebb használható beállításokat tartalmazzák. Továbbra is használhatja a mobileszközök biztonsági házirendjét, és minden meglévő telepítés továbbra is működni fog, de meg kell terveznie az új konfigurációs házirendekre való mielőbbi áttérést.<br />Részletekért lásd: [Mobileszközök biztonsági házirendjének beállításai a Microsoft Intune-ban](mobile-device-security-policy-settings-in-microsoft-intune.md).|

## Feltételes hozzáférés és megfelelőségi házirendek

### Feltételes hozzáférés

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Exchange Online-házirend**<br /><br />**Helyszíni Exchange-házirend**|A Microsoft Exchange e-mail-elérésének kezelése olyan eszközökön, amelyeket nem az Intune felügyel, vagy amelyek nem felelnek meg a létrehozott megfelelőségi szabályzatnak.<br /><br />Részletekért lásd: [Az Exchange Online-hoz és az új dedikált Exchange Online-hoz való e-mail hozzáférés korlátozása a Microsoft Intune-nal](restrict-access-to-exchange-online-with-microsoft-intune.md).|
|**SharePoint Online-házirend**|A SharePoint Online hozzáférésének kezelése olyan eszközökön, amelyeket nem az Intune felügyel, vagy amelyek nem felelnek meg a létrehozott megfelelőségi szabályzatnak.<br /><br />Részletekért lásd: [A SharePoint Online-hoz való hozzáférés korlátozása a Microsoft Intune-nal](restrict-access-to-sharepoint-online-with-microsoft-intune.md).|
|**Skype Vállalati verzió**|A Skype Vállalati verzió elérésének kezelése olyan eszközökön, amelyeket nem az Intune felügyel, vagy amelyek nem felelnek meg a létrehozott megfelelőségi szabályzatnak.<br /><br />Részletekért lásd: [A Skype Vállalati verzió elérésének korlátozása a Microsoft Intune-nal](restrict-access-to-skype-for-business-online-with-microsoft-intune.md).|
> [!NOTE]
> Nem kell feltételes hozzáférési házirendeket telepítenie a felhasználók és eszközök számára. Elegendő a kívánt szabályzatot konfigurálnia, amely a szabályzatban meghatározott összes csoportra vonatkozik.

### Megfelelőségi házirendek

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**Megfelelőségi házirendek**|Lehetővé teszi egy eszköz megfelelőségi szintjének meghatározását, és jelentést készít a nem megfelelő eszközökről. Ezek a házirendek a feltételeken alapuló hozzáféréssel mérik fel azokat az eszközöket, amelyek esetében nem engedélyezhető a szolgáltatások hozzáférése.<br /><br />A részleteket lásd: [Eszközmegfelelőségi szabályzatok a Microsoft Intune-ban](introduction-to-device-compliance-policies-in-microsoft-intune.md).|

## Windows-számítógépek felügyelete

|Házirend neve|Alkalmazási helyzet|
|---------------|------------------------|
|**A Microsoft Intune-ügynök beállításai**|Konfigurálja az Intune számítógépes ügyfelet a számítógépen, a következő beállításokat is beleértve:<br /><br />-   Endpoint Protection<br />-   Szoftverfrissítések<br />-   Házirend-ellenőrzés ütemezése<br /><br />Ez a házirendtípus csak eszközcsoportok számára telepíthető.<br /><br />Az Intune-ügyfelek a **Frissítések és alkalmazások keresésének gyakorisága** beállítás alapján töltik le az új és frissített szabályzatokat (a beállítás alapértelmezett értéke: 8 óra). Bármikor kényszerítheti azonban egy házirend frissítését a számítógépeken.<br /><br />A részleteket lásd: [Windows rendszerű számítógépek naprakészen tartása szoftverfrissítésekkel a Microsoft Intune-ban](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**A Microsoft Intune Center beállításai**|Konfigurálja a Microsoft Intune-ban megjelenő részleteket a felügyelt számítógépeken.<br /><br />Ez a házirendtípus csak eszközcsoportok számára telepíthető.<br /><br />Részletekért lásd: [A Windows rendszerű számítógépek a Microsoft Intune számítógépügyféllel való felügyeletének általános feladatai](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).|
|**A Windows tűzfal beállításai**|A Windows tűzfal beállításait és kivételeit konfigurálja a számítógépek általános hálózati kommunikációja számára, beleértve a következőket:<br /><br />-   BranchCache<br />-   Távsegítség<br />-   Médiafájlok megosztása<br /><br />Ez a házirendtípus csak eszközcsoportok számára telepíthető.<br /><br />A részleteket lásd: [Windows rendszerű számítógépek biztonságossá tétele a Microsoft Intune-hoz készült Endpoint Protection szolgáltatással](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).|

### További információ

[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO2-->


