---
title: "A Skycure és a Microsoft Intune közötti integráció beállítása"
titlesuffix: 
description: "A Skycure Mobile Threat Defense beállítása a Microsoft Intune-ban a mobileszközök a vállalati erőforrásokhoz való hozzáférésének kezeléséhez."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a09806afae72f60961a94ab27707b4851006cf0
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="set-up-the-skycure-integration-with-intune"></a>A Skycure és az Intune közötti integráció beállítása

A Skycure Mobile Threat Defense megoldás Intune-beli integrálásához kövesse az alábbi lépéseket. Az egyszeri bejelentkezés lehetőségéhez a Skycure-alkalmazásokat fel kell venni az Azure AD-be.

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

    ![A Skycure Management konzolon található iOS-alkalmazás képe](./media/skycure-setup-1.png)

5.  Megnyílik a bejelentkezési oldal. Adja meg Intune-os hitelesítő adatait, majd kattintson az **Accept** (Elfogadom) gombra.

    ![Kép az iOS-alkalmazás Intune-bejelentkezési képernyőjéről](./media/skycure-setup-2.png)

6.  Ha az alkalmazás bekerült az Azure AD-be, ezzel kapcsolatos jelzés jelenik meg a Skycure Management konzolon.

    ![Kép az iOS-alkalmazás sikeres felvételét jelző képernyőről](./media/skycure-setup-3.png)

> [!NOTE]
> Végezze el ugyanezt az eljárást az **Androidra készült Skycure alkalmazással** és a **Felügyeleti alkalmazással** is.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Azure AD-biztonsági csoport felvétele a Skycure-ba

Fel kell vennie egy olyan biztonsági csoportot, amelynek tagja az összes Skycure-t futtató eszköz.

-  Adja meg és jelölje ki az összes Skycure-t futtató eszközöket tartalmazó biztonsági csoportot, majd kattintson az **Apply changes** (Módosítások alkalmazása) elemre.

    ![Kép a biztonsági csoport konfigurálásának helyéről a Skycure Management konzolon](./media/skycure-setup-4.png)

A Skycure a Mobile Threat Defense szolgáltatást futtató eszközöket az Azure AD biztonsági csoportjaival szinkronizálja.

![Kép a biztonsági csoport konfigurálásának befejezéséről a Skycure Management konzolon](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Teljes integráció beállítása az Intune és a Skycure között

1.  Nyissa meg a [Skycure Management konzolt](https://aad.skycure.com).

2.  Írja be **Skycure-adminisztrátori hitelesítő adatait**, majd kattintson a **Tovább** gombra.

3.  A **Settings** (Beállítások) lap **Intune Integration** (Intune-integráció) területén válassza a **Full Integration** (Teljes integráció) lehetőséget.

4.  Jelölje be az alábbi beállításokat:

    a.  Report the health and risk of devices to Intune (Eszközök állapotának és kockázatának jelentése az Intune-nak)

    b.  Also report security incidents to Intune (A biztonsági incidensek jelentése az Intune-nak)

5.  Kattintson az **Apply changes** (Módosítások alkalmazása) elemre.

    ![Kép a teljes Skycure-integráció befejezéséről](./media/skycure-setup-6.png)

## <a name="next-steps"></a>További lépések

[Skycure-alkalmazások beállítása](mtd-apps-ios-app-configuration-policy-add-assign.md)
