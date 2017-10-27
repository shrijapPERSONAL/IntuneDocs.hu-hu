---
title: "Az Intune-adattárház használata | Microsoft Docs"
description: "Az Intune-adattárház használatával a vállalat mobilkörnyezetéről szóló jelentéseket hozhat létre."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e399c36d4c6a855766ee956b3ca24c503a1f974b
ms.sourcegitcommit: e57512698a479df0d25ece6ece4492ec0e4f0f3e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/19/2017
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
- A hivatkozást felhasználva készítsen egyéni jelentéseket a Power BI használatával. Ehhez a [Jelentés készítése az OData-adatcsatornából a Power BI használatával](reports-proc-create-with-odata.md) című témakörben talál útmutatót.
- Az Intune-adattárház API-ról, az adatmodellről és az entitások közötti kapcsolatokról, <!-- , and an example of creating a custom client to retrieve data,--> további információt az [Intune-adattárház API](reports-nav-intune-data-warehouse.md) című témakörben talál.