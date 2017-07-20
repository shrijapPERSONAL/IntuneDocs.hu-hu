---
title: "Mi az alkalmazáskezelés?"
titleSuffix: Intune on Azure
description: "Ezen témakör a Microsoft Intune-nal történő alkalmazáskezeléssel kapcsolatos alapismereteket tartalmazza"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 33ddb60df7aebe36ff652e1da6da592442b96d4b
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2017
---
# A Microsoft Intune-alkalmazásfelügyelet ismertetése
<a id="what-is-microsoft-intune-app-management" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Rendszergazdaként az Ön feladata biztosítani, hogy a végfelhasználók hozzáférhessenek a munkájukhoz szükséges alkalmazásokhoz. Ez kihívást jelenthet, mivel:
- Sokféle eszközplatformot és alkalmazástípust kell kezelnie.
- Előfordulhat, hogy a vállalati eszközökön, valamint a felhasználók saját eszközein található alkalmazásokat is felügyelnie kell.
- Gondoskodnia kell a céges hálózat és a felhasználói adatok biztonságáról.

Emellett előfordulhat, hogy az Intune-ban nem regisztrált eszközökön található alkalmazásokat is szeretne hozzárendelni és felügyelni.

Az Intune számos szolgáltatást kínál az szükséges alkalmazások a kívánt eszközökön való használata érdekében.

## Alkalmazás-felügyeleti szolgáltatások platform szerint
<a id="app-management-capabilities-by-platform" class="xliff"></a>

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
|Alkalmazás telepítési hivatkozása a weben (webklip)|Igen|Igen|Igen|Igen|
|Belső fejlesztésű (üzletági) alkalmazások|Igen|Igen|Nem|Nem|
|Áruházbeli alkalmazások|Igen|Igen|Igen|Igen|
|Alkalmazások frissítése|Igen|Igen|Igen|Igen|

<sup>1</sup> Vagye fontolóra a [Windows Információvédelem](windows-information-protection-configure.md) használatát a Windows 10 rendszerű eszközökön futó alkalmazások védelmére.

<sup>2</sup>Csak az Intune által kezelt eszközökre vonatkozik.

## Első lépések
<a id="how-to-get-started" class="xliff"></a>

Az alkalmazáshoz kapcsolódó legtöbb dolgot a **Mobile Apps** munkafolyamatban találja, amely a következőképpen érhető el:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.

    ![A Mobile Apps munkafolyamat](./media/apps-workload.png)

### A számítógépeken futó
<a id="manage" class="xliff"></a>
- **Alkalmazások** – Itt veheti fel, oszthatja ki és figyelheti az alkalmazások többségét.
    - [Alkalmazások hozzáadása](apps-add.md)
    - [Alkalmazások hozzárendelése](apps-deploy.md)
    - [Alkalmazások figyelése](apps-monitor.md)
- **Alkalmazáskonfigurációs szabályzatok** – Az alkalmazáskonfigurációs szabályzatokkal automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy alkalmazást futtat.
    - [iOS-es alkalmazáskonfigurációs szabályzatok](app-configuration-policies-use-ios.md)
    - [Androidos alkalmazáskonfigurációs szabályzatok](app-configuration-policies-use-android.md)
- **Alkalmazásvédelmi szabályzatok** – Lehetővé teszik beállítások társítását egy alkalmazáshoz a használt céges adatok védelme érdekében. Például korlátozhatja egy alkalmazás más alkalmazásokkal való kommunikációját, vagy előírhatja PIN-kód megadását a felhasználónak egy céges alkalmazás eléréséhez.
    - [Alkalmazásvédelmi szabályzatok](app-protection-policies.md)
- **Szelektív alkalmazástörlés** – Csak a céges adatok eltávolítása a kiválasztott felhasználó eszközéről.
    - [Alkalmazások szelektív törlése](apps-selective-wipe.md)
- **iOS-alapú kiépítési profilok** – Az iOS-alkalmazások tartalmaznak egy kiépítési profilt és kódot, tanúsítvánnyal aláírva. Ha a tanúsítvány lejár, az alkalmazás a továbbiakban nem futtatható. Az Intune biztosítja az eszközöket, amelyek segítségével proaktív módon rendelhet hozzá új kiépítési profilt azokhoz az eszközökhöz, amelyeken hamarosan lejárnak az alkalmazások.
    - [iOS-alkalmazáskiépítési profilok](app-provisioning-profile-ios.md)

### Figyelő
<a id="monitor" class="xliff"></a>
- **Licencelt alkalmazások** – Mennyiségi licencszerződés keretében, az alkalmazás-áruházakból vásárolt alkalmazások megtekintése, hozzárendelése és figyelése.
    - [A Vállalati Windows Áruházból mennyiségi programban vásárolt alkalmazások](windows-store-for-business.md)
- **Felderített alkalmazások** – Az Intune által hozzárendelt, és az eszközön telepített összes alkalmazás megjelenítése.
- **Alkalmazástelepítési állapot** – Egy Ön által létrehozott alkalmazás-hozzárendelés állapotát jeleníti meg.
- **Alkalmazásvédelem állapota** – A kiválasztott felhasználó egy alkalmazásvédelmi szabályzatának állapotát jeleníti meg.

További információkért lásd: [Alkalmazások figyelése](apps-monitor.md)

### Setup
<a id="setup" class="xliff"></a>
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **Vállalati Windows Áruház** – A Vállalati Windows Áruházba történő integráció beállítása. Ezt követően az Intune-ban szinkronizálhatja és kioszthatja a megvásárolt alkalmazásokat, továbbá nyilvántarthatja a licenchasználatot.
    - [A Vállalati Windows Áruházból mennyiségi programban vásárolt alkalmazások](windows-store-for-business.md)
- **A Céges portál védjegye** – A Céges portál testreszabása saját céges védjegy megadásával.
    - [Céges portál konfigurálása](company-portal-app.md)