---
title: Megfelelőségi szabályzat beállításai Androidhoz
description: Ez a témakör bemutatja az eszközmegfelelőségi szabályzat beállításait Android-eszközökhöz.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 63618f9af5f2bdb863a19c229c862e446dd4ea7a
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a>Megfelelőségi szabályzat beállításai Android-eszközökhöz a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A jelen témakörben leírt szabályzati beállítások az Android 4.0-s és újabb verzióival, illetve a Samsung KNOX 4.0-s és újabb verzióival működő eszközökre vonatkoznak.

Ha más platformokra vonatkozó információkat keres, válassza az alábbiak egyikét:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai iOS-eszközökhöz](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Windows-eszközökhöz](windows-compliance-policy-settings-in-microsoft-intune.md)
- [Az Android for Work-eszközök megfelelőségi szabályzatainak beállításai](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai
### <a name="password"></a>Jelszó
- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget.

-  **Jelszó minimális hossza**: Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

- **Jelszó erőssége**: Ez a beállítás észleli, hogy a megadott jelszókövetelmények beállítása megtörtént-e az eszközön. A beállítás bekapcsolásával megkövetelheti a felhasználóktól az Android-eszközök bizonyos jelszókövetelményeinek teljesítését. A következő lehetőségek közül választhat:

  -   **Alacsony biztonságú biometrikus**
  -   **Kötelező**
  -   **Legalább számok**
  -   **Legalább betűk**
  -   **Legalább alfanumerikus karakterek**
  -   **Alfanumerikus karakterek és szimbólumok**

- **Jelszó kérése ennyi perc inaktivitás után**: arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a felhasználó jelszava, ami után újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése**: A beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással együtt használva korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** Adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni (ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve).

- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból:** A **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt használhatja. A rendszer jelszó beírását kéri a végfelhasználótól a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz eléréséhez.

### <a name="encryption"></a>Encryption
- **Titkosítás megkövetelése mobileszközökön:** Állítsa ezt a beállítást **Igen** értékre, ha azt szeretné, hogy az eszközök csak titkosítás használatával csatlakozhassanak az erőforrásokhoz. Az eszközök **A mobileszközök zárolásának feloldásához jelszó szükséges** beállítás konfigurálásával titkosíthatók.

## <a name="device-health-and-security-settings"></a>Eszközállapot és biztonsági beállítások

- **Az eszköz nem lehet jaibreakelt vagy rootolással feltört eszköz:** Ha bekapcsolja ezt a beállítást, a rendszer nem megfelelőként fogja értékelni azon eszközöket, amelyeken a rendszerkorlátozásokat feltörték.
- **Annak megkövetelése, hogy az ismeretlen forrásból származó alkalmazások telepítését a rendszer megakadályozza az eszközökön (Android 4.0 vagy újabb)**: A beállítás engedélyezésével és az **Igen** lehetőség beállításával letilthatja azokat az eszközöket, amelyeken engedélyezve van a **Biztonság > Ismeretlen források** beállítás.  

>[!IMPORTANT]
>Az alkalmazások közvetlen telepítéséhez engedélyezni kell az **Ismeretlen források** beállítást. Csak akkor szükséges ennek a megfelelőségi szabályzatnak a kényszerítése, ha nem Android-alkalmazások közvetlen telepítését végzi az eszközökön.

- **Az USB-hibakeresés letiltásának megkövetelése (Android 4.2 vagy újabb)**: Megadhatja, hogy a rendszer ellenőrizze-e az USB-hibakeresés engedélyezését az eszközön.
- **A Biztonsági fenyegetések keresése az eszközön beállítás engedélyezésének megkövetelése az eszközökön (Android 4.2–4.4)**: Megadja, hogy az **Alkalmazások ellenőrzése** funkció engedélyezve van-e az eszközön.
- **Az Android minimálisan előírt biztonsági javítási szintje (Android 6.0 vagy újabb)**: Megadja az Android minimálisan előírt javítási szintjét.  Az ennél régebbi javítási szintű eszközök nem megfelelőek. A dátumot a következő formátumban kell megadni: ÉÉÉÉ-HH-NN.
- **Veszélyforrások elleni eszközvédelem engedélyezése**: ezzel a beállítással megfelelési feltételként kiveszi a kockázatelemzést Lookout MTP-megoldásból. Válassza ki a maximális megengedett kockázati szintet, ami az alábbiak egyike lehet:

  - **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség. Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Ha a rendszer magas szintű fenyegetéseket észlel az eszközön, nem megfelelőként értékeli azt.
  - **Magas**: Ez a legkevésbé biztonságos beállítás. Lényegében minden kockázati szintet engedélyez, ami valószínűleg csak jelentéskészítési célokra használható.

  További információkért lásd [A Lookout eszközmegfelelőségi szabályzatának létrehozása](create-lookout-device-compliance-policy.md) című cikket.

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Operációs rendszer minimális verziója:** Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni.
  Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Maximálisan engedélyezett operációsrendszer-verzió:** Ha egy eszköz a szabályban megadott legmagasabb operációsrendszer-verziónál újabbat használ, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie a rendszergazdával. Az eszköz nem használható a vállalati erőforrások elérésére, amíg a szabályt nem módosítják úgy, hogy engedélyezze az operációs rendszer verzióját.
