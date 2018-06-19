---
title: IOS-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Létrehozhat vagy konfigurálhat Microsoft Intune-beli eszközmegfelelőségi szabályzatokat iOS-eszközökhöz e-mail-fiók megadásához, feltört eszközök ellenőrzéséhez, az operációs rendszer használható minimális és maximális verziójának ellenőrzéséhez, valamint a jelszókorlátozásoknak, például a jelszó hosszának és az eszköz inaktivitási idejének a beállításához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f711a6bec9be0ac1fd94183931070f9988d49e3
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/18/2018
ms.locfileid: "31442644"
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>iOS-es eszközök megfelelőségi szabályzatainak felvétele az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune iOS-eszközmegfelelőségi szabályzataival megszabhatja az iOS-eszközök megfelelőségéhez kötelezően szükséges szabályokat és beállításokat. Az eszközmegfelelőségi szabályzatokat a feltételes hozzáféréssel használva engedélyezheti vagy letilthatja a hozzáférést a vállalati erőforrásokhoz. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén. Az Intune Azure Portalon minden platformhoz létrehozhat megfelelőségi szabályzatokat. A megfelelőségi szabályzatokról és azok előfeltételeiről az [Eszközmegfelelőség – első lépések](device-compliance-get-started.md) című cikk nyújt bővebb tájékoztatást.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

---------------------------

| **Szabályzat-beállítás** | **iOS 8.0 vagy újabb** |
| --- | --- |
| **PIN-kód vagy jelszó konfigurálása** | Kijavítva |
| **Eszköztitkosítás** | Kijavítva (PIN-kód beállításával) |
| **Jailbreakelt vagy rootolt eszköz** | Karanténba helyezve (nem beállítás)
| **E-mail profil** | Karanténba helyezve |
|**Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** | Karanténba helyezve |
| **Windows-állapotigazolás** | Nem alkalmazható |

---------------------------

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználó kénytelen lesz PIN-kódot beállítani.)

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. A **Platform** beállításnál adja meg az **iOS** értéket. Válassza a **Beállítások konfigurálása** lehetőséget az **E-mail**, **Eszközállapot**, **Eszköztulajdonságok** és **Rendszerbiztonság** beállításainak megadásához. Ha elkészült, válassza az **OK** majd a **Létrehozás** lehetőséget.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="email"></a>E-mail

- **Felügyelt e-mail-profil megkövetelése a mobileszközökön**: Ha ez Kötelezőként van megadva, akkor az Intune által felügyelt e-mail-profillal nem rendelkező eszközök nem megfelelőnek minősülnek. Egy eszköz akkor nem rendelkezhet felügyelt e-mail-profillal, ha nincs megfelelő célcsoportban, vagy ha a felhasználó manuálisan állította be az e-mail-fiókot az eszközön.

  Az eszköz a következő esetekben számít nem megfelelőnek:
  - Az e-mail-profil nem a megfelelőségi szabályzat által célzott felhasználócsoporttól különböző felhasználócsoportnál van telepítve.
  - A felhasználó már beállított egy, az eszközre telepített Intune levelezési profillal egyező e-mail-fiókot az eszközön. Az Intune nem írhatja felül a felhasználó által létesített profilt, így nem kezelheti. A megfelelőség biztosítása érdekében a felhasználónak törölnie kell a meglévő e-mail-beállításokat. Ezt követően az Intune képes lesz a felügyelt e-mail-profil telepítésére.

- **Az Intune-ban felügyelni kívánt levelezési profil:** Ha a **Csak az Intune által felügyelt e-mail fiók használható** beállítás be van jelölve, kattintson a **Kiválasztás** elemre az Intune levelezési profil kiválasztásához. A levelezési profilnak megtalálhatónak kell lennie az eszközön.

Az e-mail-profilról a [Vállalati levelezéshez való hozzáférés konfigurálása e-mail-profilokkal a Microsoft Intune-ban](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) című témakörben talál további információt.

## <a name="device-health"></a>Device health

- **Feltört eszközök**: Ha ezt a beállítást engedélyezi, akkor a feltört eszközök nem lesznek kompatibilisek.
- **Maximálisan elérhető eszközfenyegetettségi szint használata** (iOS 8.0 és újabb verziók): Válassza ki a legmagasabb fenyegetettségi szintet az eszközök nem megfelelőként való megjelöléséhez. Az ezt a szintet meghaladó fenyegetettségű eszközök nem megfelelőként lesznek megjelölve:
  - **Védett**: Ez a legbiztonságosabb beállítás, mivel az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő beállítás. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.

## <a name="device-properties"></a>Eszköztulajdonságok

- **Az operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó választhatja az eszköz frissítését. Azt követően hozzáférhet a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva. A felhasználónak ezután kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

## <a name="system-security"></a>Rendszerbiztonság

### <a name="password"></a>Jelszó

> [!NOTE]
> Miután megfelelőségi vagy konfigurációs szabályzatot alkalmazott egy iOS-eszközre, a felhasználóktól 15 percenként egy PIN-kódot kér a rendszer. A kérések mindaddig megjelennek, amíg a felhasználó meg nem ad egy PIN-kódot.

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: A felhasználók **kötelesek** jelszót megadni az eszköz eléréséhez. A jelszót használó iOS-eszközöket titkosítja a rendszer.
- **Egyszerű jelszavak**: Ha nem szeretné engedélyezni, hogy a felhasználók olyan egyszerű jelszavakat használhassanak, mint az **1234** vagy az **1111**, válassza a **Tiltás** lehetőséget. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Meghatározhatja a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó megkövetelt típusa**: Megadható, hogy a jelszó csak **számjegy** karaktereket vagy számjegy és más (**alfanumerikus**) karaktereket vegyesen tartalmazzon.
- **Nem alfanumerikus karakterek száma a jelszóban**: Megadhatja, hogy hány speciális karakternek (például &, #, %, ! stb.) kell szerepelnie a jelszóban.

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány legutóbbi jelszó ne legyen újra felhasználható.

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

1. Válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely csoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)