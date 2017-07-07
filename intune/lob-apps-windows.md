---
title: "Üzletági Windows-alkalmazások felvétele az Intune-ba"
titleSuffix: Intune on Azure
description: "Útmutató az üzletági Windows-alkalmazások Intune-ba való felvételéhez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f8be4f6bf47ceb966e9042465dc8839d9aa9119
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Windows rendszerű üzletági (LOB) alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>1. lépés – A szoftvertelepítő fájl megadása

1. Jelentkezzen be az Azure Portal webhelyre.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget.

## <a name="step-2---configure-the-app-package-file"></a>2. lépés – az alkalmazáscsomag-fájl konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazáscsomag** fájlt.
2. Az **Alkalmazáscsomag** panelen válassza a tallózás gombot, majd válasszon egy **.msi** kiterjesztésű Windows telepítési fájlt (más telepítési fájltípusok nem támogatottak).
3. Ha elkészült, válassza az **OK** elemet.


## <a name="step-3---configure-app-information"></a>3. lépés – Az alkalmazás adatainak konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazáscsomag** fájlt.
2. Az **Alkalmazás adatai** panelen adja meg az alábbi információkat. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név** – Itt adhatja meg az alkalmazásnak a vállalati portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a vállalati portálon.
    - **Leírás** – Itt adhatja meg az alkalmazás leírását. amelyet meg szeretne jeleníteni a felhasználók számára a vállalati portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Kategória** – Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Parancssori argumentumok** – Igény esetén parancssori argumentumokat adhat meg, amelyeket az .msi fájl futtatásakor kíván alkalmazni, mint például **/q**.
    - **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a vállalati portálon böngésző felhasználók számára.
3. Ha elkészült, válassza az **OK** elemet.

## <a name="step-4---finish-up"></a>4. lépés – befejezés

1. Az **Alkalmazás hozzáadása** panelen ellenőrizze, hogy helyesek-e a megadott információk.
2. Az alkalmazást a **Hozzáadás** elem kiválasztásával töltheti fel az Intune-ba.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).
