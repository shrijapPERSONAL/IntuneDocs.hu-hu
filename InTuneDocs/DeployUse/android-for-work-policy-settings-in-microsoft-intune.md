---

title: "Az Android for Work szabályzatbeállításai | Microsoft Intune"
description: "Szabályzatok létrehozása, amelyek vezérlik a beállításokat és a szolgáltatásokat az Intune-nal felügyelt Android for Work-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: f7c676b25f5dd5b7ee1d1d7c1b51b75a41b5c102


---

# Az Android for Work szabályzatbeállításai a Microsoft Intune-ban

Az Intune az Android for Work-eszközökön konfigurálható, beépített általános beállítások széles választékát kínálja.

## Általános konfigurációs szabályzat

Az Intune **Android for Work általános konfigurációs szabályzata** használatával konfigurálja Android for Work-eszközeire a biztonsági és a munkahelyi profil beállításait.

Ha a keresett beállítás nem szerepel ebben a témakörben, valószínűleg létre tudja hozni egy egyéni Android-szabályzattal, amely lehetővé teszi az OMA-URI-beállítások használatát az eszköz vezérlésére. További információkért olvassa el a jelen témakörben alább található [Egyéni szabályzatbeállítások](#custom-policy-settings) című részt.

> [!TIP]
> Az eszközök titkosítása automatikusan megtörténik a munkahelyi profil kiépítésekor. Ezt a beállítást nem változtathatja meg.

### Jelszóbeállítások

|Beállítás neve|Részletek|
|----------------|-|
|**Jelszó szükséges a mobileszközök feloldásához**|Meghatározza, hogy szükséges-e jelszó a felügyelt eszközön. A következő lehetőségek közül választhat:<br><br>- **Összetett** - tartalmaznia kell legalább egy betűt, számot és szimbólumot<br>- **Alfanumerikus** - tartalmaznia kell legalább egy számot és egy betűt<br>- **Alfabetikus** - legalább betűket vagy szimbólumokat igényel<br>- **Numerikus összetett** - nem ismétlődő és egymást nem követő számkaraktereket igényel<br>- **Numerikus**<br><br>Ha ez a beállítás nincs engedélyezve, akkor nem állnak fenn bonyolultsági feltételek.|
|**Jelszó minimális hossza**|A jelszóban használandó karakterek vagy számok minimális számát határozza meg.|
|**Inaktív percek száma az eszköz zárolásáig**|Az eszköz az itt megadott számú felhasználói tevékenység nélküli perc elteltével automatikusan zárolja magát.|
|**Intelligens zárolás és más megbízhatósági ügynökök engedélyezése**<br>(Android 6 és újabb verziók)|A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van, például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.|
|**Sikertelen bejelentkezések száma a munkahelyi profil eltávolítása előtt**|Megadja, hogy hány sikertelen bejelentkezés legyen megengedett, mielőtt az eszközön található munkaprofil el lenne távolítva. Ez nem hajt végre teljes törlést az eszközön.|
|**Jelszóelőzmények megjegyzése**|Letiltja a korábban használt jelszavak ismételt használatát.|
|**Korábbi jelszavak megjegyzése** - **Korábbi jelszavak újbóli használatának tiltása**|Megadja, hogy az eszköz hány korábban használt jelszót jegyezzen meg.|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.|
|**Ujjlenyomattal történő zárolásfeloldás engedélyezése**<br>(Android 6 és újabb verziók)|Lehetővé teszi az eszközök ujjlenyomattal történő zárolásfeloldását, ha az eszköz támogatja ezt a funkciót.|


### Munkahelyi profil beállításai

|Beállítás neve|Részletek|
|----------------|-|
|**Lehetővé teszi a munkahelyi és személyes profilok közötti adatmegosztást**|Lehetővé teszi a munkahelyi profilban és a felhasználók személyes profiljában található alkalmazások közötti adatmegosztást. A következő lehetőségek közül választhat:<br><br>- **Határokon keresztüli megosztás letiltása**<br>- **A munkahelyi profilban szereplő alkalmazások kezelhetik a személyes profiltól érkező megosztási kérést**<br>- **Nincs megosztási korlátozás**|
|**Munkahelyi profil értesítéseinek elrejtése, ha az eszköz zárolva van**<br>(Android 6 és újabb verziók)|Szabályozza a munkahelyi profiltól érkező értesítések láthatóságát, ha az eszköz zárolva van.|
|**Alapértelmezett alkalmazásengedélyezési szabályzat beállítása**<br>(Android 6 és újabb verziók)|Meghatározza a munkahelyi profilban található összes alkalmazásra vonatkozó alapértelmezett szabályzatot.|




## Egyéni szabályzatbeállítások
A Microsoft Intune **Android for Work egyéni konfigurációs szabályzatával** OMA-URI-beállításokat léptethet érvénybe, amelyekkel vezérelhetők az Android for Work-eszközökön elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

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

### Példák

- [Wi-Fi-profil létrehozása előmegosztott kulccsal](pre-shared-key-wi-fi-profile.md)
- [Egyéni szabályzat használata az Android-eszközök alkalmazásonkénti VPN-profiljainak létrehozásához](per-app-vpn-for-android-pulse-secure.md)

### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=Oct16_HO2-->


