---
title: "MAM-szabályzatok létrehozása és telepítése"
description: "Az ebben a témakörben található részletes útmutatóval MAM-szabályzatokat hozhat létre és telepíthet."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93ec41c756c802986b85a45f53329ef6daba6c08
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a>Alkalmazásvédelmi szabályzatok létrehozása és telepítése a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör azt a folyamatot ismerteti, amellyel az **Azure Portalon** hozható létre alkalmazásvédelmi szabályzat. Az alkalmazásvédelmi szabályzatok létrehozására szolgáló új felügyeleti konzol az Azure Portal. Azt javasoljuk, hogy a továbbiakban ezen a portálon hozza létre az alkalmazásvédelmi szabályzatokat. Az Azure-portál a következő MAM-forgatókönyveket teszi lehetővé:

- Az Intune-ban regisztrált eszközök
- Külső MDM-megoldás által kezelt eszközök
- MDM-megoldással (BYOD) nem kezelt eszközök

>[!IMPORTANT]
Ha jelenleg az **Intune felügyeleti konzolt** használja eszközei kezeléséhez, vegye figyelembe az alábbiakat:

> * Az [Intune felügyeleti konzollal](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) létrehozhat olyan alkalmazásvédelmi szabályzatot, amely az Intune-ban regisztrált eszközökön futó alkalmazásokat támogatja.
> * Az Intune felügyeleti konzolon létrehozott alkalmazásvédelmi szabályzatokat nem lehet importálni az Azure Portalra.  Újra létre kell hozni az alkalmazásvédelmi szabályzatokat az Azure Portalon.

> * Előfordulhat, hogy az Intune felügyeleti konzolon nem látja az alkalmazásvédelmi szabályzatok minden beállítását. Az Azure Portal az alkalmazásvédelmi szabályzatok létrehozására szolgáló új felügyeleti konzol.

> * Felügyelt alkalmazások telepítéséhez létre kell hoznia egy alkalmazásvédelmi szabályzatot az Intune felügyeleti konzolon. Ebben az esetben érdemes lehet mind az Intune felügyeleti konzolon, mind az Azure Portalon létrehozni alkalmazásvédelmi szabályzatokat. Az Intune felügyeleti konzol szabályzataival gondoskodhat róla, hogy tudja telepíteni a felügyelt alkalmazást, az Azure Portal pedig az új felügyeleti konzol, ahol az alkalmazásvédelmi szabályzatok minden beállítását megadhatja.

> * Ha az Intune felügyeleti konzolon és az Azure Portalon is létrehoz alkalmazásvédelmi szabályzatokat, a rendszer az Azure Portalon létrehozott szabályzatot érvényesíti az alkalmazásokra.

Az Android és az iOS platformokon támogatott szabályzatbeállítások listájának megtekintéséhez válasszon a következő lehetőségek közül:

> [!div class="op_single_selector"]
- [iOS-szabályzatok](ios-mam-policy-settings.md)
- [Android-szabályzatok](android-mam-policy-settings.md)

- Az alkalmazásvédelmi szabályzatok működését és az Intune alkalmazásvédelmi szabályzataival kezelhető típushelyzeteket [az alkalmazások adatainak az alkalmazásvédelmi szabályzatokkal való védelmét ismertető cikk](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) mutatja be részletesen.

##  <a name="create-an-app-protection-policy"></a>Alkalmazásvédelmi szabályzat létrehozása
Alkalmazásvédelmi szabályzatokat az Azure Portalon lehet létrehozni. Ha első alkalommal használja az Azure Portalt, az [Azure Portal a Microsoft Intune alkalmazásvédelmi szabályzatainak kezeléséhez](azure-portal-for-microsoft-intune-mam-policies.md) című témakörből ismerkedhet meg vele. Alkalmazásvédelmi szabályzat létrehozása előtt olvassa el [az előfeltételekre és a támogatásra](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) vonatkozó információkat.

Az alábbi lépésekkel hozhat létre alkalmazásvédelmi szabályzatokat:

1. Nyissa meg az [Azure Portal](https://portal.azure.com) webhelyet, és adja meg hitelesítő adatait.

2. Válassza a **További szolgáltatások** lehetőséget, majd írja be az Intune kifejezést.

3. Válassza az **Intune alkalmazásvédelem** lehetőséget.

4. Válassza az **Intune mobilalkalmazás-felügyelet &gt; Beállítások** elemet a **Minden beállítás** panel megnyitásához.

    ![Az Intune mobilalkalmazás-felügyelet panel képernyőfelvétele](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  A **Beállítások** panelen válassza az **Alkalmazásszabályzat** elemet. Ekkor megnyílik a **Alkalmazásszabályzat** panel, amelyen új szabályzatokat hozhat létre, és szerkesztheti a meglévő szabályzatokat. Válassza a **Szabályzat hozzáadása** elemet.

    ![A kijelölt Szabályzat hozzáadása menüpont az Alkalmazásszabályzat panelen – képernyőfelvétel ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  Írja be a szabályzat nevét, adjon meg egy rövid leírást, és válassza ki platform típusát az iOS- vagy Android-alapú szabályzat létrehozásához. Az egyes platformokon egynél több szabályzatot is beállíthat.

    ![Képernyőfelvétel a Szabályzat hozzáadása panelről](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  Válassza az **Alkalmazások** elemet az **Alkalmazások panel** megnyitásához, ahol megjelenik a rendelkezésre álló alkalmazások listája. Egy vagy több alkalmazást is kijelölhet a listában a létrehozott szabályzattal való társításra. Ha kiválasztotta az alkalmazásokat, mentse őket az **Alkalmazások** panel alján található **Kiválasztás** gombbal.

    > [!IMPORTANT]
    > Legalább egy alkalmazást ki kell jelölnie a szabályzat létrehozásához.

5.  A **Szabályzat hozzáadása** panelen kattintson a **Kötelező beállítások konfigurálása** elemre a szabályzatbeállítási panel megnyitásához.

    A szabályzatbeállításoknak két kategóriájuk van, az **Adatáthelyezés** és a **Hozzáférés**.  Az adatáthelyezési szabályzatok az alkalmazások mindkét irányú adatátvitelére vonatkoznak. A hozzáférési szabályzatok meghatározzák, hogyan érheti el a végfelhasználó az alkalmazásokat munkahelyi környezetben.
    Használatuk megkönnyítése érdekében a szabályzatbeállításoknak alapértelmezett értékük van. Nem szükséges változtatnia, ha az alapértelmezett értékek megfelelnek az elvárásainak.

    > [!TIP]
    > A szabályzat beállításai csak akkor lépnek érvénybe, ha munkahelyi környezetben használják az alkalmazásokat.  Amikor a végfelhasználó az alkalmazást személyes feladatra használja, nem vonatkoznak rá a szabályzatok.

    ![Képernyőfelvétel a Beállítások panelről és a Szabályzat hozzáadása panelről](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Szabályzat hozzáadása** panelbe. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.

    ![A megadott alkalmazások és a beállítások a Szabályzat hozzáadása panelen – képernyőfelvétel](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

Ha az előző eljárásban leírtak szerint hozta létre a szabályzatot, az a felhasználók számára ekkor még nincs telepítve. A szabályzatok életbe léptetéséről a következő, „Szabályzat telepítése a felhasználók számára” című szakasz nyújt tájékoztatást.

> [!IMPORTANT]
> Ha egy alkalmazáshoz létrehoz egy alkalmazásszabályzatot az Intune felügyeleti konzoljával, és az Azure Portalon is létrehoz egy alkalmazásszabályzatot hozzá, akkor az Azure Portalon létrehozott szabályzat élvez elsőbbséget. Az Intune vagy a Configuration Manager-konzol jelentéseiben azonban az Intune felügyeleti konzoljában létrehozott szabályzatbeállítások szerepelnek. Példa:
>
> -   Az Intune felügyeleti konzolján létrehozott egy alkalmazásszabályzatot, amely tiltja az alkalmazásból való másolást.
> -   Az Azure konzolján létrehozott egy alkalmazásszabályzatot, amely engedélyezi az alkalmazásból való másolást.
> -   Mindkét szabályzatot ugyanahhoz az alkalmazáshoz rendeli.
> -   Ennek eredményeképp az Azure-konzolon létrehozott szabályzat elsőbbséget kap, így a másolás engedélyezve lesz.
> -   Azonban az Intune-konzolon megjelenő állapot és jelentések szerint a másolás tiltott, ami nem felel meg a valóságnak.

## <a name="line-of-business-lob-apps-optional"></a>Üzletági (LOB) alkalmazások (nem kötelező)

Az Intune 1703-as verziójától kezdve az új alkalmazásvédelmi szabályzatok létrehozásakor általánosan fel lehet venni üzletági alkalmazásokat az Intune-ba. Így lehetőség nyílik arra is, hogy a MAM SDK-val alkalmazásvédelmi szabályzatokat definiáljon üzletági alkalmazásokhoz a teljes körű alkalmazástelepítési jogosultságok megkövetelése nélkül.
/intune/app-sdk-get-started
> [!TIP]
> Az [Intune App SDK](/intune/app-sdk-get-started) munkafolyamatán végighaladva is fel lehet venni üzletági alkalmazásokat az Intune-ba.

> [!IMPORTANT]
> Ha a felhasználóknak csak MAM-alkalmazások telepítésére van konkrét engedélyük, olyan teljes körű alkalmazástelepítési jogosultságuk viszont nincs, amellyel tetszőleges alkalmazást telepíthetnének az Intune-ba, akkor nem tudják végigkövetni az Intune SDK munkafolyamatát, de a MAM alkalmazásvédelmi szabályzatok létrehozására szolgáló munkafolyamatával felvehetik üzletági alkalmazásaikat.

### <a name="to-add-lob-apps-ios-and-android"></a>Üzletági alkalmazások felvétele (iOS és Android)

1.  A Házirend hozzáadása panelen az **Alkalmazások** konfigurálása elemet választva nyissa meg az Alkalmazások panelt.

    ![A MAM Házirend hozzáadása panele](../media/AppManagement/mam-lob-apps-1.png)

2.  Kattintson a **További alkalmazások** elemre, majd írja be a **Csomagazonosító** (iOS-en) vagy a **package ID** (Androidon) értékét, majd a Kiválasztás gombra kattintva adja meg az üzletági alkalmazásokat.

    ![A MAM További alkalmazások panele](../media/AppManagement/mam-lob-apps-2.png)

### <a name="to-add-lob-apps-windows"></a>Üzletági alkalmazások felvétele (Windows)

> [!IMPORTANT]
> Új alkalmazásvédelmi szabályzat létrehozásakor válassza a Windows 10 értéket a platformok listájából.

1.  A Házirend hozzáadása panelen az **Engedélyezett alkalmazások** vagy a **Mentesített alkalmazások** lehetőséget választva nyissa meg az Engedélyezett vagy a Mentesített alkalmazások panelt.

    > [!NOTE]
    >
    - **Engedélyezett alkalmazások:** ezeknek be kell tartaniuk az adott szabályzatot.
    - **Mentesített alkalmazások:** ezek mentesülnek az adott szabályzat alól, és korlátozás nélkül hozzáférnek a vállalati adatokhoz.
<br></br>
2. Az Engedélyezett vagy a Mentesített alkalmazások panelen válassza az **Alkalmazások felvétele** lehetőséget. Felveheti a Microsoft ajánlott alkalmazásait, áruházbeli és asztali alkalmazásokat.

    a.  **Ajánlott alkalmazások:** a szabályzatba egyszerűen importálható (leginkább Office-) alkalmazásokból előre összeállított lista.

    b.  **Áruházbeli alkalmazások:** a rendszergazda a Windows Áruházból bármilyen alkalmazást felvehet a szabályzatba.

    c.  **Asztali Windows-alkalmazások:** a rendszergazda bármilyen hagyományos asztali Windows-alkalmazást (exe, dll stb.) felvehet a szabályzatba.

## <a name="deploy-a-policy-to-users"></a>Szabályzat telepítése a felhasználók számára

1.  A **Szabályzat** panelen válassza a **Felhasználói csoportok** elemet a **Felhasználói csoportok** panel megnyitásához. Válassza a **Felhasználói csoport hozzáadása** elemet a **Felhasználói csoportok** panelen a **Felhasználói csoport hozzáadása** panel megnyitásához.

    ![A kijelölt Felhasználói csoport hozzáadása menüpont a Felhasználói csoportok panelen – képernyőfelvétel](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  A **Felhasználói csoport hozzáadása** panelen megjelenik a felhasználói csoportok listája. Ezen a listán az **Azure Active Directory**összes biztonsági csoportja szerepel. Válassza ki azokat a felhasználói csoportokat, amelyekhez hozzá szeretné rendelni a szabályzatot, és válassza a **Kiválasztás** elemet. A **Kiválasztás** elem választásával telepítheti a szabályzatot a felhasználók számára.

    ![Az Azure Active Directory-felhasználók listája a Felhasználói csoportok hozzáadása panelen – képernyőfelvétel](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    A szabályzat ezzel létrejött, és telepítve lett a felhasználók számára.

A szabályzat csak az Intune-licenccel rendelkező felhasználókra érvényes. A kijelölt biztonsági csoport Intune-licenccel nem rendelkező felhasználóira nem vonatkozik a szabályzat.

>[!IMPORTANT]
> Ha az Intune-ban és a Configuration Managerben kezeli az iOS- és Android-eszközöket, a szabályzatok csak a közvetlenül kijelölt csoport felhasználói esetében lépnek érvénybe. A csoportba ágyazott alárendelt csoportok tagjaira nem vonatkozik a szabályzat.

A végfelhasználók az App Store-ból vagy a Google Play áruházból tölthetik le az alkalmazásokat. További információkért lásd:
* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](/intune/end-user-mam-apps-android)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](/intune/end-user-mam-apps-ios)

##  <a name="change-existing-policies"></a>A meglévő szabályzatok módosítása
A meglévő szabályzatokat szerkesztheti, és alkalmazhatja azokat a megcélzott felhasználókra. Ha azonban a meglévő szabályzatok módosításakor a felhasználók már be voltak jelentkezve az alkalmazásokba, csak egy 8 órás időszak elteltével láthatják a változtatásokat.

A változtatások hatásának megfigyeléséhez a felhasználónak ki kell jelentkeznie az alkalmazásból, majd újból be kell jelentkeznie.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>A szabályzathoz társított alkalmazások listájának módosítása

1.  Az **Alkalmazásszabályzat** panelen válassza ki a módosítani kívánt szabályzatot. Ekkor megnyílik a kiválasztott szabályzat tulajdonságait tartalmazó panel.

    ![Képernyőfelvétel egy külön panelen megnyitott meglévő szabályzatról](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  A szabályzat paneljén válassza a **Megcélzott alkalmazások** elemet az alkalmazások listájának megnyitásához.

3.  A listában eltávolíthat vagy hozzáadhat alkalmazásokat, és a **Mentés** ikont választva mentheti a módosításokat.

### <a name="to-change-the-list-of-user-groups"></a>A felhasználói csoportok listájának módosítása

1.  Az **Alkalmazásszabályzat** panelen válassza ki a módosítani kívánt szabályzatot. Ekkor megnyílik a kiválasztott szabályzat tulajdonságait tartalmazó panel.

2.  A szabályzat paneljén válassza a **Felhasználói csoportok** elemet a **Felhasználói csoport** panel megnyitásához. Itt láthatja azokat a felhasználói csoportokat, amelyekre érvényes a szabályzat.

3.  Ha a szabályzathoz új felhasználói csoportot szeretne felvenni, válassza a **Felhasználói csoport hozzáadása** elemet, és válasszon felhasználói csoportot. Válassza a **Kiválasztás** elemet, ha telepíteni szeretné a szabályzatot a kiválasztott csoport számára.

    ![Két kijelölt felhasználócsoport a Felhasználói csoport hozzáadása panelen – képernyőfelvétel](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  Ha törölni szeretne egy felhasználócsoportot, jelölje ki. Ezután válassza a három pontot (...), végül a **Törlés** elemmel törölje a felhasználócsoportot.

    ![A Törlés elemet ábrázoló képernyőfelvétel ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a>A szabályzatbeállítások módosítása

1.  Az **Alkalmazásszabályzat** panelen válassza ki a módosítani kívánt szabályzatot. Ekkor megnyílik a kiválasztott szabályzat tulajdonságait tartalmazó panel.

    ![Képernyőfelvétel egy külön panelen megnyitott meglévő szabályzatról ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Válassza a **Szabályzatbeállítások** elemet a **Szabályzatbeállítások** panel megnyitásához.

3.  Módosítsa a beállításokat, majd mentse a változtatásokat a **Mentés** ikonnal.

    ![A mentési menüparancs a Szabályzatbeállítások panelen – képernyőfelvétel](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a>Szabályzatbeállítások
Az iOS és az Android szabályzatbeállításait tartalmazó lista megtekintéséhez válasszon a következő lehetőségek közül:

> [!div class="op_single_selector"]
- [iOS-szabályzatok](ios-mam-policy-settings.md)
- [Android-szabályzatok](android-mam-policy-settings.md)

## <a name="next-steps"></a>További lépések
[A megfelelőség és a felhasználói állapot figyelése](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a>További információ
* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](/intune/end-user-mam-apps-android)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](/intune/end-user-mam-apps-ios)
