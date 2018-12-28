---
title: Mit jelent az alkalmazáskezelés a Microsoft Intune-ban?
titlesuffix: ''
description: Ügyféloldali alkalmazás felügyeleti funkcióinak bemutatása platform Microsoft Intune-hoz.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: f156accf5b51e7fff51db738c70b0b0840d7e365
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642829"
---
# <a name="what-is-microsoft-intune-app-management"></a>A Microsoft Intune-alkalmazásfelügyelet ismertetése


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A rendszergazdák a Microsoft Intune használatával kezelhetik a cég által használt ügyfélalkalmazásokat. Ez a funkció az eszközkezelési és adatvédelmi funkciókat egészíti ki. A rendszergazdák egyik elsődleges feladata annak biztosítása, hogy a végfelhasználók hozzáférjenek a munkájukhoz szükséges alkalmazásokhoz. Ez a célkitűzés kihívást jelenthet, mivel:
- Sokféle eszközplatformot és alkalmazástípust kell kezelnie.
- Előfordulhat, hogy a vállalati eszközökön és a felhasználók saját eszközein található alkalmazásokat egyaránt felügyelnie kell.
- Folyamatosan gondoskodnia kell a hálózat és az adatok biztonságáról.

Emellett előfordulhat, hogy az Intune-ban nem regisztrált eszközökön található alkalmazásokat is szeretne hozzárendelni és felügyelni.

Az Intune számos szolgáltatással segít a szükséges alkalmazások üzembe helyezésében azokon az eszközökön, amelyeken futtatni kívánják azokat. Az alábbi táblázat az alkalmazáskezelési lehetőségeket foglalja össze: 

## <a name="app-management-capabilities-by-platform"></a>Alkalmazás-felügyeleti szolgáltatások platform szerint

|  | Android | iOS | macOS | Windows 10 | Windows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Alkalmazások hozzáadása és hozzárendelése eszközökhöz és felhasználókhoz | Igen | Igen | Igen | Igen | Igen |
| Alkalmazások hozzárendelése az Intune-ban nem regisztrált eszközökhöz | Igen | Igen | Nem | Nem | Nem |
| Az alkalmazások indítási viselkedését vezérlő alkalmazáskonfigurációs szabályzatok használata | Nem | Igen | Nem | Nem | Nem |
| Mobilalkalmazás-kiépítési szabályzatok használata a lejárt alkalmazások megújítására | Nem | Igen | Nem | Nem | Nem |
| Az alkalmazásokban található vállalati adatok védelme alkalmazásvédelmi szabályzatokkal | Igen | Igen | Nem | Nem1 | Nem |
| Csak a vállalati adatok eltávolítása egy telepített alkalmazásból (alkalmazások szelektív törlése) | Igen | Igen | Nem | Igen | Igen |
| Az alkalmazás-hozzárendelések monitorozása | Igen | Igen | Igen | Igen | Igen |
| Egy alkalmazás-áruházból mennyiségi licencszerződés keretében vásárolt alkalmazások hozzárendelése és nyomon követése | Nem | Nem | Nem | Igen | Nem |
| Az alkalmazások kötelező telepítése az eszközökön (kötelező)2 | Igen | Igen | Igen | Igen | Igen |
| Opcionális telepítés az eszközökön a Céges portálról (elérhető telepítés) | Igen | Igen | Igen | Igen | Igen |
| Alkalmazás telepítési hivatkozása az interneten (webes hivatkozás) | Igen | Igen | Igen | Igen | Igen |
| Belső fejlesztésű (üzletági) alkalmazások | Igen | Igen | Igen | Igen | Nem |
| Áruházbeli alkalmazások | Igen | Igen | Nem | Igen | Igen |
| Alkalmazások frissítése | Igen | Igen | Nem | Igen | Igen |

<sup>1</sup> Vagye fontolóra a [Windows Információvédelem](windows-information-protection-configure.md) használatát a Windows 10 rendszerű eszközökön futó alkalmazások védelmére.

<sup>2</sup> Csak az Intune által kezelt eszközökre vonatkozik.

## <a name="get-started"></a>Bevezetés

Az alkalmazáshoz kapcsolódó legtöbb információ az **Ügyfélalkalmazások** területen található, amely a következőképpen érhető el:

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. A **Microsoft Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.

    ![Az Ügyfélalkalmazások tevékenységprofil](./media/apps-workload.png)

A következő négy szakasz az **Ügyfélalkalmazások** ablaktáblán elérhető lehetőségeket ismerteti.

### <a name="manage"></a>A számítógépeken futó
- **Alkalmazások**: Válassza ki ezt a beállítást, hozzáadása, megtekintése, hozzárendelése és a munkaerő által használt alkalmazások figyelése. További információkért lásd:
    - [Alkalmazások hozzáadása](apps-add.md).
    - [Alkalmazások hozzárendelése](apps-deploy.md).
    - [Alkalmazások figyelése](apps-monitor.md).
- **Alkalmazáskonfigurációs szabályzatok**: Válassza ki az ezzel a beállítással megadhatja azokat a beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy alkalmazást futtat. További információkért lásd:
    - [Az Intune alkalmazáskonfigurációs szabályzatai](app-configuration-policies-overview.md).
        - [iOS-es alkalmazáskonfigurációs szabályzatok](app-configuration-policies-use-ios.md).
        - [Androidos alkalmazáskonfigurációs szabályzatok](app-configuration-policies-use-android.md).
- **Az alkalmazásvédelmi szabályzatok**: Válassza ezt a lehetőséget a beállítások társítását egy alkalmazáshoz, és a használt céges adatok védelme érdekében. Korlátozhatja például egy alkalmazás más alkalmazásokkal való kommunikációját, vagy előírhatja PIN-kód megadását a felhasználónak egy céges alkalmazás eléréséhez. További információkért lásd:
    - [Alkalmazásvédelmi szabályzatok](app-protection-policies.md).
- **Alkalmazások szelektív törlése**: Ezt a beállítást csak a céges adatok eltávolítása a kijelölt felhasználók eszközeiről. További információkért lásd:
    - [Alkalmazások szelektív törlése](apps-selective-wipe.md).
- **iOS-alkalmazáskiépítési profilok**: Az iOS-alkalmazások tartalmaznak egy kiépítési profilt és kódot, tanúsítvánnyal aláírva. Ha a tanúsítvány lejár, az alkalmazás a továbbiakban nem futtatható. Az Intune biztosítja az eszközöket, amelyek segítségével proaktív módon rendelhet hozzá új kiépítési profilt azokhoz az eszközökhöz, amelyeken hamarosan lejárnak az alkalmazások. További információkért lásd:
    - [iOS-alkalmazáskiépítési profilok](app-provisioning-profile-ios.md).

Az e szakasz tartalmával kapcsolatos további információ: [Alkalmazáskezelés](app-management.md).

### <a name="monitor"></a>Figyelés
- **Alkalmazáslicencek**: Megtekintése, hozzárendelése és figyelése az alkalmazás-áruházakból származó, mennyiségi licencszerződés keretében vásárolt alkalmazások. További információkért lásd:
    - [iOS Volume Purchase Program-alkalmazások](vpp-apps-ios.md).
    - [A Microsoft Store Vállalatoknak áruházból mennyiségi programban vásárolt alkalmazások](windows-store-for-business.md).
- **Felderített alkalmazások**: Az Intune által hozzárendelt vagy az eszközön telepített alkalmazások megtekintése. Erről az [Eszközadatok megtekintése a Microsoft Intune-ban](device-inventory.md) című cikk nyújt további tájékoztatást.
- **Alkalmazás telepítési állapota**: Egy Ön által létrehozott alkalmazás-hozzárendelés állapotának megtekintése. További információk: [Alkalmazásadatok és -hozzárendelések figyelése a Microsoft Intune-ban](apps-monitor.md#device-and-user-status-graphs).
- **Alkalmazásvédelem állapota**: A kiválasztott felhasználó egy alkalmazásvédelmi szabályzatának állapotát megtekintheti.
- **Auditnaplók**: Az összes rendszergazda Intune alkalmazáshoz kapcsolódó tevékenységeinek megtekintése.

Az e szakasz tartalmával kapcsolatos további információ: [Alkalmazások figyelése](apps-monitor.md).

### <a name="set-up"></a>Beállítás
- **iOS VPP-jogkivonatok**: Az iOS Volume Purchase Program (VPP) licenceit megtekintheti és felhasználhatja. További információkért lásd:
    - [mennyiségi programban vásárolt iOS-alkalmazások](vpp-apps-ios.md)
- **Windows vállalati tanúsítvány**: Alkalmazása, vagy egy kódaláíró tanúsítványt, amellyel a felügyelt Windows-eszközök – üzletági alkalmazások terjesztéséhez az állapota megtekintése.
- **Windows Symantec-tanúsítvány**: Alkalmazása, vagy megtekintheti az állapotát a Symantec kódaláíró tanúsítványt, amely XAP és WP8.x appx-fájlok Windows 10 Mobile-eszközökön terjeszteni van szükség.
- **Microsoft Store vállalatoknak**: A Microsoft Store vállalatoknak történő integráció beállítása. Ezt követően az Intune-ban szinkronizálhatja és kioszthatja a megvásárolt alkalmazásokat, továbbá nyilvántarthatja a licenchasználatot. További információkért lásd:
    - [A Microsoft Store Vállalatoknak áruházból mennyiségi programban vásárolt alkalmazások](windows-store-for-business.md).
- **Windows közvetlen telepítési kulcsok**: Adjon hozzá egy Windows közvetlen telepítési kulcs, amely segítségével közvetlenül a eszközök helyett közzététele és az alkalmazás letöltése a Windows áruházból származó alkalmazások telepítése. További információkért lásd:
    - [Windows-alkalmazás közvetlen telepítése](app-sideload-windows.md).
- **A céges portál védjegyezése**: A céges védjegy megadásával a céges portál testreszabása. További információkért lásd:
    - [Céges portál konfigurálása](company-portal-app.md).
- **Alkalmazáskategóriák**: Adja hozzá a PIN-kód, és törölje az alkalmazáskategória-neveket.
- **Androidos munkahelyi profil**: Hagyja jóvá, és a cégben engedélyezett alkalmazások szinkronizálása. További információkért lásd:
    - [Androidos munkahelyi profilos alkalmazások](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Súgó és támogatás
- **Súgó és támogatás**: Hibaelhárítás, támogatást kérhet, vagy megtekintheti az Intune állapotát. További információkért lásd:
    - [Problémák elhárítása](help-desk-operators.md).

## <a name="next-steps"></a>További lépések

- [Alkalmazás hozzáadása a Microsoft Intune-hoz](apps-add.md)
