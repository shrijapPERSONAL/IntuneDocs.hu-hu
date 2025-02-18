---
title: A Microsoft Intune szolgáltatásba való regisztráció vagy bejelentkezés
description: Regisztrálás Microsoft Intune-előfizetésre, illetve bejelentkezés az előfizetés használatbavételéhez.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f3ce07a-b718-42a9-bace-f99a8b8abd94
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 956fe061912e0eb96a18c410e1455252874d6b84
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57459951"
---
# <a name="sign-up-or-sign-in-to-microsoft-intune"></a>A Microsoft Intune szolgáltatásba való regisztráció vagy bejelentkezés

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Ez a témakör arról tájékoztatja a rendszergazdákat, hogy miképpen regisztrálhatnak Intune-fiókra.

Mielőtt regisztrálna az Intune-ra, ellenőrizze, hogy rendelkezik-e már Microsoft Online Services-fiókkal, Nagyvállalati Szerződéssel vagy egyenértékű mennyiségi licencszerződéssel. A Microsoft mennyiségi licencszerződései és az egyéb Microsoft-felhőszolgáltatások előfizetései (például az Office 365) általában magukban foglalnak egy munkahelyi vagy iskolai fiókot.

Ha már rendelkezik munkahelyi vagy iskolai fiókkal, **jelentkezzen be** vele, és adja hozzá az Intune-t az előfizetéshez. Ha még nem, **regisztrálhat** egy új fiókot, amellyel használatba veheti az Intune-t a cégében.

>[!WARNING]
>Meglévő munkahelyi vagy iskolai fiókok nem vonhatók össze újonnan regisztrált fiókokkal.

## <a name="how-to-sign-up-or-sign-in-to-intune"></a>Az Intune szolgáltatásba való regisztráció vagy bejelentkezés módja

1. Látogasson el az [Intune regisztrációs oldalára](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

   ![Képernyőkép a Microsoft Intune próbaverziójának fiókregisztrációs weboldaláról](./media/account-sign-up-site.png)

2. Új Intune-előfizetése kezeléséhez lépjen be vagy regisztráljon a regisztrációs oldalon.

## <a name="post-sign-up-considerations"></a>A regisztrációt követően megfontolandó szempontok
Az új előfizetés regisztrálása után e-mailben elküldjük a fiókadatait a regisztráció során megadott e-mail címre. Az e-mail megerősíti, hogy az előfizetés aktív.

A regisztrációs folyamat befejezését követően átirányítjuk a Microsoft 365 felügyeleti központban, a felhasználók hozzáadása és licenceket rendelhet a felhasználókhoz. Ha kizárólag az alapértelmezett onmicrosoft.com tartományt használó felhőalapú fiókokkal rendelkezik, akkor már ennél a lépésnél felveheti a felhasználókat, és hozzárendelheti a licenceket. Ha azonban a szervezet [egyéni tartománynevét](custom-domain-name-configure.md) szeretné használni, illetve szeretné [szinkronizálni a felhasználóifiók-adatokat](users-add.md#sync-active-directory-and-add-users-to-intune) a helyi Active Directoryval, zárja be a böngészőablakot.
