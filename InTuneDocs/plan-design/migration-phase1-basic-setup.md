---
title: "Az Intune alapszintű beállítása | Microsoft Docs"
description: "Ez a cikk a Microsoft Intune beállításához szükséges lépéseket ismerteti."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 0fce3edb43a147491465d8a58d1a9a4f009fba55
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-basic-setup"></a>1. fázis: alapszintű beállítás

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A környezet felmérése után ideje beállítani az Intune-t.

## <a name="external-dependencies-for-an-intune-deployment"></a>Intune-környezet külső függőségei

### <a name="identity"></a>Identitás

Az Intune-hoz az Azure Active Directoryt (AAD) kell használni felhasználóicsoport- és identitásszolgáltatóként.

-   További tudnivalók [az identitással kapcsolatos követelményekről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   További tudnivalók [a címtár-szinkronizálás követelményeiről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   További tudnivalók [a többtényezős hitelesítés követelményeiről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

-   További tudnivalók [a felhasználói és eszközcsoportok megtervezéséről](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups)

-   Útmutató [a felhasználói és eszközcsoportok létrehozásához](https://docs.microsoft.com/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)

Ha a szervezet már használja az Office 365-öt, akkor fontos, hogy az Intune is ugyanazt az Azure Active Directory-környezetet használja.

### <a name="pki-optional"></a>Nyilvános kulcsú infrastruktúra (nem kötelező)

Ha az Intune VPN-, Wi-Fi- vagy e-mail-profiljaihoz tanúsítványalapú hitelesítést tervez használni, bizonyosodjon meg róla, hogy a szervezetnél már ki van alakítva a tanúsítványprofilok létrehozására és üzembe helyezésére kész, támogatott [PKI-infrastruktúra](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles).

Az Intune-ban történő tanúsítványkonfigurálással kapcsolatos további tudnivalókat alább olvashatja.

-   [SCEP-tanúsítványinfrastruktúra konfigurálása](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep)

-   [PFX-tanúsítványinfrastruktúra konfigurálása](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx)

-   [Intune-tanúsítványprofilok konfigurálása](file:///C:/intune/deploy-use/https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Erőforrás-hozzáférési szabályzatok konfigurálása](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune)

## <a name="task-list-for-an-intune-setup"></a>Intune-beállítás feladatlistája

### <a name="task-1-intune-subscription"></a>1. feladat: Intune-előfizetés

Az Intune-ra való migráláshoz Intune-előfizetés szükséges.

-   [Ezen a lapon](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) útmutatást találhat a következőkhöz:

    -   Új AAD-bérlőhöz kapcsolt új Intune-előfizetés létrehozása

    -   Intune-előfizetés összekapcsolása meglévő AAD-bérlőbe való bejelentkezés révén.

### <a name="task-2-assign-intune-user-licenses"></a>2. feladat: Intune felhasználói licencek kiosztása

-   Ismerje meg, [hogyan oszthatja ki az Intune felhasználói licenceit](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

-   Ha új Azure Active Directory-bérlőt hozott létre, ismerje meg, [hogyan lehet új felhasználókat létrehozni vagy a helyszíni Active Directory (AD) felhasználóit ide szinkronizálni.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>3. feladat: az Intune beállítása MDM-szolgáltatóként

Az Intune kezelhető az Azure Portalról vagy a Configuration Manager Aktuális ágának konzoljáról. Ha nincs rá szükség, hogy az Intune-t a Configuration Manager Aktuális ágán alapuló környezettel integrálja, ajánlott az Intune-t az [Azure Portalról](https://portal.azure.com) kezelni.

Az Azure-beli Intune-portál aktiválásához állítsa be az **Intune**-t MDM-szolgáltatóként. Ha másik MDM-szolgáltatót használ, akkor az Intune a Microsoft más felügyeleti konzoljainak is átadhatja a mobileszköz-felügyeletet. Ezek a helyzetek elég ritkán fordulnak elő.

> [!IMPORTANT]
> Ha első alkalommal adja át a mobileszköz-felügyeletet az Intune-nak, akkor mindenképpen az Intune-t adja meg MDM-szolgáltatónak.

-   Ismerje meg, [hogyan állíthatja be a mobileszköz-felügyeleti szolgáltatót](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

## <a name="next-step"></a>Következő lépés

[1. fázis: Eszköz- és alkalmazásfelügyeleti szabályzatok konfigurálása](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

