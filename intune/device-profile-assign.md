---
title: Eszközprofilok hozzárendelése az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Az Azure Portal használatával rendelhet hozzá eszközprofilokat és szabályzatokat a felhasználókhoz és eszközökhöz. Megtudhatja, hogyan csoportok kizárása profil hozzárendelésekor a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c950efdd95fd8d856ec677385712a022dead870
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423854"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Felhasználói és eszközprofilok hozzárendelése a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil létrehozása, és a megadott összes beállítást tartalmazza. A következő lépés, hogy üzembe helyezése vagy "" a profil hozzárendelése az Azure Active Directory (Azure AD) felhasználói vagy eszközcsoportokhoz. Ha van hozzárendelve, a felhasználók és eszközök megkapják a profilját, és a megadott beállítások lesznek alkalmazva.

Ez a cikk bemutatja, hogyan szeretne hozzárendelni egy profilt, és a profilok a hatókörcímkék használatával információkat tartalmaz.

## <a name="assign-a-device-profile"></a>Eszközprofil hozzárendelése

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** lehetőséget. Minden profilhoz vannak felsorolva.
3. Válassza ki a hozzárendelni kívánt profilt > **hozzárendelések**.
4. Válassza ki a **Belefoglalás** csoportok vagy **kizárása** csoportosítja, és válassza ki a csoportokat. A csoportok kiválasztásakor egy Azure AD-csoportot is választ. Több csoport kijelöléséhez tartsa lenyomva a **Ctrl** kulcsát, és válassza ki azokat a csoportokat.

    ![Képernyőkép profil hozzárendelésekor a csoportok belefoglalásához és kizárásához megadható beállításokról](./media/group-include-exclude.png)

5. **Mentse** a változtatásokat.

### <a name="evaluate-how-many-users-are-targeted"></a>Kiértékelheti, hogy hány felhasználóra vonatkozik

A profil hozzárendelésekor is **Evaluate** hány felhasználó érintett. Ez a funkció számítja ki a felhasználók; eszköz nem számítja ki.

1. Válassza ki az Intune-ban **eszközkonfiguráció** > **profilok**.
2. Profil kiválasztása > **hozzárendelések** > **Evaluate**. Megjelenik egy üzenet, hogy hány felhasználóra vonatkozik ez a profil.

Ha a **Evaluate** gomb szürkén jelenik meg, ellenőrizze, hogy a profil hozzá van rendelve egy vagy több csoportot.


## <a name="use-scope-tags"></a>Hatókörcímkék használata

Amikor hoz létre, vagy frissíteni egy profilt, a profil is hatókörcímkék is hozzáadhat.

**Címkék hatókör** praktikus módot nyújtanak hozzárendelni, és a házirendek adott csoportokra, például a HR vagy az összes USA-NC szűréséhez alkalmazott. [Rbac-RÓL és a hatókör címkék használata az elosztott informatikai](scope-tags.md) tartalmaz további információkat.

## <a name="exclude-groups-from-a-profile-assignment"></a>Csoportok kizárása profil hozzárendelésekor

Az Intune-beli eszközkonfigurációs profilok lehetővé teszik csoportok kizárását a szabályzat-hozzárendelésből. Például hozzárendelhet egy eszközprofilt a **minden vállalati felhasználó** csoportot, de kizárja a tagokat a **felsővezetők** csoport.

Ha kizár csoportokat, csak a felhasználók, vagy csak eszközcsoportot (nem vegyes csoportokat) egy hozzárendelésből, az Intune meg nem felhasználó-eszköz kapcsolatokat. Felhasználói csoportok belefoglalása és eszközcsoportok egyidejű kizárása minden nem lehet beolvasni a kívánt eredményt. Vegyes csoportok használata esetén, vagy más ütközés esetén a Belefoglalás élvez elsőbbséget kizárás felett.

Tegyük fel például, hogy egy eszközprofilt a szervezet valamennyi eszközéhez hozzá kíván rendelni, kivéve a kioszkmódban működő eszközöket. Belefoglalja a **Minden felhasználó** csoportot, de kizárja a **Minden eszköz** csoportot. Ebben az esetben minden felhasználó és az eszközeik megkapja a szabályzatot még akkor is, ha a felhasználó-eszköz szerepel a **minden eszköz** csoport.

Kizárási csak megvizsgálja a csoport közvetlen tagjai. Ebben nem tartoznak bele, amelyek a felhasználóval társított eszközöket. A felhasználóval nem rendelkező eszközök azonban nem kapják meg a szabályzatot. Ez akkor fordul elő, mert ezeknek az eszközöknek nincs kapcsolata a **minden felhasználó** csoport.

A **Minden eszköz** csoport belefoglalása és a **Minden felhasználó** csoport kizárása esetén minden eszköz megkapja a szabályzatot. A cél ezúttal azoknak az eszközöknek a kizárása, amelyekhez a szabályzat szerint felhasználó van társítva. Ez azonban zárja ki az eszközöket, hiszen a kizárás funkció csak a közvetlen csoporttagokat hasonlítja össze.

## <a name="next-steps"></a>További lépések

Lásd: [eszközprofilok figyelése](device-profile-monitor.md) útmutatást a figyelés, a profilokat, és a profilok futtató eszközre.