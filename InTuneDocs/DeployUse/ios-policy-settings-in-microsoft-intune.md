---
title: "Az iOS szabályzatbeállításai | Microsoft Intune"
description: "Szabályzatok létrehozása Intune-ban felügyelt iOS-eszközök beállításainak és funkcióinak felügyeletére."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cd5930995a6da130fedcb6d89851460e6f0614eb
ms.openlocfilehash: 24540a74ce98adbf3f908cbea401328f027867ca


---

# iOS-szabályzatbeállítások a Microsoft Intune-ban

Az Intune számos beépített beállítási lehetőséget kínál, amelyeket iOS-eszközökön konfigurálhat. Ezen kívül használhatja az Apple Configurator eszközt is olyan egyéni beállítások létrehozására, amelyek nem érhetők el az Intune-ban.

## Az általános konfigurációs szabályzat beállításai

A Microsoft Intune **iOS-hoz készült általános konfigurációs szabályzatát** a következő beállítások konfigurálásához használhatja:

-   **Általános eszköz- és biztonsági beállítások**. Az előre meghatározott beállítások listájából választva számos szolgáltatást és funkciót szabályozhat az eszközökön.

-   **Kioszkmód**. Zárolhatja az eszközöket, hogy csak bizonyos szolgáltatások működjenek rajtuk. Megadhatja például, hogy az eszköz csak egy meghatározott felügyelt alkalmazás futtatását engedélyezze, vagy letilthatja a hangerő-szabályozó gombok használatát. Ezek a beállítások használhatók például egy eszköz bemutató modelljéhez vagy olyan eszközökhöz, amelyek dedikáltan egyetlen funkciót hajtanak végre (például a pénztári eszközök).

-   **Megfelelő és nem megfelelő alkalmazások**. Adja meg a vállalatnál megfelelőnek vagy nem megfelelőnek ítélt alkalmazások listáját. Android és iOS rendszerű eszközökön a **nem megfelelő alkalmazásokról készült jelentéssel** ellenőrizhető, hogy a listában megadott alkalmazások kompatibilisek-e a felhasználók által telepített alkalmazásokkal (az alkalmazás telepítése azonban ténylegesen nem tiltható le).

> [!TIP]
> Beállíthat feltételeket a felhasználók számára, amelyekkel gondoskodhat arról, hogy tudomásul vegyék, hogy az eszközükön lévő alkalmazásokat (beleértve a személyes alkalmazásokat is) értékelni fogják és a nem megfelelő alkalmazások letiltásra kerülnek, vagy nem megfelelőként lesznek jelentve. A felhasználóknak el kell fogadniuk ezeket a feltételeket ahhoz, hogy beléptethessék eszközüket, és a vállalati portál segítségével beszerezhessék az alkalmazásokat. A használati feltételekkel kapcsolatos további információkért lásd: [Használati feltételek szabályzatbeállításai a Microsoft Intune-ban](terms-and-condition-policy-settings-in-microsoft-intune.md).

Ha a keresett beállítás nem jelenik meg ebben a témakörben, valószínűleg létre tudja hozni egy egyéni iOS-szabályzattal, amellyel az [Apple Configurator eszközzel](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) létrehozott beállításokat importálhatja. További információkért lásd a jelen témakörben alább található „Egyéni szabályzatbeállítások” című részt.

### Biztonsági beállítások
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Jelszó szükséges a mobileszközök feloldásához**|Azt határozza meg, hogy a felhasználóknak kell-e jelszót megadniuk az eszközeikhez való hozzáféréshez.|
|**Kötelező jelszótípus**|A kötelező jelszó típusát határozza meg, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.|
|**Jelszó speciális karaktereinek minimális száma**|Azt határozza meg, hogy hány szimbólumnak (például **#** vagy **@**) kell szerepelnie a jelszóban.|
|**Jelszó minimális hossza**|Meghatározza, hogy legalább hány karakterből álljon a jelszó.|
|**Egyszerű jelszavak engedélyezése**|Egyszerű jelszavak, például **0000** vagy **1234** engedélyezése.|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|Meghatározza, hogy hány sikertelen bejelentkezési kísérlet után kerülnek törlésre az eszköz adatai.|
|**Tétlen percek száma, mielőtt az eszköz újból kéri a jelszót**<sup>1</sup>|Azt határozza meg, hogy az eszköz mennyi időt tölthet üresjáratban, mielőtt a felhasználónak újra meg kellene adnia a jelszavát.|
|**Jelszó lejárata (nap)**|Meghatározza, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát.|
|**Jelszóelőzmények megjegyzése**|Meghatározza, hogy a felhasználó használhatja-e az általa korábban már használt jelszavakat.|
|**Korábbi jelszavak megjegyzése** – **Korábbi jelszavak újbóli használatának tiltása**|Azt határozza meg, hogy az eszköz hány korábban használt jelszót jegyezzen meg.|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**<sup>1</sup>|Ennyi perc elteltével kapcsol ki a kijelző.|
|**Ujjlenyomattal történő zárolásfeloldás engedélyezése**|Az eszközzárolás ujjlenyomattal történő feloldásának engedélyezése.|
<sup>1</sup> Ha a **Képernyő kikapcsolása ennyi perc inaktivitás után** és a **Jelszó kérése ennyi perc inaktivitás után** beállítást is konfigurálja iOS-eszközökön, azok egymás után lesznek alkalmazva. Ha például mindkét beállítást az **5** perc értékre állítja be, a képernyő 5 perc után automatikusan ki fog kapcsolni, és az eszköz további 5 perc után lesz zárolva. Ha azonban a felhasználó manuálisan kapcsolja ki a képernyőt, azonnal a második beállítás lesz alkalmazva. Ugyanebben a példában az eszköz 5 perccel azután lesz zárolva, hogy a felhasználó kikapcsolta a képernyőt.

### Rendszerbeállítások
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Képernyőkép-készítés engedélyezése**|Engedélyezi a felhasználó számára, hogy képként rögzítse a képernyő tartalmát.|
|**Vezérlőközpont engedélyezése a zárolási képernyőn**|Engedélyezi a felhasználó számára a hozzáférést a vezérlőközpont-alkalmazáshoz olyankor is, amikor az eszköz zárolva van.|
|**Értesítési nézet engedélyezése a zárolási képernyőn**|Engedélyezi a felhasználó számára, hogy az eszköz zárolásának feloldása nélkül is hozzáférhessen az értesítések nézetéhez.|
|**Ma nézet engedélyezése a zárolási képernyőn**|Engedélyezi a felhasználó számára az értesítések megtekintését olyankor is, amikor az eszköz zárolva van.|
|**Nem megbízható TLS tanúsítványok engedélyezése**|Engedélyezi nem megbízható TLS-tanúsítványok használatát az eszközön.|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezi vagy letiltja, hogy az eszköz diagnosztikai adatokat küldjön az Apple számára.|
|**Passbook zárolt állapotban való használatának engedélyezése**|Engedélyezi a felhasználó számára a Passbook alkalmazás eszközzárolás alatti elérését.|

### Felhőbeállítások dokumentumok és adatok számára
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**iCloudba történő biztonsági mentés engedélyezése**|Engedélyezi, hogy a felhasználó biztonsági mentést készítsen az iCloudba az eszközről.|
|**Dokumentum iCloudba szinkronizálásának engedélyezése**|Engedélyezi a dokumentumok és kulcsértékek szinkronizálását az iCloud tárhelyére.|
|**Fényképadatfolyamok iCloudba szinkronizálásának engedélyezése**|Engedélyezi az eszközön lévő fényképek szinkronizálását az iCloudba.|
|**Biztonsági másolat titkosításának engedélyezése**|Megköveteli az eszköz minden biztonsági másolatának titkosítását.|
|**Engedélyezi, hogy a felügyelt alkalmazások adatokat szinkronizáljanak az iClouddal**|Engedélyezi, hogy az Intune-nal felügyelt alkalmazások adatokat szinkronizáljanak a felhasználó iCloud-fiókjával.|
|**Tevékenységek más eszközön való folytatásának engedélyezése a Handoff számára**|Lehetővé teszi, hogy a felhasználó folytassa az iOS-eszközön vagy másik Mac OS X rendszerű gépen elkezdett munkát.|
|**Fényképek iCloudban való megosztásának engedélyezése**|Az iOS megosztott fényképadatfolyam funkciója használatának engedélyezése.|
|**iCloud-fotókönyvtár engedélyezése**|A fényképek iCloudban való tárolásának engedélyezése a felhasználó számára. Ha le van tiltva, akkor a már korábban az iCloudban tárolt fényképek is eltávolításra kerülnek.|

### Alkalmazásbeállítások a böngésző számára
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Safari engedélyezése**|Ez a beállítás azt határozza meg, hogy a Safari böngésző használható-e az eszközön.|
|**Automatikus kitöltés engedélyezése**|Engedélyezi a felhasználó számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását.|
|**Előugróablak-blokkoló engedélyezése**|Engedélyezi vagy letiltja a böngésző előugróablak-blokkolóját.|
|**Cookie-k engedélyezése**|Engedélyezi sütik (cookie-k) használatát a böngésző számára.|
|**JavaScript engedélyezése**|Java-parancsfájlok böngészőben történő futtatásának engedélyezése.|
|**Csalás elleni figyelmeztetés engedélyezése**|Csalás elleni figyelmeztetések engedélyezése a böngészőben.|

### Alkalmazásbeállítások az alkalmazások számára
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Alkalmazások telepítésének engedélyezése**|Az alkalmazásáruház elérésének és alkalmazások telepítésének engedélyezése az eszköz számára.|
|**Jelszó megkövetelése az alkalmazástárolóhoz való hozzáféréshez**|A felhasználóktól jelszót kér, mielőtt hozzáférhetnének az alkalmazás-áruházhoz.|
|**Alkalmazáson belüli vásárlás engedélyezése**|A futó alkalmazásokból történő áruházi vásárlások engedélyezése.|
|**Felügyelt dokumentumok engedélyezése egyéb, nem felügyelt alkalmazásokban**|A vállalati dokumentumok bármely alkalmazásban való megtekintésének engedélyezése.<br>**Példa:** Szeretné megakadályozni, hogy a felhasználók fájlokat mentsenek a OneDrive alkalmazásból a Dropbox alkalmazásba. Állítsa be ezt a beállítást „Nem” értékre. Miután az eszköz megkapja a házirendet (például újraindítás után), a továbbiakban nem engedélyezi a mentést.|
|**Nem felügyelt dokumentumok engedélyezése egyéb, felügyelt alkalmazásokban**|Bármely dokumentum felügyelt vállalati alkalmazásokban való megtekintésének engedélyezése.|
|**Videokonferenciák engedélyezése**|Videokonferencia-alkalmazások, például a Facetime engedélyezése az eszközön.|
|**Új vállalati alkalmazások szerzői megbízhatóként való kezelésének engedélyezése**|Nem az alkalmazásáruházból letöltött alkalmazásokban való megbízás lehetőségének engedélyezése a felhasználó számára.|


### Alkalmazásbeállítások a játékok számára
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Game Centerbeli ismerősök felvételének engedélyezése**|Barátok hozzáadásának engedélyezése a Game Center alkalmazásban a felhasználó számára.|
|**Több résztvevős játék engedélyezése**|Engedélyezi a felhasználó számára, hogy többszereplős játékokat játsszon az eszközön.|

### Médiatartalmakra vonatkozó alkalmazásbeállítások
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Minősítési régió**|Válasszon régiót, majd válassza ki azt a maximális korhatár-besorolást, amellyel **filmeket**, **tévéműsorokat** és **alkalmazásokat** tölthetnek le a felhasználók.|
|**Felnőtt tartalom engedélyezése a médiatárban**|Felnőttnek minősített áruházi tartalom elérésének engedélyezése az eszköz számára.|
|**Az iBooks áruházban erotikus tartalomként megjelölt tartalom letöltésének engedélyezése a felhasználó számára**|Az „erotikus tartalom” kategóriába sorolt könyvek letöltésének engedélyezése a felhasználó számára.|


### Eszközképességek beállításai a hardver számára
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Kamera használatának engedélyezése**|Meghatározza, hogy használható-e az eszközön a kamera.|
|**A párosított Apple Watch órák kényszerítése csuklóérzékelés használatára**|Ha ez a beállítás engedélyezve van, az Apple Watch nem jelenít meg értesítéseket, amikor nem viselik.|
|**Párosítási jelszó kérése a kimenő AirPlay-kérésekhez**|Párosítási jelszó kérése, ha a felhasználó az AirPlay segítségével tartalmat kíván közvetíteni egyéb Apple-eszközökre.|

### Eszközképességek beállításai a mobilhálózat számára
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Hangroaming használatának engedélyezése**|Hangroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|
|**Adatroaming használatának engedélyezése**|Adatroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|
|**Roamingolás közbeni globális, háttérbeli adatbeolvasás engedélyezése**|Mobilhálózati roaming közben történő adatlehívás, például e-mail engedélyezése az eszköz számára.|

### Eszközképességek beállításai a mobilhálózat számára
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|-------|
|**Siri engedélyezése**|A Siri beszédfelismerési asszisztens használatának engedélyezése az eszközön.|
|**Siri zárolt eszközön való használatának engedélyezése**|A Siri beszédfelismerési asszisztens eszközzárolás alatti használatának engedélyezése az eszközön.|
|**Hangtárcsázás engedélyezése**|A hangtárcsázási funkció engedélyezése az eszközön.|
|**Az Airdrop szolgáltatás a felügyelt alkalmazásokból való használatának tiltása**|A felügyelt alkalmazásokból az Airdrop szolgáltatással való adatküldés lehetőségének letiltása.|


### A szabályzatnak megfelelő és nem megfelelő alkalmazásokra vonatkozó beállítások
A **Szabályzatnak megfelelő és nem megfelelő alkalmazások** listában adja meg a megfelelő vagy nem megfelelő alkalmazások listáját az alábbi információk alapján.

> [!NOTE]
> Egy szabályzatban csak a megfelelő vagy a nem megfelelő alkalmazások listája szerepelhet. Mindkét típusú lista nem adható meg ugyanabban a házirendben.

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Meg nem felelésről szóló jelentés küldése, ha a felhasználók telepítik a listán szereplő alkalmazások valamelyikét**|Azokat a nem az Intune által kezelt alkalmazásokat listázza, amelyek telepítése és futtatása nem engedélyezett a felhasználók számára.|
|**Meg nem felelésről szóló jelentés küldése, ha a felhasználók a listán nem szereplő alkalmazásokat telepítenek**|Azokat az alkalmazásokat listázza, amelyek telepítése engedélyezett a felhasználók számára. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.|
|**Hozzáadás**|Alkalmazás hozzáadása a kiválasztott listához. Meg kell adnia egy szabadon választott nevet, valamint tetszés szerint megadhatja az alkalmazás kiadóját, valamint az alkalmazás alkalmazás-áruházbeli URL-címét. További segítségért olvassa el az ebben a témakörben alább található „Alkalmazás-áruházak URL-címének megadása” című részt.|
|**Alkalmazások importálása**|Importálja az Ön által vesszővel tagolt fájlban megadott alkalmazásokat. A fájlban ezt a formátumot használja: alkalmazásnév, kiadó, alkalmazás URL-címe.|
|**Szerkesztés**|A kijelölt alkalmazás nevének, kiadójának és URL-címének szerkesztése.|
|**Törlés**|A kijelölt alkalmazás törlése a listából.|

### Teljes képernyős mód beállításai

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Az eszköz Kioszk módjában futtatható kezelt alkalmazás kiválasztása**|Válassza a **Tallózás** elemet, majd adja meg azt a kezelt vagy áruházbeli alkalmazást, amelynek futtatását engedélyezni kívánja, amikor az eszköz kioszkmódban van. Az itt megadotton kívül más alkalmazás nem futtatható az eszközön. További segítségért olvassa el a jelen témakörben alább található „Alkalmazásáruházak URL-címének megadása” című részt.|
|**Érintés engedélyezése**|Engedélyezi vagy letiltja az érintőképernyő használatát az eszközön.|
|**Képernyő elforgatásának engedélyezése**|Engedélyezi vagy letiltja a képernyő tájolásának módosítását az eszköz elforgatásakor.|
|**Hangerőszabályzó gombok engedélyezése**|Engedélyezi vagy letiltja a hangerőszabályzó gombok használatát az eszközön.|
|**Csengetőkapcsoló engedélyezése**|Engedélyezi vagy letiltja a csengető- (némító-) kapcsolót az eszközön.|
|**Képernyő ébresztőgombjának engedélyezése**|Engedélyezi vagy letiltja a képernyő ébresztőgombját az eszközön.|
|**Automatikus zárolás engedélyezése**|Engedélyezi vagy letiltja az eszköz automatikus zárolását.|
|**Monó hang engedélyezése**|Engedélyezi vagy letiltja a **Monó hang** kisegítő beállítást.|
|**Hangalámondás engedélyezése**|Engedélyezi vagy letiltja a **VoiceOver** kisegítő beállítást, amely hangosan felolvassa az eszköz képernyőjén megjelenő szöveget.|
|**A hangalámondás módosításának engedélyezése**|Engedélyezi vagy letiltja a VoiceOver (hangalámondás) funkció beállítását (például hogy milyen gyorsan történjen a képernyőn látható szöveg felolvasása).|
|**Nagyítás engedélyezése**|Engedélyezi vagy letiltja a **Nagyítás** kisegítő beállítást, amellyel a felhasználó érintéssel nagyíthatja az eszköz képernyőjén megjelenő tartalmat.|
|**Nagyítás módosításának engedélyezése**|Engedélyezi vagy letiltja a nagyítási funkció működésének felhasználó általi beállítását.|
|**Színek invertálásának engedélyezése**|Engedélyezi vagy letiltja a **Színek invertálása** kisegítő beállítást, amellyel módosíthatja a képernyőt a látásukban korlátozott felhasználók számára.|
|**Színinvertálás módosításának engedélyezése**|Engedélyezi vagy letiltja a színinvertálási funkció beállításainak módosítását.|
|**Kisegítő érintés engedélyezése**|Engedélyezi vagy letiltja a **Kisegítő érintés** kisegítő beállítást, amely segít a nehézségekkel küszködő felhasználóknak a képernyőn elvégezhető kézmozdulatok végrehajtásában.|
|**Kisegítő érintés módosításának engedélyezése**|Engedélyezi vagy letiltja a Kisegítő érintés funkció beállításának módosítását.|
|**Beszéd kiválasztásának engedélyezése**|Engedélyezi vagy letiltja a **Beszéd kiválasztása** kisegítő beállítást, amellyel felolvastatható a felhasználó által kijelölt szöveg.|
> [!NOTE]
> Az alábbi megjegyzések az iOS-eszközök Kioszk módjának beállításaira vonatkoznak:
>
> -   Az iOS-eszközök Kioszk módra való konfigurálása előtt felügyelt módba kell állítania az eszközt az [Apple Configurator eszközzel](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) vagy az [Apple Device Enrollment Program](ios-device-enrollment-program-in-microsoft-intune) eszközregisztráció-kezelővel. Az Apple Configurator eszközzel kapcsolatos további információkat az Apple dokumentációjában talál.
> -   Ha a megadott iOS-alkalmazás a konfigurációs házirend telepítése után települ, az eszköz mindaddig nem lép kioszkmódba, amíg újra nem indítják.

### A szabályzatnak megfelelő és nem megfelelő alkalmazások referenciaadatai

A **Nem kompatibilis alkalmazások jelentése** beállítás használatával megtekintheti az engedélyezett és letiltott alkalmazások kompatibilitását.

##### A nem kompatibilis alkalmazások jelentésének futtatása

1.  A [Microsoft Intune felügyeleti konzolban](https://manage.microsoft.com) válassza a **Jelentések** &gt; **Jelentés a szabályzatnak nem megfelelő alkalmazásokról** elemet.

2.  Jelölje ki az ellenőrizni kívánt eszközcsoportokat, adja meg, hogy a megfelelő, a nem megfelelő alkalmazásokat vagy mindkettőt szeretné ellenőrizni, majd válassza a **Jelentés megtekintése**elemet.

#### Alkalmazás-áruházak URL-címének megadása
Ha meg szeretné adni egy alkalmazás URL-címét a szabályzatnak megfelelő és nem megfelelő alkalmazások listájában, illetve **Az eszköz kioszkmódjában futtatandó felügyelt alkalmazás kiválasztása** beállításban (csak iOS rendszerben), használja a következő formátumot:

1. Keresőmotor segítségével keresse meg az iTunes alkalmazás-áruházban használni kívánt alkalmazást, és nyissa meg az alkalmazás lapját.

2. Másolja a vágólapra a lap URL-címét, és használja ezt az URL-címet a megfelelő és nem megfelelő alkalmazások listájának, illetve a kioszkmódban futtatni kívánt alkalmazásnak a konfigurálásához.

**Például:** Keressen rá az **iPad Microsoft Word**kifejezésre. Ebben az esetben a következő URL-t használja: **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Az iTunes szoftverrel is megkeresheti az alkalmazást, majd a **Hivatkozás másolása** parancs használatával beszerezheti az alkalmazás URL-címét.

### Regisztrációs beállítások
Az összes beállítás az iOS 8.0-ás és újabb verzióira vonatkozik.

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Az aktiválási zár engedélyezése, ha az eszköz felügyelt módban van**|Aktiválási zár engedélyezése felügyelt iOS-eszközökön.|

### A felügyelt mód beállításai
Az alábbi beállításokat a felügyelt módban lévő, az iOS 8.0-ás vagy újabb verzióját futtató eszközökön konfigurálhatja.

### A felügyelt mód eszközkorlátozásokra vonatkozó beállításai

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Fiók módosításának engedélyezése**|Engedélyezi, hogy a felhasználó megváltoztassa a fiók beállításait, például az e-mail-konfigurációkat.|
|**Alkalmazás mobiladatátvitel-használati beállításai módosításának engedélyezése**|Engedélyezi, hogy a felhasználó szabályozza, melyik alkalmazások bonyolíthatnak le mobilhálózati adatforgalmat.|
|**Az összes tartalom és beállítás törlésére szolgáló funkció használatának engedélyezése az eszközön**|Lehetővé teszi, hogy a felhasználó törölje az összes tartalmat és beállítást az eszközről.|
|**A korlátozások bekapcsolásának engedélyezése a felhasználó számára az eszközbeállítások között**|Lehetővé teszi, hogy a felhasználó eszközkorlátozásokat (szülői felügyeletet) állítson be az eszközön.|
|**Az iOS-alapú eszközzel párosítható eszközök szabályozásának engedélyezése a gazdapárosítási (host pairing) funkció számára**|Annak engedélyezése a gazdapárosítási (host pairing) funkció számára, hogy lehetővé tegye az iOS-alapú eszközzel párosítható eszközök szabályozását a rendszergazda számára.|
|**Konfigurációs profilok és tanúsítványok telepítésének engedélyezése a felhasználó számára**|Engedélyezi, hogy a felhasználó konfigurációs profilokat és tanúsítványokat telepítsen.|
|**Eszköznév módosításának engedélyezése**|Engedélyezi a felhasználó számára, hogy módosítsa az eszköz nevét.|
|**PIN kód módosításának engedélyezése**|Az eszközjelszó hozzáadásának, módosításának vagy eltávolításának engedélyezése.|
|**Apple Watch óra párosításának engedélyezése**|Az eszköz Apple Watch órával való párosításának engedélyezése.|
|**Értesítési beállítások módosításának engedélyezése**|Engedélyezi a felhasználó számára, hogy módosítsa az eszköz értesítési beállításait.|
|**Háttérkép módosításának engedélyezése**|Engedélyezi a felhasználó számára, hogy megváltoztassa az eszköz háttérképét.|

### A felügyelt mód szolgáltatáskorlátozásokra vonatkozó beállításai

|Beállítás neve|Részletek|
|----------------|--------------------|
|**AirDrop engedélyezése**|Az AirDrop funkció használatának engedélyezése a közeli eszközökkel való tartalomcseréhez.|
|**Felhasználók által létrehozott tartalom lekérésének engedélyezése Siri számára az internetről**|Engedélyezi, hogy a Siri kérdések megválaszolása céljából hozzáférjen webhelyekhez.|
|**Siri profanitásszűrőjének használata**|Megakadályozza, hogy a Siri durva kifejezéseket mondjon ki vagy elfogadja ilyenek diktálását.|
|**Internetes eredmények visszaadásának engedélyezése a Spotlight kereső számára**|Lehetővé teszi, hogy a Spotlight kereső csatlakozzon az internethez, hogy további találatokat adjon vissza.|
|**Szómeghatározások keresésének engedélyezése**|Engedélyezi az iOS-funkciót, amellyel kijelölhet egy szót és megkeresheti annak meghatározását.|
|**Prediktív billentyűzetek engedélyezése**|Engedélyezi a prediktív billentyűzetek használatát, amelyek javaslatokat tesznek a felhasználó által leírni kívánt szavakra.|
|**Automatikus javítás engedélyezése**|Engedélyezi, hogy az eszköz automatikusan kijavítsa a hibásan leírt szavakat.|
|**Billentyűzet helyesírás-ellenőrzésének engedélyezése**|Engedélyezi az eszköz helyesírás-ellenőrzőjének használatát.|
|**Billentyűparancsok engedélyezése**|Engedélyezi a billentyűparancsok használatát.|

### A felügyelt mód alkalmazáskorlátozásokra vonatkozó beállításai

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Vállalati alkalmazások megbízhatósági beállításai módosításának engedélyezése**|Lehetővé teszi a felhasználók számára a vállalati alkalmazások megbízhatósági beállításainak módosítását.|
|**Alkalmazások telepítésének engedélyezése csak az Apple Configurator és az iTunes használatával**|Az App Store áruház az eszköz kezdőképernyőjén engedélyezhető vagy tiltható le. A felhasználók továbbra is használhatják az iTunest vagy az Apple Configurator eszközt alkalmazások telepítésére vagy frissítésére.|
|**Alkalmazások automatikus letöltésének engedélyezése**|Más eszközökkel vásárolt alkalmazások automatikus letöltésének engedélyezése erre az eszközre. Ez a beállítás nem befolyásolja az alkalmazások frissítéseit.|
|**A Barátok alkalmazás beállításai módosításának engedélyezése**|Lehetővé teszi, hogy a felhasználó megváltoztassa a Barátok alkalmazás beállításait.|
|**Az iBooks áruház elérésének engedélyezése**|Lehetővé teszi, hogy a felhasználó könyveket böngésszen és vásároljon az iBook áruházban.|
|**Az Üzenetek alkalmazás használatának engedélyezése az eszközön**|Engedélyezi az Üzenetek alkalmazást a szöveges üzenetek küldéséhez.|
|**Podcastok használatának engedélyezése**|A Podcastok alkalmazás használatának engedélyezése.|
|**Music szolgáltatás használatának engedélyezése**|Az Apple Music alkalmazás használatának engedélyezése.|
|**iTunes Radio szolgáltatás engedélyezése**|Az iTunes Radio alkalmazás használatának engedélyezése.|
|**Apple News engedélyezése**|Az Apple News alkalmazás használatának engedélyezése.|
|**Game Center engedélyezése**|A Game Center alkalmazás használatának engedélyezése.|


### Alkalmazások megjelenítése vagy elrejtése

A **Rejtett és megjelenített alkalmazások listája** segítségével az alábbiakat szabályozhatja az iOS 9.3-as vagy újabb verzióját futtató felügyelt eszközökön:

- Megadhatja a felhasználók elől elrejtett alkalmazások listáját. Az ilyen alkalmazásokat a felhasználók nem látják és nem tudják elindítani.
- Megadhatja a felhasználók által látható és elindítható alkalmazások listáját. Ezeken kívül a felhasználók más alkalmazásokat nem látnak és nem indíthatnak el.


#### Rejtett és megjelenített alkalmazások listájának létrehozása

Adja meg a következő beállításokat:

|Beállítás neve|Részletek|
|-|-|
|**Rejtett és megjelenített alkalmazások listája**|Engedélyezze ezt a beállítást rejtett és megjelenített alkalmazások listájának létrehozásához.|
|**A listán szereplő alkalmazások elrejtése a felhasználó elől**|Ha ezt a beállítást választja, létrehozhatja azoknak az alkalmazásoknak a listáját, amelyek rejtve lesznek a felhasználók elől.|
|**Csak a listán szereplő alkalmazások megjelenítése a felhasználónak**|Ha ezt a beállítást választja, létrehozhatja azoknak az alkalmazásoknak a listáját, amelyek megjelennek a felhasználók számára.<br>Ha ezt a típusú listát választja, az iOS **Beállítások** és **Telefon** (iPhone esetén) alkalmazásokon kívül minden más alkalmazás rejtve lesz.<br>Ezen kívül a listához kell adnia a Vállalati portál alkalmazást és minden más, az Intune-nal telepített és felügyelt alkalmazást.|
|**Hozzáadás**|Hozzáadhat egy alkalmazást a kijelölt listához.<br>Az elrejtett alkalmazások listájában minden elrejteni kívánt alkalmazás esetén meg kell adnia a következőket: **Név**, **Kiadó** és az **Alkalmazás URL-címe vagy csomagazonosítója**.<br>A megjelenített alkalmazások listájában használhatja a **Felügyelt alkalmazás kiválasztása** lehetőséget, így az Intune által felügyelt alkalmazások listájából választhatja ki a megjeleníteni kívánt alkalmazásokat. Használhatja az Áruházbeli alkalmazás kiválasztása lehetőséget is, mely esetben minden megjeleníteni kívánt alkalmazás esetén meg kell adnia a következőket: **Név**, **Kiadó** és az **Alkalmazás URL-címe vagy csomagazonosítója**.|
|**Alkalmazások importálása**|Importálhatja azokat az alkalmazásokat, amelyeket egy vesszővel tagolt fájlban megadott. Használja a fájlban megadott formátumot, alkalmazásnevet, kiadót és URL-címet.|
|**Szerkesztés**|Segítségével szerkesztheti a kijelölt alkalmazás nevét, kiadóját és URL-címét.|
|**Törlés**|Törölheti a kijelölt alkalmazást a listából.|

#### Beépített iOS-alkalmazások adatai

Ebben a listában megtalálhatja a megjeleníteni vagy elrejteni kívánt beépített iOS-alkalmazás nevét, kiadóját és csomagazonosítóját. Ha a listán szereplő összes alkalmazást szeretné megjeleníteni vagy elrejteni, az alábbi adatokat másolja be egy **.csv** kiterjesztésű szövegfájlba, majd használja az **Alkalmazások importálása** lehetőséget az alkalmazások egyidejű importálásához.

```
App Store,Apple,com.apple.AppStore
Calculator,Apple,com.apple.calculator
Calendar,Apple,com.apple.mobilecal
Camera,Apple,com.apple.camera
Clock,Apple,com.apple.mobiletimer
Compass,Apple,com.apple.compass
Contacts,Apple,com.apple.MobileAddressBook
FaceTime,Apple,com.apple.facetime
Find Friends,Apple,com.apple.mobileme.fmf1
Find iPhone,Apple,com.apple.mobileme.fmip1
Game Center,Apple,com.apple.gamecenter
GarageBand,Apple,com.apple.mobilegarageband
Health,Apple,com.apple.Health
iBooks,Apple,com.apple.iBooks
iTunes Store,Apple,com.apple.MobileStore
iTunes U,Apple,com.apple.itunesu
Keynote,Apple,com.apple.Keynote
Mail,Apple,com.apple.mobilemail
Maps,Apple,com.apple.Maps
Messages,Apple,com.apple.MobileSMS
Music,Apple,com.apple.Music
News,Apple,com.apple.news
Notes,Apple,com.apple.mobilenotes
Numbers,Apple,com.apple.Numbers
Pages,Apple,com.apple.Pages
Photo Booth,Apple,com.apple.Photo-Booth
Photos,Apple,com.apple.mobileslideshow
Podcasts,Apple,com.apple.podcasts
Reminders,Apple,com.apple.reminders
Safari,Apple,com.apple.mobilesafari
Settings,Apple,com.apple.Preferences
Stocks,Apple,com.apple.stocks
Tips,Apple,com.apple.tips
Videos,Apple,com.apple.videos
VoiceMemos,Apple,com.apple.VoiceMemos
Wallet,Apple,com.apple.Passbook
Watch,Apple,com.apple.Bridge
Weather,Apple,com.apple.weather


```




## Egyéni szabályzatbeállítások

A Microsoft Intune **Egyéni iOS-szabályzat** használatával az [Apple Configurator eszközzel](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) létrehozott beállítások iOS-alapú eszközökre telepíthetők. Ezzel az eszközzel számos olyan beállítást készíthet, amelyek ezen eszközök működését vezérlik, és egy konfigurációs profilba exportálhatja őket. Ezt a konfigurációs profilt később Intune iOS-szabályzatokba importálhatók, és a beállítások telepíthetők a szervezetben lévő felhasználók és eszközök számára.

Ezzel a funkcióval olyan iOS-beállításokat léptethet érvénybe, amelyek nem konfigurálhatók az Intune általános konfigurációs szabályzataival.

### Előfeltételek
Mielőtt elkezdené, telepítenie kell az Apple Configurator eszközt, és létre kell hoznia a felhasználók vagy eszközök számára telepíteni kívánt beállításokat tartalmazó konfigurációs fájlt. Az Apple Configurator eszköz a [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) áruházból tölthető le, ahol további információkat is talál az eszközről.

> [!NOTE]
> Az Intune nem készít jelentést az egyéni iOS-házirendek egyes beállításainak betartásáról. a teljes házirend betartásáról azonban igen.

### Általános beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    |**Név**|Adjon meg egy egyedi nevet az egyéni iOS-házirend számára, hogy az azonosítható legyen az Intune konzolján.|
    |**Leírás**|Adjon meg egy leírást, amely áttekintést nyújt az iOS egyéni szabályzatáról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.|

### Egyéni beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
|**Egyéni konfigurációs profil neve (megjelenik a felhasználók számára)**|Nevezze el a szabályzatot. Ez a név jelenik majd meg az eszközön és az Intune szabályzatjelentéseiben.|
|**Konfigurációs profilfájl**|Válassza az **Importálás** elemet, majd keresse meg az Apple Configurator eszközzel létrehozott konfigurációs profilt. **Megjegyzés:** Ellenőrizze, hogy az Apple Configurator eszközből exportált beállítások kompatibilisek-e azon eszközök iOS-verziójával, amelyekre az egyéni iOS-házirendet telepíti. A nem kompatibilis beállításokból fakadó problémák megoldásával kapcsolatos információkat az [Apple Developer](https://developer.apple.com/) webhelyről letölthető **Configuration Profile Reference** és **Mobile Device Management Protocol Reference** című (angol nyelvű) útmutatókban talál.|
    |**Konfigurációs profil részletei**|Megjeleníti az importált konfigurációs profil XML-kódját.|

### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Sep16_HO2-->


