---
title: Windows-eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Microsoft Intune-eszközmegfelelőségi szabályzatot hozhat létre vagy konfigurálhat Windows Phone 8.1, Windows 8.1 és újabb és Windows 10 és újabb rendszerű eszközökhöz. A megfelelőség szempontjából ellenőrizheti az operációs rendszer minimális és maximális verzióját, jelszóra és annak hosszára vonatkozó követelményeket állíthat be, megkövetelheti a bitlocker használatát, ellenőrizheti a harmadik féltől származó vírusvédelmi megoldásokat, beállíthatja az elfogadható fenyegetettségi szintet és az adattárolók titkosításának engedélyezését. Ez a Surface Hubra és a Windows Holographic for Businessre is vonatkozik.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11ccace4ca8e43e09b8aebeb92530629cf50a472
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602316"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Windowsos eszközök megfelelőségi szabályzatainak hozzáadása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Windows-eszközmegfelelőségi szabályzatokkal megszabhatja a Windows-eszközöktől a megfelelőséghez kötelezően elvárt szabályokat és beállításokat. Ezeket a szabályzatokat feltételes hozzáféréssel használva megakadályozható vagy engedélyezhető a vállalati erőforrásokhoz való hozzáférés. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén. Az Azure-beli Intune portálon minden platformhoz létrehozhat megfelelőségi szabályzatokat. A megfelelőségi szabályzatokról és azok előfeltételeiről az [Eszközmegfelelőség – első lépések](device-compliance-get-started.md) című cikk nyújt bővebb tájékoztatást.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

---------------------------

| **Szabályzat-beállítás** | **Windows 8.1 és újabb verziók** | **Windows Phone 8.1 és újabb verziók** |
|----| ----| --- |
| **PIN-kód vagy jelszó konfigurálása** | Kijavítva | Kijavítva |   
| **Eszköztitkosítás** | Nem alkalmazható | Kijavítva |   
| **Jailbreakelt vagy rootolt eszköz** | Nem alkalmazható | Nem alkalmazható |  
| **E-mail profil** | Nem alkalmazható | Nem alkalmazható |   
| **Operációs rendszer minimális verziója** | Karanténba helyezve | Karanténba helyezve |   
| **Operációs rendszer maximális verziója** | Karanténba helyezve | Karanténba helyezve |   
| **Windows-állapotigazolás** | Karanténba helyezve: Windows 10 és Windows 10 Mobile|Nem alkalmazható: Windows 8.1 |

-------------------------------

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználó kénytelen lesz PIN-kódot beállítani.)

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. A **Platform** alatt válassza a **Windows Phone 8.1**, **Windows 8.1 és újabb** vagy **Windows 10 és újabb** lehetőséget.
6. Válassza a **Beállítások konfigurálása** lehetőséget az **Eszközállapot**, **Eszköztulajdonságok** és **Rendszerbiztonság** beállításainak megadásához. Ha elkészült, válassza az **OK** majd a **Létrehozás** lehetőséget.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="windows-81-devices-policy-settings"></a>Windows 8.1-eszközök szabályzatbeállításai

Ezek a szabályzatbeállítások a következő platformokat futtató eszközökre vonatkoznak:

- Windows Phone 8.1
- Windows 8.1 és újabb

### <a name="device-properties"></a>Eszköztulajdonságok

- **Operációs rendszer minimális verziója:** Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ez után pedig hozzáférést kap a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz csak akkor használható a vállalati erőforrások elérésére, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

Windows 8.1-es számítógépek esetén például a visszaadott verzió a **3**-as. Ha az operációs rendszer verziószabálya Windows 8.1-re van megadva a Windows esetén, az eszköz akkor is nem megfelelőként jelenik meg, ha Windows 8.1 operációs rendszer fut rajta.

### <a name="system-security"></a>Rendszerbiztonság

#### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: A felhasználók **kötelesek** jelszót megadni az eszköz eléréséhez.
- **Egyszerű jelszavak**: Ha nem szeretné engedélyezni, hogy a felhasználók olyan egyszerű jelszavakat használhassanak, mint az **1234** vagy az **1111**, válassza a **Tiltás** lehetőséget. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Meghatározhatja a jelszóban szereplő számjegyek vagy karakterek minimális számát.

  Windows rendszerű, Microsoft-fiókon keresztül elért eszközök esetén a megfelelőségi szabályzat nem lesz helyesen kiértékelve:
  - Ha a jelszó minimális hossza nyolc karakternél nagyobb
  - Vagy ha a karakterkészletek minimális száma kettőnél több

- **Jelszó típusa**: Megadható, hogy a jelszó csak **számjegy** karaktereket vagy számjegy és más (**Alfanumerikus**) karaktereket vegyesen tartalmazzon.
  
  - **Jelszavak nem alfanumerikus karaktereinek száma:** Ha a **Megkövetelt jelszótípus** **alfanumerikus**, ez a beállítás határozza meg a jelszóban használandó karakterkészletek minimális számát. A négy karakterkészlet a következő:
    - Kisbetűk
    - Nagybetűk
    - Szimbólumok
    - Számok

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk. A Windows rendszerű és Microsoft-fiókkal elért eszközök esetén a megfelelőségi szabályzat kiértékelése helytelen, ha a jelszó minimális hossza hosszabb nyolc karakternél, vagy ha a karakterkészletek minimális száma meghaladja a kettőt.

- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány korábbi jelszó ne legyen újra felhasználható.

#### <a name="encryption"></a>Encryption

- **Titkosítás megkövetelése mobileszközön:**: **Megkövetelhető**, hogy az eszközök csak titkosítás használata esetén csatlakozhassanak az adattároló erőforrásokhoz.

## <a name="windows-10-and-later-policy-settings"></a>Windows 10 és újabb verziók szabályzati beállításai

### <a name="device-health"></a>Device health

- **BitLocker megkövetelése**: Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni az eszközön tárolt adatokat a jogosulatlan hozzáféréstől, amikor a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker-meghajtótitkosítás titkosítja a Windows operációs rendszer kötetén tárolt összes adatot. A BitLocker a TPM-mel segíti elő a Windows operációs rendszer és a felhasználói adatok védelmét. Segít abban is, hogy ne lehessen illetéktelenül hozzáférni a számítógéphez akkor sem, ha az felügyelet nélkül van, elveszett vagy ellopták. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM-mel zárolja az adatokat védő titkosítási kulcsokat. Ezért a kulcsok nem érhetők el addig, amíg a TPM nem ellenőrizte a számítógép állapotát.
- **Biztonságos rendszerindítás engedélyezésének megkövetelése az eszközön**: Amikor a biztonságos rendszerindítás engedélyezett, az a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül amikor a biztonságos rendszerindítás engedélyezett, a gép rendszerindításához használt fő összetevőknek a megfelelő titkosított aláírásokra van szükségük, amelyekben az eszközt gyártó szervezet megbízik. Az UEFI belső vezérlőprogram ellenőrzi az aláírást, mielőtt engedélyezi a számítógép elindítását. Ha bármelyik megfigyelt fájlt illetéktelen módosítás ért az aláírás feltörésével, a rendszer nem indul el.

  > [!NOTE]
  > A **Biztonságos rendszerindítás engedélyezésének megkövetelése az eszközön** beállítás a TPM 1.2- és 2.0-eszközökön támogatott. Azon eszközök esetében, amelyek nem támogatják a TPM 2.0-s vagy újabb verzióit, az Intune-ban a szabályzat állapotánál a **Nem megfelelő** érték jelenik meg. Ez a Windows 10 [eszközállapot-igazolási](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation) szolgáltatásának egyik korlátozása miatt van.

- **Kódintegritás megkövetelése**: A kódintegritás olyan szolgáltatás, amely ellenőrzi az illesztők vagy rendszerfájlok integritását, amikor azokat betölti a memóriába. A kódintegritás észleli, ha aláíratlan illesztőprogramot vagy rendszerfájlt töltenek be a kernelbe. Azt is észleli, ha egy rendszerfájlt módosít egy olyan kártevő szoftver, amelyet rendszergazdai jogosultságokkal rendelkező felhasználói fiókkal futtatnak.

A HAS szolgáltatás működésével kapcsolatban lásd: [Állapotigazolási CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp).

A Windows Defender ATP (Advanced Threat Protection) fenyegetések elleni védelmi szolgáltatásként való beállításáról a [Windows Defender ATP engedélyezése feltételes hozzáféréssel](advanced-threat-protection.md) című témakörben talál információt.

### <a name="device-properties"></a>Eszköztulajdonságok

- **Operációs rendszer minimális verziója**: Adja meg a minimálisan megkövetelt verziót a **főverzió.alverzió.build.CU szám** formátumban. A helyes érték megtekintéséhez nyisson meg egy parancssort, és írja be a következőt: `ver`. A `ver` parancs visszaadja a verziószámot a következő formátumban:

  `Microsoft Windows [Version 10.0.17134.1]`

  Ha egy eszköz a megadott verziónál korábbi operációs rendszerrel rendelkezik, azt a rendszer nem megfelelőként fogja jelenteni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Operációs rendszer maximális verziója**: Adja meg a maximálisan megengedhető verziót a **főverzió.alverzió.build.változatszám** formátumban. A helyes érték megtekintéséhez nyisson meg egy parancssort, és írja be a következőt: `ver`. A `ver` parancs visszaadja a verziószámot a következő formátumban:

  `Microsoft Windows [Version 10.0.17134.1]`

  Ha egy eszközön a szabályban megadott operációsrendszer-verziótól újabb fut, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

- **Operációs rendszer minimális verziója mobileszközöknél**: Adja meg a minimálisan megkövetelt verziót a főverzió.alverzió.build formátumban.

  Ha egy eszköz a megadott verziónál korábbi operációs rendszerrel rendelkezik, azt a rendszer nem megfelelőként fogja jelenteni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Operációs rendszer maximális verziója mobileszközöknél**: Adja meg a maximálisan megengedett verziót a főverzió.alverzió.build formátumban.

  Ha egy eszközön a szabályban megadott operációsrendszer-verziótól újabb fut, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

- **Érvényes operációsrendszer-buildek**: Megadható az elfogadható operációsrendszer-verziók minimumot és maximumot is tartalmazó tartománya. Az elfogadható OS-buildszámok listáját vesszővel tagolt (CSV) fájlban **exportálhatja**.

### <a name="system-security-settings"></a>A rendszer biztonsági beállításai

#### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: A felhasználók **kötelesek** jelszót megadni az eszköz eléréséhez.
- **Egyszerű jelszavak**: Ha nem szeretné engedélyezni, hogy a felhasználók olyan egyszerű jelszavakat használhassanak, mint az **1234** vagy az **1111**, válassza a **Tiltás** lehetőséget. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó típusa**: Megadható, hogy a jelszó csak **számjegy** karaktereket vagy számjegy és más (**Alfanumerikus**) karaktereket vegyesen tartalmazzon.

  - **Jelszavak nem alfanumerikus karaktereinek száma:** Ha a **Megkövetelt jelszótípus** **alfanumerikus**, ez a beállítás határozza meg a jelszóban használandó karakterkészletek minimális számát. A négy karakterkészlet a következő:
    - Kisbetűk
    - Nagybetűk
    - Szimbólumok
    - Számok

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Jelszó minimális hossza**: Meghatározhatja a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Jelszó kérése legfeljebb ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Újból nem használható jelszavak száma**: Megadhatja, hogy hány korábbi jelszó ne legyen újra felhasználható.
- **Jelszó megkövetelése amikor az eszköz visszatér az inaktív állapotból (mobil és Holographic rendszer esetén)**: A felhasználóknak minden alkalommal meg kell adniuk a jelszót, amikor az eszköz visszatér az inaktív állapotból.

#### <a name="encryption"></a>Encryption

- **Adattároló titkosítása az eszközön**: A **Kötelező** lehetőséget választva az adattárolók titkosítva lesznek az eszközökön.

#### <a name="device-security"></a>Eszközbiztonság

- **Vírusvédelem**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centerben regisztrált vírusvédelmi megoldások (például Symantec és Windows Defender) használatával ellenőrizheti a megfelelőséget. A **Nincs konfigurálva** beállítás esetén az Intune nem ellenőrzi az eszközön telepített vírusvédelmi megoldásokat.
- **Kémprogram-elhárító**: Ha a **Szükséges** lehetőség van beállítva, a Windows Security Centerben regisztrált kémprogram-elhárító megoldások (például Symantec és Windows Defender) használatával ellenőrizheti a megfelelőséget. A **Nincs konfigurálva** beállítás esetén az Intune nem ellenőrzi az eszközön telepített kémprogram-elhárító megoldásokat.

### <a name="windows-defender-atp"></a>Windows Defender ATP

- **A következő vagy ez alatti számítógép-kockázati pontszám megkövetelése**: Ezzel a beállítással a fenyegetéseket elhárító szolgáltatásoktól származó kockázatbecslés lesz a megfelelőség feltétele. Megadható a legnagyobb megengedett fenyegetettségi szint:
  - **Tiszta**: Ez a legbiztonságosabb beállítás, mivel az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelésekor az eszközt a rendszer nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a legkevésbé biztonságos, minden fenyegetettségi szintet megengedő beállítás. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

A Windows Holographic for Business **Windows 10 vagy újabb** platformot használ. A Windows Holographic for Business az alábbi beállításokat támogatja:

- **Rendszerbiztonság** > **Titkosítás** > **Adattároló titkosítása az eszközön**.

A Microsoft Hololens eszköz titkosításának ellenőrzéséhez tekintse meg az [Eszköztitkosítás ellenőrzése](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) című témakört.

## <a name="surface-hub"></a>Surface Hub
A Surface Hub **Windows 10 vagy újabb** platformot használ. A Surface Hubokon a megfelelőség és a feltételes hozzáférés is támogatott. Ezeknek a funkcióknak a Surface Hubokon való engedélyezéséhez ajánlott a [Windows 10 automatikus regisztrációjának engedélyezése](windows-enroll.md) az Intune-ban (ehhez Azure Active Directory (AAD) is szükséges), és a Surface Hub-eszközök megjelölése eszközcsoportokként. A megfelelőség és a feltételes hozzáférés működéséhez a Surface Hubokat be kell léptetni az Azure Active Directoryba.

Erről a [Windowsos eszközök regisztrációjának beállítása](windows-enroll.md) című cikk nyújt útmutatást.

## <a name="assign-user-or-device-groups"></a>Felhasználói vagy eszközcsoportok hozzárendelése

1. Válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure AD-biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely felhasználói vagy eszközcsoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Ezzel érvénybe léptette a szabályzatot. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)
