---
title: "Kapcsolódás az adattárházhoz a Power BI használatával | Microsoft Docs"
description: "A Power BI-hoz letölthető egy fájl, amellyel az Intune-bérlőhöz kapcsolódó interaktív, dinamikusan létrehozott jelentéseket hozhat létre."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 56f80e7cede68364d1a98b58acab3e7dd2f51b73
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Kapcsolódás az adattárházhoz a Power BI használatával

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Power BI-hoz letölthető egy fájl, amellyel az Intune-bérlőhöz kapcsolódó interaktív, dinamikusan létrehozott jelentéseket hozhat létre. Az adattárházzal használható Power BI-fájl (pbix) kapcsolati beállításokat tartalmaz a bérlőhöz való kapcsolódáshoz, és az alábbi mintajelentések és diagramok is elérhetőek benne:  

  -  Eszközök
  -  Beléptetés
  -  Alkalmazásvédelmi szabályzat
  -  Megfelelőségi szabályzat
  -  Eszközkonfigurációs profilok
  -  Szoftverfrissítések
  -  Eszközleltár-naplók

A jelentésekben szerepelnek továbbá a regisztrálásokra, a megfelelőségre, az eszközkonfigurációs profilokra és a szoftverfrissítésekre vonatkozó adatok és trendek. A mintadiagramok és a jelentések könnyen használható szűrőket alkalmaznak a megjelenítésnél. A Power BI Desktop **Szűrők** paneljének használatával speciális szűrőket is alkalmazhat.

Az alábbiakban bemutatjuk, hogyan töltheti le a Power BI-fájl, és hogyan használhatja az OData-hivatkozást a Power BI-vel.

[!INCLUDE[reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>A Power BI telepítése

Telepítse a Power BI Desktop legújabb verzióját. Ezt a [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop) webhelyről töltheti le.

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Az adatok és jelentések betöltése a Power BI-fájl (pbix) használatával

A Power BI-fájl (pbix) tartalmazza a bérlő eléréséhez használható csatlakozási információkat, valamint az adattárház adatmodelljén alapuló előre elkészített jelentéseket is. Nyissa meg a fájlt a Power BI Desktopban, és jelentkezzen be az Azure AD-be. A jelentés betölti az Intune-bérlő adatait.

> [!Important]  
> A bérlő földrajzi helyétől függően a Power BI-fájlok (pbix) eltérőek lehetnek. Ha több Intune-bérlőt felügyel, akkor ügyeljen arra, hogy azt a fájlt használja, amelyet ebbe a bérlőbe bejelentkezve letöltött az Azure Portalról.  

1.  Jelentkezzen be az Azure Portalra, és válassza a **Monitoring + Management (Figyelés és kezelés)** > **Intune** elemet. Az **Intune** elemet erőforrások keresésével is megtalálhatja.  
2.  Nyissa meg a **Microsoft Intune-adattárház API (előnézet)** panelt.
3.  Kattintson a **Download PowerBI file** (Power BI-fájl letöltése) elemre. Adjon meg egy helyet a pbix kiterjesztésű fájl letöltéséhez, és töltse le a fájlt.
4.  Nyissa meg a fájlt a Power BI-ben. Betöltődik az *Intune-beli adattárház-jelentés*, ami a bérlő adatainak betöltésétől függően hosszabb ideig is eltarthat.
5.  Ahhoz, hogy az adatok betöltődjenek, és a bérlőadatok megjelenjenek a jelentésekben, kattintson a **Frissítés** elemre.
6.  Ha a Power BI-hoz nem az Azure Active Directory-hez tartozó hitelesítő adatait használta, a Power BI kérni fogja a hitelesítő adatokat. Az adatok megadásához hitelesítő módszerként válassza a **Szervezeti fiók** lehetőséget.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Adatok betöltése a Power BI-be az OData-hivatkozás használatával

Ha az ügyfél hitelesítve van az Azure AD-ben, az OData-URL kapcsolódni tud az adattárház-API RESTful-végpontjához, és így a jelentéskészítő ügyfél hozzáfér az adatmodellhez. Az alábbi lépéseket követve a Power BI Desktop használatával végezheti el a kapcsolódást, és létrehozhatja saját jelentéseit. Az OData-URL alkalmazásánál a Power BI-n kívül más elemzőeszközöket is használhat, amennyiben az ügyfél OAUTH2.0-hitelesítést, valamint az OData-szabvány 4.0-ás verzióját használja.

1.  Jelentkezzen be az Azure Portalra, és válassza a **Monitoring + Management (Figyelés és kezelés)** > **Intune** elemet. Az **Intune** elemet erőforrások keresésével is megtalálhatja.  
2.  Nyissa meg a **Microsoft Intune-adattárház API (előnézet)** panelt.
3. A jelentések panelről szerezze be az egyéni hírcsatorna URL-címét, például: `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4. Nyissa meg a **Power BI Desktopot**.
5. Válassza a **Kezdőlap** > **Adatforrás lekérése** elemet. Válassza az **OData-betöltés** lehetőséget.
6. Válassza a **Basic** (Egyszerű) lehetőséget.
7. Írja be vagy másolja be az **OData-URL-t** az URL mezőbe.
8. Kattintson az **OK**gombra.
9. Ha a Power BI Desktop-ügyfélben nem adta meg az Azure AD-s hitelesítő adatait, most adja meg azokat. Ahhoz, hogy hozzáférjen az adatokhoz, az OAuth 2.0 protokollt használva igazolnia kell, hogy jogosult az Azure Active Directory (Azure AD) használatára.  
    1.  Válassza a **Szervezeti fiók** lehetőséget.  
    2.  Adja meg felhasználónevét és jelszavát.  
    3.  Kattintson a **Bejelentkezés** elemre.  
    4.  Kattintson a **Csatlakozás**gombra.  
10. Kattintson a **Betöltés** lehetőségre.

## <a name="next-steps"></a>További lépések

A fenti módszerrel olyan információkat kaphat a környezetről, mint például a regisztrált eszközök száma az elmúlt egy hétben napi bontásban. Az Intune-os adattárház Azure-panelről beszerezhető Power BI-fájljának (pbix) használatával készült jelentésekből a bérlőről és az ügyfelekről kaphat részletes információkat. Ezen kívül azonban az Intune számos további lehetőséget is kínál az adatok bővítésére vagy újbóli felhasználására. A Power BI és az Intune adattárház-API-jának használatával még sok más lehetőség is rendelkezésére áll, többek között:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  A bérlő adatai olyan módon vannak felépítve, hogy azokból egyszerűen lehessen információhoz jutni. Az adatok felépítéséről az [Adattárház adatmodellje](reports-ref-data-model.md) című témakörben tájékozódhat.
 -  Egy RESTful interfészről is elérheti az adatokat, és belefoglalhatja azokat a saját alkalmazásába. További információért lásd [Adatok beolvasása az adattárház API-ból REST-ügyféllel](reports-proc-data-rest.md).
