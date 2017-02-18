---

title: "Az Android for Work szabályzatbeállításai | Microsoft Docs"
description: "Szabályzatok létrehozása, amelyek vezérlik a beállításokat és a szolgáltatásokat az Intune-nal felügyelt Android for Work-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 31e28514ab4bdb0f5af261a1f7c87633ca0bd4a6
ms.openlocfilehash: b95f7dbf37a159a62894ae27d1fdb731ede5570c


---

# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Az Android for Work szabályzatbeállításai a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Intune az [Android for Work-eszközökön](android-for-work.md) konfigurálható, beépített általános beállítások széles választékát kínálja.

## <a name="general-configuration-policy"></a>Általános konfigurációs szabályzat

Az Intune **Android for Work általános konfigurációs szabályzata** használatával konfigurálja Android for Work-eszközeire a biztonsági és a munkahelyi profil beállításait.

Ha a keresett beállítás nem szerepel ebben a témakörben, valószínűleg létre tudja hozni egy egyéni Android-szabályzattal, amely lehetővé teszi az OMA-URI-beállítások használatát az eszköz vezérlésére. További információkért olvassa el a jelen témakörben alább található [Egyéni szabályzatbeállítások](#custom-policy-settings) című részt.

> [!TIP]
> Az eszközök titkosítása automatikusan megtörténik a munkahelyi profil kiépítésekor. Ezt a beállítást nem változtathatja meg.

### <a name="password-settings"></a>Jelszóbeállítások

|Beállítás neve|Részletek|
|----------------|-|
|**Jelszó szükséges a mobileszközök feloldásához**|Meghatározza, hogy szükséges-e jelszó a felügyelt eszközön. A következő lehetőségek közül választhat:<br><br>- **Összetett** – tartalmaznia kell legalább egy betűt, számot és szimbólumot<br>- **Alfanumerikus** – tartalmaznia kell legalább egy számot és egy betűt<br>- **Alfabetikus** – legalább betűket vagy szimbólumokat igényel<br>- **Numerikus összetett** – nem ismétlődő és egymást nem követő számkaraktereket igényel<br>- **Numerikus**<br><br>Ha ez a beállítás nincs engedélyezve, akkor nem állnak fenn bonyolultsági feltételek.|
|**Jelszó minimális hossza**|A jelszóban használandó karakterek vagy számok minimális számát határozza meg.|
|**Inaktív percek száma az eszköz zárolásáig**|Az eszköz az itt megadott számú felhasználói tevékenység nélküli perc elteltével automatikusan zárolja magát.|
|**Intelligens zárolás és más megbízhatósági ügynökök engedélyezése**<br>(Android 6 és újabb verziók)|A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van, például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.|
|**Sikertelen bejelentkezések száma a munkahelyi profil eltávolítása előtt**|Megadja, hogy hány sikertelen bejelentkezés legyen megengedett, mielőtt az eszközön található munkaprofil el lenne távolítva. Ez nem hajt végre teljes törlést az eszközön.|
|**Jelszóelőzmények megjegyzése**|Letiltja a korábban használt jelszavak ismételt használatát.|
|**Korábbi jelszavak megjegyzése** - **Korábbi jelszavak újbóli használatának tiltása**|Megadja, hogy az eszköz hány korábban használt jelszót jegyezzen meg.|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.|
|**Ujjlenyomattal történő zárolásfeloldás engedélyezése**<br>(Android 6 és újabb verziók)|Lehetővé teszi az eszközök ujjlenyomattal történő zárolásfeloldását, ha az eszköz támogatja ezt a funkciót.|


### <a name="work-profile-settings"></a>Munkahelyi profil beállításai

|Beállítás neve|Részletek|
|----------------|-|
|**A munkahelyi és a személyes profilok közötti adatmegosztás engedélyezése**|Lehetővé teszi a munkahelyi profilban és a felhasználók személyes profiljában található alkalmazások közötti adatmegosztást. A következő lehetőségek közül választhat:<br><br>- **Határokon keresztüli megosztás letiltása**<br>- **A munkahelyi profilban szereplő alkalmazások kezelhetik a személyes profiltól érkező megosztási kérést**<br>- **Nincs megosztási korlátozás**|
|**Munkahelyi profil értesítéseinek elrejtése, ha az eszköz zárolva van**<br>(Android 6 és újabb verziók)|Szabályozza a munkahelyi profiltól érkező értesítések láthatóságát, ha az eszköz zárolva van.|
|**Alapértelmezett alkalmazásengedélyezési szabályzat beállítása**<br>(Android 6 és újabb verziók)|Meghatározza a munkahelyi profilban található összes alkalmazásra vonatkozó alapértelmezett szabályzatot.|


## <a name="custom-policy-settings"></a>Egyéni szabályzatbeállítások
A Microsoft Intune **Android for Work egyéni konfigurációs szabályzatával** OMA-URI-beállításokat léptethet érvénybe, amelyekkel vezérelhetők az Android for Work-eszközökön elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a képességgel olyan Android-beállításokat telepíthet, amelyek nem konfigurálhatók Intune-szabályzatokkal.
Az Intune jelenleg csak korlátozott számú egyéni Android-szabályzatot támogat. E témakör példái alapján megtudhatja, mely szabályzatokat lehet konfigurálni.

### <a name="general-settings"></a>Általános beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    |**Név**|Adjon egyedi nevet az egyéni Android-szabályzatnak, hogy az azonosítható legyen az Intune konzolján.|
    |**Leírás**|Adjon meg egy leírást, amely áttekintést nyújt az Android egyéni szabályzatáról, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.|

### <a name="oma-uri-settings"></a>OMA-URI-beállítások

   |Beállítás neve|Részletek|
    |--------|--------------------|
    |**A beállítás neve**|Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.|
    |**A beállítás leírása**|Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.|
    |**Adattípus**|Válassza ki az adattípust az OMA-URI-beállítás megadásához. A **Karakterlánc, Karakterlánc (XML), Dátum és idő, Egész szám, Lebegőpontos szám** vagy **Logikai** lehetőségek közül választhat.|
    |**OMA-URI (megkülönbözteti a kis- és nagybetűket)**|Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.|
    |**Érték**|Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket.|

### <a name="examples"></a>Példák

- [Wi-Fi-profil létrehozása előmegosztott kulccsal](pre-shared-key-wi-fi-profile.md)
- [Egyéni szabályzat használata az Android-eszközök alkalmazásonkénti VPN-profiljainak létrehozásához](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Feb17_HO1-->


