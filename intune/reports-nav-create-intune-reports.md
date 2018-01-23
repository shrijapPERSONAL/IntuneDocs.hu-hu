---
title: "Az Intune-adattárház használata | Microsoft Docs"
description: "Az Intune-adattárház használatával a vállalat mobilkörnyezetéről szóló jelentéseket hozhat létre."
keywords: "Intune-adattárház"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 910d279b57c885040d2ad092e460d3e7ca71090e
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2018
---
# <a name="use-the-intune-data-warehouse"></a>Az Intune-adattárház használata

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune-adattárház használatával a vállalat mobilkörnyezetéről szóló jelentéseket hozhat létre. A jelentésekben például a következők szerepelhetnek:
-   Az Intune-ban regisztráló felhasználók trendje a licencvásárlások optimalizálásához
-   Az alkalmazások és az operációs rendszerek listázása verziók szerinti bontásban a mobileszközök állapotának ellenőrzéséhez
-   Regisztrációs és eszközmegfelelőségi trendek a szabályzatfrissítések zökkenőmentes bevezetéséhez

Az adattárház az Azure Portalnál több információt nyújt a mobilkörnyezettel kapcsolatban. Az Intune-adattárház segítségével a következőkhöz férhet hozzá:

  -  Intune-előzményadatok
  -  Napi szintű frissített adatok
  -  OData-szabványt használó adatmodell

> [!Note]
> Ha hibrid mobileszköz-kezelést (MDM) használ a System Center Configuration Managerrel és a Microsoft Intune-nal, az adatokat az SCCM-ből kell lekérnie. Az Intune-adattárház csak az Intune-adatokat tartalmazza. Az egyéni jelentésekhez használhatja az SCCM Power BI-irányítópultot. További információ: „[A Power BI-megoldássablon bejelentése a System Center Configuration Managerhez]( https://powerbi.microsoft.com/blog/sccm-solution-template)”, és „[Power BI-jelentés és -irányítópult létrehozása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard).”


> [!Important]  
> A bétaverzió használatával kipróbálhatja az adattárház legújabb funkcióit. A bétaverzió használatához URL-címének az `api-version=beta` lekérdezési paraméterrel kell rendelkeznie. A bétaverzió olyan funkciókat is kínál, amelyek támogatott szolgáltatásként még érhetőek el általánosan. Amikor az Intune új funkciókkal bővíti a szolgáltatást, előfordulhat, hogy a bétaverzió viselkedése és az adategyezmény megváltozik. Frissítések esetén a bétaverziót használó egyéni kódok vagy jelentéskészítő eszközök működésében hibák jelentkezhetnek.

**További lépések**

- Kapcsolódjon az adattárházhoz a Power BI használatával, és készítsen információs jelentéseket. További információt a [Csatlakozás az Intune-adattárházhoz a Power BI segítségével](reports-proc-get-a-link-powerbi.md)című témakörben talál.
- A hivatkozást felhasználva készítsen egyéni jelentéseket a Power BI használatával. Ehhez a [Jelentés készítése az OData-adatcsatornából a Power BI használatával](reports-proc-create-with-odata.md) című témakörben talál útmutatót.
- Az Intune-adattárház API-ról, az adatmodellről és az entitások közötti kapcsolatokról, <!-- , and an example of creating a custom client to retrieve data,--> további információt az [Intune-adattárház API](reports-nav-intune-data-warehouse.md) című témakörben talál.