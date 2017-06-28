---
title: "A Skycure és az Intune közötti integráció beállítása"
description: "Állítsa be a Skycure és a Microsoft Intune közötti integrációt."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93722f66-7641-4a3f-b1fb-3a0a58a36675
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 1d5a59f34a5dacdc2e1a0d5c6601b4ede1a908e4
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---

# <a name="set-up-the-skycure-integration-with-intune"></a>A Skycure és az Intune közötti integráció beállítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az egyszeri bejelentkezés lehetőségéhez a Skycure-alkalmazásokat fel kell venni az Azure AD-be.

## <a name="before-you-begin"></a>Előkészületek

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Az Intune és a Skycure integrálásához használt Azure AD-fiók

-   A Skycure alapvető beállítási folyamatának megkezdése előtt ellenőrizze, hogy megfelelően konfigurálta-e az Azure AD-fiókot a [Skycure Management konzolon](https://aad.skycure.com).

### <a name="full-integration-vs-read-only"></a>Teljes integráció vagy írásvédelem

A Skycure kétféleképpen integrálható az Intune-nal:

-   Az **írásvédett integráció (alapszintű beállítás)** csak kiolvassa az Azure Active Directoryból az eszközöket, és betölti őket a Skycure-konzolba.
<br>
    -   Ha a **Report the health and risk of devices to Intune** (Eszközök állapotának és kockázatának jelentése az Intune-nak) és az **Also report security incidents to Intune** (A biztonsági incidensek jelentése az Intune-nak) jelölőnégyzetek nincsenek bejelölve a Skycure Management konzolon, az integráció írásvédett, ezért nem fogja módosítani az eszközök megfelelőségi állapotát az Intune-ban.
<br></br>
-   A **teljes integráció** lehetővé teszi, hogy a Skycure jelentse az eszközökkel kapcsolatos kockázatokat és a biztonsági incidensek részleteit az Intune-nak, amely kétirányú kommunikációt alakít ki a két felhőszolgáltatás között.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Hogyan használhatók a Skycure-alkalmazások az Azure AD-vel és az Intune-nal?

-   **iOS-es alkalmazás:** A végfelhasználók iOS-es alkalmazással jelentkezhetnek be az Azure AD-ba.

-   **Androidos alkalmazás:** A végfelhasználók androidos alkalmazással jelentkezhetnek be az Azure AD-ba.

-   **Felügyeleti alkalmazás:** Ez a Skycure több-bérlős Azure AD-alkalmazása, amely lehetővé teszi a szolgáltatásközi kommunikációt az Intune-nal.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>Írásvédett integráció beállítása az Intune és a Skycure között

> [!IMPORTANT]
> A Skycure-adminisztrátor hitelesítő adatai egy olyan e-mail-fióknak felelnek meg, amely egy érvényes felhasználóhoz tartozik az Azure Active Directoryban. Ellenkező esetben nem fog tudni bejelentkezni. A Skycure az Azure Active Directoryval hitelesíti egyszeri bejelentkezéshez (SSO) az adminisztrátort.

1.  Nyissa meg a [Skycure Management konzolt](https://aad.skycure.com).

2.  Írja be **Skycure-adminisztrátori hitelesítő adatait**, majd kattintson a **Tovább** gombra.

3.  A **Settings** (Beállítások) lap **Intune Integration** (Intune-integráció) területén válassza a **Basic Setup** (Alapszintű beállítás) lehetőséget.

4.  Az **iOS App** (iOS-es alkalmazás) címkén kattintson az **Add to Active Directory** (Felvétel az Active Directoryba) elemre.

    ![iOS-es alkalmazás a Skycure Management konzolon](../media/mtp/skycure-setup-1.png)

5.  Megnyílik a bejelentkezési oldal. Adja meg Intune-os hitelesítő adatait, majd kattintson az **Accept** (Elfogadom) gombra.

    ![Az iOS-es alkalmazás Intune-bejelentkezési képernyője](../media/mtp/skycure-setup-2.png)

6.  Ha az alkalmazás bekerült az Azure AD-be, ezzel kapcsolatos jelzés jelenik meg a Skycure Management konzolon.

    ![iOS-es alkalmazás sikeres felvételét jelző képernyő](../media/mtp/skycure-setup-3.png)

> [!NOTE]
> Végezze el ugyanezt az eljárást az **Androidra készült Skycure alkalmazással** és a **Felügyeleti alkalmazással** is.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Azure AD-biztonsági csoport felvétele a Skycure-ba

Fel kell vennie egy olyan biztonsági csoportot, amelynek tagja az összes Skycure-t futtató eszköz.

1.  Adja meg és jelölje ki az összes Skycure-t futtató eszközöket tartalmazó biztonsági csoportot, majd kattintson az **Apply changes** (Módosítások alkalmazása) elemre.

    ![Biztonsági csoport konfigurálása a Skycure Management konzolon](../media/mtp/skycure-setup-4.png)

A Skycure a Mobile Threat Defense szolgáltatást futtató eszközöket az Azure AD biztonsági csoportjaival szinkronizálja.

![Biztonsági csoport konfigurálásának befejezése a Skycure Management konzolon](../media/mtp/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Teljes integráció beállítása az Intune és a Skycure között

1.  Nyissa meg a [Skycure Management konzolt](https://aad.skycure.com).

2.  Írja be **Skycure-adminisztrátori hitelesítő adatait**, majd kattintson a **Tovább** gombra.

3.  A **Settings** (Beállítások) lap **Intune Integration** (Intune-integráció) területén válassza a **Full Integration** (Teljes integráció) lehetőséget.

4.  Jelölje be az alábbi beállításokat:

    a.  Report the health and risk of devices to Intune (Eszközök állapotának és kockázatának jelentése az Intune-nak)

    b.  Also report security incidents to Intune (A biztonsági incidensek jelentése az Intune-nak)

5.  Kattintson az **Apply changes** (Módosítások alkalmazása) elemre.

    ![A teljes Skycure-integráció befejezése](../media/mtp/skycure-setup-6.png)

## <a name="next-steps"></a>További lépések

[A Skycure Mobile Threat Defense engedélyezése az Intune-ban](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

