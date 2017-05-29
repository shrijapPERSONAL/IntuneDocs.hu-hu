---
title: "Alkalmazások hozzárendelése Android for Work-eszközökhöz | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: ebből a témakörből megtudhatja, hogyan végezheti el alkalmazások szinkronizálását és telepítését Android for Work-eszközökre a Google Play for Work áruházból."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 49e86ab665d9022739c0330092734ba897ea3b02
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Alkalmazások hozzárendelése Android for Work-eszközökhöz az Intune-nal

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Az alkalmazások Android for Work-eszközökhöz való hozzárendelése eltér a hagyományos androidos eszközökhöz való hozzárendeléstől. Minden olyan alkalmazás, amelyet az Android for Work részeként telepít, a Google Play for Work áruházból szerezhető be. Jelentkezzen be az áruházba, keresse meg a kívánt alkalmazást, majd hagyja jóvá a választást.
Az alkalmazás ezt követően a **Licencelt alkalmazások** csomópontban jelenik meg az Intune-portálon. Ezen a felületen kezelheti az alkalmazások hozzárendelését, ami ugyanúgy zajlik, mint a hagyományos alkalmazásoknál.

Ha saját üzletági (LOB) alkalmazásokat hozott létre, azok hozzárendelését is elvégezheti. Ehhez hozzon létre egy Google Developer-fiókot, amellyel saját területen tehet közzé alkalmazásokat a Google Play áruházban, majd szinkronizálhatja őket az Intune-nal.

## <a name="before-you-start"></a>Előkészületek

Győződjön meg arról, hogy az Intune-t és az Android for Work-öt is beállította a közös munkára az Intune-portál **Eszközök beléptetése** területén.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work áruházbeli alkalmazások szinkronizálása


1. Nyissa meg a [Google Play for Work áruházat](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
2. Az áruházban keresse meg az Intune-nal hozzárendelendő alkalmazást.
3. A kiválasztott alkalmazás lapján válassza a **Jóváhagyás** elemet. Ebben a példában a Microsoft Excel alkalmazást választotta.<br>
  ![Alkalmazás jóváhagyása – példa](media/approve.png)
4. Ekkor megjelenik egy ablak, amelyben az alkalmazás engedélyt kér bizonyos műveletek végrehajtására. Válassza ismét a **Jóváhagyás** lehetőséget.<br>
  ![Alkalmazásengedélyek jóváhagyása – példa](media/approve-app-permissions.png)
5. Ezután egy üzenet érkezik, amely megerősíti, hogy az alkalmazás jóvá lett hagyva és elérhető a rendszergazdai konzolon.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Üzletági alkalmazások közzététele és szinkronizálása a Google Play for Work áruházban

1. Nyissa meg a Google Play Developer Console-t a [play.google.com/apps/publish](https://play.google.com/apps/publish) címen.
2. Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot. Az első bejelentkezés előtt regisztrálni kell, továbbá megfizetni a Google Developer-program regisztrációs díját.
3. A konzolon válassza az **Add new application** (Új alkalmazás hozzáadása) elemet.
4. Az alkalmazások és azok információinak feltöltése ugyanúgy történik, mint bármelyik alkalmazás közzététele a Google Play áruházban. Ugyanakkor ki kell választani az **Only make this application available to my organization (<*organization name*>)** (Az alkalmazás elérhetővé tétele csak a saját szervezet tagjai számára (<szervezet neve>)) lehetőséget, ahogy alább is látható.<br>
  ![Az alkalmazás elérhetővé tétele csak a saját szervezet számára beállítás](media/restrict.png)<br>
Ezzel gondoskodhat róla, hogy az alkalmazás csak az Ön szervezete számára legyen elérhető, a Google Play áruház nyilvános területein ne.
További információt az androidos alkalmazások feltöltéséről és közzétételéről a [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469) súgóközpontban talál.
5. Miután feltöltötte az alkalmazást, lépjen be a [Google Play for Work áruházba](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
6. Az áruház **Alkalmazások** csomópontjában ellenőrizze, hogy látja-e a közzétett alkalmazást. Vegye figyelembe, hogy az alkalmazás automatikusan megkapta az engedélyt arra, hogy szinkronizáljon az Intune-nal.

## <a name="assign-an-android-for-work-app"></a>Android for Work-alkalmazások hozzárendelése

Ha jóváhagyott egy áruházból beszerzett alkalmazást, de nem látja a **Mobilalkalmazások** terület **Licencelt alkalmazások** csomópontjában, az alábbi lépésekkel kényszerítheti az azonnali szinkronizálást:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Beállítás** > **Android for Work** elemet.
5. Az Android for Work panelen válassza a **Szinkronizálás** elemet.
6. A lapon látható az utolsó szinkronizálás időpontja és állapota is.

Ha az alkalmazás megjelenik a **Mobilalkalmazások** terület **Licencelt alkalmazások** csomópontjában, akkor [ugyanúgy hozzárendelheti, mint bármelyik alkalmazást](/intune-azure/manage-apps/deploy-apps). Az alkalmazásokat úgy is hozzá lehet rendelni, hogy csak bizonyos felhasználói csoportokat érjenek el.

A hozzárendelés után az alkalmazás rendelkezésre áll a célzott eszközökön. A rendszer nem kér telepítési jóváhagyást az eszköz felhasználójától.

## <a name="manage-app-permissions"></a>Alkalmazásengedélyek kezelése
Az Android for Work használatához jóvá kell hagynia az alkalmazásokat a Google által felügyelt Play webkonzolon, mielőtt az Intune-ba szinkronizálná és a felhasználókhoz hozzárendelné azokat.  Mivel az Android for Work lehetővé teszi az alkalmazások automatikus és csendes leküldését a felhasználói eszközökre, az alkalmazások által kért engedélyeket el kell fogadnia az összes felhasználó nevében.  A felhasználók számára a telepítésnél nem jelennek meg alkalmazásengedélyek, ezért fontos, hogy Ön elolvassa és megértse ezeket az engedélyeket.

Ha az alkalmazás fejlesztője megváltozott engedélyekkel rendelkező új alkalmazásverziót tesz közzé, az új engedélyek nem lesznek automatikusan elfogadva akkor sem, ha Ön az előző verzió engedélykéréseit elfogadta. Az alkalmazás régebbi verzióját futtató eszközök továbbra is használhatják az alkalmazást, de frissítésre nem kerül sor, amíg el nem fogadja az új engedélyeket. Az alkalmazással még nem rendelkező eszközökre nem telepíthető az alkalmazás, amíg el nem fogadja az új alkalmazásengedélyeket.

### <a name="how-to-update-app-permissions"></a>Alkalmazásengedélyek frissítése

Javasolt rendszeresen ellenőrizni a felügyelt Google Play konzolon, hogy vannak-e új alkalmazásengedélyek. Ha egy alkalmazás a hozzárendelése után sincs telepítve az eszközökön, az alábbi lépéseket követve ellenőrizheti, hogy vannak-e új alkalmazásengedélyek:

1. Keresse fel a http://play.google.com/work webhelyet
2. Jelentkezzen be azzal a Google-fiókkal, amelyet az alkalmazások közzétételénél és jóváhagyásánál használt.
3. A **Frissítések** lapon ellenőrizze, hogy szükséges-e alkalmazásokat frissíteni.  A listában szereplő összes alkalmazás új engedélyeket kér, és a hozzárendelés addig nem lehetséges, amíg az engedélyeket meg nem adják.  

