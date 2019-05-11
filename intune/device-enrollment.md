---
title: Mit jelent az eszközök regisztrálása a Microsoft Intune-ban
titleSuffix: Microsoft Intune
description: Útmutató iOS, Android és Windows rendszerű eszközök regisztrálásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 4/24/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68f5fad9d05787b6e79792d594480547ce10cf81
ms.sourcegitcommit: b0cf661145ccc6e3518db620af199786a623a0d9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64764909"
---
# <a name="what-is-device-enrollment"></a>Mi az eszközregisztrálás?
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune lehetővé teszi a dolgozók eszközeinek és alkalmazásainak, illetve a céges adatokhoz való hozzáférésük kezelését. Ezen mobileszköz-kezelés (MDM) használatához az eszközöket először regisztrálni kell az Intune szolgáltatásban. Az eszközök regisztrálásakor azok egy MDM-tanúsítványt kapnak. Ez a tanúsítvány az Intune szolgáltatással való kommunikációra szolgál.

Amint az alábbi táblázatokban látható, a dolgozók eszközeit többféleképpen is lehet regisztrálni. Az egyes módszerek az eszköz tulajdonosától (személyes vagy céges), az eszköztípustól (iOS, Windows, Android) és a felügyeleti követelményektől (alaphelyzetbe állítások, affinitás, zárolás) függ.

Alapértelmezés szerint platformtól függetlenül minden eszköz regisztrációja engedélyezett az Intune-ban. Viszont [korlátozhatja az eszközöket platform szerint](enrollment-restrictions-set.md#set-device-type-restrictions).

## <a name="ios-enrollment-methods"></a>iOS-eszközök regisztrálási módszerei

| **Módszer** |  **Alaphelyzetbe állítás szükséges** |    [**Felhasználói affinitás**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) |   **Zárolás** | **Részletek** |
|:---:|:---:|:---:|:---:|:---:|
| | A regisztráció során az eszközök összes adata törölve lesz. |  Minden eszközt egy felhasználóhoz társítja.| A felhasználók nem törölhetik az eszközök regisztrációját.  | |
|**[BYOD](#bring-your-own-device)** | Nem|   Igen |   Nem | [További információ](./apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Nem |Nem |Nem  | [További információ](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|   Igen |   Nem kötelező megadni |  Nem kötelező megadni|[További információ](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Igen |   Nem kötelező megadni |  Nem| [További információ](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Nem |    Nem  | Nem|[További információ](./apple-configurator-direct-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>macOS-eszközök regisztrálási módszerei
| **Módszer** |  **Alaphelyzetbe állítás szükséges** |  **Felhasználói affinitás** | **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Nem| Igen | Nem | [További információ](./macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Nem |Nem |Nem  | [További információ](./device-enrollment-manager-enroll.md)|
|**[DEP](#apple-device-enrollment-program)**|   Igen |   Nem kötelező megadni |  Nem kötelező megadni|[További információ](./device-enrollment-program-enroll-macos.md)|


## <a name="windows-enrollment-methods"></a>Windows-eszközök regisztrálási módszerei

| **Módszer** |  **Alaphelyzetbe állítás szükséges** |    **Felhasználói affinitás**   |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Nem |  Igen |   Nem | [További információ](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Nem |Nem |Nem  |[További információ](device-enrollment-manager-enroll.md)|
|**Automatikus regisztráció** | Nem |Igen |Nem | [További információ](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Az autopilot** |Igen |Igen |Nem | [További információ](enrollment-autopilot.md)
|**Csoportos regisztráció** |Nem |Nem |Nem | [További információ](./windows-bulk-enroll.md) |
|**Közös felügyelet** |Nem |Igen |Nem | [További információ](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)
|**GPO** |Nem |Igen |Nem | [További információ](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)


## <a name="android-enrollment-methods"></a>Android-eszközök regisztrálási módszerei

| **Személyes** | **Eszközök regisztrálási módszerei** | **Alaphelyzetbe állítás szükséges** | **Felhasználói affinitás** | **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Android-eszköz felügyelet**|**Felhasználó által kezdeményezett a vállalati portálon keresztül** | Nem | Igen | Nem | [További információ](https://docs.microsoft.com/intune-user-help/enroll-device-android-company-portal)|
|**Android Enterprise munkahelyi profil**|**Felhasználó által kezdeményezett a vállalati portálon keresztül**| Nem | Igen | Nem | [További információ](./android-work-profile-enroll.md)|


| **Vállalati** | **Eszközök regisztrálási módszerei** | **Alaphelyzetbe állítás szükséges** | **Felhasználói affinitás** | **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Android-eszköz felügyelet**|**[Készülékregisztráció-kezelő](#device-enrollment-manager) vállalati portálon keresztül kezdeményezett**| Nem | Nem | Nem |[További információ](./device-enrollment-manager-enroll.md)|
|**Android-eszköz felügyelet**|**(Előre bejelentett IMEI vagy SN) Felhasználó által kezdeményezett a vállalati portálon keresztül**| Nem | Igen | Nem | [További információ](./corporate-identifiers-add.md)|
|**Android-eszköz rendszergazdai Zebra mobilitási bővítményekkel**|**Felhasználó vagy [készülékregisztráció-kezelő](#device-enrollment-manager) vállalati portálon keresztül kezdeményezett**| Nem | Igen, ha a felhasználó által kezdeményezett, nem if [készülékregisztráció-kezelő](#device-enrollment-manager) kezdeményezett | Nem | [További információ](./android-zebra-mx-overview.md)|
|**Dedikált Android Enterprise**|**NFC, a jogkivonatot, QR-kódot, Zero Touch**| Igen | Nem | Konfigurálható csoportházirend használatával | [További információ](./android-kiosk-enroll.md)|
|**Android Enterprise teljes körűen felügyelt (előzetes verzió)**|**NFC, a jogkivonatot, QR-kódot, Zero Touch**| Igen | Igen | Konfigurálható csoportházirend használatával | [További információ](./android-dedicated-devices-fully-managed-enroll.md)|


## <a name="bring-your-own-device"></a>Saját eszközök használata (Bring Your Own Device)
A saját (BYOD-) eszközök közé tartoznak a személyes telefonok, táblagépek és számítógépek. A BYOD-eszközök regisztrálásához a felhasználók telepítik és futtatják a Céges portál alkalmazást. A program lehetővé teszi, hogy a felhasználók elérhessék a vállalati erőforrásokat, például az e-mailt.

## <a name="corporate-owned-device"></a>Céges eszköz
A [céges eszközök (COD)](corporate-identifiers-add.md) közé tartoznak a szervezet tulajdonában lévő és a dolgozóknak kiosztott telefonok, táblagépek és számítógépek. A céges eszközök (COD) regisztrációja olyan forgatókönyveket támogat, mint például az automatikus regisztráció, a megosztott eszközök vagy az előre engedélyezett regisztrációs követelmények. A céges eszközök regisztrálásának egy rendszergazdák és menedzserek által gyakran használt módja a készülékregisztráció-kezelő (DEM) alkalmazása. Az iOS-eszközök közvetlenül regisztrálhatók a Készülékregisztrációs program (DEP) Apple által biztosított eszközeivel. IMEI-számmal rendelkező eszközöket is azonosítani és céges tulajdonúként.

### <a name="device-enrollment-manager"></a>Készülékregisztráció-kezelő
Az eszközregisztráció-kezelő (DEM) egy speciális felhasználói fiók, amely több vállalati tulajdonú eszköz regisztrációjára és felügyeletére szolgál. A kezelők tudják telepíteni a Vállalati portált és regisztrálni számos, felhasználó nélküli eszközt. Az ilyen típusú eszközök például POS- vagy segédprogram-alkalmazásokhoz megfelelőek, de nem alkalmasak olyan felhasználók számára, akik hozzá szeretnének férni a levelezésükhöz vagy a vállalati erőforrásokhoz. További információ a [DEM](./device-enrollment-manager-enroll.md) módszerről. 

### <a name="apple-device-enrollment-program"></a>Apple Készülékregisztrációs program
Az Apple eszköz beléptetési Program (DEP) management lehetővé teszi házirend létrehozása és telepítése "vezeték nélkül" iOS- és macOS-eszközökre vásárolt és felügyelt eszközökre. Az eszköz regisztrálva van, amikor a felhasználók első alkalommal kapcsolja be az eszközt, és a beállítási asszisztens futtatására. Ez a módszer támogatja az iOS Supervised (Felügyelt) üzemmódját, amely lehetővé teszi konkrét funkciók beállítását az eszközön.

További információ az iOS-eszközök regisztrálásáról a DEP keretében:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](ios-enroll.md)
- [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### <a name="usb-sa"></a>USB-SA
Az Apple Configurator segítségével a rendszergazdák a beállítási asszisztens használatával USB-kapcsolaton keresztül manuálisan előkészíthetnek minden vállalat által birtokolt eszközt. A rendszergazda létrehoz egy regisztrációs profilt, és exportálja azt az Apple Configuratorba. Amikor a felhasználók megkapják az eszközeiket, választhatják a beállítási asszisztens futtatását az eszköz regisztrálásához. Ez a módszer támogatja az **iOS Supervised** (Felügyelt) üzemmódját, amely lehetővé teszi a következő funkciókat:
  - Zárolt regisztráció
  - Teljes képernyős mód és más speciális konfigurációk és korlátozások

További információk az eszközöknek az Apple Configurator és Beállítási asszisztens segítségével történő regisztrálásáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md)
- [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens használatával](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
A közvetlen regisztrációhoz a rendszergazdának a regisztrációs házirend létrehozásához és az Apple Configuratorba való exportálásához manuálisan kell regisztrálnia minden eszközt. Az USB-csatlakozású, vállalati tulajdonú eszközök regisztrálása közvetlenül történik, az összes adat törlésére nincs szükség. Az eszközök kezelése felhasználó nélküli eszközökként történik. Nincsenek zárolva, sem felügyelve, és nem támogathatják a feltételes hozzáférést, a függetlenítés észlelését, illetve a mobilalkalmazás-felügyeletet.

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md)
- [iOS-eszközök regisztrálása a Configurator és közvetlen regisztráció használatával](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.
