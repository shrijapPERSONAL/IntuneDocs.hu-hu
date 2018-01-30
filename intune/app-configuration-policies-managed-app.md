---
title: "Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközbeléptetés nélkül | Microsoft Docs"
titlesuffix: Azure portal
description: "Megtudhatja, hogyan használhat alkalmazáskonfigurációs szabályzatokat felügyelt alkalmazásokhoz eszközbeléptetés nélkül."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c2266e460d816dfdd908d6a68944c8c2cc5c0afc
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt alkalmazásokhoz eszközbeléptetés nélkül

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az alkalmazáskonfigurációs szabályzatokat nem regisztrált eszközökön is használhatja az olyan felügyelt alkalmazásokkal, amelyek támogatják az Intune App SDK-t. 

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** + **Intune** lehetőséget.
3. Válassza a **Mobilalkalmazások** panelt.
4. Válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget a **Felügyelet** csoportban, majd a **Hozzáadás** lehetőséget.
5. Adja meg a következő adatokat:
    - **Név**  
      Az Azure Portalon megjelenő profilnév.
    - **Leírás**  
      Az Azure Portalon megjelenő profilleírás.
    - **Eszközbeléptetés típusa**  
      Válassza az **Alkalmazások kezelése** lehetőséget.
6. A konfigurálni kívánt alkalmazás kiválasztásához válassza a **Társított alkalmazás** lehetőséget. Válassza ki a listából azon alkalmazásokat, amelyeket jóváhagyott az Intune-nal való szinkronizáláshoz.
7. Az alkalmazás által támogatott konfigurációs beállítások mindegyikéhez írja be a **Nevet** és az **Értéket**, majd válassza a három pontot (**…**).  
    Egy konfiguráció törléséhez válassza a három pontot (**...** ), majd a **Törlés** lehetőséget.  
    Az Intune App SDK-val kompatibilis alkalmazások támogatják a kulcs-érték párokban megadott konfigurációkat. Ha többet szeretne megtudni a támogatott kulcs-érték párokban megadott konfigurációkról, tekintse meg az egyes alkalmazások dokumentációját.  
    Ezen kívül az alkalmazás által létrehozott adatokkal dinamikusan feltöltött tokeneket is használhat.

## <a name="configuration-values-for-using-tokens"></a>Konfigurációs értékek jogkivonatok használatához

Az Intune képes bizonyos jogkivonatokat generálni és elküldeni a felügyelt alkalmazásnak. Ha például az alkalmazáskonfiguráció használhat e-mail-beállítást, egy jogkivonattal dinamikus e-mailt adhat hozzá. Írja be az alkalmazás által várt nevet a **Név** mezőbe, majd írja be az **Érték** mezőbe az alábbi értéket: `\{\{mail\}\}`.

Az Intune a következő tokentípusokat támogatja a konfigurációs beállítások között:

- \{\{userprincipalname\}\} — például **John@contoso.com**
- \{\{mail\}\} — például **John@contoso.com**
- \{\{partialupn\}\} — például **János**
- \{\{accountid\}\} — például **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{userid\}\} — például **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\} — például **Szabó János**
- \{\{PrimarySMTPAddress\}\}– például**testuser@ad.domain.com** 


> [!Note]  
> A \{\{ és \}\} karaktereket csak a tokentípusok használják, ezek más célokra nem használhatók.

## <a name="next-steps"></a>További lépések

Ezt követően a szokott módon gondoskodhat az alkalmazás valamely csoporthoz történő [hozzárendeléséről](apps-deploy.md) és [figyeléséről](apps-monitor.md).