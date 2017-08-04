---
title: "Eszközök regisztrálása"
description: "A mobileszköz-kezelési (MDM) funkció a regisztráció segítségével vonja felügyelet alá az eszközöket, és teszi lehetővé az erőforrásokhoz való hozzáférést."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e08a228c19e934e92ed2db1de407859e20559f7
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="enroll-devices-for-management-in-intune"></a>Eszközök regisztrálása felügyeletre a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Különböző eszközöket, így Windows rendszerű számítógépeket is regisztrálhat, hogy engedélyezze a mobileszköz-kezelést (MDM) a Microsoft Intune-nal. Ez a témakör ismerteti az eszközök Intune-felügyeletbe való regisztrálásának különböző módszereit. Az eszközök regisztrálásának módja az eszköz típusától, a tulajdonostól, valamint a felügyeleti szinttől függ. A saját eszközök használatával (BYOD) történő regisztráció lehetővé teszi a felhasználóknak saját, személyes telefonjaik, táblagépeik vagy számítógépeik regisztrálását. Vállalat által birtokolt eszközök (COD) használatával történő regisztráció lehetővé tesz olyan felügyeleti lehetőségeket, mint például az automatikus regisztráció, a megosztott eszközök vagy az előre engedélyezett regisztrációs követelmények.

Ha helyi vagy felhőalapú [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) programot használ, akkor regisztrálás nélkül is engedélyezhet egyszerű Intune-felügyeletet. A Windows rendszerű számítógépek az [Intune-ügyfélszoftver](#windows-pc-management-with-intune) segítségével is felügyelhetők.

Alapértelmezés szerint platformtól függetlenül minden eszköz regisztrációja engedélyezett az Intune-ban. Az eszközök regisztrációjának letiltásához jelentkezzen be a [Microsoft Intune felügyeleti portálra](https://manage.microsoft.com) a rendszergazdai hitelesítő adataival. Válassza a **Felügyelet** > **Mobileszköz-kezelés** > **Regisztráció szabályai** elemet, és törölje a letiltandó platformokhoz tartozó megfelelő jelölőnégyzeteket.

## <a name="overview-of-device-enrollment-methods"></a>Az eszközök regisztrálási módszereinek áttekintése

Az alábbi táblázat bemutatja az Intune regisztrációs módszereit, és az egyes módszerekhez kapcsolódó lehetőségeket és követelményeket. A lehetőségeket és a követelményeket alább ismertetjük.

- **Törlés** – Azt jelzi, hogy törölni kell-e mindent az eszközről ahhoz, hogy a felhasználók regisztrálni tudják. A „törlés” itt az eszköz gyári alaphelyzetének visszaállítását, vagyis az összes adat törlését jelenti. További információk: [Eszközök kivonása](retire-devices-from-microsoft-intune-management.md).
- **Affinitás** - Az eszközök felhasználókkal való társítása. Erre a mobilalkalmazás-kezeléshez (MAM) és a vállalati adatokhoz való feltételes hozzáféréshez van szükség. További információk: [Felhasználói affinitás](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices).
- **Zárolás** – Azt jelzi, hogy a rendszer megakadályozza a felhasználókat abban, hogy töröljék eszközeik regisztrációját az operációs rendszer natív menüinek használatával. A felhasználók a Céges portál alkalmazás használatával bármelyik platformon törölhetik eszközeik regisztrációját.

**iOS-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |   Nem | [További információ](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Nem |Nem |Nem  | [További információ](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Igen |   Nem kötelező megadni |  Nem kötelező megadni|[További információ](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Igen |   Nem kötelező megadni |  Nem| [További információ](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Nem |    Nem  | Nem|[További információ](ios-direct-enrollment-in-microsoft-intune.md)|

**Windows-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |   Nem | [További információ](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Nem |Nem |Nem  |[További információ](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Android-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |   Nem | [További információ](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Nem |Nem |Nem  |[További információ](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Az Android for Work-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |   Nem | [További információ](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Nem |Nem |Nem  |[További információ](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**macOS-eszközök regisztrálási módszerei**

| **Módszer** |  **Törölni kell?** |    **Affinitás**    |   **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |   Nem | [További információ](prerequisites-for-enrollment.md)|


A megfelelő módszer kiválasztásában segít az [Eszközök regisztrálási módjának kiválasztása](/intune-classic/get-started/choose-how-to-enroll-devices1) című témakörben található kérdéssor.

## <a name="byod"></a>BYOD
A saját eszközeiket használó („BYOD”) felhasználók telepítik a Vállalati portál alkalmazást, és ők regisztrálják az eszközt. Ez lehetővé teszi a felhasználók számára a vállalati hálózathoz való kapcsolódást, így csatlakozhatnak a tartományhoz vagy az Azure Active Directoryhoz. A legtöbb platformon és COD-forgatókönyv esetében engedélyeznie kell a BYOD-regisztrálást. További információk: [Az eszközök regisztrálásának előfeltételei](prerequisites-for-enrollment.md). ([Vissza a táblázathoz](#overview-of-device-enrollment-methods))

## <a name="corporate-owned-devices"></a>Vállalati tulajdonú eszközök
A vállalati tulajdonú eszközök (COD) az Intune-konzol segítségével kezelhetők. Az iOS-eszközök az Apple által biztosított megoldások segítségével közvetlenül is regisztrálhatók. A rendszergazdák vagy menedzserek bármilyen típusú eszközt regisztrálhatnak az eszközregisztráció-kezelő segítségével. Az IMEI-számmal rendelkező eszközöket azonosítani lehet, és meg lehet jelölni vállalati tulajdonúként, ami lehetőséget nyújt a vállalati tulajdonú eszközök kezelésére.

További információk: [Vállalati tulajdonú eszközök regisztrálása](manage-corporate-owned-devices.md).

### <a name="dem"></a>DEM
Az eszközregisztráció-kezelő egy speciális Intune-fiók, amely több vállalati tulajdonú eszköz regisztrációjára és felügyeletére szolgál. A kezelők tudják telepíteni a Vállalati portált és regisztrálni számos, felhasználó nélküli eszközt. További információ a [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) módszerről. ([Vissza a táblázathoz](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Az Apple készülékregisztrációs program (DEP) lehetővé teszi szabályzatok létrehozását és vezeték nélküli központi telepítését a DEP keretében vásárolt és felügyelt eszközökre. Az eszköz regisztrálása akkor történik, amikor a felhasználók első alkalommal bekapcsolják az eszközt, és futtatják rajta az iOS beállítási asszisztens alkalmazást. Ez a módszer támogatja az **iOS Supervised** (Felügyelt) üzemmódot, amely lehetővé teszi a következő funkciókat:
  - Zárolt regisztráció
  - Teljes képernyős mód és más speciális konfigurációk és korlátozások

További információk a [DEP](ios-device-enrollment-program-in-microsoft-intune.md) programról. ([Vissza a táblázathoz](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB-SA
Az Apple Configurator segítségével a rendszergazdák a beállítási asszisztens használatával USB-kapcsolaton keresztül manuálisan előkészíthetnek minden vállalat által birtokolt eszközt. A rendszergazda létrehoz egy regisztrációs profilt, és exportálja azt az Apple Configuratorba. Amikor a felhasználók megkapják az eszközeiket, választhatják a beállítási asszisztens futtatását az eszköz regisztrálásához. Ez a módszer támogatja az **iOS Supervised** (Felügyelt) üzemmódot, amely lehetővé teszi a következő funkciókat:
  - Zárolt regisztráció
  - Teljes képernyős mód és más speciális konfigurációk és korlátozások

További információ [az eszközöknek az Apple Configurator és Beállítási asszisztens segítségével történő regisztrálásáról](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Vissza a táblázathoz](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB-Direct
A közvetlen regisztrációhoz a rendszergazdának a regisztrációs házirend létrehozásához és az Apple Configuratorba való exportálásához manuálisan kell regisztrálnia minden eszközt. Az USB-csatlakozású, vállalati tulajdonú eszközök regisztrálása közvetlenül történik, a gyári beállítások visszaállítása nem szükséges. Az eszközök kezelése felhasználó nélküli eszközökként történik. Nincsenek zárolva, sem felügyelve, és nem támogathatják a feltételes hozzáférést, a függetlenítés észlelését, illetve a mobilalkalmazás-felügyeletet.  További információk [az Apple Configurator segítségével történő közvetlen regisztrálásáról](ios-direct-enrollment-in-microsoft-intune.md). ([Vissza a táblázathoz](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Mobileszköz-kezelés az Exchange ActiveSync és az Intune használatával
Azok a mobileszközök, amelyek nincsenek regisztrálva, de kapcsolódnak az Exchange ActiveSync (EAS) rendszerhez, EAS MDM-szabályzat segítségével kezelhetők az Intune-ban. Az Intune helyszíni vagy felhőalapú Exchange Connector összekötő segítségével kommunikál az EAS-szel. További információk: [Mobileszköz-kezelés az Exchange ActiveSync és az Intune használatával](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Windows-számítógépek kezelése az Intune-nal  
Az Intune ügyfélszoftvere segítségével Windows-számítógépeket is kezelhet a Microsoft Intune-nal. Az Intune ügyfél által felügyelt Windows-számítógépek:

 - Képesek szoftver- és hardverleltár jelentésére
 - Képesek asztali alkalmazások telepítésére (például .exe és .msi kiterjesztésű fájlok segítségével)
 - Tűzfal beállításainak felügyeletéhez

Az Intune ügyfélszoftverével felügyelt számítógépeken csak szelektív törlést lehet végezni, teljes törlést nem. Az Intune ügyfélszoftverével felügyelt számítógépeken az Intune számos felügyeleti funkciója (például a feltételes hozzáférés, a VPN- és Wi-Fi-beállítások meghatározása vagy a tanúsítványok és e-mail-konfigurációk telepítése) sem használható. További információk: [Windows rendszerű számítógépek felügyelete az Intune-nal](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Támogatott eszközplatformok

Az Intune a következő eszközplatformokat képes kezelni:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>További lépések
- [Az eszközök regisztrálásának előfeltételei](prerequisites-for-enrollment.md)
- [Vállalati tulajdonú eszközök kezelése](manage-corporate-owned-devices.md)
- [Támogatott mobileszközök és számítógépek](/intune/supported-devices-browsers#intune-supported-devices)
