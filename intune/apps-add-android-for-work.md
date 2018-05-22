---
title: Alkalmazások hozzárendelése Android for Work-eszközökhöz
titlesuffix: Microsoft Intune
description: Az alábbi témakörből megtudhatja, hogyan végezheti el a Google Play for Work áruházból származó alkalmazások szinkronizálását és Android for Work-eszközökhöz való hozzárendelését.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 53a3374d285baf4035b071cc867b3c6d2dec423f
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2018
---
# <a name="assign-apps-to-android-for-work-devices-with-intune"></a>Alkalmazások hozzárendelése Android for Work-eszközökhöz az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Android for Work egy Android-eszközökhöz használható program. Minden olyan alkalmazás, amelyet az Android for Work-eszközökön telepít, a Google Play for Work áruházból szerezhető be. Az alkalmazások Android for Work-eszközökhöz való hozzárendelése eltér a hagyományos androidos eszközökhöz való hozzárendeléstől. Jelentkezzen be az áruházba, keresse meg a kívánt alkalmazásokat, majd hagyja jóvá a választást. Az alkalmazás megjelenik az Azure Portal **Licencelt alkalmazások** lapján, és a hozzárendelése ugyanúgy kezelhető, mint bármely más alkalmazásé.

Ha saját üzletági (LOB) alkalmazásokat hozott létre, azok hozzárendelését is elvégezheti az alábbiak szerint:
- Hozzon létre egy Google Developer-fiókot, amellyel saját területen tehet közzé alkalmazásokat a Google Play Áruházban.
- Szinkronizálja az alkalmazásokat az Intune-nal.

## <a name="before-you-start"></a>Előkészületek

Győződjön meg arról, hogy az Intune és az Android for Work szolgáltatást is beállította a közös munkára az Azure Portal **Eszközök regisztrálása** területén.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work áruházbeli alkalmazások szinkronizálása

1. Nyissa meg a [Google Play for Work áruházat](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
2. Az áruházban keresse meg és válassza ki az Intune-nal hozzárendelendő alkalmazást.
3. Az alkalmazást megjelenítő oldalon válassza a **Jóváhagyás** lehetőséget.  
    A következő példákban a Microsoft Excel alkalmazás van kiválasztva.

    ![A Jóváhagyás gomb a Google Play for Work Áruházban](media/approve.png)
    
   Ekkor megjelenik egy ablak, amelyben az alkalmazás engedélyt kér bizonyos műveletek végrehajtására. 

4. Az engedélyek elfogadásához és a folytatáshoz válassza a **Jóváhagyás** lehetőséget.

    ![Jóváhagyás gomb az alkalmazásengedélyekhez](media/approve-app-permissions.png)

5. Adja meg, hogyan szeretné kezelni az új alkalmazásengedély-kérelmeket, majd válassza a **Mentés** lehetőséget.

    ![Új alkalmazásengedély-kérelmek kezelési lehetőségei](media/approve-app-settings.png)

    A jóváhagyás megtörténik, és az alkalmazás megjelenik a rendszergazdai konzolon. Az után [szinkronizálhatja az Android for Work alkalmazást az Intune-nal](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Az Android for Work alkalmazás szinkronizálása az Intune-nal

Ha jóváhagyott egy áruházból beszerzett alkalmazást, de nem látja a **Mobilalkalmazások** munkaterület **Licencelt alkalmazások** csomópontjában, az alábbi lépésekkel kényszerítheti az azonnali szinkronizálást:

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** munkaterületen a **Beállítások** alatt válassza az **Android for Work** lehetőséget.
5. Az **Android for Work** panelen válassza a **Szinkronizálás** elemet.  
    A lapon frissül az utolsó szinkronizálás időpontja és állapota.
6. A **Mobilalkalmazások** munkaterületen válassza az **Alkalmazások** lehetőséget.  
    Megjelenik az újonnan elérhető Android for Work-alkalmazás.

Ha az alkalmazás megjelenik a **Mobilalkalmazások** munkaterület paneljének **Alkalmazáslicencek** csomópontjában, [ugyanúgy hozzárendelheti, mint bármelyik alkalmazást](/intune-azure/manage-apps/deploy-apps). Az alkalmazásokat úgy is hozzá lehet rendelni, hogy csak bizonyos felhasználói csoportokat érjenek el.

A hozzárendelés után az alkalmazás rendelkezésre áll a célzott eszközökön. A rendszer nem kér telepítési jóváhagyást az eszköz felhasználójától.

## <a name="manage-android-for-work-app-permissions"></a>Az Android for Work alkalmazásengedélyeinek felügyelete
Az Android for Work használatához jóvá kell hagynia az alkalmazásokat a felügyelt Google Play webkonzolon, mielőtt az Intune-ba szinkronizálná és a felhasználókhoz hozzárendelné azokat. Mivel az Android for Work lehetővé teszi az alkalmazások automatikus és csendes leküldését a felhasználói eszközökre, az alkalmazások által kért engedélyeket el kell fogadnia az összes felhasználó nevében. A végfelhasználóknak az alkalmazások telepítésénél nem jelennek meg alkalmazásengedélyek, ezért fontos, hogy Ön elolvassa és megértse ezeket az engedélyeket.

Ha az alkalmazás fejlesztője megváltozott engedélyekkel rendelkező új alkalmazásverziót tesz közzé, az új engedélyek nem lesznek automatikusan elfogadva akkor sem, ha Ön az előző verzió engedélykéréseit elfogadta. Az alkalmazás korábbi verzióját futtató eszközök továbbra is használhatják az alkalmazást. Az alkalmazás frissítése azonban nem történik meg, amíg el nem fogadja az új engedélyeket. Az alkalmazással még nem rendelkező eszközökre az új engedélyek elfogadásáig nem telepíthető az alkalmazás.

### <a name="update-app-permissions"></a>Alkalmazásengedélyek frissítése

Ellenőrizze rendszeresen a felügyelt Google Play-konzolon az új alkalmazásengedélyeket. Beállíthatja, hogy a Google Play e-mailt küldjön Önnek vagy másoknak, ha új engedélyekre van szükség egy jóváhagyott alkalmazáshoz. Ha egy alkalmazás a hozzárendelése után sincs telepítve az eszközökön, az alábbiak alapján ellenőrizheti, hogy vannak-e új alkalmazásengedélyek:

1. Nyissa meg a [Google Play Áruházat](http://play.google.com/work).
2. Jelentkezzen be azzal a Google-fiókkal, amelyet az alkalmazások közzétételénél és jóváhagyásánál használt.
3. Válassza a **Frissítések** lapot és ellenőrizze, hogy van-e frissítést igénylő alkalmazás.  
    A listában szereplő összes alkalmazás új engedélyeket kér, és a hozzárendelés addig nem lehetséges, amíg az engedélyeket meg nem adják.

Alternatív megoldásként beállíthatja, hogy a Google Play alkalmazásalapon automatikusan végezze el az engedélyek ismételt megadását. 

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work áruházból származó üzletági alkalmazások használata

1. Ugyanazzal a fiókkal jelentkezzen be a [Google Play fejlesztői konzolján](https://play.google.com/apps/publish), amellyel beállította az Intune és az Android for Work közötti kapcsolatot.  
    Az első bejelentkezés előtt regisztrálni kell, továbbá megfizetni a Google Developer-program regisztrációs díját.
2. A konzolon válassza az **Új alkalmazás hozzáadása** elemet.
3. Az alkalmazások és azok információinak feltöltése ugyanúgy történik, mint bármelyik alkalmazás közzététele a Google Play áruházban. Ugyanakkor ki kell választani **Az alkalmazás elérhetővé tétele csak a saját cég tagjai számára (<*cég neve*>)** lehetőséget.

    ![Az alkalmazás elérhetővé tétele csak a saját vállalat számára](media/restrict.png)

    Ez a művelet gondoskodik arról, hogy az alkalmazás csak a munkahelye számára legyen elérhető, a Google Play Áruház nyilvános területein ne.

    Az androidos alkalmazások feltöltéséről és közzétételéről a [Google Play fejlesztői központ súgójában](https://support.google.com/googleplay/android-developer/answer/113469) talál további információt.
4. Az alkalmazás közzététele után ugyanazzal a fiókkal jelentkezzen be a [Google Play for Work áruházba](https://play.google.com/work), amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
5. Az áruház **Alkalmazások** csomópontjában ellenőrizze, hogy megjelenik-e a közzétett alkalmazás.  
    Az alkalmazás automatikusan megkapja az engedélyt az Intune-nal való szinkronizálásra.

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md) 

