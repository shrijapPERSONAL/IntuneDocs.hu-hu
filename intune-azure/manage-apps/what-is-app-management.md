---
title: "Mi az alkalmazáskezelés? | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: Ezen témakör a Microsoft Intune-nal történő alkalmazáskezeléssel kapcsolatos alapismereteket tartalmazza"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 33bc87d16834cb2950cc7c66ad4887dddb12e811


---

# <a name="what-is-app-management"></a>Mi az alkalmazáskezelés?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Rendszergazdaként valószínűleg az Ön feladata annak biztosítása, hogy a végfelhasználók hozzáférhessenek a munkájukhoz szükséges alkalmazásokhoz. Ez kihívást jelenthet, mivel:
- Sokféle eszközplatformot és alkalmazástípust kell kezelnie.
- Előfordulhat, hogy a vállalati eszközökön, valamint a felhasználók saját eszközein található alkalmazásokat is kezelnie kell.
- Mindezek mellett biztosítania kell a hálózat és az adatok biztonságát is. 

Emellett előfordulhat, hogy az Intune-ban nem regisztrált eszközökön található alkalmazásokat is szeretne hozzárendelni és felügyelni.

Az Intune számos szolgáltatást kínál az szükséges alkalmazások a kívánt eszközökön való használata érdekében.

## <a name="app-management-capabilities-by-platform"></a>Alkalmazás-felügyeleti szolgáltatások platform szerint

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Alkalmazások hozzáadása és hozzárendelése eszközökhöz és felhasználókhoz|Igen|Igen|Igen|Igen|
|Alkalmazások hozzárendelése az Intune-ban nem regisztrált eszközökhöz|Igen|Igen|Nem|Nem|
|Az alkalmazások indítási viselkedését vezérlő alkalmazáskonfigurációs szabályzatok használata|Nem|Igen|Nem|Nem|
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

<sup>1</sup> Vagye fontolóra a [Windows Információvédelem](/intune-azure/configure-devices/how-to-configure-windows-information-protection) használatát a Windows 10 rendszerű eszközökön futó alkalmazások védelmére.

<sup>2</sup>Csak az Intune által kezelt eszközökre vonatkozik.


## <a name="how-to-get-started"></a>Első lépések

Az alkalmazáshoz kapcsolódó legtöbb dolgot a **Mobile Apps** munkafolyamatban találja, amely a következőképpen érhető el:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + Felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.

    ![A Mobile Apps munkafolyamat](./media/apps-workload.png)

### <a name="manage"></a>A számítógépeken futó
- **Alkalmazások** – Itt adhatja hozzá, rendelheti hozzá és figyelheti az alkalmazások többségét. 
    - [Alkalmazások hozzáadása](add-apps.md)
    - [Alkalmazások hozzárendelése](deploy-apps.md)
    - [Alkalmazások figyelése](monitor-apps.md)
- **Licencelt alkalmazások** – Mennyiségi licencszerződés keretében, az alkalmazás-áruházakból vásárolt alkalmazások megtekintése, telepítése és figyelése.
    - [A Vállalati Windows Áruházból mennyiségi programban vásárolt alkalmazások](wsfb-apps.md)
- **Alkalmazáskonfigurációs szabályzatok** – Az alkalmazáskonfigurációs szabályzatokkal automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor egy felhasználó egy alkalmazást futtat. A részletekért lásd:
    - [Alkalmazáskonfigurációs szabályzatok](app-configuration-policies.md)
- **Alkalmazásvédelmi szabályzatok** – Lehetővé teszik beállítások társítását egy alkalmazáshoz a használt céges adatok védelme érdekében. Például korlátozhatja egy alkalmazás más alkalmazásokkal való kommunikációját, vagy előírhatja PIN-kód megadását a felhasználónak egy céges alkalmazás eléréséhez.
    - [Alkalmazásvédelmi szabályzatok](app-protection-policies.md)
- **Szelektív alkalmazástörlés** – Csak a céges adatok eltávolítása a kiválasztott felhasználó eszközéről.
    - [Alkalmazások szelektív törlése](app-selective-wipe.md)

### <a name="monitor"></a>Figyelő
- **Felderített alkalmazások** – Az Intune által hozzárendelt, és az eszközön telepített összes alkalmazás megjelenítése.
- **Alkalmazástelepítési állapot** – Egy Ön által létrehozott alkalmazás-hozzárendelés állapotát jeleníti meg.
- **Alkalmazásvédelmi felhasználó állapota** – A kiválasztott felhasználó egy alkalmazásvédelmi szabályzatának állapotát jeleníti meg.

További információkért lásd: [Alkalmazások figyelése](monitor-apps.md)

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](ios-vpp-apps.md) --->
- **Vállalati Windows Áruház** – A Vállalati Windows Áruházba történő integráció beállítása. Ezt követően a megvásárolt alkalmazásokat az Intune-ban szinkronizálhatja, hozzárendelheti és nyomon követheti licenchasználatát. 
    - [A Vállalati Windows Áruházból mennyiségi programban vásárolt alkalmazások](wsfb-apps.md)
- **A Céges portál védjegye** – A Céges portál testreszabása saját céges védjegy megadásával. 
    - [Céges portál konfigurálása](company-portal-app.md)



<!--HONumber=Feb17_HO1-->

