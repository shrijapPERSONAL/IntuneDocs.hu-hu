---
title: "Intune-adattárház API  | Microsoft Docs"
description: "Az API használatával összeállíthatja a cége mobilkörnyezetéről szóló jelentéseket."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5f03fd3a1557ef5d013fe695016ed0e3b119ee62
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/04/2017
---
#  <a name="intune-data-warehouse-api"></a>Intune-adattárház API

Az Intune-adattárház API géppel olvasható formában nyújt hozzáférést az Intune-beli adatokhoz, hogy kedvenc elemző eszközével feldolgozhassa azokat. Az API használatával összeállíthatja a cége mobilkörnyezetéről szóló jelentéseket. Az API az OData protokollt használja, amely a szabványos minták szerint kezeli az alábbiakat:

  -   Kérés- és válaszfejlécek
  -   Állapotkódok
  -   HTTP-metódusok
  -   URL-címre vonatkozó konvenciók
  -   Adathordozó-típusok
  -   Adattartalom-formátumok
  -   Lekérdezési lehetőségek

Az OData (Open Data Protocol – nyílt adatprotokoll) az OASIS (Szervezet a strukturált információs szabványok fejlesztéséért) szabványa, amely ajánlott eljárásokat határoz meg a RESTful API-k kialakításához és használatához. Az Intune-adattárház az OData 4.0-s verzióját használja.

Ez a referenciaszakasz áttekintést nyújt az Intune-adattárház adatmodelljének végpontjairól, támogatott HTTP-metódusairól, adattartalmainak visszaadási formátumairól és dokumentációjáról.

> [!Important]  
> A bétaverzió használatával kipróbálhatja az adattárház legújabb funkcióit. A bétaverzió használatához az URL-címnek tartalmaznia kell a következő lekérdezési paramétert: `api-version=beta`. A bétaverzió olyan funkciókat is kínál, amelyek támogatott szolgáltatásként még érhetőek el általánosan. Amikor az Intune új funkciókkal bővül, a bétaverzió működése és adategyezményei módosulhatnak. Frissítések esetén a bétaverziót használó egyéni kódok vagy jelentéskészítő eszközök működésében hibák jelentkezhetnek. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

<!-- ## OData custom client

You can access the Intune Data Warehouse data model through RESTful endpoints. To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0. You first set up a web app and a client app in Azure, grant permissions to the client. Your local client will get authorization, can then communicate with the Data Warehouse endpoints.

For more information, see [Get data from the Data Warehouse API with a REST client](Get-data-REST.md) -->

## <a name="interacting-with-the-api"></a>Az API használata

Az API használatához Azure AD-hitelesítésre van szükség. Az Azure AD az OAuth 2.0-s verzióját használja. A hitelesítés után egy HTTP GET művelet végrehajtásával és a közzétett entitásgyűjteményekhez kapcsolódva hozzáférhet az API adataihoz. További részletek:

 -  [Hitelesítés](reports-api-url.md)
 -  [Az API URL-címének szerkezete](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Az Intune-adattárház adatmodellje

Az OData olyan absztrakt adatmodellt és protokollt határoz meg, amely minden ügyfél számára minden adatforrás által közzétett információt hozzáférhetővé tesz. Az adatmodell dokumentációs témaköre magyarázatot nyújt az Intune-adattárház adatmodelljének névtereiről, entitásairól és visszaadott objektumairól. További tudnivalókért lásd: [Az adattárház adatmodellje](reports-ref-data-model.md).

## <a name="for-more-information"></a>További tudnivalók

[Az Azure AD hitelesítési forgatókönyvei](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)  
[odata.org](http://www.odata.org)  
[OData 4.0-s verzió](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
