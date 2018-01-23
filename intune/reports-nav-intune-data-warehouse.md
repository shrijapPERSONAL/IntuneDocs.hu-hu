---
title: "Intune-adattárház API  | Microsoft Docs"
description: "Az API használatával összeállíthatja a cége mobilkörnyezetéről szóló jelentéseket."
keywords: "Intune-adattárház"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6bdb7a8d20d86ca800b61c069dcc380f86747a30
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2018
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
> A bétaverzió használatával kipróbálhatja az adattárház legújabb funkcióit. A bétaverzió használatához URL-címének az `api-version=beta` lekérdezési paraméterrel kell rendelkeznie. A bétaverzió olyan funkciókat is kínál, amelyek támogatott szolgáltatásként még érhetőek el általánosan. Amikor az Intune új funkciókkal bővíti a szolgáltatást, előfordulhat, hogy a bétaverzió viselkedése és az adategyezmény megváltozik. Frissítések esetén a bétaverziót használó egyéni kódok vagy jelentéskészítő eszközök működésében hibák jelentkezhetnek. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

## <a name="odata-custom-client"></a>Egyéni OData-ügyfél

Az Intune-adatárház adatmodellje RESTful végpontokon keresztül érhető el. Ahhoz, hogy hozzáférjen az adatokhoz, az ügyfélnek az OAuth 2.0 protokollt használva igazolnia kell, hogy jogosult az Azure Active Directory (Azure AD) használatára. Ehhez először be kell állítani egy webalkalmazást és egy ügyfelet az Azure-ban, és meg kell adni az ügyfélnek a megfelelő jogosultságokat. A helyi ügyfél megkapja az engedélyt, és kommunikálhat az Adattárház-végpontokkal.

További információért lásd az [Adatok beolvasása az adattárház API-ból REST-ügyféllel](reports-proc-data-rest.md) című cikket.

> [!Note]  
> Kódpéldákat a [GitHub Intune-adattárház tárházban](https://github.com/Microsoft/Intune-Data-Warehouse) találhat a GitHubon.

## <a name="interacting-with-the-api"></a>Az API használata

Az API használatához Azure AD-hitelesítésre van szükség. Az Azure AD az OAuth 2.0-s verzióját használja. A hitelesítés után egy HTTP GET művelet végrehajtásával és a közzétett entitásgyűjteményekhez kapcsolódva hozzáférhet az API adataihoz. További részletek:

 -  [Hitelesítés](reports-api-url.md)
 -  [Az API URL-címének szerkezete](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Az Intune-adattárház adatmodellje

Az OData olyan absztrakt adatmodellt és protokollt határoz meg, amely minden ügyfél számára minden adatforrás által közzétett információt hozzáférhetővé tesz. Az adatmodell dokumentációs témaköre magyarázatot nyújt az Intune-adattárház adatmodelljének névtereiről, entitásairól és visszaadott objektumairól. További tudnivalókért lásd: [Az adattárház adatmodellje](reports-ref-data-model.md).

## <a name="next-steps"></a>További lépések

Az Azure AD használatáról további információt kaphat a [Hitelesítési forgatókönyvek az Azure AD-ban](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios) című témakörben.

OData-val kapcsolatos forrásokat az [odata.org](http://www.odata.org) webhelyen talál.
  
Az OData 4.0-ás verziójának szabványát az [OData 4.0-ás verzió] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html) webhelyen találja  
