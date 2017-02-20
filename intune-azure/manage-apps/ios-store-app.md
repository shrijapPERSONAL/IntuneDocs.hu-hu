---
title: "iOS áruházbeli alkalmazások hozzáadása az Intune-hoz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune Azure előzetes verzió: Útmutató iOS áruházbeli alkalmazások hozzáadásához az Intune-ban."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 01e5bfeb98aee9314fa04679cc27c8aba0e18fb0
ms.openlocfilehash: b29374c3abcca90de6cba7ed83866c04350f69c5

---

# <a name="how-to-add-ios-store-apps-to-intune"></a>iOS áruházbeli alkalmazások hozzáadása az Intune-hoz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---search-for-the-app-in-the-store"></a>1. lépés: Az alkalmazás megkeresése az áruházban

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + Felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Felügyelet** > Alkalmazások elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza a **Keresés az App Store-ban** lehetőséget.
7. Az **Apple App Store** panelen írja be a keresőmezőbe az alkalmazás nevét (vagy a név egy részét). Az Intune ekkor rákeres arra az áruházban, és a kapott eredmények listáját adja vissza.
8. Válassza ki a kívánt alkalmazást a listából, majd kattintson az **OK** gombra.

## <a name="step-2---configure-app-information"></a>2. lépés – Az alkalmazás adatainak konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
2. Az **Alkalmazás szerkesztése** panelen konfigurálja az alábbi információkat. Ha ezzel elkészült, kattintson a **Hozzáadás** lehetőségre. A választott alkalmazástól függően a panelen egyes értékek automatikusan kitöltődhetnek:
- **Alkalmazás neve** – Itt adhatja meg az alkalmazásnak a céges portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a vállalati portálon.
    - **Alkalmazás leírása** – Itt adhatja meg az alkalmazás leírását. amelyet meg szeretne jeleníteni a felhasználók számára a vállalati portálon.
- **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
- **App Store URL-cím** – Itt adhatja meg a létrehozni kívánt alkalmazás áruházbeli URL-címét.
- **Operációs rendszer minimálisan szükséges verziója** – A listából kiválaszthatja az operációs rendszer minimális verzióját, amelyre az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerrel rendelkező eszközhöz rendelik hozzá, akkor nem lesz telepítve.
- **Kategória** (nem kötelező). Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
- **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Az alkalmazás hangsúlyos megjelenítése a céges portál főoldalán alkalmazásokat kereső felhasználók számára.
- **Információs URL-cím** – Igény esetén megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
- **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
- **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
- **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét, például **HR osztály**.
- **Jegyzetek** – Ide gépelheti be az alkalmazáshoz társítani kívánt megjegyzéseket.
- **Ikon feltöltése** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a vállalati portálon böngésző felhasználók számára.
3. Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza a **Mentés** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](/intune-azure/manage-apps/deploy-apps).


<!--HONumber=Feb17_HO1-->


