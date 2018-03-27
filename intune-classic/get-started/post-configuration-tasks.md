---
title: Konfigurációt követő feladatok
description: Nem kötelező, de a mobileszköz-felügyelet működését javító konfigurációs feladatok elvégzése
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 05/11/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 34a412cd-8240-4e06-a60e-df270a711e7b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f65d7e55af7f1e8d84276ddd12a0a90cae70b54
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="post-configuration-tasks"></a>Konfigurációt követő feladatok

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A fizetős Intune előfizetés kezdeti konfigurációs lépéseinek elvégzését követően további mobileszköz-felügyeleti funkciók engedélyezését is érdemes megfontolnia.

-   **Az Exchange és az Intune összekapcsolása:** Az Intune-ban nem regisztrált mobileszközökkel rendelkező felhasználók esetében az Exchange ActiveSync-felügyelet a helyszíni Exchange és az Exchange Online összekötőjének használatával engedélyezhető a Microsoft Office 365 szolgáltatásban. Az Exchange Connector összeköttetést biztosít az Exchange-telepítéssel, és használatával mobileszközöket felügyelhet az Intune felügyeleti konzolon. Az Exchange-összekötővel kapcsolatban a [Mobileszköz-kezelés az Exchange ActiveSync és a Microsoft Intune használatával](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) című cikk nyújt további tájékoztatást.

-   **Intune-jelentések:** A Microsoft Intune olyan riasztásokat és jelentéseket biztosít, amelyek megkönnyítik az eszközök figyelését, valamint a szoftverlicencek állapotának és az eszközöket érintő műveleteknek (például az eszközön lévő adatok törlésének) a monitorozását.  A jelentésekkel kapcsolatos további információkért lásd: [A Microsoft Intune-műveletek értelmezése jelentések segítségével](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports).

-   **A vállalati erőforrások védelme:** Az Intune konfigurálását és az eszközök regisztrálását követően győződjön meg arról, hogy az eszközök védve vannak az adatvesztéssel és más fenyegetésekkel szemben. Az erőforrások védelméről az [Alkalmazások és adatok védelme a Microsoft Intune-nal](/intune-classic/deploy-use/protect-apps-and-data-with-microsoft-intune) című cikk nyújt további tájékoztatást.
