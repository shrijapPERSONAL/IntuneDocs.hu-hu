---
title: "Webalkalmazások hozzáadása a Microsoft Intune-hoz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató webalkalmazások hozzáadásához az Intune-ban."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4188957e263717d416853f308a50e3dbd7a9244a
ms.openlocfilehash: 4f8af0008300550d284957c1002be779e0e53f79

---

# <a name="how-to-add-web-apps-to-intune"></a>Webalkalmazások hozzáadása az Intune-hoz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + Kezelés** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
7. Az **Alkalmazás szerkesztése** panelen konfigurálja az alábbi információkat. Ha ezzel elkészült, kattintson a **Hozzáadás** lehetőségre:
    - **Alkalmazás URL-címe** – Adja meg annak a webhelynek az URL-címét, amelyen a telepíteni kívánt alkalmazás található.
    - **Alkalmazás neve** – Itt adhatja meg az alkalmazásnak a céges portálon megjelenő nevét.
    - **Alkalmazás leírása** – Itt adhatja meg az alkalmazás leírását. Ez fog megjelenni a felhasználók számára a céges portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Kategória (nem kötelező)** – Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a vállalati portálon:** – Az alkalmazás hangsúlyos megjelenítése a vállalati portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Felügyelt böngésző szükséges a hivatkozás megnyitásához** – Ha egy webhelyre vagy webalkalmazásra mutató hivatkozást telepít a felhasználók számára, az csak az Intune által felügyelt böngészőben lesz megnyitható. Ezt a böngészőt telepíteni kell az eszközökön.
    - **Ikon feltöltése** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a vállalati portálon böngésző felhasználók számára.
8. Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza a **Mentés** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](/intune-azure/manage-apps/deploy-apps).


<!--HONumber=Feb17_HO1-->


