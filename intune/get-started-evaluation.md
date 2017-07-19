---
title: "Bevezetés az Intune használatába"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="what-is-microsoft-intune"></a>Mi az a Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![A Microsoft Intune az Azure Portalon](./media/generic-intune-azure.png)

A Microsoft Intune az Azure egyik legújabb szolgáltatása. Eszközöket és [rendszeresen frissített](whats-new.md) alkalmazásokat kínál a vállalat mobileszközeinek és számítógépeinek kezeléséhez. Az Intune a modern Azure-konzol mellet a klasszikus konzol használatát is lehetővé teszi. A klasszikus konzol az Intune első verziója, és a [windowsos számítógépek Intune-szoftverügyféllel történő kezelését](/intune-classic/deploy-use/pc-management-comparison.md) továbbra is ezen végezheti. A Silverlightra épülő klasszikus portál kevés számú feladat végzésére használatos. Minden mást, többek között a mobileszközök és alkalmazások kezelését az Azure Portalon lehet elvégezni. Az első lépésekről szóló útmutató végigvezeti az Intune Azure Portalon való használatához elvégzendő alapvető feladatokon.

![Az Intune bal oldalsávjában a műveleti lista alján elérhető súgó és támogatás panel.](./media/intune-azure-help-support-closeup.png)

## <a name="what-does-intune-in-the-azure-portal-provide"></a>Milyen szolgáltatásokat nyújt az Intune az Azure Portalon?

Az Intune az Azure Portalon a következőket biztosítja:

* Integrált konzol az [Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security) összes biztonsági összetevőjéhez
* A [modern webböngészőket](supported-devices-browsers.md) támogató webes szabványokra épülő HTML-alapú konzol
* [Azure Active Directory-csoportok](groups-get-started.md) az Azure-os alkalmazások közötti kompatibilitás érdekében
* Automatizálás a [Microsoft Graph API-val](intune-graph-apis.md)

## <a name="prerequisites"></a>Előfeltételek

A kezdéshez aktivált Intune-rendszergazdai és -bérlői fiókkal kell rendelkeznie. Ezekre a fiókokra [itt](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) regisztrálhat. A jelenlegi előfizetők az élő bérlőben is elvégezhetik ezeket a tevékenységeket. Csak teszteszközökön dolgozzon!

Az útmutató összes feladatának elvégzéséhez az is szükséges, hogy Ön a vállalatának globális rendszergazdája legyen.
