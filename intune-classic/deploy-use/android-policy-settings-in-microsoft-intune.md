---
title: "Android- és Samsung KNOX-szabályzatbeállítások"
description: "Szabályzatok létrehozása, amelyek vezérlik a beállításokat és a szolgáltatásokat az Intune-nal felügyelt Android-eszközökön."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 502ee0f3107d197537f7f9ab3b2888246bbca1d3
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="android-and-samsung-knox-standard-policy-settings-in-microsoft-intune"></a>Android- és Samsung KNOX Standard-eszközök konfigurációs szabályzatának beállításai a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Intune egy sor Android-eszközökön konfigurálható általános beállítást biztosít. Ezek mellett megadhat Open Mobile Alliance Uniform Resource Identifier (OMA-URI) értékeket is olyan egyéni beállítások létrehozásához, amelyek nem érhetők el az Intune-ban.

## <a name="general-configuration-policy"></a>Általános konfigurációs szabályzat

Az Intune **Androidhoz készült általános konfigurációs szabályzatát** a következő beállításához használhatja:

-   **Mobileszköz-biztonsági beállítások** – előre meghatározott beállítások listájából választva számos szolgáltatást és funkciót szabályozhat az eszközön.

-   **Teljes képernyős mód** (csak Samsung KNOX-eszközök esetén) – zárolhatja az eszközt, hogy csak bizonyos szolgáltatások működjenek rajta. Megadhatja például, hogy az eszköz csak egy meghatározott felügyelt alkalmazás futtatását engedélyezze, vagy letilthatja a hangerő-szabályozó gombok használatát. Ezek a beállítások használhatók például egy eszköz bemutató modelljéhez vagy egy olyan eszközhöz, amely csak egyetlen funkció végrehajtására van kijelölve (például egy pénztári eszköz).

-   **Megfelelő és nem megfelelő alkalmazások** – egy listában megadhatja a vállalatnál megfelelőnek vagy nem megfelelőnek ítélt alkalmazásokat. Android és iOS rendszerű eszközökön a **Jelentés a szabályzatnak nem megfelelő alkalmazásokról** beállítással ellenőrizhető, hogy a listában megadott alkalmazások kompatibilisek-e a felhasználók által telepített alkalmazásokkal. A jelentés ugyanakkor nem képes ténylegesen letiltani az alkalmazás telepítését.

> [!TIP]
> Beállíthatja, hogy a felhasználóknak kötelező legyen elfogadni, hogy az eszközükön lévő valamennyi alkalmazás – így személyes alkalmazásaik is – ellenőrizve legyenek, és a nem megfelelő alkalmazásokat a rendszer letiltsa vagy nem megfelelőként jelentse. A felhasználóknak el kell fogadniuk ezeket a feltételeket ahhoz, hogy beléptethessék eszközüket, és a vállalati portál segítségével beszerezhessék az alkalmazásokat. A használati feltételekkel kapcsolatos további információt a [Használati feltételek házirend-beállításai a Microsoft Intune-ban](terms-and-condition-policy-settings-in-microsoft-intune.md) című témakörben találhat.

Ha a keresett beállítás nem szerepel ebben a témakörben, valószínűleg létre tudja hozni egy egyéni Android-szabályzattal, amely lehetővé teszi az OMA-URI-beállítások használatát az eszköz vezérlésére. További információkért olvassa el a jelen témakörben alább található [Egyéni szabályzatbeállítások](#custom-policy-settings) című részt.

### <a name="password-settings"></a>Jelszóbeállítások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|-|----------------|----------------|
|**Jelszó szükséges a mobileszközök feloldásához**|Megadja, hogy kelljen-e jelszót kérni a támogatott eszközökön.|Igen|Igen|
|**Jelszó minimális hossza**|Megadja a jelszó minimális hosszát.|Igen|Igen|
|**Ennyi ismétlődő sikertelen bejelentkezés után törlődnek végleg az adatok az eszközről**|Megadja, hogy hány sikertelen bejelentkezés legyen megengedett, mielőtt az eszközön tárolt adatok törölve lennének.|Igen|Igen|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Az eszköz az itt megadott számú másodperc elteltével automatikusan zárolja magát.|Igen|Igen|
|**Jelszó lejárata (nap)**|Megadja, hogy hány nap elteltével kötelező megváltoztatni a jelszót.|Igen|Igen|
|**Jelszóelőzmények megjegyzése**|Megadja, hogy az eszköz hány korábban használt jelszót jegyezzen meg.|Igen|Igen|
|**Korábbi jelszavak megjegyzése** - **Korábbi jelszavak újbóli használatának tiltása**|Megakadályozza a korábbi jelszavak újbóli használatát.|Igen|Igen|
|**Jelszó erőssége**|Megadja a jelszó erősségének szintjét, valamint azt, hogy használható-e biometrikus eszköz.|Igen|Igen|
|**Ujjlenyomattal történő zárolásfeloldás engedélyezése**|Az eszköz ujjlenyomattal történő feloldásának engedélyezése.|Nem|Igen|
|**Intelligens zárolás és más megbízhatósági ügynökök engedélyezése**<br>(Android 5 és újabb verziók)|A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van, például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.|Igen|Nem|

### <a name="encryption-settings"></a>Titkosítási beállítások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Mobileszköz titkosításának kötelezővé tétele**|A mobileszközön található összes fájlnak titkosítva kell lennie.|Igen|Igen|
|**Titkosítás megkövetelése tárolókártyákon**|Ez a beállítás határozza meg, hogy kötelező legyen-e az eszköz tárolókártyájának titkosítása.|Nem|Igen|

### <a name="system-settings"></a>Rendszerbeállítások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Képernyőfelvétel engedélyezése**|Lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.|Nem|Igen|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezése esetén az eszköz diagnosztikai adatokat küld a Google-nak.|Nem|Igen|
|**Gyári beállítások visszaállításának engedélyezése**|Lehetővé teszi, hogy a felhasználó visszaállítsa a gyári beállításokat az eszközön.|Nem|Igen|

### <a name="cloud-settings---documents-and-data"></a>Felhőbeállítások – dokumentumok és adatok

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------------------|----------------|
|**A Google-fiók biztonsági mentésének engedélyezése**|A Google-fiók biztonsági mentésének engedélyezése.|Nem|Igen|

### <a name="cloud-settings---accounts-and-synchronization"></a>Felhőbeállítások – fiókok és szinkronizálás

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Google-fiók automatikus szinkronizálásának engedélyezése**|Google-fiókbeállítások automatikus szinkronizálásának engedélyezése.|Nem|Igen|

### <a name="application-settings---browser"></a>Alkalmazásbeállítások – böngésző

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Webböngésző engedélyezése**|Ezzel a beállítással adható meg, hogy engedélyezett-e az eszköz alapértelmezett webböngészőjének használata.|Nem|Igen|
|**Automatikus kitöltés engedélyezése**|A böngésző automatikus kitöltési funkciójának engedélyezése.|Nem|Igen|
|**Előugróablak-blokkoló engedélyezése**|A böngésző előugróablak-blokkoló funkciójának engedélyezése.|Nem|Igen|
|**Cookie-k engedélyezése**|Engedélyezi, hogy az eszköz webböngészője cookie-kat használjon.|Nem|Igen|
|**Active Scripting engedélyezése**|Engedélyezi az eszköz webböngészője Active Scripting funkciót használjon.|Nem|Igen|

### <a name="application-settings---apps"></a>Alkalmazásbeállítások – alkalmazások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Google Play áruház engedélyezése**|A Google Play Áruház használatának engedélyezése az eszközön.|Nem|Igen|

### <a name="device-capabilities-settings---hardware"></a>Eszközképességek beállításai – hardver

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Kamera engedélyezése**|Engedélyezi az eszköz kamerájának használatát.|Igen|Igen|
|**Cserélhető tároló engedélyezése**|Cserélhető tárolók (például SD-kártya) használatának engedélyezése az eszközön.|Nem|Igen|
|**Wi-Fi engedélyezése**|Az eszköz Wi-Fi-funkciójának engedélyezése.|Nem|Igen|
|**Wi-Fi alapú internetmegosztás használatának engedélyezése**|Az eszköz Wi-Fi-alapú internetmegosztási funkciójának engedélyezése.|Nem|Igen|
|**Földrajzi hely meghatározásának engedélyezése**|Engedélyezi az eszköz számára a helyadatok használatát.|Nem|Igen|
|**NFC használatának engedélyezése**|A kis hatótávolságú kommunikációt használó műveletek engedélyezése (ha az eszköz támogatja ezt a funkciót).|Nem|Igen|
|**Bluetooth engedélyezése**|Az eszköz Bluetooth-funkciójának engedélyezése.|Nem|Igen|
|**Kikapcsolás engedélyezése**|Az eszköz felhasználó általi kikapcsolásának engedélyezése.<br /><br />Ha ez a beállítás le van tiltva, a **Megengedett sikertelen bejelentkezések száma az eszközön tárolt adatok törléséig** beállítás Samsung KNOX Standard-eszközökön nem működik.|Nem|Igen|

### <a name="device-capabilities-settings---cellular"></a>Eszközképességek beállításai – mobilhálózat

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Hangroaming engedélyezése**|Hangroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|Nem|Igen|
|**Adatroaming engedélyezése**|Adatroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|Nem|Igen|
|**SMS- és MMS-funkciók engedélyezése**|SMS- és MMS-üzenetek engedélyezése az eszközön.|Nem|Igen|

### <a name="device-capabilities-settings---features"></a>Eszközképességek beállításai – szolgáltatások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Beszédfelismerési asszisztens engedélyezése**|Hangsegéd szoftverek használatának engedélyezése az eszközön.|Nem|Igen|
|**Hangtárcsázás engedélyezése**|A hangtárcsázási funkció engedélyezése vagy letiltása az eszközön.|Nem|Igen|
|**Másolás és beillesztés engedélyezése**|Az eszköz másolási és beillesztési funkcióinak engedélyezése.|Nem|Igen|
|**Vágólap alkalmazások közötti megosztásának engedélyezése**|A vágólap használatának engedélyezése az alkalmazások közötti másoláshoz.|Nem|Igen|
|**A YouTube engedélyezése**|A YouTube használatának engedélyezése az eszközön.|Nem|Igen|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>A szabályzatnak megfelelő és nem megfelelő alkalmazásokra vonatkozó beállítások
A **Szabályzatnak megfelelő és nem megfelelő alkalmazások** listában adja meg az alábbi információkat használó megfelelő vagy nem megfelelő eszközöket:

> [!NOTE]
> Egy szabályzatban csak a megfelelő vagy a nem megfelelő alkalmazások listája szerepelhet. Mindkét típusú lista nem adható meg ugyanabban a házirendben.

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Meg nem felelésről szóló jelentés küldése, ha a felhasználók telepítik a listán szereplő alkalmazások valamelyikét**|Azokat a nem az Intune által felügyelt alkalmazásokat tartalmazza, amelyeket a felhasználók nem telepíthetnek és futtathatnak. Ha a felhasználók ezen alkalmazások egyikét telepítik, szerepelni fog a szabályzatoknak nem megfelelő alkalmazásokról készült jelentésben.|
|**Meg nem felelés jelentésének mellőzése, ha a felhasználók telepítik a listán szereplő alkalmazások valamelyikét**|Azokat az alkalmazásokat tartalmazza, amelyek használatát engedélyezni kívánja. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.|
|**Hozzáadás**|Hozzáadhat egy alkalmazást a kijelölt listához. Meg kell adnia az alkalmazás nevét, kiadóját (nem kötelező) és alkalmazás-áruházbeli URL-címét.<br /><br />További segítségért olvassa el a jelen témakör [Alkalmazás-áruházak URL-címének megadása](#specify-urls-to-app-stores) című részét.|
|**Alkalmazások importálása**|Importálja az Ön által vesszővel tagolt fájlban megadott alkalmazásokat. Használja a fájlban megadott formátumot, alkalmazásnevet, kiadót és URL-címet.|
|**Szerkesztés**|Segítségével szerkesztheti a kijelölt alkalmazás nevét, kiadóját és URL-címét.|
|**Törlés**|Törölheti a kijelölt alkalmazást a listából.|

A megfelelő és nem megfelelő alkalmazás-beállításokat is tartalmazó szabályzatokat telepíteni kell a felhasználói csoportok számára.

### <a name="kiosk-mode-settings"></a>Teljes képernyős mód beállításai
Adja meg a következő értékeket a **Samsung KNOX Standard**-eszközök beállításhoz:

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Az eszközön teljes képernyős módban futtatható felügyelt alkalmazás kiválasztása**|Válassza a **Tallózás** elemet, majd válassza ki a felügyelt alkalmazást, amelynek engedélyezni szeretné, hogy az eszköz teljes képernyős módban futtassa (az áruházra mutató hivatkozásként megadott alkalmazások jelenleg nem támogatottak). Az itt megadotton kívül más alkalmazás nem futtatható az eszközön.|
|**Hangerőszabályzó gombok engedélyezése**|Engedélyezheti vagy letilthatja a hangerőszabályzó gombok használatát az eszközön.|
|**Képernyőt felébresztő gomb engedélyezése**|Engedélyezheti vagy letilthatja a képernyő ébresztőgombját az eszközön.|

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>A szabályzatnak megfelelő és nem megfelelő alkalmazások referenciaadatai

#### <a name="monitor-compliant-and-noncompliant-apps"></a>A szabályzatnak megfelelő és nem megfelelő alkalmazások figyelése
A **Nem kompatibilis alkalmazások jelentése** beállítás használatával megtekintheti az engedélyezett és letiltott alkalmazások kompatibilitását.

###### <a name="to-run-the-noncompliant-apps-report"></a>A nem kompatibilis alkalmazások jelentésének futtatása

1.  A [Microsoft Intune felügyeleti konzolban](https://manage.microsoft.com) válassza a **Jelentések** &gt; **Jelentés a szabályzatnak nem megfelelő alkalmazásokról** elemet.

2.  Válassza ki az ellenőrizni kívánt eszközcsoportokat. Ezután válassza ki, hogy csak a megfelelő alkalmazásokat vagy csak a nem megfelelő alkalmazásokat, vagy mindkettőt kívánja ellenőrizni. Végül válassza a **Jelentés megtekintése** lehetőséget.

#### <a name="specify-urls-to-app-stores"></a>Alkalmazás-áruházak URL-címének megadása
Ha szeretné megadni egy alkalmazás URL-címét a megfelelő és nem megfelelő alkalmazások listájában, végezze el az alábbiakat:

A [Google Play Alkalmazások szakaszában](https://play.google.com/store/apps) keresse meg a használni kívánt alkalmazást.

Nyissa meg az alkalmazás telepítési lapját, és másolja az URL-címet a vágólapra. Most ezt a címet felhasználhatja URL-címként a kompatibilis vagy a nem kompatibilis alkalmazások listájában.

Például: Keressen rá a Google Play-ben a Microsoft Office Mobile kifejezésre. A használt URL-cím a következő: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## <a name="custom-policy-settings"></a>Egyéni szabályzatbeállítások
A Microsoft Intune **Androidos egyéni konfigurációs szabályzatával** OMA-URI-beállításokat léptethet érvénybe, amelyekkel vezérelhetők az Android-eszközökön elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan Android-beállításokat telepíthet, amelyek nem konfigurálhatók Intune-szabályzatokkal.
Az Intune jelenleg csak korlátozott számú egyéni Android-szabályzatot támogat. E témakör példái alapján megtudhatja, mely szabályzatokat lehet konfigurálni.

### <a name="general-settings"></a>Általános beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    | **Név** |Adjon egyedi nevet az egyéni Android-szabályzatnak, hogy az azonosítható legyen az Intune konzolján.|
    | **Leírás** |Adjon meg egy leírást, amely áttekintést nyújt az Android egyéni szabályzatáról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.|

### <a name="oma-uri-settings"></a>OMA-URI-beállítások

   |Beállítás neve|Részletek|
    |--------|--------------------|
    | **A beállítás neve** |Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.|
    | **A beállítás leírása** |Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.|
    | **Adattípus** |Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc, Karakterlánc (XML), Dátum és idő, Egész szám, Lebegőpontos szám** vagy **Logikai** lehetőségek közül választhat.|
    | **OMA-URI (megkülönbözteti a kis- és nagybetűket)** |Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.|
    | **Érték** |Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket.|

### <a name="examples"></a>Példák

- [Wi-Fi-profil létrehozása előmegosztott kulccsal](pre-shared-key-wi-fi-profile.md)
- [Egyéni szabályzat használata az Android-eszközök alkalmazásonkénti VPN-profiljainak létrehozásához](per-app-vpn-for-android-pulse-secure.md)
- [Egyéni szabályzat használata alkalmazások engedélyezéséhez és letiltásához Samsung KNOX-eszközökön](custom-policy-to-allow-and-block-samsung-knox-apps.md)

## <a name="supported-samsung-knox-standard-devices"></a>Támogatott Samsung KNOX Standard-eszközök

Az MDM-regisztráció során a Céges portál alkalmazás csak akkor kísérli meg a Samsung KNOX-aktiválást, ha az eszköz szerepel a [támogatott KNOX-eszközök listáján](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Így elkerülhetők az MDM-regisztrációt megakadályozó KNOX-aktiválási hibák. Azokat az eszközöket, melyek nem támogatják a Samsung KNOX-aktiválást, szabványos Android-eszközként regisztrálja a rendszer. Előfordulhat, hogy egy Samsung eszköz néhány modellje támogatja a KNOX platformot, míg mások nem. Egy adott eszköz megvásárlása és üzembe helyezése előtt egyeztesse az eszköz viszonteladójával, hogy kompatibilis-e a KNOX-szal.

Az alábbi Samsung eszközök nem támogatják a KNOX platformot, így ezeket az androidos Céges portál alkalmazás natív Android-eszközként fogja regisztrálni:

| **Eszköz neve** | **Eszköz modellszáma** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |



### <a name="see-also"></a>További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
