---
title: IOS-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Létrehozhat vagy konfigurálhat Microsoft Intune-beli eszközmegfelelőségi szabályzatokat iOS-eszközökhöz e-mail-fiók megadásához, feltört eszközök ellenőrzéséhez, az operációs rendszer használható minimális és maximális verziójának ellenőrzéséhez, valamint a jelszókorlátozásoknak, például a jelszó hosszának és az eszköz inaktivitási idejének a beállításához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 42ce05d2f726147caee198c79db185b87854cffb
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566148"
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
4. A **Platform** beállításnál adja meg az **iOS** értéket. 
5. Válassza **beállítások konfigurálása**, és adja meg a **E-mail**, **Eszközállapot**, **eszköztulajdonságok**, és **rendszer Biztonsági** ebben a témakörben leírt beállításokat. Ha elkészült, válassza az **OK** majd a **Létrehozás** lehetőséget.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="email"></a>E-mail

- **Mobileszközök számára a felügyelt e-mail-profil**: Ha ez szükséges, majd e-mailt nem rendelkező eszközök az Intune által felügyelt profil nem megfelelőnek minősülnek. Egy eszköz akkor nem rendelkezhet felügyelt e-mail-profillal, ha nincs megfelelő célcsoportban, vagy ha a felhasználó manuálisan állította be az e-mail-fiókot az eszközön.

  Az eszköz a következő esetekben számít nem megfelelőnek:
  - Az e-mail-profil nem a megfelelőségi szabályzat által célzott felhasználócsoporttól különböző felhasználócsoportnál van telepítve.
  - A felhasználó már beállított egy, az eszközre telepített Intune levelezési profillal egyező e-mail-fiókot az eszközön. Az Intune nem írhatja felül a felhasználó által létesített profilt, így nem kezelheti. A megfelelőség biztosítása érdekében a felhasználónak törölnie kell a meglévő e-mail-beállításokat. Ezt követően az Intune képes lesz a felügyelt e-mail-profil telepítésére.

- **Válassza ki az Intune-ban felügyelni kívánt levelezési profil**: Ha a **az Intune által felügyelt E-mail fiók** beállítás van kiválasztva, válassza a **kiválasztása** az Intune e-mail profil. A levelezési profilnak megtalálhatónak kell lennie az eszközön.

Az e-mail-profilról a [Vállalati levelezéshez való hozzáférés konfigurálása e-mail-profilokkal a Microsoft Intune-ban](email-settings-configure.md) című témakörben talál további információt.

## <a name="device-health"></a>Device health

- **Feltört eszközök**: Ha engedélyezi ezt a beállítást, a függetlenített eszközök nem lesznek kompatibilisek.
- **Az eszköz vagy az eszköz fenyegetettségi szintje alatt megkövetelése** (iOS 8.0 és újabb): Válassza ki azt a maximális fenyegetettségi szintet az eszközök kompatibilisként való megjelöléséhez. Az ezt a szintet meghaladó fenyegetettségű eszközök nem megfelelőként lesznek megjelölve:
  - **Védett**: Ez a lehetőség akkor a legtöbb beállítás, mivel az eszköz esetében semmilyen fenyegetés nem. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz abban az esetben minősül megfelelőnek Ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a beállítás a legkevésbé biztonságos, és minden kockázati szintet. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.

## <a name="device-properties"></a>Eszköztulajdonságok

- **Operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem felel meg a minimális verziójára vonatkozó követelményt, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó választhatja az eszköz frissítését. Azt követően hozzáférhet a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön operációsrendszer-verziónál újabb fut, a szabályban megadott verzió, a vállalati erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak ezután kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.
- **Minimális operációsrendszer-verziót hozzon létre**: Apple közzéteszi a biztonsági frissítéseket, ha a buildszám általában frissül, nem az operációs rendszer verzióját. Ez a funkció használatával adja meg a minimális megengedett buildszám az eszközön. A megfelelőségi ellenőrzés iOS 8.0 és újabb rendszert futtató eszközöket támogatja. 
- **Maximális operációsrendszer-verziót hozzon létre**: Apple közzéteszi a biztonsági frissítéseket, ha a buildszám általában frissül, nem az operációs rendszer verzióját. Ez a funkció használatával adja meg a maximális megengedett buildszám az eszközön. A megfelelőségi ellenőrzés iOS 8.0 és újabb rendszert futtató eszközöket támogatja.

## <a name="system-security"></a>Rendszerbiztonság

### <a name="password"></a>Windows 10

> [!NOTE]
> Miután megfelelőségi vagy konfigurációs szabályzatot alkalmazott egy iOS-eszközre, a felhasználóktól 15 percenként egy PIN-kódot kér a rendszer. A kérések mindaddig megjelennek, amíg a felhasználó meg nem ad egy PIN-kódot.

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez. A jelszót használó iOS-eszközöket titkosítja a rendszer.
- **Egyszerű jelszavak**: Állítsa be **blokk** így a felhasználók nem egyszerű jelszavakat használhassanak, mint például **1234** vagy **1111**. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Adja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Kötelező jelszótípus**: Válassza ki, ha a jelszó csak szükséges **numerikus** karakter, vagy ha számokat és más karaktereket vegyesen kell lennie (**alfanumerikus**).
- **Jelszavak nem alfanumerikus karaktereinek száma**: Adja meg a speciális karakterek minimális számát (&, #, %,! stb) kell szerepelnie a jelszóban.

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és létre kell hoznia egy újat.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható.

### <a name="restricted-applications"></a>Korlátozott alkalmazások 
Alkalmazásokat úgy korlátozhat, hogy kötegazonosítójukat hozzáadja a szabályzathoz. Így ha az alkalmazás telepítve van az eszközön, az eszköz nem megfelelőként lesz megjelölve. 
- **Alkalmazásnév**: Adjon meg egy felhasználóbarát nevet segítségével azonosíthatja a kötegazonosítót. 
- **Alkalmazásköteg-azonosító**: Adja meg a az alkalmazás szolgáltatója által hozzárendelt egyedi csomagazonosítót. A kötegazonosítót az [iOS-alkalmazás kötegazonosítójának megállapítása](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) című témakörben leírtak alapján találhatja meg.  

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

1. Válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely csoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)
