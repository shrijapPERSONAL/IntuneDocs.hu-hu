---
title: "A mobileszköz-felügyeleti szolgáltató megadása | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A mobileszköz-felügyeleti szolgáltató megadása az Intune-ban. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 72a162175e278faa236add5698d65233fa851c7b

---

# <a name="set-the-mobile-device-management-authority"></a>Mobileszköz-felügyeleti szolgáltató megadása 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A mobileszköz-felügyeleti szolgáltató beállítás szabja meg, hogy miként kezelheti mobileszközeit. A lehetséges konfigurációk a következők:

- **Önálló Intune** – kizárólag felhőalapú felügyelet használata, amelyet az Azure Portal segítségével konfigurálhat. Az Intune-ban elérhető összes lehetőség a rendelkezésére áll.

- **Hibrid Intune** – az Intune felhőalapú megoldásainak integrációja a System Center Configuration Manager alkalmazásba. Az Intune-t a Configuration Manager konzolja segítségével konfigurálhatja.

- **Mobileszköz-felügyelet az Office 365 használatával** – Az Office 365 és az Intune felhőalapú megoldásának integrációja. Az Intune-t az Office 365 Felügyeleti központ segítségével konfigurálhatja. Az önálló Intune-nal elérhető funkciók egy részét tartalmazza.

>[!IMPORTANT]
>Ha egyszer már beállított egy mobileszköz-felügyeleti szolgáltatót, a beállítás további változtatásához kapcsolatba kell lépnie a [Microsoft ügyfélszolgálatával](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune), ezért kérjük, körültekintően döntsön.

**A mobileszköz-felügyeleti szolgáltató beállítása:**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Áttekintés** elemet.

3. Az **Eszközök kezelésének indítása** panelen válassza **A Microsoft Intune beállítása mobileszköz-kezelő szolgáltatóként** lehetőséget. Egy üzenet jelzi, hogy az Intune-t sikeresen beállította mobileszköz-kezelő szolgáltatónak.



<!--HONumber=Feb17_HO3-->


