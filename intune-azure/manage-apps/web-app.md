---
title: "Webalkalmazások hozzáadása az Intune-hoz"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Útmutató webalkalmazásoknak az Intune-hoz való hozzáadásához."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 842aafd3395f7a7133f49b75a43eaaa2c6465619
ms.contentlocale: hu-hu
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Webalkalmazások hozzáadása az Intune-hoz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
7. Az **Alkalmazás szerkesztése** panelen konfigurálja az alábbi információkat. Ha ezzel elkészült, kattintson a **Hozzáadás** lehetőségre:
    - **Alkalmazás URL-címe** – Adja meg annak a webhelynek az URL-címét, amelyen a hozzárendelni kívánt alkalmazás található.
    - **Alkalmazás neve** – Itt adhatja meg az alkalmazásnak a Céges portálon megjelenő nevét.
    - **Alkalmazás leírása** – Itt adhatja meg az alkalmazás leírását. Ez fog megjelenni a felhasználók számára a céges portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Kategória (nem kötelező)** – Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Felügyelt böngésző szükséges a hivatkozás megnyitásához** – Ha egy webhelyre vagy webalkalmazásra mutató hivatkozást rendel a felhasználókhoz, az csak az Intune által felügyelt böngészőben lesz megnyitható. Ezt a böngészőt telepíteni kell az eszközökön.
    - **Ikon feltöltése** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a vállalati portálon böngésző felhasználók számára.
8. Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza a **Mentés** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](deploy-apps.md).
