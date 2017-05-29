---
title: "Alkalmazásvédelmi szabályzatok konfigurálása Intune-migráció során | Microsoft Docs"
description: "Ez a cikk az alkalmazásvédelmi szabályzatok Intune-migráció során történő beállításához szükséges lépéseket ismerteti."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ec990ecdedff0e1b7f4fd6fd9d45fd2edc1571bd
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>1. fázis: Alkalmazásvédelmi szabályzatok konfigurálása (nem kötelező)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Az alkalmazásvédelmi szabályzatokkal titkosíthat alkalmazásokat, PIN-kódot adhat meg az alkalmazás eléréséhez, letilthatja egyes alkalmazások futtatását feltört eszközökön, és számos más védelmi intézkedést tehet. Ha a felhasználó telefonját ellopják vagy elvész, mobilalkalmazás-védelmi szabályzatokkal távolról is törölhetők róla szelektíven a vállalati adatok, miközben a személyes adatok érintetlenül maradnak.

Az alkalmazásvédelmi szabályzatok alkalmazásszinten működnek, így nem igényelnek eszközregisztrációt, egyaránt használhatók az Intune-ba regisztrált és nem regisztrált eszközökkel, sőt akár külső MDM-szolgáltatónál regisztrált eszközökkel is.

## <a name="app-protection-policies-with-lob-apps"></a>Alkalmazásvédelmi szabályzatok üzletági alkalmazásokkal

A mobilalkalmazás-védelmi szabályzatokat az üzletágra is kiterjesztheti az /intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) használatával, vagy a Microsoft Intune [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) és [Android](https://www.microsoft.com/download/details.aspx?id=47267) platformokhoz készült alkalmazásburkoló eszközével.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Hogyan segítenek a migráció során az alkalmazásvédelmi szabályzatok?

A migráció során az eszközöket el kell távolítani a korábbi MDM-szolgáltatóból, és regisztrálni kell őket az Intune-ba. Ezt előre célszerű megszervezni: kérje meg a felhasználókat, hogy lépjenek ki a régi MDM-szolgáltatótól, és rögtön regisztráljanak is az Intune-ba. Előfordulhatnak azonban olyan felhasználók a migráció során, akik késlekednek a regisztrációval, így eszközeiket egyik MDM-szolgáltató sem felügyeli.

Ebben az időszakban a szervezet jobban ki van téve az eszközlopás és a vállalati adatvesztés veszélyének, ha a céges adatokhoz való hozzáférés továbbra is engedélyezve van, illetve a felhasználói produktivitás csökkenésének, ha a céges adatokhoz való hozzáférés le van tiltva.

Az Intune a migráció során is képes vállalati adatvédelmi intézkedésekre, így a céges adatok az eszközszintű felügyelet hiányában sem maradnak teljesen védtelenek.

Amikor pedig a régebbi MDM-szolgáltatóban letiltja a feltételes hozzáférést, a felhasználók az Intune-ba való belépésig is tudnak dolgozni.

## <a name="task-list-for-app-protection-policies"></a>Feladatlista az alkalmazásvédelmi szabályzatokhoz

-   1. feladat: Ismerje meg, [hogyan készülhet fel az alkalmazásvédelmi szabályzatok konfigurálására](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

-   2. feladat: Ismerje meg a [mobilalkalmazás-védelmi szabályzatok létrehozását és telepítését](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="next-steps"></a>További lépések 

[1. fázis: Speciális migrációs megfontolások](/intune-classic/plan-design/migration-phase1-special-migration-considerations)

