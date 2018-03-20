---
title: "Beépített alkalmazások hozzáadása mobileszközökhöz a Microsoft Intune-nal"
titlesuffix: 
description: "Annak ismertetése, hogyan egyszerűsíthető a beépített alkalmazások mobileszközökre való telepítése az Intune használatával."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7d90f86babc2f73acd5ccd1b454c636c6d4f79b2
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-built-in-apps-to-microsoft-intune"></a>Beépített alkalmazások hozzáadása a Microsoft Intune-hoz

A **beépített** alkalmazástípus megkönnyíti, hogy válogatott felügyelt alkalmazásokat, például Office 365-alkalmazásokat rendeljen iOS és Android-eszközökhöz. Az alkalmazástípushoz hozzárendelhet adott alkalmazásokat, például az Excel, a OneDrive, az Outlook, a Skype és egyéb alkalmazásokat. A felvett alkalmazások esetén a megjelenített alkalmazástípus **Beépített iOS-alkalmazás** vagy **Beépített Android-alkalmazás** lesz. A beépített alkalmazástípus használatával kiválaszthatja, hogy mely adott alkalmazásokat teszi közzé az eszköz felhasználóinak.

 Az Intune-konzol korábbi kiadásaiban az Intune több alapértelmezett felügyelt Office 365-alkalmazást is rendelkezésre bocsátott, például az Outlookot és a OneDrive-ot. Ezen felügyelt alkalmazások alkalmazástípusát a „Felügyelt iOS Store-alkalmazás” vagy „Felügyelt Android-alkalmazás” címke jelölte. Azt javasoljuk, hogy a beépített alkalmazástípust használja, és ne a „Felügyelt iOS Store-alkalmazás” vagy „Felügyelt Android-alkalmazás” típust. A beépített alkalmazástípus esetén rugalmasabban szerkeszthetők és törölhetők az Office 365-alkalmazások.

>[!NOTE]
>A „Felügyelt iOS Store” és „Felügyelt Android-alkalmazás” címkével rendelkező alapértelmezett Office 365-alkalmazásokat az összes hozzárendelés törlése esetén a rendszer eltávolítja az alkalmazáslistából.

## <a name="add-built-in-app"></a>Beépített alkalmazás hozzáadása

A következő lépésekkel adhat hozzá egy beépített alkalmazást az elérhető alkalmazásokhoz a Microsoft Intune-ban.
1.  Jelentkezzen be az Azure Portalra.
2.  A Microsoft Intune panel megjelenítéséhez válassza a **További szolgáltatások** > **Monitoring és felügyelet** > **Intune** lehetőséget.
3.  Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4.  A **Mobilalkalmazások** panelen válassza a **Kezelés** csoport **Alkalmazások** elemét.
5.  Válassza a **Hozzáadás** lehetőséget egy új alkalmazás hozzáadására.
6.  A **Hozzáadás** alkalmazáspanelen az **Alkalmazástípus** listából válassza a **Beépített alkalmazás** elemet.
7.  A felveendő beépített alkalmazások kiválasztásához kattintson az **Alkalmazás kiválasztása** lehetőségre.
8.  A Beépített alkalmazás panelen válassza ki a belefoglalni kívánt alkalmazásokat.
9.  Az **Alkalmazás felvétele** panelen kattintson a **Hozzáadás** gombra az alkalmazások belefoglalásához.


## <a name="configure-app-information"></a>Az alkalmazásadatok konfigurálása

Módosíthatja a beépített alkalmazással kapcsolatos információkat. Ezek révén azonosíthatja az alkalmazást az Intune-ban, és segítségükkel a végfelhasználó is könnyebben megtalálhatja azt a Céges portál alkalmazásban.
1.  A **Mobilalkalmazások – Alkalmazások** panelen válassza ki a módosítani kívánt beépített alkalmazást. Ekkor megjelenik a beépített alkalmazás panelje.
2.  A **Kezelés** csoportban válassza a **Tulajdonságok** parancsot.
3.  A beépített alkalmazás adatainak módosításához válassza a **Konfigurálás** lehetőséget.
4.  Az **Alkalmazásadatok** panelen adja meg az alábbi információkat:
    -   **Név** – Itt adhatja meg a beépített alkalmazás a céges portálon megjelenő nevét. Ügyeljen arra, hogy csak egyedi neveket használjon. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    -   **Leírás** – Itt adhatja meg az alkalmazás leírását. 
    -   **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    -   **Kategória** – Szükség esetén választhat egyet vagy többet a beépített alkalmazáskategóriák közül. A beállítás megadásával megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    -   **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    -   **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    -   **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    -   **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    -   **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például HR-osztály).
    -   **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    -   **Ikon feltöltése** – Feltölthet egy ikont, mely megjelenik az alkalmazással a céges portálon böngésző felhasználók számára.
3.  Ha elkészült, az **Alkalmazásadatok** panelen kattintson az **OK** gombra.
4.  A **Tulajdonságok** panelen kattintson a **Mentés** gombra.

## <a name="next-steps"></a>További lépések

- Mostantól hozzárendelheti az alkalmazásokat a kiválasztott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).
