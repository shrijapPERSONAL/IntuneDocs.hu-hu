---
title: "Exchange ActiveSync-alapú eszközkezelés"
description: "Mobileszközök kezelése Exchange ActiveSync (EAS) felügyelettel az Exchange-összekötő segítségével"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 02d6220a4c780eafb7afb01208e18e7df7684b68
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a>Exchange ActiveSync mobileszköz-felügyelet a Microsoft Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ahhoz, hogy a Microsoft Intune közvetlenül tudja felügyelni a mobileszközöket, [regisztrálni kell az eszközöket az Intune-ban](prerequisites-for-enrollment.md). A másik lehetőség, hogy a rendszergazdák engedélyeznek egy korlátozottabb felügyeleti megoldást, amely az Exchange ActiveSync (EAS) felügyeletet egy Exchange-összekötővel valósítja meg. Az eszközök helyszíni Exchange-kiszolgálókkal és az Office 365 segítségével az Exchange Online megoldással is felügyelhetők. Típustól függetlenül az Intune előfizetésenként csak egy Exchange-összekötő kapcsolatot támogat.

## <a name="exchange-access-rules-for-mobile-devices"></a>Mobileszközökre vonatkozó Exchange-hozzáférési szabályok ##

Az Exchange használatához olyan szabálykészletre van szükség, amely meghatározza, hogy mi történik akkor, amikor a mobileszközök csatlakozni próbálnak az Exchange ActiveSynchez. Ezeket a szabályokat az Intune felügyeleti konzol kezeli.

[Mobileszközökre vonatkozó Exchange-hozzáférési szabályok](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a>Az Exchange Connector telepítése
Az Exchange Connector lehetővé teszi az Exchange-telepítésnek az Intune-konzolon történő kezelését. Először el kell végeznie a megfelelő Intune-Exchange összekötő telepítését és beállítását. Válassza ki a megfelelő lehetőséget annak alapján, hogy helyszíni vagy felhőalapú szolgáltatásként üzemeltetett Exchange-kiszolgálót használ-e:

-   [Az Intune beállítása az Exchange Online vagy az új, dedikált Exchange Online környezetekhez](intune-service-to-service-exchange-connector.md)
-   [Az Intune-összekötő telepítése helyszíni Exchange-kiszolgálókhoz vagy a régebbi dedikált Exchange Online környezetekhez](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchange-managed-mobile-devices"></a>Exchange-felügyelet alatt álló mobileszközök szabályzatának alkalmazása
Az Intune-konzol használható az [EAS házirend-beállítások](exchange-activesync-policy-settings-in-microsoft-intune.md) kezelésére és a [vállalati erőforrásokhoz való hozzáférés korlátozására](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Az Exchange ActiveSync-szabályzat beállításainak és az egyes mobileszközök által támogatott funkciók listáját [az Exchange ActiveSync-ügyfelek összehasonlító táblázatában](http://go.microsoft.com/fwlink/?LinkId=247270) találja.

> [!NOTE]
> Az Intune Microsoft Exchange-környezethez való csatlakozását követően minden Intune-nal felügyelt felhasználó EAS-házirendje visszaáll a Microsoft Exchange-kiszolgáló aktuális alapértelmezett házirendjére, kivéve, ha az Intune-ban specifikusabb házirend lett meghatározva.

## <a name="wipe-company-data-from-mobile-devices"></a>Vállalati adatok törlése mobileszközökről
Végül [az EAS által felügyelt mobileszközökön tárolt vállalati adatokat törölheti](wipe-for-exchange-managed-mobile-devices.md), ha már nincsenek használatban, illetve ha elvesztették vagy ellopták az eszközt.
