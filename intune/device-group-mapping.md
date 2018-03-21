---
title: "Eszközök csoportokba sorolása az Intune-ban"
titleSuffix: Microsoft Intune
description: "Információ arról, hogyan lehet az eszközöket csoportokba rendezni a könnyebb kezelhetőség érdekében."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d07b025881ea78299d617205ce5ba39bb92a1231
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="categorize-devices-into-groups-for-easier-management"></a>Eszközöket csoportokba rendezése a könnyebb kezelhetőség érdekében

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune eszközkategóriáival az eszközöket a definiált kategóriák alapján automatikusan felveheti csoportokba, így egyszerűsítve az eszközfelügyeletet.

Az eszközkategóriák a következő munkafolyamatot használják:
1. Kategóriák létrehozása, amelyek közül a felhasználók választhatnak az eszközük regisztrálásakor
2. Az iOS-es és androidos eszközök végfelhasználóinak eszközük regisztrációjakor a konfigurált kategórialistából kell kategóriát választaniuk. A végfelhasználó a kategóriák Windows-eszközökhöz való hozzárendelését a Céges portál webhelyen végezheti el (további részletekért lásd **Az eszközcsoportok konfigurálása után** című cikket).
3. Ezután szabályzatokat és alkalmazásokat telepíthet ezekre a csoportokra.

Bármilyen tetszés szerinti eszközkategóriát létrehozhat, például:
- Pénztári eszközök
- Bemutatóeszközök
- Értékesítés
- Könyvelés
- Manager

## <a name="how-to-configure-device-categories"></a>Az eszközkategóriák konfigurálása

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>1. lépés - Eszközkategóriák létrehozása az Azure Portal Intune panelén
1. Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** elemet.
2. Az **Eszközregisztráció** panelen válassza az **Eszközkategóriák** elemet.
3. Az **Eszközkategóriák** lapon a **Létrehozás** elemmel hozhat létre új kategóriát.
4. Az **Eszközkategória létrehozása** panelen töltse ki az új kategória **Név** és **Leírás** mezőjét (utóbbi nem kötelező).
5. Ha végzett, kattintson a **Létrehozás** gombra. Az új kategória megjelenik a kategóriák listájában.

Azure Active Directory biztonsági csoportok létrehozásakor az eszközkategória nevét fogja használni a 2. lépésben.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2. lépés - Azure Active Directory biztonsági csoportok létrehozása
Ebben a lépésben az eszközkategória és az eszközkategória-név alapján dinamikus csoportokat fog létrehozni az Azure-portálon.

A folytatáshoz tekintse meg a [Speciális szabályok létrehozása attribútumok használatával](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) című cikket az Azure Active Directory dokumentációjában.

Ezen szakasz információi alapján hozzon létre speciális szabállyal egy eszközcsoportot a **deviceCategory** attribútum segítségével, például így: (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Ha vannak konfigurált eszközcsoportok, amikor a felhasználók regisztrálják eszközüket, meg fog jelenni számukra az Ön által beállított kategóriák listája. A kategória kiválasztását és a regisztráció befejezését követően az eszköz a kiválasztott kategóriának megfelelő Active Directory biztonsági csoportba kerül.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>A felügyelt eszközök kategóriáinak megtekintése

1.  Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza az **Eszközök** elemet.

2.  A **Felügyelet** alatt kattintson a **Minden eszköz** elemre.

3.  Az eszközlistában keresse meg az **Eszközkategória** oszlopot.

Ha az **Eszközkategória** oszlop nem látható, kattintson az **Oszlopok** elemre, a listából válassza az **Eszközkategória** elemet, és kattintson az **Alkalmaz** gombra.

### <a name="to-change-the-category-of-a-device"></a>Eszköz kategóriájának módosítása

1. Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza az **Eszközök** elemet.
2. A **Kezelés** szakasz **Eszközök** paneljén válassza a **Minden eszköz** lehetőséget.
3. Az eszközlistából válassza ki a kívánt eszközt, majd az eszköz tulajdonságainak panelén válassza a **Felügyelet** szakaszban válassza a **Tulajdonságok** lehetőséget.
4. A következő panelen a kijelölt eszköz **Eszközkategória** tulajdonságát átállíthatja a korábban konfigurált kategórianevek bármelyikére.

## <a name="after-you-configure-device-groups"></a>Az eszközcsoportok konfigurálása után

Az iOS-es és androidos eszközök végfelhasználóinak eszközük regisztrációjakor a konfigurált kategórialistából kell kategóriát választaniuk. A kategória kiválasztását és a regisztráció befejezését követően a rendszer a kiválasztott kategóriának megfelelő Intune eszközcsoporthoz vagy Active Directory biztonsági csoporthoz adja az eszközüket.

Windows használata esetén a kategória kiválasztásához a Céges portál webhelyet kell használni.

Platformtól függetlenül a végfelhasználói mindig elérhetik a portal.manage.microsoft.com webhelyet az eszköz regisztrálása után. Kérje meg a felhasználóit, hogy nyissák meg a Céges portál webhelyet, és válasszák a **Saját eszközök** lehetőséget. Itt választhatnak egy regisztrált eszközt a lapon található listából, majd megadhatnak egy kategóriát.

A kategória kiválasztása után az eszköz automatikusan bekerül az Ön által létrehozott, a kategóriának megfelelő csoportba. Ha a kategóriák konfigurálása előtt az eszköz már regisztrálva van, a végfelhasználó egy értesítést lát az eszközről a Céges portál webhelyen, és a rendszer egy adott kategória kiválasztását kéri a következő alkalommal, amikor a végfelhasználó belép az iOS-es vagy androidos Céges portál alkalmazásba.

## <a name="further-information"></a>További információ
- Az Azure Portalon szerkesztheti az eszközkategóriákat, ekkor viszont manuálisan kell módosítania az Azure Active Directoryban az adott kategóriára hivatkozó biztonsági csoportokat.

- Ha töröl egy kategóriát, az ahhoz hozzárendelt eszközöknél a **Nincs hozzárendelve** kategórianév jelenik meg.
