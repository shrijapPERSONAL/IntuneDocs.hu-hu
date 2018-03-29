---
title: Újdonságok a Microsoft Intune-ban
titlesuffix: ''
description: Az Azure-beli Intune-portál újdonságai
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: be4d02419879a765c3d84a99b65a1184f7e8353e
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Emellett tájékozódhat a [jövőbeni változtatásokról](#whats-coming), a szolgáltatással kapcsolatos [fontos bejelentésekről](#notices) és a [korábbi verziókról](whats-new-archive.md) is.

> [!Note]
> A mobileszköz-kezelés (MDM) új hibrid funkciójával kapcsolatos további információért tekintse meg a [hibrid újdonságok oldalát](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   





## <a name="week-of-march-12-2018"></a>2018. március 12-i hét

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Frissített vezérlők az Androidhoz készült Céges portálhoz <!--976944 -->

Az Android [Material Design](https://material.io/) irányelveihez igazodva frissítettük az Androidhoz készült Céges portál alkalmazást. Az új ikonok képét [Az alkalmazás felhasználói felületének újdonságai](whats-new-app-ui.md) cikkben tekintheti meg.

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Új beállítások a Windows Defender – biztonsági rés kiaknázása elleni védelemhez <!-- 1631893 -->

Hat új **Támadási felület csökkentése** beállítás és bővített **Mappahozzáférés felügyelete: Mappavédelem** funkciók érhetők el. Ezeket a beállításokat az alábbi helyen találhatja meg: Eszközkonfiguráció\Profilok\
Profil létrehozása\Endpoint Protection\Windows Defender - biztonsági rés kiaknázása elleni védelem.

#### <a name="attack-surface-reduction"></a>Támadási felület csökkentése

|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Zsarolóprogramok elleni speciális védelem|Engedélyezve, Naplózás, Nincs konfigurálva|Zsarolóprogramok elleni agresszív védelem.|
|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése|Engedélyezve, Naplózás, Nincs konfigurálva|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése (lsass.exe).|
|Folyamatlétrehozás a PSExec- és WMI-parancsokból|Tiltás, Naplózás, Nincs konfigurálva|A PSEx-ec és WMI-parancsokból eredő folyamatlétrehozások letiltása.|
|Nem megbízható és aláíratlan, USB-ről futó folyamatok|Tiltás, Naplózás, Nincs konfigurálva|Nem megbízható és aláíratlan, USB-ről futó folyamatok letiltása.|
|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok|Tiltás, Naplózás, Nincs konfigurálva|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok letiltása.|

#### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Mappavédelem (már implementálva)|Nincs konfigurálva, Engedélyezés, Csak naplózás (már implementálva)<br><br> **Új**<br>Lemezmódosítás letiltása, lemezmódosítás naplózása|
Fájlok és mappák védelme a nemkívánatos alkalmazások által végrehajtott, jogosulatlan módosítások ellen.<br><br>**Engedélyezés**: Megakadályozza, hogy a nem megbízható alkalmazások módosítsák vagy töröljék a védett mappák fájljait, valamint hogy lemezszektorokra írjanak.<br><br>
**Csak a lemezmódosítások letiltása**:<br>Nem engedélyezi a nem megbízható alkalmazásoknak, hogy lemezszektorokra írjanak. A nem megbízható alkalmazások továbbra is módosíthatják vagy törölhetik a védett mappák fájljait.|

## <a name="week-of-february-19-2018"></a>2018. február 19-ei hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-támogatás több Apple DEP- / Apple School Manager-fiókhoz <!-- 747685 -->

Az Intune mostantól támogatja az eszközök regisztrációját akár 100 különböző [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) vagy [Apple School Manager](apple-school-manager-set-up-ios.md) típusú fiókból. Minden egyes feltöltött token külön használható fel a regisztrációs profilokhoz és eszközökhöz. Automatikusan társíthat másik regisztrációs profilt minden egyes feltöltött DEP/School Manager-tokenhez. Ha több School Manager-tokent tölt fel, egyszerre csak egyet tud megosztani a Microsoft School Data Sync-kel.

Az áttelepítés után az Apple DEP vagy ASM rendszer Graphon keresztüli kezeléséhez használt bétaverziós Graph API-k és közzétett parancsfájlok nem fognak többé működni. Már fejlesztés alatt állnak az új bétaverziós Graph API-k, és az áttelepítés után kiadjuk őket.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Felhasználónkénti regisztrációs korlátozások megtekintése <!-- 1634444 eeready wnready -->
A **Hibaelhárítás** panelen a **Hozzárendelések** lista [Regisztrációs korlátozások](enrollment-restrictions-set.md) elemét választva megjeleníthetők az egyes felhasználókra vonatkozó **regisztrációs korlátozások**.

### <a name="device-management"></a>Eszközkezelés
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>A Windows Defender állapota és a fenyegetések állapotjelentései <!--854704 -->

A Windows Defender állapotának megértése kulcsfontosságú a Windows rendszerű számítógépek kezelésében.  Ezzel a frissítéssel az Intune új jelentéseket és tevékenységeket ad hozzá a Windows Defender ügynök állapotához. Ha egy összesített állapotjelentést használ az [eszközmegfelelőségi számítási feladatban](compliance-policy-monitor.md), megtekintheti azokat az eszközöket, amelyeknek a következő elemek egyikére van szüksége:
- aláírás-frissítés
- Újraindítás
- kézi beavatkozás
- teljes vizsgálat
- egyéb, beavatkozást igénylő ügynökállapotok

Az állapotkategóriákhoz tartozó részletes jelentések ismertetik a figyelmet igénylő, illetve a **tisztaként** jelentő számítógépeket.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Új adatvédelmi beállítások az eszközkorlátozások számára <!--1308926 -->
Az eszközök számára [két új adatvédelmi beállítás](device-restrictions-windows-10.md#privacy) érhető el:
- **Felhasználói tevékenységek közzététele**: A megosztott élmények és a feladatváltóban nemrég használt erőforrások megelőzéséhez ezt a beállítást **tiltsa le**.
- **Csak a helyi tevékenységek**: A csak a helyi tevékenységek alapján megosztott használat és a feladatváltóban nemrég használt erőforrások felderítésének megelőzéséhez ezt a beállítást **tiltsa le**.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>A Microsoft Edge böngésző új beállításai <!--1469166 -->
A Microsoft Edge böngészőt használó eszközök számára [két új beállítás](device-restrictions-windows-10.md#edge-browser) érhető el: **A kedvencek fájl elérési útja** és **A Kedvencek módosításai**.

### <a name="app-management"></a>Alkalmazáskezelés
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Alkalmazások protokollkivételei <!--1035509 -->

Az Intune mobilalkalmazás-kezelésének (MAM) adatátviteli szabályzatában kivételeket hozhat létre, így megnyithat konkrét nem kezelt alkalmazásokat. Az ilyen alkalmazásoknak az informatikai részleg bizalmát kell élvezniük. A létrehozott kivételen kívül az adatátvitel továbbra is csak azokra az alkalmazásokra korlátozódik, amelyeket az Intune kezel, ha az adatátviteli szabályzat **csak felügyelt alkalmazásokhoz** van konfigurálva. Korlátozásokat protokollokkal (iOS) vagy csomagokkal hozhat létre (Android).

Például hozzáadhatja kivételként a Webex-csomagot az MAM adatátviteli szabályzatához. Ezzel lehetővé teszi a kezelt Outlook-emailek Webex-hivatkozásai számára, hogy közvetlenül a Webex alkalmazásban nyíljanak meg. Az adatátvitel továbbra is korlátozva marad az egyéb nem kezelt alkalmazásokban. További információt [Az adatátviteli szabályzat kivételei alkalmazások esetén](app-protection-policies-exception.md) című témakörben találhat.

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows Information Protection (WIP) által titkosított adatok megjelenítése a Windows keresési találatai között <!-- 1469193 -->
A Windows Információvédelem (WIP) szabályzatban egy beállítás érhető el annak megadásához, hogy a WIP által titkosított adatok megjelenjenek-e a Windows keresési találatai között. Ezt az alkalmazásvédelmi szabályzatot a Windows Információvédelem szabályzatának **Speciális beállításai** között, a **Titkosított elemek keresésének engedélyezése a Windows Search szolgáltatás indexelőprogramjában** lehetőséggel állíthatja be. Az alkalmazásvédelmi szabályzatot a *Windows 10* platformhoz kell beállítani, az alkalmazásszabályzat **Regisztrációs állapot** értékeként pedig a **Regisztrációval** értéket kell megadni. További információ: [Titkosított elemek keresésének engedélyezése a Windows Search szolgáltatás indexelőprogramjában](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Egy önfrissítő MSI-mobilalkalmazás konfigurálása <!-- 1740840 -->
Az ismert önfrissítő MSI-mobilalkalmazásokat konfigurálhatja úgy, hogy figyelmen kívül hagyják a verzióellenőrzési folyamatot. Ez a funkció akkor hasznos, ha nem szeretne versenyhelyzetbe kerülni. Ilyen típusú versenyhelyzet például akkor fordulhat elő, ha az alkalmazást egyszerre frissíti automatikusan a fejlesztő és az Intune. Mindkettő megpróbálja kényszeríteni az alkalmazás egy verziójának használatát a Windows-ügyfélen, ami üközést eredményezhet. Az ilyen automatikusan frissített MSI-alkalmazások esetében konfigurálhatja az **Alkalmazásverzió figyelmen kívül hagyása** beállítást az **Alkalmazásadatok** panelen. Ha ezt a beállítást átállítja az **Igen** értékre, a Microsoft Intune nem veszi tekintetbe a Windows-ügyfélen telepített alkalmazás verzióját.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Kapcsolódó alkalmazáslicenc-készletek Intune-támogatása <!-- 1864117 -->
Az Azure Portalbeli Intune a felhasználói felület egyedülálló alkalmazáselemeként támogatja a kapcsolódó alkalmazáslicenc-készleteket. Ezenkívül a Vállalati Microsoft Áruházból szinkronizált, offline licencelt alkalmazások egyetlen alkalmazásbejegyzésben lesznek összesítve, az egyes csomagok üzembe helyezési részleteit pedig migráljuk az egyedülálló bejegyzésbe. Ha meg szeretné tekinteni a kapcsolódó alkalmazáslicenc-készleteket az Azure Portalon, válassza a **Mobilalkalmazások** panel **Alkalmazáslicencek** lehetőségét.

### <a name="device-configuration"></a>Eszközök konfigurálása
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Windows Információvédelem (WIP) fájlkiterjesztések az automatikus titkosításhoz <!-- 1463582 -->
A Windows Információvédelem (WIP) szabályzatának egy beállításával megadható, hogy milyen kiterjesztésű fájlok legyenek automatikusan titkosítva, ha Server Message Block (SMB) megosztásról másolják őket a vállalatnak a WIP-szabályzat alapján meghatározott területén belül.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Erőforrásfiók-beállítások konfigurálása a Surface Hubokban

A Surface Hubok erőforrásfiók-beállításai távolról konfigurálhatók.

A Surface Hub az erőforrásfiókkal hitelesíthető a Skype/Exchange felé, így bekapcsolódhat az értekezletbe.
Célszerű létrehozni egy egyedi erőforrásfiókot, hogy a Surface Hub konferenciateremként jelenjen meg az értekezletben.
Az erőforrásfiók megjelenhet például **Konferenciaterem B41/6233** néven.

> [!NOTE]
> - Ha üresen hagy egyes mezőket, azzal felülírja a korábban konfigurált eszközattribútumokat.
>
> - Az erőforrásfiók tulajdonságai dinamikusan változhatnak a Surface Hubon. Például ha be van kapcsolva a jelszóváltoztatás. Így előfordulhat, hogy az Azure-konzol értékei csak egy kis idő múlva jelennek meg valós értékekként az eszközön.
>
>   Ha meg szeretné tekinteni a Surface Hub aktuálisan konfigurált beállításait, az erőforrásfiók adatait belefoglalhatja a hardverleltárba (amely jelenleg egy 7 napos intervallummal bír), vagy megjelenítheti azokat írásvédett tulajdonságokként. A távoli művelet után a pontosság javítása érdekében lekérheti a paramétereket közvetlenül a művelet futtatása után, így frissítheti a Surface Hub fiókját vagy paramétereit.


##### <a name="attack-surface-reduction"></a>Támadási felület csökkentése


|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Jelszóval védett végrehajtható tartalom futtatása e-mailből|Tiltás, Naplózás, Nincs konfigurálva|E-mailből letöltött jelszóval védett végrehajtható fájlok futtatásának megakadályozása.|
|Zsarolóprogramok elleni speciális védelem|Engedélyezve, Naplózás, Nincs konfigurálva|Zsarolóprogramok elleni agresszív védelem.|
|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése|Engedélyezve, Naplózás, Nincs konfigurálva|A Windows helyi biztonsági szervezet alrendszeréből történő hitelesítő adatok lopásának megjelölése (lsass.exe).|
|Folyamatlétrehozás a PSExec- és WMI-parancsokból|Tiltás, Naplózás, Nincs konfigurálva|A PSEx-ec és WMI-parancsokból eredő folyamatlétrehozások letiltása.|
|Nem megbízható és aláíratlan, USB-ről futó folyamatok|Tiltás, Naplózás, Nincs konfigurálva|Nem megbízható és aláíratlan, USB-ről futó folyamatok letiltása.|
|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok|Tiltás, Naplózás, Nincs konfigurálva|Az elterjedtségre, korra és megbízható listákra vonatkozó kritériumoknak nem megfelelő végrehajtható fájlok letiltása.|

##### <a name="controlled-folder-access"></a>Mappahozzáférés felügyelete

|Beállítás neve  |Beállítás lehetőségei  |Description  |
|---------|---------|---------|
|Mappavédelem (már implementálva)|Nincs konfigurálva, Engedélyezés, Csak naplózás (már implementálva)<br><br> **Új**<br>Lemezmódosítás letiltása, lemezmódosítás naplózása|
Fájlok és mappák védelme a nemkívánatos alkalmazások által végrehajtott, jogosulatlan módosítások ellen.<br><br>**Engedélyezés**: Megakadályozza, hogy a nem megbízható alkalmazások módosítsák vagy töröljék a védett mappák fájljait, valamint hogy lemezszektorokra írjanak.<br><br>
**Csak a lemezmódosítások letiltása**:<br>Nem engedélyezi a nem megbízható alkalmazásoknak, hogy lemezszektorokra írjanak. A nem megbízható alkalmazások továbbra is módosíthatják vagy törölhetik a védett mappák fájljait.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>A Windows 10 rendszerbiztonsági beállításainak és a későbbi megfelelőségi szabályzatok bővítése <!--1704133-->

Elérhető a Windows 10 megfelelőségi beállításainak bővítése, amely a tűzfalat és a Windows Defender víruskeresőt is kötelezővé teszi.


### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés
### <a name="intune-apps"></a>Intune-alkalmazások
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>A Vállalati Microsoft Áruházból származó offline alkalmazások támogatása <!--1222672-->
A Vállalati Microsoft Áruházban vásárolt offline alkalmazások mostantól szinkronizálhatók az Azure Portallal. Ezeket az alkalmazásokat eszközcsoportok vagy felhasználói csoportok számára telepítheti. Az offline alkalmazásokat az Intune, és nem az Áruház telepíti.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>A munkahelyi profilban található fiókok manuális hozzáadásának vagy eltávolításának letiltása a végfelhasználók számára <!-- 1728700 -->

A Gmail alkalmazás egy Android for Work-profilba történő telepítésekor az Android for Work Eszközkorlátozások profiljának **Fiók hozzáadása és eltávolítása** beállítása segítségével megakadályozható, hogy a végfelhasználók manuálisan fiókokat adjanak hozzá vagy távolítsanak el.

## <a name="week-of-february-5-2018"></a>2018. február 5-ei hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Új felhasználóhitelesítési lehetőség az Apple-eszközök tömeges regisztrálásakor <!-- 747625 eeready -->

> [!NOTE]
> Ez azonnal látható az új bérlők számára. A meglévő bérlők számára a áprilisban válik elérhetővé a funkció. A bevezetés befejezéséig elképzelhető, hogy nem lehet hozzáférni az új funkciókhoz.

Az Intune mostantól lehetővé teszi az eszközök Céges portál alkalmazással való hitelesítését az alábbi regisztrációs módszerek használatakor:

- Apple Készülékregisztrációs program
- Apple School Manager
- Apple Configurator-regisztráció

A Céges portál lehetőség használatakor kényszerítheti az Azure Active Directory többtényezős hitelesítését anélkül, hogy blokkolná ezen regisztrációs módszereket.

A Céges portál lehetőség választásakor az Intune kihagyja a felhasználóhitelesítést az iOS beállítási asszisztensben, és felhasználói affinitáson alapuló regisztrációt végez. Ez azt jelenti, hogy az eszköz kezdetben felhasználó nélküli eszközként lesz regisztrálva, így nem kapja meg a felhasználói csoportokhoz tartozó konfigurációkat és szabályzatokat. Ehelyett csak az eszközcsoportoktól kap konfigurációkat és szabályzatokat. Az Intune automatikusan telepíti a Céges portál alkalmazást az eszközön. A Céges portál alkalmazást elindító és abba bejelentkező első felhasználót társítja az Intune az eszközhöz. Ezen a ponton a felhasználó már megkapja a felhasználói csoporthoz tartozó konfigurációkat és szabályzatokat. Ezt a felhasználótársítást csak a regisztráció megismétlésével lehet megváltoztatni.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Intune-támogatás több Apple DEP- / Apple School Manager-fiókhoz <!-- 747685 eeready -->

Az Intune mostantól támogatja az eszközök regisztrációját akár 100 különböző Apple Device Enrollment Program (DEP) vagy Apple School Manager típusú fiókból. Minden egyes feltöltött token külön használható fel a regisztrációs profilokhoz és eszközökhöz. Automatikusan társíthat másik regisztrációs profilt minden egyes feltöltött DEP/School Manager-tokenhez. Ha több School Manager-tokent tölt fel, egyszerre csak egyet tud megosztani a Microsoft School Data Sync-kel.

Az áttelepítés után az Apple DEP vagy ASM rendszer Graphon keresztüli kezeléséhez használt bétaverziós Graph API-k és közzétett parancsfájlok nem fognak többé működni. Már fejlesztés alatt állnak az új bétaverziós Graph API-k, és az áttelepítés után kiadjuk őket.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Távoli nyomtatás biztonságos hálózaton keresztül <!-- 1709994  -->
A PrinterOn vezeték nélküli nyomtatási megoldásaival a felhasználók távolról nyomtathatnak, bárhol és bármikor, egy biztonságos hálózaton keresztül. A PrinterOn integrálva lesz az Intune APP SDK-val mind az iOS, mind pedig az Android rendszerhez. Ehhez az alkalmazáshoz az Intune felügyeleti konzol **Alkalmazásvédelmi szabályzatok** paneljével társíthat alkalmazásvédelmi szabályzatokat. A végfelhasználók letölthetik a „PrinterOn for Microsoft” alkalmazást a Play Áruházból vagy az iTunes áruházból, és használhatják azt az Intune rendszerükben.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>A macOS-es Céges portál támogatja a Készülékregisztráció-kezelős regisztrációt <!-- 1352411 -->

A felhasználók a Készülékregisztráció-kezelővel regisztrálhatnak a macOS Céges portálra.

## <a name="week-of-january-29-2018"></a>2018. január 29-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Riasztás a lejárt és hamarosan lejáró tokenekről <!-- 1639263 -->
Az áttekintő lap mostantól riasztást jelenít meg a lejárt és hamarosan lejáró tokenekről. Az egyes tokenekhez tartozó riasztásra kattintva elérheti a token részleteinek lapját.  Ha több tokenről szóló riasztásra kattint, akkor a rendszer megjeleníti az adott állapotú tokenek listáját. A rendszergazdáknak meg kell újítaniuk a tokenjeiket, mielőtt lejárnának.

### <a name="device-management"></a>Eszközkezelés

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Távoli törlési parancs támogatása macOS rendszerű eszközökön <!-- 1438084 -->

A rendszergazdák távolról is kiadhatnak törlési parancsot a macOS rendszerű eszközökön.

> [!IMPORTANT]
> A törlési parancs nem vonható vissza, ezért legyen óvatos a használatakor.

A törlési parancs eltávolítja az összes adatot az eszközről, az operációs rendszert is ideértve. Emellett az Intune-ból is eltávolítja az eszközt. Nem jelenik meg figyelmeztetés a felhasználónak, és a törlés a parancs kiadása után azonnal megkezdődik.

Be kell állítania egy 6 számjegyből álló helyreállítási PIN-kódot. Ezzel a PIN-kóddal feloldhatja az eszköz zárolását a törlést követően, mely után megkezdődik az operációs rendszer újratelepítése. A törlés megkezdése után megjelenik a PIN-kód az eszköz Intune-beli áttekintő paneljén. A PIN-kód a törlés végrehajtása alatt végig látható marad. A törlés után az eszköz eltűnik az Intune rendszerből. Ne felejtse el feljegyezni ezt a helyreállítási PIN-kódot az eszköz helyreállítását végző személy számára.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>iOS Volume Purchasing Program-token licenceinek visszavonása <!-- 820870 -->
Visszavonhatja az adott VPP-tokenhez tartozó összes iOS Volume Purchasing Program-alkalmazás (VPP-alkalmazás) licencét.

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS Volume Purchase Program-alkalmazások visszavonása  <!-- 820863 -->
Ha egy adott eszközhöz egy vagy több iOS Volume Purchase Program-alkalmazás is tartozik, akkor visszavonhatja az eszköztől az eszközalapú alkalmazáslicencet. Az alkalmazáslicenc visszavonása nem törli a vonatkozó VPP-alkalmazást az eszközről. A VPP-alkalmazás törléséhez az **Eltávolítás** műveletre kell módosítania a hozzárendelési műveletet. További információért olvassa el a [Mennyiségi vásárlási program keretében vásárolt iOS-alkalmazások kezelése a Microsoft Intune-nal](vpp-apps-ios.md) című témakört.

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Office 365-mobilalkalmazások hozzárendelése iOS- és Android-eszközökhöz a regisztrált alkalmazástípussal <!-- 1332318 -->
A **Beépített** alkalmazástípussal könnyebben hozhat létre és rendelhet Office 365-alkalmazásokat a felügyelt iOS- és Android-eszközeihez. Ezek az alkalmazások olyan 0365-alkalmazásokat tartalmaznak, mint a Word, az Excel, a PowerPoint és a OneDrive. Az alkalmazástípushoz konkrét alkalmazásokat rendelhet hozzá, valamint szerkesztheti az alkalmazásadatok konfigurációját.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Alkalmazástársítás belefoglalása vagy kizárása csoportok alapján <!-- 1406920 -->

Az alkalmazások társítása során, illetve a társítás típusának kiválasztása után megadhatja a belefoglalni, valamint a kizárni kívánt csoportokat.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>A hozzárendelések belefoglalásával és kizárásával alkalmazáskonfigurációs szabályzatot rendelhet a csoportokhoz  <!-- 1480316 -->

A hozzárendelések belefoglalásának és kizárásának kombinációjával alkalmazáskonfigurációs szabályzatot rendelhet a felhasználók és eszközök egy csoportjához. A hozzárendeléseket vagy egyénileg kijelölt csoportokként, vagy virtuális csoportként lehet kiválasztani. A virtuális csoportok a következőket tartalmazhatják: **Minden felhasználó**, **Minden eszköz**, és **Minden felhasználó és minden eszköz**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Támogatás a Windows 10-kiadások frissítési szabályzatához <!-- 903672(archived), 1119689 -->  
A Windows 10-hez létrehozhat olyan kiadásfrissítési szabályzatot, amely a Windows 10-es eszközöket az alábbi verziókra frissíti: Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education és Windows 10 Professional Education N. A Windows 10 kiadásfrissítéseiről a [Windows 10 kiadásfrissítéseinek konfigurálása](edition-upgrade-configure-windows-10.md) című témakörből tájékozódhat.

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Az Intune feltételes hozzáférési szabályzatai csak az Azure Portalon állnak rendelkezésre <!-- 1737088 1634311 -->

Ettől a kiadástól kezdődően feltételes hozzáférési szabályzatok konfigurálására és felügyeletére az [Azure Portal ](https://portal.azure.com) **Azure Active Directory** > **Feltételes hozzáférés** menüpontjában van lehetőség. A kényelmes használat céljából ez a panel az Intune-ban is elérhető az Azure Portal **Intune** > **Feltételes hozzáférés** menüpontjában.

#### <a name="updates-to-compliance-emails---1637547---"></a>Frissített megfelelőségi e-mailek <!--1637547 -->

A nem megfelelő eszközökről értesítő e-mailekben szerepelnek a nem megfelelő eszközök adatai.


## <a name="week-of-january-22-2018"></a>2018. január 22-i hét

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Új funkciók a „Feloldás” művelethez Android-eszközök esetén <!--1583480-->

Az Androidhoz készült Céges portál alkalmazás bővíti az **eszközbeállítások frissítése** esetén használható „Feloldás” műveletet az [eszköztitkosítási problémák](/intune-user-help/encrypt-your-device-android) megoldásához.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Elérhető a távoli zárolás a Windows 10-es Céges portál alkalmazásban<!--676506-->
A végfelhasználók mostantól távolról zárolhatják az eszközeiket a Windows 10-es Céges portál alkalmazásból. Ez nem jelenik meg a helyi eszközön, amit aktívan használnak.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Megfelelőségi problémák egyszerűbb megoldása a Windows 10 rendszerhez készült Céges portál alkalmazásban <!--676546-->
A Windows-eszközök végfelhasználói mostantól rá tudnak koppintani a Céges portál alkalmazásban az okra, amely miatt az eszköz nem felel meg valamelyik biztonsági szabálynak. Amikor csak lehetséges, ennek hatására meg fog jelenni az a beállítási képernyő, ahol kezelhető a probléma.

## <a name="week-of-december-11-2017"></a>2017. december 11-i hét

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Új automatikus újratelepítési beállítás <!-- 1469168 -->
Az **Automatikus újbóli üzembe helyezés** beállítás lehetővé teszi a rendszergazdai jogosultságokkal rendelkező felhasználóknak, hogy az eszköz zárolási képernyőjén a **CTRL + Win + R** billentyűkombinációval törölhessék az összes felhasználói adatot és beállítást. Ennek hatására automatikusan megtörténik az eszköz újbóli konfigurálása és regisztrálása felügyeletre. A beállítás a Windows 10 > Eszközkorlátozások > Általános > Automatikus újbóli üzembe helyezés menüpontban található. További részletekért lásd: [Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Windows 10 esetén](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>További forráskiadások támogatása a Windows 10 kiadásfrissítési szabályzatában  <!-- 903672,  1119689 -->
Mostantól a Windows 10 kiadásfrissítési szabályzatával további Windows 10-kiadásokról is frissíthet (például Windows 10 Pro, Windows 10 Pro Education és Windows 10 Cloud). Korábban a támogatott kiadásfrissítési útvonalak korlátozottabbak voltak. További információért lásd: [A Windows 10 kiadásfrissítéseinek konfigurálása](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Új beállítások az eszközkonfigurációs profilban: Windows Defender biztonsági központ (WDSC)<!-- 1335507 -->

Az Intune eszközkonfigurációs profiljának beállításai új szakasszal bővültek. Ez a **Windows Defender biztonsági központ** néven szerepel az Endpoint Protection szakasznál. A rendszergazdák beállíthatják, hogy a Windows Defender biztonsági központ mely területei legyenek elérhetők a végfelhasználók számára. Ha a rendszergazda elrejti a Windows Defender biztonsági központ valamelyik területét, a felhasználó eszközén nem fognak megjelenni az adott területtel kapcsolatos értesítések.

A rendszergazdák a következő területeket rejthetik el a Windows Defender biztonsági központ eszközkonfigurációs profilbeállításai közül:
- Vírusok és veszélyforrások elleni védelem
- Eszközteljesítmény és -állapot
- Tűzfal és hálózatvédelem
- Alkalmazás- és böngészővezérlés
- Családi beállítások

A rendszergazdák azt is személyre szabhatják, hogy a felhasználók melyik értesítéseket kapják meg. Beállítható például, hogy a felhasználók a Windows Defender biztonsági központ összes látható területének értesítéseit megkapják, vagy csak a kritikus értesítéseket. A nem kritikus értesítések közé tartoznak a Windows Defender víruskereső rendszeres összefoglalói és a vizsgálatok befejezését jelző értesítések. Minden más értesítés kritikusnak minősül. Emellett testre is szabhatja az értesítések tartalmát, például a rendszergazda elérhetőségét beágyazhatja a felhasználók eszközein megjelenő értesítések szövegébe.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Több összekötő támogatása az SCEP- és a PFX-tanúsítványok kezeléshez <!-- 1361755 -->

Azok az ügyfeleink, akik helyszíni NDES-összekötővel kézbesítik a tanúsítványokat az eszközökre, mostantól több összekötőt is beállíthatnak egy bérlőben.

Ez az új funkció támogatja az alábbi forgatókönyvet:

- **Magas rendelkezésre állás**

Az egyes NDES-összekötők lekérik a tanúsítványkérelmeket az Intune-ból.  Ha az egyik NDES-összekötő offline állapotba kerül, a másik összekötő folytathatja a kérelmek feldolgozását.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Az ügyfelek tulajdonosnevében használható az AAD_DEVICE_ID változó  <!-- 1468599 -->

Az SCEP-tanúsítványprofilok Intune-ban való létrehozásakor mostantól használhatja az AAD_DEVICE_ID változót az egyéni tulajdonosnevek létrehozásakor.   Az ilyen SCEP-profillal való tanúsítványkéréskor a rendszer lecseréli a változót a tanúsítványkérelmező eszköz AAD-eszközazonosítójára.


### <a name="device-management"></a>Eszközkezelés

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>A Jamf-ban regisztrált macOS-eszközök kezelése az Intune eszközmegfelelőségi motorjával <!-- 1592747 -->
Mostantól a Jamf a macOS-eszközök eszközállapotát is elküldheti az Intune-nak, az pedig vizsgálni fogja, hogy megfelelnek-e az eszközök az Intune konzolban meghatározott szabályzatoknak. Az eszközmegfelelőségi állapot és más feltételek (például tartózkodási hely, felhasználói kockázat) vizsgálata alapján a feltételes hozzáférés megköveteli, hogy a macOS-eszközök megfeleljenek a szabályzatoknak, ha az Azure AD-hoz kapcsolt felhőalapú vagy helyszíni alkalmazásokat érnek el (az Office 365-öt is beleértve). Tudjon meg többet [a Jamf-integráció beállításáról](conditional-access-integrate-jamf.md) és [a Jamf által felügyelt eszközök megfelelőségének kényszerítéséről](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Új iOS-eszközművelet   <!-- 1424701 -->

Mostantól leállíthatja az iOS 10.3 rendszerű felügyelt eszközöket. Ez a művelet azonnal leállítja az eszközt, anélkül, hogy a végfelhasználót figyelmeztetné. A **Leállítás (csak felügyelt eszköz esetén)** műveletet az eszköztulajdonságoknál találhatja, amikor kiválaszt egy eszközt az **Eszköz** tevékenységprofilban.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Dátum- és időmódosítás letiltása Samsung Knox-eszközökön <!-- 1468103 -->

Bevezettünk egy új funkciót, melynek segítségével letilthatja a dátum- és időmódosítást a Samsung Knox-eszközökön. Ezt a következő területen találhatja meg: **Eszközkonfigurációs profilok** > **Eszközkorlátozások (Android)** > **Általános**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Surface Hub-erőforrásfiókok támogatása <!-- 1566442  -->

Egy új eszközművelet segítségével mostantól a rendszergazdák megadhatják és frissíthetik a Surface Hubhoz társított erőforrásfiókot.

A Surface Hub az erőforrásfiókkal hitelesíthető a Skype/Exchange felé, így bekapcsolódhat az értekezletbe. Létrehozhat egy egyedi erőforrásfiókot, hogy a Surface Hub konferenciateremként jelenjen meg az értekezletben. Az erőforrásfiók megjelenhet például *Konferenciaterem B41/6233* néven. A Surface Hub-erőforrásfiókot (vagyis az eszközfiókot) általában a konferencia helyszínéhez kell beállítani akkor, amikor az erőforrásfiók egyéb paramétereit is meg kell változtatni.

Ha a rendszergazdák megpróbálják frissíteni az eszköz erőforrásfiókjának adatait, meg kell adniuk az eszközhöz rendelt Active Directory-beli/Azure Active Directory-beli hitelesítő adatokat. Ha az eszköznél jelszóváltoztatás van beállítva, a rendszergazdának az Azure Active Directoryban kell megkeresnie a jelszót.

> [!NOTE]
> A mezőket egy csomagban küldi el a rendszer, és az összes korábban beállított mező értékét felülírja. Az üres mezők is felülírják a meglévő mezőket.

A rendszergazdák a következő beállításokat konfigurálhatják:

- **Erőforrásfiók**
   - **Active Directory-felhasználó**

      Tartománynév\felhasználónév vagy egyszerű felhasználónév (UPN): user@domainname.com

   - **Jelszó**

- **További nem kötelezően kitöltendő erőforrásfiók-paraméterek**  (az adott erőforrásfiókkal kell beállítani)

   - **Jelszóváltoztatás gyakorisága**

     Gondoskodik róla, hogy a fiók jelszavát a Surface Hub biztonsági okokból minden héten automatikusan frissítse. A funkció bekapcsolását követően a további paraméterek beállításához új jelszót kell kérni a fiókhoz az Azure Active Directoryban.

   - **SIP-cím**

     Csak abban az esetben szükséges, ha az automatikus felfedezés sikertelen.

   - **Email**

     Az eszköz/erőforrásfiók e-mail-címe.

   - **Exchange-kiszolgáló**

     Csak abban az esetben szükséges, ha az automatikus felfedezés sikertelen.

   - **Naptár-szinkronizálás**

     A naptár-szinkronizálás és más Exchange Server-szolgáltatások engedélyezését teszi lehetővé. Például: értekezlet-szinkronizálás.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Office-alkalmazások telepítése macOS-eszközökre <!-- 1494311 -->
Mostantól macOS-eszközökre is telepíthetők az Office-alkalmazások. Az új alkalmazástípusnak köszönhetően telepíteni lehet a Word, az Excel, a PowerPoint, az Outlook és a OneNote alkalmazást. Az alkalmazások a Microsoft AutoUpdater (MAU) szolgáltatást is tartalmazzák, amely segít a biztonság megőrzésében és az alkalmazások folyamatos frissítésében.

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>iOS Volume Purchasing Program-token törlése <!-- 820879 -->
A konzol segítségével törölheti az iOS Volume Purchasing Program (VPP) tokenjét. Ez akkor lehet szükséges, ha egy VPP-token több példányban van meg.

### <a name="intune-apps"></a>Intune-alkalmazások


### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Az Aktuális felhasználó nevű új entitásgyűjtemény a jelenleg aktív felhasználói adatokra korlátozódik <!-- 1667026 -->

A **Felhasználók** entitásgyűjtemény a vállalaton belül hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználót tartalmazza. Például az elmúlt egy hónap során hozzáadhattak az Intune-hoz egy felhasználót, majd el is távolíthatták onnan. A felhasználó a jelentés időpontjában nincs jelen, de az adatok tartalmazzák a felhasználót és állapotát. Ekkor létrehozhat egy olyan jelentést, amely megjeleníti a felhasználó korábbi jelenlétének időtartamát az adatokban.

Ezzel szemben az új **Aktuális felhasználó** entitásgyűjtemény csak azokat a felhasználókat tartalmazza, akiket nem távolítottak el. Az **Aktuális felhasználó** entitásgyűjtemény csak a jelenleg aktív felhasználókat tartalmazza. Az **Aktuális felhasználó** entitásgyűjteménnyel kapcsolatban az [Aktuális felhasználó típusú entitás referenciája](reports-ref-current-user.md) oldalon talál további információkat.


### <a name="updated-graph-apis----1736360---"></a>Frissített Graph API-k <!-- 1736360 -->

A jelen kiadásban frissítettük az Intune-hoz készült bétaverziós Graph API-k egy részét. További információt a [Graph API havi változásnaplójában](https://developer.microsoft.com/graph/docs/concepts/changelog) találhat.

## <a name="week-of-december-4-2017"></a>2017. december 4-i hét

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Az Intune támogatja a Windows Information Protection (WIP) által tiltott alkalmazásokat <!-- 1479103 -->
A tiltott alkalmazásokat az Intune-ban lehet meghatározni. Tiltás esetén az adott alkalmazás nem férhet hozzá vállalati információkhoz, ellentétben az engedélyezett listán lévő alkalmazásokkal. További információért lásd: [A Windows Information Protection ajánlott letiltási listája](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="week-of-november-27-2017"></a>2017. november 27-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Regisztrálással kapcsolatos problémák elhárítása <!-- 746324 -->

A **Hibaelhárítás** munkaterületen mostantól megtalálhatók a felhasználói regisztrálással kapcsolatos problémák. A hiba adatai és a megoldáshoz javasolt lépések segítséget nyújtanak a rendszergazdának és az ügyfélszolgálati munkatársaknak a hibalehárításban. A rendszer nem jegyez fel minden regisztrálási hibát, és bizonyos hibáknál nem kínál fel megoldási javaslatokat.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Csoportregisztrációs korlátozások <!-- 747598 -->

Intune-rendszergazdaként mostantól létrehozhat [egyéni, eszköztípusra és eszközkorlátra vonatkozó regisztrációs korlátozásokat a felhasználói csoportok számára](enrollment-restrictions-set.md).

Az Intune Azure Portalon akár 25 példányt hozhat létre az egyes korlátozástípusokból, amelyeket aztán felhasználói csoportokhoz rendelhet. A csoportkorlátozások felülírják az alapértelmezett korlátozásokat.

Egy korlátozástípus minden példánya egy szigorúan rendezett listában található. Ez a sorrend határozza meg az ütközések feloldásának prioritási értékét. Azokra a felhasználókra, akiket egynél több korlátozáspéldány érint, csak a legmagasabb prioritási értékkel rendelkező példány korlátozása vonatkozik. Egy adott példány prioritását a listán való húzással módosíthatja.

Ez a funkció az Android for Work-beállítások az Android for Work-regisztráció menüjéből a Regisztrációs korlátozások menübe való migrálásának során jelenik meg. Mivel a migrálás több napig is eltarthat, előfordulhat, hogy a fiókja a novemberi kiadás többi részére vonatkozóan frissül, a Regisztrációs korlátozások csoport-hozzárendelés funkciója azonban még nem jelenik meg.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Támogatás több NDES-összekötőhöz<!-- 1528104 -->

A hálózati eszközök tanúsítványigénylési szolgáltatása (NDES) lehetővé teszi a mobileszközökön tartományi hitelesítő adatok nélkül futó szoftverek számára, hogy az egyszerű tanúsítványigénylési protokoll (SCEP) alapján tanúsítványokat szerezzenek be.
Ez a frissítés több NDES-összekötő támogatását teszi lehetővé.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work-eszközök kezelése függetlenül az Android-eszközöktől <!-- 1490731 EEready-->

**Megjegyzés:** Az alábbi módosítások a novemberi frissítésben jelennek meg, azonban időbe telhet, míg végbemennek a fiókjában. Az Office 365 portálon értesítést kap arról, ha a módosítások életbe léptek a fiókjában. A bevezetés után további felügyeleti lehetőségei lesznek. A bevezetésnek nem lesz észrevehető hatása a végfelhasználók számára.

Az Intune támogatja az Android for Work-eszközök regisztrációjának az Android-platformtól független kezelését. Ezek a beállítások az **Eszközregisztráció** > **Regisztrációs korlátozások** > **Eszköztípus-korlátozások** területen kezelhetők. (Korábban az **Eszközregisztráció** > **Android for Work-regisztráció** > **Az Android for Work regisztrációs beállításai** területen voltak elérhetők.)

Alapértelmezés szerint az Android for Work-eszközök beállításai ugyanazok, mint az Android-eszközöké. Az Android for Work-beállítások módosítása után ez azonban már nem lesz így.

Ha letiltja a személyes Android for Work-regisztrációt, csak a vállalati Android-eszközök regisztrálhatók Android for Work-eszközként.

Az új beállítások használata során vegye figyelembe a következőket:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Ha még soha nem végzett előkészítést Android for Work-regisztrációhoz

Az új Android for Work-platform le van tiltva az alapértelmezett Eszköztípus-korlátozások beállításban. A funkció előkészítése után engedélyezheti az eszközök számára az Android for Work-regisztrációt. Ehhez meg kell változtatnia az alapértelmezett korlátozást, vagy létre kell hoznia egy új eszköztípus-korlátozást, amely felülírja az alapértelmezett eszköztípus-korlátozást.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Ha már végzett előkészítést Android for Work-regisztrációhoz

Ha már korábban végzett előkészítést, a további lépések a választott beállításoktól függnek:

| Beállítás | Az Android for Work állapota az alapértelmezett Eszköztípus-korlátozás beállításban | Megjegyzések |
| --- | --- | --- |
| **Minden eszköz felügyelete Android-eszközként** | Blokkolva | Minden Android-eszköznek regisztrálnia kell az Android for Work nélkül. |
| **Minden támogatott eszköz felügyelete Android for Work-eszközként** | Engedélyezett | Minden, az Android for Worköt támogató Android-eszközt regisztrálni kell az Android for Workkel. |
| **Csak a megadott csoportokban szereplő felhasználók támogatott eszközeinek felügyelete Android for Work-eszközként** | Blokkolva | Létrejött egy különálló eszköztípus-regisztrációs szabályzat, amely felülírja az alapértelmezettet. Ez a szabályzat határozza meg a korábban az Android for Work-beléptetés engedélyezéséhez kiválasztott csoportokat. A kiválasztott csoportok felhasználói továbbra is regisztrálhatják az Android for Work-eszközeiket. A többi felhasználó nem regisztrálhat eszközöket az Android for Workkel. |

A kívánt szabály minden esetben megmarad. Önnek nem kell semmilyen további lépést végeznie a környezetében az Android for Work globális vagy csoportonkénti engedélyezésének fenntartásához.

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Az alkalmazástelepítési jelentés bővült a Telepítés függőben állapottal <!-- 1249446 -->  

Az **Alkalmazás telepítésének állapota** jelentés, amely a **Mobilalkalmazások** terület **Alkalmazás** listájában tekinthető meg az egyes alkalmazásokhoz, mostantól tartalmazza a **Telepítés függőben** állapotot is a felhasználókra és az eszközökre vonatkozóan.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>iOS 11 alkalmazásleltár-API a Mobil fenyegetésészleléshez <!-- 1391759 -->

Az Intune mind a személyes, mind a vállalati tulajdonban lévő eszközöktől alkalmazásleltár-adatokat gyűjt, amelyeket elérhetővé tesz a Mobil fenyegetésészlelés szolgáltatói, például a Lookout for Work számára. Az alkalmazásleltárt iOS 11 vagy újabb operációs rendszerrel rendelkező felhasználóktól gyűjtheti be.

**Alkalmazásleltár**  
Az Intune mind a személyes, mind a vállalati tulajdonban lévő, iOS 11 vagy újabb operációs rendszerű eszközöktől alkalmazásleltár-adatokat küld az Ön Mobil fenyegetésészlelés-szolgáltatójának. Az alkalmazásleltár adatai az alábbiakat tartalmazzák:

 - Alkalmazásazonosító
 - Alkalmazásverzió
 - Alkalmazás rövid verziója
 - Alkalmazásnév
 - Alkalmazás csomagjának mérete
 - Alkalmazás dinamikus mérete
 - Az alkalmazás ellenőrzési állapota
 - Az alkalmazás felügyeleti állapota


### <a name="device-management"></a>Eszközkezelés

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Hibrid MDM-felhasználók és -eszközök migrálása az önálló Intune szolgáltatásba <!-- 1463747 wnready -->
Az Azure Portalon mostantól új folyamatok és eszközök érhetők el a felhasználók és eszközeik hibrid MDM-ből Intune-ba való áthelyezésének elvégzéséhez, melyekkel az alábbiakra van lehetősége:
- Szabályzatok és profilok másolása a Configuration Manager-konzolból az Intune-ba az Azure Portal használatával
- Felhasználók részhalmazának áthelyezése az Intune-ba az Azure Portal használatával, miközben a többi felhasználó a hibrid MDM-ben marad
- Eszközök migrálása az Intune-ba az Azure Portal használatával újbóli regisztráció nélkül

A részletekért lásd: [Hibrid MDM-felhasználók és -eszközök migrálása az önálló Intune szolgáltatásba](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Magas rendelkezésre állású helyszíni Exchange Connector támogatása  <!-- 676614 -->
Miután az Exchange-összekötő létrehozott egy Exchange-kapcsolatot a megadott CAS (ügyfél-hozzáférési kiszolgáló) használatával, mostantól képes felfedezni más CAS kiszolgálókat is. Ha az elsődleges CAS elérhetetlenné válik, az összekötő átvált egy másik CAS-ra (ha elérhető), amíg az elsődleges CAS elérhetősége helyre nem áll. További információért lásd: [Magas rendelkezésre állású helyszíni Exchange Connector támogatása](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS-eszköz távoli újraindítása (csak felügyelt eszközök esetén) <!-- 1424595 -->

Eszközművelettel újraindíthat egy felügyelt, iOS 10.3 vagy újabb operációs rendszerű eszközt. További információ az eszköz-újraindítás műveletről: [Az eszközök távoli újraindítása az Intune-nal](device-restart.md).

> [!Note]
> Ehhez a parancshoz felügyelt eszközökre és az **Eszközzárolás** hozzáférési jogosultságra van szükség. Az eszköz azonnal újraindul. A PIN-kóddal zárolt iOS-eszközök nem csatlakoznak újra a Wi-Fi-hálózatokra az újraindítás után, így előfordulhat, hogy ilyen esetekben nem tudnak kommunikálni a kiszolgálóval.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Egyszeri bejelentkezés támogatása iOS-en <!-- 1333645 -->  

Az iOS-felhasználók is használhatják az egyszeri bejelentkezést. Azok az iOS-alkalmazások, amelyek az egyszeri bejelentkezés hasznos forgalmában található felhasználói hitelesítő adatok keresésére vannak kódolva, ezzel a hasznosforgalom-konfigurációs frissítéssel fognak működni. Emellett az egyszerű felhasználónévvel és az Intune-eszközazonosítóval is konfigurálhatja az egyszerű nevet és a tartományt. A részletekért lásd: [Az Intune konfigurálása egyszeri bejelentkezéshez iOS-es eszközökön](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Az „iPhone keresése” alkalmazás hozzáadása személyes eszközökhöz <!--1427287-->
Mostantól megtekintheti, hogy az iOS-eszközökön be van-e kapcsolva az aktiválási zár. Ez a szolgáltatás korábban a klasszikus Intune-portálon volt elérhető.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Felügyelt macOS-eszközök távoli zárolása az Intune-nal <!-- 1437691 -->

Zárolhatja az elveszett macOS-eszközöket, és beállíthat egy hat számjegyű jelszó-helyreállító PIN-kódot. A zárolt eszköz **Az eszköz áttekintése** panelén megjelenik a PIN-kód mindaddig, amíg az eszköznek nem kell egy másik műveletet végrehajtania.

További információ: [Felügyelt eszközök távoli zárolása az Intune-nal](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Új támogatott SCEP-profiladatok <!-- 1559808 -->

A rendszergazdák további beállításokat adhatnak meg a SCEP-profilok létrehozásakor Windows-, iOS-, macOS- és Android-platformokon.  A rendszergazdák a tárgy névformátumának IMEI-t, sorozatszámot vagy köznapi nevet adhatnak meg, beleértve az e-mail-címeket.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Adatok megőrzése a gyári beállítások visszaállításakor <!--1588489 -->
A Windows 10 rendszer 1709-es és újabb verziójának gyári beállításokra való visszaállítása egy új funkcióval bővült. A rendszergazdák megszabhatják, hogy az eszközregisztráció és egyéb kiépített adatok megmaradjanak-e az eszközökön a gyári beállítások visszaállítása után.

A következő adatok maradnak meg az eszközön a gyári beállítások visszaállításakor:
- Az eszközhöz társított felhasználói fiókok
- A gép állapota (tartományhoz való csatlakozás, Azure Active Directory-csatlakozás)
- MDM-regisztráció
- Az eredeti berendezésgyártók által telepített alkalmazások (áruház és Win32-alkalmazások)
- Felhasználói profil
- A felhasználói profilon kívüli felhasználói adatok
- Felhasználói automatikus bejelentkezés

Az alábbi adatok nem őrződnek meg:
- Felhasználói fájlok
- A felhasználók által telepített alkalmazások (áruház és Win32-alkalmazások)
- Nem alapértelmezett eszközbeállítások

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Megjelennek a Windows 10 frissítési kör hozzárendelései <!-- 1621837 -->
**Hibaelhárítás** során az éppen megtekintett felhasználónál láthatja a Windows 10 frissítési körének hozzárendeléseit.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>A Windows Defender Komplex veszélyforrások elleni védelem jelentéseinek gyakorisága  <!-- 1455974  -->
A Windows Defender Komplex veszélyforrások elleni védelem (WDATP) szolgáltatással a rendszergazdák kezelhetik a felügyelt eszközök jelentéseinek gyakoriságát. Az új **Telemetriai jelentések gyakoriságának növelése** beállítással a WDATP gyakrabban gyűjt adatokat és méri fel a kockázatokat. A jelentések alapértelmezett beállítása optimalizálja a sebességet és a teljesítményt. A jelentések gyakoriságának növelése értékes lehet a magas fokú kockázattal bíró eszközök esetében. Ez a beállítás a **Windows Defender ATP** profilban, az **Eszközkonfigurációk** területen érhető el.

#### <a name="audit-updates----1412961---"></a>Naplózási frissítések <!-- 1412961 -->  
Az Intune-naplózás az Intune-hoz kapcsolódó változtatási műveletekről szolgáltat információt.  Minden létrehozási, frissítési, törlési és távoli feladatműveletet rögzít és egy évig megőriz.  Az Azure Portalon megtekintheti az elmúlt 30 nap naplózási adatait számítási feladatonként, szűrhető állapotban.  Egy kapcsolódó Graph API segítségével lekérheti az elmúlt egy év tárolt naplózási adatait.

A naplózás funkció a **FIGYELÉS** csoportban érhető el. A csoportban minden számítási feladathoz tartozik egy **Naplók** menüpont.




## <a name="week-of-november-20-2017"></a>2017. november 20-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="google-play-protect-support-on-android----908720---"></a>Google Play Protect-támogatás Androidon <!-- 908720 -->

Az Android Oreo megjelenésétől kezdve a Google egy új védelmi funkciót vezetett be Google Play Protect néven, amely lehetővé teszi, hogy a felhasználók és a szervezetek biztonságos alkalmazásokat és biztonságos Android-rendszerképeket futtassanak. Az Intune mostantól támogatja a Google Play Protect-funkciókat, például a SafetyNet távoli igazolást. A rendszergazdák olyan megfelelőségi szabályzatokat állíthatnak be, amelyek megkövetelik a Google Play Protect konfigurálását és biztonságos állapotát.
A **SafetyNet eszközigazolás** beállítás azt követeli meg, hogy az eszköz kapcsolódjon egy Google-szolgáltatáshoz, amely igazolja, hogy az eszköz a biztonságot tekintve kifogástalan állapotban van. Android for Work esetén a rendszergazda megadhat egy olyan konfigurációs profilbeállítást is, amely megköveteli, hogy a telepített alkalmazások állapotát Google Play-szolgáltatások ellenőrizzék. Amennyiben egy eszköz nem felel meg a Google Play Protect követelményeinek, a feltételes hozzáférés meg is akadályozhatja, hogy a felhasználók hozzáférjenek a vállalati erőforrásokhoz.

- Lásd: [Eszközmegfelelőségi szabályzat létrehozása a Google Play Protect engedélyezéséhez ‒ útmutató](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Engedélyezett szövegprotokoll a felügyelt alkalmazásokból <!-- 1414050  -->

Az Intune App SDK által felügyelt alkalmazások SMS-eket küldhetnek.

## <a name="week-of-november-13-2017"></a>2017. november 13-i hét

### <a name="intune-apps"></a>Intune-alkalmazások
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Elérhető a macOS-hez készült Céges portál alkalmazás <!--1541700-->
A macOS-hez készült Intune Céges portál frissített felhasználói felületet kapott, és ezentúl átláthatóbban jeleníti meg a regisztrált eszközökkel kapcsolatos, felhasználók számára szükséges információkat és megfelelőségi értesítéseket. És ha az Intune Céges portál már telepítve van az eszközre, a macOS-hez készült Microsoft AutoUpdate gondoskodni fog a frissítéséről is. Az új, macOS-hez készült Intune Céges portál alkalmazást az Intune Céges portál webhelyről, macOS-eszközzel bejelentkezve töltheti le.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>A Microsoft Planner mostantól a mobilalkalmazás-kezelési MAM-lista engedélyezett alkalmazásai közé tartozik  <!-- 1248473 -->
A Microsoft Planner alkalmazás iOS és Android rendszerű eszközök számára készült verziói a mobilalkalmazás-kezelési MAM-lista engedélyezett alkalmazásai közé tartoznak. Az alkalmazás az összes bérlőre vonatkozóan konfigurálható az Azure Portal Intune App Protection paneljén.
- További tudnivalók az [engedélyezett alkalmazások MAM-listájáról](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Az Alkalmazásonkénti VPN követelmény frissítési gyakorisága iOS-eszközök esetén   <!-- 1547061 -->  
A rendszergazdák mostantól eltávolíthatják az alkalmazásonkénti VPN követelményét az iOS-eszközökről. Az érintett eszközök állapota a következő Intune-bejelentkezés után frissül (ez általában 15 percen belül következik be).  

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Támogatás a System Center Operations Manager Exchange Connectorhoz készült felügyeleti csomagjához <!-- 885457 -->
A System Center Operations Manager (SCOM) mostantól elérhető, az Exchange Connectorhoz készült felügyeleti csomagja segít az Exchange Connector naplófájljainak elemzésében. Ez a funkció számos lehetőséget nyújt a szolgáltatás figyelésére hibaelhárítás esetén.

## <a name="week-of-november-6-2017"></a>2017. November 6-i hét

### <a name="device-enrollment"></a>Eszközök beléptetése
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Windows 10-es eszközök közös felügyelete <!-- 1243445 -->
A közös felügyelet olyan megoldás, amely a hagyományos és a modern felügyelet között teremt átjárhatóságot, és lehetővé teszi a fokozatos áttérést. Közös felügyelet esetén a Windows 10-es eszközöket együttesen felügyeli a Configuration Manager és a Microsoft Intune, és emellett az Azure Active Directoryhoz (AD) és az Azure Active Directoryhoz (Azure AD) is csatlakoztatva vannak.  Ez a konfiguráció lehetővé teszi, hogy idővel át lehessen térni a modern megoldásra, de elegendő időt hagy a vállalatnak, ha pillanatnyilag nincs mód az azonnali áttérésre.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>A Windows-regisztráció korlátozása az operációs rendszer verziója alapján <!-- 245498 -->
Az Intune-rendszergazdák mostantól megadhatják az eszközregisztrációhoz megkövetelt minimális és maximális Winows 10-verziót. Ezek a korlátozások a **Platformkonfigurációk** panelen állíthatók be.

Az Intune továbbra is támogatja Windows 8.1 rendszerű számítógépek és telefonok regisztrációját. Alsó és felső korlát azonban csak a Windows 10 verzióihoz állítható be. A 8.1-es eszközök regisztrációjának engedélyezéséhez az alsó korlátot üresen kell hagyni.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>A Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztások <!-- 1631236 -->
Új Windows AutoPilot-hozzárendelés nélküli eszközökre vonatkozó riasztás érhető el a **Microsoft Intune** > **Eszközregisztráció** > **Áttekintés** oldalon. Ez a riasztás azt mutatja meg, hogy az AutoPilot-programban hány eszközhöz nincs hozzárendelve AutoPilot Deployment-profil. A riasztás adatai alapján a profilok létrehozhatók és a hozzárendelés nélküli eszközökhöz rendelhetők. A riasztásra kattintva megjelenik a Windows AutoPilot-eszközök részletes adatokat is tartalmazó, teljes listája. További információt a [Windows-eszközök regisztrálása a Windows AutoPilot Deployment Program használatával](https://docs.microsoft.com/intune/enrollment-autopilot) című témakörben találhat.

### <a name="device-management"></a>Eszközkezelés

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Frissítés gomb az eszközök listájához <!-- 1333581 -->
Mivel az eszközlista nem frissül automatikusan, a listában megjelenő eszközök a Frissítés gombbal frissíthetők.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Támogatás a Symantec Cloud Certification Authorityhez (CA)  <!-- 1333638 -->    
Az Intune mostantól támogatást nyújt a Symantec Cloud CA-hez, amely lehetővé teszi, hogy az Intune Tanúsítvány-összekötő a Symantec Cloud CA-től származó PKCS-tanúsítványokat bocsásson ki az Intune által felügyelt eszközökhöz. Ha már használja az Intune Tanúsítvány-összekötőt a Microsoft hitelesítésszolgáltatóval (CA), akkor az Intune Tanúsítvány-összekötő meglévő beállításaival hozzáadhatja a Symantec CA-támogatást is.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Új elemek az eszközleltárban <!--1404455 -->
A következő új elemek érhetők el mostantól a [regisztrált eszközök által rögzített leltárban](device-inventory.md):

- Wi-Fi MAC-címe
- Teljes tárterület
- Összes szabad terület
- MEID
- Előfizető szolgáltatója


### <a name="app-management"></a>Alkalmazáskezelés
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Alkalmazásokhoz való hozzáférés beállítása az eszközön telepített Android biztonsági javítás minimum szintje alapján <!-- 1278463 -->   
A rendszergazdák meghatározhatják, hogy az eszközön milyen minimális szintű Android biztonsági javításnak kell telepítve lennie ahhoz, hogy felügyelt fiók esetén hozzáférést kapjon a felügyelt alkalmazásokhoz.

> [!Note]  
> Ez a funkció csak azokat a biztonsági javítási szinteket határozza meg, amelyeket a Google az Android 6.0 vagy újabb verzióihoz tesz közzé.

#### <a name="app-conditional-launch-support----1193313---"></a>Alkalmazásfüggő indítás támogatása <!-- 1193313 -->
A rendszergazdák most már beállíthatnak egy követelményt az Azure felügyeleti portálján, amely a mobilalkalmazás-kezelésen (MAM) keresztül PIN-jelszót követel meg numerikus PIN-kód helyett, amikor az alkalmazás elindul. Ha a beállítás engedélyezve van, akkor a rendszer a felhasználót egy PIN-jelszó beállítására kéri, amelyet kötelező alkalmaznia, mielőtt hozzáférhetne a MAM-kompatibilis alkalmazásokhoz. A PIN-jelszó olyan numerikus PIN-kód, amely legalább egy speciális karaktert vagy kisbetűt/nagybetűt is tartalmaz. Az Intune jelen kiadása ezt a funkciót **csak iOS** esetén támogatja. Az Intune a PIN-jelszót a PIN-kódhoz hasonlóan támogatja minimális jelszóhossz megkövetelésével és karakterek és sorozatok ismétlődésének engedélyezésével. A funkcióhoz az alkalmazásoknak (például WXP, Outlook, Managed Browser, Yammer) integrálniuk kell az Intune App SDK-t ennek a funkciónak a kódjával, hogy a megcélzott alkalmazásoknál kötelezővé lehessen tenni a PIN-jelszóbeállításokat.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Üzleti alkalmazás verziószáma az eszköz telepítési állapotjelentésében <!-- 1233999 -->
Ettől a kiadástól kezdve az eszköz telepítési állapotjelentése megjeleníti az iOS-es és androidos üzletági alkalmazások verziószámát. A verziószám hasznos lehet az alkalmazás hibakeresésénél, vagy ha olyan eszközöket szeretne megtalálni, amelyek elavult verziószámú alkalmazásokat futtatnak.


### <a name="device-configuration"></a>Eszközök konfigurálása
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Eszközkonfigurációs profilt használó eszközök esetén a rendszergazdák most már konfigurálhatják a tűzfalbeállításokat <!-- 951708 -->   
A rendszergazdák bekapcsolhatják a tűzfalat az eszközökhöz, és különféle protokollokat konfigurálhatnak tartományhoz, valamint privát és nyilvános hálózathoz.  Ezek a tűzfalbeállítások az „Endpoint Protection” profilban találhatók.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>A Windows Defender Application Guard segít megvédeni az eszközöket a szervezet által meghatározott nem megbízható webhelyektől <!-- 958257 -->   
A rendszergazdák az egyes helyeket a Windows Information Protection munkafolyamattal, vagy az eszközkonfiguráció alatt található új „Hálózathatár” (Network boundary) profil használatával jelölhetik meg „megbízható” (trusted) vagy „vállalati” (corporate) típusúként. Ha olyan helyet néznek meg a Microsoft Edge böngészőben, amely nem szerepel a 64-bites Windows 10-es eszköz megbízhatónak jelölt hálózathatárainak listáján, akkor az egy Hyper-V virtuális számítógép böngészőjében fog megnyílni.

Az Application Guard az eszközkonfigurációs profilok között, az „Endpoint Protection” profilban található. A rendszergazdák ott konfigurálhatják a virtualizált böngésző és a gazdagép közötti és a nem megbízható és megbízható helyek közötti interakciót, valamint a virtualizált böngészőben generált adatok tárolását. Ahhoz hogy az Application Guard használható legyen egy eszközön, először konfigurálni kell egy hálózathatárt. Fontos, hogy egy eszközhöz csak egy hálózathatár legyen definiálva.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>A Windows Defender Alkalmazásvezérlés lehetővé teszi Windows 10 Enterprise rendszeren, hogy csak a jogosultsággal rendelkező alkalmazások minősüljenek megbízhatónak <!-- 1031096 -->    
Ma már naponta több ezer rosszindulatú fájlt hoznak létre, így az aláírás-alapú felderítést használó víruskereső használata már nem nyújt elegendő biztonságot a kártevők elleni védelemben, hiszen újabb és újabb típusú támadások jelennek meg. A Windows 10 Enterprise rendszeren használható Windows Defender Alkalmazásvezérlés használatával különféle eszközkonfigurációs módokat lehet beállítani, többek között olyat, amelynél az alkalmazások megbízhatónak minősülnek mindaddig, amíg egy víruskereső vagy más biztonsági megoldás le nem tiltotta őket, vagy olyat, amelynél az operációs rendszer csak a vállalat által engedélyezett alkalmazásokat tekinti megbízhatónak. Az alkalmazások megbízhatósága a Windows Defender Alkalmazásvezérlésben állítható be.

Az Intune-ban az alkalmazásvezérlési szabályzatok beállíthatók „csak naplózási” vagy kötelező módban is. „Naplózási módban” az alkalmazások nincsenek letiltva. A „naplózási mód” minden eseményt egy ügyfélnaplóban rögzít. Az is beállítható, hogy csak a Windows-összetevők és a Microsoft Áruházbeli alkalmazások futtatása legyen engedélyezve, de az Intelligent Security Graphban megbízhatóként meghatározott további alkalmazások futtatása is engedélyezhető.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>A Windows Defender Exploit Guard új behatolásmegelőzési képességeket tartalmazó készlet Windows 10 rendszerhez <!-- 1063615 -->   
A Windows Defender Exploit Guard olyan szabályokat tartalmaz, amelyekkel csökkenthető az alkalmazások rosszindulatú kihasználása, megelőzhetőek a makró- és parancsfájl-fenyegetések, automatikusan letilthatók a nem megbízhatónak tekintett IP-címek, és biztosítható az adatok védelme a zsarolóprogramok és az ismeretlen fenyegetések ellen. A Windows Defender Exploit Guard az alábbi összetevőket tartalmazza:

- A **Támadási felület csökkentése (ASR)** a makró-, parancsfájl- és e-mail-fenyegetések megelőzésére szolgáló szabályokat tartalmaz.
- A **Felügyelt mappahozzáférés** automatikusan letiltja a védett mappák tartalmához való hozzáférést.
- A **Hálózati szűrő** minden alkalmazás esetében letiltja az alacsony megbízhatóságú IP-címek vagy tartományok felé irányuló kimenő adatforgalmat
- A **Biztonsági rések elleni védelem** a memóriára, a vezérlésfolyamra és a szabályzatokra vonatkozó korlátozásokat tartalmaz, amelyekkel megvédhetők az alkalmazások a biztonsági résektől.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>PowerShell-parancsfájlok kezelése az Intune-ban Windows 10-es eszközök esetén <!-- 790537 -->

Az Intune felügyeleti bővítményével Windows 10-es eszközökön futtatandó PowerShell-parancsfájlokat tölthet fel az Intune-ba. A bővítmény kiegészíti a Windows 10 mobileszköz-kezelési (MDM-) funkcióit, és könnyebbé teszi a modern felügyeletre való váltást. További részleteket a [PowerShell-parancsfájlok kezelése az Intune-ban Windows 10-es eszközök esetén](intune-management-extension.md) című témakörben találhat.

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Új eszközkorlátozási beállítások Windows 10-hez      <!-- 1308850 -->
-    Üzenetek (csak mobil) – szöveges vagy MMS-üzenetek letiltása
-    Jelszó – beállítások FIPS engedélyezésére, valamint Windows Hello-eszközök és másodlagos eszközök hitelesítéshez való használatára 
-    Képernyő – beállítások GDI-méretezés ki- és bekapcsolására régebbi alkalmazások esetén

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Eszközkorlátozás Windows 10-es teljes képernyős mód esetén <!-- 1308872 -->   
Windows 10-es eszközök esetén lehetséges a teljes képernyős mód kötelezővé tétele, ami a felhasználók számára egy előre meghatározott alkalmazáscsoportot tesz csak elérhetővé.  Ehhez egy Windows 10-es eszközkorlátozási profilt kell létrehozni, és meg kell adni a teljes képernyős beállításokat.

A teljes képernyős mód két lehetőséget támogat: az **egyetlen alkalmazás** módot (csak egy alkalmazás futtatható), és a **több alkalmazás** módot (alkalmazások egy csoportja érhető el).  Önnek kell meghatároznia a felhasználói fiókot és az eszköznevet, amely meghatározza a támogatott alkalmazásokat).  Bejelentkezés után a felhasználó csak a meghatározott alkalmazásokhoz férhet hozzá.  További információt az [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) témakörben talál. 

A teljes képernyős módhoz az alábbiak szükségesek:

- MDM-szolgáltatóként az Intune-t kell beállítani.
- A céleszközön már telepítve kell lenniük az alkalmazásoknak.
- Az eszköznek [megfelelően kiépített](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) állapotban kell lennie.

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Új eszközkonfigurációs profil hálózathatárok létrehozásához <!-- 1311967 -->   
Egy **Hálózathatár** nevű új eszközkonfigurációs profil található meg a többi eszközkonfigurációs profil között. Ezzel a profillal olyan online erőforrásokat határozhat meg, amelyeket vállalatiként és megbízhatóként szeretne definiálni. Ahhoz, hogy az eszközön használható legyen a Windows Defender Application Guard és a Windows Information Protection vagy más funkciók, *először* definiálnia kell az eszközhöz egy hálózathatárt. Fontos, hogy egy eszközhöz csak egy hálózathatár legyen definiálva.

Definiálhat felhőbeli erőforrásokat, IP-címtartományokat és belső proxykiszolgálókat is, amelyeket megbízhatóként szeretne megjelölni. Definiálás után a hálózathatárt más funkciók is felhasználhatják, például a Windows Defender Application Guard vagy a Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Két további beállítás a Windows Defender víruskeresőhöz <!-- 1338409 -->  
**Fájlblokkolási szint**

| | |
|---|---|
| Nincs konfigurálva | A **Nincs konfigurálva** beállítás a Windows Defender víruskereső alapértelmezett blokkolási szintjét használja, és erős szintű észlelést végez anélkül, hogy a kockázatmentes fájlok észlelésének kockázatát növelné. |
| Magas | A **Magas** beállítás erős szintű észlelést eredményez.
| Magas +  | A **Magas +** beállítás a Magas szintet további védelmi funkciókkal bővíti ki, ami hatással lehet az ügyfélteljesítményre.
| Zéró tolerancia  | A **Zéró tolerancia** minden ismeretlen végrehajtható állományt letilt. |

Noha valószínűtlen, hogy megtörténik, elképzelhető, hogy a **Magas** beállításnál egyes kockázatmentes fájlok is észlelve lesznek.
Javasoljuk, hogy a fájlblokkolás szintjénél az alapértelmezés szerinti **Nincs konfigurálva** beállítást alkalmazza.

**Időtúllépési bővítmény felhőalapú fájlvizsgálathoz**  

| | |
|--|--|
| Másodpercek száma (0-50) | Adja meg azt a maximális időt, ameddig a Windows Defender víruskeresőnek blokkolnia kell a fájlt, amíg meg nem érkezik az eredmény a felhőből. Az alapértelmezett érték 10 másodperc. Az itt megadott érték (legfeljebb 50 másodperc) hozzáadódik ehhez a 10 másodperchez. A vizsgálat a legtöbb esetben a maximális időnél jelentősen rövidebb ideig tart. Az idő növelésével azonban elegendő időt biztosíthat ahhoz, hogy a felhő alaposan megvizsgálja a gyanús fájlokat. Javasoljuk, hogy engedélyezze ezt a beállítást, és értékeként legalább 20 másodpercet adjon meg. |

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN Windows 10-ez eszközökhöz <!-- 1512457 -->  
A Citrix VPN konfigurálható Windows 10 rendszerű eszközökhöz. A Citrix VPN az **Alapszintű VPN** panelen, a *Kapcsolat típusának kiválasztása* listában választható ki a Windows 10 VPN-konfigurálásakor vagy később.

> [!Note]
> A Citrix-konfiguráció iOS és Android rendszerekhez már korábban is elérhető volt.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>A Wi-Fi-kapcsolatok támogatják az előmegosztott kulcsok használatát iOS rendszer esetén <!-- 1550823 -->
Az ügyfelek konfigurálhatják a Wi-Fi-profilokat úgy, hogy azok előmegosztott kulcsokat (PSK) használjanak a WPA/WPA2-Personal-kapcsolatokhoz iOS-eszközökön. Ezek a profilok akkor lesznek leküldve a felhasználó eszközére, amikor regisztrálja az eszközt az Intune-ban.

A profilnak az eszközre való leküldése után a következő lépés a profil konfigurációjától függ.  Ha automatikus csatlakozásra van beállítva, akkor ezt teszi, amikor a hálózatra legközelebb szükség lesz.  Manuálisan csatlakozó profil esetén a felhasználónak kell aktiválnia a kapcsolatot.  

### <a name="intune-apps"></a>Intune-alkalmazások

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>A felügyelt alkalmazások naplóinak elérése iOS rendszeren <!-- 1469920 -->
Azon végfelhasználók, akiknél telepítve van a Managed Browser alkalmazás, a Microsoft által közzétett valamennyi alkalmazás felügyeleti állapotát láthatják és naplófájlokat küldhetnek a felügyelt iOS-alkalmazásaik hibaelhárításához.

A Managed Browser hibaelhárítási módjának iOS-eszközökön való engedélyezéséről [A felügyelt alkalmazások naplóinak elérése a Managed Browser használatával iOS rendszeren](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) című témakörben találhat további információt.

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Újdonságok az iOS rendszerre készült Céges portál 2.9.0-s verziójának eszközbeállítási munkafolyamatával kapcsolatban <!-- 1417174 -->

Az iOS rendszerhez készült Céges portál alkalmazás eszközbeállítási munkafolyamatának továbbfejlesztése. Nyelvezete felhasználóbarátabb lett, képernyőit – ahol lehetett – összevontuk. A nyelvezet jobban igazodik a céghez, mivel a cég neve megjelenik a telepítés során látható szövegekben. A frissített munkafolyamatot a  [Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban](whats-new-app-ui.md) oldalon tekintheti meg.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>A felhasználói entitás tartalmazza a legújabb felhasználói adatokat az adattárház adatmodelljében <!-- 1544273 -->
Az Intune-adattárház adatmodelljének első verziója csak a legújabb Intune-előzményadatokat tartalmazta. A jelentéskészítők így nem tudták felmérni a felhasználók aktuális állapotát. Ebben a frissítésben a **Felhasználói entitás** a legújabb felhasználói adatokkal lett feltöltve.


## <a name="notices"></a>Értesítések


### <a name="coming-soon-workflow-updates-to-intune-administration-ui"></a>Hamarosan: Munkafolyamat frissítések az Intune-felügyelet felhasználói felületéhez

Az Intune a márciusi kiadással megújítja a rendszergazdai felületet. Önnek nincs teendője, de a Microsoft áttekinthetőség iránti elkötelezettségének jegyében tájékoztatni szeretnénk erről. Engedélyezett Android- vagy Apple-eszközkezelés esetén az Intune eszköz- és felhasználóadatok küldésével végzi el az eszközök kezeléséhez szükséges integrációt a külső szolgáltatásokkal. A márciusi kiadásban megjelenő továbbfejlesztett rendszergazdai felhasználói felület a megosztott adatok jobb áttekintését teszi lehetővé. A felhasználói felületnek ezek a változásai a végfelhasználókat nem érintik.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?

Néhány új helyzet, amelyben az adatok megosztásához jóváhagyást kérő ablak jelenik meg:
- Android for Work engedélyezése
- Apple MDM leküldéses tanúsítványok engedélyezése és feltöltése
- Olyan Apple-szolgáltatások engedélyezése, mint a Készülékregisztrációs program, a School Manager és a mennyiségi vásárlási program (VPP)

A jóváhagyás minden esetben szigorúan csak egy mobileszköz-felügyeleti szolgáltatás futtatására vonatkozik. Ilyen például annak megerősítése, hogy egy rendszergazda engedélyezte Google- vagy Apple-eszközök regisztrálását. Az új munkafolyamatok indulásakor megosztott információról szóló dokumentáció az alábbi címeken érhető el:
- [Az Intune által a Google-nek küldött adatok](data-intune-sends-to-google.md)
- [Az Intune által az Apple-nek küldött adatok](data-intune-sends-to-apple.md)

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?

A változás előkészítéséhez Önnek nincs teendője, mivel kisebb munkafolyamat-kezelőfelületi frissítésekről van szó.
A Microsoft GDPR-megfelelőségével kapcsolatban további információért forduljon a További információk hivatkozáson keresztül elérhető Adatvédelmi központhoz.



### <a name="plan-for-change-update-where-you-configure-your-app-protection-policies"></a>Tervezett módosítás: Az alkalmazásvédelmi szabályzatok konfigurálási helyének frissítése

2018 márciusától ideiglenesen átirányítás lesz érvényben az Intune App Protection szolgáltatás az Azure Portalon található paneljéről az Intune Mobilalkalmazás paneljére az Azure Portalon. Fontos megjegyezni, hogy már minden alkalmazásvédelmi szabályzat megtalálható az Intune Mobilalkalmazás paneljén, az alkalmazáskonfigurációban. Az Intune App Protection szolgáltatás megnyitása helyett csak az Intune-t kell majd megnyitnia. Áprilisban le fog állni az átirányítás, és az Intune App Protection szolgáltatás panelje teljes egészében el lesz távolítva, mivel azon a most már az Intune-ban is megtalálható funkciók vannak duplikálva.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?
Ez a változás a különálló Intune-t használó ügyfeleket és a hibrid (az Intune-t a Configuration Managerrel használó) ügyfeleket egyaránt érinti. Az integráció leegyszerűsíti a felhőfelügyelet adminisztrációját. Mostantól csak egyetlen panelt – az Intune panelt – kell megnyitnia az Azure-ban a csoportok, a szabályzatok, az alkalmazások és a mobileszköz-felügyelet kezeléséhez.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?
Az Intune App Protection szolgáltatás panelje helyett az Intune-t jelölje meg kedvencként, és mindenképpen ismerkedjen meg az alkalmazásvédelmi szabályzatok munkafolyamatával az Intune Mobilalkalmazás paneljén. Egy rövid ideig átirányítás lesz érvényben, majd az App Protection panel el lesz távolítva. Ne feledje, hogy már minden alkalmazásvédelmi szabályzat elérhető az Intune-ban, és bármely feltételes hozzáférési szabályzatot módosíthatja az itt található dokumentáció alapján: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**További információ**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="updated-new-security-enhancements-in-the-intune-service-----1637539---"></a>Frissítve: Új biztonsági fejlesztések az Intune szolgáltatásban  <!-- 1637539 -->   

Biztonsági fejlesztéseket vezetünk be az Intune szolgáltatásban. Ezen változás részeként az Intune szolgáltatás márciusi frissítésével megjelenik egy váltógomb az Azure-beli Intune konzolján, mellyel be-vagy kikapcsolható ez a biztonsági funkció. Ha a funkció be van kapcsolva, „nem megfelelőként” lesznek megjelölve azok az eszközök, melyekhez nincs megfelelőségi szabályzat hozzárendelve.

**Hibrid ügyfelek**: Ez a változás jelenleg nem lesz bevezetve hibrid ügyfelek számára. Semmit nem kell tennie. Ugyanakkor erősen ajánlott meggyőződni arról, hogy az eszközök legalább egy megfelelőségi szabályzattal rendelkeznek.

#### <a name="how-does-this-affect-me"></a>Hogyan érint ez engem?

A változtatás a márciusi frissítéssel való bevezetésének megkezdésekor eltérően fogja érinteni attól függően, hogy vannak-e már hozzárendelve megfelelőségi szabályzatok, vagy sem.

- Ha Ön új vagy meglévő bérlő, és az eszközeinek nincsenek hozzárendelve megfelelőségi szabályzatok, a váltógomb automatikusan a **megfelelő** értékre lesz beállítva. A funkció a konzolon alapértelmezés szerint ki lesz kapcsolva. Ez nem lesz hatással a végfelhasználókra.
- Ha Ön új vagy meglévő bérlő, és vannak olyan eszközei, melyekhez van hozzárendelve megfelelőségi szabályzat, a váltógomb automatikusan a „nem megfelelő” értékre lesz beállítva. A funkció alapértelmezés szerint be lesz kapcsolva a márciusi frissítés bevezetésekor.

Ha feltételes hozzáféréssel (CA) használ megfelelőségi szabályzatokat, és a funkció be van kapcsolva, a CA innentől fogva le fog tiltani minden olyan eszközt, amelyhez nincs hozzárendelve legalább egy megfelelőségi szabályzat. Az ezen eszközökhöz társított végfelhasználók, akik korábban hozzáférhettek a levelezéshez, elveszítik a hozzáférésüket, hacsak nem rendel hozzá legalább egy megfelelőségi szabályzatot minden eszközhöz.   

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Hogyan készüljek fel a változásra?  

A feltételes hozzáférés használata esetén ajánlott bekapcsolni a funkciót, és a **nem megfelelő** értékre állítva hagyni a váltógombot. Annak elkerülése érdekében, hogy a végfelhasználók elveszítsék a levelezéshez való hozzáférésüket, győződjön meg arról, hogy minden eszközhöz hozzá van rendelve legalább egy megfelelőségi szabályzat. Az alábbi néhány változtatás segíti ennek végrehajtásában:   

- Megjelent egy **Megfelelőségi szabályzat nélküli eszközök** nevű jelentés az Intune-portálon, mellyel azonosíthatja a környezetben lévő összes olyan eszközt, amelyhez nincs hozzárendelve megfelelőségi szabályzat.
- A **Minden felhasználó** lehetőséggel könnyedén rendelhet hozzá megfelelőségi szabályzatokat minden felhasználóhoz.

Ha úgy dönt, hogy kikapcsolva hagyja a váltógombot, nincsen egyéb teendője.

**További információ**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Tervezett módosítás: A Microsoft Intune App SDK for Cordova beépülő modul támogatásának változása
Az Intune 2018. május 1-ével befejezi a [Microsoft Intune App SDK Cordova beépülő modul](app-sdk-cordova.md) támogatását. Helyette az Intune App Wrapping Tool eszköz használatát javasoljuk a Cordova-alapú alkalmazások előkészítésére a kezelhetőség és a rendelkezésre állás érdekében az Intune-ban. A módosítás életbe lépését követően a Microsoft Intune APP SDK for Cordova beépülő modul támogatása megszűnik, és frissítést sem fog kapni. Az alkalmazásfejlesztők a továbbiakban nem használhatják ezt a beépülő modult. Az Intune azt tervezi, hogy továbbra is támogatja a Cordovával készített alkalmazásokat. A Microsoft Intune APP SDK for Cordova beépülő modullal készült alkalmazások azonban csökkentett funkcionalitással fognak működni az Intune-ban. Az Intune App Wrapping Tool eszközével elvégzett alkalmazásburkolást követően az alkalmazások ugyanúgy üzembe helyezhetők a végfelhasználók számára, mint a normál esetben. A Google Play Áruházban megjelent Cordova-alapú Android-alkalmazások esetén:
- Az alkalmazás első indításakor a végfelhasználóknak meg kell adniuk a hitelesítő adataikat, hogy megkapják az Intune-szabályzatot.
- Az alkalmazásokat az Intune-felhasználókat megcélozva kell közzétenni az alkalmazásáruházban. Példa: „Contoso alkalmazás Intune-hoz”.

További információk az alkalmazásburkoló eszközről: [iOS-hez készült alkalmazásburkoló eszköz](app-wrapper-prepare-ios.md) és [Androidhoz készült alkalmazásburkoló eszköz](app-wrapper-prepare-android.md). Ha problémája vagy kérdése van, írjon az [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com) címre.

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Tervezett változtatás: Az Intune használata az Azure-on MDM-kezelésre <!-- 1227338 -->
Több mint egy évvel ezelőtt bejelentettük az [Azure Intune nyilvános előzetes verzióját](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/), hat hónapja pedig az [Intune új rendszergazdai felületének általános elérhetővé válását](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/). 2018. augusztus 31-étől kikapcsoljuk a hagyományos Silverlight-konzol mobileszköz-kezelését (MDM) azon ügyfelek számára, akik az Intune önálló verzióját használják. Ők ehelyett az [Azure Intune-t](https://aka.ms/Intune_on_Azure) használhatják a mobileszközök kezelésére. Ha még a hagyományos konzolt használja a mobileszköz-kezeléshez, ismerkedjen meg az Azure Intune-nal, és térjen át a használatára. Ez a módosítás várhatóan nem lesz hatással a végfelhasználókra. A hagyományos PC-kezelés továbbra is a Silverlightban marad. Erről a változásról, valamint annak hatásairól [itt](https://aka.ms/Intune_on_Azure_mdm) találhat további információt.


### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work-eszközök kezelése függetlenül az Android-eszközöktől <!-- 1490731 EEready-->    
**Megjegyzés:** Az alábbi módosítások a novemberi frissítésben jelennek meg, azonban időbe telhet, míg végbemennek a fiókjában. Az Office 365 portálon értesítést kap arról, ha a módosítások életbe léptek a fiókjában. A bevezetés után további felügyeleti lehetőségei lesznek. A bevezetésnek nem lesz észrevehető hatása a végfelhasználók számára.

Az Intune támogatja az Android for Work-eszközök regisztrációjának az Android-platformtól független kezelését. Ezek a beállítások az **Eszközregisztráció** > **Regisztrációs korlátozások** > **Eszköztípus-korlátozások** területen kezelhetők. (Korábban az **Eszközregisztráció** > **Android for Work-regisztráció** > **Az Android for Work regisztrációs beállításai** területen voltak elérhetők.)

Alapértelmezés szerint az Android for Work-eszközök beállításai ugyanazok, mint az Android-eszközöké. Az Android for Work-beállítások módosítása után ez azonban már nem lesz így.

Ha letiltja a személyes Android for Work-regisztrációt, csak a vállalati Android-eszközök regisztrálhatók Android for Work-eszközként.

Az új beállítások használata során vegye figyelembe a következőket:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Ha még soha nem végzett előkészítést Android for Work-regisztrációhoz

Az új Android for Work-platform le van tiltva az alapértelmezett Eszköztípus-korlátozások beállításban. A funkció előkészítése után engedélyezheti az eszközök számára az Android for Work-regisztrációt. Ehhez meg kell változtatnia az alapértelmezett korlátozást, vagy létre kell hoznia egy új eszköztípus-korlátozást, amely felülírja az alapértelmezett eszköztípus-korlátozást.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Ha már végzett előkészítést Android for Work-regisztrációhoz

Ha már korábban végzett előkészítést, a további lépések a választott beállításoktól függnek:

| Beállítás | Az Android for Work állapota az alapértelmezett Eszköztípus-korlátozás beállításban | Megjegyzések |
| --- | --- | --- |
| **Minden eszköz felügyelete Android-eszközként** | Blokkolva | Minden Android-eszköznek regisztrálnia kell az Android for Work nélkül. |
| **Minden támogatott eszköz felügyelete Android for Work-eszközként** | Engedélyezett | Minden, az Android for Worköt támogató Android-eszközt regisztrálni kell az Android for Workkel. |
| **Csak a megadott csoportokban szereplő felhasználók támogatott eszközeinek felügyelete Android for Work-eszközként** | Blokkolva | Létrejött egy különálló eszköztípus-regisztrációs szabályzat, amely felülírja az alapértelmezettet. Ez a szabályzat határozza meg a korábban az Android for Work-beléptetés engedélyezéséhez kiválasztott csoportokat. A kiválasztott csoportok felhasználói továbbra is regisztrálhatják az Android for Work-eszközeiket. A többi felhasználó nem regisztrálhat eszközöket az Android for Workkel. |

A kívánt szabály minden esetben megmarad. Önnek nem kell semmilyen további lépést végeznie a környezetében az Android for Work globális vagy csoportonkénti engedélyezésének fenntartásához.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->
A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Portalon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el az Azure Portal, javasoljuk, hogy hozzon létre egy próbafiókot az új felület kipróbálásához.

## <a name="whats-coming"></a>Mi várható?

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Új frissítés a felhasználói felülethez a Céges portál webhelyen <!--2000968-->

Áprilisban új felhasználói élményt vezetünk be a Céges portál webhelyén, melynek része a megújult felhasználói felület, az egyszerűsített műveletek és továbbfejlesztett kisegítő lehetőségek. A felhasználóbarátabb élmény érdekében az ügyfelek által javasolt olyan fejlesztéseket valósítottunk meg, mint az alkalmazások megosztása és a teljesítmény javítása általában.
Ügyfeleink javaslatai alapján olyan új funkciókat is bevezettünk, amelyek jelentősen megnövelik a jelenlegi funkciók használhatóságát és működését:

-   A webhely felhasználói felületének fejlesztései
-   Alkalmazások közvetlen hivatkozásainak megoszthatósága
- Nagy méretű alkalmazáskatalógusok javított teljesítménye

A változás érvénybe lépéséhez Önnek semmit nem kell tennie. Értesíteni fogjuk Önt, ha elérhetővé válik a megújult Céges portál webhely. Arra azonban szükség lehet, hogy a végfelhasználói dokumentumokat az új képernyőképekkel frissítse. Emellett frissítést igényelhet az iOS-es Céges portál alkalmazás dokumentációja is, mivel az iOS-alkalmazás **Alkalmazások** szakasza a webhelyre támaszkodik. Ehhez egy képet is talál az [újdonságok az alkalmazás felhasználói felületén](whats-new-app-ui.md) című oldalon.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Felhasználóiélmény-frissítés az iOS-hez készült Céges portál alkalmazásban <!--1412866-->

Egy nagyszabású felhasználóiélmény-frissítést adunk ki az iOS-es Céges portál alkalmazáshoz. A frissítés teljes mértékben átalakítja az alkalmazás látványát, modernebb külsőt, valamint könnyebb használhatóságot és elérhetőséget nyújtva. Az iOS-es Céges portál minden funkciója továbbra is ugyanúgy működik.

A frissített, iOS-es Céges portál alkalmazás előzetes verziója elérhető az Apple TestFlight programjában, amelynek keretében kipróbálhatja az alkalmazást, és visszajelzést küldhet róla. Feliratkozás a TestFlighthoz való hozzáféréshez: https://aka.ms/intune_ios_cp_testflight. A frissítéssel kapcsolatos a legújabb híreket itt találja: https://aka.ms/iOS_companyportal_update.

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->
Az Apple bejelentette, hogy konkrét követelményeket ír elő az Application Transport Security (ATS) használatakor. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja.

Az új ATS-követelményeket érvényesítő Apple TestFlight alkalmazásban elérhetővé vált a Céges portál alkalmazás iOS rendszerű verziója. Ha szeretné kipróbálni az alkalmazást az ATS-megfelelőség tesztelése céljából, küldje el a kereszt- és vezetéknevét, az e-mail-címét és a munkahelye nevét a <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> e-mail-címre. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

## <a name="see-also"></a>Lásd még:
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](https://www.microsoft.com/cloud-platform/roadmap)
* [A Céges portál felhasználói felületének újdonságai](whats-new-app-ui.md)
* [Korábbi hónapok újdonságai](whats-new-archive.md)
