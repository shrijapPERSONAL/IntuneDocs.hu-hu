---
title: "A Zimperium integrálása az Intune-nal"
titleSuffix: Intune on Azure
description: "Az Intune integrálása a Zimperiummal"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 515f99f694a9125d60bb9210becc6722bfb9e24f
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/30/2017
---
# <a name="integrate-zimperium-with-intune"></a>A Zimperium integrálása az Intune-nal

A Zimperium mobilfenyegetések elleni megoldás Intune-beli integrálásához kövesse az alábbi lépéseket.

## <a name="before-you-begin"></a>Előkészületek

> [!NOTE]
> Az alábbi lépéseket a [Zimperium MTD konzolon](https://staging2-console.zimperium.com) kell végrehajtania.

Mielőtt elkezdené a Zimperium integrálását az Intune-nal, ellenőrizze, hogy rendelkezik-e az alábbiakkal:

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

-   A Zimperium szinkronizálást végez az Azure AD regisztrációs csoporttagsággal az eszköz adatbázisának feltöltéséhez.

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

7.  Miután hozzáadta a **Zimperium zConsole-t** és a **zIPS iOS- és Android-alkalmazást** az Azure AD-hez, hozzá kell adnia az Azure AD-beli biztonsági csoportokat, hogy a Zimperium saját szolgáltatásával is szinkronizálni tudja az Azure AD-beli biztonsági csoportot.

8.  A **Befejezés** elem kiválasztásával menti a konfigurációt, és elindítja az Azure AD biztonsági csoport első szinkronizálását.

## <a name="next-steps"></a>További lépések

-   [Zimperium-alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)
