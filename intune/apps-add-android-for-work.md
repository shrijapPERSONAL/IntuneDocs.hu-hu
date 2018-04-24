---
title: Alkalmazások hozzárendelése Android for Work-eszközökhöz
titlesuffix: Microsoft Intune
description: Az alábbi témakörből megtudhatja, hogyan végezheti el a Google Play for Work áruházból származó alkalmazások szinkronizálását és Android for Work-eszközökhöz való hozzárendelését.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4168f78bff8937ca403cdb75b1028954cbbebd6f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Alkalmazások hozzárendelése Android for Work-eszközökhöz az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Android for Work egy Android-eszközökhöz használható program. Minden olyan alkalmazás, amelyet az Android for Work-eszközökön telepít, a Google Play for Work áruházból szerezhető be. Az alkalmazások Android for Work-eszközökhöz való hozzárendelése eltér a hagyományos androidos eszközökhöz való hozzárendeléstől. Jelentkezzen be az áruházba, keresse meg a kívánt alkalmazásokat, majd hagyja jóvá a választást. Az alkalmazás ezt követően a **Licencelt alkalmazások** csomópontban jelenik meg az Azure Portal webhelyen. Ezen a felületen kezelheti az alkalmazások hozzárendelését, ami ugyanúgy zajlik, mint a hagyományos alkalmazásoknál.

Ha saját üzletági (LOB) alkalmazásokat hozott létre, azok hozzárendelését is elvégezheti az alábbiak szerint:
- Hozzon létre egy Google Developer-fiókot, amellyel saját területen tehet közzé alkalmazásokat a Google Play Áruházban.
- Szinkronizálja az alkalmazásokat az Intune-nal.

## <a name="before-you-start"></a>Előkészületek

Győződjön meg arról, hogy az Intune és az Android for Work szolgáltatást is beállította a közös munkára az Azure Portal **Eszközök regisztrálása** területén.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work áruházbeli alkalmazások szinkronizálása

1. Nyissa meg a [Google Play for Work áruházat](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
2. Az áruházban keresse meg és válassza ki az Intune-nal hozzárendelendő alkalmazást.
3. Az alkalmazást megjelenítő lapon válassza a **Jóváhagyás** lehetőséget. A következő példákban a Microsoft Excel alkalmazás van kiválasztva.</br>

    ![Példa – Alkalmazás jóváhagyása a Google Play for Work Áruházban](media/approve.png)</br>
    
   Ekkor megjelenik egy ablak, amelyben az alkalmazás engedélyt kér bizonyos műveletek végrehajtására. 

4. Az engedélyek elfogadásához és a folytatáshoz válassza a **Jóváhagyás** lehetőséget.</br>

    ![Példa – Alkalmazásengedélyek jóváhagyása](media/approve-app-permissions.png)

5. Adja meg, hogyan szeretné kezelni az új alkalmazásengedély-kérelmeket. Ezt követően válassza a **Mentés** lehetőséget az új alkalmazásengedély-kérelmek kezelési módjának mentéséhez.</br>

    ![Példa – Új alkalmazásengedély-kérelmek mentése](media/approve-app-settings.png)</br>

    A jóváhagyás megtörténik, és az alkalmazás megjelenik a rendszergazdai konzolon. Mostantól [szinkronizálhatja az Android for Work alkalmazást az Intune-nal](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Az Android for Work alkalmazás szinkronizálása az Intune-nal

Ha jóváhagyott egy áruházból beszerzett alkalmazást, de nem látja a **Mobilalkalmazások** munkaterület **Licencelt alkalmazások** csomópontjában, az alábbi lépésekkel kényszerítheti az azonnali szinkronizálást:

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** terület **Beállítás** szakaszában válassza az **Android for Work** lehetőséget.
5. Az Android for Work panelen válassza a **Szinkronizálás** elemet. A lapon frissül az utolsó szinkronizálás időpontja és állapota.
6. A **Mobilalkalmazások** területen válassza az **Alkalmazások** lehetőséget az újonnan elérhető Android for Work-alkalmazás megjelenítéséhez.

Ha az alkalmazás megjelenik a **Mobilalkalmazások** munkaterület **Alkalmazáslicencek** csomópontjában, [ugyanúgy hozzárendelheti, mint bármelyik alkalmazást](/intune-azure/manage-apps/deploy-apps). Az alkalmazásokat úgy is hozzá lehet rendelni, hogy csak bizonyos felhasználói csoportokat érjenek el.

A hozzárendelés után az alkalmazás rendelkezésre áll a célzott eszközökön. A rendszer nem kér telepítési jóváhagyást az eszköz felhasználójától.

## <a name="manage-android-for-work-app-permissions"></a>Az Android for Work alkalmazásengedélyeinek felügyelete
Az Android for Work használatához jóvá kell hagynia az alkalmazásokat a Google által felügyelt Play webkonzolon, mielőtt az Intune-ba szinkronizálná és a felhasználókhoz hozzárendelné azokat.  Mivel az Android for Work lehetővé teszi az alkalmazások automatikus és csendes leküldését a felhasználói eszközökre, az alkalmazások által kért engedélyeket el kell fogadnia az összes felhasználó nevében.  A végfelhasználóknak a telepítésnél nem jelennek meg alkalmazásengedélyek, ezért fontos, hogy Ön elolvassa és megértse ezeket az engedélyeket.

Ha az alkalmazás fejlesztője megváltozott engedélyekkel rendelkező új alkalmazásverziót tesz közzé, az új engedélyek nem lesznek automatikusan elfogadva akkor sem, ha Ön az előző verzió engedélykéréseit elfogadta. Az alkalmazás korábbi verzióját futtató eszközök továbbra is használhatják az alkalmazást. Az alkalmazás frissítése azonban nem történik meg, amíg el nem fogadja az új engedélyeket. Az alkalmazással még nem rendelkező eszközökre az új engedélyek elfogadásáig nem telepíthető az alkalmazás.

### <a name="how-to-update-app-permissions"></a>Alkalmazásengedélyek frissítése

Ellenőrizze rendszeresen a felügyelt Google Play-konzolon az új alkalmazásengedélyeket. Beállíthatja, hogy a Google Play e-mailt küldjön Önnek vagy másoknak, ha új engedélyekre van szükség egy jóváhagyott alkalmazáshoz. Ha egy alkalmazás a hozzárendelése után sincs telepítve az eszközökön, az alábbi lépéseket követve ellenőrizheti, hogy vannak-e új alkalmazásengedélyek:

1. Látogasson el a http://play.google.com/work címre
2. Jelentkezzen be azzal a Google-fiókkal, amelyet az alkalmazások közzétételénél és jóváhagyásánál használt.
3. A **Frissítések** lapon ellenőrizze, hogy szükséges-e alkalmazásokat frissíteni.  A listában szereplő összes alkalmazás új engedélyeket kér, és a hozzárendelés addig nem lehetséges, amíg az engedélyeket meg nem adják.  

Alternatív megoldásként beállíthatja, hogy a Google Play alkalmazásalapon automatikusan végezze el az engedélyek ismételt megadását. 

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work áruházból származó üzletági alkalmazások használata

1. Nyissa meg a Google Play Developer Console-t a [play.google.com/apps/publish](https://play.google.com/apps/publish) címen.
2. Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot. Az első bejelentkezés előtt regisztrálni kell, továbbá megfizetni a Google Developer-program regisztrációs díját.
3. A konzolon válassza az **Add new application** (Új alkalmazás hozzáadása) elemet.
4. Az alkalmazások és azok információinak feltöltése ugyanúgy történik, mint bármelyik alkalmazás közzététele a Google Play áruházban. Ugyanakkor ki kell választani az **Only make this application available to my organization (<*organization name*>)** (Az alkalmazás elérhetővé tétele csak a saját cég tagjai számára (<cég neve>)) lehetőséget:</br>

    ![Az alkalmazás elérhetővé tétele csak a saját szervezet számára beállítás](media/restrict.png)</br>

Ezzel a művelettel gondoskodhat arról, hogy az alkalmazás csak a munkahelye számára legyen elérhető, a Google Play Áruház nyilvános területein ne.
További információt az androidos alkalmazások feltöltéséről és közzétételéről a [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469) súgóközpontban talál.
5. Miután feltöltötte az alkalmazást, lépjen be a [Google Play for Work áruházba](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
6. Az áruház **Alkalmazások** csomópontjában ellenőrizze, hogy látja-e a közzétett alkalmazást. Az alkalmazás automatikusan megkapja az engedélyt az Intune-nal való szinkronizálásra.

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

