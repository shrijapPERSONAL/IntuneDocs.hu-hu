---
title: RBAC a Microsoft Intune-nal
description: Megtudhatja, hogyan szabhatja meg a Szerepköralapú hozzáférés-vezérléssel, hogy mely felhasználók hajthatnak végre műveleteket és végezhetnek módosításokat a Microsoft Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/17/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8cce5da762c119ec04553d80d717fb586c962566
ms.sourcegitcommit: 698bd1488be3a269bb88c077eb8d99df6e552a9a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2018
---
# <a name="role-based-administration-control-rbac-with-microsoft-intune"></a>Szerepköralapú hozzáférés-vezérlés (RBAC) a Microsoft Intune-nal

Az RBAC lehetővé teszi annak szabályozását, hogy a cégen belül ki hajthat végre különböző Intune-feladatokat, és kikre vonatkozhatnak az adott feladatok. A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat. Egy szerepkört a következők határoznak meg:

- **Szerepkör-definíció**: a szerepkör neve, a szerepkör által kezelt erőforrások és az egyes erőforrásokhoz rendelt engedélyek.
- **Tagok**: Az engedélyekkel rendelkező felhasználói csoportok.
- **Hatókör**: Azok a felhasználói vagy eszközcsoportok, amelyeken a tagok alkalmazások vagy szabályzatok üzembe helyezését végezhetik, vagy távoli műveleteket hajthatnak végre.
- **Feladat**: A definíció, a tagok és a hatókör konfigurálása után feladat rendelhető a szerepkörköz.

![Példa az Intune-beli RBAC felépítésére](./media/intune-rbac-1.PNG)

Az új Azure Portaltól kezdődően az **Azure Active Directory (Azure AD)** két, Intune-nal használható címtárbeli szerepkört kínál fel. Ezek a szerepkörök teljes körű engedélyt biztosítanak minden Intune-beli tevékenységhez:

- **Globális rendszergazda:** Az ezzel a szerepkörrel rendelkező felhasználók hozzáférnek az Azure AD minden felügyeleti funkciójához, valamint olyan, az Azure AD-val összevont szolgáltatásokhoz is, mint az Exchange Online, a SharePoint Online és a Skype Vállalati online verzió. Az a személy lesz globális rendszergazda, aki regisztrált az Azure AD-bérlőre. Csak a globális rendszergazdák oszthatnak ki további Azure AD-rendszergazdai szerepköröket. A szervezetnek egynél több globális rendszergazdája is lehet. A globális rendszergazdák bármely felhasználó és az összes többi rendszergazda jelszavát is alaphelyzetbe állíthatják.

- **Intune-beli szolgáltatás-rendszergazda:** Az ezzel a szerepkörrel rendelkező felhasználók az Intune-szolgáltatás megléte esetén globális engedélyt kapnak az Intune-ban. A szerepkör emellett, ha nincsenek érvényben az Azure-ban ezt felülíró korlátozások, feljogosít a felhasználók és eszközök felügyeletére, valamint Intune-csoportok létrehozására és felügyeletére.

- **Feltételes hozzáférésű rendszergazda:** A felhasználók ezzel a szerepkörrel csak a feltételes hozzáférési szabályzatok megtekintésére, létrehozására és törlésére rendelkeznek jogosultságokkal.

    > [!IMPORTANT]
    > Az Intune-beli szolgáltatás-rendszergazdai szerepkör nem teszi lehetővé az Azure AD feltételes hozzáférési beállításainak felügyeletét.

    > [!TIP]
    > Az Intune-ban három olyan Azure AD-bővítmény látható (**Felhasználók**, **Csoportok** és **Feltételes hozzáférés**), amelyeket az Azure AD RBAC segítségével szabályozhat. A **Felhasználóifiók-adminisztrátori** szerepkör csak az Azure AD-felhasználói vagy -csoporttevékenységek végrehajtására jogosít fel, és nem biztosít teljes körű engedélyt az összes Intune-beli tevékenységhez. További információkért tekintse meg a [Szerepköralapú hozzáférés-vezérlés (RBAC) az Azure AD-vel](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) című cikket.

## <a name="roles-created-in-the-intune-classic-portal"></a>Klasszikus Intune-portálon létrehozott szerepkörök

Csak a „Teljes körű” engedéllyel rendelkező Intune-beli **szolgáltatás-rendszergazdákat** migrálja a rendszer a klasszikus Intune-portálról az Azure Portalbeli Intune-ba. Az Intune-beli **szolgáltatás-rendszergazdákat** „Csak olvasási" vagy „Ügyfélszolgálat" hozzáféréssel újra hozzá kell rendelni az Azure Portalon található Intune-szerepkörökhöz, és el kell távolítani őket a klasszikus portálról.

> [!IMPORTANT]
> Az Intune-beli szolgáltatás-rendszergazdai szerepkör hozzáférését szükség esetén fenn lehet tartani a klasszikus portálon, ha a rendszergazdáknak Windows rendszerű gépek Intune-alapú felügyeletéhez továbbra is hozzá kell férniük ahhoz.

## <a name="built-in-roles"></a>Beépített szerepkörök

A következő szerepköröket beépített szerepkörként tartalmazza az Intune, és további konfiguráció nélkül rendelhetők hozzá a csoportokhoz:

- **Ügyfélszolgálat**: Távoli feladatokat hajt végre felhasználókon és eszközökön, valamint alkalmazásokat és szabályzatokat rendelhet hozzájuk.
- **Szabályzat- és profilkezelő**: A megfelelőségi szabályzatot, a konfigurációs profilokat, az Apple-regisztrációt és a céges eszközazonosítókat kezeli.
- **Csak olvasási jogosultságú operátor**: Megtekintheti a felhasználókra, regisztrációra, konfigurációra és alkalmazásokra vonatkozó információkat. Az Intune-ban nem hajthat végre változtatásokat.
- **Alkalmazáskezelő**: Kezeli a mobil- és felügyelt alkalmazásokat, és olvashatja az eszközadatokat.
- **Iskolai rendszergazda**: Az [Intune for Education](introduction-intune-education.md) Windows 10-eszközeit kezeli, és az alábbi műveleteket hajthatja végre: 

|Engedély|Működés|
|---|---|
|Adatnaplózás|Olvasás|
|DeviceConfigurations|Hozzárendelés, létrehozás, törlés, olvasás, frissítés|
|Eszközregisztráció-kezelők|Olvasás, frissítés|
|Kezelt eszközök|Olvasás, frissítés<!--, Delete [To be added in 1803]-->|
|Mobilalkalmazásokban|Hozzárendelés, létrehozás, törlés, olvasás, frissítés|
|Reports|Olvasás|
|Távoli műveletek|Számítógép megtisztítása, újraindítás, távoli zárolás, kivonás, eszközszinkronizálás, törlés|
|Szervezet|Olvasás|

### <a name="to-assign-a-built-in-role"></a>Beépített szerepkör hozzárendelése

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Intune-szerepkörök**, majd a **Minden szerepkör** lehetőséget.
4. Válassza ki a hozzárendelni kívánt szerepkört az **Intune-szerepkörök – Minden szerepkör** panelen.

5. A <*szerepkör neve*> – **Áttekintés** panelen válassza a **Hozzárendelések** > **Hozzárendelés** lehetőséget.

    > [!NOTE]
    > A beépített szerepkörök nem törölhetők és nem szerkeszthetők

6. A **Szerepkör-hozzárendelések** panelen töltse ki a **Hozzárendelés neve** és igény esetén a **Hozzárendelés leírása** mezőt, majd végezze el a következőket:
    - **Tagok** – Válasszon ki egy csoportot, amely tartalmazza azt a felhasználót, akinek meg szeretné adni az engedélyeket.
    - **Hatókör** – Válassza ki az azon felhasználókat tartalmazó csoportot, akik kezelése a fenti tag számára engedélyezett lesz. A hatókört a **Minden felhasználó**, a **Minden eszköz** vagy a **Minden felhasználó és eszköz** értékre is állíthatja.
<br></br>
7. Amikor elkészült, kattintson az **OK**gombra. Az új hozzárendelés megjelenik a hozzárendelések listájában.

### <a name="intune-rbac-table"></a>Intune-os RBAC-táblázat

- Töltse le az [Intune-os RBAC-táblázatot](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) az egyes szerepkörök lehetőségeinek részletesebb megtekintéséhez.

## <a name="custom-roles"></a>Egyéni szerepkörök

Egyéni szerepkört is létrehozhat, amely az adott munkakörhöz szükséges összes engedélyt tartalmazza. Például ha egy IT-részleg alkalmazásokat, szabályzatokat, és konfigurációs profilokat kezel, mindezeket az engedélyeket együtt adhatja meg egy egyéni szerepkör segítségével.

> [!IMPORTANT]
> A szerepkörök létrehozásához, szerkesztéséhez vagy hozzárendeléséhez a fióknak rendelkeznie kell a következő jogosultságok egyikével az Azure AD-ben:
> - **Globális rendszergazda**
> - **Intune-beli szolgáltatás-rendszergazda**

### <a name="to-create-a-custom-role"></a>Egyéni szerepkör létrehozása

1. Jelentkezzen be az [Azure Portalon](https://portal.azure.com) az Intune-os hitelesítő adataival.

2. Válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Az **Intune** lehetőség választásával nyissa meg az Intune irányítópultot, és kattintson az **Intune-szerepkörök** elemre.

4. Az **Intune-szerepkörök** panelen kattintson a **Minden szerepkör** elemre, majd válassza az **Egyéni hozzáadása** lehetőséget.

5. Az **Egyéni szerepkör hozzáadása** panelen adja meg az új szerepkör nevét és leírását, majd kattintson az **Engedélyek** elemre.

3. Az **Engedélyek** panelen válassza ki az ehhez a szerepkörhöz használni kívánt engedélyeket. Az [Intune-os RBAC-táblázat](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) segít eldönteni, hogy milyen engedélyeket alkalmazzon.

4. Ha elkészült, válassza az **OK** elemet.

5. Az **Egyéni szerepkör hozzáadása** panelen kattintson a **Létrehozás** elemre. Az új szerepkör megjelenik az **Intune-szerepkörök – Minden szerepkör** panel listájában.

### <a name="to-assign-a-custom-role"></a>Egyéni szerepkör hozzárendelése

1. Válassza ki a hozzárendelni kívánt egyéni szerepkört az **Intune-szerepkörök – Minden szerepkör** panelen.

2. A <*szerepkör neve*> – **Áttekintés** panelen válassza a **Hozzárendelések** lehetőséget. A panelen szerkesztheti és törölheti is a meglévő szerepköröket.

3. Kattintson a **Hozzárendelés** elemre az Egyéni szerepkör panelen.

4. A **Szerepkör-hozzárendelések** panelen adja meg a hozzárendelés **nevét** és választható **leírását**, és válassza ki a következőket:
    - **Tagok** – Válasszon ki egy csoportot, amely tartalmazza azt a felhasználót, akinek meg szeretné adni az engedélyeket.
    - **Hatókör** – Válassza ki az azon felhasználókat tartalmazó csoportot, akik kezelése a fenti tag számára engedélyezett lesz. A hatókört a **Minden felhasználó**, a **Minden eszköz** vagy a **Minden felhasználó és eszköz** értékre is állíthatja.
<br></br>
5. Amikor elkészült, kattintson az **OK**gombra. Az új hozzárendelés megjelenik a hozzárendelések listájában.

## <a name="next-steps"></a>További lépések

[Az Intune Ügyfélszolgálat szerepkörének használata a hibaelhárítási portállal](help-desk-operators.md)

## <a name="see-also"></a>Lásd még:

[Szerepkörök hozzárendelése az Azure AD használatával](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)


