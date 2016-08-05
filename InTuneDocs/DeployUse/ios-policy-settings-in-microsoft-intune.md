---
title: "Az iOS szabályzatbeállításai | Microsoft Intune"
description: "Szabályzatok létrehozása Intune-ban felügyelt iOS-eszközök beállításainak és funkcióinak felügyeletére."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 947328a5c28839d8227a9e5ae0dd8b1fc5ad8e81
ms.openlocfilehash: 63bc2cedf8d81b050a384a947a0b43827de5c352


---

# iOS-szabályzatbeállítások a Microsoft Intune-ban

Az Intune számos olyan beépített általános beállítást tartalmaz, amelyekkel konfigurálhatja iOS-eszközeit. Ezen kívül használhatja az Apple Configurator eszközt is olyan egyéni beállítások létrehozására, amelyek nem érhetők el az Intune-ban.

## Az általános konfigurációs szabályzat beállításai

A Microsoft Intune **iOS-hoz készült általános konfigurációs szabályzatát** a következő beállítások konfigurálásához használhatja:

-   **Általános eszköz- és biztonsági beállítások** – előre meghatározott beállítások egy listájából választva számos szolgáltatást és funkciót szabályozhat az eszközön.

-   **Teljes képernyős mód** – zárolhatja az eszközöket, hogy csak bizonyos szolgáltatások működjenek rajtuk. Megadhatja például, hogy az eszköz csak egy meghatározott felügyelt alkalmazás futtatását engedélyezze, vagy letilthatja a hangerő-szabályozó gombok használatát az eszközön. Ezek a beállítások egy eszköz demonstrációs modelljéhez, illetve egy olyan eszközhöz használhatók, amely csak egyetlen funkció végrehajtására van kijelölve (például egy pénztári eszköz).

-   **Megfelelő és nem megfelelő alkalmazások** – egy listában megadhatja a vállalatban megfelelőnek vagy nem megfelelőnek ítélt alkalmazásokat. Android és iOS rendszerű eszközökön a **Nem kompatibilis alkalmazások jelentése** beállítással ellenőrizhető, hogy a listában megadott alkalmazás kompatibilis-e a felhasználók által telepített alkalmazásokkal (az alkalmazás telepítése azonban ténylegesen nem tiltható le).

> [!TIP]
> Beállíthat feltételeket a felhasználók számára, amelyekkel gondoskodhat arról, hogy tudomásul vegyék, hogy az eszközükön lévő alkalmazásokat – beleértve a személyes alkalmazásokat – értékelni fogják, a nem kompatibilis alkalmazások pedig le lesznek tiltva, vagy nem kompatibilisként lesznek jelentve. A felhasználóknak el kell fogadniuk ezeket a feltételeket ahhoz, hogy beléptethessék eszközüket, és a vállalati portál segítségével beszerezhessék az alkalmazásokat. A használati feltételekkel kapcsolatos további információkért lásd: [Használati feltételek szabályzatbeállításai a Microsoft Intune-ban](terms-and-condition-policy-settings-in-microsoft-intune.md).

Ha a keresett beállítás nem jelenik meg ebben a témakörben, valószínűleg létre tudja hozni egy egyéni iOS-szabályzattal, mellyel az [Apple Configurator eszközzel](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) létrehozott beállításokat importálhatja. További információkért olvassa el a jelen témakörben alább található **Egyéni szabályzatbeállítások** című részt.

### Biztonsági beállítások
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Jelszó szükséges a mobileszközök feloldásához**|Ez a beállítás azt határozza meg, hogy a felhasználóknak kell-e jelszót megadniuk az eszközükhöz való hozzáféréshez.|
|**Kötelező jelszótípus**|A megkövetelt jelszótípust határozza meg, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.|
|**Jelszó speciális karaktereinek minimális száma**|Azt határozza meg, hogy hány szimbólumnak (például **#** vagy **@**) kell szerepelnie a jelszóban.|
|**Jelszó minimális hossza**|A jelszóban használandó karakterek minimális számát határozza meg.|
|**Egyszerű jelszavak engedélyezése**|Egyszerű jelszavak, például „0000” vagy „1234” engedélyezése.|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|A megadott számú sikertelen bejelentkezési kísérlet után törli az eszközt.|
|**Tétlen percek száma, mielőtt az eszköz újból kéri a jelszót**<sup>1</sup>|Ez a beállítás azt határozza meg, hogy az eszköz mennyi időt tölthet üresjáratban, mielőtt a felhasználónak újra be kell írnia a jelszavát.|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.|
|**Jelszóelőzmények megjegyzése**|Ez a beállítás azt határozza meg, hogy a felhasználó használhatja-e az általa korábban használt jelszavakat.|
|**Korábbi jelszavak megjegyzése** – **Korábbi jelszavak újbóli használatának tiltása**|Ez a beállítás az eszköz által megjegyzett korábbi jelszavak számát határozza meg.|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**<sup>1</sup>|Ennyi perc elteltével kapcsol ki a kijelző.|
|**Ujjlenyomattal történő zárolásfeloldás engedélyezése**|Az eszközzárolás ujjlenyomattal történő feloldásának engedélyezése.|
<sup>1</sup> Ha a **Képernyő kikapcsolása ennyi perc inaktivitás után** és a **Jelszó kérése ennyi perc inaktivitás után** beállítást is konfigurálja iOS-eszközökön, azok egymás után lesznek alkalmazva. Ha például mindkét beállítást az **5** perc értékre állítja be, a képernyő 5 perc után automatikusan ki fog kapcsolni, és az eszköz további 5 perc után lesz zárolva. Ha azonban a felhasználó manuálisan kapcsolja ki a képernyőt, azonnal a második beállítás lesz alkalmazva. Ugyanebben a példában az eszköz 5 perccel azután lesz zárolva, hogy a felhasználó kikapcsolta a képernyőt.

### Rendszerbeállítások
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Képernyőkép-készítés engedélyezése**|Engedélyezi a felhasználó számára, hogy képként rögzítse a képernyő tartalmát.|
|**Vezérlőközpont engedélyezése a zárolási képernyőn**|Itt adható meg, hogy a Vezérlőközpont alkalmazás elérhető legyen-e, amikor az eszköz zárolva van.|
|**Értesítési nézet engedélyezése a zárolási képernyőn**|Engedélyezi a felhasználó számára, hogy az eszköz zárolásának feloldása nélkül is hozzáférhessen az értesítések nézetéhez.|
|**Ma nézet engedélyezése a zárolási képernyőn**|Itt adható meg, hogy megtekinthetők-e az értesítések, amikor az eszköz zárolva van.|
|**Nem megbízható TLS tanúsítványok engedélyezése**|Engedélyezi nem megbízható TLS-tanúsítványok használatát az eszközön.|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezi vagy letiltja, hogy az eszköz diagnosztikai adatokat küldjön az Apple számára.|
|**Passbook zárolt állapotban való használatának engedélyezése**|Engedélyezi a felhasználó számára a Passbook alkalmazás eszközzárolás alatti elérését.|

### Felhőbeállítások – dokumentumok és adatok
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**iCloudba történő biztonsági mentés engedélyezése**|Engedélyezi a felhasználó számára, hogy biztonsági mentést készítsen az iCloudba az eszközről.|
|**Dokumentum iCloudba szinkronizálásának engedélyezése**|Engedélyezi a dokumentumok és kulcsértékek szinkronizálását az iCloud tárhelyére.|
|**Fényképadatfolyamok iCloudba szinkronizálásának engedélyezése**|Engedélyezi az eszközön lévő fényképek szinkronizálását az iCloudba.|
|**Biztonsági másolat titkosításának engedélyezése**|Megköveteli az eszköz minden biztonsági másolatának titkosítását.|
|**Engedélyezi, hogy a felügyelt alkalmazások adatokat szinkronizáljanak az iClouddal**|Engedélyezi, hogy az alkalmazások adatokat szinkronizáljanak a felhasználók iCloud-fiókjával.|
|**Tevékenységek más eszközön való folytatásának engedélyezése a Handoff számára**|A Handoff segítségével folytathatja az iOS-eszközön vagy másik Mac OS X rendszerű gépen elkezdett munkát.|

### Alkalmazásbeállítások – böngésző
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Safari engedélyezése**|Ez a beállítás azt határozza meg, hogy a Safari böngésző használható-e az eszközön.|
|**Automatikus kitöltés engedélyezése**|A felhasználók módosíthatják a böngésző automatikus kiegészítési funkciójának beállításait.|
|**Előugróablak-blokkoló engedélyezése**|Engedélyezi vagy letiltja a böngésző előugróablak-blokkolóját.|
|**Cookie-k engedélyezése**|Engedélyezi Cookie-k használatát az eszköz webböngészője számára.|
|**JavaScript engedélyezése**|Java-parancsfájlok böngészőben történő futtatásának engedélyezése.|
|**Csalás elleni figyelmeztetés engedélyezése**|Csalás elleni figyelmeztetés engedélyezése az eszköz böngészőjében.|

### Alkalmazásbeállítások – alkalmazások
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Alkalmazástároló használatának engedélyezése**|Az alkalmazás-áruház elérésének engedélyezése az eszköz számára.|
|**Jelszó megkövetelése az alkalmazástárolóhoz való hozzáféréshez**|A felhasználókat jelszó beírására kötelezi az alkalmazás-áruházhoz való hozzáféréshez.|
|**Alkalmazáson belüli vásárlás engedélyezése**|A futó alkalmazásokból történő áruházi vásárlások engedélyezése.|
|**Felügyelt dokumentumok engedélyezése egyéb, nem felügyelt alkalmazásokban**|A vállalati dokumentumok bármely alkalmazásban való megtekintésének engedélyezése.<br>**Példa:** Szeretné megakadályozni, hogy a felhasználók fájlokat mentsenek a OneDrive alkalmazásból a Dropbox alkalmazásba. Állítsa be ezt a beállítást „Nem” értékre. Miután az eszköz megkapja a házirendet (például újraindítás után), nem engedélyezi többé a mentést.|
|**Nem felügyelt dokumentumok engedélyezése egyéb, felügyelt alkalmazásokban**|Bármely dokumentum felügyelt vállalati alkalmazásokban való megtekintésének engedélyezése.|
|**Videokonferenciák engedélyezése**|Videokonferencia-alkalmazások, például a Facetime engedélyezése az eszközön.|
|**Felnőtt tartalom engedélyezése a médiatárban**|Felnőttnek minősített áruházi tartalom elérésének engedélyezése az eszköz számára.|
|**Az iBooks áruházban erotikus tartalomként megjelölt tartalom letöltésének engedélyezése a felhasználó számára**|Az erotikusként kategorizált könyvek letöltésének engedélyezése a felhasználó számára.|

### Alkalmazásbeállítások – játékok
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Game Centerbeli ismerősök felvételének engedélyezése**|Barátok hozzáadásának engedélyezése a Game Center alkalmazásban a felhasználó számára.|
|**Több résztvevős játék engedélyezése**|Engedélyezi a felhasználó számára, hogy többszereplős játékokat játsszon az eszközön.|

### Eszközképességek beállításai – hardver
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Kamera használatának engedélyezése**|A beállítás meghatározza, hogy használható-e az eszközön a kamera.|
|**Párosítási jelszó kérése a kimenő AirPlay-kérésekhez**|Az Airplay segítségével tartalmat streamelhet másik Apple-eszközre. Ezzel a beállítással párosítási jelszót kérhet más eszközökhöz való csatlakozáskor.|

### Eszközképességek beállításai – mobilhálózat
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Hangroaming használatának engedélyezése**|Hangroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|
|**Adatroaming használatának engedélyezése**|Adatroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|
|**Roamingolás közbeni globális, háttérbeli adatbeolvasás engedélyezése**|Mobilhálózati roaming közben történő adatlehívás, például e-mail engedélyezése az eszköz számára.|

### Eszközképességek beállításai – szolgáltatások
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|-------|
|**Siri engedélyezése**|A Siri beszédfelismerési asszisztens használatának engedélyezése az eszközön.|
|**Siri zárolt eszközön való használatának engedélyezése**|A Siri beszédfelismerési asszisztens eszközzárolás alatti használatának engedélyezése az eszközön.|
|**Hangtárcsázás engedélyezése**|A hangtárcsázási funkció engedélyezése az eszközön.|


### A szabályzatnak megfelelő és nem megfelelő alkalmazásokra vonatkozó beállítások
A **Szabályzatnak megfelelő és nem megfelelő alkalmazások** listában adja meg a kompatibilis vagy nem kompatibilis eszközök listáját az alábbi információk alapján:

> [!NOTE]
> Egy házirendben csak egy, kompatibilis vagy nem kompatibilis alkalmazásokat tartalmazó lista szerepelhet. Mindkét típusú lista nem adható meg ugyanabban a házirendben.

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Meg nem felelésről szóló jelentés küldése, ha a felhasználók telepítik a listán szereplő alkalmazások valamelyikét**|Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyek telepítése és futtatása nem engedélyezett a felhasználóknak.|
|**Meg nem felelésről szóló jelentés küldése, ha a felhasználók a listán nem szereplő alkalmazásokat telepítenek**|Azokat az alkalmazásokat tartalmazza, amelyeket a felhasználók telepíthetnek. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.|
|**Hozzáadás**|Hozzáadhat egy alkalmazást a kijelölt listához. Meg kell adnia egy szabadon választott nevet, valamint tetszés szerint megadhatja az alkalmazás kiadóját, valamint az alkalmazás alkalmazás-áruházbeli URL-címét. További segítségért olvassa el az ebben a témakörben alább található **Alkalmazás-áruházak URL-címének megadása** című részt.|
|**Alkalmazások importálása**|Importálhatja azokat az alkalmazásokat, amelyeket egy vesszővel tagolt fájlban megadott. Használja a fájlban megadott formátumot, alkalmazásnevet, kiadót és URL-címet.|
|**Szerkesztés**|Segítségével szerkesztheti a kijelölt alkalmazás nevét, kiadóját és URL-címét.|
|**Törlés**|Törölheti a kijelölt alkalmazást a listából.|

### Teljes képernyős mód beállításai

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Az eszköz Kioszk módjában futtatható kezelt alkalmazás kiválasztása**|Válassza a **Tallózás** elemet, majd adja meg azt a kezelt alkalmazást, illetve áruházbeli alkalmazást, amelynek engedélyezni szeretné a futtatását, amikor az eszköz kioszkmódban van. Más alkalmazás nem lesz futtatható az eszközön. További segítségért olvassa el az ebben a témakörben alább található **Alkalmazás-áruházak URL-címének megadása** című részt.|
|**Érintés engedélyezése**|Engedélyezheti vagy letilthatja az érintőképernyőt az eszközön.|
|**Képernyő elforgatásának engedélyezése**|Engedélyezheti vagy letilthatja a képernyő tájolásának módosítását az eszköz elforgatásakor.|
|**Hangerőszabályzó gombok engedélyezése**|Engedélyezheti vagy letilthatja a hangerőszabályzó gombok használatát az eszközön.|
|**Csengetőkapcsoló engedélyezése**|Engedélyezheti vagy letilthatja a csengető- (némító-) kapcsolót az eszközön.|
|**Képernyő ébresztőgombjának engedélyezése**|Engedélyezheti vagy letilthatja a képernyő ébresztőgombját az eszközön.|
|**Automatikus zárolás engedélyezése**|Engedélyezheti vagy letilthatja az eszköz automatikus zárolását.|
|**Monó hang engedélyezése**|Engedélyezheti vagy letilthatja a **Monó hang**kisegítő beállítást.|
|**Hangalámondás engedélyezése**|Engedélyezheti vagy letilthatja a **VoiceOver** kisegítő beállítást, amely hangosan felolvassa az eszköz képernyőjén megjelenő szöveget.|
|**A hangalámondás módosításának engedélyezése**|Engedélyezheti vagy letilthatja a VoiceOver funkció módosítását (például hogy milyen gyorsan történjen a képernyőn látható szöveg felolvasása).|
|**Nagyítás engedélyezése**|Engedélyezheti vagy letilthatja a **Nagyítás** kisegítő beállítást, amellyel érintéssel nagyíthatja az eszköz képernyőjén megjelenő tartalmat.|
|**Nagyítás módosításának engedélyezése**|Engedélyezheti vagy letilthatja a nagyítási funkció módosítását.|
|**Színek invertálásának engedélyezése**|Engedélyezheti vagy letilthatja a **Színek invertálása** kisegítő beállítást, amellyel módosíthatja a képernyőt a látásukban korlátozott felhasználók számára.|
|**Színinvertálás módosításának engedélyezése**|Engedélyezheti vagy letilthatja a színinvertálási funkció módosítását.|
|**Kisegítő érintés engedélyezése**|Engedélyezheti vagy letilthatja a **Kisegítő érintés** kisegítő beállítást, amely segít a nehézségekkel küszködő felhasználóknak a képernyőn elvégezhető kézmozdulatok végrehajtásában.|
|**Kisegítő érintés módosításának engedélyezése**|Engedélyezheti vagy letilthatja a Kisegítő érintés funkció módosítását.|
|**Beszéd kiválasztásának engedélyezése**|Engedélyezheti vagy letilthatja a **Beszéd kiválasztása** kisegítő beállítást, amellyel felolvastatható az Ön által kijelölt szöveg.|
> [!NOTE]
> Az alábbi megjegyzések az iOS-eszközök Kioszk módjának beállításaira vonatkoznak:
> 
> -   Az iOS-eszközök a teljes képernyős módra való konfigurálása előtt felügyelt módra kell állítania az eszközt az [Apple Configurator eszközzel](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) vagy az eszközregisztráció-kezelővel. Az Apple Configurator eszközzel kapcsolatos további információkat az Apple dokumentációjában talál.
> -   Ha a megadott iOS-alkalmazás a konfigurációs házirend alkalmazása után települ, az eszköz mindaddig nem lép Kioszk módba, amíg újra nem indítják.

### A szabályzatnak megfelelő és nem megfelelő alkalmazások referenciaadatai

#### A szabályzatnak megfelelő és nem megfelelő alkalmazások figyelése
A **Nem kompatibilis alkalmazások jelentése** beállítás használatával megtekintheti az engedélyezett és letiltott alkalmazások kompatibilitását.

##### A nem kompatibilis alkalmazások jelentésének futtatása

1.  A [Microsoft Intune felügyeleti konzolban](https://manage.microsoft.com) válassza a **Jelentések** &gt; **Jelentés a szabályzatnak nem megfelelő alkalmazásokról** elemet.

2.  Jelölje ki az ellenőrizni kívánt eszközcsoportokat, adja meg, hogy a kompatibilis vagy a nem kompatibilis alkalmazásokat szeretné-e ellenőrizni, illetve mindkettőt, majd válassza a **Jelentés megtekintése**elemet.

#### Alkalmazás-áruházak URL-címének megadása
Ha meg szeretné adni egy alkalmazás URL-címét a szabályzatnak megfelelő és nem megfelelő alkalmazások listájában, illetve **Az eszköz kioszkmódjában futtatandó felügyelt alkalmazás kiválasztása** beállításban (csak iOS rendszerben), használja a következő formátumot:

Egy keresőmotor segítségével keresse meg az iTunes alkalmazás-áruházban használni kívánt alkalmazást, és nyissa meg az alkalmazás lapját.

Másolja a vágólapra a lap URL-címét, és használja ezt az URL-címet a kompatibilis és nem kompatibilis alkalmazások listájának, illetve a Kioszk módban futtatni kívánt alkalmazásnak a konfigurálásához.

**Például:** Keressen rá az **iPad Microsoft Word**kifejezésre. Ebben az esetben a következő URL-t használja: **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Az iTunes szoftverrel is megkeresheti az alkalmazást, majd a **Hivatkozás másolása** parancs használatával beszerezheti az alkalmazás URL-címét.

### Regisztrációs beállítások
Az összes beállítás az iOS 7.1-es és újabb verzióira érvényes.

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Az aktiválási zár engedélyezése, ha az eszköz felügyelt módban van**|Aktiválási zár engedélyezése felügyelt iOS-eszközökön.|

### Felügyelet
Az alábbi beállításokat a felügyelt módban lévő, az iOS 7.1-es vagy újabb verzióját futtató eszközökön konfigurálhatja.

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Fiók módosításának engedélyezése**|Engedélyezi, hogy a felhasználó megváltoztassa a fiók beállításait, például az e-mail-konfigurációkat.|
|**AirDrop engedélyezése**|Az AirDrop funkció használatának engedélyezése a közeli eszközökkel való tartalomcseréhez.|
|**Alkalmazás mobiladatátvitel-használati beállításai módosításának engedélyezése**|Engedélyezi, hogy a felhasználó szabályozza, melyik alkalmazások bonyolíthatnak le mobilhálózati adatforgalmat.|
|**Felhasználók által létrehozott tartalom lekérésének engedélyezése Siri számára az internetről**|Engedélyezi, hogy a Siri kérdések megválaszolása céljából hozzáférjen webhelyekhez.|
|**Az iBooks áruház elérésének engedélyezése**|Lehetővé teszi, hogy a felhasználó könyveket böngésszen és vásároljon az iBook áruházban.|
|**A Barátok alkalmazás beállításai módosításának engedélyezése**|Lehetővé teszi, hogy a felhasználó megváltoztassa a Barátok alkalmazás beállításait.|
|**Az összes tartalom és beállítás törlésére szolgáló funkció használatának engedélyezése az eszközön**|Lehetővé teszi, hogy a felhasználó törölje az összes tartalmat és beállítást az eszközről.|
|**A korlátozások bekapcsolásának engedélyezése a felhasználó számára az eszközbeállítások között**|Lehetővé teszi, hogy a felhasználó eszközkorlátozásokat (szülői felügyeletet) konfiguráljon az eszközön|
|**Internetes eredmények visszaadásának engedélyezése a Spotlight kereső számára**|Lehetővé teszi, hogy a Spotlight kereső csatlakozzon az internethez, hogy további találatokat adjon vissza.|
|**A Game Center alkalmazás használatának engedélyezése**|A Game Center alkalmazás használatának engedélyezése.|
|**Az iOS-alapú eszközzel párosítható eszközök szabályozásának engedélyezése a gazdapárosítási (host pairing) funkció számára**|A gazdapárosítási funkcióval a rendszergazda szabályozhatja, hogy az iOS 7-alapú eszköz milyen eszközökkel legyen párosítható.|
|**Konfigurációs profilok és tanúsítványok telepítésének engedélyezése a felhasználó számára**|Engedélyezi, hogy a felhasználó konfigurációs profilokat és tanúsítványokat telepítsen.|
|**Az Üzenetek alkalmazás használatának engedélyezése az eszközön**|Engedélyezi az Üzenetek alkalmazást a szöveges üzenetek küldéséhez.|


## Egyéni szabályzatbeállítások

A Microsoft Intune **egyéni iOS-szabályzat** használatával az [Apple Configurator eszközzel](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) létrehozott beállítások iOS-alapú eszközökre telepíthetők. Ezzel az eszközzel számos olyan beállítást készíthet, amelyek ezen eszközök működését vezérlik, és egy konfigurációs profilba exportálhatja őket. Ezt a konfigurációs profilt később Intune iOS-szabályzatokba importálhatók, és a beállítások telepíthetők a szervezetben lévő felhasználók és eszközök számára.

Ezzel a funkcióval olyan iOS-beállításokat léptethet érvénybe, amelyek nem konfigurálhatók az Intune általános konfigurációs szabályzatával.

### Előfeltételek
Mielőtt elkezdené, telepítenie kell az Apple Configurator eszközt, és létre kell hoznia a felhasználók vagy eszközök számára telepíteni kívánt beállításokat tartalmazó konfigurációs fájlt. Az Apple Configurator eszköz letöltése és az azzal kapcsolatos információk a [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)áruházban érhetők el

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
|**Konfigurációs profilfájl**|Válassza az **Importálás** elemet, majd keresse meg az Apple Configurator eszközzel létrehozott konfigurációs profilt. **Megjegyzés:** Ellenőrizze, hogy az Apple Configurator eszközből exportált beállítások kompatibilisek-e azon eszközök iOS-verziójával, amelyekre az egyéni iOS-házirendet telepíti. A nem kompatibilis beállításokból fakadó problémák megoldásával kapcsolatos információkat az [Apple Developer](https://developer.apple.com/) webhelyről letölthető **Configuration Profile Reference** és **Mobile Device Management Protocol Reference** című (angol nyelvű) útmutatóban talál.|
    |**Konfigurációs profil részletei**|Megjeleníti az importált konfigurációs profil xml-kódját.|

### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO4-->


