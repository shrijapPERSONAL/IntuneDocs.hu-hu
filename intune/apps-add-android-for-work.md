---
title: Felügyelt Google Play-alkalmazások hozzárendelése Android enterprise-eszközök
titlesuffix: Microsoft Intune
description: Megtudhatja, hogyan szinkronizálhatja és alkalmazások hozzárendelése Android enterprise-eszközöket a felügyelt Google Play áruházból.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/25/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: ee9e72b727f5634721cf3a45c918aeee44e83309
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55072473"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Felügyelt Google Play-alkalmazások hozzáadása az Intune-nal vállalati Android-eszköz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android enterprise Android munkahelyi profilos eszközök, dedikált/kioszkok, a programot, és teljes körűen felügyelt eszközökre. Androidos munkahelyi profilos eszközök esetén a vállalati Android olyan funkciókat jelent, amelyekkel elkülöníthetőek a személyes alkalmazások és adatok a munkahelyi alkalmazásoktól és adatoktól. A vállalati Android további felügyeleti lehetőségeket és adatvédelmet biztosít, amikor a felhasználók Android-eszközt használnak munkavégzésre. Az Intune-nal úgy telepítheti az alkalmazásokat és a beállításokat az androidos munkahelyi profilos eszközökre, hogy elkülöníti egymástól a munkához kapcsolódó és a személyes adatokat. Minden olyan alkalmazás, amelyet az androidos munkahelyi profilos eszközökön telepít, a felügyelt Google Play áruházból szerezhető be. Az alkalmazások androidos munkahelyi profilos eszközökhöz való hozzárendelése eltér a hagyományos androidos eszközökhöz való hozzárendeléstől. Jelentkezzen be az áruházba, keresse meg a kívánt alkalmazásokat, majd hagyja jóvá a választást. Az alkalmazás megjelenik az Azure Portal **Licencelt alkalmazások** lapján, és a hozzárendelése ugyanúgy kezelhető, mint bármely más alkalmazásé.

Ha saját üzletági (LOB) alkalmazásokat hozott létre, azok hozzárendelését is elvégezheti az alábbiak szerint:
- Hozzon létre egy Google Developer-fiókot, amellyel saját területen tehet közzé alkalmazásokat a Google Play Áruházban.
- Szinkronizálja az alkalmazásokat az Intune-nal.

## <a name="before-you-start"></a>Előkészületek

Fontos, hogy az Intune-t és az androidos munkahelyi profilokat beállítsa a közös munkára az Azure Portal **Eszközök regisztrálása** területén. További információ: [Android-eszközök regisztrálása](android-work-profile-enroll.md).

## <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Felügyelt Google Play áruházbeli alkalmazások szinkronizálása

1. Keresse fel a [Felügyelt Google Play áruházat](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és a vállalati Android közötti kapcsolatot.
2. Az áruházban keresse meg és válassza ki az Intune-nal hozzárendelendő alkalmazást.
3. Az alkalmazást megjelenítő oldalon válassza a **Jóváhagyás** lehetőséget.  
    A következő példákban a Microsoft Excel alkalmazás van kiválasztva.

    ![A Jóváhagyás gomb a Felügyelt Google Play áruházban](media/approve.png)
    
   Ekkor megjelenik egy ablak, amelyben az alkalmazás engedélyt kér bizonyos műveletek végrehajtására. 

4. Az engedélyek elfogadásához és a folytatáshoz válassza a **Jóváhagyás** lehetőséget.

    ![Jóváhagyás gomb az alkalmazásengedélyekhez](media/approve-app-permissions.png)

5. Adja meg, hogyan szeretné kezelni az új alkalmazásengedély-kérelmeket, majd válassza a **Mentés** lehetőséget.

    ![Új alkalmazásengedély-kérelmek kezelési lehetőségei](media/approve-app-settings.png)

    A jóváhagyás megtörténik, és az alkalmazás megjelenik a rendszergazdai konzolon. Ezt követően [szinkronizálhatja az androidos munkahelyi profilos alkalmazást az Intune-nal](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune). 

## <a name="sync-a-managed-google-play-app-with-intune"></a>Felügyelt Google Play áruházbeli alkalmazás szinkronizálása az Intune-nal

Ha jóváhagyott egy áruházból beszerzett alkalmazást, de nem látja az **Ügyfélalkalmazások** munkaterület **Licencelt alkalmazások** csomópontjában, az alábbi lépésekkel kényszerítheti az azonnali szinkronizálást:

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** munkaterületen a **Beállítások** alatt válassza a **Felügyelt Google Play** lehetőséget.
5. A **Felügyelt Google Play** panelen válassza a **Frissítés** lehetőséget.  
    A lapon frissül az utolsó szinkronizálás időpontja és állapota.
6. Az **Ügyfélalkalmazások** munkaterületen válassza az **Alkalmazások** lehetőséget.  
    Megjelenik az elérhetővé vált Felügyelt Google Play-alkalmazás.

Ha az alkalmazás megjelenik az **Ügyfélalkalmazások** munkaterület paneljének **Alkalmazáslicencek** csomópontjában, [ugyanúgy hozzárendelheti, mint bármelyik alkalmazást](/intune-azure/manage-apps/deploy-apps). Az alkalmazásokat úgy is hozzá lehet rendelni, hogy csak bizonyos felhasználói csoportokat érjenek el.

A hozzárendelés után az alkalmazás rendelkezésre áll a célzott eszközökön. A rendszer nem kér telepítési jóváhagyást az eszköz felhasználójától.

## <a name="manage-android-enterprise-app-permissions"></a>Vállalati androidos alkalmazások engedélyeinek kezelése
A vállalati Android használatához jóvá kell hagynia az alkalmazásokat a felügyelt Google Play webkonzolon, mielőtt az Intune-ba szinkronizálná és a felhasználókhoz hozzárendelné azokat. Mivel a vállalati Android lehetővé teszi az alkalmazások automatikus és csendes leküldését a felhasználói eszközökre, az alkalmazások által kért engedélyeket el kell fogadnia az összes felhasználó nevében. A végfelhasználóknak az alkalmazások telepítésénél nem jelennek meg alkalmazásengedélyek, ezért fontos, hogy Ön megértse ezeket az engedélyeket.

Ha az alkalmazás fejlesztője megváltozott engedélyekkel rendelkező új alkalmazásverziót tesz közzé, az új engedélyek nem lesznek automatikusan elfogadva akkor sem, ha Ön az előző verzió engedélykéréseit elfogadta. Az alkalmazás korábbi verzióját futtató eszközök továbbra is használhatják az alkalmazást. Az alkalmazás frissítése azonban nem történik meg, amíg el nem fogadja az új engedélyeket. Az alkalmazással még nem rendelkező eszközökre az új engedélyek elfogadásáig nem telepíthető az alkalmazás.

### <a name="update-app-permissions"></a>Alkalmazásengedélyek frissítése

Ellenőrizze rendszeresen a felügyelt Google Play-konzolon az új alkalmazásengedélyeket. Beállíthatja, hogy a Google Play e-mailt küldjön Önnek vagy másoknak, ha új engedélyekre van szükség egy jóváhagyott alkalmazáshoz. Ha egy alkalmazás a hozzárendelése után sincs telepítve az eszközökön, az alábbiak alapján ellenőrizheti, hogy vannak-e új alkalmazásengedélyek:

1. Nyissa meg a [Google Play Áruházat](https://play.google.com/work).
2. Jelentkezzen be azzal a Google-fiókkal, amelyet az alkalmazások közzétételénél és jóváhagyásánál használt.
3. Válassza a **Frissítések** lapot és ellenőrizze, hogy van-e frissítést igénylő alkalmazás.  
    A listában szereplő összes alkalmazás új engedélyeket kér, és a hozzárendelés addig nem lehetséges, amíg az engedélyeket meg nem adják.

Alternatív megoldásként beállíthatja, hogy a Google Play alkalmazásalapon automatikusan végezze el az engedélyek ismételt megadását. 

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>A felügyelt Google Play áruházból származó üzletági alkalmazások használata

1. Ugyanazzal a fiókkal jelentkezzen be a [Google Play fejlesztői konzolján](https://play.google.com/apps/publish), amellyel beállította az Intune és a vállalati Android közötti kapcsolatot.  
    Az első bejelentkezés előtt regisztrálni kell, továbbá megfizetni a Google Developer-program regisztrációs díját.
2. A konzolon válassza az **Új alkalmazás hozzáadása** elemet.
3. Az alkalmazások és azok információinak feltöltése ugyanúgy történik, mint bármelyik alkalmazás közzététele a Google Play áruházban. Ugyanakkor ki kell választani **Az alkalmazás elérhetővé tétele csak a saját cég tagjai számára (<*cég neve*>)** lehetőséget.

    ![Az alkalmazás elérhetővé tétele csak a saját vállalat számára](media/restrict.png)

    Ez a művelet az alkalmazást csak a saját cége számára teszi elérhetővé. A nyilvános Google Play áruházban azonban nem lesz elérhető.

    Az androidos alkalmazások feltöltéséről és közzétételéről a [Google Play fejlesztői központ súgójában](https://support.google.com/googleplay/android-developer/answer/113469) talál további információt.
4. Az alkalmazás közzététele után ugyanazzal a fiókkal jelentkezzen be a [Felügyelt Google Play áruházba](https://play.google.com/work), amellyel beállította az Intune és a vállalati Android közötti kapcsolatot.
5. Az áruház **Alkalmazások** csomópontjában ellenőrizze, hogy megjelenik-e a közzétett alkalmazás.  
    Az alkalmazás automatikusan megkapja az engedélyt az Intune-nal való szinkronizálásra.

## <a name="delete-managed-google-play-apps"></a>Felügyelt Google Play-alkalmazások törlése 
Ha szükséges, törölheti a felügyelt Google Play-alkalmazások Microsoft Intune-ból. Felügyelt Google Play alkalmazás törléséhez nyissa meg a Microsoft Intune az Azure Portalon, és válassza a **ügyfélalkalmazás** > **alkalmazások**. Az alkalmazás listában jelölje ki a három pontra (...) jobb oldalán a felügyelt Google Play-alkalmazást, majd válassza ki **törlése** a megjelenő listából. Ha egy felügyelt Google Play-alkalmazást töröl alkalmazásokat az alkalmazáslistából, a felügyelt Google Play alkalmazás automatikusan jóvá nem hagyott.

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md) 

