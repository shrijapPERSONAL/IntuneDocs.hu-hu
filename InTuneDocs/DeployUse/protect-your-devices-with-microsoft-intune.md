---
title: "Eszközök védelme | Microsoft Intune"
description: "Megismerhet néhány módot, amelyek segítségével az Intune segít megvédeni az eszközét a jogosulatlan hozzáféréstől és más fenyegetésektől."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c999a852b68762002ac94269e27ecbf46c8f9999
ms.openlocfilehash: 3318590eaedc6f0e96fb463dc016d5786eeb38fb


---

# Eszközök védelme a Microsoft Intune-nal
Miután valamennyi eszközét az Intune felügyelete alá helyezte, gondoskodjon védelmükről is a jogosulatlan hozzáféréssel és más fenyegetésekkel szemben. Íme az Intune néhány olyan funkciója, amelyek e célok megvalósítását segítik elő.

> [!TIP]
> Ez a témakör nem ismerteti az Intune valamennyi, az eszközök védelmét szolgáló módszerét. Az Intune-szabályzatokat számos eszközbiztonsági beállítás megadásához használhatja; ilyenek a jelszó- és titkosítási beállítások vagy az olyan hardverfunkciók, mint a Bluetooth és a kamera beállításai. A beállításokkal kapcsolatban bővebben lásd [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) című témakört.

## PIN-kódok alaphelyzetbe állítása a felhasználók eszközökről való kizárása esetén
Az első lépés a mobileszközökön tárolt vállalati adatok védelme érdekében a PIN-kód megadásának kötelezővé tétele az eszköz használatához. Előfordulhat, hogy [új PIN-kódot kell kérnie](use-remote-lock-and-passcode-reset-in-microsoft-intune.md), vagy ehhez segítséget kell nyújtania valamelyik alkalmazottnak a kód eltávolításával vagy egy ideiglenes hitelesítő kód távolról történő beállításával. Elvesztés vagy lopás esetén [távolról is zárolhatja az eszközöket](use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

## Kiegészítő védelmi réteg hozzáadása Windows rendszerű eszközökhöz
A[többtényezős hitelesítés (MFA)](protect-windows-devices-with-multi-factor-authentication.md) biztonságosabb módszer a hálózatban lévő Windows és Windows Phone rendszerű eszközök felhasználóinak hitelesítésére. A többtényezős hitelesítés (MFA) szolgáltatás használatakor a felhasználóknak a felhasználónév-jelszó pároson túlmenően egy telefonhívással vagy szöveges üzenettel is igazolniuk kell személyazonosságukat.

## A Microsoft Passport beállításainak szabályozása Windows-eszközökön
Az Intune integrálható a [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) szolgáltatással. Ez egy alternatív bejelentkezési mód Windows 10 vagy annál újabb verziók esetében. A Microsoft Passport for Work egy Active Directory- vagy Azure Active Directory-fiókot használ jelszó, intelligens kártya vagy virtuális intelligens kártya helyett.

## Az aktiválási zár megkerülése iOS-eszközökön
Az aktiválási zár funkció azáltal nyújt védelmet a felhasználók eszközeinek, hogy nem teszi lehetővé, hogy valaki törölje vagy újraaktiválja az eszközt anélkül, hogy megadná Apple ID azonosítóját és jelszavát. Ugyanakkor ez problémákkal is járhat, például abban az esetben, ha a felhasználó a zár feloldása nélkül elhagyja a vállalatot. Az [iOS aktiválási zár megkerülésével](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) feloldhatja a felügyelt iOS-eszközök zárolását, így azokat új feladatokhoz használhatja, vagy törölheti a tartalmukat.

## Intune ügyfélprogram által felügyelt Windows rendszerű számítógépek védelme
Az Intune továbbra is támogatja az olyan Windows rendszerű számítógépek védelmét, amelyek nincsenek regisztrálva, de felügyeletüket az Intune ügyfélszoftvere biztosítja. Ha szeretné tudni, hogyan segítik ezek a szabályzatok a Windows rendszerű számítógépek védelmét, a [Szabályzatok használata az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek védelméhez](policies-to-protect-windows-pcs-in-microsoft-intune.md) című témakörből tájékozódhat.



<!--HONumber=Aug16_HO2-->


