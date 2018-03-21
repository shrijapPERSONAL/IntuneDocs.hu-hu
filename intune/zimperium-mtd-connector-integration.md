---
title: "A Zimperium MTD integrálása a Microsoft Intune-nal"
titleSuffix: 
description: "A Zimperium Mobile Threat Defense (MTD) beállítása a Microsoft Intune-ban a mobileszközök a vállalati erőforrásokhoz való hozzáférésének kezeléséhez."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fada315aad9bce47a3a04286d84e1c7dbdd2ce61
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="integrate-zimperium-with-intune"></a>A Zimperium integrálása az Intune-nal

A Zimperium mobilfenyegetések elleni megoldás Intune-beli integrálásához kövesse az alábbi lépéseket.

## <a name="before-you-begin"></a>Előkészületek

> [!NOTE]
> Az alábbi lépéseket a [Zimperium MTD konzolon](https://staging2-console.zimperium.com) kell végrehajtania.

Mielőtt elkezdené a Zimperium integrálását az Intune-nal, ellenőrizze, hogy rendelkezik-e az alábbi előfizetéssel és hitelesítő adatokkal:

-   Microsoft Intune-előfizetés

-   Azure Active Directory rendszergazdai hitelesítő adatok a következő engedélyek megadására:

    -   Bejelentkezés és felhasználói profil olvasása

    -   A címtár elérése a bejelentkezett felhasználó nevében

    -   Címtáradatok olvasása

    -   Eszközadatok küldése az Intune-ba

-   Rendszergazdai hitelesítő adatok a Zimperium MTD konzol eléréséhez.

### <a name="zimperium-app-authorization"></a>A Zimperium alkalmazás engedélyezése

A Zimperium alkalmazás engedélyezési folyamata a következő:

-   Engedélyezze a Zimperium szolgáltatásnak, hogy az eszközállapottal kapcsolatos információt küldhessen az Intune-ba.

-   A Zimperium szinkronizálást végez az Azure Active Directory (AD) regisztrációs csoporttagsággal az eszköz adatbázisának feltöltéséhez.

-   Engedélyezze a Zimperium felügyeleti konzolja számára az Azure AD-alapú egyszeri bejelentkezést (SSO-t).

-   Engedélyezze a Zimperium alkalmazás számára az Azure AD SSO használatát a bejelentkezéshez.

## <a name="to-set-up-zimperium-integration"></a>A Zimperium-integráció beállítása

1.  Nyissa meg a [Zimperium MTD konzolt](https://staging2-console.zimperium.com), és jelentkezzen be a hitelesítő adataival.

2.  Válassza a bal oldali menü **Felügyelet** pontját.

3.  Válassza az **MDM-beállítások** panelt.

4.  Válassza az **MDM hozzáadása** elemet, majd az **MDM-szolgáltatók** listájából válassza ki a **Microsoft Intune** elemet.

5.  Miután beállította a Microsoft Intune-t mobileszköz-kezelési szolgáltatásként, a megjelenő **Microsoft Intune-konfiguráció** ablakban válassza az **Azure Active Directory hozzáadása** lehetőséget mind a **Zimperium zConsole**, mind pedig a **zIPS iOS- és Android-alkalmazás** esetében. Ezzel engedélyezi a Zimperiumnak, hogy az Azure AD egyszeri bejelentkezési szolgáltatásán keresztül kommunikáljon az Intune-nal és az Azure AD-vel.

    > [!IMPORTANT]
    > Az Intune-nal való sikeres integráció érdekében hozzá kell adnia a Zimperium zConsole-t és a zIPS iOS- és Android-alkalmazás elemet is.

6.  Válassza az **Elfogadás** elemet. Ezzel engedélyezi, hogy a Zimperium kommunikáljon az Intune-nal és az Azure Active Directoryval.

7.  Miután hozzáadta a **Zimperium zConsole-t** és a **zIPS iOS- és Android-alkalmazást** az Azure AD-hez, hozzá kell adnia az Azure AD-beli biztonsági csoportokat. A hozzáadás lehetővé teszi, hogy a Zimperium szinkronizálja a szolgáltatással az Azure AD biztonsági csoportját.

8.  A **Befejezés** elem kiválasztásával menti a konfigurációt, és elindítja az Azure AD biztonsági csoport első szinkronizálását.

## <a name="next-steps"></a>További lépések

-   [Zimperium-alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)
