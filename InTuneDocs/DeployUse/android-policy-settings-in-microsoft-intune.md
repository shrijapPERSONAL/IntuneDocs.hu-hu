---

title: "Android- és Samsung KNOX-eszközök konfigurációs szabályzatának beállításai | Microsoft Intune"
description: "Szabályzatok létrehozása, amelyek vezérlik a beállításokat és a szolgáltatásokat az Intune-nal felügyelt Android-eszközökön."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6e3e81f37e677a016ac49240cc70602a568afcd5
ms.openlocfilehash: 9385ca0e5aa9dd8fc2daf79c57b47951bcd5c0cb


---

# Android- és Samsung KNOX-eszközök konfigurációs házirendjének beállításai a Microsoft Intune-ban

Az Intune egy sor Android-eszközökön konfigurálható általános beállítást biztosít. Ezek mellett megadhat Open Mobile Alliance Uniform Resource Identifier (OMA-URI) értékeket is olyan egyéni beállítások létrehozásához, amelyek nem érhetők el az Intune-ban.

## Általános konfigurációs szabályzat

Az Intune **Androidhoz készült általános konfigurációs szabályzatát** a következő beállításához használhatja:

-   **Mobileszköz-biztonsági beállítások** – előre meghatározott beállítások listájából választva számos szolgáltatást és funkciót szabályozhat az eszközön.

-   **Teljes képernyős mód** (csak Samsung KNOX-eszközök esetén) – zárolhatja az eszközt, hogy csak bizonyos szolgáltatások működjenek rajta. Megadhatja például, hogy az eszköz csak egy meghatározott felügyelt alkalmazás futtatását engedélyezze, vagy letilthatja a hangerő-szabályozó gombok használatát. Ezek a beállítások használhatók például egy eszköz bemutató modelljéhez vagy egy olyan eszközhöz, amely csak egyetlen funkció végrehajtására van kijelölve (például egy pénztári eszköz).

-   **Megfelelő és nem megfelelő alkalmazások** – egy listában megadhatja a vállalatnál megfelelőnek vagy nem megfelelőnek ítélt alkalmazásokat. Android és iOS rendszerű eszközökön a **Jelentés a szabályzatnak nem megfelelő alkalmazásokról** beállítással ellenőrizhető, hogy a listában megadott alkalmazások kompatibilisek-e a felhasználók által telepített alkalmazásokkal. A jelentés ugyanakkor nem képes ténylegesen letiltani az alkalmazás telepítését.

> [!TIP]
> Beállíthatja, hogy a felhasználóknak kötelező legyen elfogadni, hogy az eszközükön lévő valamennyi alkalmazás – így személyes alkalmazásaik is – ellenőrizve legyenek, és a nem megfelelő alkalmazásokat a rendszer letiltsa vagy nem megfelelőként jelentse. A felhasználóknak el kell fogadniuk ezeket a feltételeket ahhoz, hogy beléptethessék eszközüket, és a vállalati portál segítségével beszerezhessék az alkalmazásokat. A használati feltételekkel kapcsolatos további információt a [Használati feltételek házirend-beállításai a Microsoft Intune-ban](terms-and-condition-policy-settings-in-microsoft-intune.md) című témakörben találhat.

Ha a keresett beállítás nem szerepel ebben a témakörben, valószínűleg létre tudja hozni egy egyéni Android-szabályzattal, amely lehetővé teszi az OMA-URI-beállítások használatát az eszköz vezérlésére. További információkért olvassa el a jelen témakörben alább található [Egyéni szabályzatbeállítások](#custom-policy-settings) című részt.

### Jelszóbeállítások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Jelszó szükséges a mobileszközök feloldásához**|Megadja, hogy kelljen-e jelszót kérni a támogatott eszközökön.|Igen|Igen|
|**Jelszó minimális hossza**|Megadja a jelszó minimális hosszát.|Igen|Igen|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|Megadja, hogy hány sikertelen bejelentkezés legyen megengedett, mielőtt az eszközön tárolt adatok törölve lennének.|Igen|Igen|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Az eszköz az itt megadott számú másodperc elteltével automatikusan zárolja magát.|Igen|Igen|
|**Jelszó lejárata (nap)**|Megadja, hogy hány nap elteltével kötelező megváltoztatni a jelszót.|Igen|Igen|
|**Jelszóelőzmények megjegyzése**|Megadja, hogy az eszköz hány korábban használt jelszót jegyezzen meg.|Igen|Igen|
|**Korábbi jelszavak megjegyzése** - **Korábbi jelszavak újbóli használatának tiltása**|Megakadályozza a korábbi jelszavak újbóli használatát.|Igen|Igen|
|**Jelszó minősége**|Megadja a jelszó erősségének szintjét, valamint azt, hogy használható-e biometrikus eszköz.|Igen|Igen|
|**Ujjlenyomattal történő zárolásfeloldás engedélyezése**|Az eszköz ujjlenyomattal történő feloldásának engedélyezése.|Nem|Igen|
|**Intelligens zárolás és más megbízhatósági ügynökök engedélyezése**<br>(Android 5 és újabb verziók)|A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van, például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.|Igen|Nem|

### Titkosítási beállítások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Mobileszköz titkosításának kötelezővé tétele**|A mobileszközön található összes fájlnak titkosítva kell lennie.|Igen|Igen|
|**Titkosítás megkövetelése tárolókártyákon**|Ez a beállítás határozza meg, hogy kötelező legyen-e az eszköz tárolókártyájának titkosítása.|Nem|Igen|

### Rendszerbeállítások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Képernyőfelvétel-készítés használatának engedélyezése**|Lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.|Nem|Igen|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezése esetén az eszköz diagnosztikai adatokat küld a Google-nak.|Nem|Igen|
|**Gyári beállítások visszaállításának engedélyezése**|Lehetővé teszi, hogy a felhasználó visszaállítsa a gyári beállításokat az eszközön.|Nem|Igen|

### Felhőbeállítások – dokumentumok és adatok

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------------------|----------------|
|**A Google-fiók biztonsági mentésének engedélyezése**|A Google-fiók biztonsági mentésének engedélyezése.|Nem|Igen|

### Felhőbeállítások – fiókok és szinkronizálás

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google-fiók automatikus szinkronizálásának engedélyezése**|Google-fiókbeállítások automatikus szinkronizálásának engedélyezése.|Nem|Igen|

### Alkalmazásbeállítások – böngésző

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Webböngésző használatának engedélyezése**|Ezzel a beállítással adható meg, hogy engedélyezett-e az eszköz alapértelmezett webböngészőjének használata.|Nem|Igen|
|**Automatikus kitöltés engedélyezése**|A böngésző automatikus kitöltési funkciójának engedélyezése.|Nem|Igen|
|**Előugróablak-blokkoló engedélyezése**|A böngésző előugróablak-blokkoló funkciójának engedélyezése.|Nem|Igen|
|**Cookie-k engedélyezése**|Engedélyezi, hogy az eszköz webböngészője cookie-kat használjon.|Nem|Igen|
|**Active Scripting engedélyezése**|Engedélyezi az eszköz webböngészője Active Scripting funkciót használjon.|Nem|Igen|

### Alkalmazásbeállítások – alkalmazások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google Play áruház engedélyezése**|A Google Play Áruház használatának engedélyezése az eszközön.|Nem|Igen|

### Eszközképességek beállításai – hardver

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Kamera használatának engedélyezése**|Engedélyezi az eszköz kamerájának használatát.|Igen|Igen|
|**Cserélhető tároló használatának engedélyezése**|Cserélhető tárolók (például SD-kártya) használatának engedélyezése az eszközön.|Nem|Igen|
|**Wi-Fi használatának engedélyezése**|Az eszköz Wi-Fi-funkciójának engedélyezése.|Nem|Igen|
|**Wi-Fi alapú internetmegosztás használatának engedélyezése**|Az eszköz Wi-Fi-alapú internetmegosztási funkciójának engedélyezése.|Nem|Igen|
|**Földrajzi hely meghatározásának engedélyezése**|Engedélyezi az eszköz számára a helyadatok használatát.|Nem|Igen|
|**NFC használatának engedélyezése**|A kis hatótávolságú kommunikációt használó műveletek engedélyezése (ha az eszköz támogatja ezt a funkciót).|Nem|Igen|
|**Bluetooth használatának engedélyezése**|Az eszköz Bluetooth-funkciójának engedélyezése.|Nem|Igen|
|**Kikapcsolás engedélyezése**|Az eszköz felhasználó általi kikapcsolásának engedélyezése.<br /><br />Ha ez a beállítás le van tiltva, a **Megengedett sikertelen bejelentkezések száma az eszközön tárolt adatok törléséig** beállítás Samsung KNOX-eszközökön nem működik.|Nem|Igen|

### Eszközképességek beállításai – mobilhálózat

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Hangroaming engedélyezése**|Hangroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|Nem|Igen|
|**Adatroaming engedélyezése**|Adatroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|Nem|Igen|
|**SMS-/MMS-üzenetküldés engedélyezése**|SMS- és MMS-üzenetek engedélyezése az eszközön.|Nem|Igen|

### Eszközképességek beállításai – szolgáltatások

|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Hangsegéd engedélyezése**|Hangsegéd szoftverek használatának engedélyezése az eszközön.|Nem|Igen|
|**Hangtárcsázás engedélyezése**|A hangtárcsázási funkció engedélyezése vagy letiltása az eszközön.|Nem|Igen|
|**Másolás és beillesztés használatának engedélyezése**|Az eszköz másolási és beillesztési funkcióinak engedélyezése.|Nem|Igen|
|**Vágólap alkalmazások közötti megosztásának engedélyezése**|A vágólap használatának engedélyezése az alkalmazások közötti másoláshoz.|Nem|Igen|
|**A YouTube használatának engedélyezése**|A YouTube használatának engedélyezése az eszközön.|Nem|Igen|

### A szabályzatnak megfelelő és nem megfelelő alkalmazásokra vonatkozó beállítások
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

### Teljes képernyős mód beállításai
Adja meg a következő értékeket a **Samsung KNOX**-eszközök beállításhoz:

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Az eszközön teljes képernyős módban futtatható felügyelt alkalmazás kiválasztása**|Válassza a **Tallózás** elemet, majd válassza ki a felügyelt alkalmazást, amelynek engedélyezni szeretné, hogy az eszköz teljes képernyős módban futtassa (az áruházra mutató hivatkozásként megadott alkalmazások jelenleg nem támogatottak). Az itt megadotton kívül más alkalmazás nem futtatható az eszközön.|
|**Hangerőszabályzó gombok engedélyezése**|Engedélyezheti vagy letilthatja a hangerőszabályzó gombok használatát az eszközön.|
|**Képernyő ébresztőgombjának engedélyezése**|Engedélyezheti vagy letilthatja a képernyő ébresztőgombját az eszközön.|

### A szabályzatnak megfelelő és nem megfelelő alkalmazások referenciaadatai

#### A szabályzatnak megfelelő és nem megfelelő alkalmazások figyelése
A **Nem kompatibilis alkalmazások jelentése** beállítás használatával megtekintheti az engedélyezett és letiltott alkalmazások kompatibilitását.

###### A nem kompatibilis alkalmazások jelentésének futtatása

1.  A [Microsoft Intune felügyeleti konzolban](https://manage.microsoft.com) válassza a **Jelentések** &gt; **Jelentés a szabályzatnak nem megfelelő alkalmazásokról** elemet.

2.  Válassza ki az ellenőrizni kívánt eszközcsoportokat. Ezután válassza ki, hogy csak a megfelelő alkalmazásokat vagy csak a nem megfelelő alkalmazásokat, vagy mindkettőt kívánja ellenőrizni. Végül válassza a **Jelentés megtekintése** lehetőséget.

#### Alkalmazás-áruházak URL-címének megadása
Ha szeretné megadni egy alkalmazás URL-címét a megfelelő és nem megfelelő alkalmazások listájában, végezze el az alábbiakat:

A [Google Play Alkalmazások szakaszában](https://play.google.com/store/apps) keresse meg a használni kívánt alkalmazást.

Nyissa meg az alkalmazás telepítési lapját, és másolja az URL-címet a vágólapra. Most ezt a címet felhasználhatja URL-címként a kompatibilis vagy a nem kompatibilis alkalmazások listájában.

Például: Keressen rá a Google Play-ben a Microsoft Office Mobile kifejezésre. A használt URL-cím a következő: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Egyéni szabályzatbeállítások
A Microsoft Intune **Androidos egyéni konfigurációs szabályzatával** OMA-URI-beállításokat léptethet érvénybe, amelyekkel vezérelhetők az Android-eszközökön elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan Android-beállításokat telepíthet, amelyek nem konfigurálhatók Intune-szabályzatokkal.

> [!NOTE]
> Jelenleg az egyéni Android-házirendek csak az előmegosztott kulcsot tartalmazó Android-eszközök Wi-Fi beállításainak konfigurálását támogatják.

### Általános beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    |**Név**|Adjon egyedi nevet az egyéni Android-szabályzatnak, hogy az azonosítható legyen az Intune konzolján.|
    |**Leírás**|Adjon meg egy leírást, amely áttekintést nyújt az Android egyéni szabályzatáról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.|

### OMA-URI-beállítások

   |Beállítás neve|Részletek|
    |--------|--------------------|
    |**Beállítás neve**|Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.|
    |**Beállítás leírása**|Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.|
    |**Adattípus**|Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc, Karakterlánc (XML), Dátum és idő, Egész szám, Lebegőpontos szám** vagy **Logikai** lehetőségek közül választhat.|
    |**OMA-URI (megkülönbözteti a kis- és nagybetűket)**|Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.|
    |**Érték**|Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket.|

### Példa: Egyéni Wi-Fi profil konfigurálása előmegosztott kulccsal
Bár az Intune támogatja az Android-eszközök Wi-Fi-profiljait, ez a szolgáltatás jelenleg nem támogatja az előmegosztott kulcs használatát a konfigurációban. Ebből a példából megtudhatja, hogyan hozhat létre előmegosztott kulcsot használó Wi-Fi profilt létrehozó egyéni Android-házirendet az Android-eszközön.

#### Wi-Fi profil létrehozása előmegosztott kulccsal

1.  Győződjön meg arról, hogy a felhasználók az Android rendszerhez készült [Intune Vállalati portál alkalmazás](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) legújabb verzióját használják.

2.  Hozzon létre egy egyéni Android-házirendet, és vegye fel a következő beállításokat:

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Beállítás neve**|Adja meg a beállítás kívánt nevét.|
|**Beállítás leírása**|Adja meg a jelentés leírását.|
|**Adattípus**|Válassza a **Karakterlánc (XML)** lehetőséget.|
|**OMA-URI**|Írja be a következőket: ./Vendor/MSFT/WiFi/Profile/*&lt;az Ön Wi-Fi profilja&gt;*/Settings|

3.  Az **Érték** mezőbe másolja és illessze be a következő XML-kódot:

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile
                    <SSID of wifi profile> = Plain text version of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  Amikor végzett, mentse a házirendet, és telepítse azt a szükséges Android-eszközökre. Az új Wi-Fi profil megjelenik a kapcsolatok listájában az eszközön.

### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jul16_HO4-->


