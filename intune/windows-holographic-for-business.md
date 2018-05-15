---
title: Windows Holographic rendszerű eszközök felügyelete az Azure-beli Microsoft Intune-nal | Microsoft Docs
description: Windows Holographic for Business rendszerű eszközökön sokféle feladatot végrehajthat a Microsoft Intune használatával, egyebek között konfigurálhatja a Céges portált, létrehozhat megfelelőségi szabályzatokat, testre szabhat OMA-URI-beállításokat, telepíthet alkalmazásokat, csoportokba sorolhat eszközöket, profilokat hozhat létre, eszközöket korlátozhat, szoftverfrissítéseket engedélyezhet, konfigurálhatja a VPN- és Wi-Fi-beállításokat és használhatja a Hello for Businesst.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18f86580fc4c80fade7aeaa9678e9d8edac9a53e
ms.sourcegitcommit: b57be56524ddb5026fab94f7638dc516ed118325
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Windows Holographic rendszerű eszközök testre szabása az Intune-nal

A Microsoft Intune-nal felügyelhetőek a Windows Holographic for Business rendszert futtató eszközök is, például a [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Windows Holographic rendszerű eszközök Microsoft Intune-nal való felügyeletéhez létre kell hoznia egy kiadásfrissítési profilt. Ez a frissítési profil frissíti az eszközöket a Windows Holographic rendszerről a Windows Holographic for Business rendszerre. A Microsoft HoloLens esetében a frissítéshez szükséges licenc beszerzéséhez megvásárolhatja a Commercial Suite-ot is. További információt [A Windows Holographic operációs rendszert futtató eszközök frissítése a Windows Holographic for Business verzióra](holographic-upgrade.md) című témakörben talál.

A Windows Holographic for Business rendszerű eszközök felügyeletében és testre szabásában segítenek az e cikkben leírt műveletek. Kezelheti többek között például a szoftverfrissítéseket és konfigurálhatja a VPN-beállításokat.

## <a name="azure-active-directory"></a>Azure Active Directory

Az Azure Active Directory (AD) segítségével könnyedén kezelheti és vezérelheti a Windows Holographic for Business rendszerű eszközeit. Az Intune és az Azure AD használatával: 

- **[Az Azure Active Directoryhoz kapcsolt eszközök beállítása](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-setup)**: Windows 10 rendszerű munkahelyi eszközeit, beleértve a Windows Holographic for Business rendszerű eszközöket is, hozzáadhatja az Azure Active Directoryhoz. Ez a funkció lehetővé teszi, hogy az Azure AD vezérelje az eszközt. Segít biztosítani, hogy a felhasználói olyan eszközökről csatlakozzanak a vállalati erőforrásokhoz, amelyek megfelelnek a vállalat biztonsági és megfelelőségi szabványainak.

  További részletekért tekintse meg [Az Azure AD-val történő eszközkezelés bemutatása](https://docs.microsoft.com/azure/active-directory/device-management-introduction) cikket.

- **[Csoportos regisztráció Windows-eszközök esetében](windows-bulk-enroll.md)**: Egyszerre nagy számú új windowsos eszközt is csatlakoztathat az Azure Active Directoryhoz és az Intune-hoz. Ezt a szolgáltatást csoportos regisztrációnak hívják, és kiépítési csomagokat használ. Ezek a csomagok összekötik a Windows Holographic for Business rendszerű eszközöket az Azure AD-bérlővel, és regisztrálják őket az Intune-ban.

## <a name="company-portal"></a>Céges portál
**[A Céges portál alkalmazás konfigurálása](company-portal-app.md)**

Az Intune része a Céges portál, ahol a felhasználók egyebek között hozzáférnek a vállalat adataihoz, eszközöket regisztrálnak, alkalmazásokat telepítenek és kapcsolatba lépnek az IT-részleggel. A Céges portál alkalmazás testre szabható a Windows Holographic for Bussines rendszerű eszközökhöz.

## <a name="compliance-policy"></a>Megfelelőségi szabályzat
**[Eszközmegfelelőségi szabályzat létrehozása](compliance-policy-create-windows.md)**

A megfelelőségi szabályzatok olyan szabályok és beállítások, amelyeknek az eszközöknek eleget kell tenniük, hogy megfelelőnek minősüljenek. Ezeket a szabályzatokat feltételes hozzáféréssel használva megakadályozhatja, hogy nem megfelelő eszközök hozzáférjenek a vállalati erőforrásokhoz. Az Intune-ban létrehozhat a Windows Holographic for Business rendszerű eszközök hozzáférését engedélyező vagy tiltó megfelelőségi szabályzatokat is. Létrehozhat például olyan szabályzatot, amely megköveteli a Bitlocker engedélyezését.

Lásd még: **[Első lépések a megfelelőségi szabályzatokkal](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Alkalmazások központi telepítése és kezelése
**[Alkalmazások hozzáadása az Intune-hoz](apps-add.md)**

Az Intune használatával alkalmazásokat adhat hozzá a Windows Holographic for Business rendszerű eszközeihez. Alkalmazások telepítésére több mód is van, többek között:

- [Microsoft Áruházbeli alkalmazások hozzáadása](store-apps-windows.md)
- [Saját készítésű alkalmazások hozzáadása](lob-apps-windows.md)
- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

A Microsoft Intune-nal univerzális Windows-alkalmazások telepíthetők a Windows Holographic for Business rendszert futtató Microsoft HoloLens-eszközökre. Az alkalmazáscsomagok közvetlenül feltölthetők az Intune Azure Portalon, vagy üzembe helyezhetők a Microsoft Store Vállalatoknak áruházból. A kapcsolódó témakörökről az alábbi cikkek nyújtanak bővebb információt:
- Üzletági alkalmazások telepítéséről az Intune Azure Portalon: [Windowsos üzletági alkalmazások hozzáadása a Microsoft Intune-hoz](lob-apps-windows.md).
- Alkalmazások telepítéséről a Microsoft Store Vállalatoknak áruházból: [A Microsoft Store Vállalatoknak áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal](windows-store-for-business.md). 
- Alkalmazások kezeléséről a Microsoft Intune-nal: [Alkalmazáskezelés a Microsoft Intune-ban](app-management.md).
- A Microsoft HoloLensre készülő alkalmazások fejlesztéséről: [Vegyes valóság alkalmazások a Microsoft HoloLenshez](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> A Windows 10 Holographic for Business 1607 rendszerű HoloLens-eszközök nem támogatják a Microsoft Store Vállalatoknak áruházból származó, online licencelt alkalmazásokat. További információ: [Alkalmazások telepítése a HoloLens-re](https://docs.microsoft.com/en-us/hololens/hololens-install-apps).

## <a name="device-actions"></a>Eszközműveletek
Az Intune rendelkezik néhány olyan beépített funkcióval, amelyek használatával a rendszergazdák különböző műveleteket végezhetnek lokálisan az eszközön, vagy távoli eléréssel az Intune-ban az Azure Portalról. A saját tulajdonban lévő, Intune-ban regisztrált eszközeikre a felhasználók is kiadhatnak egy távoli parancsot az Intune céges portálon keresztül.

Windows Holographic for Business rendszert futtató eszközök használata esetén a következő műveletek végezhetők: 

- **[Gyári beállítások visszaállítása](devices-wipe.md#factory-reset)**: A **Gyári beállítások visszaállítása** művelet eltávolítja az eszközt az Intune-ból, és visszaállítja az eszköz gyári alapértelmezett beállításait. Ezt a műveletet akkor érdemes használni, mielőtt az eszközt egy új felhasználónak adják, vagy ha az eszköz elveszett, vagy ellopták.

- **[Céges adatok eltávolítása](devices-wipe.md#remove-company-data)**: A **Céges adatok eltávolítása** művelet eltávolítja az eszközt az Intune-ból, eltávolítja a felügyelt alkalmazásadatokat, beállításokat és az Intune által hozzárendelt e-mail-profilokat. A felhasználó személyes adatai az eszközön maradnak.

- **[Eszköz szinkronizálása a legfrissebb szabályzatok és műveletek hozzáadásához](device-sync.md)**: A **Szinkronizálás** művelettel kényszeríteni lehet az eszközt, hogy azonnal csatlakozzon az Intune-hoz. Bejelentkezéskor az eszköz azonnal fogadja az hozzárendelt összes függőben lévő műveletet vagy szabályzatot. Ez a funkció segíthet ellenőrizni a vonatkozó szabályzatokat és elhárítani a hibákat anélkül, hogy ki kellene várni a következő ütemezett bejelentkezést.

**[A Microsoft Intune-eszközfelügyelet ismertetése](device-management.md)**  című cikkből további részleteket is megtudhat az Azure Portal használatával történő eszközkezelésről. 

## <a name="device-categories-and-groups"></a>Eszközkategóriák és csoportok
**[Eszközök csoportokba sorolása](device-group-mapping.md)**

Az Intune használatával eszközkategóriákat hozhat létre, hogy azok alapján automatikusan hozzáadja az eszközöket az olyan csoportokhoz, mint az Értékesítés, Könyvelés, Emberi erőforrások stb. A cél a Windows Holographic for Business rendszerű eszközök felügyeletének megkönnyítése.

## <a name="device-configuration-profiles"></a>Eszközkonfigurációs profilok 
**[Első lépések a konfigurációs profilokkal](device-profiles.md) és [saját profil létrehozása](device-profile-create.md)**

Az Intune olyan beállításokat és funkciókat kínál, amelyeket Ön engedélyezhet vagy letilthat a vállalatához tartozó különböző eszközökön. Ezek a beállítások és funkciók profilok használatával kezelhetők. Létrehozhat például olyan profilt, amely a Cortanát engedélyezi vagy a Windows Defender SmartScreent használja a Windows Holographic for Business rendszerű eszközein.

Profiljaiban OMA-URI használatával testre szabhat néhány beállítást, létrehozhat eszközkorlátozásokat és konfigurálhatja a virtuális magánhálózatokat (VPN) és a Wi-Fit.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Egyéni eszközbeállítások](custom-settings-windows-holographic.md)

Az OMA-URI (Open Mobile Alliance Uniform Resource Identifier) konfigurálásához egyéni profilt hozhat létre az Intune-ban. Az OMA-URI beállítások használatával a Windows Holographic for Business rendszerű eszközök olyan funkcióit szabályozhatja, mint a VPN engedélyezése vagy a frissítések keresése a Microsoft Update szolgáltatásban.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Eszközkorlátozások](device-restrictions-windows-holographic.md)

Az eszközkorlátozásokkal többek között az eszközök olyan beállításai és funkciói szabályozhatók, mint a jelszó megkövetelése, alkalmazások telepítése a [Microsoft Áruházból](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps) vagy a Bluetooth engedélyezése. Ezek a korlátozások egy Intune-profilban jönnek létre. Ez a profil több Windows Holographic for Business rendszerű eszközön is alkalmazható.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[VPN konfigurálása](vpn-settings-configure.md)

A virtuális magánhálózatok (VPN) segítségével biztonságos távoli hozzáférést biztosíthat felhasználóinak a vállalati hálózathoz. Az Intune-ban létrehozhat a Windows Holographic for Business rendszerű eszközeire vonatkozó beállításokat tartalmazó VPN-profilt. Létrehozhat például egy VPN-profilt, hogy minden Windows Holographic for Business rendszerű eszköz Citrix VPN-t használjon kapcsolattípusként.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Wi-Fi konfigurálása](wi-fi-settings-configure.md)

Az Intune-ban Wi-Fi-profilt is létrehozhat, amellyel vezeték nélküli hálózati beállításokat rendel a Windows Holographic for Business rendszerű eszközeihez. Wi-Fi-profil hozzárendelésekor a végfelhasználók a hálózat konfigurálása nélkül kapnak vállalati hálózati hozzáférést. Létrehozhat például egy Wi-Fi hálózatot külön a Windows Holographic for Business rendszerű eszközöknek.

## <a name="software-updates"></a>Szoftverfrissítések
**[Szoftverfrissítések kezelése](windows-update-for-business-configure.md)**

Az Intune tartalmaz egy frissítési körök nevű funkciót a Windows 10-es eszközökhöz. A frissítési körökhöz tartozik a frissítések telepítési módját meghatározó beállítások egy csoportja. Létrehozhat például egy karbantartási időszakot a frissítések telepítésére vagy eldöntheti, hogy kíván-e újraindítást a frissítések telepítése után. Egy frissítési kör több Windows Holographic for Business rendszerű eszközre is alkalmazható.

## <a name="terms-and-conditions"></a>használati feltételei
**[A vállalati felhasználói hozzáférési használati feltételek megadása](terms-and-conditions-create.md)**

Megkövetelheti, hogy a felhasználók csak a használati feltételek elfogadása után regisztrálhassák eszközeiket és érhessék el a céges alkalmazásokat, köztük a levelezést. Az Intune-ban megadhatja, hogy hogyan jelenjenek meg a használati feltételek a Céges portálon és ezeket a használati feltételeket hozzá is rendelheti a Windows Holographic for Business rendszerű eszközökhöz.

## <a name="windows-hello-for-business"></a>Vállalati Windows Hello
**[A Vállalati Windows Hello használata](windows-hello.md)**

A Vállalati Windows Hello egy alternatív bejelentkezési módszer, amely egy Azure Active Directory-fiókot használ jelszó, intelligens kártya vagy virtuális intelligens kártya helyett. A Vállalati Windows Hellóval Windows Holographic for Business rendszerű eszközei PIN-kóddal jelentkezhetnek be, amelynek minimális hosszát Ön állítja be.
