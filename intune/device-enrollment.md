---
title: "Mit jelent az eszközök regisztrálása a Microsoft Intune-ban"
titlesuffix: Azure portal
description: "Útmutató iOS, Android és Windows rendszerű eszközök regisztrálásához."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a94703ecc1d7fd464f565855bb9b8dd9ee3c3bfb
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-device-enrollment"></a>Mi az eszközregisztrálás?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune lehetővé teszi a dolgozók eszközeinek és alkalmazásainak, illetve a céges adatokhoz való hozzáférésük kezelését. Ezen mobileszköz-kezelés (MDM) használatához az eszközöket először regisztrálni kell az Intune szolgáltatásban. Az eszközök regisztrálásakor azok egy MDM-tanúsítványt kapnak. Ez a tanúsítvány az Intune szolgáltatással való kommunikációra szolgál.

Amint az alábbi táblázatokban látható, a dolgozók eszközeit többféleképpen is lehet regisztrálni. Az egyes módszerek az eszköz tulajdonosától (személyes vagy céges), az eszköztípustól (iOS, Windows, Android) és a felügyeleti követelményektől (alaphelyzetbe állítások, affinitás, zárolás) függ.

## <a name="ios-enrollment-methods"></a>iOS-eszközök regisztrálási módszerei

| **Módszer** |  **Alaphelyzetbe állítás szükséges** |    [**Felhasználói affinitás**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) |   **Zárolás** | **Részletek** |
|:---:|:---:|:---:|:---:|:---:|
| | A rendszer a regisztráció során visszaállítja az eszközök gyári beállításait. |  Minden eszközt egy felhasználóhoz társítja.| A felhasználók nem törölhetik az eszközök regisztrációját.  | |
|**[BYOD](#bring-your-own-device)** | Nem|   Igen |   Nem | [További információ](./apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Nem |Nem |Nem  | [További információ](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|   Igen |   Nem kötelező megadni |  Nem kötelező megadni|[További információ](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Igen |   Nem kötelező megadni |  Nem| [További információ](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Nem |    Nem  | Nem|[További információ](./apple-configurator-direct-enroll-ios.md)|

## <a name="windows-enrollment-methods"></a>Windows-eszközök regisztrálási módszerei

| **Módszer** |  **Alaphelyzetbe állítás szükséges** |    **Felhasználói affinitás**   |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Nem |  Igen |   Nem | [További információ](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Nem |Nem |Nem  |[További információ](device-enrollment-manager-enroll.md)|
|**Automatikus regisztráció** | Nem |Igen |Nem | [További információ](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Csoportos regisztráció** |Nem |Nem |Nem | [További információ](./windows-bulk-enroll.md) |

## <a name="android-enrollment-methods"></a>Android-eszközök regisztrálási módszerei

| **Módszer** |  **Alaphelyzetbe állítás szükséges** |    **Felhasználói affinitás**   |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Nem|   Igen |   Nem | [További információ](./android-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Nem |Nem |Nem  |[További információ](./device-enrollment-manager-enroll.md)|
|**Android for Work**| Nem | Igen | Nem| [További információ](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="bring-your-own-device"></a>Saját eszközök használata (Bring Your Own Device)
A saját (BYOD-) eszközök közé tartoznak a személyes telefonok, táblagépek és számítógépek. A BYOD-eszközök regisztrálásához a felhasználók telepítik és futtatják a Céges portál alkalmazást. A program lehetővé teszi, hogy a felhasználók elérhessék a vállalati erőforrásokat, például az e-mailt.

## <a name="corporate-owned-device"></a>Céges eszköz
A céges eszközök (COD) közé tartoznak a szervezet tulajdonában lévő és a dolgozóknak kiosztott telefonok, táblagépek és számítógépek. A céges eszközök (COD) regisztrációja olyan forgatókönyveket támogat, mint például az automatikus regisztráció, a megosztott eszközök vagy az előre engedélyezett regisztrációs követelmények. A céges eszközök regisztrálásának egy rendszergazdák és menedzserek által gyakran használt módja a készülékregisztráció-kezelő (DEM) alkalmazása. Az iOS-eszközök közvetlenül regisztrálhatók a Készülékregisztrációs program (DEP) Apple által biztosított eszközeivel. Az IMEI-számmal rendelkező eszközöket is lehet azonosítani és meg lehet jelölni céges tulajdonúként.

### <a name="device-enrollment-manager"></a>Készülékregisztráció-kezelő
Az eszközregisztráció-kezelő (DEM) egy speciális felhasználói fiók, amely több vállalati tulajdonú eszköz regisztrációjára és felügyeletére szolgál. A kezelők tudják telepíteni a Vállalati portált és regisztrálni számos, felhasználó nélküli eszközt. További információ a [DEM](./device-enrollment-manager-enroll.md) módszerről.

### <a name="apple-device-enrollment-program"></a>Apple Készülékregisztrációs program
Az Apple készülékregisztrációs program (DEP) lehetővé teszi szabályzatok létrehozását és vezeték nélküli központi telepítését a DEP keretében vásárolt és felügyelt eszközökre. Az eszköz regisztrálása akkor történik, amikor a felhasználók első alkalommal bekapcsolják az eszközt, és futtatják rajta az iOS beállítási asszisztens alkalmazást. Ez a módszer támogatja az iOS Supervised (Felügyelt) üzemmódját, amely lehetővé teszi konkrét funkciók beállítását az eszközön.

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
A közvetlen regisztrációhoz a rendszergazdának a regisztrációs házirend létrehozásához és az Apple Configuratorba való exportálásához manuálisan kell regisztrálnia minden eszközt. Az USB-csatlakozású, vállalati tulajdonú eszközök regisztrálása közvetlenül történik, a gyári beállítások visszaállítása nem szükséges. Az eszközök kezelése felhasználó nélküli eszközökként történik. Nincsenek zárolva, sem felügyelve, és nem támogathatják a feltételes hozzáférést, a függetlenítés észlelését, illetve a mobilalkalmazás-felügyeletet.

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md)
- [iOS-eszközök regisztrálása a Configurator és közvetlen regisztráció használatával](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Mobileszköz-kezelés az Exchange ActiveSync és az Intune használatával
Azok a mobileszközök, amelyek nincsenek regisztrálva, de kapcsolódnak az Exchange ActiveSync (EAS) rendszerhez, EAS MDM-szabályzat segítségével kezelhetők az Intune-ban. Az Intune helyszíni vagy felhőalapú Exchange Connector összekötő segítségével kommunikál az EAS-szel. Hamarosan további információ válik elérhetővé.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.
