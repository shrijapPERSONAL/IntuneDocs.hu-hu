---
title: Oktatóanyag – útmutató az Intune az Azure Portalon
titleSuffix: Microsoft Intune
description: Ebben az oktatóanyagban, fog ismerkedhet meg a Microsoft Intune értelmezheti a feladatok elvégzésének módját.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 01/31/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c733dbbf992ae10e14ba711b34e621d3f0fb3da8
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57395266"
---
# <a name="tutorial-walkthrough-of-microsoft-intune-in-the-azure-portal"></a>Oktatóanyag: Az útmutató a Microsoft Intune-ban az Azure Portalon

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) több mint 100, segítségére lehetnek a felhő-számítástechnikai helyzetekben és a lehetőségek különböző szolgáltatásokat tartalmaz. A Microsoft Intune Azure-ban elérhető számos szolgáltatás egyike. Az Intune segítségével győződjön meg arról, hogy a vállalati eszközök, alkalmazások és adatok megfelelnek-e a vállalat biztonsági követelményeinek. Rendelkezik a vezérlő, amely követelményeknek kell ellenőrizni kell, és mi történik, ha ezek a követelmények nem teljesülnek. A Microsoft Intune szolgáltatást az [Azure Portalon](https://portal.azure.com) találhatja meg. Az Intune-ban elérhető szolgáltatások megismerése segít a különböző mobileszköz-felügyeleti (MDM) és mobilalkalmazás-felügyeleti (MAM) feladatok elvégzését.

Az oktatóanyag során az alábbi lépéseket fogja végrehajtani:
> [!div class="checklist"]
> * A bemutató a Microsoft Intune-ban
> * Az Azure portál konfigurálása

Ha nem rendelkezik Intune-előfizetéssel, [regisztráljon egy ingyenes próbafiókkal](free-trial-sign-up.md).

## <a name="prerequisites"></a>Előfeltételek
A Microsoft Intune beállítása előtt tekintse át az alábbi követelményeket:

   - [Támogatott operációs rendszerek és böngészők](supported-devices-browsers.md) 
   - [A hálózati konfiguráció követelményei és a sávszélesség](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Regisztráció a Microsoft Intune ingyenes próbaverziójára

Az Intune kipróbálása 30 napig ingyenes. Ha már rendelkezik munkahelyi vagy iskolai fiókkal, **jelentkezzen be** vele, és adja hozzá az Intune-t az előfizetéshez. Egyéb esetben [regisztráljon egy ingyenes próbafiókot](free-trial-sign-up.md) az Intune-nal a szervezet számára.

> [!IMPORTANT]
> Meglévő munkahelyi vagy iskolai fiókok nem vonhatók össze újonnan regisztrált fiókokkal.

## <a name="tour-microsoft-intune"></a>A bemutató a Microsoft Intune-ban

Az Intune segít jobban megérteni az Azure Portalon az alábbi lépésekkel. Miután elvégezte a bemutatót, rendelkezni fog néhány olyan Intune főbb területei jobb megértése.

1. Nyisson meg egy böngészőt, és jelentkezzen be a [Intune-portálon](https://aka.ms/intuneportal). Ha most ismerkedik az Intune-ban, használhatja az ingyenes próba-előfizetését.

    ![A Microsoft Intune-portál képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-01.png)

    Ha megnyitja az Intune-ban vagy bármely más szolgáltatást az Azure-ban, a szolgáltatás panelen jelenik meg. Használhatja az Intune-ban először tevékenységprofilok néhány **eszközök**, **ügyfélalkalmazás**, **felhasználók**, és **csoportok**. Egy számítási feladat a szolgáltatás egyszerűen egy alárendelt területe. Amikor kiválasztja a tevékenységprofilt, panelen megnyílik teljes oldalon. Más panelek megnyitáskor jobb oldali ablaktábla megnyitásához, és közel váljanak az előző ablaktáblára. A panelen is nevezik tartalmazó panel. 

    Alapértelmezés szerint az Intune megnyitásakor látni fogja a **áttekintése** ablaktáblán. Ezen a panelen biztosít egy eszköz-hozzárendelés és megfelelőségi állapotát, valamint az alkalmazás telepítési állapotának általános képi pillanatképét.

2. A [Intune](https://aka.ms/intuneportal)válassza **eszközregisztráció** az Intune-bérlőben a regisztrált eszközök adatainak megjelenítéséhez. Egy új Intune-bérlő rendszertől, ha még nem fog a regisztrált eszközöket. 

    ![Az eszköz regisztrációs panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-02.png)
    
    Az Intune lehetővé teszi a dolgozók az eszközök és alkalmazások, beleértve a vállalati adatokhoz való hozzáférésük kezelését. A mobileszköz-felügyelet (MDM) szolgáltatás használatához, az eszközöket először regisztrálni kell az Intune-ban. Az eszközök regisztrálásakor azok egy MDM-tanúsítványt kapnak. Ez a tanúsítvány az Intune szolgáltatással való kommunikációra szolgál. 

    A munkaerő-eszközök regisztrálása az Intune-ban többféle módszer áll rendelkezésre. Az egyes módszerek az eszköz tulajdonosától (személyes vagy céges), az eszköztípustól (iOS, Windows, Android) és a felügyeleti követelményektől (alaphelyzetbe állítások, affinitás, zárolás) függ. Azonban eszközregisztráció engedélyezése előtt be kell állítania az Intune-infrastruktúrát. Különösen fontos, hogy az eszközregisztrációhoz szükség van [saját MDM-szolgáltató beállítására](mdm-authority-set.md). Felkészülés az Intune-környezet (bérlő) kapcsolatos további információkért lásd: [beállítása az Intune-ban](setup-steps.md). Miután készen áll az Intune-bérlőjéhez, az eszközt regisztrálhat. További információt az eszközregisztrációról a [Mi az eszközregisztrálás?](device-enrollment.md) című témakörben találhat

3. A [Intune](https://aka.ms/intuneportal)válassza **eszközmegfelelőség** az Intune által felügyelt eszközök megfelelőségi adatainak megjelenítéséhez. Látni fogja, az alábbi képhez hasonló részleteit.

    ![Az eszköz megfelelőségi panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-03.png)
    
    Megfelelőségi követelmények lényegében szabályok; például az eszköz PIN-KÓDJÁNAK igénylő vagy az eszköztitkosítás megkövetelése. Az eszközmegfelelőségi szabályzatok definiálása a szabályokat és beállításokat, amelyek az eszközök megfelelőségéhez kell követnie. Eszközmegfelelőség használatához meg kell rendelkeznie:
    - Az Intune-ra és az Azure Active Directory (Azure AD) Premium előfizetéssel
    - Eszközök támogatott platformmal működik
    - Eszközöket regisztrálni kell az Intune-ban
    - Egy felhasználó vagy az elsődleges felhasználóval nem regisztrált eszközökön.
    
    További információkért lásd: [az Intune eszközmegfelelőségi szabályzatai – első lépések](device-compliance-get-started.md).

4. A [Intune](https://aka.ms/intuneportal)válassza **eszközkonfiguráció** az Intune-ban eszközprofilok részleteit jeleníti meg. 

    ![Az eszköz konfigurációs panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-04.png)
    
    Az Intune olyan beállításokat és funkciókat kínál, amelyeket Ön engedélyezhet vagy letilthat a vállalatához tartozó különböző eszközökön. Ezek a beállítások és funkciók "profilok" kerülnek. A különböző eszközökre és a különböző platformokon, beleértve az iOS, Android és Windows profilokat hozhat létre. Ezt követően az Intune segítségével a szervezet a profil-eszközökre vonatkoznak.   

    Eszköz konfigurálásával kapcsolatos további információkért lásd: [funkciók beállítások alkalmazásához az eszközök Microsoft Intune-ban eszközprofilok segítségével](device-profiles.md).

5. A [Intune](https://aka.ms/intuneportal)válassza **eszközök** részleteit az Intune bérlői a regisztrált eszközökre. Egy új Intune-ban bejegyzési rendszertől, ha még nem fog a regisztrált eszközöket. 

    ![Az eszköz regisztrációs panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-05.png)
    
    A **eszközök** ablaktáblája tartalmaz a bérlő adatait a regisztrált eszközökre. Kattinthat **minden eszköz** az eszközök listáját jeleníti meg az Intune-bérlőhöz. 

6. A [Intune](https://aka.ms/intuneportal), jelölje be **ügyfélalkalmazás** alkalmazás telepítési állapotának megjelenítéséhez.

    ![Az ügyfél alkalmazások panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-06.png)
    
    A rendszergazdák a Microsoft Intune használatával kezelhetik a cég által használt ügyfélalkalmazásokat. Ez a funkció az eszközkezelési és adatvédelmi funkciókat egészíti ki. A rendszergazdák egyik elsődleges feladata annak biztosítása, hogy a végfelhasználók hozzáférjenek a munkájukhoz szükséges alkalmazásokhoz. Emellett előfordulhat, hogy az Intune-ban nem regisztrált eszközökön található alkalmazásokat is szeretne hozzárendelni és felügyelni. Az Intune számos szolgáltatást kínál a szükséges alkalmazások kívánt eszközökön való használatához. Hozzáadásával és alkalmazások hozzárendelésével kapcsolatos további információkért lásd: [alkalmazások hozzáadása Microsoft Intune-bA](apps-add.md) és [alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal](apps-deploy.md).

7. A [Intune](https://aka.ms/intuneportal)válassza **feltételes hozzáférési** hozzáférési házirendek részleteit jeleníti meg.

    ![A feltételes hozzáférési panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-07.png)

    A feltétles hozzáférés azokat a módszereket jelenti, amelyekkel vezérelheti az e-mail-fiókjához és a céges erőforrásaihoz való eszköz- és alkalmazás-hozzáférést. További tudnivalók: eszközalapú és alkalmazásalapú feltételes hozzáférés, és keresse meg a gyakori forgatókönyvek a feltételes hozzáférés használata az Intune-nal: [Mi a feltételes hozzáférés?](conditional-access.md)

8. A [Intune](https://aka.ms/intuneportal)válassza **felhasználók** a felhasználók az Intune-ban szereplő részleteit jeleníti meg. Ezek a felhasználók a cég munkatársának kell lennie. 
 
    ![Képernyőkép a felhasználók panelről](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-08.png)

    Felhasználók hozzáadása az Intune közvetlenül, vagy a felhasználók a helyszíni Active Directoryból szinkronizál. Ha felvették a felhasználókat a szolgáltatásba, regisztrálhatják az eszközeiket, és elérhetik a vállalati erőforrásokat. Meg is adhat a felhasználóknak további engedélyeket az eléréséhez az Intune-ban. További információkért lásd: [felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-ban](users-add.md).

9. A [Intune](https://aka.ms/intuneportal)válassza **csoportok** az Azure Active Directory (Azure AD) csoportok az Intune-ban szereplő részleteit jeleníti meg. Intune rendszergazdaként csoport használatával kezelheti az eszközöket és felhasználókat. 

    ![A csoportok panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-09.png)

    Csoportokat állíthat a szervezet igényeinek. Létrehozhat csoportokat a felhasználók és eszközök földrajzi hely, részleg vagy hardverjellemzők szerinti rendezéséhez. Használjon csoportokat a feladatok nagy számban való végrehajtásához. Például sok felhasználó házirendjeinek beállítása vagy alkalmazások telepítése az eszközök. Csoportokkal kapcsolatos további információkért lásd: [adja hozzá a felhasználók és eszközök rendszerezéséhez csoportok](groups-add.md).

10. A [Intune](https://aka.ms/intuneportal)válassza **Súgó és támogatás** kérelem súgójában. Rendszergazdaként, használhatja a **Súgó és támogatás** keresheti ki és megoldások, megtekintése, valamint egy online támogatási jegy fájlt az Intune-hoz lehetőséget. 

    ![A Súgó és támogatás panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-10.png)

    Hozzon létre egy támogatási jegyet, hogy a fiók az Azure Active Directory rendszergazdai szerepköréhez kell hozzárendelni. Adja meg rendszergazdai szerepköröket, **Intune-rendszergazda**, **globális rendszergazdai**, és **szolgáltatás-rendszergazda**. További információkért lásd: [hogyan kérhet támogatást a Microsoft Intune](get-support.md).

11. A [Intune](https://aka.ms/intuneportal)válassza **Bérlőállapot** az Intune-bérlő részleteit jeleníti meg.

    ![A bérlő állapotának panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-11.png)

    Bérlői állapot részletei tartalmazzák összekötő állapota, az Intune szolgáltatás állapota és az Intune híreket. Bármilyen probléma merül fel a bérlőhöz vagy az Intune önmagában, a részleteket megtalálja a **Bérlőállapot** ablaktáblán. További információkért lásd: [Intune-bérlő állapotát](tenant-status.md).

12. A [Intune](https://aka.ms/intuneportal)válassza **hibaelhárítás** elérni egy parancsikont a hibaelhárítási tippek, támogatás kéréséhez vagy az Intune állapotának ellenőrzése. Ez az információ csak az Intune-felhasználó választja.

    ![A hibaelhárítás panel képernyőképe](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-12.png)

Intune-ban hibaelhárítással kapcsolatos további információkért lásd: [a céges felhasználóknak a hibaelhárítási portál használatával](help-desk-operators.md).

## <a name="configure-the-azure-portal"></a>Az Azure portál konfigurálása

Az Azure lehetővé teszi, hogy a nézet a portál konfigurálása és testreszabását.

### <a name="change-the-sidebar"></a>Az oldalsáv módosítása

Az Azure Portal bal oldalán található **oldalsáv** megjeleníti az összes rendelkezésre álló Azure-szolgáltatást tartalmazó listát. Ennek az átfogó listának az alapértelmezett nézetét módosíthatja, hogy egy állandó nézetet hozzon létre azokból a szolgáltatásokból, amelyek az Ön számára a legfontosabbak. Az alábbiakban példaszolgáltatásként az Intune-t fogjuk felvenni a lista tetejére.

![Egy felhasználó a Microsoft Intune-t keresi a „További szolgáltatások” listában.](./media/azure-add-intune1.png)

1. Válassza a lap bal oldalán lévő oldalsávon a **Minden szolgáltatás** hivatkozást.
2. Keressen az **Intune** kifejezésre a szűrőmezőben.
3. Kattintson a **csillagra**, amivel felveszi az Intune-t a kedvenc szolgáltatásai listájának az aljára.
4. Mutasson az Intune szolgáltatásra. Jelölje ki és húzza át az Intune-t a szolgáltatás nevének jobb oldalán található **három függőleges ponttal**.

### <a name="change-the-dashboard"></a>Az irányítópult módosítása

Az alapértelmezett kezdőlap az **irányítópult**. Ezen a lapon szabhatja személyre a csempéket az Ön számára legfontosabb információk megjelenítéséhez.

![Az általános új irányítópult képe. Az oldalsáv látható az összes szolgáltatással a bal oldalon, a fő irányítópult pedig középen. Az irányítópult módosítógombjai felül vannak, valamint csempék láthatók, amelyekkel elérhető az összes erőforrás, a gyorsútmutatók, a szolgáltatásállapot és az Azure-piactér.](./media/azure-default-dashboard.png)

A jelenlegi irányítópult módosításához válassz az **Irányítópult szerkesztése** gombot. Ha nem szeretné módosítani az alapértelmezett irányítópultot, létrehozhat egy **új irányítópultot** is. Új irányítópult létrehozásakor egy üres saját irányítópultot kap **Csempetárral**, amelyen új csempéket vehet fel és átrendezheti a csempéket. Csempéket találhat **általános** kategóriájuk, **típusuk** segítségével, **kereséssel** és **erőforráscsoportjuk** vagy **címkéjük** alapján.

Ezeken kívül felvehet csempéket az irányítópultra bármely **három pont** gombbal, ha a **Rögzítés az irányítópulton** lehetőséget választja.

![A Felhasználók és csoportok > Minden csoport hely közelképe az Intune-ban, amelyen látszik a „Rögzítés az irányítópulton” menüpont a csoport jobb szélén.](./media/azure-pin-to-dashboard.png)

Ez a funkció relevánsabb lesz, miután további tartalmakat is hozzáadott az Intune-hoz, például csoportokat és felhasználókat.

## <a name="next-steps"></a>További lépések

Az első futtat gyorsan a Microsoft Intune-végighaladhat az Intune rövid útmutatók első beállítása egy ingyenes Intune-fiók.

> [!div class="nextstepaction"]
> [Gyors útmutató: A Microsoft Intune ingyenes kipróbálása](free-trial-sign-up.md)


