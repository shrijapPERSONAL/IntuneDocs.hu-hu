---
title: "Az alkalmazáskezelés a Microsoft Intune-ban"
titlesuffix: 
description: "Ezen témakör a Microsoft Intune-nal történő alkalmazáskezeléssel kapcsolatos alapismereteket tartalmazza."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 737c2900b2cdd57cb4dfc8373d06111a52e772b2
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2018
---
# <a name="what-is-microsoft-intune-app-management"></a>A Microsoft Intune-alkalmazásfelügyelet ismertetése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


A Microsoft Intune lehetővé teszi a rendszergazdáknak, hogy a cég által használt mobilalkalmazásokat felügyeljék. Ez a funkció az eszközkezelési és adatvédelmi funkciókat egészíti ki. A funkció használatánál elsődleges szempont, hogy a felhasználók hozzáférhessenek a munkájukhoz szükséges alkalmazásokhoz. Ez kihívást jelenthet, mivel:
- Sokféle eszközplatformot és alkalmazástípust kell kezelnie.
- Előfordulhat, hogy a vállalati eszközökön és a felhasználók saját eszközein található alkalmazásokat egyaránt felügyelnie kell.
- Gondoskodnia kell a céges hálózat és a felhasználói adatok biztonságáról.

Emellett előfordulhat, hogy az Intune-ban nem regisztrált eszközökön található alkalmazásokat is szeretne hozzárendelni és felügyelni.

Az Intune számos szolgáltatást kínál a szükséges alkalmazások kívánt eszközökön való használatához. Az alábbi táblázat az alkalmazáskezelési lehetőségeket foglalja össze. A táblázat alatt segítséget talál ahhoz, hogy a Microsoft Intune Azure Portalbeli használatával is megismerkedjen.

## <a name="app-management-capabilities-by-platform"></a>Alkalmazás-felügyeleti szolgáltatások platform szerint

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Alkalmazások hozzáadása és hozzárendelése eszközökhöz és felhasználókhoz|Igen|Igen|Igen|Igen|
|Alkalmazások hozzárendelése az Intune-ban nem regisztrált eszközökhöz|Igen|Igen|Nem|Nem|
|Az alkalmazások indítási viselkedését vezérlő alkalmazáskonfigurációs szabályzatok használata|Nem|Igen|Nem|Nem|
|A mobilalkalmazás-kiépítési szabályzatok használata a lejárt alkalmazások megújítására|Nem|Igen|Nem|Nem|
|A céges adatok védelme alkalmazásvédelmi szabályzatokkal az alkalmazásokban|Igen|Igen|Nem|Nem<sup>1</sup>|
|Csak a céges adatok eltávolítása egy telepített alkalmazásból (alkalmazások szelektív törlése)|Igen|Igen|Igen|Igen|
|Az alkalmazás-hozzárendelések figyelése|Igen|Igen|Igen|Igen|
|Egy alkalmazás-áruházból mennyiségi licencszerződés keretében vásárolt alkalmazások hozzárendelése és nyomon követése|Nem|Nem|Nem|Igen|
|Az alkalmazások kötelező telepítése eszközökön (kötelező)<sup>2</sup>|Igen|Igen|Igen|Igen|
|Nem kötelező telepítés az eszközökön a Céges portálról (elérhető telepítés)|Igen|Igen|Igen|Igen|
|Alkalmazás telepítési hivatkozása a weben (webes hivatkozás)|Igen|Igen|Igen|Igen|
|Belső fejlesztésű (üzletági) alkalmazások|Igen|Igen|Nem|Igen|
|Áruházbeli alkalmazások|Igen|Igen|Igen|Igen|
|Alkalmazások frissítése|Igen|Igen|Igen|Igen|

<sup>1</sup> Vagye fontolóra a [Windows Információvédelem](windows-information-protection-configure.md) használatát a Windows 10 rendszerű eszközökön futó alkalmazások védelmére.

<sup>2</sup>Csak az Intune által kezelt eszközökre vonatkozik.

## <a name="how-to-get-started"></a>Első lépések

Az alkalmazáshoz kapcsolódó legtöbb dolgot a **Mobile Apps** munkafolyamatban találja, amely a következőképpen érhető el:

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.

    ![A Mobile Apps munkafolyamat](./media/apps-workload.png)

Az alábbi információ a **Mobilalkalmazások** panelen elérhető lehetőségeknek felel meg.

### <a name="manage"></a>A számítógépeken futó
- **Alkalmazások** – Ezzel a beállítással a munkaerő által használt alkalmazásokat adhatja hozzá, tekintheti meg, rendelheti hozzá és figyelheti. További információt az alábbi cikkekben talál:
    - [Alkalmazások hozzáadása](apps-add.md)
    - [Alkalmazások hozzárendelése](apps-deploy.md)
    - [Alkalmazások figyelése](apps-monitor.md)
- **Alkalmazáskonfigurációs szabályzatok** – Az alkalmazáskonfigurációs szabályzatokkal automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy alkalmazást futtat. További információt az alábbi cikkekben talál:
    - [Az Intune alkalmazáskonfigurációs szabályzatai](app-configuration-policies-overview.md)
        - [iOS-es alkalmazáskonfigurációs szabályzatok](app-configuration-policies-use-ios.md)
        - [Androidos alkalmazáskonfigurációs szabályzatok](app-configuration-policies-use-android.md)
- **Alkalmazásvédelmi szabályzatok** – Az alkalmazásvédelmi szabályzatok lehetővé teszik beállítások társítását egy alkalmazáshoz a használt céges adatok védelme érdekében. Például korlátozhatja egy alkalmazás más alkalmazásokkal való kommunikációját, vagy előírhatja PIN-kód megadását a felhasználónak egy céges alkalmazás eléréséhez. További információt az alábbi cikkekben talál:
    - [Alkalmazásvédelmi szabályzatok](app-protection-policies.md)
- **Szelektív alkalmazástörlés** – Csak a céges adatok eltávolítása a kiválasztott felhasználó eszközéről. További információt az alábbi cikkekben talál:
    - [Alkalmazások szelektív törlése](apps-selective-wipe.md)
- **iOS-alkalmazáskiépítési profilok** – Az iOS-alkalmazások tartalmaznak egy kiépítési profilt és kódot, tanúsítvánnyal aláírva. Ha a tanúsítvány lejár, az alkalmazás a továbbiakban nem futtatható. Az Intune biztosítja az eszközöket, amelyek segítségével proaktív módon rendelhet hozzá új kiépítési profilt azokhoz az eszközökhöz, amelyeken hamarosan lejárnak az alkalmazások. További információt az alábbi cikkekben talál:
    - [iOS-alkalmazáskiépítési profilok](app-provisioning-profile-ios.md)

További információért lásd: [Alkalmazások kezelése](app-management.md).

### <a name="monitor"></a>Figyelő
- **Alkalmazáslicencek** – Az alkalmazás-áruházakból vásárolt mennyiségi licencszerződéses alkalmazások megtekintése, hozzárendelése és figyelése. További információt az alábbi cikkekben talál:
    - [iOS Volume Purchase Program-alkalmazások](vpp-apps-ios.md)
    - [A Vállalati Microsoft Áruházból mennyiségi programban vásárolt alkalmazások](windows-store-for-business.md)
- **Felderített alkalmazások** – Megjeleníti az Intune által hozzárendelt, és az eszközön telepített összes alkalmazást.
- **Alkalmazástelepítési állapot** – Egy Ön által létrehozott alkalmazás-hozzárendelés állapotát jeleníti meg.
- **Alkalmazásvédelem állapota** – A kiválasztott felhasználó egy alkalmazásvédelmi szabályzatának állapotát jeleníti meg.
- **Naplók** – Megjeleníti az Intune alkalmazáshoz kapcsolódó tevékenységeket az összes rendszergazdától.

További információért lásd: [Alkalmazások figyelése](apps-monitor.md).

### <a name="setup"></a>Setup
- **iOS VPP-jogkivonatok** – Megtekintheti és felhasználhatja az iOS Volume Purchase Program (VPP) keretében beszerzett licenceit.
    - [iOS Volume-Purchased Program keretében vásárolt alkalmazások](vpp-apps-ios.md)
- **Windowsos vállalati tanúsítvány** – Alkalmazhat egy olyan kódaláíró tanúsítványt, amely üzletági alkalmazások felügyelt Windows-eszközökre való terjesztésére szolgál, vagy megtekintheti az állapotát.
- **Windowsos Symantec-tanúsítvány** – Alkalmazhat egy Symantec kódaláíró tanúsítványt, mely XAP és WP8.x appx-fájlok Windows 10 Mobile-eszközökre való terjesztéséhez szükséges, vagy megtekintheti az állapotát.
- **Vállalati Microsoft Áruház** – A Vállalati Microsoft Áruházba történő integráció beállítása. Ezt követően az Intune-ban szinkronizálhatja és kioszthatja a megvásárolt alkalmazásokat, továbbá nyilvántarthatja a licenchasználatot. További információt az alábbi cikkekben talál:
    - [A Vállalati Microsoft Áruházból mennyiségi programban vásárolt alkalmazások](windows-store-for-business.md)
- **Közvetlen telepítési kulcsok (Windows)** – Hozzáadhat egy Windowsos közvetlen telepítési kulcsot, mellyel közvetlenül az eszközre telepíthet egy alkalmazást, ahelyett hogy közzétenné azt a Windows Áruházban, majd onnan telepítené. További információt az alábbi cikkekben talál:
    - [Windows-alkalmazás közvetlen telepítése](app-sideload-windows.md)
- **A Céges portál védjegye** – A Céges portál testreszabása saját céges védjegy megadásával. További információt az alábbi cikkekben talál:
    - [Céges portál konfigurálása](company-portal-app.md)
- **Alkalmazáskategóriák** – Alkalmazáskategória-neveket adhat hozzá, rögzíthet és törölhet.
- **Android for Work** – Jóváhagyhatja a cégben engedélyezett alkalmazásokat, és szinkronizálhatja őket. További információt az alábbi cikkekben talál:
    - [Android for Work-alkalmazások](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Súgó és támogatás
- **Súgó és támogatás** – Hibaelhárítási információkat kereshet, támogatást kérhet, és megtekintheti az Intune állapotát. További információt az alábbi cikkekben talál:
    - [Problémák elhárítása](help-desk-operators.md)

## <a name="next-steps"></a>További lépések

- [Alkalmazás hozzáadása a Microsoft Intune-hoz](apps-add.md)
