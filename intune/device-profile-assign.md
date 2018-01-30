---
title: "Eszközprofilok hozzárendelése az Intune-ban"
titlesuffix: Azure portal
description: "Az Intune-os eszközprofil létrehozását követően ebből a témakörből megtudhatja, hogyan tudja azt eszközökhöz hozzárendelni.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef03eeab32050559d34d3d7d580c06c21f5ffb05
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Microsoft Intune-eszközprofilok hozzárendelése

## <a name="assign-a-device-profile"></a>Eszközprofil hozzárendelése

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
1. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
2. A Profilok panel listáján válassza ki azt profilt, amelyet kezelni szeretne, majd a *profilnév*> **Jelentések** panelen a **Felügyelet** > **Hozzárendelések** elemet.
3. A következő panelen válasszon a **Belefoglalás** (csoportok belefoglalása) és a **Kizárás** (csoportok kizárása) közül, majd kattintson a **Csoportok kiválasztása** elemre.
![Csoportok belefoglalása vagy kizárása profil hozzárendelésekor.](./media/group-include-exclude.png)
4. A **Csoportok kiválasztása** panelen jelölje ki a hozzárendelésbe belefoglalandó vagy abból kizárandó Azure AD-csoportokat. Több csoport kijelöléséhez tartsa lenyomva a **CTRL** billentyűt.
4. Ha elkészült, a **Csoportok kiválasztása** panelen válassza a **Kijelölés** elemet.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Csoportok kizárása eszközprofil-hozzárendelésből

Az Intune-beli eszközkonfigurációs profilok lehetővé teszik csoportok kizárását a szabályzat-hozzárendelésből. Hozzárendelhet például egy eszközprofilt a **Minden vállalati felhasználó** csoporthoz úgy, hogy a **Felsővezetők** csoport tagjait kizárja.

Amikor csoportot zár ki egy hozzárendelésből, akkor vagy csak felhasználói vagy csak eszközcsoportot zárjon ki, ne vegyesen. Az Intune nem veszi számításba a felhasználók és eszközök közötti társításokat a csoportok kizárásánál. Felhasználói csoportok belefoglalása és eszközcsoportok egyidejű kizárása minden bizonnyal nem éri el a kívánt eredményt. Vegyes csoportok használata vagy más ütközés esetén a belefoglalás élvez elsőbbséget a kizárás felett.

Tegyük fel például, hogy egy eszközprofilt a szervezet valamennyi eszközéhez hozzá kíván rendelni, kivéve a kioszkmódban működő eszközöket. Belefoglalja a **Minden felhasználó** csoportot, de kizárja a **Minden eszköz** csoportot.

Ebben az esetben minden felhasználó és azok minden eszköze megkapja a szabályzatot még akkor is, ha a felhasználó eszköze tagja a **Minden eszköz** csoportnak. 

A kizárás csak a csoportok közvetlen tagjaira vonatkozik és nem érinti a felhasználóval társított eszközöket. A felhasználó nélküli eszközök viszont nem kapják meg a szabályzatot, mert nincs hozzájuk társított elem a **Minden felhasználó** csoportban. 

A **Minden eszköz** csoport belefoglalása és a **Minden felhasználó** csoport kizárása esetén minden eszköz megkapja a szabályzatot. A cél ezúttal azoknak az eszközöknek a kizárása, amelyekhez a szabályzat szerint felhasználó van társítva. Ez azonban nem történik meg, hiszen a kizárás funkció csak a közvetlen csoporttagokat hasonlítja össze. 

>[!Tip]
>A kizárás egyelőre nem használható megfelelőségi szabályzatok és alkalmazás-hozzárendelés esetén. Egy hozzárendelésből az Elérhető és Nem alkalmazható hozzárendelési szándék használatával zárhat ki tagokat. Ha például egy alkalmazást a **Minden vállalati felhasználó** csoporthoz rendel az **Elérhető** szándékkal, a **Felsővezetők** csoporthoz pedig a **Nem alkalmazható** szándékkal, akkor az alkalmazás minden felhasználóhoz hozzá lesz rendelve, *kivéve* a **Felsővezetők** csoport tagjait. Ha az alkalmazást a **Kötelező** szándékkal rendel **Minden vállalati felhasználó** csoporthoz, akkor a **Felsővezetők** csoport tagjai nem lesznek kizárva.
 
    
## <a name="next-steps"></a>További lépések
Az eszközprofil-hozzárendelések figyeléséhez az [Eszközprofilok figyelése](device-profile-monitor.md) témakör nyújt segítséget.
