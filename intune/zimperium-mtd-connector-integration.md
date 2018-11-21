---
title: A Zimperium MTD integrálása a Microsoft Intune-nal
titleSuffix: ''
description: A Zimperium Mobile Threat Defense (MTD) beállítása a Microsoft Intune-ban a mobileszközök a vállalati erőforrásokhoz való hozzáférésének kezeléséhez.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 68896a363cab37aabe9a597872da0fe75c44c473
ms.sourcegitcommit: 3903f20cb5686532ccd8c36aa43c5150cee7cca2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/21/2018
ms.locfileid: "52267237"
---
# <a name="integrate-zimperium-with-intune"></a>A Zimperium integrálása az Intune-nal

A Zimperium mobilfenyegetések elleni megoldás Intune-beli integrálásához kövesse az alábbi lépéseket.

## <a name="before-you-begin"></a>Előkészületek

> [!NOTE]
> A következő lépéseket kell elvégezni a [Zimperium MTD-konzolon](https://sso.zimperium.com/signon/aad/).

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

1.  Lépjen a [Zimperium MTD-konzolon](https://sso.zimperium.com/signon/aad/) , és jelentkezzen be a hitelesítő adataival.

2.  Válassza a bal oldali menü **Felügyelet** pontját.

3.  Válassza ki a **mobileszköz-kezelési beállítások** fülre.

4.  Válassza az **MDM hozzáadása** elemet, majd az **MDM-szolgáltatók** listájából válassza ki a **Microsoft Intune** elemet.

5.  Miután beállította a Microsoft Intune mobileszköz-kezelési szolgáltatásként, a **a Microsoft Intune-konfiguráció** ablakban, válassza ki a **hozzáadása az Azure Active Directory** minden mód:  **Zimperium zconsole-t**, **zIPS iOS- és Android-alkalmazások** Zimperium kommunikáljon az Intune és az Azure AD keresztül az Azure AD egyszeri bejelentkezés engedélyezéséhez.

    > [!IMPORTANT]
    > Az Intune-nal való sikeres integráció érdekében hozzá kell adnia a Zimperium zConsole-t és a zIPS iOS- és Android-alkalmazás elemet is.

6.  Válasszon **elfogadás** , engedélyezze a Zimperium alkalmazás számára az Intune és az Azure Active Directoryval folytatott kommunikációhoz.

7.  Miután hozzáadta a **Zimperium zConsole-t** és a **zIPS iOS- és Android-alkalmazást** az Azure AD-hez, hozzá kell adnia az Azure AD-beli biztonsági csoportokat. A hozzáadás lehetővé teszi, hogy a Zimperium szinkronizálja a szolgáltatással az Azure AD biztonsági csoportját.

8.  Válasszon **Befejezés** a konfiguráció mentéséhez, és az Azure AD biztonsági csoport menet közbeni kezdeti szinkronizálás elindításához.

## <a name="next-steps"></a>További lépések

-   [Zimperium-alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)
