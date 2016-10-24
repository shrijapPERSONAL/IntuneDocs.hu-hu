---
title: "A Microsoft Intune-műveletek értelmezése jelentések segítségével | Microsoft Intune"
description: "Jelentéseket hozhat létre a szervezetében lévő szoftverekről, hardverekről és szoftverlicencekről, majd kezelheti őket."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 936989a19c836c558efc43e3778180d5d4a8fb7a
ms.openlocfilehash: e6b81b1bfb53f0a85d5550b7a25ece1b948afeb6



---

# A Microsoft Intune-műveletek értelmezése jelentések segítségével
Ebből a témakörből megtudhatja, hogy miképpen hozhat létre és kezelhet Microsoft Intune-jelentéseket a szervezetében lévő szoftverekről, hardverekről és szoftverlicencekről.

## Using reports (A jelentések használata)
Az Intune-jelentések információkat nyújtanak a szervezetében lévő szoftverekről, hardverekről és szoftverlicencekről. Segítségükkel áttekintheti a szervezet aktuális szükségleteit, illetve felmérheti a jövőbeli kiadásokat. A jelentések létrehozásának és kezelésének eszközeit a **Jelentések** munkaterületen találhatja meg. 

### Jelentéstípusok

|Jelentés típusa|Leírás|
|---------------|---------------|
|**Update Reports**|A szervezet számítógépein sikeresen végrehajtott szoftverfrissítéseket jelenítik meg. Emellett megjelenítik a sikertelen, függőben lévő vagy szükséges frissítéseket is. A szoftverfrissítéssel kapcsolatos további információkért lásd: [Windows rendszerű számítógépek naprakészen tartása szoftverfrissítésekkel a Microsoft Intune-ban](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Észlelt szoftverekről szóló jelentés**|Megjeleníti a szervezete számítógépein telepített szoftvereket. Szoftververziók tartoznak. A megjelenített információkat a szoftver gyártója és kategóriája szerint szűrheti is. A listában lévő frissítések kibontásával, a listaelem mellett lévő iránymutató nyílra kattintva részletes információkat jeleníthet meg (például azokat a számítógépeket, amelyeken a frissítés telepítve van).<br /><br />Ha számítógépeket von ki vagy csoporttagságot módosít az Intune-ban, akkor több percig is eltarthat, mire a módosítások megjelennek az Észlelt szoftverek jelentésben. Ha szeretné, hogy a szoftverleltár a lehető legpontosabb legyen, akkor a számítógépek kivonása vagy a csoporttagságuk módosítása után várjon néhány percet, mielőtt az érintett számítógépeket magában foglaló jelentést készítene.|
|**Computer Inventory Reports**|Információkat jelenít meg a szervezetben lévő felügyelt számítógépekről. Ezzel a jelentéssel megtervezheti a hardvervásárlásokat, és jobban átláthatja a szervezeti felhasználók hardverszükségleteit. A felügyelt számítógépekkel folytatott munkáról bővebben a következő témakörben olvashat: [Windows rendszerű számítógépek felügyelete a Microsoft Intune-nal](manage-windows-pcs-with-microsoft-intune.md).|
|**Mobileszközkészlet-jelentések**|Információkat jelenít meg a szervezetben használt mobileszközökről. A megjelenített információkat szűrheti csoportok és operációs rendszerek szerint, illetve aszerint, hogy az eszköz jailbreakelt vagy rootolt-e.|
|**License Purchase Reports**|Megjeleníti az összes licencelt szoftvert a licencszerződés típusa szerint csoportosítva. Ha a szoftverlicencadatok több mint 24 órája nem frissültek, akkor a licencjelentés generálásakor frissíti őket a rendszer. A licencjelentés nem ad garantáltan pontos képet a használt szoftverekről, és nem használható szerződéses kötelezettségek teljesítésének igazolására. A jelentés egy olyan eszköz, amely segít a vállalat licenckezelési döntéseinek a meghozatalában. Előfordulhat, hogy az Intune nem észleli az összes olyan terméket, amelyre kiterjedhet a Microsoft mennyiségi licencprogramja. A rendelkezésre álló szűrők a következők:<br /><br />A **Minden szerződés** szűrő az Intune által kezelt összes licencelt szoftvert megjeleníti.<br /><br />A **Mennyiségi licencszerződések** szűrő csak a Mennyiségi licencszolgáltatási központ (VLSC) által kezelt szoftvertermékeket jeleníti meg.<br /><br />Az **Egyéb szoftverlicenc-szerződések** szűrő a VLSC-n kívül kezelt szoftvertermékeket jeleníti meg.|
|**License Installation Reports**|A vállalati számítógépeken telepített szoftvereket összehasonlítja a VLSC adatain alapuló vállalati licencjogosultságokkal. A szűrők a következők:<br /><br />A **Minden szerződés** szűrő az Intune által kezelt összes licencelt szoftvert megjeleníti.<br /><br />A **Mennyiségi licencszerződések** szűrő csak a mennyiségi licencszolgáltatási központ által kezelt szoftvertermékeket jeleníti meg.<br /><br />Az **Egyéb szoftverlicenc-szerződések** szűrő a VLSC-n kívül kezelt szoftvertermékeket jeleníti meg.|
|**Terms and Conditions Reports**|Megjeleníti, hogy a felhasználók elfogadták-e az alkalmazott használati feltételeket, és ha igen, akkor azok mely verzióját fogadták el. Legfeljebb 10 felhasználót adhat meg, akik esetében a rendszer megjeleníti a rájuk vonatkozó használati feltételek elfogadásának meglétét, vagy megjelenítheti egy rájuk vonatkozó konkrét feltétel elfogadási állapotát.|
|**Szabályzatoknak nem megfelelő alkalmazások – jelentések**|Információkat jelenít meg azokról a felhasználókról, akiknek olyan telepített alkalmazásaik vannak, amelyek szerepelnek az Ön megfelelő és meg nem felelő alkalmazásokat tartalmazó listáján. Ezzel a jelentéssel megtalálhatja azokat a felhasználókat és eszközöket, akik és amelyek nem felelnek meg a szervezete alkalmazás-házirendjeinek.|
|**Certificate Compliance Reports**|Megjeleníti, hogy mely tanúsítványok lettek kibocsátva a felhasználóknak és az eszközöknek az SCEP vagy PKCS #12 (.PFX) formátumban. Ezzel a jelentéssel megtalálhatja a kibocsátott, lejárt és visszavont tanúsítványokat.|
|**Device History Reports**|Megjeleníti a korábbi kivonási, tartalomtörlési és egyéb törlési műveletek naplóját. Ezzel a jelentéssel megállapíthatja, hogy korábban ki indított műveleteket az egyes eszközökön.|
|**Állapotigazolási jelentések**|Megjeleníti a mobileszközök állapotát.|
|**Mac OS X hardverjelentés**|Megjeleníti a kiválasztott csoportokban lévő összes regisztrált Mac OS X-alapú eszköz hardveres jellemzőit. Az eszközökről gyűjtött hardverleltárakkal kapcsolatos további információkért lásd: [A regisztrált eszközök áttekintése a Microsoft Intune leltárfunkciójával](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Mac OS X szoftverjelentés**|Megjeleníti a kiválasztott csoportokban lévő összes regisztrált Mac OS X-alapú eszközön telepített szoftvereket. A jelentés a szoftver nevét (csomagazonosítóként), a rövid (vagy valódi) nevet, a verziót és a szoftverrel telepített eszközök számát tünteti fel.|

#### Jelentés létrehozása

1.  Az Intune felügyeleti konzolon válassza a **Jelentések** lehetőséget. Ezután válassza ki a létrehozni kívánt jelentés típusát az előző táblázatban leírt módon.

2.  Az **Új jelentés létrehozása** lapon fogadja el az alapértelmezett értékeket, vagy szabja testre azokat a jelentés által visszaadott eredmények szűréséhez. Megadhatja például, hogy csak a Microsoft által kiadott szoftverek jelenjenek meg az Észlelt szoftverek jelentésében.

3.  Kattintson a **Jelentés megtekintése** lehetőségre a jelentés új ablakban való megnyitásához.

Ha rendezni szeretné a jelentést az egyik megjelenített oszlop alapján, kattintson az oszlop fejlécére. Ezenkívül egyes jelentésekben a listaelemek kibontásával is további információkhoz juthat.

## A jelentésekkel végezhető további műveletek
A fentiek mellett a jelentések az alábbi műveleteket támogatják:

|Művelet|További információ|
|----------|--------------------|
|**Nyomtatás**|A megnyitott jelentésben kattintson a nyomtatás ikonra, és kövesse az utasításokat.|
|**Exportálás**|A megnyitott jelentésben kattintson az exportálás ikonra, és kövesse az utasításokat. Az exportáláshoz választhat vesszővel tagolt (.csv) vagy HTML formátumot.|
|**Mentés**|Az **Új jelentés létrehozása** lapon minden egyes felhasználó menthet legfeljebb 100 jelentést. Állítsa be a jelentés kívánt paramétereit, majd kattintson a **Mentés** vagy, ha másik nevet szeretne használni, a **Mentés másként** lehetőségre.|
|**Betöltés**|A korábban elmentett jelentésparaméter-készletek betöltéséhez az **Új jelentés létrehozása** lapon válassza a **Betöltés** lehetőséget.|
|**Törlés**|A **Jelentések** munkaterületen válassza ki a kívánt jelentéstípust majd kattintson a **Betöltés** lehetőségre. Ezután a jelentések listáján kattintson a törlés (x) ikonra a jelentés mellett.|

### További információ
[Figyelés és jelentéskészítés a Microsoft Intune-ban](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


