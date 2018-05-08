---
title: Android for Work megfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Android for Work-eszközök Microsoft Intune eszközmegfelelőségi szabályzatának létrehozása vagy konfigurálása. Feltört eszközök választható engedélyezése, az elfogadható fenyegetettségi szint megadása, a Google Play Áruház ellenőrzése, minimális és maximális operációsrendszer-verzió megadása, jelszókövetelmények megválasztása és alkalmazások közvetlen telepítésének engedélyezése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 74fe0897764957e84e5a13944305221cc85bd8c7
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Android for Work-eszközök eszközmegfelelőségi szabályzatának hozzáadása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune-beli Android for Work-eszközmegfelelőségi szabályzatokkal megszabhatja az ilyen eszközöktől a megfelelőséghez kötelezően elvárt szabályokat és beállításokat. Ezeket a szabályzatokat feltételes hozzáféréssel használva megakadályozható vagy engedélyezhető a vállalati erőforrásokhoz való hozzáférés. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén. Az Azure-beli Intune portálon különböző platformokhoz hozhat létre megfelelőségi szabályzatokat. A megfelelőségi szabályzatokról és azok előfeltételeiről az [Eszközmegfelelőség – első lépések](device-compliance-get-started.md) című cikk nyújt bővebb tájékoztatást.

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

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. A **Platform** beállításban válassza az **Android for Work** lehetőséget. Válassza a **Beállítások konfigurálása** lehetőséget az **Eszközállapot**, **Eszköztulajdonságok** és **Rendszerbiztonság** beállításainak megadásához. Ha elkészült, válassza az **OK**, majd a **Létrehozás** lehetőséget.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="device-health"></a>Device health

- **Feltört eszközök**: Ezt a beállítást engedélyezve a függetlenített eszközök nem megfelelőként lesznek minősítve.
- **Maximálisan elérhető eszközfenyegetettségi szint használata**: Ezzel a beállítással a Lookout MTP-től származó kockázatbecslés lesz a megfelelőség feltétele. Megadható a legnagyobb megengedett fenyegetettségi szint:
  - **Védett**: Ez a legbiztonságosabb beállítás. Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő beállítás. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.
- **A Google Play-szolgáltatások be van állítva**: Megadása esetén a Google Play-szolgáltatások alkalmazást telepíteni és engedélyezni kell. A Google Play-szolgáltatások lehetővé teszik a biztonsági frissítéseket, és számos biztonsági funkció előfeltételei a hitelesített Google-eszközökön.
- **Naprakész biztonsági szolgáltató**: Megadása esetén egy naprakész biztonsági szolgáltatóval kell védeni az eszközöket az ismert biztonsági kockázatokkal szemben.
- **SafetyNet eszközigazolás**: Megadható a [SafetyNet igazolás](https://developer.android.com/training/safetynet/attestation.html) elvárt szintje. A választható lehetőségek:
  - **Nincs konfigurálva**
  - **Alapvető integritás ellenőrzése**
  - **Alapvető integritás ellenőrzés és tanúsított eszközök**

#### <a name="threat-scan-on-apps"></a>Alkalmazások fenyegetettségvizsgálata

A munkahelyi profilokkal rendelkező (Android for Work ) eszközökön az **Alkalmazások fenyegetettségvizsgálata** beállítás a konfigurációs szabályzat beállításai között található. A beállítást rendszergazdák tudják engedélyezni az adott eszközre.

Ha cég használ androidos munkahelyi profilokat, a regisztrált eszközökre vonatkozóan engedélyezhető az **Alkalmazások fenyegetettségvizsgálata** beállítás. Hozzon létre egy eszközprofilt, és tegye kötelezővé a rendszerbiztonsági beállítást. További információt az [Android for Work-eszközök korlátozásaira vonatkozó beállítások az Intune-ban](device-restrictions-android-for-work.md) című témakörben talál.

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Minimális operációsrendszer-verzió**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ezután pedig hozzáfér a vállalati erőforrásokhoz.
- **Maximális operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: A felhasználók **kötelesek** jelszót megadni az eszköz eléréséhez.
- **Jelszó minimális hossza**: Meghatározhatja a felhasználó jelszavában szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó megkövetelt típusa**: Megadható, hogy a jelszó csak számjegyeket vagy számokat és más karaktereket vegyesen tartalmazzon. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Legalább számok**
  - **Komplex numerikus**
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Megadható, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány legutóbbi jelszó ne legyen újra felhasználható. Ezzel a beállítással korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

### <a name="encryption"></a>Encryption

- **Titkosítás megkövetelése mobileszközön**: Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközök megkövetelik a titkosítást.

### <a name="device-security"></a>Eszközbiztonság

- **Az ismeretlen forrásból származó alkalmazások tiltása**: Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközök mindig korlátozzák az ismeretlen forrásokból való telepítést.
- **Céges portál alkalmazás futtatókörnyezetének integritása**: Ellenőrzi, hogy a Céges portál alkalmazás alapértelmezett futtatókörnyezete van-e telepítve, megfelelően alá van-e írva, nincs-e hibakereső módban, és ismert forrásból telepítették-e.
- **Az USB-hibakeresés letiltása az eszközön**: Ezt a beállítást nem szükséges konfigurálni, mivel az Android for Work-eszközökön már le van tiltva az USB-hibakeresés.
- **Minimális biztonsági javítási szint**: Megadható a legrégebbi biztonsági javítás, amellyel az eszköz rendelkezhet. Az ennél régebbi javítási szintű eszközök nem megfelelőek. A dátumot `YYYY-MM-DD` formátumban kell megadni.

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

1. Válassza ki a konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely csoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)