---
title: Szabályzatok a Windows rendszerű számítógépek védelméhez
titlesuffix: Microsoft Intune
description: Ezek a szabályzatok az Intune ügyfélszoftver által felügyelt Windows rendszerű számítógépek biztonságának megőrzését segítik elő.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: e91e19c17cb72725c8fe8c613dc41307f6cfecf6
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57234579"
---
# <a name="use-policies-to-help-protect-windows-pcs-that-run-the-intune-client-software"></a>Szabályzatok használata az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek védelméhez

[!INCLUDE [classic-portal](includes/classic-portal.md)]

A Microsoft Intune három olyan szabályzatot kínál, amelyek az [Intune ügyfélszoftver](manage-windows-pcs-with-microsoft-intune.md) által felügyelt Windows rendszerű számítógépek biztonságát segítik elő.


## <a name="software-updates"></a>Szoftverfrissítések

Az Intune megkönnyíti [a felügyelt Windows-számítógépek naprakészen tartását](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) azáltal, hogy értesítést küld a Microsoft és más vállalatok fontos, elérhetővé vált szoftverfrissítéseiről. Ezeket a frissítéseket elfogadhatja, de el is utasíthatja. A jóváhagyott frissítéseket a rendszer automatikusan telepíti minden megfelelő számítógépre.

## <a name="windows-firewall"></a>Windows tűzfal

A Windows tűzfal segít távol tartani a támadókat és a kártevőket a Windows rendszerű számítógépektől, illetve védelmet nyújt az egyéb fenyegetésekkel szemben. Az Intune segítségével valamennyi felügyelt számítógép [Windows-tűzfalbeállításait és -funkcióit kezelheti](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

## <a name="endpoint-protection"></a>Endpoint Protection

Rendszergazdaként egyik legfontosabb feladata a [kezelt Windows rendszerű számítógépek vírusoktól és kártevő szoftverektől mentesen tartása](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md). Az Endpoint Protection Intune-ba való integrálása valós idejű védelmet biztosít a veszélyes kártevők ellen, naprakészen tartja a kártevő-definíciókat, valamint automatikus vizsgálatokat végez a számítógépen. Az Endpoint Protection olyan eszközöket is biztosít, amelyek segítenek kezelni és megfigyelni a kártékony programok támadásait.

## <a name="see-also"></a>Lásd még:

[Gyakori kérdések, problémák és megoldások a szabályzatok és profilok](device-profile-troubleshoot.md)
