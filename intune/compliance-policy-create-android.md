---
title: "Megfelelőségi szabályzat létrehozása Android rendszerhez"
titleSuffix: Intune on Azure
description: "Útmutató az androidos eszközök megfelelőségi szabályzatának létrehozásához.”"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cc68bf4a52e5fcf9a8fbb3550a5bee814f4f46f0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a>Android-eszközök eszközmegfelelőségi szabályzatának létrehozása az Intune-ban


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Megfelelőségi szabályzatok az Intune Azure portálon hozhatók létre az egyes platformokhoz. 

- A megfelelőségi szabályzatokról a [What is a device compliance](device-compliance.md) (Mi az eszközmegfelelőség?) című témakörben találhat további információt.
- A megfelelőségi szabályzatok létrehozása előtt teljesítendő előfeltételekről a [Get started with device compliance](device-compliance-get-started.md) (Az eszközmegfelelőség használatának első lépései) című témakörben találhat további információt.

## <a name="to-create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozásához

1. Az **Intune** panelen válassza az **Eszközmegfelelőség beállítása** lehetőséget. A **Kezelés** alatt válassza az **Összes eszközmegfelelőségi szabályzat**, majd a **Létrehozás** lehetőséget.
2. Írjon be egy nevet és egy leírást, és válassza ki azt a platformot, amelyre ez a szabályzat vonatkozik.
3. A **Megfelelőségi követelmények** területen megadhatja a **Biztonság**, az **Eszközállapot** és az **Eszköztulajdonság** beállításait. Ha elkészült, válassza az **OK** elemet.

<!-- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.-->

## <a name="to-assign-user-groups"></a>Felhasználói csoportok hozzárendeléséhez

A megfelelőségi szabályzatok felhasználókhoz való hozzárendeléséhez válasszon egy már konfigurált szabályzatot. A meglévő szabályzatok a **Megfelelőségi szabályzatok** panelen találhatók.

1. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik az a panel, amelyen kiválaszthatja a kívánt **Azure Active Directory-csoportokat**, és hozzárendelheti őket a szabályzathoz.
2. Az Azure AD biztonság csoportokat megjelenítő panel megnyitásához válassza a **Csoportok kiválasztása** lehetőséget. Itt találhatóak az Azure Active Directory biztonsági csoportjai.  Válassza ki azokat a felhasználói csoportokat, amelyekhez hozzá szeretné rendelni a szabályzatot, és válassza a **Kiválasztás** elemet. A **Kiválasztás** elem választásával telepítheti a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára.  A szabályzattal megcélzott felhasználók által használt eszközök megfelelőségét értékelni fogja a rendszer.

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a>Eszközállapot és biztonsági beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz:** Ha bekapcsolja ezt a beállítást, a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.
- **Annak megkövetelése, hogy az ismeretlen forrásból származó alkalmazások telepítését a rendszer megakadályozza az eszközökön (Android 4.0 vagy újabb)**: A beállítás engedélyezésével és az **Igen** lehetőség beállításával letilthatja azokat az eszközöket, amelyeken engedélyezve van a **Biztonság** >; **Ismeretlen források** beállítás.

### <a name="important"></a>Fontos

Az alkalmazások közvetlen telepítéséhez engedélyezni kell az **Ismeretlen források** beállítást. Csak akkor szükséges ennek a megfelelőségi szabályzatnak a kényszerítése, ha nem Android-alkalmazások közvetlen telepítését végzi az eszközökön.

- **Az USB-hibakeresés letiltásának megkövetelése (Android 4.2 vagy újabb)**: Ezzel a beállítással adhatja meg, hogy a rendszer ellenőrizze-e az USB-hibakeresés engedélyezését az eszközön.
- **A Biztonsági fenyegetések keresése az eszközön beállítás engedélyezésének megkövetelése az eszközökön (Android 4.2-4.4)**: Ezzel a beállítás szabja meg, hogy az **Alkalmazások ellenőrzése** funkció engedélyezve van-e az eszközön.
- **Az Android minimálisan előírt biztonsági javítási szintje (Android 6.0 vagy újabb)**: Ezzel a beállítással adható meg az Android minimálisan előírt javítási szintje. Az ennél régebbi javítási szintű eszközök nem megfelelőek. A dátumot a következő formátumban kell megadni: ÉÉÉÉ-HH-NN.
- **Veszélyforrások elleni eszközvédelem engedélyezésének megkövetelése**: ez a beállítás a Lookout MTP-megoldás kockázatelmérését megfelelőségi feltételként állítja be. Válassza ki a megengedett maximális kockázati szintet, amely az alábbiak egyike lehet:
  - **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség. Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a legkevésbé biztonságos beállítás. Alapvetően az összes kockázati szintet engedélyezi. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.

További információ: [az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget.
- **Jelszó minimális hossza**: Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó erőssége**: Ez a beállítás észleli, hogy a megadott jelszókövetelmények beállítása megtörtént-e az eszközön. A beállítás bekapcsolásával megkövetelheti a felhasználóktól az Android-eszközök bizonyos jelszókövetelményeinek teljesítését. A következő lehetőségek közül választhat:
  - **Alacsony biztonságú biometrikus**
  - **Kötelező**
  - **Legalább számok**
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Alfanumerikus karakterek és szimbólumok**
- **Jelszó kérése ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Korábbi jelszavak megjegyzése**: A beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással együtt használva korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.
- **Korábbi jelszavak újbóli használatának tiltása**: Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.
- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**: Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt használhatja. A rendszer megkéri a felhasználót egy jelszó beírására a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz elérésekor.

### <a name="encryption"></a>Titkosítás

- **Titkosítás megkövetelése mobileszközön**: Állítsa ezt a beállítást **Igen** értékre, ha szeretné megkövetelni, hogy az eszközök csak titkosítás használatával csatlakozhassanak az erőforrásokhoz. Az eszközök **A mobileszközök zárolásának feloldásához jelszó szükséges** beállítás használatával titkosíthatók.

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Az operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

## <a name="how-non-compliant-settings-work-with-conditional-access-policies"></a>A nem megfelelő besorolású beállítások kezelése a feltételes hozzáférési szabályzatokkal

Az alábbi táblázat azt ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

--------------------

|**Szabályzat-beállítás**| **Android 4.0-s és újabb verziók, Samsung KNOX szabvány 4.0-s és újabb verziók** |
| --- | ----|
| **PIN-kód vagy jelszó konfigurálása** |  Karanténba helyezve |
| **Eszköztitkosítás** | Karanténba helyezve |
| **Jailbreakelt vagy rootolt eszköz** | Karanténba helyezve (nem beállítás) |
| **e-mail profil** | Nem alkalmazható |
| **Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** |   Karanténba helyezve |
| **Windows-állapotigazolás** | Nem alkalmazható |

--------------------------

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználónak kötelező PIN-kódot beállítani.)+

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) A rendszer a következő műveleteket hajtja végre, ha az eszköz nem megfelelő:+

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->