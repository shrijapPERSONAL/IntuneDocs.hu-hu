---
title: "Megfelelőségi szabályzat létrehozása macOS rendszerhez"
titleSuffix: Azure portal
description: "További információ megfelelőségi szabályzat létrehozásáról macOS rendszerhez.”"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0444183e-f924-4605-96a8-48fdfbc58fd1
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3cf085ff2ee4668ea4c14718719c466bcb982b10
ms.sourcegitcommit: d4623cbfe296ae370c3d88c3213fffbda255e474
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2017
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a>macOS-es eszközök megfelelőségi szabályzatainak létrehozása az Intune-nal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>Előkészületek

Az eszközmegfelelőségi szabályzatok létrehozása és hozzárendelése előtt tekintse át az Intune eszközmegfelelőségi szabályzataival kapcsolatos fogalmakat.

- Az eszközmegfelelőségi szabályzatokkal kapcsolatos további információkért lásd [Az Intune eszközmegfelelőségi szabályzatai – első lépések](device-compliance.md) című részt.

> [!IMPORTANT]
> Minden egyes platformhoz létre kell hoznia eszközmegfelelőségi szabályzatokat. Az Intune-os eszközmegfelelőségi szabályzat beállításai a platformképességektől, azaz az MDM protokollon keresztül elérhetővé tett beállításoktól függenek.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

-------------------------------


| **Szabályzat-beállítás** | **macOS 10.11 és újabb verziók** |
| --- | --- |
| **PIN-kód vagy jelszó konfigurálása** | Kijavítva |   
| **Eszköztitkosítás** | Kijavítva (PIN-kód beállításával) |
| **E-mail profil** | Karanténba helyezve |
|**Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** | Karanténba helyezve |  
| **Windows-állapotigazolás** | Nem alkalmazható |  
----------------------------


**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználó kénytelen lesz PIN-kódot beállítani.)

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="macos-compliance-policy-settings"></a>MacOS-es megfelelőségiszabályzat-beállítások

Az új eszközmegfelelőségnek az Intune-nal létrehozásakor választhat a különböző beállításokkal rendelkező különböző kategóriák közül:

- Eszközállapot

- Eszköztulajdonságok

- Rendszerbiztonság

### <a name="device-health"></a>Eszközállapot

- **Rendszerintegritás-védelem megkövetelése** : válassza a **Kötelező** beállítást annak ellenőrzésére, hogy a macOS-es eszközöknél engedélyezve van-e a rendszerintegritás-védelem.

### <a name="device-properties"></a>Eszköztulajdonságok

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó választhatja az eszköz frissítését. Azt követően hozzáférhet a vállalati erőforrásokhoz.

- **Maximális operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

### <a name="system-security-settings"></a>A rendszer biztonsági beállításai

#### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza a **Kötelező** lehetőséget.

- **Egyszerű jelszavak**: Ha engedélyezni szeretné, hogy a felhasználók használhassanak olyan egyszerű jelszavakat, mint az **1234** vagy az **1111**, válassza a **Blokkolás** lehetőséget.

- **Jelszó minimális hossza:** meghatározza a jelszóban szereplő számjegyek vagy karakterek minimális számát.

- **Jelszó típusa**: Meghatározza, hogy a felhasználóknak **alfanumerikus** jelszót vagy **numerikus** jelszót kell-e létrehozniuk.

- **Nem alfanumerikus karakterek száma a jelszóban**: Ha a **Megkövetelt jelszótípus** **Alfanumerikus**, ez a beállítás határozza meg a jelszóban használandó karakterkészletek minimális számát. 

    > [!NOTE]
    > Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

    > [!IMPORTANT]
    > A macOS-eszközök esetében ez a beállítás a speciális karakterek minimális számára utal, például: **!** **#** , **&amp;**), amelynek szerepelnie kell a jelszóban.

- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap (1–250 között) elteltével járjon le a jelszó, ami után újat kell létrehoznia.

- **Újból nem használható jelszavak száma**: Meghatározza, hogy hány korábbi jelszó ne legyen újra felhasználható.

    > [!IMPORTANT]
    > Ha macOS-eszközön megváltozik a jelszóra vonatkozó követelmény, akkor az csak akkor lép érvénybe, amikor a felhasználó legközelebb megváltoztatja jelszavát. Például ha a jelszó kötelező minimális hosszát 8 számjegyűre állítja át, és a macOS-eszköz jelenlegi jelszava 6 számjegyű, az eszköz egészen addig megfelelőnek minősül, amíg a felhasználó legközelebb meg nem változtatja az eszköz jelszavát.

## <a name="to-create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozásához

1. Az [Azure Portalon](https://portal.azure.com) jelentkezzen be az Intune-os hitelesítő adataival.

2. Miután sikeresen bejelentkezett, megjelenik az **Azure irányítópultja**.

3. Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

4. Az **Intune** kiválasztásával megjelenik az **Intune irányítópultja**.

5. Válassza az **Eszközmegfelelőség** elemet, majd a **Kezelés** csoportban válassza a **Házirendek** lehetőséget.

6. Válassza a **Házirend létrehozása** lehetőséget.

7. Írjon be egy nevet és egy leírást, és válassza ki azt a platformot, amelyre ez a szabályzat vonatkozik.

8. A megjelenő **macOS rendszerű megfelelőségi szabályzat** panelen válassza ki az eszközmegfelelőségi beállításkategóriákat (**Biztonság**, **Eszközállapot** és **Eszköztulajdonság**) a saját beállítások meghatározásához.

10. Ha elkészült a beállítások kiválasztásával, kattintson az **OK** gombra az egyes eszközmegfelelőségi beállításkategóriák alatt.

11. Válassza az **OK**, majd a **Létrehozás** gombot.

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

A megfelelőségi szabályzatok felhasználókhoz való hozzárendeléséhez válasszon egy már konfigurált szabályzatot. A meglévő szabályzatok a **Megfelelőségi szabályzatok** panelen találhatók.

1. Válassza ki azt az eszközmegfelelőségi szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt **Azure Active Directory-beli biztonsági csoportokat**, és hozzárendelheti őket a szabályzathoz.

2. Válassza a **Csoportok kiválasztása** lehetőséget az Azure AD biztonsági csoportjait megjelenítő panel megnyitásához.

3. Válassza a **Kijelölés**, majd a **Mentés** gombot az eszközmegfelelőségi szabályzat Azure AD biztonsági csoportokhoz rendelésére.

4. Miután befejezte az eszközmegfelelőségi szabályzat hozzárendelése a csoportokhoz, bezárhatja a **Hozzárendelések** panelt.

    > [!TIP]
    > Alapértelmezés szerint az eszközök 8 óránként ellenőrzik a megfelelőséget, de a felhasználók kényszeríthetik ezt a folyamatot az Intune Céges portál alkalmazás használatával.

## <a name="next-steps"></a>További lépések

[Az eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)
