---
title: Eszközprofilok hozzárendelése az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Az Azure Portal használatával rendelhet hozzá eszközprofilokat és szabályzatokat a felhasználókhoz és eszközökhöz. Útmutató ahhoz, hogyan zárhat ki csoportokat egy profil-hozzárendelésből a Microsoft InTune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9840298df981bee6c33d3cb36ec5e4ada46d11bd
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/20/2018
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Felhasználói és eszközprofilok hozzárendelése a Microsoft Intune-ban

Profil létrehozása után hozzárendelheti a profilt az Azure Active Directory- (Azure AD) csoportokhoz.

## <a name="assign-a-device-profile"></a>Eszközprofil hozzárendelése

1. Az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** lehetőséget, majd keresse meg a **Microsoft Intune** elemet.
2. A **Microsoft Intune** területen válassza az **Eszközkonfiguráció** lehetőséget, majd a **Profilok** elemet.
3. A profilok listájából válassza ki a hozzárendelendő profilt, majd válassza a **Hozzárendelés** lehetőséget.
4. Adja meg, hogy **belefoglalni** vagy **kizárni** szeretne egyes csoportokat, majd válassza ki a csoportokat.  

    ![Képernyőkép profil hozzárendelésekor a csoportok belefoglalásához és kizárásához megadható beállításokról](./media/group-include-exclude.png)

5. A csoportok kiválasztásakor egy Azure AD-csoportot is választ. Több csoport kijelöléséhez tartsa lenyomva a **Ctrl** billentyűt.
6. Amikor elkészült, válassza a **Mentés** gombot.

## <a name="exclude-groups-from-a-profile-assignment"></a>Csoportok kizárása profil hozzárendelésekor

Az Intune-beli eszközkonfigurációs profilok lehetővé teszik csoportok kizárását a szabályzat-hozzárendelésből. Hozzárendelhet például egy eszközprofilt a **Minden vállalati felhasználó** csoporthoz úgy, hogy a **Felsővezetők** csoport tagjait kizárja.

Amikor kizár egyes csoportokat, felhasználókat vagy eszközcsoportokat (nem vegyes csoportokat) a hozzárendelésből, az Intune figyelmen kívül hagyja a felhasználók és az eszközök közötti kapcsolatokat. Felhasználói csoportok belefoglalása és eszközcsoportok egyidejű kizárása esetén előfordulhat, hogy nem éri el a kívánt eredményt. Vegyes csoportok használata vagy más ütközés esetén a belefoglalás élvez elsőbbséget a kizárás felett.

Tegyük fel például, hogy egy eszközprofilt a szervezet valamennyi eszközéhez hozzá kíván rendelni, kivéve a kioszkmódban működő eszközöket. Belefoglalja a **Minden felhasználó** csoportot, de kizárja a **Minden eszköz** csoportot. Ebben az esetben minden felhasználó és azok minden eszköze megkapja a szabályzatot még akkor is, ha a felhasználó eszköze tagja a **Minden eszköz** csoportnak.

A kizárás csak a csoportok közvetlen tagjaira vonatkozik és nem érinti a felhasználóval társított eszközöket. A felhasználóval nem rendelkező eszközök azonban nem kapják meg a szabályzatot. Ez amiatt van, hogy az ilyen eszközöknek nincs kapcsolata a **Minden felhasználó** csoporttal.

A **Minden eszköz** csoport belefoglalása és a **Minden felhasználó** csoport kizárása esetén minden eszköz megkapja a szabályzatot. A cél ezúttal azoknak az eszközöknek a kizárása, amelyekhez a szabályzat szerint felhasználó van társítva. Ez azonban zárja ki az eszközöket, hiszen a kizárás funkció csak a közvetlen csoporttagokat hasonlítja össze.

>[!TIP]
>A kizárás nem használható megfelelőségi szabályzatok és alkalmazás-hozzárendelés esetén. Egy hozzárendelésből az **Elérhető** és a **Nem alkalmazható** hozzárendelési szándék használatával zárhat ki tagokat. Ha például egy alkalmazást a **Minden vállalati felhasználó** csoporthoz rendel az **Elérhető** szándékkal, a **Felsővezetők** csoporthoz pedig a **Nem alkalmazható** szándékkal, akkor az alkalmazás minden felhasználóhoz hozzá lesz rendelve, *kivéve* a **Felsővezetők** csoport tagjait. Ha az alkalmazást a **Kötelező** szándékkal rendel **Minden vállalati felhasználó** csoporthoz, akkor a **Felsővezetők** csoport tagjai nem lesznek kizárva.

## <a name="next-steps"></a>További lépések
Az eszközprofil-hozzárendelések figyeléséhez az [Eszközprofilok figyelése](device-profile-monitor.md) témakör nyújt segítséget.
