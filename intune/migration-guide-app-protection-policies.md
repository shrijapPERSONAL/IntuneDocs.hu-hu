---
title: "Alkalmazásvédelmi szabályzatok konfigurálása Intune-migráció során"
description: "Ez a cikk az alkalmazásvédelmi szabályzatok Intune-migráció során történő beállításához szükséges lépéseket ismerteti."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cbe2c794a68ab37722c56448560a3c64f6087969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="configure-app-protection-policies-optional"></a>Alkalmazásvédelmi szabályzatok konfigurálása (nem kötelező)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Az alkalmazásvédelmi szabályzatokkal titkosíthat alkalmazásokat, PIN-kódot adhat meg az alkalmazás eléréséhez, letilthatja egyes alkalmazások futtatását feltört eszközökön, és számos más védelmi intézkedést tehet. Ha a felhasználó telefonját ellopják vagy elvész, mobilalkalmazás-védelmi szabályzatokkal távolról is törölhetők róla szelektíven a vállalati adatok, miközben a személyes adatok érintetlenül maradnak.

Az alkalmazásvédelmi szabályzatok alkalmazásszinten működnek, így nem igényelnek eszközregisztrációt, egyaránt használhatók az Intune-ba regisztrált és nem regisztrált eszközökkel, sőt akár külső MDM-szolgáltatónál regisztrált eszközökkel is.

## <a name="app-protection-policies-with-lob-apps"></a>Alkalmazásvédelmi szabályzatok üzletági alkalmazásokkal

A [Microsoft Intune App SDK-val](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) vagy a Microsoft Intune [iOS-en](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) és [Androidon](https://www.microsoft.com/download/details.aspx?id=47267) is elérhető alkalmazásburkoló eszközével az üzletági alkalmazásokat is bevonhatja a mobilalkalmazás-védelmi szabályzatok hatókörébe.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Hogyan segítenek a migráció során az alkalmazásvédelmi szabályzatok?

A migráció során az eszközöket el kell távolítani a korábbi MDM-szolgáltatóból, és regisztrálni kell őket az Intune-ba. Ezt előre célszerű megszervezni: kérje meg a felhasználókat, hogy lépjenek ki a régi MDM-szolgáltatótól, és rögtön regisztráljanak is az Intune-ba. Előfordulhatnak azonban olyan felhasználók a migráció során, akik késlekednek a regisztrációval, így eszközeiket egyik MDM-szolgáltató sem felügyeli.

Ebben az időszakban a szervezet jobban ki van téve az eszközlopás és a vállalati adatvesztés veszélyének, ha a céges adatokhoz való hozzáférés továbbra is engedélyezve van, illetve a felhasználói produktivitás csökkenésének, ha a céges adatokhoz való hozzáférés le van tiltva.

Az Intune a migráció során is képes vállalati adatvédelmi intézkedésekre, így a céges adatok az eszközszintű felügyelet hiányában sem maradnak teljesen védtelenek.

Amikor pedig a régebbi MDM-szolgáltatóban letiltja a feltételes hozzáférést, a felhasználók az Intune-ba való belépésig is tudnak dolgozni.

## <a name="task-list-for-app-protection-policies"></a>Feladatlista az alkalmazásvédelmi szabályzatokhoz

1. [Alkalmazásvédelmi szabályzat létrehozása](/intune/app-protection-policies#create-an-app-protection-policy)
2. [Szabályzat telepítése](/intune/app-protection-policies#deploy-a-policy-to-users)


## <a name="next-steps"></a>További lépések 

[Speciális áttelepítési megfontolások](migration-guide-considerations.md)
