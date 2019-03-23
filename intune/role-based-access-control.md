---
title: RBAC a Microsoft Intune-nal
description: Megtudhatja, hogyan szabhatja meg a Szerepköralapú hozzáférés-vezérléssel, hogy mely felhasználók hajthatnak végre műveleteket és végezhetnek módosításokat a Microsoft Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: ecc315bfcccc5d3b71107e80720d39e675d42d19
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394658"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Szerepköralapú hozzáférés-vezérlés (RBAC) a Microsoft Intune-nal

Az RBAC lehetővé teszi annak szabályozását, hogy a cégen belül ki hajthat végre különböző Intune-feladatokat, és kikre vonatkozhatnak az adott feladatok. A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat. Egy szerepkört a következők határoznak meg:

- **Szerepkör-definíció**: A szerepkör által kezelt erőforrások és az egyes erőforrásokhoz rendelt engedélyek neve.
- **A tagok**: A felhasználói csoportok, amelyek az engedélyekkel.
- **Hatókör (csoportok)**: A felhasználói vagy eszközcsoportok, hogy a tagok kezelhetnek.
- **[Hatókör (címkék)](https://docs.microsoft.com/intune/scope-tags)**: Ha a szerepkör-hozzárendelés alkalmazandó címkék.
- **Hozzárendelés**: Ha a definíció, a tagok és a hatókör konfigurálása megtörtént, a szerepkör van hozzárendelve.

![Példa az Intune-beli RBAC felépítésére](./media/intune-rbac-1.PNG)

## <a name="azure-active-directory-roles-with-intune-access"></a>Az Intune hozzáférés az Azure Active Directory-szerepkör

| Az Azure Active Directory-szerepkör | Az összes Intune-beli adatokhoz | Az Intune-naplóadatok |
| --- | :---: | :---: |
| Globális rendszergazda | Olvasási/írási | Olvasási/írási |
| Az Intune szolgáltatás Aministrator | Olvasási/írási | Olvasási/írási |
| Feltételes hozzáférésű rendszergazda | Nincsenek | Nincsenek |
| Biztonsági rendszergazda | Csak olvasható | Csak olvasható |
| Biztonsági operátor | Csak olvasható | Csak olvasható |
| Biztonsági olvasó | Csak olvasható | Csak olvasható |
| Globális olvasó | Csak olvasható | Csak olvasható |
| Szabályozási ügyintéző | Nincsenek | Csak olvasható |
| Megfelelőségi adatok rendszergazda | Nincsenek | Csak olvasható |

**Az Azure Active Directory (Azure AD)** két az Intune-nal használható címtárbeli szerepkört kínál. Ezek a szerepkörök teljes körű engedélyt biztosítanak minden Intune-beli tevékenységhez:

- **Globális rendszergazda:** Ezzel a szerepkörrel rendelkező felhasználók hozzáférhetnek az Azure AD minden felügyeleti funkciójához, valamint szolgáltatások, amely val összevont, az Azure AD, mint például az Exchange Online, SharePoint Online és Skype vállalati online. Az a személy lesz globális rendszergazda, aki regisztrált az Azure AD-bérlőre. Csak a globális rendszergazdák oszthatnak ki további Azure AD-rendszergazdai szerepköröket. A szervezetnek egynél több globális rendszergazdája is lehet. A globális rendszergazdák bármely felhasználó és az összes többi rendszergazda jelszavát is alaphelyzetbe állíthatják.

- **Az Intune szolgáltatás-rendszergazda:** Ezzel a szerepkörrel rendelkező felhasználók az Intune globális engedélyekkel rendelkeznek, ha a szolgáltatás nem található. A szerepkör emellett, ha nincsenek érvényben az Azure-ban ezt felülíró korlátozások, feljogosít a felhasználók és eszközök felügyeletére, valamint Intune-csoportok létrehozására és felügyeletére.

- **Feltételes hozzáférésű rendszergazda:** Ezzel a szerepkörrel rendelkező felhasználók csak engedélye megtekintése, létrehozása, módosítása és törlése a feltételes hozzáférési szabályzatokat.

    > [!IMPORTANT]
    > Az Intune-beli szolgáltatás-rendszergazdai szerepkör nem teszi lehetővé az Azure AD feltételes hozzáférési beállításainak felügyeletét.
    >
    > Az Intune-szerepkörhöz hozzárendelni, a felhasználó Intune-licenccel kell rendelkeznie.

    > [!TIP]
    > Intune-ban három olyan Azure AD-bővítmény látható: **Felhasználók**, **csoportok**, és **feltételes hozzáférési**, amely Azure AD RBAC segítségével szabályozhat. A **Felhasználóifiók-adminisztrátori** szerepkör csak az Azure AD-felhasználói vagy -csoporttevékenységek végrehajtására jogosít fel, és nem biztosít teljes körű engedélyt az összes Intune-beli tevékenységhez. További információkért lásd: [az Azure AD RBAC](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).

## <a name="roles-created-in-the-intune-classic-portal"></a>Klasszikus Intune-portálon létrehozott szerepkörök

Csak a „Teljes körű” engedéllyel rendelkező Intune-beli **szolgáltatás-rendszergazdákat** migrálja a rendszer a klasszikus Intune-portálról az Azure Portalbeli Intune-ba. Intune-ban kell újbóli **szolgáltatás-rendszergazdák** felhasználók "Csak Olvasás" vagy "Ügyfélszolgálat" hozzáféréssel az Intune-szerepkörök az Azure Portalon, és távolítsa el őket a klasszikus portálról.

> [!IMPORTANT]
> Szüksége lehet az Intune szolgáltatás-rendszergazda hozzáférést tartani a klasszikus portálon, ha a rendszergazdák továbbra is hozzáférhetnek a számítógépek az Intune-nal kezelheti.

## <a name="built-in-roles"></a>Beépített szerepkörök

Beépített szerepkörök további konfiguráció nélkül csoportokhoz is hozzárendelhet. Nem lehet törölni, vagy szerkesztheti egy beépített szerepkör.

- **Ügyfélszolgálat**: A felhasználók és eszközök távoli feladatokat hajtja végre, és alkalmazásokat és szabályzatokat rendelhet a felhasználókhoz vagy eszközökhöz.
- **A házirend- és Profilkezelő**: Megfelelőségi szabályzat, konfigurációs profilokat, az Apple regisztrációs, cégeseszköz-azonosítók és biztonsági előírások kezeli.
- **Csak olvasási operátor**: Nézetek felhasználói, eszköz, regisztráció, konfigurációs és alkalmazással kapcsolatos adatok. Az Intune-hoz nem végezhet módosításokat.
- **Application Manager**: Kezeli a mobil- és felügyelt alkalmazásokat, olvashatja az eszközadatokat, és megtekintheti az eszközkonfigurációs profilok.
- **Intune-rendszergazda szerepkör**: Egyéni Intune-szerepkörök kezeli, és hozzáadja a beépített Intune-szerepkörök hozzárendeléseit. A csak az Intune-szerepkör, amely a rendszergazdák engedélyeket rendelhet.
- **Iskolai rendszergazda**: Kezeli a Windows 10 rendszerű eszközökhöz az [az Intune for Education](introduction-intune-education.md), és a következő műveleteket hajthatja végre: 

    |Engedély|Művelet|
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

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az a **Intune** panelen válassza a **szerepkörök** > **minden szerepkör**.
4. Az a **az Intune-szerepkörök – minden szerepkör** panelen válassza ki a hozzárendelni kívánt szerepkört.

5. Az a <*szerepkörnév*>- **áttekintése** panelen válassza a **kezelés** > **hozzárendelések**.

6. Kattintson a **Hozzárendelés** elemre az Egyéni szerepkör panelen.

7. Az a **szerepkör-hozzárendelések** panelen adjon meg egy **hozzárendelés neve** és választható **hozzárendelés leírása** a hozzárendelés.

8. A **tagok (csoportok)**, válasszon egy csoportot, amely tartalmazza azt a felhasználót szeretne adni az engedélyeket.

9. A **hatókör (csoportok)**, válassza ki a csoport tartalmazza a felhasználókat, akik a fenti tag kezelése engedélyezve lesz.

10. A **hatókör (címkék)**, válassza ki a címkét, ahol a szerepkör-hozzárendelési alkalmazza.

11. Ha elkészült, válassza az **OK** gombot. Az új hozzárendelés megjelenik a hozzárendelések listájában.

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

3. Válasszon **Intune** > **szerepkörök** > **minden szerepkör** > **Hozzáadás**.

4. Az **Egyéni szerepkör hozzáadása** panelen adja meg az új szerepkör nevét és leírását, majd kattintson az **Engedélyek** elemre.

5. Az **Engedélyek** panelen válassza ki az ehhez a szerepkörhöz használni kívánt engedélyeket. Az [Intune-os RBAC-táblázat](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) segít eldönteni, hogy milyen engedélyeket alkalmazzon.

6. Az a **hatókör (címkék)** panelen válassza ki a címkét, ahol az egyéni szerepkör alkalmazza.

7. Ha elkészült, válassza az **OK** gombot.

7. Az **Egyéni szerepkör hozzáadása** panelen kattintson a **Létrehozás** elemre. Az új szerepkör megjelenik a listában a **az Intune-szerepkörök – minden szerepkör** panelen.

### <a name="to-assign-a-custom-role"></a>Egyéni szerepkör hozzárendelése

Ugyanazokat a lépéseket követve [beépített szerepkör hozzárendelése](https://docs.microsoft.com/intune/role-based-access-control#to-assign-a-built-in-role) , és válassza ki az egyéni szerepkör.

## <a name="next-steps"></a>További lépések

- [Az Intune Ügyfélszolgálat szerepkörének használata a hibaelhárítási portállal](help-desk-operators.md)



## <a name="see-also"></a>Lásd még:

- [Szerepkörök hozzárendelése az Azure AD használatával](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
- Ismerje meg [szerepköralapú hozzáférés az Intune-ban a Microsoft Graph API támogatása](https://docs.microsoft.com/graph/api/resources/intune-rbac-roledefinition?view=graph-rest-1.0)
- Első a [PowerShell SDK esetében az Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10)