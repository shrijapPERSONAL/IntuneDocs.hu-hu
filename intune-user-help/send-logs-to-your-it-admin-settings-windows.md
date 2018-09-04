---
title: Windows 10-eszközök naplóinak küldése a cég informatikai támogatási szolgálatának | Microsoft Docs
description: Windows 10 1511 rendszerű eszköz regisztrálása az Intune-ban
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/25/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1e9b9908fcc48e9137c07f9a5397661d66e5be95
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43146739"
---
# <a name="send-logs-to-your-company-support-from-the-settings-app-for-windows-10"></a>Naplók küldése a cég informatikai támogatási szolgálatának a Windows 10 Gépház alkalmazásából

Ha a cég által felügyelt Windows 10-eszközén használat közben hibaüzenet jelenik meg, a probléma megoldásához e-mailben elküldheti a cég informatikai támogatási szolgálatának a hibával kapcsolatos információkat. Ezek az információk az eszközön tárolt, _diagnostic log_ (diagnosztikai napló) nevű speciális dokumentumban találhatók.

1. Nyissa meg a Windows **Gépház** alkalmazást a **Start menü** **Gépház** gombját kiválasztva. Kereshet a „Gépház” kifejezésre is a keresősávban.
2. Lépjen a **Fiókok** > **Hozzáférés munkahelyi vagy iskolai rendszerhez** pontra.
3. Válassza „A felügyeleti naplófájlok exportálása” lehetőséget.

   ![A „Hozzáférés munkahelyi vagy iskolai rendszerhez” képernyő, amelyen elérhető az Exportálás a „Kapcsolódó beállítások” fejléc alatt.](./media/w10-export-logs.png)

4. A naplókat a rendszer a **C:\Users\Public\Public Documents\MDMDiagnostics** könyvtárba menti. Két fájl jön létre: az egyik maga a napló, a másik egy speciális dokumentum, amely lehetővé teszi a rendszergazda számára, hogy a naplót különféle programokban tekinthesse meg, például a Microsoft Excelben. Csatolja mindkét fájlt egy e-mailhez, és küldje el az e-mailt a rendszergazdának. Ha ezt többször is megteszi, egyszerűen csak válassza ki a naplók létrehozási napján készül fájlokat. 

Szükség lehet [naplók küldésére a céges portál alkalmazásból](send-logs-to-your-it-admin-cp-windows.md) is, amivel segítséget nyújthat a cég informatikai támogatási szolgálatának az esetleges problémák megoldásához. 

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).
