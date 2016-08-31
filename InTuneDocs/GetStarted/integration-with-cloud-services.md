---
title: "Intune-integráció a Microsoft felhőszolgáltatásaival | Microsoft Intune"
description: "Intune-integráció a Microsoft felhőszolgáltatásaival és termékeivel, valamint más Microsoft-termékekkel"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: 83020d347a4bc036778d830f5189e68e7f8d85da


---

# Intune-integráció a Microsoft más felhőszolgáltatásaival és termékeivel

A [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] beállítása előtt olvassa el ezt a témakört, valamint ismerkedjen meg a [Tudnivalók a Microsoft Intune elindítása előtt](what-to-know-before-you-start-microsoft-intune.md) című témakörben leírt követelményekkel.
##Integráció a Microsoft más felhőszolgáltatásaival


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a Microsoft más felhőszolgáltatásaival közös alaprendszert használ. Amikor ugyanazzal a fiókkal fizet elő több felhőszolgáltatásra, ezek a szolgáltatások ugyanazt a Microsoft Azure AD-infrastruktúrát használják, és az Azure AD bérlői. Az Azure AD alapvető fontosságú címtár- és identitáskezelési funkciókat biztosít a Microsoft felhőszolgáltatásai számára.

Az [Azure AD felügyeletéről](http://technet.microsoft.com/library/hh967611.aspx) a TechNet könyvtárban olvashat bővebben.

## Integráció más Microsoft-termékekkel
A [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] szolgáltatás használható önálló felhőszolgáltatásként vagy más termékekkel integrált felhőszolgáltatásként is. Jelenleg csak a [!INCLUDE[cmshort](../includes/cmshort_md.md)] integrálható közvetlenül az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] szolgáltatással.

Az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a [!INCLUDE[cmshort](../includes/cmshort_md.md)] alkalmazással való integrálása végleges döntés, melyhez a [!INCLUDE[cmshort](../includes/cmshort_md.md)] helyett a [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] konzolon szükséges beállítani a mobileszköz-kezelő szolgáltatót. A mobileszköz-kezelő szolgáltató beállítása után ez a beállítás nem módosítható vagy vonható vissza.

Az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] a [!INCLUDE[cmshort](../includes/cmshort_md.md)]rel való használatakor, az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kezeléséhez a [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] helyett a [!INCLUDE[cmshort](../includes/cmshort_md.md)] konzolt használja. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] továbbra is az Azure-ban található felhőbeli tárhelyét használja az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-nal kezelt eszközökre telepített szoftverek üzemeltetéséhez.

További információk a [!INCLUDE[cm5short](../includes/cm5short_md.md)] SP1 dokumentációjának [Mobileszközök kezelése a Configuration Manager és a Microsoft Intune használatával](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) című témakörében találhatók.

### További információ
[Tudnivalók a Microsoft Intune elindítása előtt](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


