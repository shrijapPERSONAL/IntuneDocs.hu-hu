---
title: "Az Intune-adattárház használata | Microsoft Docs"
description: "Az Intune-adattárház használatával a vállalat mobilkörnyezetéről szóló jelentéseket hozhat létre."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: db6661dd92b890d711f655a60eb883b417a30d8a
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/04/2017
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

> [!Important]  
> A bétaverzió segítségével az adattárház legújabb funkcióit próbálhatja ki. A bétaverzió használatához URL-címének az `api-version=beta` lekérdezési paraméterrel kell rendelkeznie. A bétaverzió olyan funkciókat is kínál, amelyek támogatott szolgáltatásként még érhetőek el általánosan. Amikor az Intune új funkciókkal bővíti a szolgáltatást, előfordulhat, hogy a bétaverzió viselkedése és az adategyezmény megváltozik. Frissítések esetén a bétaverziót használó egyéni kódok vagy jelentéskészítő eszközök működésében hibák jelentkezhetnek. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**További lépések**

- Kapcsolódjon az adattárházhoz a Power BI használatával, és készítsen információs jelentéseket. További információt a [Csatlakozás az Intune-adattárházhoz a Power BI segítségével](reports-proc-get-a-link-powerbi.md)című témakörben talál.
- Az Intune-adattárház API-ról, az adatmodellről és az entitások közötti kapcsolatokról, <!-- , and an example of creating a custom client to retrieve data,--> további információt az [Intune-adattárház API](reports-nav-intune-date-warehouse.md) című témakörben talál.