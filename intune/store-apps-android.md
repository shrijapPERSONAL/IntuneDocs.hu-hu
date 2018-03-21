---
title: "Androidos áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz"
titleSuffix: 
description: "Útmutató Android Áruházbeli alkalmazások a Microsoft Intune-ba való hozzáadásához."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 87fea551dea1f80ee071fe6b477b84729e000874
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Androidos áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mielőtt az alkalmazást hozzárendelné egy eszközhöz vagy felhasználói csoporthoz, az eszközt először hozzá kell adnia a Microsoft Intune-hoz. Az alábbi lépések azt mutatják be, hogyan adhat hozzá az Intune-hoz áruházból származó Android-alkalmazást az Azure Portalon.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** területen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **alkalmazás hozzáadása** panelen az **Áruházbeli alkalmazás** elérhető típusai közül válassza az **Android** lehetőséget.
7. A **Konfigurálás** választásával a következő alkalmazásinformációkat adhatja meg: A választott alkalmazástól függően előfordulhat, hogy bizonyos információk már automatikusan kitöltve jelennek meg a panelen:
    - **Név** – Itt adhatja meg az alkalmazásnak a vállalati portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a vállalati portálon.
    - **Leírás** – Itt adhatja meg az alkalmazás leírását. A leírás a céges portálon megjelenik a felhasználóknak.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás-áruház URL-címe** – Itt adhatja meg a létrehozni kívánt alkalmazás áruházbeli URL-címét.
    - **Minimális operációsrendszer-verzió** – A listából kiválaszthatja az operációs rendszer legkorábbi olyan verzióját, amelyre az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerrel rendelkező eszközhöz rendelik hozzá, akkor nem lesz telepítve.
    - **Kategória (nem kötelező)** – Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** (nem kötelező) – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Adatvédelmi nyilatkozat URL-címe** (nem kötelező) – Itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Fejlesztő** (nem kötelező) – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos** (nem kötelező) – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR osztály**).
    - **Megjegyzések** (nem kötelező) – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon** (nem kötelező) – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a céges portálon böngésző felhasználók számára.
8. Az alkalmazásinformációk megadása után kattintson az **OK** lehetőségre.
9. Az alkalmazás hozzáadásához kattintson a **Hozzáadás** gombra.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. 

##<a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)