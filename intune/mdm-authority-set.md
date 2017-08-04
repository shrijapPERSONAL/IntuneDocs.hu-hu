---
title: "Mobileszköz-felügyeleti szolgáltató megadása"
titleSuffix: Intune on Azure
description: "A cikk azt ismerteti, hogyan állítható be a mobileszköz-felügyeleti szolgáltató az Intune-ban. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 97dede1ac393a434342f62d1f8488389dcb28d44
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Mobileszköz-felügyeleti szolgáltató megadása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A mobileszköz-felügyeleti (MDM-) szolgáltató beállítása szabja meg, hogy miként kezelheti mobileszközeit. Ahhoz, hogy a felhasználók felügyeletre tudják regisztrálni eszközeiket, a rendszergazdának be kell állítania egy MDM-szolgáltatót.

A lehetséges konfigurációk a következők:

- **Önálló Intune** – kizárólag felhőalapú felügyelet használata, amelyet az Azure Portal segítségével konfigurálhat. Az Intune-ban elérhető összes lehetőség a rendelkezésére áll. [MDM-szolgáltató beállítása az Intune-konzolon](#set-mdm-authority-to-intune).

- **Hibrid Intune** – az Intune felhőalapú megoldásainak integrációja a System Center Configuration Manager alkalmazásba. Az Intune-t a Configuration Manager konzolja segítségével konfigurálhatja. [MDM-szolgáltató beállítása a Configuration Managerben](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobileszköz-felügyelet az Office 365 használatával** – Az Office 365 és az Intune felhőalapú megoldásának integrációja. Az Intune-t az Office 365 Felügyeleti központ segítségével konfigurálhatja. Az önálló Intune-nal elérhető funkciók egy részét tartalmazza. MDM-szolgáltató beállítása az Office 365 felügyeleti központjában.

>[!IMPORTANT]    
A Configuration Manager 1610-es vagy későbbi verziójában és a Microsoft Intune 1705-ös verziójában anélkül módosíthatja az MDM-szolgáltatót, hogy fel kellene vennie a kapcsolatot a Microsoft ügyfélszolgálatával, valamint anélkül, hogy el kellene végeznie a meglévő felügyelt eszközök regisztrációjának törlését és a regisztráció újbóli elvégzését. További információért tekintse meg a [Mi a teendő, ha nem a megfelelő MDM-szolgáltatót választotta?](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) című részt.

## <a name="set-mdm-authority-to-intune"></a>Az Intune beállítása MDM-szolgáltatóként

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
  ![Képernyőkép: az Intune Hibaelhárítás feladata a Felhasználó kijelölése hivatkozással](media/set-mdm-auth.png)
2. Az Intune panelen válassza az **Eszközregisztrálás**, majd pedig az **Áttekintés** elemet.

3. Az **Eszközök kezelésének indítása** panelen válassza **A Microsoft Intune beállítása mobileszköz-kezelő szolgáltatóként** lehetőséget. Egy üzenet jelzi, hogy az Intune-t sikeresen beállította mobileszköz-kezelő szolgáltatónak.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.
