---
title: "Migrálás Azure Active Directory-csoportokba| Microsoft Intune"
description: "A csoportok migrálása az Intune-ból az Azure AD-be"
keywords: 
author: nbigman
manager: angerobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: d7a1da3b9e1e6ce3e2034cc5e8e1926a671276b8
ms.openlocfilehash: f7aa05f4a569392be60522437508fdb78f56c55c


---

## A csoportok kezelésére szolgáló új rendszergazdai felület
    
A felhasználók jelezték, hogy egységes csoportosítási és célcsoport-kezelési felületet szeretnének az Enterprise Mobility & Security egészéhez, ezért az Intune-csoportokat átalakítjuk Azure Active Directory-alapú biztonsági csoportokká. Ez egységesíti a csoportfelügyeletet az Intune és az Azure Active Directory (Azure AD) egészében. Az új felület jóvoltából a jövőben nem kell csoportokat duplikálni a szolgáltatások között, és támogatott lesz PowerShell- és a Graph-alapú bővíthetőség is. 

Novemberben az elkezdődik a meglévő Intune-ügyfelek migrálása az új, Azure AD-alapú csoportfelügyeleti rendszerbe. A felhasználó- és eszközcsoportok mindegyikét át fogjuk telepíteni az Azure AD-alapú biztonsági csoportokba. Mindaddig nem kezdjük meg a migrálást, amíg nem sikerül minimalizálni annak hatását a napi munkára, és nem biztosított, hogy a végfelhasználók semmiféle hatást ne érzékeljenek. A fiókjuk áttelepítését megelőzően is küldünk értesítést.

### Hogyan és mikor kerülök át az új csoportkezelési rendszerbe?
A meglévő ügyfelek migrálása nem azonnal, hanem folyamatosan történik. A migrálás ütemezését jelenleg véglegesítjük, és néhány héten belül további információkkal frissítjük ezt a témakört. A migrálás előtt értesíteni fogjuk. Ha bármilyen kérdése vagy problémája van a migrálással kapcsolatban, kérjük, forduljon a migrálási csapathoz az [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com) címen.

### Milyen új funkciókat érhetek el?
A bevezetésre kerülő új funkciók: 
 
-    Az Intune minden telepítéstípus esetében támogatni fogja az Azure AD-alapú biztonsági csoportokat. 
-    Az Azure AD-alapú biztonsági csoportok támogatni fogják az eszközök csoportosítását a felhasználók csoportosításával együtt.
-    Az Azure AD-alapú biztonsági csoportok támogatni fogják az Intune-eszközattribútumokkal rendelkező dinamikus csoportokat. Lehetséges lesz többek között platform (például iOS) alapján dinamikusan csoportosítani az eszközöket. Így amikor új iOS-eszközt regisztrálnak a szervezetnél, az automatikusan hozzáadódik az iOS dinamikus eszközcsoporthoz.
-    Egységes csoportfelügyelet az Azure AD-ben és az Intune-ban.
- Az Azure AD-be bekerül az *Intune-szolgáltatásadminisztrátor* szerepkör, így az Intune szolgáltatásadminisztrátorai az Azure AD-ben is végrehajthatnak csoportfelügyeleti feladatokat.

 
### Mely Intune-funkciók nem lesznek elérhetők?
Jóllehet a csoportfelügyelet minősége javulni fog, vannak olyan Intune-funkciók, amelyek a migrálás után elérhetetlenné válnak.

#### Csoportfelügyeleti funkciók

-   Új csoport létrehozásakor nem lesz lehetséges tagok vagy csoportok kizárása. Az Azure AD-alapú dinamikus csoportok ugyanakkor lehetővé teszik, hogy attribútumok alkalmazásával speciális szabályokat alakítson ki bizonyos tagok feltételalapú kizárására. Létrehozhat például egy olyan speciális szabályt, amely egyetlen biztonsági csoportba foglalja a Sales osztály minden munkatársát, kivéve azokat, akiknek a beosztásában szerepel az „Assistant” szó. Ezt a következő szabállyal érheti el: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. További tájékoztatást az [Attribútumok használata speciális szabályok létrehozására](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) című cikkben olvashat.
-   A **Nem csoportosított felhasználók** és a **Nem csoportosított eszközök** csoportjai nem támogatottak. Ezek csoportok nem kerülnek migrálásra.

#### Csoportfüggő funkciók

-   A Szolgáltatásadminisztrátor szerepkör nem rendelkezik majd **Csoportok kezelése** engedéllyel.
-   Az Exchange ActiveSync-eszközök nem lesznek csoportosíthatók.  A **Minden EAS által kezelt eszköz** csoport csoportnézetből jelentésnézetté alakul.
-  A jelentésekben nem lesz elérhető a csoportok alapján történő kimutatás.
-  Az értesítési szabályok egyedi csoportcélzási lehetősége megszűnik.

### Hogyan készüljek fel a változásra?
 A következőket ajánljuk a zökkenőmentes átállás érdekében:
 
- A migrálás előtt töröljön minden olyan Intune-csoportot, amelyre nincs szüksége.
- Vizsgálja felül a csoportokból való kizárás eddigi használatát, és próbálja meg úgy átalakítani a csoportokat, hogy a jövőben ne legyen szüksége erre a funkcióra, vagy úgy, hogy speciális szabályokkal el tudja érni ugyanezt a célt.
-  Ha vannak olyan rendszergazdák, akik számára nem engedélyezett csoportok létrehozása az Azure AD-ben, kérje meg Azure AD-rendszergazdáját, hogy adja hozzá őket az **Intune-szolgáltatásadminisztrátor** Azure AD-szerepkörhöz.

Az Azure AD biztonsági csoportjairól is tájékozódhat részletesebben:
-  Áttekintést szerezhet [Az erőforrásokhoz való hozzáférés kezelése Azure Active Directory-csoportokkal](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/) című cikkből.
-  Az Azure AD-csoportok létrehozásáról és kezeléséről a [Csoportkezelés az Azure Active Directoryban](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/) című cikk nyújt tájékoztatást.
-  A biztonsági csoportokra vonatkozó speciális szabályokról az [Attribútumok használata speciális szabályok létrehozására](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) című cikkben olvashat további tájékoztatást.

> [!NOTE]
Feltűnhetett, hogy az Azure AD biztonsági csoportok nem tárgyalják az eszközök számára történő csoportlétrehozást. Ezt a funkciót azt megelőzően fogjuk engedélyezni az Azure AD-ben, hogy elkezdődik az Intune-csoportok migrálása.

## A migrálás részletei
Az alábbiakban bemutatjuk, hogyan fog lezajlani az Intune-csoportoknak az Azure AD biztonsági csoportokba való migrálása.

### A meglévő csoportok migrálása

| Forrás Intune-csoport|Cél Azure AD biztonsági csoport|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Intune-szabályzattal megcélzott statikus felhasználócsoportok|Ugyanazokat a felhasználókat tartalmazó statikus Azure AD biztonsági csoportok|
|Intune-szabályzattal megcélzott dinamikus felhasználócsoportok|Statikus Azure AD biztonsági csoportok Azure AD biztonságicsoport-hierarchiával|
|Intune-szabályzattal megcélzott statikus eszközcsoportok|Eszközöket tartalmazó statikus Azure AD biztonsági csoportok|
|Eszközattribútumokat tartalmazó dinamikus eszközcsoportok, amelyeket Intune-szabályzatok céloznak|Eszközattribútumokat tartalmazó dinamikus Azure AD biztonsági csoportok|
|Belefoglalási feltételt tartalmazó csoport|Külön statikus Azure AD biztonsági csoport, amely tartalmaz egy csoportot, továbbá az olyan statikus/dinamikus tagokat, amelyeket a belefoglalási feltétel engedélyezett az Intune-ban|
|Kizárási feltételt tartalmazó csoport|Nem történik meg a migrálása. A kizáró feltételek nem támogatottak a statikus csoportok Azure AD-ben történő létrehozásakor. Akkor használhat kizáró feltételt, ha dinamikus csoportot hoz létre az Azure AD-ben.|
|Minden olyan alapértelmezett csoport (**Minden felhasználó**, **Nem csoportosított felhasználók**, **Minden eszköz**, **Nem csoportosított eszközök**, **Minden számítógép**, **Minden mobileszköz**, ** MDM által felügyelt eszközök** és ** EAS által felügyelt eszközök**), amelyet az Intune-szabályzatokban használ  |Azure AD biztonsági csoportok. A nem használt alapértelmezett csoportokat szükség szerint, dinamikus csoportok létrehozásával kell létrehoznia az ügyfélnek.|

### A hierarchikus nézetek változásai
Az Intune hierarchikus nézetcsoportjai. Az Intune-ban a szülő-gyermek viszony halmaz-részhalmaz viszony volt, az Azure AD-ben azonban ez másképpen van. A gyermeknek lehetnek olyan tagjai, amelyek nem voltak tagjai a szülőnek. Az Azure AD-ben ciklikusak is lehetnek a csoportok, vagyis egy szülőcsoport lehet gyermeke egy gyermekcsoportnak.

### Az attribútumok konvertálása a migráció során
Az attribútumok a csoportok definiálása során felhasználható eszköztulajdonságok. Ez a táblázat bemutatja, hogyan fog történni ezeknek a feltételeknek az Azure AD-alapú biztonsági csoportokba való migrálása.

| Intune-attribútum|Azure AD-attribútum|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Eszközcsoportok szervezeti egység (OU) attribútuma|Dinamikus csoportok OU attribútuma. Úgy tesszük elérhetővé az attribútumértékeket az egyes bérlők rendszergazdái számára, hogy felvesszük őket megtekintésre a bérlő egyik összetevőjeként.|
|Eszközcsoportok Tartománynév attribútuma|Dinamikus csoportok Tartománynév attribútuma. Úgy tesszük elérhetővé az attribútumértékeket az egyes bérlők rendszergazdái számára, hogy felvesszük őket megtekintésre a bérlő egyik összetevőjeként|
|Biztonsági csoport mint a felhasználócsoportok attribútuma|A csoportok nem lehetnek attribútumok az Azure AD dinamikus lekérdezéseiben. A dinamikus csoportok csak felhasználó- vagy eszközspecifikus attribútumokat tartalmazhatnak.|
|A felhasználócsoportok Manager (Kezelő) attribútuma|A *manager* (kezelő) attribútumra vonatkozó speciális szabály dinamikus csoportokban|
|A szülő felhasználócsoport minden felhasználója|Statikus csoport, amelynek ez a csoport a tagja|
|A szülő eszközcsoport minden mobileszköze|Statikus csoport, amelynek ez a csoport a tagja|
|A Microsoft Intune közvetlen kezelése alatt álló összes mobileszköz|Egy dinamikus csoport Management Type (Kezelés típusa) attribútumának „MDM” értéke|
|Az EAS által kezelt összes mobileszköz|Az EAS-eszközök nem foglalhatók csoportba az Azure AD-ben. A **Minden EAS által kezelt eszköz** csoport csoportnézetből jelentésnézetté alakul.|
|Statikus csoportokba ágyazott csoportok |Statikus csoportokba ágyazott csoportok|
|Dinamikus csoportokba ágyazott csoportok|Egy beágyazott szintet tartalmazó dinamikus csoport|


## Szabályzatok migrálása
A csoportmigráció során továbbra is az Intune konzolon kezelheti a szabályzatokat. Az Intune konzolon látható lesz egy az Azure felügyeleti konzolra mutató hivatkozás, arra kattintva kezelheti a csoportokat. A szabályzatok továbbra is alkalmazva lesznek az Intune-csoportokkal párhuzamos, migrált Azure AD-csoportokra.

Amikor befejeződik az Intune minden funkciójának az Azure felügyeleti portáljára történő migrálása (körülbelül 2017 első negyedévére), ott fogja kezelni a szabályokat és a csoportokat is.

     
### További információ
[Az erőforrásokhoz való hozzáférés kezelése Azure Active Directory-csoportokkal](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Csoportkezelés az Azure Active Directoryban](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Attribútumok használata speciális szabályok létrehozására](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Sep16_HO4-->


