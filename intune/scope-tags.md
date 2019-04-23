---
title: Szűrési szabályzatok hatókörcímkékkel a Microsoft Intune-ban – Azure | Microsoft Docs
description: Hatókörcímkékkel a konfigurációs profilokat meghatározott szerepkörök szerint szűrheti.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2eb709ad0d649b2ac32505b395fa91e85ad81b8a
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61507778"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Szerepköralapú hozzáférés-vezérlés (RBAC) és a hatókörcímkék használható elosztott IT

Szerepköralapú hozzáférés-vezérléshez és a hatókör címkék segítségével győződjön meg arról, hogy a megfelelő rendszergazdák rendelkeznek-e a megfelelő hozzáférést és látható-e a megfelelő Intune-objektumokhoz. Szerepkörök milyen általi hozzáférés megállapításához, hogy mely objektumok rendszergazdák rendelkeznek. Hatókörcímkék határozza meg, hogy mely objektumok rendszergazdák számára látható.

Például tegyük fel, hogy egy Seattle területi képviseletenként rendszergazdai szerepköre a házirend- és Profilkezelő. Azt szeretné, hogy ez a rendszergazda megtekintheti és kezelheti a csak a profilok és a házirendeket, amelyek csak a Seattle-eszközökre vonatkoznak. Ehhez ugyanúgy:

1. Hozzon létre egy Seattle nevű hatókörcímke.
2. A házirend- és Profilkezelő szerepkörének szerepkör-hozzárendelés létrehozásához: 
    - Tagok (csoportok) = Budapest Rendszergazdák nevű biztonsági csoportot. Ebben a csoportban minden rendszergazda házirendeket és a felhasználók és eszközök a hatókör (csoportok) profilok kezelése engedéllyel rendelkeznek.
    - Hatókör (csoportok) = egy biztonsági csoport nevű Seattle felhasználók. Ez a csoport összes felhasználókra vagy eszközökre azok profilok és szabályzatok az Adminisztrátorok a tagok (csoportok) által felügyelt lehet. 
    - Hatókör (címkék) = budapest. A tagok (csoportok) a rendszergazdák számára látható a Seattle hatókörcímke rendelkező eszközök.
3. Adja hozzá a Seattle hatókörcímke házirendek és profilok –, amelyek azt szeretné, hogy a rendszergazdák a tagok (csoportok) érhetik el.
4. Adja hozzá a Seattle hatókörcímke körét a tagok (csoportok) a rendszergazdák számára látható. 


## <a name="to-create-a-scope-tag"></a>Hatókörcímke létrehozása

1. Válassza ki az Intune-ban **szerepkörök** > **hatókör (címkék)** > **létrehozás**.

    ![Képernyőkép a hatókörcímke létrehozása.](./media/scope-tags/create-scope-tag.png)

2. Adjon meg egy **nevet** és egy **leírást**.
3. Válassza a **Létrehozás** lehetőséget.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Hatókörcímke hozzárendelése egy szerepkörhöz

1. Válassza ki az Intune-ban **szerepkörök** > **minden szerepkör** > Válassza ki a szerepkört > **hozzárendelések** > **hozzárendelése**.

    ![Képernyőkép a hatókör hozzárendelése szerepkörhöz.](./media/scope-tags/assign-scope-to-role.png)

2. Adjon meg egy **hozzárendelés neve** és **leírás**.
3. Válasszon **tagok (csoportok)** > **Hozzáadás** > Válassza ki a csoportokat az ehhez a hozzárendeléshez részeként > **válassza**  >   **OK**. Ebben a csoportban mUsers házirendek és a felhasználók és eszközök a hatókör (csoportok) profilok kezelése engedéllyel rendelkezik majd.

    ![Tag kiválasztása csoportok képernyőképe.](./media/scope-tags/select-member-groups.png)

4. Ha azt szeretné, kezelheti a csoportok meghatározott felhasználókra vagy eszközökre, válassza ki a **hatókör (csoportok)** > **kijelölt csoportok** > **belefoglalandó csoportok**> Válassza ki a csoportokat > **kiválasztása** > **OK**. Ez a csoport összes felhasználókra vagy eszközökre azok profilok és szabályzatok az Adminisztrátorok a tagok (csoport) által felügyelt lehet.

    ![Képernyőkép – válassza ki a hatókörcsoportokat.](./media/scope-tags/select-scope-groups.png)

    Választhatja azt is megteheti, **minden eszköz**, **minden felhasználó**, vagy **minden felhasználó és minden eszköz**.

    ![Képernyőkép – válassza ki a hatókörcsoportokat beállításának további lehetőségei.](./media/scope-tags/scope-group-other-options.png)
    
5. Válasszon **hatókör (címkék)** > **Hozzáadás** > Válassza ki a címkék hozzáadása ehhez a szerepkörhöz használni kívánt > **válassza** > **OK**. Tagok (csoportok) a felhasználók hozzáférhetnek a házirendek és profilok –, amelyek az ugyanazon hatókörcímke is rendelkezik.

    ![Képernyőfelvétel a hatókörcímkék válassza.](./media/scope-tags/select-scope-tags.png)

6. Válassza az **OK** gombot. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Hatókörcímke hozzáadása egy konfigurációs profilhoz
1. Válassza ki az Intune-ban **eszközkonfiguráció** > **profilok** > Válasszon egy profilt.

    ![Képernyőkép a profil válassza.](./media/scope-tags/choose-profile.png)

2. Válasszon **tulajdonságok** > **hatókör (címkék)** > **hozzáadása**.

    ![Képernyőfelvétel a hatókör-címkék felvétele.](./media/scope-tags/add-scope-tags.png)

3. A **válassza ki a címkék**, válassza ki a címkék, amelyeket szeretne hozzáadni a profil.
4. Válasszon **kiválasztása** > **OK** > **mentése**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Hatókörcímke hozzárendelése alkalmazás-konfigurációs házirend
Az eszközök **eszközregisztráció típusa** beállítása **felügyelt eszközök**:
1. Válasszon **ügyfélalkalmazás** > **alkalmazáskonfigurációs szabályzatok** > Válassza ki az alkalmazás-konfigurációs házirend.
2. Válasszon **tulajdonságok** > **hatókör (címkék)** > Válassza ki a házirendhez hozzárendelni kívánt címkéket.

Az eszközök **eszközregisztráció típusa** beállítása **felügyelt alkalmazások**:
1. Válasszon **ügyfélalkalmazás** > **alkalmazáskonfigurációs szabályzatok** > Válassza ki az alkalmazás-konfigurációs házirend.
2. Válasszon **hatókör (címkék)** > Válassza ki a házirendhez hozzárendelni kívánt címkéket.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Hatókörcímke hozzárendelése egy IOS-es alkalmazáskiépítési profil
1. Válassza ki az Intune-ban **ügyfélalkalmazás** > **iOS-alkalmazáskiépítési profilok** > Válasszon egy profilt.
2. Válasszon **tulajdonságok** > **hatókör (címkék)** > Válassza ki az, hogy a profilhoz hozzárendelni kívánt címkéket.
3. Válasszon **kiválasztása** > **OK** > **mentése**.

## <a name="to-assign-a-scope-tag-to-an-apple-volume-purchase-program-vpp-token"></a>Hatókörcímke hozzárendelése egy Apple Volume Purchase Program (VPP) tokent
1. Az Intune-ban válassza **ügyfélalkalmazás** > **Apple VPP-tokenek** > Válassza ki a VPP-tokent.
2. Válassza ki **hatókör (címkék)** > Válassza ki az, hogy a profilhoz hozzárendelni kívánt címkéket. A VPP-alkalmazások és e-könyvek a VPP-token társított öröklik a hozzárendelt címkék.
3. Válasszon **kiválasztása** > **OK** > **mentése**.

## <a name="scope-tag-details"></a>Címke részleteinek hatókör
Ha hatókörcímkék dolgozik, ne felejtse el ezeket az adatokat:

- A hatókörcímkék jelenleg hozzárendelését is elvégezheti:
    - Szerepkör-hozzárendelések
    - Eszközmegfelelőségi szabályzatok
    - Eszközkonfigurációs profilok
    - A Windows 10 frissítések körök
    - Felügyelt eszközök
    - Alkalmazások
    - Alkalmazáskonfigurációs szabályzatok – a felügyelt eszközök
    - PowerShell-parancsprogramok
    - DEP-tokenek
    - iOS-es alkalmazáskiépítési profil
    - Volume Purchase Program (VPP) tokenek
- Amikor a rendszergazda létrehoz egy objektumot az Intune-ban, azt a rendszergazdát rendelt összes hatókörcímkék automatikusan rendeli hozzá az új objektumot.
- Intune-os RBAC az Azure Active Directory-szerepkör nem vonatkozik. Így az Intune szolgáltatás-rendszergazdák és a globális Rendszergazdák szerepkör nincs teljes rendszergazdai hozzáféréssel az Intune-hoz, függetlenül attól, milyen hatókörcímkék rendelkeznek.
- A szerepkör-hozzárendelés hatóköre címkékkel rendelkező rendszergazdák nem hatókörcímkék Intune objektumokat is megtekintheti.
- Csak a szerepkör-hozzárendelések rendelkező hatókörcímke rendelhet hozzá.
- Csak olyan célcsoportokat, amelyek szerepelnek a hatókör (csoportok), a szerepkör-hozzárendelés is.
- Ha a szerepkörhöz rendelt hatókörcímke, minden hatókörcímkék egy Intune-objektum nem törölhető. Legalább egy hatókörcímkét megadása kötelező.

## <a name="next-steps"></a>További lépések

A [szerepkörök](role-based-access-control.md) és a [profilok](device-profile-assign.md) kezelése.
