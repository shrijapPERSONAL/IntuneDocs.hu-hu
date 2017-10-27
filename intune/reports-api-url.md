---
title: "Intune-adattárház API-végpontja | Microsoft Docs"
description: "A referencia-témakör az API URL-szerkezetét írja le."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f36327f21fbb2f08906a7621b701a4e6c9deee03
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune-adattárház API-végpontja

Az Intune-adattárház API-t az adott szerepköralapú hozzáférés-vezérlőkkel és Azure AD-beli hitelesítő adatokkal rendelkező fiókokkal használhatja. Ezután az OAuth 2.0 segítségével hitelesíti majd REST-ügyfelét az Azure AD szolgáltatással. Végül pedig megalkotja az adattárház-erőforrás hívására szolgáló beazonosítható URL-címet.

[!INCLUDE[reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Engedélyezés

Az Azure Active Directory (Azure AD) az OAuth 2.0 használatával teszi lehetővé a webalkalmazásokhoz és webes API-khez való hozzáférés engedélyezését az Azure AD-bérlőben. Jelen útmutató nyelvektől független, és azt ismerteti, hogyan küldhetők és fogadhatók HTTP-üzenetek a nyílt forráskódú könyvtáraink bármelyikének használata nélkül. Az OAuth 2.0 engedélyezési kódfolyamról bővebben az OAuth 2.0 ismertetőjének [4.1 szakaszában](https://tools.ietf.org/html/rfc6749#section-4.1) olvashat.

További információt az [Hozzáférés engedélyezése webes alkalmazásokhoz az OAuth 2.0 és az Azure Active Directory használatával](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code) című témakörben talál.

## <a name="api-url-structure"></a>API URL-címének szerkezete

Az adattárház API-végpontjai az egyes készletekhez tartozó entitásokat olvassák. Az API támogatja a **GET** HTTP-parancsot, valamint a lekérdezési beállítások alkészletét.

Az Intune-hoz tartozó URL-cím a következő formátumot használja:  
https://fef.{***location***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***entity-collection***}?api-version={***api-version***}

Az URL-cím a következő elemeket tartalmazza:

| Elem | Példa | Leírás |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Az alap URL-cím helye az Azure Portalon található adattárház API paneljén látható. |
| entitásgyűjtemény | dátumok | Az OData-entitásgyűjtemény neve. Az adatmodellben lévő gyűjteményekről és entitásokról további információt a [Adatmodell](reports-ref-data-model.md) című témakörben talál. |
| api-verzió | béta | Verzió alatt az elérni kívánt API verzióját értjük. További információt a [Verzió](#API-version-information) című témakörben talál. |


## <a name="api-version-information"></a>Az API-verzióra vonatkozó információk

Az API jelenlegi verziója a következő: `beta`. 

## <a name="odata-query-options"></a>Az OData-lekérdezés beállításai

A jelenlegi verzió a következő OData-lekérdezésparamétereket támogatja: `$filter, $orderby, $select, $skip,` és `$top`.