---
title: "Az Android for Work megfelelőségi beállításai"
description: "Ez a témakör az Android for Workkel kompatibilis Android-eszközök eszközmegfelelőségi szabályzatainak beállításait mutatja be."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 79be4993c9b23294d1f49743f863588f9d0cb9b5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Az Android for Work-eszközök megfelelőségi szabályzatainak beállításai a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A jelen témakörben leírt szabályzati beállítások Android for Work-eszközökre vonatkoznak.

Ha más platformokra vonatkozó információkat keres, válassza az alábbiak egyikét:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai Android-eszközökhöz](android-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai iOS-eszközökhöz](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Windows-eszközökhöz](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai
### <a name="password"></a>Jelszó
- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához:** Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget.

-  **Jelszó minimális hossza:** meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

- **Jelszó erőssége:** Ez a beállítás észleli, hogy az Ön által megadott jelszókövetelmények konfigurálva vannak-e az eszközön. E beállítás bekapcsolásával írja elő a felhasználóknak az Android-eszközök bizonyos jelszókövetelményeinek konfigurálását. A következő lehetőségek közül választhat:
  -   **Alacsony biztonságú biometrikus**
  - **Kötelező**
  -   **Legalább számok**
  -   **Legalább betűk**
  -   **Legalább alfanumerikus karakterek**
  -   **Alfanumerikus karakterek és szimbólumok**

- **Jelszó kérése ennyi perc inaktivitás után:** arra a tétlenségi időre vonatkozik, amin belül a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban):** Válassza ki, hány nap elteltével járjon le a felhasználó jelszava, ami után újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése:** Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban már használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.

- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból:** Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt kell használni. A rendszer jelszó beírását kéri a végfelhasználótól a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz eléréséhez.

### <a name="encryption"></a>Titkosítás
- **Titkosítás megkövetelése mobileszközön:** Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközök megkövetelik a titkosítást.

## <a name="device-health-and-security-settings"></a>Eszközállapot és biztonsági beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz:** Ha bekapcsolja ezt a beállítást, a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.
- **Az ismeretlen forrásból származó alkalmazások telepítése megakadályozásának megkövetelése az eszközökön:** Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközök mindig korlátozzák az ismeretlen eredetű telepítést. .  

- **Az USB-hibakeresés letiltásának megkövetelése:** Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközökön már le van tiltva az USB-hibakeresés.

- **Az Android minimálisan előírt biztonsági javítási szintje:** Ezzel a beállítással adható meg az Android minimálisan előírt biztonsági javítási szintje.  Az ennél régebbi javítási szintű eszközök nem megfelelőek. A dátumot a következő formátumban kell megadni: ÉÉÉÉ-HH-NN.
- **A Veszélyforrások elleni eszközvédelem alkalmazás engedélyezésének megkövetelése:** Ezzel a beállítással felveszi megfelelési feltételként a Veszélyforrások elleni eszközvédelem megoldás általi kockázatelemzést. Válassza ki a maximális megengedett kockázati szintet, ami az alábbiak egyike lehet:

  - **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség. Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelése esetén az eszköz értékelése nem megfelelő lesz.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha vonatkozásában kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.
  - **Magas**: Ez a legkevésbé biztonságos beállítás. Lényegében minden kockázati szintet engedélyez, ezért valószínűleg csak jelentéskészítési célokra használható.

  További részletek: [Eszköz-megfelelőségi szabályzat létrehozása](create-lookout-device-compliance-policy.md).

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások
- **Az operációs rendszer szükséges minimális verziója:** Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni.
  Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ezt követően pedig hozzáférhet a vállalati erőforrásokhoz.

- **Maximálisan engedélyezett operációsrendszer-verzió:** Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie a rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.
