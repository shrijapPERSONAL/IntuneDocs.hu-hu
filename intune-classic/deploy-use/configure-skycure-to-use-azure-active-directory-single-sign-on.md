---
title: A Skycure konfigurálása Azure Active Directory-alapú egyszeri bejelentkezés használatára
description: A Skycure konfigurálása Azure Active Directory-alapú egyszeri bejelentkezés (SSO) használatára
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f7f83e87ed3e625775aa41295cab122653ec160c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31015217"
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>A Skycure konfigurálása Azure Active Directory-alapú egyszeri bejelentkezés (SSO) használatára

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Az Intune és a Skycure integrálásakor Azure AD SSO-t kell használni. A fő előnyök:

-   A **rendszergazdák** ugyanazokkal a hitelesítő adatokkal jelentkezhetnek be és ki a Microsoft-portálokon (Intune, Azure) és a Skycure Management konzolon anélkül, hogy minden alkalommal be kellene gépelniük őket.

-   A **végfelhasználók** ugyanazokkal az Azure AD-hitelesítő adatokkal jelentkezhetnek be és ki a Skycure-alkalmazásokban anélkül, hogy minden alkalommal be kellene gépelniük őket.

A Skycure és az Azure Active Directory egyszeri bejelentkezés (SSO) integrálásának lépéseit alább olvashatja.

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Az Azure Active Directory-bérlőazonosító kiolvasása

Ki kell olvasnia az Azure Active Directory-bérlőazonosítót.

1.  Az [Azure-portálon](https://portal.azure.com/) jelentkezzen be hitelesítő adataival.

2.  Az **Irányítópulton** válassza az **Azure Active Directory** lehetőséget.

![Az Azure AD irányítópultja](../media/mtp/skycure-sso-1.png)

1.  Az **Azure Active Directory** panelen válassza a **Tulajdonságok** elemet.

![Az Azure AD Tulajdonságok panele](../media/mtp/skycure-sso-2.png)

1.  Az **Azure Active Directory – tulajdonságok** panelen kattintson a **Címtár azonosítója** mező melletti **Másolás ikonra**.

> Illessze be a kimásolt címtár-azonosítót egy szövegfájlba későbbi felhasználásra. A címtár-azonosító értékére a Skycure–Intune-integráció folyamatának egy későbbi pontján lesz szükség.

![Az Azure AD irányítópultja](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Az Azure Active Directoryval való kommunikáció engedélyezése a Skycure-nak

1.  Írja be az alábbi URL-címet a böngészőjébe. A **DIRECTORY_ID** helyén a korábban a szövegfájlba másolt Azure Active Directory-bérlőazonosítót adja meg.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Azure Active Directory-beli hitelesítő adataival jelentkezzen be. A folytatáshoz kattintson az **Accept** (Elfogadom) gombra.

![Azure AD bejelentkezési oldal](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Azure AD-biztonsági csoport létrehozása a Skycure-hoz (nem kötelező)

Célszerű lehet külön felhasználói csoportot (pl. „Skycure-felhasználók”) létrehozni a Skycure-t futtató felhasználók számára. Ez hasznos lehet, amikor a Skycure-tevékenységet jelentések alapján elemzik.

-   További tudnivalók [a csoport létrehozásáról és a tagok felvételéről az Azure AD-ben](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> Korábban létrehozott Azure AD-biztonsági csoportot is használhat.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Az Azure AD-fiók beállítása az Intune és a Skycure integrálásához

1.  A [Skycure Management konzolon](https://aad.skycure.com/) adja meg a korábban a szövegfájlba másolt Azure Active Directory-bérlőazonosítót.

![A Skycure Management konzol Azure AD-bérlőazonosító mezője](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> A Skycure az Azure AD lekérdezésével ellenőrzi, hogy létezik-e az adott Azure AD-bérlőazonosító. Ha a Skycure megtalálta, a rendszergazda továbbléphet a következő lépésre (alapszintű beállítás).

## <a name="next-steps"></a>További lépések

[Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat letöltése](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)
