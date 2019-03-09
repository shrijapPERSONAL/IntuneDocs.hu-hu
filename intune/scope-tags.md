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
ms.openlocfilehash: 0625968c4f0c30d125be73045a52b58a032b2fd7
ms.sourcegitcommit: a59c78c13c4ff68e8a56b69029adfe51704ba570
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57682623"
---
# <a name="use-rbac-and-scope-tags-for-distributed-it"></a>Rbac-RÓL és a hatókör címkék használata az elosztott IT

Szerepköralapú hozzáférés-vezérlés (RBAC) és a hatókörcímkék segítségével győződjön meg arról, hogy a megfelelő rendszergazdák rendelkeznek-e a megfelelő hozzáférést és látható-e a megfelelő Intune-objektumokhoz. Szerepkörök milyen általi hozzáférés megállapításához, hogy mely objektumok rendszergazdák rendelkeznek. Hatókörcímkék határozza meg, hogy mely objektumok rendszergazdák számára látható.

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
2. Adjon meg egy **nevet** és egy **leírást**.
3. Válassza a **Létrehozás** lehetőséget.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Hatókörcímke hozzárendelése egy szerepkörhöz

1. Válassza ki az Intune-ban **szerepkörök** > **minden szerepkör** > Válassza ki a szerepkört > **hozzárendelések** > **hozzárendelése**.
2. Adjon meg egy **hozzárendelés neve** és **leírás**.
3. Válasszon **tagok (csoportok)** jelölje ki a csoportokat, amelyeket szeretne ehhez a hozzárendeléshez részeként. Ez a csoport felhasználói házirendek és a felhasználók és eszközök a hatókör (csoportok) profilok kezelése engedéllyel rendelkezik majd.
4. Válasszon **hatókör (csoportok)** , és válassza ki a felhasználókat és csoportokat, amelyekhez ezt a hozzárendelést részeként szeretne. Ez a csoport összes felhasználókra vagy eszközökre azok profilok és szabályzatok az Adminisztrátorok a tagok (csoport) által felügyelt lehet.
5. Válasszon **hatókör (címkék)** > **Hozzáadás** > Válassza ki a címkék, amelyeket szeretne hozzáadni ehhez a szerepkörhöz. Tagok (csoportok) a felhasználók hozzáférhetnek a házirendek és profilok –, amelyek az ugyanazon hatókörcímke is rendelkezik.
6. Válassza a **Kiválasztás** > **OK** > **OK** lehetőséget. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Hatókörcímke hozzáadása egy konfigurációs profilhoz
1. Válassza ki az Intune-ban **eszközkonfiguráció** > **profilok** > Válasszon egy profilt > **tulajdonságok** > **hatókör (címkék)**   >  **Hozzáadása**.
2. A **válassza ki a címkék**, válassza ki a címkék, amelyeket szeretne hozzáadni a profil.
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
    - Amikor a rendszergazda létrehoz egy objektumot az Intune-ban, azt a rendszergazdát rendelt összes hatókörcímkék automatikusan rendeli hozzá az új objektumot.
- Intune-os RBAC az Azure Active Directory-szerepkör nem vonatkozik. Így az Intune szolgáltatás-rendszergazdák és a globális Rendszergazdák szerepkör nincs teljes rendszergazdai hozzáféréssel az Intune-hoz, függetlenül attól, milyen hatókörcímkék rendelkeznek.
- A szerepkör-hozzárendelés hatóköre címkékkel rendelkező rendszergazdák nem hatókörcímkék Intune objektumokat is megtekintheti.
- Csak a szerepkör-hozzárendelések rendelkező hatókörcímke rendelhet hozzá.
- Csak olyan célcsoportokat, amelyek szerepelnek a hatókör (csoportok), a szerepkör-hozzárendelés is.
- Ha a szerepkörhöz rendelt hatókörcímke, minden hatókörcímkék egy Intune-objektum nem törölhető. Legalább egy hatókörcímkét megadása kötelező.
- Ha egy felhasználó több szerepkör-hozzárendeléseket, azokat a szerepkör-hozzárendeléseket az engedélyek kiterjesztése a különböző objektumokat a következő:
    - Rendeljen engedélyeket csak az objektumok (például a szabályzatokat vagy alkalmazásokat) az adott szerepkör-hozzárendelési hatókör (csoportok) vonatkoznak. Rendeljen engedélyeket nem vonatkoznak más szerepkör-hozzárendelések objektumokat, ha a többi hozzárendelés kifejezetten megadja számára.
    - Egyéb engedélyek (például a létrehozás és olvasás), sem a felhasználó-hozzárendelés az azonos típusú (például az összes házirend vagy az összes alkalmazás) összes objektumra vonatkozik.
    - Engedélyek (például a szabályzatokat vagy alkalmazásokat) a különböző típusú objektumok egymáshoz nem érvényesek. Olvasási engedély egy házirendet, például egy olvasási engedélyt a felhasználó-hozzárendeléseket az alkalmazások nem biztosít.





## <a name="next-steps"></a>További lépések

A [szerepkörök](role-based-access-control.md) és a [profilok](device-profile-assign.md) kezelése.
