---
title: "Az Intune alapszintű beállítása"
description: "Ez a cikk a Microsoft Intune beállításához szükséges lépéseket ismerteti."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="basic-setup"></a>Alapszintű beállítás

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

A környezet felmérése után ideje beállítani az Intune-t.

## <a name="external-dependencies-for-an-intune-deployment"></a>Intune-környezet külső függőségei

### <a name="identity"></a>Identitás

Az Intune-hoz az Azure Active Directoryt (AAD) kell használni felhasználóicsoport- és identitásszolgáltatóként.

-   További tudnivalók [az identitással kapcsolatos követelményekről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   További tudnivalók [a címtár-szinkronizálás követelményeiről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   További tudnivalók [a többtényezős hitelesítés követelményeiről](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

-   További tudnivalók [a felhasználói és eszközcsoportok megtervezéséről](/intune/users-permissions-add)

-   Útmutató [a felhasználói és eszközcsoportok létrehozásához](/intune/groups-get-started)

Ha a szervezet már használja az Office 365-öt, akkor fontos, hogy az Intune is ugyanazt az Azure Active Directory-környezetet használja.

### <a name="pki-optional"></a>Nyilvános kulcsú infrastruktúra (nem kötelező)

Ha az Intune VPN-, Wi-Fi- vagy e-mail-profiljaihoz tanúsítványalapú hitelesítést tervez használni, bizonyosodjon meg róla, hogy a szervezetnél már ki van alakítva a tanúsítványprofilok létrehozására és üzembe helyezésére kész, támogatott [PKI-infrastruktúra](/intune/certificates-configure).

Az Intune-ban történő tanúsítványkonfigurálással kapcsolatos további tudnivalókat alább olvashatja.

-   [SCEP-tanúsítványinfrastruktúra konfigurálása](/intune/certificates-scep-configure)

-   [PFX-tanúsítványinfrastruktúra konfigurálása](/intune/certficates-pfx-configure)


## <a name="task-list-for-an-intune-setup"></a>Intune-beállítás feladatlistája

### <a name="task-1-intune-subscription"></a>1. feladat: Intune-előfizetés

Az Intune-ra való migráláshoz Intune-előfizetés szükséges.

-   [Ezen a lapon](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) útmutatást találhat a következőkhöz:

    -   Új AAD-bérlőhöz kapcsolt új Intune-előfizetés létrehozása

    -   Intune-előfizetés összekapcsolása meglévő AAD-bérlőbe való bejelentkezés révén.

### <a name="task-2-assign-intune-user-licenses"></a>2. feladat: Intune felhasználói licencek kiosztása

-   Ismerje meg, [hogyan oszthatja ki az Intune felhasználói licenceit](licenses-assign.md).

-   Ha új Azure Active Directory-bérlőt hozott létre, ismerje meg, [hogyan lehet új felhasználókat létrehozni vagy a helyszíni Active Directory (AD) felhasználóit ide szinkronizálni.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>3. feladat: az Intune beállítása MDM-szolgáltatóként

Az Intune kezelhető az Azure Portalról vagy a Configuration Manager Aktuális ágának konzoljáról. Ha nincs rá szükség, hogy az Intune-t a Configuration Manager Aktuális ágán alapuló környezettel integrálja, ajánlott az Intune-t az [Azure Portalról](https://portal.azure.com) kezelni.

Az Azure-beli Intune-portál aktiválásához állítsa be az **Intune**-t MDM-szolgáltatóként. Ha másik MDM-szolgáltatót használ, akkor az Intune a Microsoft más felügyeleti konzoljainak is átadhatja a mobileszköz-felügyeletet. Ezek a helyzetek elég ritkán fordulnak elő.

> [!IMPORTANT]
> Ha első alkalommal adja át a mobileszköz-felügyeletet az Intune-nak, akkor mindenképpen az Intune-t adja meg MDM-szolgáltatónak.

-   Ismerje meg, [hogyan állíthatja be a mobileszköz-felügyeleti szolgáltatót](/intune/mdm-authority-set).

## <a name="next-step"></a>Következő lépés

[Eszköz- és alkalmazásszabályzatok konfigurálása](migration-guide-configure-policies.md)
