---
title: "Feltételes hozzáférés a Microsoft Intune-nal"
titlesuffix: 
description: "Útmutató a felhasználókra, eszközökre és alkalmazásokra vonatkozó feltételek meghatározásához a vállalati adatok eléréséhez a Microsoft Intune-ban."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/06/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08589f3d9186699ce5241579cc1879be2d442e3d
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="whats-conditional-access"></a>Mi a feltételes hozzáférés?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A feltétles hozzáférés azokat a módszereket jelenti, amelyekkel vezérelheti az e-mail-fiókjához és a céges erőforrásaihoz való eszköz- és alkalmazás-hozzáférést. Ez a témakör az eszköz- és alkalmazásalapú feltételes hozzáférést ismerteti, valamint az Intune feltételes hozzáférésének gyakori használati eseteit mutatja be.

Az Enterprise Mobility + Security (EMS) feltételes hozzáférése nem önálló termék, hanem olyan megoldás, amely az EMS részét képező összes szolgáltatásban és a termékben megtalálható. A részletes hozzáférés-vezérlést biztosít a vállalati adatok védelméhez, miközben olyan felhasználói felületet nyújt, amely lehetővé teszi, hogy bármely eszközről, bárhonnan a lehető leghatékonyabban dolgozhassanak a felhasználók.

Olyan feltételeket adhat meg, amelyek a vállalati adatokhoz való hozzáférést helyszín, eszköz, felhasználói állapot vagy az alkalmazás bizalmassági szintje alapján korlátozzák.

> [!NOTE] 
> A feltételes hozzáférési funkciók kiterjednek az [Office 365-szolgáltatásokra](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/) is.

![A feltételes hozzáférés architekturális diagramja](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Feltételes hozzáférés az Intune-nal

Az Intune a mobileszköz-megfelelőség és az alkalmazás-felügyeleti szabályzatok hozzáadásával támogatja az EMS feltételes hozzáférési megoldását.

![Az Intune és a feltételes hozzáférés az EMS használata esetén](./media/intune-with-ca-1.png)

A feltételes hozzáférés használatának szokásos módjai az Intune-nal:

-   **Eszközalapú feltételes hozzáférés**

    -   Feltételes hozzáférés a helyszíni Exchange-hez

    -   Hálózati hozzáférés-vezérlésen alapuló feltételes hozzáférés

    -   Eszközkockázaton alapuló feltételes hozzáférés

    -   Feltételes hozzáférés Windows rendszerű számítógépeken

        -   Céges tulajdonú eszközök

        -   Saját eszközök használata (Bring Your Own Device, BYOD)

-   **Alkalmazásalapú feltételes hozzáférés**

## <a name="next-steps"></a>További lépések

[A feltételes hozzáférés szokásos módjai az Intune-nal](conditional-access-intune-common-ways-use.md)
