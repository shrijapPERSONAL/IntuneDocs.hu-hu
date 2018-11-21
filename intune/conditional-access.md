---
title: Feltételes hozzáférés a Microsoft Intune-nal
titlesuffix: ''
description: Útmutató a felhasználókra, eszközökre és alkalmazásokra vonatkozó feltételek meghatározásához a vállalati adatok eléréséhez a Microsoft Intune-ban.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: 1e9e8db76978f9547d10fd4709d74ea809f2c281
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184845"
---
# <a name="whats-conditional-access"></a>Mi a feltételes hozzáférés?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A feltétles hozzáférés azokat a módszereket jelenti, amelyekkel vezérelheti az e-mail-fiókjához és a céges erőforrásaihoz való eszköz- és alkalmazás-hozzáférést. Ez a témakör az eszköz- és alkalmazásalapú feltételes hozzáférést ismerteti, valamint az Intune feltételes hozzáférésének gyakori használati eseteit mutatja be.

Az Enterprise Mobility + Security (EMS) feltételes hozzáférése nem önálló termék, hanem olyan megoldás, amely az EMS részét képező összes szolgáltatásban és a termékben megtalálható. A részletes hozzáférés-vezérlést biztosít a vállalati adatok védelméhez, miközben olyan felhasználói felületet nyújt, amely lehetővé teszi, hogy bármely eszközről, bárhonnan a lehető leghatékonyabban dolgozhassanak a felhasználók.

Olyan feltételeket adhat meg, amelyek a vállalati adatokhoz való hozzáférést helyszín, eszköz, felhasználói állapot vagy az alkalmazás bizalmassági szintje alapján korlátozzák.

> [!NOTE] 
> A feltételes hozzáférési funkciók kiterjednek az [Office 365-szolgáltatásokra](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/) is.

![A feltételes hozzáférés architekturális diagramja](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Feltételes hozzáférés az Intune-nal

A feltételes hozzáférés az Azure Active Directory egyik lehetősége, amelyet a prémium szintű Azure Active Directory-licencek biztosítanak. Az Intune ezt a lehetőséget mobileszköz-megfelelőségi és mobilalkalmazás-felügyeleti megoldások hozzáadásával bővíti tovább. 

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
