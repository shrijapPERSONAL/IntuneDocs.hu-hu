---
title: "Android for Work-alapú megfelelőségi szabályzat létrehozása"
titleSuffix: Microsoft Intune
description: "Az eszközmegfelelőségi követelmények megszabásához hozzon létre egy Intune Android for Work-eszközmegfelelőségi szabályzatot."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ca31d4c83ccc6b786933080b96f66953cf1a108
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Android for Work-eszközök eszközmegfelelőségi szabályzatának létrehozása az Intune-ban


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Android for Work-eszközmegfelelőségi szabályzatokkal megszabhatja az Android for Work-eszközöktől a megfelelőséghez kötelezően elvárt szabályokat és beállításokat. Ezeket a szabályzatokat feltételes hozzáféréssel használhatja, így engedélyezheti vagy letilthatja a céges erőforrásokhoz való hozzáférést, eszközjelentéseket kaphat, és különböző műveleteket hajthat végre meg nem felelés esetén. Megfelelőségi szabályzatok az Intune Azure portálon hozhatók létre az egyes platformokhoz. A megfelelőségi szabályzatokról és a létrehozásuk előtt teljesítendő előfeltételekről [Az eszközmegfelelőség használatának első lépései](device-compliance-get-started.md) című témakörben találhat további információt.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

--------------------------

|**házirend-beállítás**| **Android for Work** |
| --- | --- |
| **PIN-kód vagy jelszó konfigurálása** |  Karanténba helyezve |
| **Eszköztitkosítás** |  Karanténba helyezve |
| **Jailbreakelt vagy rootolt eszköz** | Karanténba helyezve (nem beállítás) |
| **e-mail profil** | Nem alkalmazható |
| **Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** | Karanténba helyezve |
| **Windows-állapotigazolás** |Nem alkalmazható |

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználónak kötelező PIN-kódot beállítani.)+

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

- Ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik, a rendszer letiltja az eszközt.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Megfelelőségi szabályzat létrehozása az Azure Portal webhelyen

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
1. Az **Intune** panelen válassza az **Eszközmegfelelőség** lehetőséget. A **Kezelés** területen válassza a **Szabályzatok**, majd a **Szabályzat létrehozása** lehetőséget.
2. Írjon be egy nevet és egy leírást, és válassza ki azt a platformot, amelyre ez a szabályzat vonatkozik.
3. A **Beállítások > konfigurálás** lehetőséggel adja meg a **Rendszerbiztonság**, az **Eszközállapot** és az **Eszköztulajdonságok** beállításokat. Ha elkészült, válassza az **OK** elemet.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

A megfelelőségi szabályzatok felhasználókhoz való hozzárendeléséhez válasszon egy már konfigurált szabályzatot. A meglévő szabályzatokat az **Eszközmegfelelőségi szabályzatok** panelen tekintheti meg.

1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt **Azure Active Directory-biztonsági csoportokat**, és hozzárendelheti azokat a szabályzathoz.
2. Válassza a **Kiválasztott csoportok** lehetőséget az Azure AD biztonsági csoportjait megjelenítő lap megnyitásához.  A **Mentés** elemet választva telepítheti a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára.  A szabályzattal megcélzott felhasználók által használt eszközök megfelelőségét értékelni fogja a rendszer.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget.
- **Jelszó minimális hossza**: Meghatározza a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó erőssége**: Ez a beállítás észleli, hogy az Ön által megadott jelszókövetelmények konfigurálva vannak-e az eszközön. E beállítás bekapcsolásával írja elő a felhasználóknak az Android-eszközök bizonyos jelszókövetelményeinek konfigurálását. A következő lehetőségek közül választhat:
  - **Alacsony biztonságú biometrikus**
  - **Kötelező**
  - **Legalább számok**
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Alfanumerikus karakterek és szimbólumok**
- **Jelszó kérése ennyi perc inaktivitás után**: Azt a tétlenségi időt adja meg, amelyen túl a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Adja meg, hogy hány nap elteltével járjon le a felhasználó jelszava, és legyen szükséges újat létrehoznia.
- **Korábbi jelszavak megjegyzése:** Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban már használt jelszavakat hozzon létre.
- **Korábbi jelszavak újbóli használatának tiltása:** Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.
- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**: Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással kell használni. A rendszer a jelszó beírását kéri a végfelhasználótól a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz eléréséhez.


### <a name="encryption"></a>Encryption

- **Titkosítás megkövetelése mobileszközön**: Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközök megkövetelik a titkosítást.


## <a name="device-health-and-security-settings"></a>Eszközállapot és biztonsági beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz**: Ha bekapcsolja ezt a beállítást, a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.
- **Az ismeretlen forrásból származó alkalmazások telepítése megakadályozásának megkövetelése az eszközökön**: Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközök mindig korlátozzák az ismeretlen forrásokból való telepítést.
- **Az USB-hibakeresés letiltásának megkövetelése**: Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközökön már le van tiltva az USB-hibakeresés.
- **Az Android minimálisan előírt biztonsági javítási szintje:** Ezzel a beállítással adható meg az Android minimálisan előírt biztonsági javítási szintje. Az ennél régebbi javítási szintű eszközök nem megfelelőek. A dátumot a következő formátumban kell megadni: ÉÉÉÉ-HH-NN.
- **Veszélyforrások elleni eszközvédelem engedélyezése**: ezzel a beállítással megfelelési feltételként kiveszi a kockázatelemzést Lookout MTP-megoldásból. Válassza ki a maximális megengedett kockázati szintet, ami az alábbiak egyike lehet:
  - **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség. Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha vonatkozásában kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.
  - **Magas**: Ez a legkevésbé biztonságos beállítás. Lényegében minden kockázati szintet engedélyez, ezért valószínűleg csak jelentéskészítési célokra lehet hasznos.

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Az operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie a rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
