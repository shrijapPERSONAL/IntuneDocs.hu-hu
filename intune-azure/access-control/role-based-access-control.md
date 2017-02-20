---
title: "Szerepköralapú hozzáférés-vezérlés (RBAC) a Microsoft Intune-hoz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: megtudhatja, hogyan teszi lehetővé a szerepköralapú hozzáférés-vezérlés annak szabályozását, hogy ki hajthat végre műveletet és végezhet módosításokat."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: db0f88db8eee33781ccf3ef54e34089a25118726


---

# <a name="role-based-access-control-rbac-for-microsoft-intune"></a>Szerepköralapú hozzáférés-vezérlés (RBAC) a Microsoft Intune-hoz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Egyszerűen fogalmazva az Intune-os **szerepkörök** (vagy RBAC) segítségével szabályozhatja, hogy kik hajthat végre különböző műveleteket az Intune-ban, és kikre vonatkozzanak ezen műveletek. A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat.

Egy szerepkört a következők határoznak meg:

- **Definíció** – A szerepkör neve és az általa konfigurált engedélyek.
- **Tagok** – Az a felhasználó vagy felhasználók csoportja, aki vagy akik megkapják ezeket az engedélyeket.
- **Hatókör** – Azok a felhasználók vagy eszközök, akiket, illetve amelyeket a megadott személy (tag) kezelhet.
- **Hozzárendelés** – Amikor megtörtént a definíció, a tagok és a hatókör konfigurálása, a szerepkör hozzá van rendelve.

## <a name="built-in-roles"></a>Beépített szerepkörök

A következő szerepkörök az Intune beépített szerepkörei, amelyek testreszabhatók, vagy további konfiguráció nélkül csoportokhoz rendelhetők.

- **Intune-rendszergazda** – Az összes Intune-műveletre vonatkozó teljes körű engedélyekkel rendelkezik.
- **Alkalmazás-kezelő** – Az alkalmazások és a profilok kezelésére és telepítésére jogosult.
- **Konfigurációs szabályzat kezelője** – A konfigurációs beállítások és a profilok központi telepítésére és kezelésére jogosult.
- **Segélyszolgálati operátor** – Távoli feladatokat hajthat végre, és megtekintheti a felhasználók és az eszközök adatait.
- **Csak olvasási operátor** –Módosítások nélkül megtekintheti az információkat az Intune-portálon.


## <a name="custom-roles"></a>Egyéni szerepkörök

Ha a beépített szerepkörök egyike sem felel meg igényeinek, az Intune számos képességére kiterjedő beállítások kiválasztásával saját szerepkört is létrehozhat. A rendelkezésre álló beállítások listája a témakör későbbi részében található.

### <a name="example"></a>Példa

Egy új rendszergazdát vesz fel, akinek feladata alkalmazások telepítése és kezelése a felhasználók részére, londoni irodájában. A felhasználók a **London** nevű Azure AD-csoport tagjai. Szeretné biztosítani, hogy a rendszergazda ne telepíthessen alkalmazásokat bármelyik más iroda felhasználói részére is. Végezze el a következő műveleteket:

- Rendelje hozzá a beépített **Alkalmazáskezelő** szerepkört a következő tulajdonságokkal:
    - **Tagok** – Válasszon ki egy olyan csoportot, amely tartalmazza azt a rendszergazdát, aki az alkalmazások telepítését végzi majd
    - **Hatókör** – Válassza ki a **London** Azure AD-csoportot.

    >[!IMPORTANT]
    >A szerepkörök létrehozásához, szerkesztéséhez vagy hozzárendeléséhez a fióknak rendelkeznie kell a következő jogosultságok egyikével az Azure AD-ben:
    >- **Globális AAD-rendszergazda**
    >- **Intune szolgáltatásadminisztrátor**

### <a name="how-to-create-a-custom-role"></a>Egyéni szerepkör létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + Felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza a **Hozzáférés-vezérlés** lehetőséget.
![Hozzáférés-vezérlés munkafolyamat](./media/axxess-control.png)
1. A **Hozzáférés-vezérlés** munkafolyamatban, a **Szerepkörök** panelen válassza az **Egyéni hozzáadása** elemet.
2. Az **Egyéni szerepkör hozzáadása** panelen írja be az új szerepkör nevét és leírását, és kattintson az **Engedélyek** elemre.
3. Az **Engedélyek** panelen válassza ki az ehhez a szerepkörhöz használni kívánt engedélyeket. A témakör későbbi részében megtalálja az egyéni szerepkör beállítások hivatkozási listáját segítségként.
4. Amikor elkészült, kattintson az **OK**gombra.
5. Az **Egyéni szerepkör hozzáadása** panelen kattintson a **Létrehozás** elemre.

Az új szerepkör ekkor megjelenik a **Szerepkörök** panel listájában.

## <a name="how-to-assign-a-role"></a>Szerepkör hozzárendelése

1. A **Hozzáférés-vezérlés** munkafolyamatban, a **Szerepkörök** panelen válassza ki a hozzárendelni kívánt beépített vagy egyéni szerepkört.
2. A *szerepkörnév*>- **Tulajdonságok** panelen válassza a **Felügyelet** > **Hozzárendelések** elemet.
    >[!TIP]
    >A panelen szerkesztheti és törölheti is a meglévő szerepköröket.
3. Válassza ki a következő panelen a **Hozzárendelés** elemet.
4. A **Szerepkör-hozzárendelések** panelen adja meg a hozzárendelés **nevét** és választható **leírását**, és válassza ki a következőket:
    - **Tagok** – Válasszon ki egy csoportot, amely tartalmazza azt a felhasználót, akinek meg szeretné adni az engedélyeket.
    - **Hatókör** – Válassza ki az azon felhasználókat tartalmazó csoportot, akik kezelése a fenti tag számára engedélyezett lesz.
5. Amikor elkészült, kattintson az **OK**gombra.

Az új hozzárendelés megjelenik a hozzárendelések listájában.

## <a name="custom-role-settings-reference"></a>Egyéni szerepkör-beállítások ismertetése

Amikor létrehoz egy egyéni biztonsági szerepkört, konfigurálhat egyet vagy többet az alábbi beállítások közül:

### <a name="device-configurations"></a>Eszközkonfigurációk

|||
|-|-|
|**Hozzárendelés**|Eszközprofilok hozzárendelése a csoportokhoz.|
|**Létrehozás**|Eszközprofilok létrehozása.|
|**Törlés**|Eszközprofilok törlése.|
|**Olvasás**|Az eszközprofilok és azok tulajdonságainak elolvasása.|
|**Frissítés**|A meglévő eszközprofilok frissítése.|

### <a name="managed-apps"></a>Felügyelt alkalmazások

|||
|-|-|
|**Hozzárendelés**|Felügyelt alkalmazások hozzárendelése csoportokhoz.|
|**Létrehozás**|Új felügyelt alkalmazások hozzáadása az Intune-hoz.|
|**Törlés**|Felügyelt alkalmazások törlése.|
|**Olvasás**|A felügyelt alkalmazások és azok tulajdonságainak elolvasása.|
|**Frissítés**|Meglévő felügyelt alkalmazások frissítése.|
|**Törlés**|Felügyelt alkalmazások törlése az eszközökről.|

### <a name="managed-devices"></a>Felügyelt eszközök

|||
|-|-|
|**Törlés**|A felügyelt eszközök törlése az Intune-ból.|
|**Olvasás**|Az Intune-portál felügyelt eszközökre vonatkozó információinak megtekintése.|
|**Frissítés**|A felügyelt eszközök frissítési adatai.|

### <a name="mobile-apps"></a>Mobilalkalmazásokban

|||
|-|-|
|**Hozzárendelés**|Mobilalkalmazások hozzárendelése a csoportokhoz.|
|**Létrehozás**|Új mobilalkalmazások hozzáadása az Intune-hoz.|
|**Törlés**|Mobilalkalmazások törlése.|
|**Olvasás**|A mobilalkalmazások és azok tulajdonságainak elolvasása.|
|**Frissítés**|A meglévő mobilalkalmazások frissítése.|

### <a name="organization"></a>Szervezet

|||
|-|-|
|**Olvasás**|Bérlői beállítások beolvasása.|
|**Frissítés**|Bérlői beállítások frissítése.|

### <a name="remote-tasks"></a>Távoli feladatok

|||
|-|-|
|**Az aktiválási zár megkerülése**|A felhasználó Apple azonosítója és jelszava nélkül távolítja el az aktiválási zárat az iOS-eszközről. |
|**Elveszett mód letiltása**|Elveszett mód letiltása. Ez eszköz elvesztése esetére megadható egy üzenet és egy telefonszám, amely megjelenik az eszköz zárolási képernyőjén.|
|**Elveszett mód engedélyezése**|Elveszett mód engedélyezése. Ez eszköz elvesztése esetére megadható egy üzenet és egy telefonszám, amely megjelenik az eszköz zárolási képernyőjén.|
|**Eszköz megkeresése**|-|
|**Újraindítás most**|Kiváltja az eszköz újraindulását.|
|**Távoli zárolás**|Zárolja az eszközt. Az eszköz zárolását a tulajdonosnak a PIN-kódjával vagy jelszavával kell feloldania.|
|**Jelszó alaphelyzetbe állítása**|Új PIN-kódot generál az eszközhöz, amely az <device name>Áttekintés panelen jelenik meg.|
|**Kivonás**|Csak az Intune által kezelt céges adatokat távolítja el. Személyes adatokat nem távolít el az eszközről.|
|**Törlés**|Visszaállítja az eszköz alapbeállításait.|



### <a name="telecom-expenses"></a>Távközlési költségek

|||
|-|-|
|**Olvasás**|Távközlésiköltség-kezelés (TEM) beállításainak elolvasása.|
|**Frissítés**|Távközlésiköltség-kezelés (TEM) beállításainak frissítése.|

### <a name="terms-and-conditions"></a>használati feltételei

|||
|-|-|
|**Hozzárendelés**|Feltételek és kikötések hozzárendelése a csoportokhoz.|
|**Létrehozás**|Létrehozza a használati feltételek beállításait.|
|**Törlés**|Törli a használati feltételek beállításait.|
|**Olvasás**|A használati feltételek beállításainak elolvasása az Intune-portálon.|
|**Frissítés**|A meglévő használati feltételek beállításainak frissítése.|


<!--HONumber=Feb17_HO1-->


