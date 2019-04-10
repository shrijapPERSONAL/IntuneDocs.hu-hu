---
title: Windows 10-es megfelelőségi beállításai a Microsoft Intune – Azure |} A Microsoft Docs
description: Használhatja a Microsoft Intune-ban a Windows 10-es, a Windows holographic operációs rendszert, és a Surface Hub eszköz megfelelőségi beállításakor minden beállítások listájának megtekintéséhez. A minimális a megfelelőség ellenőrzése és az operációs rendszer maximális, jelszóra és hosszát, a megoldások keresése a partner víruskereső (Víruskereső), engedélyezheti a titkosítást az adattárolás és a további.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d956526d483a74ca5929180a48ea2dcd8b3eab7
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423628"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Windows 10-es és újabb beállításai eszközök megjelölése a megfelelő vagy nem megfelelő, az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk és ismerteti a különböző megfelelőségi beállításokat konfigurálhatja a Windows 10-es és újabb rendszerű eszközökhöz az Intune-ban. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat megkövetelése a BitLocker, állítsa be az operációs rendszer minimális és maximális, használja a Windows Defender komplex veszélyforrások elleni védelem (ATP) és további kockázati szint beállítása.

Ez a funkció az alábbiakra vonatkozik:

- Windows 10 és újabb
- Windows Holographic for Business
- Surface Hub

Intune-rendszergazdák a megfelelőségi beállítások segítségével a szervezeti erőforrások védelme érdekében. További információ a megfelelőségi szabályzatok, és milyen talál, [eszközmegfelelőség használatának első lépései](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Előkészületek

[Megfelelőségi szabályzat létrehozása](create-compliance-policy.md#create-the-policy). A **Platform** beállításnál válassza a **Windows 10 és újabb** lehetőséget.

## <a name="device-health"></a>Device health

- **BitLocker megkövetelése**: Ha a beállítása **megkövetelése**, az eszköz meg tudja védeni az adatokat a jogosulatlan hozzáférés a meghajtón tárolja, amikor a rendszer ki van kapcsolva, vagy szeretné. A Windows BitLocker-meghajtótitkosítás titkosítja a Windows operációs rendszer kötetén tárolt összes adatot. A BitLocker a TPM-mel segíti elő a Windows operációs rendszer és a felhasználói adatok védelmét. Abban is segít, győződjön meg arról, hogy a számítógép nem illetéktelenül, akkor is, ha a bal oldalán a felügyelet nélküli, az elveszett vagy ellopták. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM-mel zárolja az adatokat védő titkosítási kulcsokat. Ennek eredményeképpen a kulcsok nem érhetők el addig, amíg a TPM-eszköz ellenőrzi a számítógép állapotát.

  Ha a beállítása **nincs konfigurálva** (alapértelmezett), ez a beállítás nem kerül kiértékelésre, megfelelőségi vagy meg nem felelés.

- **Az eszközön engedélyezni kell a biztonságos rendszerindítás szükséges**: Ha a beállítása **megkövetelése**, a rendszer kényszerítetten megbízható gyári állapotban. Ha engedélyezve van, a gép használt fő összetevőknek megfelelő titkosított aláírásokra a szervezet, amely az eszköz gyártott megbízhatónak kell rendelkeznie. Az UEFI belső vezérlőprogram ellenőrzi az aláírást, mielőtt engedélyezi a számítógép elindítását. Ha a fájlok vannak illetéktelenül, amely megszakítja az aláírás feltörésével, a rendszer nem indul.

  Ha a beállítása **nincs konfigurálva** (alapértelmezett), ez a beállítás nem kerül kiértékelésre, megfelelőségi vagy meg nem felelés.

  > [!NOTE]
  > A **szükséges a biztonságos rendszerindítás engedélyezésének az eszközön** beállítás az egyes TPM 1.2-es és 2.0-s eszközökön támogatott. Azon eszközök esetében, amelyek nem támogatják a TPM 2.0-s vagy újabb verzióit, az Intune-ban a szabályzat állapotánál a **Nem megfelelő** érték jelenik meg. A támogatott verziókról további információkért lásd: [Eszközállapot-igazolás](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Kódintegritás megkövetelése**: Kódintegritási szolgáltatás ellenőrzi a illesztők vagy rendszerfájlok integritását minden alkalommal, amikor azt betölti a memóriába. Ha a beállítása **megkövetelése**, a kódintegritás észleli, ha az aláíratlan illesztőprogramot vagy rendszerfájlt töltődött be a kernelbe. Azt is észleli, ha egy fájl-e rendszergazdai jogosultságokkal rendelkező felhasználói fiók által futtatott rosszindulatú szoftver módosításokat.

  Ha a beállítása **nincs konfigurálva** (alapértelmezett), ez a beállítás nem kerül kiértékelésre, megfelelőségi vagy meg nem felelés.

További források:

- [Állapotigazolási CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) a HAS szolgáltatás működésével kapcsolatos részleteket is tartalmaz.
- [Támogatási. tipp: Eszközállapot-igazolási beállítások használata az Intune Eszközmegfelelőségi szabályzat részeként ](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Eszköztulajdonságok

- **Minimális operációsrendszer-verzió**: Adja meg a minimális verzióját az engedélyezett a **major.minor.build.CU számot** formátumban. A helyes érték megtekintéséhez nyisson meg egy parancssort, és írja be a következőt: `ver`. A `ver` parancs visszaadja a verziószámot a következő formátumban:

  `Microsoft Windows [Version 10.0.17134.1]`

  Ha egy eszközhöz tartozik egy korábbi, mint az operációs rendszer verzióját, adja meg, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt választhat. Azok a frissítés után hozzáférhet a vállalati erőforrásokhoz.

- **Maximális operációsrendszer-verzió**: Adja meg a megengedett maximális verziója, az a **főverzió.alverzió.build.változat szám** formátumban. A helyes érték megtekintéséhez nyisson meg egy parancssort, és írja be a következőt: `ver`. A `ver` parancs visszaadja a verziószámot a következő formátumban:

  `Microsoft Windows [Version 10.0.17134.1]`

  Ha egy eszköz operációsrendszer-verziónál újabb fut, a megadott, a szervezeti erőforrásokhoz való hozzáférés le van tiltva. A végfelhasználónak meg kell adnia, forduljon az IT-rendszergazdához. Az eszköz nem lehet hozzáférni a szervezet erőforrásaihoz, amíg a szabályt, hogy az operációs rendszer verziója megváltozott.

- **Mobileszközök minimális verziója**: Adja meg a által támogatott minimális verzió, a számformátumú Főverzió.alverzió.build formában.

  Ha egy eszköz rendelkezik a korábbi verziójú, hogy az operációs rendszer verziószámának ad meg, hogy nem megfelelőként. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt választhat. Azok a frissítés után hozzáférhet a vállalati erőforrásokhoz.

- **Mobileszközök maximális verziója**: Adja meg a megengedett maximális verzióját, a főverzió.alverzió.build.

  Ha egy eszköz operációsrendszer-verziónál újabb fut, a megadott, a szervezeti erőforrásokhoz való hozzáférés le van tiltva. A végfelhasználónak meg kell adnia, forduljon az IT-rendszergazdához. Az eszköz nem lehet hozzáférni a szervezet erőforrásaihoz, amíg a szabályt, hogy az operációs rendszer verziója megváltozott.

- **Érvényes operációsrendszer-buildek**: Adjon meg egy tartományt az elfogadható operációsrendszer-verziók, beleértve egy minimális és maximális. Az elfogadható OS-buildszámok listáját vesszővel tagolt (CSV) fájlban **exportálhatja**.

## <a name="configuration-manager-compliance"></a>Configuration Manager Compliance

Csak Windows 10 és újabb operációs rendszert futtató közösen kezelt eszközökre vonatkozik. Csak az Intune-eszközök nem érhető el állapotát adja vissza.

- **A System Center Configuration Manager eszköz megfelelőségének megkövetelése**: Válasszon **megkövetelése** kényszerítése minden beállítás (konfigurációelemek esetén) a System Center Configuration Managerben, meg kell felelnie. 

  Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. A Configuration Managerben az ehhez a követelményhez tartozó állapot a „Telepítve”. Ismeretlen állapotban van az eszközön a programokat, ha az eszköz akkor nem kompatibilis az Intune-ban.
  
  Amikor **nincs konfigurálva**, az Intune nem jelentkezik be, a Configuration Manager megfelelőségi beállításainak bármelyikéhez.

## <a name="system-security"></a>Rendszerbiztonság

### <a name="password"></a>Windows 10

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

### <a name="encryption"></a>Encryption

- **Egy eszközön való adattárolás titkosításának**: Válasszon **megkövetelése** az adattárolás, az eszközök titkosításához.

  > [!NOTE]
  > Az **Adattárolás titkosítása az eszközön** beállítás általánosságban ellenőrzi, hogy van-e titkosítás az eszközön. Robusztusabb titkosítási beállítás megadásához fontolja meg a **BitLocker megkövetelése** beállítás használatát, amely a windowsos Eszközállapot-igazolást használja a Bitlocker-állapot ellenőrzéséhez a TPM szintjén.

### <a name="device-security"></a>Eszközbiztonság

- **A víruskereső**: Ha beállítása **megkövetelése**, ellenőrizheti a megfelelőségi regisztrált vírusvédelmi megoldások használatával [Windows biztonsági központban](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), például a Symantec és a Windows Defender. A **Nincs konfigurálva** beállítás esetén az Intune nem ellenőrzi az eszközön telepített vírusvédelmi megoldásokat.
- **Kémprogram-elhárító**: Ha beállítása **megkövetelése**, ellenőrizheti a megfelelőségi regisztrált kémprogram-elhárító megoldásokkal [Windows biztonsági központban](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), például a Symantec és a Windows Defender. A **Nincs konfigurálva** beállítás esetén az Intune nem ellenőrzi az eszközön telepített kémprogram-elhárító megoldásokat.

## <a name="windows-defender-atp"></a>Windows Defender ATP

- **Az eszköz vagy az alatt a gép kockázati pontszám megkövetelése**: Ez a beállítás segítségével a védelmet a kockázatelemzést threat szolgáltatások igénybe a megfelelőség feltétele. Megadható a legnagyobb megengedett fenyegetettségi szint:

  - **Egyértelmű**: Ez a lehetőség akkor a legtöbb beállítás, mivel az eszköz esetében semmilyen fenyegetés nem. Ha az eszköz bármilyen szintű fenyegetés észlelése, nem megfelelőként értékeli.
  - **Alacsony**: Az eszköz abban az esetben minősül megfelelőnek Ha kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszközön észlelt fenyegetések alacsony vagy közepes szintűek. Az eszköz magas szintű fenyegetés észlelése esetén azt állapította nem kompatibilis.
  - **Magas**: Ez a beállítás a legkevésbé biztonságos, és minden kockázati szintet. Akkor lehet hasznos, ha ezt a megoldást kizárólag jelentéskészítési célokra használja.
  
  A Windows Defender ATP (Advanced Threat Protection) fenyegetések elleni védelmi szolgáltatásként való beállításáról a [Windows Defender ATP engedélyezése feltételes hozzáféréssel](advanced-threat-protection.md) című témakörben talál információt.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

A Windows Holographic for Business **Windows 10 vagy újabb** platformot használ. A Windows Holographic for Business az alábbi beállításokat támogatja:

- **Rendszerbiztonság** > **Titkosítás** > **Adattároló titkosítása az eszközön**.

A Microsoft Hololens eszköz titkosításának ellenőrzéséhez tekintse meg az [Eszköztitkosítás ellenőrzése](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) című témakört.

## <a name="surface-hub"></a>Surface Hub

A Surface Hub **Windows 10 vagy újabb** platformot használ. A Surface Hubokon a megfelelőség és a feltételes hozzáférés is támogatott. Ahhoz, hogy ezeknek a funkcióknak a Surface Hubokban, azt javasoljuk, hogy [Windows 10 automatikus regisztrációjának engedélyezése](windows-enroll.md) az Intune-ban (Azure Active Directory (Azure AD) van szükség), és célozhat meg a Surface Hub-eszközök megjelölése eszközcsoportokként. A Surface hubokon kell az Azure AD-hez a megfelelőségi és feltételes hozzáférés működéséhez szükségesek.

Erről a [Windowsos eszközök regisztrációjának beállítása](windows-enroll.md) című cikk nyújt útmutatást.

## <a name="next-steps"></a>További lépések

- [Nem megfelelő eszközök műveletek hozzáadása a](actions-for-noncompliance.md) és [használja a szűrő házirendek hatókörcímkék](scope-tags.md).
- [Az eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).
- Tekintse meg a [megfelelőségi szabályzat beállításai Windows 8.1](compliance-policy-create-windows-8-1.md) eszközök.