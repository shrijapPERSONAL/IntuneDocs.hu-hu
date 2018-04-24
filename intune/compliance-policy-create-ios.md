---
title: IOS-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Létrehozhat Microsoft Intune-beli eszközmegfelelőségi szabályzatokat iOS-eszközökhöz e-mail-fiók megadásához, feltört eszközök ellenőrzéséhez, az operációs rendszer használható minimális és maximális verziójának ellenőrzéséhez, valamint a jelszókorlátozásoknak, például a jelszó hosszának és az eszköz inaktivitási idejének a beállításához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 887f45cdc79aa5e45de3e8a1df5d12665d2ed8ab
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>iOS-es eszközök megfelelőségi szabályzatainak felvétele az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune iOS-eszközmegfelelőségi szabályzataival megszabhatja az iOS-eszközök megfelelőségéhez kötelezően szükséges szabályokat és beállításokat. Az eszközmegfelelőségi szabályzatokat a feltételes hozzáféréssel használva engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén. Az Intune Azure Portalon minden platformhoz létrehozhat megfelelőségi szabályzatokat. A megfelelőségi szabályzatokról és a létrehozásuk előtt teljesítendő előfeltételekről az [Eszközmegfelelőség használatának első lépései](device-compliance-get-started.md) című témakörben találhat további információt.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

| **Szabályzat-beállítás** | **iOS 8.0 vagy újabb** |
| --- | --- |
| **PIN-kód vagy jelszó konfigurálása** | Kijavítva |
| **Eszköztitkosítás** | Kijavítva (PIN-kód beállításával) |
| **Jailbreakelt vagy rootolt eszköz** | Karanténba helyezve (nem beállítás)
| **E-mail profil** | Karanténba helyezve |
|**Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** | Karanténba helyezve |
| **Windows-állapotigazolás** | Nem alkalmazható |

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználó kénytelen lesz PIN-kódot beállítani.)

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Megfelelőségi szabályzat létrehozása az Azure Portal webhelyen

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** lehetőséget.
4. Adjon meg egy nevet és egy leírást, és válassza ki azt a platformot, amelyre ez a szabályzat vonatkozik.
5. Válassza a **Beállítások** lehetőséget az **E-mail**, **Eszközállapot****Eszköztulajdonságok** és **Rendszerbiztonság** beállításainak megadásához. Ha elkészült, válassza az **OK** gombot.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

A megfelelőségi szabályzatok felhasználókhoz való hozzárendeléséhez válasszon egy már konfigurált szabályzatot. A meglévő szabályzatokat az **Eszközmegfelelőségi szabályzatok** panelen tekintheti meg.

1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt **Azure Active Directory-biztonsági csoportokat**, és hozzárendelheti azokat a szabályzathoz.
2. A **Kiválasztott csoportok** elemre kattintva nyissa meg az Azure AD-biztonsági csoportokat megjelenítő panelt.  A **Mentés** elemet választva telepítheti a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára.  A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

<!---## Compliance policy settings--->

## <a name="email"></a>E-mail

- **Csak az Intune által felügyelt e-mail fiók használható:** Ha **Igen** értékre állítja a beállítást, az eszköznek az eszközre telepített e-mail-fiókot kell használnia. Az eszköz a következő esetekben számít nem megfelelőnek:
  - Az e-mail-profil nem a megfelelőségi szabályzat által célzott felhasználócsoporttól különböző felhasználócsoportnál van telepítve.
  - A felhasználó már beállított egy, az eszközre telepített Intune levelezési profillal egyező e-mail-fiókot az eszközön. Az Intune nem írhatja felül a felhasználó által létesített profilt, így nem kezelheti. A megfelelőség biztosítása érdekében a felhasználónak törölnie kell a meglévő e-mail-beállításokat. Ezt követően az Intune képes lesz a felügyelt e-mail-profil telepítésére.
- **Az Intune-ban felügyelni kívánt levelezési profil:** Ha a **Csak az Intune által felügyelt e-mail fiók használható** beállítás be van jelölve, kattintson a **Kiválasztás** elemre az Intune levelezési profil kiválasztásához. A levelezési profilnak megtalálhatónak kell lennie az eszközön.

Az e-mail-profilról a [Vállalati levelezéshez való hozzáférés konfigurálása e-mail-profilokkal a Microsoft Intune-ban](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) című témakörben talál további információt.

## <a name="device-health"></a>Device health

- **Feltört eszközök**: Ha ezt a beállítást engedélyezi, akkor a feltört eszközök nem lesznek kompatibilisek.
- **Annak a megkövetelése, hogy az eszköz az eszközfenyegetettségi szinten vagy az alatt legyen**: Válassza a maximális fenyegetettségi szintet az eszközök nem kompatibilisként való megjelöléséhez. Ha például a **Közepes** fenyegetettségi szintet állítja be, akkor a közepes, alacsony vagy biztonságos szintű eszközök kompatibilisek. A magas fenyegetettségi szintű eszközök nem kompatibilisek.

## <a name="device-properties"></a>Eszköztulajdonságok

- **Az operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó választhatja az eszköz frissítését. Azt követően hozzáférhet a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva. A felhasználónak ezután kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

## <a name="system-security"></a>Rendszerbiztonság

### <a name="password"></a>Jelszó

> [!NOTE]
> Miután megfelelőségi vagy konfigurációs szabályzatot alkalmazott egy iOS-eszközre, a felhasználóktól 15 percenként egy PIN-kódot kér a rendszer. A kérések mindaddig megjelennek, amíg a felhasználó meg nem ad egy PIN-kódot.

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget. A jelszót használó iOS-eszközöket titkosítja a rendszer.
- **Egyszerű jelszavak**: Ha engedélyezni szeretné, hogy a felhasználók használhassanak olyan jelszavakat, mint az **1234** vagy az **1111**, válassza az **Igen** lehetőséget.
- **Jelszó minimális hossza**: Meghatározhatja a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Megkövetelt jelszótípus**: Megadhatja, hogy a felhasználóknak **alfanumerikus** jelszót vagy **numerikus** jelszót kell-e létrehozniuk.
- **Nem alfanumerikus karakterek száma a jelszóban**: Megadhatja, hogy hány speciális karakternek (például &, #, %, ! stb.) kell szerepelnie a jelszóban.

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány korábbi jelszó ne legyen újra felhasználható.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
