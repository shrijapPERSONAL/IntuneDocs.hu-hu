---
title: "Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközbeléptetés nélkül | Microsoft Docs"
titlesuffix: Azure portal
description: "Megtudhatja, hogyan használhat alkalmazáskonfigurációs szabályzatokat felügyelt alkalmazásokhoz eszközbeléptetés nélkül."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 750ce7dbb0dccf08757e076826e2d3650b6e6ab5
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközbeléptetés nélkül

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az alkalmazáskonfigurációs szabályzatokat nem regisztrált eszközökön is használhatja az olyan felügyelt alkalmazásokkal, amelyek támogatják az Intune App SDK-t. 

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** + **Intune** lehetőséget.
3. Válassza a **Mobilalkalmazások** panelt.
4. A **Felügyelet** csoportban válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget, majd kattintson a **Hozzáadás** gombra.
5. Adja meg a következő adatokat:
    - **Név**  
      Az Azure Portalon megjelenő profilnév.
    - **Leírás**  
      Az Azure Portalon megjelenő profilleírás.
    - **Eszközbeléptetés típusa**  
      Válassza az **Alkalmazások kezelése** lehetőséget.
6. A konfigurálni kívánt alkalmazás kiválasztásához válassza a **Társított alkalmazás** lehetőséget. Válassza ki a listából azon alkalmazásokat, amelyeket jóváhagyott az Intune-nal való szinkronizáláshoz.
7. Az alkalmazás által támogatott konfigurációs beállításokhoz írja be a **Név** és az **Érték** adatokat, majd kattintson a három pontra (**…**).  
    Egy konfiguráció törléséhez kattintson a három pontra (**...** ), és válassza a **Törlés** lehetőséget.  
    Az Intune App SDK-kompatibilis alkalmazások támogatják a kulcs-érték pár konfigurációit. Ha többet szeretne megtudni a támogatott kulcs-érték párok konfigurációiról, tekintse meg az egyes alkalmazások dokumentációját.  
    Ezen kívül az alkalmazás által létrehozott adatokkal dinamikusan feltöltött tokeneket is használhat.

## <a name="configuration-values-using-tokens"></a>Tokeneket használó konfigurációs értékek

Az Intune létrehozhat és elküldhet egyes tokeneket a felügyelt alkalmazásnak. Ha például az alkalmazáskonfigurációja használhat e-mail beállítást, tokennel dinamikus e-mailt adhat hozzá. Írja be az alkalmazás által várt nevet a **Név** mezőbe, majd írja be az **Érték** mezőbe az alábbi értéket: `\{\{mail\}\}`.

Az Intune a következő tokentípusokat támogatja a konfigurációs beállítások között:

- \{\{userprincipalname\}\} – (példa: **John@contoso.com**)
- \{\{mail\}\} – (példa: **John@contoso.com**)
- \{\{partialupn\}\} – (Példa: **János**)
- \{\{accountid\}\} – (Példa: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Példa: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Példa: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Példa: **Kovács János**)
- \{\{PrimarySMTPAddress\}\} – (Példa: testuser@ad.domain.com) 


> [!Note]  
> A \{\{ és \}\} karaktereket csak a tokentípusok használják, ezek más célokra nem használhatók.

## <a name="next-steps"></a>További lépések

Ezt követően a szokott módon gondoskodhat az alkalmazás valamely csoporthoz történő [hozzárendeléséről](apps-deploy.md) és [figyeléséről](apps-monitor.md).