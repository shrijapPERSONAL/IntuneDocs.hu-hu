---
title: "Windowsos szabályzatbeállítások | Microsoft Intune"
description: "A Microsoft Intune Windows-eszközökhöz készült általános konfigurációs házirendjét (Windows 8.1 és újabb verziók) regisztrált Windows 8.1- és Windows 8-eszközökhöz használhatja."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 073e3df63a5de9cf92c739c1ced858e21a9ac351
ms.openlocfilehash: 6b2d805561067d2dc0de70d93c45622a951e5981


---

# Windowsos szabályzatbeállítások a Microsoft Intune-ban
A Microsoft Intune **Windows-eszközökhöz készült általános konfigurációs szabályzatával (Windows 8.1 és újabb verziók)** a következő beállításokat konfigurálhatja a regisztrált Windows 8- és Windows 8.1-eszközökhöz:

## Alkalmazhatósági beállítások

|Beállítás neve|Részletek|
|----------------|----------------------------------|
|**Az összes konfiguráció alkalmazása a Windows 10-re**|Ezzel a beállítással lehetővé teszi, hogy a szabályzatban szereplő beállítások a rendszer Windows Phone 8- és 8.1-eszközökön felül a Windows 10-eszközökre is alkalmazhatók legyenek.|

## Biztonsági beállítások

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|------|----------------------------|--------------|
|**Kötelező jelszótípus**|Meghatározza a megkövetelt jelszótípust, például hogy a jelszó számokat és betűket is, vagy csak számokat tartalmazhat.|Igen|Igen|
|**Megkövetelt jelszótípus – a karakterkészletek minimális száma**|Azt határozza meg, hány különböző karakterkészletnek kell szerepelnie a jelszóban. A következő négy karakterkészlet létezik: kisbetűk, nagybetűk, számok és szimbólumok. iOS-eszközök esetén azonban ez a beállítás azt határozza meg, hány szimbólumnak kell szerepelnie a jelszóban.|Igen|Igen|
|**Jelszó minimális hossza**<sup>1</sup>|Konfigurálja a jelszó minimális hosszát (karakterszámát).|Igen|Igen|
|**Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt**|A megadott számú sikertelen bejelentkezési kísérlet után törli az eszközt.|Igen|Igen|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Azt állítja be, hogy az eszköz hány perc tétlenség után kérjen jelszót a zárolás feloldásához.| Igen|Igen|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.|Igen|Igen|
|**Jelszóelőzmények megjegyzése**|Ez a beállítás azt határozza meg, hogy a felhasználó beállíthat-e általa korábban már használt jelszavakat.|Igen|Igen|
|**Korábbi jelszavak megjegyzése** – **Korábbi jelszavak újbóli használatának tiltása**|Ez a beállítás az eszköz által megjegyzett korábbi jelszavak számát határozza meg.|Igen|Igen|
|**Képjelszó és PIN-kód engedélyezése**|Engedélyezi a képjelszó és a PIN-kód használatát. A képjelszó segítségével a felhasználó egy képre rajzolt kézmozdulatokkal jelentkezhet be. A PIN-kód gyors bejelentkezést tesz lehetővé egy négyjegyű kóddal.|Igen|Igen|
<sup>1</sup> Ha Windows RT rendszerű eszközökre beállítja a jelszóhosszúságra vonatkozó házirend alkalmazását, a rendszer a felhasználókat a jelszavuk módosítására kényszeríti, még akkor is, ha az aktuális jelszó megfelel a házirend követelményeinek.

## Titkosítási beállítások

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**Titkosítás megkövetelése mobileszközön**<sup>1</sup>|Az eszközön található összes fájlnak titkosítva kell lennie.<br>A Windows Phone 8-telefonokon ezt **Igen**értékre kell állítani.|Igen|Nem|
<sup>1</sup> További információ a Windows 8.1 rendszerű eszközökhöz

-   A Windows 8.1 rendszerű eszközökön a titkosítás kényszerítéséhez minden egyes eszközön telepíteni kell a következőt: [2014. decemberi MDM-ügyfélfrissítés Windows rendszerre](http://support.microsoft.com/kb/3013816) .

-   Ha engedélyezi ezt a beállítást a Windows 8.1 rendszerű eszközökön, az eszköz valamennyi felhasználójának rendelkeznie kell Microsoft-fiókkal.

-   A titkosítás működéséhez az eszköznek teljesítenie kell a Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardvertanúsítvány követelményeit.

-   Amikor kényszeríti az eszközön a titkosítást, a helyreállítási kulcs csak a felhasználó OneDrive-fiókon keresztül elérhető Microsoft-fiókjából érhető el. Ez a kulcs nem állítható vissza egy felhasználó nevében.

## Kártevőkre vonatkozó beállítások

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**Hálózati tűzfal megléte szükséges**|Előírja a Windows tűzfal bekapcsolását.|Igen|Nem|
|**SmartScreen engedélyezése**|Kötelezővé teszi a Windows SmartScreen használatát.|Igen|Nem|

## Rendszerbeállítások

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|-------|---------------------------|--------------|
|**Automatikus frissítés szükséges**|Aktiválja az automatikus frissítési beállítást az eszközökön.|Igen|Nem|
|**Automatikus frissítés szükséges – Az automatikusan telepített frissítések legalacsonyabb besorolása**|Kiválasztja az automatikusan telepített frissítések besorolását:<br /><br />-   **Fontos** – Minden fontosként megjelölt frissítést telepít.<br />-   **Ajánlott** – Minden fontosként vagy ajánlottként megjelölt frissítést telepít.|Igen|Nem|
|**Felhasználói fiókok felügyelete**|Kötelezővé teszi a felhasználói fiókok felügyeletének használatát az eszközökön.|Igen|Nem|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezése esetén az eszköz diagnosztikai adatokat küld a Microsoftnak.|Igen|Nem|


## Felhőbeállítások – dokumentumok és adatok

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|------|----------------------------|--------------|
|**Munkahelyi mappák URL-címe**|Beállítja a munkahelyi mappa URL-címét, hogy lehetővé tegye a dokumentumok az eszközök közötti szinkronizálását.|Igen|Nem|

## E-mail beállítások

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**A Microsoft-fiók opcionálissá tétele a Windows Mail alkalmazásban**|Microsoft-fiók nélkül is hozzáférhetővé teszi a Windows Posta alkalmazást.|Igen|Nem|

## Alkalmazásbeállítások – böngésző

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|-----|-----------------------------|--------------|
|**Automatikus kitöltés engedélyezése**|Engedélyezi a felhasználók számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását.|Igen|Nem|
|**Előugróablak-blokkoló engedélyezése**|A böngésző előugróablak-blokkolójának engedélyezése vagy letiltása.|Igen|Nem|
|**Beépülő modulok engedélyezése**|Engedélyezi a felhasználók számára, hogy beépülő modulokat adjanak hozzá az Internet Explorerhez.|Igen|Nem|
|**Active Scripting engedélyezése**|Engedélyezi, hogy a böngésző parancsfájlokat futtasson (például Active X- parancsfájlok).|Igen|Nem|
|**Csalás elleni figyelmeztetés engedélyezése**|Engedélyezi vagy letiltja a potenciálisan rosszindulatú webhelyekről szóló figyelmeztetéseket.|Igen|Nem|
|**Intranetes hely engedélyezése egyetlen szó beírásakor**|Engedélyezi, hogy egyetlen szó, például a „Bing” használatával az Internet Explorert webhelyekre lehessen irányítani.|Igen|Nem|
|**Intranet hálózat automatikus észlelésének engedélyezése**|Segít az intranetes webhelyek biztonságának konfigurálásában az Internet Explorerben.|Igen|Nem|
|**Internet zóna biztonsági szintje**|Az Internet Explorer internetes webhelyekre vonatkozó biztonsági szintjét állítja be.|Igen|Nem|
|**Intranet zóna biztonsági szintje**|Az Internet Explorer intranetes webhelyekre vonatkozó biztonsági szintjét állítja be.|Igen|Nem|
|**Megbízható helyek zóna biztonsági szintje**|A megbízható helyek zóna biztonsági szintjét állítja be.|Igen|Nem|
|**Tiltott helyek zóna biztonsági szintje**|A tiltott helyek zóna biztonsági szintjét állítja be.|Igen|Nem|
|**Do Not Track (Nyomkövetés tiltása) fejléc küldése**|A nyomkövetést tiltó fejlécet küld az Internet Explorerben a felkeresett webhelyeknek.|Igen|Nem|
|**Vállalati üzemmód menü elérések engedélyezése**|Lehetővé teszi, hogy a felhasználók férhetnek hozzá a vállalati üzemmód menü beállítások Internet Explorer programból.<br>Engedélyezése esetén meghatározhatja a **Naplózási jelentés helyét** is, ahol megtalálható annak a jelentésnek az URL-címe, amely megjeleníti azokat a webhelyeket, amelyekhez a felhasználók bekapcsolták a vállalati üzemmódot.|Igen|Nem|
|**Vállalati üzemmód webhelylistájának helye**|Azon webhelyek listájának helyét adja meg, amelyek a Vállalati üzemmódot használják, ha az aktív.|Igen|Nem|

## Eszközképességek beállításai – mobilhálózat

|Beállítás neve|Részletek|Windows 8.1 és Windows RT 8.1|Windows RT|
|----------------|----|------------------------------|--------------|
|**Adatroaming használatának engedélyezése**|Adatroaming használatát engedélyezi, ha az eszköz mobilhálózathoz csatlakozik.|Igen|Nem|



### További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Sep16_HO2-->


