---
title: Beépített alkalmazások hozzáadása mobileszközökhöz a Microsoft Intune-nal
titleSuffix: ''
description: Annak ismertetése, hogyan egyszerűsíthető a beépített alkalmazások mobileszközökre való telepítése az Intune használatával.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f46cd1295c9ecf593765cf26f4c8685eccbffa0
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61506831"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Beépített alkalmazások hozzáadása a Microsoft Intune-hoz

A *beépített* alkalmazástípus megkönnyíti, hogy válogatott felügyelt alkalmazásokat, például Office 365-alkalmazásokat rendeljen iOS és Android-eszközökhöz. Az alkalmazástípushoz hozzárendelhet adott alkalmazásokat, például az Excel, a OneDrive, az Outlook, a Skype és egyéb alkalmazásokat. Alkalmazás hozzáadása után a megjelenített alkalmazástípus *Beépített iOS-alkalmazás* vagy *Beépített Android-alkalmazás* lesz. A beépített alkalmazástípus használatával kiválaszthatja, hogy mely alkalmazásokat teszi közzé az eszköz felhasználóinak.

Az Intune-konzol korábbi verzióiban az Intune több alapértelmezett felügyelt Office 365-alkalmazást is rendelkezésre bocsátott, például az Outlookot és a OneDrive-ot. Ezen felügyelt alkalmazások alkalmazástípusát a *Felügyelt iOS Store-alkalmazás* vagy *Felügyelt Android-alkalmazás* címke jelölte. Ajánlott ezek helyett a beépített alkalmazástípust használni. A beépített alkalmazástípus használatával rugalmasabban szerkeszthetők és törölhetők az Office 365-alkalmazások.

>[!NOTE]
>A *Felügyelt iOS Store* és *Felügyelt Android-alkalmazás* címkével rendelkező alapértelmezett Office 365-alkalmazásokat az összes hozzárendelés törlése esetén a rendszer eltávolítja az alkalmazáslistából.

## <a name="add-a-built-in-app"></a>Beépített alkalmazás hozzáadása

Beépített alkalmazást a következő módon adhat hozzá az elérhető alkalmazásokhoz a Microsoft Intune-ban:
1. Jelentkezzen be az Azure portálra.
2. A Microsoft Intune panel megjelenítéséhez válassza a **További szolgáltatások** > **Figyelés és felügyelet** > **Intune** lehetőséget.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** panelen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen az **Alkalmazástípus**-listából válassza a **Beépített alkalmazás** lehetőséget.
7. Válassza az **Alkalmazás kiválasztása** lehetőséget.
8. A **Beépített alkalmazás** panelen jelölje ki a belefoglalni kívánt alkalmazásokat.
9. Az **Alkalmazás hozzáadása** panelen válassza a **Hozzáadás** lehetőséget.


## <a name="configure-app-information"></a>Az alkalmazásadatok konfigurálása

Módosíthatja a beépített alkalmazással kapcsolatos információkat. Ezek révén azonosíthatja az alkalmazást az Intune-ban, és segítségükkel a felhasználók is könnyebben megtalálhatják azt a Céges portál alkalmazásban.
1. Az a **ügyfélalkalmazások - alkalmazások** ablaktáblán válassza ki a beépített alkalmazást, amelyet módosítani szeretne.  
    Megjelenik a beépített alkalmazás panelje.
2. A **Kezelés** alatt válassza a **Tulajdonságok** lehetőséget.
3. A beépített alkalmazás adatainak módosításához válassza a **Konfigurálás** lehetőséget.
4. Az **Alkalmazásadatok** panelen adja meg az alábbi információkat:
    - **Név**: Adja meg a beépített alkalmazás nevét, a vállalati portálon megjelenített formában. Ügyeljen arra, hogy csak egyedi neveket használjon. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    - **Description** (Leírás): Adja meg az alkalmazás leírását. 
    - **Közzétevő**: Itt adhatja meg az alkalmazás kiadójának nevét.
    - **Kategória**: Kiválaszthat egyet vagy többet a beépített Alkalmazáskategóriák közül. A beállítás megadásával megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a céges portálon**: Az alkalmazás jól észrevehető módon való megjelenítése a vállalati portál fő lapján, amikor a felhasználók tallózással alkalmazásokat keresnek.
    - **Információs URL-cím**: Nem kötelező: megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi URL-címe**: Nem kötelező: megadhatja az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztői**: Megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Szükség esetén adja meg az alkalmazás tulajdonosának nevét (például *HR részleg*).
    - **Megjegyzések**: Adja meg az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon feltöltése**: Töltse fel egy ikont, mely megjelenik az alkalmazással a céges portálon böngésző felhasználók számára.
4. Kattintson az **OK** gombra.
5. A **Tulajdonságok** panelen válassza a **Mentés** lehetőséget.

## <a name="next-steps"></a>További lépések

- Mostantól hozzárendelheti az alkalmazásokat a kiválasztott csoportokhoz. További információ: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).
