---
title: "Mobileszköz-felügyeleti szolgáltató megadása"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A mobileszköz-felügyeleti szolgáltató megadása az Intune-ban. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c36ddef7e53d6f4f15c82c97dc6d18863e6859f1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Mobileszköz-felügyeleti szolgáltató megadása

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A mobileszköz-felügyeleti (MDM-) szolgáltató beállítása szabja meg, hogy miként kezelheti mobileszközeit. Ahhoz, hogy a felhasználók felügyeletre tudják regisztrálni eszközeiket, a rendszergazdának be kell állítania egy MDM-szolgáltatót.

A lehetséges konfigurációk a következők:

- **Önálló Intune** – kizárólag felhőalapú felügyelet használata, amelyet az Azure Portal segítségével konfigurálhat. Az Intune-ban elérhető összes lehetőség a rendelkezésére áll. [MDM-szolgáltató beállítása az Intune-konzolon](#mdm-authority-set-to-intune).

- **Hibrid Intune** – az Intune felhőalapú megoldásainak integrációja a System Center Configuration Manager alkalmazásba. Az Intune-t a Configuration Manager konzolja segítségével konfigurálhatja. [MDM-szolgáltató beállítása a Configuration Managerben](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobileszköz-felügyelet az Office 365 használatával** – Az Office 365 és az Intune felhőalapú megoldásának integrációja. Az Intune-t az Office 365 Felügyeleti központ segítségével konfigurálhatja. Az önálló Intune-nal elérhető funkciók egy részét tartalmazza. MDM-szolgáltató beállítása az Office 365 felügyeleti központjában.

>[!IMPORTANT]
>Ha egyszer már beállított egy mobileszköz-felügyeleti szolgáltatót, a beállítás további változtatásához kapcsolatba kell lépnie a [Microsoft ügyfélszolgálatával](https://docs.microsoft.com/intune-classic/troubleshoot/get-support), ezért kérjük, körültekintően döntsön.

## <a name="set-mdm-authority-to-intune"></a>Az Intune beállítása MDM-szolgáltatóként

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
  ![Képernyőkép: az Intune Hibaelhárítás feladata a Felhasználó kijelölése hivatkozással](media/set-mdm-auth.png)
2. Az Intune panelen válassza az **Eszközregisztrálás**, majd pedig az **Áttekintés** elemet.

3. Az **Eszközök kezelésének indítása** panelen válassza **A Microsoft Intune beállítása mobileszköz-kezelő szolgáltatóként** lehetőséget. Egy üzenet jelzi, hogy az Intune-t sikeresen beállította mobileszköz-kezelő szolgáltatónak.

