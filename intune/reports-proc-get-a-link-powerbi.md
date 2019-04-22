---
title: Kapcsolódás az adattárházhoz a Power BI használatával
titleSuffix: Microsoft Intune
description: A Microsoft Power BI-hoz letölthető egy fájl, amellyel a Microsoft Intune-bérlőhöz kapcsolódó interaktív, dinamikusan létrehozott jelentéseket hozhat létre.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 259d700d04547a801b0ebc37242dacf536ad61d3
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59899703"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Kapcsolódás az adattárházhoz a Power BI használatával

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Power BI megfelelésével alkalmazást az Intune-bérlőhöz kapcsolódó interaktív, dinamikusan létrehozott jelentéseket használhatja. Ezenkívül betöltheti a bérlő adatainak a Power BI az OData-hivatkozás használatával. Intune kapcsolati beállításokat a bérlő által biztosított, hogy az alábbi mintajelentések és diagramok kapcsolatos is megtekintheti:  

  -  Eszközök
  -  Beléptetés
  -  Alkalmazásvédelmi szabályzat
  -  Megfelelőségi szabályzat
  -  Eszközkonfigurációs profilok
  -  Szoftverfrissítések
  -  Eszközleltár-naplók

A jelentésekben szerepelnek továbbá a regisztrálásokra, a megfelelőségre, az eszközkonfigurációs profilokra és a szoftverfrissítésekre vonatkozó adatok és trendek. A mintadiagramok és a jelentések könnyen használható szűrőket alkalmaznak a megjelenítésnél. A Power BI Desktop **Szűrők** paneljének használatával speciális szűrőket is alkalmazhat.

Az alábbiakban bemutatjuk, hogyan töltheti le a Power BI-fájl, és hogyan használhatja az OData-hivatkozást a Power BI-vel.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>A Power BI telepítése

Telepítse a legújabb verzióját, [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi). További információkért lásd: [Power BI Desktopban](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Az adatok és a jelentések használata a Power BI az Intune megfelelőségi Data Warehouse alkalmazás betöltése

A Power BI [alkalmazás Intune-adattárház megfelelőségi](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) a bérlői és az adattárház adatmodellje alapján előre elkészített jelentéseket számos kapcsolatos tudnivalókat tartalmazza.

1.  Keresse meg a [alkalmazás Intune-adattárház megfelelőségi](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) a telepítés megkezdéséhez.
2.  Amikor a rendszer kéri, telepítse a Power BI alkalmazás megbízható forrásból származó, kattintson a **telepítése**.
3.  Kattintson a **Intune megfelelőségi Data Warehouse alkalmazás** csempére.
4.  Kattintson a **adatok** gombra. 
    A **csatlakozhat az Intune megfelelőségi Data Warehouse alkalmazás** párbeszédpanel jelenik meg.
5.  Kattintson a **jelentkezzen be a** gombra.
6.  Jelentkezzen be egy felhasználói fiókkal, amely hozzáfér ehhez az Intune-adattárház, amely rendelkezik a bérlőhöz tartozó jelentések megtekintéséhez. 
7.  Kattintson a **jelentések** lapfülre, majd kattintson a **megfelelőségi 1.0-s verziójú** jelentést.
8.  Lépjen vissza a jelentések később megkönnyíteni a csillag mellett kattintson a **megfelelőségi 1.0-s verziójú** jelentést. Ez a jelentés hozzáadása a Power BI-kedvenceit.

Azt is megteheti telepíthetik az alkalmazást az Intune-portálon:

1.  Jelentkezzen be az Azure Portalra, és válassza a **Monitoring + Management (Figyelés és kezelés)** > **Intune** elemet. Erőforrások az Intune-hoz is kereshet.
2.  Nyissa meg a **beállítása az Intune-adattárház** panelen.
3.  Válassza ki **Power BI alkalmazás első** eléréséhez, és előre elkészített Power BI-jelentések megosztása a böngészőben a bérlő számára.
4.  Kövesse a lépéseket 2 – 8 fenti.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Adatok betöltése a Power BI-be az OData-hivatkozás használatával

Ha az ügyfél hitelesítve van az Azure AD-ben, az OData-URL kapcsolódni tud az adattárház-API RESTful-végpontjához, és így a jelentéskészítő ügyfél hozzáfér az adatmodellhez. Az alábbi lépéseket követve a Power BI Desktop használatával végezheti el a kapcsolódást, és létrehozhatja saját jelentéseit. Az OData-URL alkalmazásánál a Power BI-n kívül más elemzőeszközöket is használhat, amennyiben az ügyfél OAUTH2.0-hitelesítést, valamint az OData-szabvány 4.0-ás verzióját használja.

1.  Jelentkezzen be az Azure Portalra, és válassza a **Monitoring + Management (Figyelés és kezelés)** > **Intune** elemet. Az **Intune** elemet erőforrások keresésével is megtalálhatja.  
2.  Nyissa meg a **beállítása az Intune-adattárház** panelen.
3. A jelentések panelről szerezze be az egyéni hírcsatorna URL-címét, például: `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`
4. Nyissa meg a **Power BI Desktopot**.
5. Válassza a **Kezdőlap** > **Adatforrás lekérése** elemet. Válassza az **OData-betöltés** lehetőséget.
6. Válassza a **Basic** (Egyszerű) lehetőséget.
7. Írja be vagy másolja be az **OData-URL-t** az URL mezőbe.
8. Kattintson az **OK** gombra.
9. Ha a Power BI Desktop-ügyfélben nem adta meg az Azure AD-s hitelesítő adatait, most adja meg azokat. Ahhoz, hogy hozzáférjen az adatokhoz, az OAuth 2.0 protokollt használva igazolnia kell, hogy jogosult az Azure Active Directory (Azure AD) használatára.  
    1.  Válassza a **Szervezeti fiók** lehetőséget.  
    2.  Adja meg felhasználónevét és jelszavát.  
    3.  Válassza a **Bejelentkezés** lehetőséget.  
    4.  Kattintson a **Csatlakozás** gombra.  
10. Válassza a **Betöltés** lehetőséget.

## <a name="next-steps"></a>További lépések

A fenti módszerrel olyan információkat kaphat a környezetről, mint például a regisztrált eszközök száma az elmúlt egy hétben napi bontásban. Az Intune bérlői és az ügyfél population olvassa be a panelt az Azure-ban az Intune Data Warehouse a Power BI-jelentések segítségével betekintést kaphatnak. Ezen kívül azonban az Intune számos további lehetőséget is kínál az adatok bővítésére vagy újbóli felhasználására. A Power BI és az Intune-adattárház API olyan további funkciókat biztosítanak, például:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  A bérlő adatai olyan módon vannak felépítve, hogy azokból egyszerűen lehessen információhoz jutni. Az adatok felépítéséről az [Adattárház adatmodellje](reports-ref-data-model.md) című témakörben tájékozódhat.
 -  Egy RESTful interfészről is elérheti az adatokat, és belefoglalhatja azokat a saját alkalmazásába. További információért lásd [Adatok beolvasása az adattárház API-ból REST-ügyféllel](reports-proc-data-rest.md).
