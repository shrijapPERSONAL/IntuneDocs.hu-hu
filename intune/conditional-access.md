---
title: "Feltételes hozzáférés az Intune-nal"
titlesuffix: Azure portal
description: "Útmutató a felhasználókra és eszközökre vonatkozó feltételek meghatározásához a vállalati adatok eléréséhez a Microsoft Intune-ban.”"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 970b84c51c994b5917a87992de2eae666c94c027
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="whats-conditional-access"></a>Mi a feltételes hozzáférés?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör ismerteti az Enterprise Mobility + Security (EMS) szolgáltatásra vonatkozó feltételes hozzáférést, majd általános példákat ad a feltételes hozzáférésre alkalmazására az Intune használata során.

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