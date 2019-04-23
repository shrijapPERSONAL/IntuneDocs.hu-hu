---
title: Biztonsági alapterveket használja a Microsoft Intune – Azure |} A Microsoft Docs
description: Adja hozzá, vagy a felhasználó és a Microsoft Intune-nal a mobileszköz-felügyelet eszközökön lévő adatok védelme érdekében ajánlott biztonsági beállítások konfigurálása. Engedélyezze a bitlockert, a Windows Defender komplex veszélyforrások elleni védelem konfigurálása, szabályozhatja az Internet Explorer, SmartScreen használata, helyi biztonsági házirendek beállítása, jelszó kérése, internetes tölt le, és további letiltása.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b2a5e2bbd6d06cc4ec0cf71ee815229b01040a8
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61490687"
---
# <a name="create-a-windows-10-security-baseline-in-intune"></a>Az Intune-ban Windows 10 biztonsági alapterv létrehozása

Biztonsági alapterveket funkciója, amely vagy újabb Windows 10 rendszerű eszközökhöz érhető el előzetes verzióban érhető el. Ez a funkció, amellyel védelme érdekében, és a felhasználók és eszközök védelme az Intune által támogatott számos beállításokat tartalmaz. Biztonsági csapat által javasolt értékek ezek a beállítások automatikusan is beállítja. Az alapkonfiguráció például automatikusan engedélyezi a Bitlockert, automatikusan az eszköz zárolásának feloldásához jelszó szükséges, automatikusan letiltja, és alapszintű hitelesítést.

Ez a funkció az alábbiakra vonatkozik:

- A Windows 10-es 1809 és újabb verziók

> [!NOTE]
> Bár biztonsági előírások előzetes verzióban érhető el, a Microsoft nem változtassa-profilok használatával éles környezetben, mint az alapkonfigurációk előfordulhat, hogy folyamán az előzetes verzióra. Biztonsági alapterveket általánosan elérhetők, ha meglévő profilok nem konvertálja a legújabb támogatott profilokat.

A biztonsági alapterv használatával célja, hogy adjon meg egy végpontok közötti biztonságos munkafolyamatot a Microsoft 365 használatakor. Az előnyök közé:

- Egy biztonsági alaptervet az ajánlott eljárásokat és javaslatokat, amely hatással van a biztonsági beállításait tartalmazza. Az azonos Windows biztonsági csapat, amely csoport házirend biztonsági előírások hoz létre az Intune-partnerek. Ezekkel az ajánlásokkal útmutatást és széles körű ismeretekkel alapulnak.
- Ha az Intune-hoz a vadonatúj, és nem tudja, hogy hol kell elkezdeni, majd biztonsági előírások lehetővé teszi egy nagy előnnyel jár. Gyors létrehozása és üzembe helyezése egy biztonságos profilt, tudván, hogy Ön segítséget a munkahelyi erőforrások és adatok védelme.
- Ha jelenleg használja a csoportházirendet, felügyelethez az Intune-ba való migrálás sokkal egyszerűbb, mivel ezek alapterveket. Ezek az alapkonfigurációkat az Intune-hoz natív módon épülnek, és többek között a modern felügyeleti környezetet biztosít.

Biztonsági alapterveket az Intune-ban hozzon létre egy "konfigurációs profil". Ezt a profilt az alapkonfiguráció összes beállítást tartalmazza. Alkalmazása vagy a felhasználók, csoportok és eszközök hozzárendelése ehhez a profilhoz.

Miután a profil hozzá van rendelve, a profil monitorozza, és figyelheti az alaptervhez. Láthatja például, mely eszközök egyezik az alaptervhez, vagy nem egyezik az alaptervhez.

Ez a cikk bemutatja, hogyan biztonsági előírások használatával hozzon létre egy profilt a profil hozzárendelése és figyelése a profil.

[Windows biztonsági előírások](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) egy nagyszerű forrás, amely további információk a funkcióról. [Mobileszköz-kezelés](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) egy nagyszerű forrás MDM és a Windows-eszközökön elvégezhető.

## <a name="prerequisites"></a>Előfeltételek
Az Intune-ban alapkonfigurációk kezelésére, a fióknak rendelkeznie kell a [házirend- és Profilkezelő](role-based-access-control.md#built-in-roles) beépített szerepkör.


## <a name="co-managed-devices"></a>Közösen kezelt eszközök

Az Intune által felügyelt eszközökön a biztonsági előírások hasonlóak közösen kezelt eszközök Configuration Managerrel. Közösen kezelt eszközök a System Center Configuration Manager és a Microsoft Intune használatával egyszerre kezelheti a Windows 10 rendszerű eszközökre. Lehetővé teszi a meglévő Configuration Manager befektetési és az Intune felhőalapú csatolása. [Megosztott kezelés – áttekintés](https://docs.microsoft.com/sccm/comanage/overview) van egy nagyszerű forrás, ha használja a Configuration Managert, és a felhő nyújtotta előnyök is érdemes.

Közösen kezelt eszközök használata esetén kell váltania a **eszközkonfiguráció** munkaterhelés (beállítások) az Intune-hoz. [Eszköz konfigurációs számítási feladatok](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) további információkat biztosít.

## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com/), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza ki **biztonsági előírások (előzetes verzió)**. Az elérhető alapkonfigurációk listáját érhető el. További alaptervek hozzáadásakor, akkor azokat itt jelenik meg:

    ![Az Intune-ban jelenleg elérhető biztonsági alapkonfigurációit listáját lásd:](./media/security-baselines/available-baselines.png)

3. Válassza ki a használni kívánt referenciakonfiguráció > **profil létrehozása**.
4. A **alapjai**, adja meg a következő tulajdonságokat:

    - **Név**: Adja meg a biztonsági alapterveket profil nevét. Például írja be a következőt: `pilot Windows 10 MDM baseline - Oct 2018`.
    - **Description** (Leírás): Adja meg, amely azt ismerteti, Mire jó ez a alapvető szöveget. A leírás megadása nem adhatja meg a kívánt szöveget. Nem kötelező, de határozottan ajánlott.

5. Bontsa ki a **beállítások**. A listában lásd: Ez a alapvető biztonsági, és mi az automatikus beállítása a beállításokat. A beállításokat és azok értékeit használata ajánlott, és az Ön által módosítható.

    ![Bontsa ki a beállítások az Intune-ban az alapvető biztonsági beállításokról](./media/security-baselines/sample-list-of-settings.png)

    Bontsa ki az egyes beállításai ellenőrizze azok értékeit. Bontsa ki például **a Windows Defender**. Tekintse át a beállításokat, és mi van-e állítva:

    ![Milyen része a Windows Defender automatikus beállítása az Intune-ban](./media/security-baselines/expand-windows-defender.png)

6. **Hozzon létre** a profilt. 
7. Válassza ki **profilok**. A profil létrehozásáról, és látható a listában. De azt nem csinál semmit még. Ezután rendelje hozzá a profilt.

## <a name="assign-the-profile"></a>A profil hozzárendelése

A profil létrehozását követően készen áll a felhasználók, eszközök és csoportok kell hozzárendelni. Kiosztás után a a profil és a beállítások érvényesek a felhasználók, eszközök és Ön által választott csoportokhoz.

1. Válassza ki az Intune-ban **biztonsági előírások** > Válassza ki az alapkonfigurációt > **profilok**.
2. Válassza ki a profilt > **hozzárendelések**.

    ![Válassza ki a biztonsági alapkonfiguráció profilt az Intune-ban, és kattintson a profil-hozzárendelések](./media/security-baselines/assignments.png)

3. Az a **Belefoglalás** lapon vegye fel a csoportokat, felhasználók vagy eszközök a szabályzatot alkalmazni szeretné.

    > [!TIP]
    > Figyelje meg, hogy is **kizárása** csoportok. Ha a alkalmazni a szabályzatot **minden felhasználó**, fontolja meg a rendszergazdai csoportok kizárása. Abban az esetben, ha hiba történik, Ön és a rendszergazdák nem szeretne kizárva.

4. **Mentse** a változtatásokat.

Amint menti, a profil át lett helyezve eszközök során, hogy jelentkezzen be az Intune-ban. Tehát akkor fordulhat elő, azonnal.

## <a name="available-security-baselines"></a>Biztonsági alapterveket  

A következő biztonsági előírások az Intune-nal való használatra kilistázása.
- **Előzetes verzió: Mobileszköz-kezelési biztonsági alapterv**
  - Verzió: [2018. október](security-baseline-settings-windows.md)

## <a name="q--a"></a>Kérdések és válaszok

#### <a name="why-these-settings"></a>Miért ezek a beállítások?

A Microsoft biztonsági csoportja van tapasztalata közvetlenül, a Windows-fejlesztőknek és a biztonsági Közösséggel ezek a javaslatok létrehozása. Ez a alapvető beállításait a leginkább releváns biztonsági konfigurációs beállítások minősülnek. Az egyes Windows új verzióját a csapat megjeleníti a javaslatokat, újonnan kiadott funkciókat alapján állítja be.

#### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Van különbség a Windows biztonsági alapterveket a csoport házirend vs kapcsolatos ajánlások. Intune-ban?

A azonos biztonsági csoportja úgy döntött, és a beállítások minden egyes referenciakonfigurációnál rendezve. Az Intune a vonatkozó beállítások az Intune-ban biztonsági alapkonfiguráció tartalmaz. Van még néhány a csoport házirend alapkonfiguráció egy helyi tartományvezérlő jellemző. Ezek a beállítások az Intune javaslatok nem tartoznak. A többi beállítás megegyeznek.

#### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Az Intune-ban biztonsági előírások CI-k vagy a megfelelő NSIT?

Szigorúan véve, nem. A Microsoft biztonsági csapat olvas, szervezetek, például a CI-k, a fordítási javaslatait. De "CIS-kompatibilis" és a Microsoft alaptervek között egy-az-egyhez leképezés nem létezik.

#### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Milyen minősítések rendelkezik a Microsoft biztonsági előírások? 

- A Microsoft továbbra is a biztonsági előírások a csoportházirendek (GPO-k) közzététele és a [biztonsági megfelelőségi eszközkészlet](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), mert már sok éve van. Ezek alaptervek számos vállalat használja. A javaslatokat ezen alaptervek a vállalati ügyfelekkel és a külső ügynökségek, beleértve a védelmi Minisztérium (DoD), nemzeti szabványügyi és Technology (NIST) a Microsoft biztonsági csapat engagement származnak. Osztjuk meg a javaslatok és alaptervek ezek szervezetekkel. Ezek a szervezetek saját javaslatok, amelyek szorosan tükrözik a Microsoft javaslatokat is. Mobileszköz-felügyelet (MDM) fejlesztéseiről a felhőbe, a Microsoft ezen csoport házirend alapkonfigurációkat egyenértékű MDM javaslatok hozta létre. Ezek további alaptervek beépített Microsoft Intune-ba, és a felhasználók, csoportok és hajtsa végre a (vagy nem) az alapkonfiguráció megfelelőségi jelentéseket tartalmazza.

- Számos ügyfél használja az Intune általános javaslatok kiindulási pontként, és majd szabja testre a felel meg az informatikai és biztonsági igényeinek. A Microsoft Windows 10-es RS5 **MDM biztonsági alapterv** az első alapkonfiguráció felszabadítása érdekében. Ez a alapvető általános infrastruktúra, amely lehetővé teszi az ügyfelek számára, végül importálja a többi CI-k, NIST és más szabványok alapján biztonsági előírások épül. Jelenleg Windows érhető el, és végül fogja tartalmazni, iOS és Android rendszerhez.

- Áttérés a helyszíni Active Directory csoportházirendjei-ről az Azure Active Directory (AD) használatával a Microsoft Intune-nal tiszta felhőalapú megoldásokhoz. Annak érdekében, nincsenek hibrid AD és az Azure AD-hez csatlakoztatott eszközök közzétett csoportházirend-objektumok kiegészítő. Ezek az eszközök beszerezheti a mobileszköz-kezelési beállításokat a felhőből (Intune) és a csoportházirend-beállítások helyi tartományvezérlőkön, szükség szerint.

## <a name="next-steps"></a>További lépések
- Nézet a [Windows biztonsági Alapterv beállítások](security-baseline-settings-windows.md) az Intune által támogatott.  
- Ellenőrizze az állapotát és a figyelő a [alapkonfiguráció és a profil](security-baselines-monitor.md).
