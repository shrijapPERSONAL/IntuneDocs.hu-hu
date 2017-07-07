---
title: "Alkalmazások hozzárendelése Android for Work-eszközökhöz"
titleSuffix: Intune on Azure
description: "Az alábbi témakörből megtudhatja, hogyan végezheti el a Google Play for Work áruházból származó alkalmazások szinkronizálását és Android for Work-eszközökhöz való hozzárendelését."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 94394a889d97b4d1bdf09303b11cdc3688e4f55a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Alkalmazások hozzárendelése Android for Work-eszközökhöz az Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az alkalmazások Android for Work-eszközökhöz való hozzárendelése eltér a hagyományos androidos eszközökhöz való hozzárendeléstől. Minden olyan alkalmazás, amelyet az Android for Work részeként telepít, a Google Play for Work áruházból szerezhető be. Jelentkezzen be az áruházba, keresse meg a kívánt alkalmazást, majd hagyja jóvá a választást.
Az alkalmazás ezt követően a **Licencelt alkalmazások** csomópontban jelenik meg az Intune-portálon. Ezen a felületen kezelheti az alkalmazások hozzárendelését, ami ugyanúgy zajlik, mint a hagyományos alkalmazásoknál.

Ha saját üzletági (LOB) alkalmazásokat hozott létre, azok hozzárendelését is elvégezheti az alábbiak szerint:
- Hozzon létre egy Google Developer-fiókot, amellyel saját területen tehet közzé alkalmazásokat a Google Play Áruházban.
- Szinkronizálja az alkalmazásokat az Intune-nal.

## <a name="before-you-start"></a>Előkészületek

Győződjön meg arról, hogy az Intune-t és az Android for Work-öt is beállította a közös munkára az Intune-portál **Eszközök beléptetése** területén.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work áruházbeli alkalmazások szinkronizálása

1. Nyissa meg a [Google Play for Work áruházat](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
2. Az áruházban keresse meg az Intune-nal hozzárendelendő alkalmazást.
3. A kiválasztott alkalmazás lapján válassza a **Jóváhagyás** elemet. Ebben a példában a Microsoft Excel alkalmazást választotta.<br>
  ![Alkalmazás jóváhagyása – példa](media/approve.png)
4. Ekkor megjelenik egy ablak, amelyben az alkalmazás engedélyt kér bizonyos műveletek végrehajtására. A folytatáshoz válassza a **Jóváhagyás** elemet.<br>
  ![Alkalmazásengedélyek jóváhagyása – példa](media/approve-app-permissions.png)
5. A jóváhagyás megtörténik, és az alkalmazás megjelenik a rendszergazdai konzolon.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work áruházból származó üzletági alkalmazások közzététele és szinkronizálása

1. Nyissa meg a Google Play Developer Console-t a [play.google.com/apps/publish](https://play.google.com/apps/publish) címen.
2. Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot. Az első bejelentkezés előtt regisztrálni kell, továbbá megfizetni a Google Developer-program regisztrációs díját.
3. A konzolon válassza az **Add new application** (Új alkalmazás hozzáadása) elemet.
4. Az alkalmazások és azok információinak feltöltése ugyanúgy történik, mint bármelyik alkalmazás közzététele a Google Play áruházban. Ugyanakkor ki kell választani az **Only make this application available to my organization (<*organization name*>)** (Az alkalmazás elérhetővé tétele csak a saját cég tagjai számára (<cég neve>)) lehetőséget.<br>
  ![Az alkalmazás elérhetővé tétele csak a saját szervezet számára beállítás](media/restrict.png)<br>
Ezzel a művelettel gondoskodhat arról, hogy az alkalmazás csak a munkahelye számára legyen elérhető, a Google Play Áruház nyilvános területein ne.
További információt az androidos alkalmazások feltöltéséről és közzétételéről a [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469) súgóközpontban talál.
5. Miután feltöltötte az alkalmazást, lépjen be a [Google Play for Work áruházba](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
6. Az áruház **Alkalmazások** csomópontjában ellenőrizze, hogy látja-e a közzétett alkalmazást. Az alkalmazás automatikusan megkapja az engedélyt az Intune-nal való szinkronizálásra.

## <a name="assign-an-android-for-work-app"></a>Android for Work-alkalmazások hozzárendelése

Ha jóváhagyott egy áruházból beszerzett alkalmazást, de nem látja a **Mobilalkalmazások** munkaterület **Licencelt alkalmazások** csomópontjában, az alábbi lépésekkel kényszerítheti az azonnali szinkronizálást:

1. Jelentkezzen be az Azure Portalra.
2. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
3. A **Mobilalkalmazások** területen válassza a **Beállítás** > **Android for Work** elemet.
4. Az Android for Work panelen válassza a **Szinkronizálás** elemet.
5. A lapon látható az utolsó szinkronizálás időpontja és állapota is.

Ha az alkalmazás megjelenik a **Mobilalkalmazások** munkaterület **Licencelt alkalmazások** csomópontjában, [ugyanúgy hozzárendelheti, mint bármelyik alkalmazást](/intune-azure/manage-apps/deploy-apps). Az alkalmazásokat úgy is hozzá lehet rendelni, hogy csak bizonyos felhasználói csoportokat érjenek el.

A hozzárendelés után az alkalmazás rendelkezésre áll a célzott eszközökön. A rendszer nem kér telepítési jóváhagyást az eszköz felhasználójától.

## <a name="manage-android-for-work-app-permissions"></a>Az Android for Work alkalmazásengedélyeinek felügyelete
Az Android for Work használatához jóvá kell hagynia az alkalmazásokat a Google által felügyelt Play webkonzolon, mielőtt az Intune-ba szinkronizálná és a felhasználókhoz hozzárendelné azokat.  Mivel az Android for Work lehetővé teszi az alkalmazások automatikus és csendes leküldését a felhasználói eszközökre, az alkalmazások által kért engedélyeket el kell fogadnia az összes felhasználó nevében.  A végfelhasználóknak a telepítésnél nem jelennek meg alkalmazásengedélyek, ezért fontos, hogy Ön elolvassa és megértse ezeket az engedélyeket.

Ha az alkalmazás fejlesztője megváltozott engedélyekkel rendelkező új alkalmazásverziót tesz közzé, az új engedélyek nem lesznek automatikusan elfogadva akkor sem, ha Ön az előző verzió engedélykéréseit elfogadta. Az alkalmazás korábbi verzióját futtató eszközök továbbra is használhatják az alkalmazást. Az alkalmazás frissítése azonban nem történik meg, amíg el nem fogadja az új engedélyeket. Az alkalmazással még nem rendelkező eszközökre az új engedélyek elfogadásáig nem telepíthető az alkalmazás.

### <a name="how-to-update-app-permissions"></a>Alkalmazásengedélyek frissítése

Ellenőrizze rendszeresen a felügyelt Google Play-konzolon az új alkalmazásengedélyeket. Beállíthatja, hogy a Google Play e-mailt küldjön Önnek vagy másoknak, ha új engedélyekre van szükség egy jóváhagyott alkalmazáshoz. Ha egy alkalmazás a hozzárendelése után sincs telepítve az eszközökön, az alábbi lépéseket követve ellenőrizheti, hogy vannak-e új alkalmazásengedélyek:

1. Keresse fel a http://play.google.com/work webhelyet
2. Jelentkezzen be azzal a Google-fiókkal, amelyet az alkalmazások közzétételénél és jóváhagyásánál használt.
3. A **Frissítések** lapon ellenőrizze, hogy szükséges-e alkalmazásokat frissíteni.  A listában szereplő összes alkalmazás új engedélyeket kér, és a hozzárendelés addig nem lehetséges, amíg az engedélyeket meg nem adják.  

Alternatív megoldásként beállíthatja, hogy a Google Play alkalmazásonként automatikusan végezze el az engedélyek ismételt megadását. 



