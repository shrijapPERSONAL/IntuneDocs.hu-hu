---
title: "Mit jelent az eszközregisztráció a Microsoft Intune-ban? | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató iOS-, Android- és Windows-eszközök regisztrálásához"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/26/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 10cf9980468eff912557747c31994747c17a3ab4
ms.openlocfilehash: 01bf32ef874385019ea4b0fb0ce278554459287d


---

# <a name="what-is-device-enrollment"></a>Mi az eszközregisztrálás?
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ez a témakör az eszközregisztrálást írja le, és felsorolja azokat a különféle módszereket, amelyekkel a mobileszközök regisztrálhatók az Intune-nal való felügyeletre.

Az eszközök, köztük a Windows rendszerű számítógépek Intune-ban való regisztrálásának az a célja, hogy kezelhetők legyenek. Ezt a funkciót mobileszköz-kezelésnek (MDM) nevezzük az Intune dokumentációjában. A mobileszközként (nem számítógépként) regisztrált eszközök részére a rendszer MDM-tanúsítvány állít ki. Ezt az eszközök az Intune szolgáltatással való kommunikációban használják. 

Az eszköz regisztrálásának módja függ az eszköz típusától, tulajdonosától és az elvárt felügyeleti szinttől. A saját eszközök használatával (BYOD) történő regisztráció lehetővé teszi a felhasználóknak saját, személyes telefonjaik, táblagépeik vagy számítógépeik regisztrálását. Vállalat által birtokolt eszközök (COD) használatával történő regisztráció lehetővé tesz olyan felügyeleti lehetőségeket, mint például az automatikus regisztráció, a megosztott eszközök vagy az előre engedélyezett regisztrációs követelmények.

Ha az Exchange ActiveSyncet használja helyben vagy a felhőben, akkor regisztrálás nélkül is engedélyezheti az egyszerű Intune-felügyeletet (hamarosan további információ válik elérhetővé). A Windows rendszerű számítógépek is kezelhetők mobileszközként. Ez az ajánlott módszer, az alábbiakban leírtak szerint. Az [Intune ügyfélszoftverrel](https://docs.microsoft.com/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) számítógépként is kezelhetők.


## <a name="overview-of-device-enrollment-methods"></a>Az eszközök regisztrálási módszereinek áttekintése

Az alábbi táblázat bemutatja az Intune regisztrációs módszereit, és az egyes módszerekhez kapcsolódó lehetőségeket és követelményeket. A lehetőségeket és a követelményeket alább ismertetjük. A táblázatban az alábbi fogalmak szerepelnek:

- **Törlés** – Azt jelzi, hogy törölni kell-e mindent az eszközről ahhoz, hogy a felhasználók regisztrálni tudják. A „törlés” itt az eszköz gyári alaphelyzetének visszaállítását, vagyis az összes adat törlését jelenti. További információ: [Teljes vagy szelektív törlés használata az eszközökön](/intune-azure/manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune).
- **Affinitás** - Az eszközök felhasználókkal való társítása. Erre a mobilalkalmazás-kezeléshez (MAM) és a vállalati adatokhoz való feltételes hozzáféréshez van szükség. További információk: [Felhasználói affinitás](enroll-ios-devices-using-device-enrollment-program.md).
- **Zárolás** – Jelzi, hogy a rendszer megakadályozza a felhasználókat abban, hogy töröljék eszközeik regisztrációját, és ezzel kivonják azokat a felügyelet alól. A felhasználók a Céges portál alkalmazás használatával bármelyik platformon törölhetik eszközeik regisztrációját. A natív operációs rendszer menüit nem használhatják a regisztráció törlésére.


**iOS-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |   Nem | Hamarosan további információ válik elérhetővé|
|**[DEM](#dem)**|   Nem |Nem |Nem  | [További információ](enroll-ios-devices-using-device-enrollment-program.md)|
|**[DEP](#dep)**|   Igen |   Nem kötelező megadni |  Nem kötelező megadni|[További információ](enroll-ios-devices-using-device-enrollment-program.md)|
|**[USB-SA](#usb-sa)**| Igen |   Nem kötelező megadni |  Nem| [További információ](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)|
|**[USB-Direct](#usb-direct)**| Nem |    Nem  | Nem|[További információ](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)|



**Windows-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Igen|   Igen |   Nem | Hamarosan további információ válik elérhetővé|
|**[DEM](#dem)**|   Nem |Nem |Nem  |[További információ](enroll-devices-using-device-enrollment-manager.md)|

**Android-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |   Nem | Hamarosan további információ válik elérhetővé|
|**[DEM](#dem)**|   Nem |Nem |Nem  |[További információ](enroll-ios-devices-using-device-enrollment-program.md)|


## <a name="byod"></a>BYOD
A saját eszközeiket használó („BYOD”) felhasználók telepítik a Vállalati portál alkalmazást, és ők regisztrálják az eszközt. Ez lehetővé teszi a felhasználók számára a vállalati hálózathoz való kapcsolódást, így csatlakozhatnak a tartományhoz vagy az Azure Active Directoryhoz. A legtöbb platformon és COD-forgatókönyv esetében engedélyeznie kell a BYOD-regisztrálást.

## <a name="corporate-owned-devices"></a>Vállalati tulajdonú eszközök
A vállalati tulajdonú eszközök (COD) az Azure Portal segítségével kezelhetők. Az iOS-eszközök az Apple által biztosított megoldások segítségével közvetlenül is regisztrálhatók. A rendszergazdák vagy menedzserek bármilyen típusú eszközt regisztrálhatnak az eszközregisztráció-kezelő segítségével. Az IMEI-számmal rendelkező eszközöket azonosítani lehet, és meg lehet jelölni vállalati tulajdonúként, ami lehetőséget nyújt a vállalati tulajdonú eszközök kezelésére.

### <a name="dem"></a>DEM
A készülékregisztráció-kezelő egy speciális felhasználói fiók, amely több vállalati tulajdonú eszköz regisztrációjára és felügyeletére szolgál. A kezelők tudják telepíteni a Vállalati portált és regisztrálni számos, felhasználó nélküli eszközt. További információ a [DEM](enroll-devices-using-device-enrollment-manager.md) módszerről. ([Vissza a táblázathoz](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Az Apple készülékregisztrációs program (DEP) lehetővé teszi szabályzatok létrehozását és vezeték nélküli központi telepítését a DEP keretében vásárolt és felügyelt eszközökre. Az eszköz regisztrálása akkor történik, amikor a felhasználók első alkalommal bekapcsolják az eszközt, és futtatják rajta az iOS beállítási asszisztens alkalmazást. Ez a módszer támogatja az **iOS Supervised** (Felügyelt) üzemmódot, amely lehetővé teszi a következő funkciókat:

  - Zárolt regisztráció
  - Teljes képernyős mód és más speciális konfigurációk és korlátozások

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](choose-ios-enrollment-method.md)
- [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](enroll-ios-devices-using-device-enrollment-program.md). 
- [Vissza a fenti táblázathoz](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
Az Apple Configurator segítségével a rendszergazdák a beállítási asszisztens használatával USB-kapcsolaton keresztül manuálisan előkészíthetnek minden vállalat által birtokolt eszközt. A rendszergazda létrehoz egy regisztrációs profilt, és exportálja azt az Apple Configuratorba. Amikor a felhasználók megkapják az eszközeiket, választhatják a beállítási asszisztens futtatását az eszköz regisztrálásához. Ez a módszer támogatja az **iOS Supervised** (Felügyelt) üzemmódot, amely lehetővé teszi a következő funkciókat:
  - Zárolt regisztráció
  - Teljes képernyős mód és más speciális konfigurációk és korlátozások

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](choose-ios-enrollment-method.md)
- [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens használatával](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). 

### <a name="usb-direct"></a>USB-Direct
A közvetlen regisztrációhoz a rendszergazdának a regisztrációs házirend létrehozásához és az Apple Configuratorba való exportálásához manuálisan kell regisztrálnia minden eszközt. Az USB-csatlakozású, vállalati tulajdonú eszközök regisztrálása közvetlenül történik, a gyári beállítások visszaállítása nem szükséges. Az eszközök kezelése felhasználó nélküli eszközökként történik. Nincsenek zárolva, sem felügyelve, és nem támogathatják a feltételes hozzáférést, a függetlenítés észlelését, illetve a mobilalkalmazás-felügyeletet. 

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](choose-ios-enrollment-method.md)
- [iOS-eszközök regisztrálása a Configurator és közvetlen regisztráció használatával](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Mobileszköz-kezelés az Exchange ActiveSync és az Intune használatával
Azok a mobileszközök, amelyek nincsenek regisztrálva, de kapcsolódnak az Exchange ActiveSync (EAS) rendszerhez, EAS MDM-szabályzat segítségével kezelhetők az Intune-ban. Az Intune helyszíni vagy felhőalapú Exchange Connector összekötő segítségével kommunikál az EAS-szel. Hamarosan további információ válik elérhetővé.


## <a name="windows-pc-management-with-intune"></a>Windows-számítógépek kezelése az Intune-nal  
Az Intune ügyfélszoftvere segítségével Windows-számítógépeket is kezelhet a Microsoft Intune-nal. Az Intune ügyfél által felügyelt Windows-számítógépek:

 - Képesek szoftver- és hardverleltár jelentésére
 - Képesek asztali alkalmazások telepítésére (például .exe és .msi kiterjesztésű fájlok segítségével)
 - Tűzfal beállításainak felügyeletéhez

Az Intune ügyfélszoftverével felügyelt számítógépeken csak szelektív törlést lehet végezni, teljes törlést nem. Az Intune ügyfélszoftverével felügyelt számítógépeken az Intune számos felügyeleti funkciója (például a feltételes hozzáférés, a VPN- és Wi-Fi-beállítások meghatározása vagy a tanúsítványok és e-mail-konfigurációk telepítése) sem használható. Hamarosan további információ válik elérhetővé.

## <a name="supported-device-platforms-and-browsers"></a>Támogatott eszközplatformok és böngészők

Lásd: [Az Intune által támogatott eszközök és böngészők](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek (nem számítógépnek) törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.



<!--HONumber=Feb17_HO1-->

