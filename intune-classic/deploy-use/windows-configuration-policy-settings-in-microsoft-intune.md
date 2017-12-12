---
title: "Windowsos szabályzatbeállítások"
description: "A Microsoft Intune Windows-eszközökhöz készült általános konfigurációs házirendjét (Windows 8.1 és újabb verziók) regisztrált Windows 8.1- és Windows 8-eszközökhöz használhatja."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9fa8d8454e9d22b2d3c36cd6449805d709c34ffa
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2017
---
# <a name="windows-policy-settings-in-microsoft-intune"></a>Windowsos szabályzatbeállítások a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune **Windows-eszközökhöz készült általános konfigurációs szabályzatával (Windows 8.1 és újabb verziók)** a következő beállításokat konfigurálhatja a regisztrált Windows 8- , Windows 8.1- , és Windows RT 8.1-eszközökhöz:

## <a name="applicability-settings"></a>Alkalmazhatósági beállítások

|Beállítás neve|Részletek|
|----------------|----------------------------------|
|**Az összes konfiguráció alkalmazása a Windows 10-re**|Ezzel a beállítással lehetővé teszi, hogy a szabályzatban szereplő beállítások a rendszer Windows Phone 8- és 8.1-eszközökön felül a Windows 10-eszközökre is alkalmazhatók legyenek.|

## <a name="security-settings"></a>Biztonsági beállítások

|Beállítás neve|Részletek|
|----------------|------|
|**Kötelező jelszótípus**|Meghatározza a megkövetelt jelszótípust, például hogy a jelszó számokat és betűket is, vagy csak számokat tartalmazhat.|
|**Megkövetelt jelszótípus – a karakterkészletek minimális száma**|Azt határozza meg, hány különböző karakterkészletnek kell szerepelnie a jelszóban. A következő négy karakterkészlet létezik: kisbetűk, nagybetűk, számok és szimbólumok. iOS-eszközök esetén azonban ez a beállítás azt határozza meg, hány szimbólumnak kell szerepelnie a jelszóban.|
|**Jelszó minimális hossza**|Konfigurálja a jelszó minimális hosszát (karakterszámát).|
|**Ennyi ismétlődő sikertelen bejelentkezés után törlődnek végleg az adatok az eszközről**|A megadott számú sikertelen bejelentkezési kísérlet után törli az eszközt.|
|**Képernyő kikapcsolása ennyi perc inaktivitás után**|Azt állítja be, hogy az eszköz hány perc tétlenség után kérjen jelszót a zárolás feloldásához.|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.|
|**Jelszóelőzmények megjegyzése**|Ez a beállítás azt határozza meg, hogy a felhasználó beállíthat-e általa korábban már használt jelszavakat.|
|**Korábbi jelszavak megjegyzése** – **Korábbi jelszavak újbóli használatának tiltása**|Ez a beállítás az eszköz által megjegyzett korábbi jelszavak számát határozza meg.|
|**Képjelszó és PIN-kód engedélyezése**|Engedélyezi a képjelszó és a PIN-kód használatát. A képjelszó segítségével a felhasználó egy képre rajzolt kézmozdulatokkal jelentkezhet be. A PIN-kód gyors bejelentkezést tesz lehetővé egy négyjegyű kóddal.|

## <a name="encryption-settings"></a>Titkosítási beállítások

|Beállítás neve|Részletek|
|----------------|-----|
|**Titkosítás megkövetelése mobileszközön**<sup>1</sup>|Az eszközön található összes fájlnak titkosítva kell lennie.|
<sup>1</sup> További információ a Windows 8.1 rendszerű eszközökhöz

-   A Windows 8.1 rendszerű eszközökön a titkosítás kényszerítéséhez minden egyes eszközön telepíteni kell a következőt: [2014. decemberi MDM-ügyfélfrissítés Windows rendszerre](http://support.microsoft.com/kb/3013816) .

-   Ha engedélyezi ezt a beállítást a Windows 8.1 rendszerű eszközökön, az eszköz valamennyi felhasználójának rendelkeznie kell Microsoft-fiókkal.

-   A titkosítás működéséhez az eszköznek teljesítenie kell a Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardvertanúsítvány követelményeit.

-   Amikor kényszeríti az eszközön a titkosítást, a helyreállítási kulcs csak a felhasználó OneDrive-fiókon keresztül elérhető Microsoft-fiókjából érhető el. Ez a kulcs nem állítható vissza egy felhasználó nevében.

## <a name="malware-settings"></a>Kártevőkre vonatkozó beállítások

|Beállítás neve|Részletek|
|----------------|-----|
|**Hálózati tűzfal megkövetelése**|Előírja a Windows tűzfal bekapcsolását.|
|**SmartScreen engedélyezése**|Kötelezővé teszi a Windows SmartScreen használatát.|

## <a name="system-settings"></a>Rendszerbeállítások

|Beállítás neve|Részletek|
|----------------|-------|
|**Automatikus frissítések megkövetelése**|Aktiválja az automatikus frissítési beállítást az eszközökön.|
|**Automatikus frissítések megkövetelése – Az automatikusan telepített frissítések minimális besorolása**|Kiválasztja az automatikusan telepített frissítések besorolását:<br /><br />-   **Fontos** – Minden fontosként megjelölt frissítést telepít.<br />-   **Ajánlott** – Minden fontosként vagy ajánlottként megjelölt frissítést telepít.|
|**Felhasználói fiókok felügyelete**|Kötelezővé teszi a felhasználói fiókok felügyeletének használatát az eszközökön.|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezése esetén az eszköz diagnosztikai adatokat küld a Microsoftnak.|


## <a name="cloud-settings--documents-and-data"></a>Felhőbeállítások – dokumentumok és adatok

|Beállítás neve|Részletek|
|----------------|------|
|**Munkahelyi mappák URL-címe**|Beállítja a munkahelyi mappa URL-címét, hogy lehetővé tegye a dokumentumok az eszközök közötti szinkronizálását.|

## <a name="email-settings"></a>E-mail beállítások

|Beállítás neve|Részletek|
|----------------|-----|
|**A Microsoft-fiók használata nem kötelező a Windows Mail alkalmazásban**|Microsoft-fiók nélkül is hozzáférhetővé teszi a Windows Posta alkalmazást.|

## <a name="application-settings---browser"></a>Alkalmazásbeállítások – böngésző

|Beállítás neve|Részletek|
|----------------|-----|
|**Automatikus kitöltés engedélyezése**|Engedélyezi a felhasználók számára a böngésző automatikus kiegészítési funkciója beállításainak módosítását.|
|**Előugróablak-blokkoló engedélyezése**|A böngésző előugróablak-blokkolójának engedélyezése vagy letiltása.|
|**Beépülő modulok engedélyezése**|Engedélyezi a felhasználók számára, hogy beépülő modulokat adjanak hozzá az Internet Explorerhez.|
|**Active Scripting engedélyezése**|Engedélyezi, hogy a böngésző parancsfájlokat futtasson (például Active X- parancsfájlok).|
|**Csalás elleni figyelmeztetés engedélyezése**|Engedélyezi vagy letiltja a potenciálisan rosszindulatú webhelyekről szóló figyelmeztetéseket.|
|**Intranetes webhelyek engedélyezése egyszavas kereséshez**|Engedélyezi, hogy egyetlen szó, például a „Bing” használatával az Internet Explorert webhelyekre lehessen irányítani.|
|**Intranetes hálózatok automatikus felderítésének engedélyezése**|Segít az intranetes webhelyek biztonságának konfigurálásában az Internet Explorerben.|
|**Internetes biztonsági szint**|Az Internet Explorer internetes webhelyekre vonatkozó biztonsági szintjét állítja be.|
|**Intranetes biztonsági szint**|Az Internet Explorer intranetes webhelyekre vonatkozó biztonsági szintjét állítja be.|
|**Megbízható helyek biztonsági szintje**|A megbízható helyek zóna biztonsági szintjét állítja be.|
|**Tiltott helyek biztonsági szintje**|A tiltott helyek zóna biztonsági szintjét állítja be.|
|**„Do Not Track” fejléc küldése**|A nyomkövetést tiltó fejlécet küld az Internet Explorerben a felkeresett webhelyeknek.|
|**Vállalati üzemmód menüpont használatának engedélyezése**|Lehetővé teszi, hogy a felhasználók férhetnek hozzá a vállalati üzemmód menü beállítások Internet Explorer programból.<br>Engedélyezése esetén meghatározhatja a **Naplózási jelentés helyét** is, ahol megtalálható annak a jelentésnek az URL-címe, amely megjeleníti azokat a webhelyeket, amelyekhez a felhasználók bekapcsolták a vállalati üzemmódot.|
|**Vállalati üzemmód webhelylistájának helye**|Azon webhelyek listájának helyét adja meg, amelyek a Vállalati üzemmódot használják, ha az aktív.|

## <a name="device-capabilities-settings---cellular"></a>Eszközképességek beállításai – mobilhálózat

|Beállítás neve|Részletek|
|----------------|----|
|**Adatroaming engedélyezése**|Adatroaming használatát engedélyezi, ha az eszköz mobilhálózathoz csatlakozik.|



### <a name="see-also"></a>További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
