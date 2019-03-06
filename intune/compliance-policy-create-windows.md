---
title: Windows-eszközök Microsoft Intune - Azure-ban megfelelőségének ellenőrzése |} A Microsoft Docs
description: Microsoft Intune-eszközmegfelelőségi szabályzatot hozhat létre vagy konfigurálhat Windows Phone 8.1, Windows 8.1 és újabb és Windows 10 és újabb rendszerű eszközökhöz. A megfelelőség szempontjából ellenőrizheti az operációs rendszer minimális és maximális verzióját, jelszóra és annak hosszára vonatkozó követelményeket állíthat be, megkövetelheti a bitlocker használatát, ellenőrizheti a harmadik féltől származó vírusvédelmi megoldásokat, beállíthatja az elfogadható fenyegetettségi szintet és az adattárolók titkosításának engedélyezését. Ez a Surface Hubra és a Windows Holographic for Businessre is vonatkozik.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ceabe17df3aeaf7790f7cf9e18eac86f7d2fb91
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57398409"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Windowsos eszközök megfelelőségi szabályzatainak hozzáadása az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Egy Intune eszközmegfelelőségi szabályzata tartalmaz szabályokat és beállításokat, az eszközök megfelelőnek minősülnek. A feltételes hozzáférés ezek a házirendek segítségével a szervezet erőforrásaihoz való hozzáférés engedélyezése vagy letiltása. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén.

A megfelelőségi szabályzatokról és azok előfeltételeiről az [Eszközmegfelelőség – első lépések](device-compliance-get-started.md) című cikk nyújt bővebb tájékoztatást.

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
| **Windows-állapotigazolás** | Karanténba helyezve: Windows 10 és Windows 10 Mobile|Not applicable: Windows 8.1 |

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

- **Operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem teljesíti a minimális verziójára vonatkozó követelményt, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ez után pedig hozzáférést kap a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszköz operációsrendszer-verziónál újabb verziójú, mint az a szabályban megadott, a vállalati erőforrásokhoz való hozzáférés le van tiltva. A felhasználónak ekkor az informatikai rendszergazdához kell fordulnia. Az eszköz nem fér hozzá a munkahelyi erőforrásokhoz, amíg nem módosítja a szabályt, amely engedélyezi az operációs rendszer verzióját.

Windows 8.1-es számítógépek esetén például a visszaadott verzió a **3**-as. Ha az operációs rendszer verziószabálya Windows 8.1-re van megadva a Windows esetén, az eszköz akkor is nem megfelelőként jelenik meg, ha Windows 8.1 operációs rendszer fut rajta.

### <a name="system-security"></a>Rendszerbiztonság

#### <a name="password"></a>Windows 10

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez.
- **Egyszerű jelszavak**: Állítsa be **blokk** így a felhasználók nem egyszerű jelszavakat használhassanak, mint például **1234** vagy **1111**. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó minimális hossza**: Adja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát.

  Windows rendszerű, Microsoft-fiókon keresztül elért eszközök esetén a megfelelőségi szabályzat nem lesz helyesen kiértékelve:
  - Ha a jelszó minimális hossza nyolc karakternél nagyobb
  - Vagy ha a karakterkészletek minimális száma kettőnél több

- **Jelszó típusa**: Válassza ki, ha a jelszó csak szükséges **numerikus** karakter, vagy ha számokat és más karaktereket vegyesen kell lennie (**alfanumerikus**).
  
  - **Jelszavak nem alfanumerikus karaktereinek száma**: Ha a **Jelszó kötelező** típusa **Alfanumerikus**, ez a beállítás határozza meg a jelszóban szereplő karakterkészletek minimális számát. A négy karakterkészlet a következő:
    - Kisbetűk
    - Nagybetűk
    - Szimbólumok
    - Számok

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk. A Microsoft-fiókkal elért eszközök esetén a megfelelőségi szabályzat kiértékelése helytelen, sikertelen:

    - Ha a jelszó minimális hossza nyolc karakternél nagyobb
    - Vagy ha a karakterkészletek minimális száma kettőnél több

- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és létre kell hoznia egy újat.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható.

#### <a name="encryption"></a>Encryption

- **Mobileszköz titkosításának kötelezővé tétele**: **Szükséges** az eszközök csak titkosítás csatlakozni az adattároló-erőforrásokat.

## <a name="windows-10-and-later-policy-settings"></a>Windows 10 és újabb verziók szabályzati beállításai

### <a name="device-health"></a>Device health

- **BitLocker megkövetelése**: Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni tárolt adatokat a jogosulatlan hozzáférés a meghajtón, ha a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker-meghajtótitkosítás titkosítja a Windows operációs rendszer kötetén tárolt összes adatot. A BitLocker a TPM-mel segíti elő a Windows operációs rendszer és a felhasználói adatok védelmét. Abban is segít, győződjön meg arról, hogy a számítógép nem illetéktelenül, akkor is, ha a bal oldalán a felügyelet nélküli, az elveszett vagy ellopták. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM-mel zárolja az adatokat védő titkosítási kulcsokat. Ennek eredményeképpen a kulcsok nem érhetők el addig, amíg a TPM-eszköz ellenőrzi a számítógép állapotát.
- **Az eszközön engedélyezni kell a biztonságos rendszerindítás szükséges**: Amikor a biztonságos rendszerindítás engedélyezett, az a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül amikor a biztonságos rendszerindítás engedélyezett, a gép rendszerindításához használt fő összetevőknek a megfelelő titkosított aláírásokra van szükségük, amelyekben az eszközt gyártó szervezet megbízik. Az UEFI belső vezérlőprogram ellenőrzi az aláírást, mielőtt engedélyezi a számítógép elindítását. Ha a fájlok vannak illetéktelenül, amely megszakítja az aláírás feltörésével, a rendszer nem indul.

  > [!NOTE]
  > A **szükséges a biztonságos rendszerindítás engedélyezésének az eszközön** beállítás az egyes TPM 1.2-es és 2.0-s eszközökön támogatott. Azon eszközök esetében, amelyek nem támogatják a TPM 2.0-s vagy újabb verzióit, az Intune-ban a szabályzat állapotánál a **Nem megfelelő** érték jelenik meg. A támogatott verziókról további információkért lásd: [Eszközállapot-igazolás](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Kódintegritás megkövetelése**: Kódintegritási szolgáltatás ellenőrzi a illesztők vagy rendszerfájlok integritását minden alkalommal, amikor azt betölti a memóriába. A kódintegritás észleli, ha az aláíratlan illesztőprogramot vagy rendszerfájlt töltődött be a kernelbe. Azt is észleli, ha egy rendszerfájlt rendszergazdai jogosultságokkal rendelkező felhasználói fiók által futtatott rosszindulatú szoftver módosul.

A HAS szolgáltatás működésével kapcsolatban lásd: [Állapotigazolási CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp).

### <a name="device-properties"></a>Eszköztulajdonságok

- **Minimális operációsrendszer-verzió**: Adja meg a minimális verzióját az engedélyezett a **major.minor.build.CU számot** formátumban. A helyes érték megtekintéséhez nyisson meg egy parancssort, és írja be a következőt: `ver`. A `ver` parancs visszaadja a verziószámot a következő formátumban:

  `Microsoft Windows [Version 10.0.17134.1]`

  Ha egy eszközhöz tartozik egy korábbi, mint az operációs rendszer verzióját, adja meg, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt választhat. Azok a frissítés után hozzáférhet a vállalati erőforrásokhoz.

- **Maximális operációsrendszer-verzió**: Adja meg a megengedett maximális verziója, az a **főverzió.alverzió.build.változat szám** formátumban. A helyes érték megtekintéséhez nyisson meg egy parancssort, és írja be a következőt: `ver`. A `ver` parancs visszaadja a verziószámot a következő formátumban:

  `Microsoft Windows [Version 10.0.17134.1]`

  Ha egy eszköz operációsrendszer-verziónál újabb fut, a szabályban megadott, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak, lépjen kapcsolatba a rendszergazdával. Az eszköz nem fér hozzá a vállalati erőforrások, addig, amíg a szabályt, hogy az operációs rendszer verziója megváltozott.

- **Mobileszközök minimális verziója**: Adja meg a által támogatott minimális verzió, a számformátumú Főverzió.alverzió.build formában.

  Ha egy eszköz rendelkezik a korábbi verziójú, hogy az operációs rendszer verziószámának ad meg, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt választhat. Azok a frissítés után hozzáférhet a vállalati erőforrásokhoz.

- **Mobileszközök maximális verziója**: Adja meg a megengedett maximális verzióját, a főverzió.alverzió.build.

  Ha egy eszközön operációsrendszer-verziónál újabb fut, az Ön adja meg, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak, lépjen kapcsolatba a rendszergazdával. Az eszköz nem fér hozzá a vállalati erőforrások, addig, amíg a szabályt, hogy az operációs rendszer verziója megváltozott.

- **Érvényes operációsrendszer-buildek**: Adjon meg egy tartományt az elfogadható operációsrendszer-verziók, beleértve egy minimális és maximális. Az elfogadható OS-buildszámok listáját vesszővel tagolt (CSV) fájlban **exportálhatja**.

### <a name="configuration-manager-compliance"></a>Configuration Manager Compliance

Csak Windows 10 és újabb operációs rendszert futtató közösen kezelt eszközökre vonatkozik. Csak az Intune-eszközök nem érhető el állapotát adja vissza.

- **A System Center Configuration Manager eszköz megfelelőségének megkövetelése**: Válasszon **megkövetelése** kényszerítése minden beállítás (konfigurációelemek esetén) a System Center Configuration Managerben, meg kell felelnie. 

  Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. A Configuration Managerben az ehhez a követelményhez tartozó állapot a „Telepítve”. Ismeretlen állapotban van az eszközön a programokat, ha az eszköz akkor nem kompatibilis az Intune-ban.
  
  Amikor **nincs konfigurálva**, az Intune nem jelentkezik be, a Configuration Manager megfelelőségi beállításainak bármelyikéhez.

### <a name="system-security-settings"></a>A rendszer biztonsági beállításai

#### <a name="password"></a>Windows 10

- **A mobileszközök zárolásának feloldásához jelszó szükséges**: **Szükséges** felhasználók csak jelszó beírása után az eszköz eléréséhez.
- **Egyszerű jelszavak**: Állítsa be **blokk** így a felhasználók nem egyszerű jelszavakat használhassanak, mint például **1234** vagy **1111**. A **Nincs konfigurálva** beállítással a felhasználók olyan jelszavakat is létrehozhatnak, mint az **1234** vagy az **1111**.
- **Jelszó típusa**: Válassza ki, ha a jelszó csak szükséges **numerikus** karakter, vagy ha számokat és más karaktereket vegyesen kell lennie (**alfanumerikus**).

  - **Jelszavak nem alfanumerikus karaktereinek száma**: Ha a **Jelszó kötelező** típusa **Alfanumerikus**, ez a beállítás határozza meg a jelszóban szereplő karakterkészletek minimális számát. A négy karakterkészlet a következő:
    - Kisbetűk
    - Nagybetűk
    - Szimbólumok
    - Számok

    Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

- **Jelszó minimális hossza**: Adja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Ennyi perc inaktivitás után kell jelszót**: Adja meg az üresjárati idő után a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki a hány nap elteltével a jelszó lejár, és létre kell hoznia egy újat.
- **Hány korábbi jelszót újból**: Adja meg a korábban használt jelszavak számát, amelyeket nem használható.
- **Jelszó kérése, ha az eszköz visszatér inaktív állapotból (Mobile és Holographic)**: Kényszerítse a felhasználókat a minden alkalommal, amikor az eszköz visszatér inaktív állapotból, adja meg a jelszót.

#### <a name="encryption"></a>Encryption

- **Egy eszközön való adattárolás titkosításának**: Válasszon **megkövetelése** az adattárolás, az eszközök titkosításához.

  > [!NOTE]
  > Az **Adattárolás titkosítása az eszközön** beállítás általánosságban ellenőrzi, hogy van-e titkosítás az eszközön. Robusztusabb titkosítási beállítás megadásához fontolja meg a **BitLocker megkövetelése** beállítás használatát, amely a windowsos Eszközállapot-igazolást használja a Bitlocker-állapot ellenőrzéséhez a TPM szintjén.

#### <a name="device-security"></a>Eszközbiztonság

- **A víruskereső**: Ha beállítása **megkövetelése**, ellenőrizheti a megfelelőségi regisztrált vírusvédelmi megoldások használatával [Windows biztonsági központban](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), például a Symantec és a Windows Defender. A **Nincs konfigurálva** beállítás esetén az Intune nem ellenőrzi az eszközön telepített vírusvédelmi megoldásokat.
- **Kémprogram-elhárító**: Ha beállítása **megkövetelése**, ellenőrizheti a megfelelőségi regisztrált kémprogram-elhárító megoldásokkal [Windows biztonsági központban](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), például a Symantec és a Windows Defender. A **Nincs konfigurálva** beállítás esetén az Intune nem ellenőrzi az eszközön telepített kémprogram-elhárító megoldásokat.

### <a name="windows-defender-atp"></a>Windows Defender ATP

- **Az eszköz vagy az alatt a gép kockázati pontszám megkövetelése**: Ez a beállítás segítségével a védelmet a kockázatelemzést threat szolgáltatások igénybe a megfelelőség feltétele. Megadható a legnagyobb megengedett fenyegetettségi szint:
  - **Egyértelmű**: Ez a lehetőség akkor a legtöbb beállítás, mivel az eszköz esetében semmilyen fenyegetés nem. Az eszköz bármilyen szintű fenyegetés észlelése esetén, nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz abban az esetben minősül megfelelőnek Ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelésekor a rendszer nem megfelelőként értékeli az eszközt.
  - **Magas**: Ez a beállítás a legkevésbé biztonságos, és minden kockázati szintet. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.
  
  A Windows Defender ATP (Advanced Threat Protection) fenyegetések elleni védelmi szolgáltatásként való beállításáról a [Windows Defender ATP engedélyezése feltételes hozzáféréssel](advanced-threat-protection.md) című témakörben talál információt.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

A Windows Holographic for Business **Windows 10 vagy újabb** platformot használ. A Windows Holographic for Business az alábbi beállításokat támogatja:

- **Rendszerbiztonság** > **Titkosítás** > **Adattároló titkosítása az eszközön**.

A Microsoft Hololens eszköz titkosításának ellenőrzéséhez tekintse meg az [Eszköztitkosítás ellenőrzése](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) című témakört.

## <a name="surface-hub"></a>Surface Hub
A Surface Hub **Windows 10 vagy újabb** platformot használ. A Surface Hubokon a megfelelőség és a feltételes hozzáférés is támogatott. Ahhoz, hogy ezeknek a funkcióknak a Surface Hubokban, azt javasoljuk, hogy [Windows 10 automatikus regisztrációjának engedélyezése](windows-enroll.md) az Intune-ban (is igényel az Azure Active Directory (Azure AD)), és célozhat meg a Surface Hub-eszközök megjelölése eszközcsoportokként. A Surface hubokon kell az Azure AD-hez a megfelelőségi és feltételes hozzáférés működéséhez szükségesek.

Erről a [Windowsos eszközök regisztrációjának beállítása](windows-enroll.md) című cikk nyújt útmutatást.

## <a name="assign-user-or-device-groups"></a>Felhasználói vagy eszközcsoportok hozzárendelése

1. Válasszon ki egy konfigurált szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure AD-biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely felhasználói vagy eszközcsoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Ezzel érvénybe léptette a szabályzatot. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

## <a name="next-steps"></a>További lépések
[Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz](actions-for-noncompliance.md)  
[Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)
