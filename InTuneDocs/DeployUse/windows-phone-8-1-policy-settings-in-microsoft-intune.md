---
title: "Windows Phone 8.1-es házirend-beállítások | Microsoft Intune"
description: "Az Intune a Windows Phone 8.1-eszközökön beállítható, beépített általános beállítások széles választékát kínálja. Ezenkívül megadhatja az OMA-URI-értékeket is olyan egyéni beállítások létrehozásához, amelyek nem érhetők el az Intune-ban."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4279ecd098ddaa6d6eb239ee71f9c3f7d450ab3f
ms.openlocfilehash: f2ccc52ceae6bbb63ea76ff4391922099c69f4dd


---

# Windows Phone 8.1-es házirend-beállítások a Microsoft Intune-ban

Az Intune a Windows Phone 8.1-eszközökön beállítható, beépített általános beállítások széles választékát kínálja. Ezek mellett megadhat Open Mobile Alliance Uniform Resource Identifier (OMA-URI) értékeket is olyan egyéni beállítások létrehozásához, amelyek nem érhetők el az Intune-ban.

## Általános konfigurációs beállítások

A Microsoft Intune **Windows Phone-eszközökhöz készült általános konfigurációs szabályzatával (Windows Phone 8.1 és újabb rendszereknél)** a következő beállításokat adhatja meg a Windows 8.1-eszközökön:

-   **Mobileszköz-biztonsági beállítások** – előre meghatározott beállítások egy listájából választva számos szolgáltatást és funkciót szabályozhat az eszközökön.

-   **Megfelelő és nem megfelelő alkalmazások** – egy listában megadhatja a vállalatban megfelelőnek vagy nem megfelelőnek ítélt alkalmazásokat. A Windows Phone-telefonok blokkolhatják vagy engedélyezhetik ezeknek az alkalmazásoknak a telepítését.

### Alkalmazhatósági beállítások

|Beállítás neve|Részletek|
|----------------|----------------------------------|
|**Az összes konfiguráció alkalmazása a Windows 10-re**|Ezzel a beállítással engedélyezheti, hogy a szabályzatban szereplő beállítások a rendszer Windows Phone 8.1-eszközökön felül a Windows 10 Mobile-eszközökre is alkalmazza.|

### Jelszóbeállítások

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Jelszó szükséges a mobileszközök feloldásához**|Ez a beállítás azt határozza meg, hogy a felhasználóknak kell-e jelszót megadniuk az eszközükhöz való hozzáféréshez.|Igen|Igen|
|**Kötelező jelszótípus**|Meghatározza a megkövetelt jelszótípust, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.|Igen|Igen|
|**Megkövetelt jelszótípus – a karakterkészletek minimális száma**|Azt határozza meg, hány különböző karakterkészletnek kell szerepelnie a jelszóban. A következő négy karakterkészlet létezik: kisbetűk, nagybetűk, számok és szimbólumok. iOS-eszközök esetén azonban ez azt határozza meg, hány szimbólumnak kell szerepelnie a jelszóban.|Igen|Igen|
|**Jelszó minimális hossza**|A jelszóban használandó karakterek minimális számát határozza meg.|Igen|Igen|
|**Egyszerű jelszavak engedélyezése**|Engedélyezi az egyszerű jelszavak (például a „0000”vagy az”1234”) használatát.|Igen|Igen|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|Meghatározza, hogy a felhasználó hányszor adhat meg helytelen jelszót, mielőtt a rendszer törölné az eszközt.|Igen|Igen|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő automatikus zárolása előtt.|Igen|Igen|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.|Igen|Igen|
|**Jelszóelőzmények megjegyzése**|Meghatározza, hogy a korábban használt jelszavak rendszer megjegyezze annak megakadályozásához, hogy a felhasználó újra használni.|Igen|Igen|
|**Korábbi jelszavak megjegyzése** – **Korábbi jelszavak újbóli használatának tiltása**|Meghatározza, hogy a rendszer hány korábban használt jelszót jegyezzen meg.|Igen|Igen|

### Titkosítási beállítások

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Mobileszköz titkosításának kötelezővé tétele**|Kötelezővé teszi az adatok titkosítását a támogatott mobileszközökön.<br>A Windows Phone 8-telefonokon ezt **Igen**értékre kell állítani.|Igen|Igen|

### Rendszerbeállítások

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Képernyőfelvétel-készítés használatának engedélyezése**|A képernyőtartalom képfájlban történő rögzítésének engedélyezése a felhasználó számára.|Nem|Igen|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezése esetén az eszköz diagnosztikai adatokat küld a Microsoftnak.|Nem|Igen|

### Felhőbeállítások – fiókok és szinkronizálás

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Microsoft-fiók használatának engedélyezése**|Engedélyezi Microsoft-fiók társítását az eszközzel.|Nem|Igen|

### E-mail beállítások

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Egyéni e-mail fiókok engedélyezése**|Nem Microsoft e-mail fiókokhoz való kapcsolódás engedélyezése az eszköz számára.|Nem|Igen|

### Alkalmazásbeállítások – böngésző

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Webböngésző használatának engedélyezése**|Engedélyezi vagy letiltja az eszköz beépített webböngészőjét.|Nem|Igen|

### Alkalmazásbeállítások – alkalmazások

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Alkalmazástároló használatának engedélyezése**|Lehetővé teszi a felhasználók számára az alkalmazás-áruház elérését az eszközről.|Nem|Igen|

### Eszközképességek beállításai – hardver

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kamera használatának engedélyezése**|Engedélyezi vagy letiltja az eszköz kamerájának használatát.|Nem|Igen|
|**Cserélhető tároló használatának engedélyezése**|Cserélhető tárolók (például SD-kártya) használatának engedélyezése az eszközön.|Igen|Igen|
|**Wi-Fi használatának engedélyezése**|Az eszköz Wi-Fi funkciójának engedélyezése vagy letiltása.|Nem|Igen|
|**Wi-Fi alapú internetmegosztás használatának engedélyezése**|Engedélyezi az eszköz Wi-Fi-alapú internetmegosztási funkciójának használatát.|Nem|Igen
|**Wi-Fi elérési pontokhoz való automatikus csatlakozás engedélyezése**|Engedélyezi az eszközön az ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozást és a vonatkozó használati feltételek automatikus elfogadását.|Nem|Igen|
|**Wi-Fi elérési pontok jelentéskészítésének engedélyezése**|Információt küld a Wi-Fi kapcsolatokról a közeli kapcsolatok felderítésének elősegítése érdekében.|Nem|Igen|
|**Földrajzi hely meghatározásának engedélyezése**|Engedélyezi az eszköz számára a helyadatok használatát.|Nem|Igen|
|**NFC használatának engedélyezése**|Engedélyezi a kis hatótávolságú kommunikációt használó műveleteket.|Nem|Igen|
|**Bluetooth használatának engedélyezése**|Az eszköz Bluetooth funkciójának engedélyezése vagy letiltása.|Nem|Igen|

### Eszközképességek beállításai – szolgáltatások

|Beállítás neve|Részletek|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Másolás és beillesztés használatának engedélyezése**|Engedélyezi az eszköznek a másolási és a beillesztési funkció használatát.|Nem|Igen|

### Az engedélyezett és letiltott alkalmazások beállításai
Az **Engedélyezett és letiltott alkalmazások** listában adja meg az engedélyezni vagy letiltani kívánt alkalmazásokat a következő információk alapján:

> [!NOTE]
> Egyetlen szabályzatban csak egy, vagy engedélyezett, vagy letiltott alkalmazásokat tartalmazó lista szerepelhet. Mindkét típusú lista nem adható meg ugyanabban a házirendben.

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Nem engedélyezi, hogy az eszközök megnyissák a listázott alkalmazásokat**|Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyek telepítése és futtatása nem engedélyezett a felhasználóknak.|
|**Engedélyezi, hogy az eszközök megnyissák csak a listázott alkalmazásokat**|Azokat az alkalmazásokat tartalmazza, amelyeket a felhasználók telepíthetnek. A felhasználók ezeken kívül más alkalmazásokat nem telepíthetnek. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.|
|**Hozzáadás**|Hozzáadhat egy alkalmazást a kijelölt listához. Meg kell adnia egy szabadon választott nevet, valamint tetszés szerint megadhatja az alkalmazás kiadóját, valamint alkalmazás-áruházbeli URL-címét. További segítségért olvassa el az Alkalmazás-áruházak URL-címének megadása című részt a jelen témakörben.
|**Alkalmazások importálása**|Importálja az Ön által vesszővel tagolt fájlban megadott alkalmazásokat. Használja a fájlban megadott formátumot, alkalmazásnevet, kiadót és URL-címet.|
|**Szerkesztés**|Segítségével szerkesztheti a kijelölt alkalmazás nevét, kiadóját és URL-címét.|
|**Törlés**|Törölheti a kijelölt alkalmazást a listából.|
> [!IMPORTANT]
> Ha megadja a kompatibilis alkalmazások listáját a Windows Phone 8.1 rendszerű eszközökhöz, fel kell vennie a Vállalati portál alkalmazást, mert ellenkező esetben az le lesz tiltva.


### Referenciainformációk az engedélyezett és letiltott alkalmazásokhoz

#### Alkalmazás-áruházak URL-címének megadása
Ha meg szeretné adni egy alkalmazás URL-címét az engedélyezett vagy letiltott alkalmazások listájában, használja a következő formátumot:

A [Windows Phone Alkalmazások+játékok](http://www.windowsphone.com/en-us/store/overview) lapon keressen rá a használni kívánt alkalmazásra.

Nyissa meg az alkalmazás lapját, és másolja az URL-címet a vágólapra. Ezt a címet az engedélyezett és a tiltott alkalmazások listájában egyaránt használhatja URL-címként.

**Például:** Keressen rá az áruházban a Skype alkalmazásra. A használt URL-cím a következő: **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Egyéni szabályzatbeállítások
A Microsoft Intune **Windows Phone-os egyéni konfigurációs szabályzatával** OMA-URI-beállításokat léptethet érvénybe, amelyekkel vezérelhetők a **Windows Phone 8.1-eszközökön** elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a funkcióval olyan Windows Phone-beállításokat léptethet érvénybe, amelyek nem konfigurálhatók az Intune általános konfigurációs házirendjével. Az ezen házirendekkel konfigurálható beállításokkal kapcsolatos további információkért lásd: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

A Windows Phone-telefonokra érvényes OMA-URI beállítások létrehozásához lásd a [Windows Phone 8.1 MDM-protokoll dokumentációját](http://technet.microsoft.com/library/dn499787.aspx).

### Általános beállítások

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Név**|Adjon meg egy egyedi nevet a házirend számára, hogy azonosítható legyen az Intune konzolján.|
|**Leírás**|Adjon meg egy olyan leírást, amely áttekintést nyújt a szabályzatról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek megkeresésében.|

### OMA-URI-beállítások

Az **OMA-URI beállítások** szakaszban kattintson a **Hozzáadás** elemre egy beállítás hozzáadásához. Szerkesztheti és törölheti is a meglévő beállításokat.

Az **OMA-URI beállítás hozzáadása vagy szerkesztése** párbeszédpanelen adja meg a következő információkat:

|Beállítás neve|Részletek|
    |--------|--------------------|
    |**Beállítás neve**|Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.|
    |**Beállítás leírása**|Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.|
    |**Adattípus**|Válassza ki az adattípust az OMA-URI-beállítás megadásához. A következő lehetőségek közül választhat:<br /><br />-   **Karakterlánc**<br />-   **Karakterlánc (XML)**<br />-   **Dátum és időpont**<br />-   **Egész szám**<br />-   **Lebegőpontos szám**<br />-   **Logikai**|
    |**OMA-URI (megkülönbözteti a kis- és nagybetűket)**|Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.|
    |**Érték**|Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket.|

### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


