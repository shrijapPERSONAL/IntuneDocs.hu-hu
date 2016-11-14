---
title: "Alkalmazások telepítése Android for Work-eszközökre | Microsoft Intune"
description: "Itt megtudhatja, hogyan szinkronizáljon és telepítsen alkalmazásokat Android for Work-eszközökre a Google Play for Work áruházból."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: f3b7c3a07ef3530805f4f951bcdb99cc5f7eb93d


---

# Alkalmazások telepítése Android for Work-eszközökre | Microsoft Intune

Az alkalmazások Android for Work-eszközökre való telepítése eltér a hagyományos androidos eszközökre való telepítéstől. Minden olyan alkalmazás, amelyet az Android for Work részeként telepít, a Google Play for Work áruházból szerezhető be. Jelentkezzen be az áruházba, keresse meg a kívánt alkalmazást, majd hagyja jóvá a választást.
Az alkalmazás ezt követően a **Mennyiségi licencszerződés keretében vásárolt alkalmazások** csomópontban jelenik meg az Intune-konzolon. Ezen a felületen kezelheti az alkalmazások telepítését, ami ugyanúgy zajlik, mint a hagyományos alkalmazásoknál.
Ha saját üzletági (LOB) alkalmazásokat hozott létre, azokat is telepítheti. Ehhez hozzon létre egy Google Developer-fiókot, amellyel saját területen tehet közzé alkalmazásokat a Google Play áruházban, majd szinkronizálhatja őket az Intune-nal.

## Előkészületek

1. Győződjön meg róla, hogy az Intune-t és az Android for Work-öt is beállította a közös munkára az Intune-konzol **Felügyelet** lapján.

## Google Play for Work áruházbeli alkalmazások szinkronizálása


1. Nyissa meg a [Google Play for Work áruházat](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot.
2. Az áruházban keresse meg az alkalmazást, amelyet telepíteni kíván az Intune-nal.
3. A kiválasztott alkalmazás lapján válassza a **Jóváhagyás** elemet. Ebben a példában a Microsoft Excel alkalmazást választotta.<br>
  ![Alkalmazás jóváhagyása példa](/intune/deploy-use/media/approve.png)
4. Ekkor megjelenik egy ablak, amelyben az alkalmazás engedélyt kér bizonyos műveletek végrehajtására. Válassza ismét a **Jóváhagyás** lehetőséget.<br>
  ![Alkalmazásengedélyek jóváhagyása példa](/intune/deploy-use/media/approve-app-permissions.png)
5. Ezután egy üzenet érkezik, amely megerősíti, hogy az alkalmazás jóvá lett hagyva és elérhető a rendszergazdai konzolon. 

## Üzletági alkalmazások közzététele és szinkronizálása a Google Play for Work áruházban 

1. Nyissa meg a Google Play Developer Console-t a [play.google.com/apps/publish](play.google.com/apps/publish) címen.
2. Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot. Az első bejelentkezés előtt regisztrálni kell, továbbá megfizetni a Google Developer-program regisztrációs díját.
3. A konzolon válassza az **Add new application** (Új alkalmazás hozzáadása) elemet.
4. Az alkalmazások és azok információinak feltöltése ugyanúgy történik, mint bármelyik alkalmazás közzététele a Google Play áruházban. Ugyanakkor ki kell választani az **Only make this application available to my organization (<*organization name*>)** (Az alkalmazás elérhetővé tétele csak a saját szervezet tagjai számára (<szervezet neve>)**) lehetőséget, ahogy alább is látható.<br>
  ![Az alkalmazás elérhetővé tétele csak a saját szervezet számára beállítás](/intune/deploy-use/media/restrict.png)<br>
Ezzel gondoskodhat róla, hogy az alkalmazás csak az Ön szervezete számára legyen elérhető, a Google Play áruház nyilvános területein ne.
További információt az androidos alkalmazások feltöltéséről és közzétételéről a [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469) súgóközpontban talál.
5. Miután feltöltötte az alkalmazást, lépjen be a [Google Play for Work áruházba](https://play.google.com/work). Ugyanazzal a fiókkal jelentkezzen be, amellyel beállította az Intune és az Android for Work közötti kapcsolatot. 
6. Az áruház **Alkalmazások** csomópontjában ellenőrizze, hogy látja-e a közzétett alkalmazást. Vegye figyelembe, hogy az alkalmazás automatikusan megkapta az engedélyt arra, hogy szinkronizáljon az Intune-nal.

## Android for Work-alkalmazások telepítése

Az Intune jellemzően naponta kétszer szinkronizál a Google Play for Work áruházzal. Ha jóváhagyott egy áruházból beszerzett alkalmazást, de nem látja az **Alkalmazások** munkaterület **Mennyiségi licencszerződés keretében vásárolt alkalmazások** csomópontjában, az alábbi lépésekkel kényszerítheti a szinkronizálást:

1. Az [Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Felügyelet** > **Mobileszköz-kezelés** > **Android for Work** elemre.
2. **Az Android for Work mobileszköz-kezelési beállításai** lapon válassza a **Szinkronizálás most** lehetőséget.
3. A lapon látható az utolsó szinkronizálás időpontja és állapota is.

Ha az alkalmazás megjelenik az **Alkalmazások** munkaterület **Mennyiségi licencszerződés keretében vásárolt alkalmazások** csomópontjában, akkor [ugyanúgy telepítheti, mint bármelyik alkalmazást](deploy-apps-in-microsoft-intune.md). Az alkalmazások úgy is telepíthetők, hogy csak bizonyos felhasználói csoportok érjék el. Egyelőre csak a **Kötelező** és az **Eltávolítás** lehetőségek elérhetők. 2016. októberétől az új bérlők számára az **Elérhető** lehetőséggel bővítjük a fejlesztői műveleteket. 

A telepítés után az alkalmazás elérhető lesz a kijelölt eszközökön. Az eszköz használójának a hozzájárulását a rendszer nem kéri.



<!--HONumber=Oct16_HO2-->


