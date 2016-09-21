---
title: "Az előfizetés beállítása a Lookout MTP használatára | Microsoft Intune"
description: "Ez a cikk az MTP konfigurálásának lépéseit ismerteti."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: 8e2c71127801afc21d52e08d13dd9099b263e801


---

# Az előfizetés beállítása a Lookout mobilfenyegetések elleni védelemhez
Az előfizetés Lookout MTP-szolgáltatáshoz való előkészítéséhez a Lookout-támogatásnak (enterprisesupport@lookout.com) az alábbi információkra lesz szüksége az Ön Azure Active Directory- (Azure AD-) előfizetéséről. 

* Az Azure AD-bérlő azonosítója
* Az Azure AD-csoportobjektum azonosítója a Lookout MTP teljes körű hozzáféréséhez a konzolhoz
* Az Azure AD-csoportobjektum azonosítója a Lookout MTP korlátozott hozzáféréséhez a konzolhoz (nem kötelező)

A következő szakaszban található információk segítenek összegyűjteni a Lookout-támogatás számára szükséges információkat.  

## Az Azure AD-adatok lekérdezése
### Az Azure AD-bérlő azonosítójának lekérdezése
Jelentkezzen be az Azure AD felügyeleti portálra: https://manage.windowsazure.com, és válassza ki az előfizetését. 

![képernyőkép az Azure AD-oldalról a bérlő nevével](../media/mtp/aad_tenant_name.png)Az előfizetés nevének kiválasztása után megjelenő URL-cím tartalmazza az előfizetés azonosítóját.  Ha problémát tapasztal az előfizetési azonosító lekérdezése közben, további információt talál ebben a [Microsoft-támogatási cikkben](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US).   
### Az Azure AD-csoportazonosító lekérdezése
A Lookout MTP-konzol két hozzáférési szintet támogat:  
* **Teljes hozzáférés:** Az Azure AD-rendszergazda létrehozhat egy csoportot teljes hozzáférésű felhasználók számára, és választhatóan egy korlátozott hozzáférésű felhasználókból álló csoportot is.  A **Lookout MTP-konzolba** csak ennek a két csoportnak a tagjai jelentkezhetnek be.
* **Korlátozott hozzáférés:** a Lookout MTP-konzol több konfigurációs és regisztrációval kapcsolatos moduljához nincs hozzáférésük; csak olvasási hozzáférés a Lookout MTP-konzol **Biztonsági szabályzat** moduljához.  

Az engedélyekről további információt talál a Lookout-webhelyen, [ebben a cikkben](https://personal.support.lookout.com/hc/en-us/articles/114094105653).

A **Csoportobjektum azonosítója** az Azure AD felügyeleti konzolján, a csoport Tulajdonságok lapján található.

![a tulajdonságok lap képernyőképe a csoportazonosító mező kiemelésével](../media/mtp/aad_group_object_id.png)

Miután kigyűjtötte ezeket az információkat, lépjen kapcsolatba a Lookout támogatási szolgálatával (e-mail: enterprisesupport@lookout.com).

A Lookout támogatási szolgálat a megadott információkat felhasználva, az elsődleges kapcsolattartóval együttműködve előkészíti az előfizetést, és elkészíti a vállalati MTP-fiókot.


## Az előfizetés konfigurálása a Lookout MTP használatához
### 1. lépés: az MTP beállítása
Miután a Lookout támogatási szolgálata létrehozta a vállalati Lookout MTP-fiókot, bejelentkezhet a Lookout MTP-konzolba.   A Lookout e-mailben küldi el a bejelentkezési URL-címet a vállalat elsődleges kapcsolattartójának címére: https://aad.lookout.com/les?action=consent

A Lookout MTP-konzolra való első bejelentkezésnél egy Azure AD-szerepkörű globális rendszergazdai felhasználói fiókkal kell bejelentkezni, mert a Lookout MTP ezt követeli meg az Azure AD-bérlő regisztrálásához.   A későbbi bejelentkezéseknél nem szükséges ezt a szintű Azure AD-jogosultságot használni.  Az első bejelentkezésnél egy hozzájárulást kérő lap jelenik meg. A regisztráció befejezéséhez válassza az **elfogad** lehetőséget.

![képernyőkép a Lookout MTP-konzolra való első belépésről](../media/mtp/lookout_mtp_initial_login.png) A hozzájárulás és beleegyezés után a rendszer átirányítja a Lookout MTP-konzolra. A regisztráció elvégzése után a későbbiekben ezen az URL-címen jelentkezhet be: https://aad.lookout.com

Bejelentkezési problémák esetén olvassa el a [hibaelhárításról szóló cikket](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

A következőkben azokat a lépéseket mutatjuk be, amelyeket a Lookout MTP telepítéséhez el kell végezni a [Lookout MTP-konzolon](https://aad.lookout.com).

### 2. lépés: az Intune-összekötő konfigurálása

A Lookout MTP-konzolon lépjen a **System** (Rendszer) modulba, válassza a **Connectors** (Összekötők) lapot, majd az **Intune** lehetőséget.

![képernyőkép a Lookout MTP-konzolról, amelyen az összekötők lap meg van nyitva, az Intune lehetőség pedig ki van emelve](../media/mtp/lookout_mtp_setup-intune-connector.png)

A kapcsolat beállítása lehetőségnél állítsa be a szívverés percenkénti gyakoriságát.  Ha ezzel elkészült, az Intune-összekötő használatra készen áll.  

![képernyőkép a kapcsolat beállítása lapról, amin a szívverés gyakorisága már konfigurálva van](../media/mtp/lookout-mtp-connection-settings.png)

### 3. lépés: regisztrációs csoportok konfigurálása
A **Regisztrációkezelés** lehetőséget választva adja meg azoknak a felhasználóknak a csoportját, akiknek az eszközei regisztrálva lesznek a Lookout-ban.   Tesztelési célok miatt ajánlatos először egy kisebb csoportot definiálni, így könnyebben megismerkedhet az integráció működésével.  Ha a tesztelés után mindent rendben talál, a regisztrációt kiterjesztheti újabb felhasználói csoportokra is.

A regisztrációs csoportok kezeléséhez első lépésként adjon meg egy Azure AD biztonsági csoportot, amely kiindulásként jól használható a Lookout MTP-ben való regisztrációhoz. Miután létrehozta a csoportot az Azure AD-ban, a Lookout MTP-konzolon válassza a **Regisztrációkezelés** lehetőséget, és adja meg az Azure AD biztonsági csoport **Megjelenített nevét/neveit** a regisztrációhoz.

Ha egy felhasználó tagja egy regisztrációs csoportnak, akkor az Azure AD által támogatott és azonosított minden eszköze regisztrálható és aktiválható a Lookout MTP-ben.  Az eszköz akkor kerül aktiválásra a Lookout MTP-ben, amikor a felhasználó először nyitja meg a Lookout for Work alkalmazást a támogatott eszközön.
![képernyőkép az Intune-összekötő regisztrálási oldaláról](../media/mtp/lookout-mtp-enrollment.png)

Az új eszközök keresésének gyakorisága értéknél javasolt megtartani az alapértelmezett 5 perces beállítást.

>[!IMPORTANT]
> A megjelenítendő névben különbséget kell tenni a kis- és nagybetűk között.  A **Megjelenített névnél** használja azt a formát, amely az Azure portálon a biztonsági csoport **Tulajdonságok** lapján látható. Amint az alábbi képen látható, a biztonsági csoport **Tulajdonságok** lapján a megjelenített névben nagybetűs szavak szerepelnek.  A címsorban azonban csupa kisbetű szerepel – ezt a formát ne használja a Lookout MTP-konzolon.
>![képernyőkép az Azure portálról, az Azure Active Directory szolgáltatás tulajdonságok lapjáról](../media/mtp/aad-group-display-name.png)

A jelenlegi verzió az alábbi korlátozásokat tartalmazza:  
* A csoport megjelenítendő nevénél nem történik ellenőrzés.  Fontos, hogy azt az értéket használja, amely az Azure Portalon az Azure AD biztonsági csoportjának **MEGJELENÍTETT NÉV** mezőjében látható.
* Csoporton belüli csoport létrehozása jelenleg nem támogatott.  A megadott Azure AD biztonsági csoportok csak felhasználókat tartalmazhatnak, beágyazott csoportokat nem.


### 4. lépés: az állapotszinkronizálás konfigurálása
Az **Állapotszinkronizálás** lehetőségnél adja meg az Intune-ba küldendő adattípusokat.  A Lookout és az Intune integrációjának megfelelő működéséhez jelenleg az eszközállapotot és a fenyegetések állapotát egyaránt engedélyeznie kell.  Alapértelmezés szerint ezek engedélyezve vannak.
### 5. lépés: e-mail-címzettek adatainak konfigurálása hibajelentésekhez
A **Hibakezelés** lehetőségnél írja be azt az e-mail címet, amelyre a hibajelentéseket szeretné irányítani.

![képernyőkép az Intune-összekötő hibakezelési oldaláról](../media/mtp/lookout-mtp-connector-error-notifications.png)

### 6. lépés: e-mail értesítések konfigurálása
Ha e-mail értesítéseket szeretne kapni a fenyegetésekről, jelentkezzen be a [Lookout MTP-konzolba](https://aad.lookout.com) azzal a felhasználói fiókkal, amelyre az értesítéseket szeretné kapni.  Lépjen be a **Rendszer** modulba, majd a **Beállítások** lapon a kívánt értesítések melletti kapcsolót állítsa **BE** értékre. Mentse a változtatásokat.

![képernyőkép a beállítások lapról a felhasználói fiókkal](../media/mtp/lookout-mtp-email-notifications.png) Ha már nem szeretne email értesítéseket kapni, állítsa az értesítés típusa melletti kapcsolót **KI** értékre.
### 7. lépés: a fenyegetések besorolásának konfigurálása
A Lookout MTP a különféle fenyegetési típusokat osztályokba sorolja. A [Lookout MTP fenyegetési besorolásban](http://personal.support.lookout.com/hc/en-us/articles/114094130693) a fenyegetésekhez alapértelmezett kockázati szintek tartoznak. Ezek bármikor módosíthatók a vállalat igényeinek megfelelően.

![képernyőkép a szabályzat oldaláról a fenyegetések besorolásával](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Az itt meghatározott kockázati szintek az MTP fontos elemét jelentik, mert az Intune-integráció az eszköz megfelelőségét az itt meghatározott kockázati szintek alapján számítja ki futásidőben. Vagyis az Intune-rendszergazda állítja be a szabályzatban, hogy egy eszköz akkor nem megfelelő, ha egy olyan aktív fenyegetés található rajta, amelynek a szintje: magas, közepes vagy alacsony. Az MTP fenyegetésbesorolási szabályzata határozza meg közvetlenül az eszközmegfelelőségi értékelést az Intune-ban.

## A regisztráció figyelése
A telepítés befejezése után a Lookout MTP elkezdi lekérdezni az Azure AD-ből azokat az eszközöket, amelyek megfelelnek a megadott regisztrációs csoportoknak.  A regisztrált eszközök adatai az Eszközök modulban találhatók.  Az eszközök kezdeti állapota mindig „folyamatban” lesz.  Az eszközállapot akkor frissül, ha a Lookout for Work alkalmazás az illető eszközön telepítve lett, megnyitották és aktiválták azt.  A Lookout for Work alkalmazás eszközökre való elküldéséről további információt talál a [Lookout for Work alkalmazás konfigurálása és telepítése](configure-and-deploy-lookout-for-work-apps.md) című témakörben.
## További lépések
[Lookout MTP-kapcsolat engedélyezése az Intune-ban](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO2-->


