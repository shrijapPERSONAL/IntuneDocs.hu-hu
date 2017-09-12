---
title: "Útmutató az eszközkategóriák használatához az Intune-ban"
titleSuffix: Azure portal
description: "Ez a témakör azoknak az eszközkategóriáknak a használatát ismerteti, amelyeket a felhasználók eszközeik Intune-regisztrációjakor választhatnak."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00becba338f9a64e341b0b6d220b1a4ace3b40a9
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="map-device-groups"></a>Eszközcsoportok leképezése


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune eszközkategóriáival az eszközöket a definiált kategóriák alapján automatikusan felveheti csoportokba, így egyszerűsítve az eszközfelügyeletet.

Az eszközkategóriák a következő munkafolyamatot használják:
1. Hozzon létre kategóriákat, amelyek közül a felhasználók választani fognak az eszközük regisztrálásakor
3. Az iOS-es és androidos eszközök végfelhasználóinak eszközük regisztrációjakor a konfigurált kategórialistából kell kategóriát választaniuk. A végfelhasználó a kategóriák Windows-eszközhöz való hozzárendelését a Céges portál webhelyen végezheti el (további részletekért lásd **Az eszközcsoportok konfigurálása után** című témakört).
4. Ezután szabályzatokat és alkalmazásokat telepíthet ezekre a csoportokra.

Bármilyen tetszés szerinti eszközkategóriát létrehozhat, például:
- Pénztári eszközök
- Bemutatóeszközök
- Értékesítés
- Könyvelés
- Manager

## <a name="how-to-configure-device-categories"></a>Az eszközkategóriák konfigurálása

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>1. lépés - Eszközkategóriák létrehozása az Azure Portal Intune panelén
1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközregisztráció** lehetőséget.
3. Az **Eszközregisztráció** panelen válassza az **Eszközkategóriák** elemet.
4. Az **Eszközkategóriák** lapon a **Létrehozás** elemmel hozhat létre új kategóriát.
5. A következő panelen töltse ki az új kategória **Név** és **Leírás** mezőjét (utóbbi nem kötelező).
6. Ha végzett, kattintson a **Létrehozás** gombra. Az imént létrehozott kategória bekerül a listába.

Azure Active Directory biztonsági csoportok létrehozásakor az eszközkategória nevét fogja használni a 2. lépésben.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2. lépés - Azure Active Directory biztonsági csoportok létrehozása
Ebben a lépésben az eszközkategória és az eszközkategória-név alapján dinamikus csoportokat fog létrehozni az Azure-portálon.

A folytatáshoz tekintse meg a [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) (Speciális szabályok létrehozása attribútumok használatával) című témakört az Azure Active Directory dokumentációjában. 

Ezen szakasz információi alapján hozzon létre speciális szabállyal egy eszközcsoportot a **deviceCategory** attribútum segítségével, például így: (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Ha vannak konfigurált eszközcsoportok, amikor a felhasználók regisztrálják eszközüket, meg fog jelenni számukra az Ön által beállított kategóriák listája. A kategória kiválasztását és a regisztráció befejezését követően az eszköz a kiválasztott kategóriának megfelelő Active Directory biztonsági csoportba kerül.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>A felügyelt eszközök kategóriáinak megtekintése

1.  Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Azure Portal Intune panelén válassza az **Eszközök és csoportok** lehetőséget.

3.  A **Felügyelet** alatt kattintson a **Minden eszköz** elemre.

4.  Az eszközlistában keresse meg a **Kategória** oszlopot.

Ha a **Kategória** oszlop nem látható, kattintson az **Oszlopok** elemre, a listából válassza a **Kategória** elemet, és kattintson az **Alkalmaz** gombra.

### <a name="to-change-the-category-of-a-device"></a>Eszköz kategóriájának módosítása

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök és csoportok** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Felügyelet** > **Minden eszköz** lehetőséget.
5. Az eszközlistából válassza ki a kívánt eszközt, majd az eszköz tulajdonságainak panelén válassza a **Felügyelet** > **Tulajdonságok** lehetőséget.
6. A következő panelen a kijelölt eszköz **Eszközkategória** tulajdonságát átállíthatja a korábban konfigurált kategórianevek bármelyikére.

## <a name="after-you-configure-device-groups"></a>Az eszközcsoportok konfigurálása után

Az iOS-es és androidos eszközök végfelhasználóinak eszközük regisztrációjakor a konfigurált kategórialistából kell kategóriát választaniuk. A kategória kiválasztását és a regisztráció befejezését követően a rendszer a kiválasztott kategóriának megfelelő Intune eszközcsoporthoz vagy Active Directory biztonsági csoporthoz adja az eszközüket.

A végfelhasználó a kategóriák Windows-eszközhöz való hozzárendelését a Céges portál webhelyen (portal.manage.microsoft.com) végezheti el az eszköz regisztrálása után. A windowsos eszközön nyissa meg a webhelyet, és válassza a **Menü** > **Saját eszközök** elemet. Válasszon egy regisztrált eszközt a lapon található listából, majd válasszon egy kategóriát. 

A kategória kiválasztása után az eszköz automatikusan bekerül az Ön által létrehozott, a kategóriának megfelelő csoportba. Ha a kategóriák konfigurálása előtt az eszköz már regisztrálva van, a végfelhasználó egy értesítést lát az eszközről a Céges portál webhelyen, és a rendszer egy adott kategória kiválasztását kéri a következő alkalommal, amikor a végfelhasználó belép az iOS-es vagy androidos Céges portál alkalmazásba.

## <a name="further-information"></a>További információ
- Az Azure Portalon szerkesztheti az eszközkategóriákat, de ha így tesz, akkor manuálisan kell módosítania az Azure Active Directoryban az adott kategóriára hivatkozó biztonsági csoportokat.

- Ha törli valamelyik kategóriát, az ahhoz rendelt eszközöknél a **Nincs hozzárendelve** kategórianév jelenik meg.


