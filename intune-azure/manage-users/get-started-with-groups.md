---
title: "Ismerkedés a csoportokkal az Intune Azure Portal előzetesében | Microsoft Docs"
description: "További információk az Intune Azure Portal előzetes csoportokkal kapcsolatos újdonságaival"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 27a9c9d8269b302fa9735972056d38e7919f42b5


---

# <a name="get-started-with-groups"></a>Csoportok – első lépések

[!INCLUDE[azure preview](../includes/azure_preview.md)]

A visszajelzések alapján módosításokat vezetünk be a Microsoft Intune-beli csoportok használatában.
Az Azure Portalról használt Intune esetén az Intune-csoportok migrálva lettek az Azure Active Directory biztonsági csoportjaiba.

Az ügyfeleknek ez azért hasznos, mert így ugyanazt a csoportkezelési élményt kapják a teljes Enterprise Mobility + Security, valamint az Azure AD-alkalmazások esetén is. Ezen kívül az új funkció kiterjesztéséhez és testre szabásához a PowerShell és a Graph API is használható.

Az Azure AD-alapú biztonsági csoportok az Intune minden telepítéstípusát támogatják mind a felhasználókat, mind az eszközöket tekintve. Használhatók továbbá az Azure AD-alapú dinamikus csoportok, amelyek az Ön által megadott attribútumok alapján automatikusan frissülnek. Például létrehozhat egy csoportot, amely az összes iOS 9 rendszerű eszközt tartalmazza. Amikor egy új iOS 9 rendszerű eszközt regisztrálnak, az automatikusan hozzáadódik a dinamikus csoporthoz.

## <a name="what-is-not-available"></a>Mi az, ami nem érhető el?

Előfordulhat, hogy a korábbi Intune-csoportok funkcióinak némelyike nem érhető el az Azure AD-ben:

- A **Nem csoportosított felhasználók** és a **Nem csoportosított eszközök** Intune-csoportjai már nem érhetők el.
- A **Meghatározott tagok kizárása** a csoportból funkció az Azure Portalon nem elérhető. Ennek megoldására azonban használhatja az Azure AD-alapú biztonsági csoportok speciális szabályait. Létrehozhat például egy olyan speciális szabályt, amely egyetlen biztonsági csoportba foglalja a Sales osztály minden munkatársát, kivéve azokat, akiknek a beosztásában szerepel az „Assistant” szó. Ezt a következő szabállyal érheti el: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Az Intune-konzolon elérhető **Minden, az Exchange ActiveSync által felügyelt eszköz** csoport nem lett migrálva az Azure AD-be. Az EAS által kezelt eszközök információit azonban továbbra is elérheti az Azure Portalról.


## <a name="how-to-get-started"></a>Első lépések

- Az alábbi Azure AD-vel kapcsolatos cikkek segítenek tájékozódni az Azure AD-alapú biztonsági csoportokról és azok működéséről:
    -  [Az erőforrásokhoz való hozzáférés kezelése Azure Active Directory-csoportokkal](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Csoportkezelés az Azure Active Directoryban](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Attribútumok használata speciális szabályok létrehozására](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Fontos, hogy azok a rendszergazdák, akik csoportokat fognak létrehozni, hozzá legyenek adva az **Intune szolgáltatásadminisztrátor** Azure AD-szerepkörhöz. Vegye figyelembe, hogy az Azure AD szolgáltatásadminisztrátori szerepkör nem rendelkezik **Csoportok kezelése** engedéllyel.
-  Ha **Meghatározott tagok kizárása** funkcióval használ csoportokat, vizsgálja meg, hogy átalakíthatók-e ezek a csoportok úgy, hogy ne legyen szükség kizárásokra, illetve hogy elérhető-e ugyanaz az eredmény az Azure AD-lekérdezésekben használt speciális szabályokkal.


## <a name="what-happened-to-intune-groups"></a>Mi történt az Intune-csoportokkal?

| Csoportok az Intune-ban|Azure AD csoport|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statikus felhasználói csoport|Statikus Azure AD biztonsági csoport|
|Dinamikus felhasználói csoport|Statikus Azure AD biztonsági csoportok Azure AD biztonságicsoport-hierarchiával|
|Statikus eszközcsoport|Statikus Azure AD biztonsági csoport|
|Dinamikus eszközcsoport|Dinamikus Azure AD biztonsági csoport|
|Belefoglalási feltételt tartalmazó csoport|Statikus Azure AD biztonsági csoport, amely tartalmazza az Intune-beli belefoglalási feltétel által érintett statikus/dinamikus tagokat|
|Kizárási feltételt tartalmazó csoport|Nem lesz áttelepítve|
|Beépített csoportok: **Minden felhasználó**, **Nem csoportosított felhasználók**, **Minden eszköz**, **Nem csoportosított eszközök**, **Minden számítógép**, **Minden mobileszköz**, **MDM által felügyelt eszközök** és **EAS által felügyelt eszközök**|Azure AD biztonsági csoportok|

Az Intune-ban minden létrehozott csoportnak rendelkeznie kell szülőcsoporttal. A csoportok csak a szülőcsoport tagjait tartalmazhatják. Az Azure AD-ben a gyermekcsoportok olyan tagokat is tartalmazhatnak, amelyek nem részei a szülőcsoportnak.

Az attribútumok a csoportok definiálása során felhasználható eszköztulajdonságok. Ez a táblázat bemutatja, hogyan fog történni ezeknek a feltételeknek az Azure AD-alapú biztonsági csoportokba való migrálása.

| Attribútum az Intune-ban|Attribútum az Azure AD-ben|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Eszközcsoportok szervezeti egység (OU) attribútuma|Dinamikus csoportok OU attribútuma.|
|Eszközcsoportok Tartománynév attribútuma|Dinamikus csoportok Tartománynév attribútuma.|
|Biztonsági csoport mint a felhasználócsoportok attribútuma|A csoportok nem lehetnek attribútumok az Azure AD dinamikus lekérdezéseiben. A dinamikus csoportok csak felhasználó- vagy eszközspecifikus attribútumokat tartalmazhatnak.|
|A felhasználócsoportok Manager (Kezelő) attribútuma|A *manager* (kezelő) attribútumra vonatkozó speciális szabály dinamikus csoportokban|
|A szülő felhasználócsoport minden felhasználója|Statikus csoport, amelynek ez a csoport a tagja|
|A szülő eszközcsoport minden mobileszköze|Statikus csoport, amelynek ez a csoport a tagja|
|Az Intune által kezelt összes mobileszköz|Egy dinamikus csoport Management Type (Kezelés típusa) attribútumának „MDM” értéke|
|Statikus csoportokba ágyazott csoportok |Statikus csoportokba ágyazott csoportok|
|Dinamikus csoportokba ágyazott csoportok|Egy beágyazott szintet tartalmazó dinamikus csoport|

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Mi történik a korábban telepített szabályzatokkal és alkalmazásokkal?

A szabályzatokat és az alkalmazásokat továbbra is telepíteni lehet a csoportokba. Ezeket a csoportokat azonban a klasszikus Intune-konzol helyett az Azure portálon lehet kezelni.



<!--HONumber=Feb17_HO1-->


