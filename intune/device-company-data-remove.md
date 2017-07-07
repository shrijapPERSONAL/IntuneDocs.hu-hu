---
title: "Céges adatok eltávolítása az Intune-ban felügyelt eszközökről"
titleSuffix: Intune on Azure
description: "Ismerje meg, hogyan távolíthatja el csak a céges adatokat az Intune-ban felügyelt eszközökről."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Céges adatok eltávolítása az Intune-ban felügyelt eszközökről


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A **Céges adatok eltávolítása** csak az Intune által kezelt céges adatokat távolítja el. Személyes adatokat nem távolít el az eszközről. Az eszköz a továbbiakban nem áll az Intune felügyelete alatt, és nem fér hozzá a vállalati erőforrásokhoz (nem támogatott az Azure Active Directory szolgáltatáshoz csatlakoztatott Windows-eszközökön).

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. Az eszközök listájából válassza ki az eszközt, majd válassza a **Céges adatok eltávolítása** távoli eszközműveletet.

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.
