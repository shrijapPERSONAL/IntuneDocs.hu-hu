---
title: "iOS-felhasználói alkalmazások letöltése | Microsoft Intune"
description: "Módszerek az iOS-alkalmazások elérhetővé tételére végfelhasználók számára"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9f1946c02c6267a22844106e8f72555ec5e9cabb
ms.openlocfilehash: 212dcd31697180dae61569dda13b56704a079bf4


---


# iOS-felhasználói alkalmazások letöltése

Ez a témakör ismerteti, hogy végfelhasználói hol és hogyan juthatnak hozzá a Microsoft Intune-ban elérhetővé tett alkalmazásokhoz.

**Kötelező alkalmazások** – A rendszergazda által kötelezően előírt alkalmazások, amelyeknek a telepítéséhez az adott platformtól függően minimális felhasználói beavatkozás szükséges.

**Elérhető alkalmazások** – A Vállalati portál alkalmazáslistájában szereplő azon alkalmazások, amelyeknek a telepítése nem kötelező.

**Felügyelt alkalmazások** – Az Intune által szabályzatokkal felügyelt és „becsomagolt”, illetve az Intune Mobile Application Management (MAM) SDK-val készített alkalmazások. Ezek az alkalmazások az Intune-nal kezelhetők, és alkalmazás-házirendekkel felügyelhetők.

**Nem felügyelt alkalmazások** – Azok az alkalmazások, amelyeket nem az Intune csomagolt be, illetve amelyek nem foglalják magukban az Intune MAM SDK-t. Ezekre az alkalmazásokra nem alkalmazhatók alkalmazás-házirendek.

Az Apple korlátozásai tiltják üzletági és felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban, ami annyit jelent, hogy ahhoz, hogy valamennyi alkalmazásukat megtalálják, a felhasználóknak több különböző nézetet kell használniuk. A Vállalati portál alkalmazás Alkalmazások lapján megjelenő csempékhez tartozó alkalmazások a következők szerint érhetők el:

- A **Vállalati alkalmazások** csempe a [Vállalati portál webhely](http://portal.manage.microsoft.com) **ÖSSZES** lapjára mutat.

- Az **Egyéb alkalmazások** csempe jelenleg a Vállalati portál alkalmazás azokat az alkalmazásokat listázó nézetére mutat, amelyek megjelenítését az Apple engedélyezi a Vállalati portál alkalmazás számára. Az üzletági és a felügyelt App Store-alkalmazásokon kívül valamennyi alkalmazás ide tartozik.

- A **Kategóriák** csempe jelenleg egy olyan nézetre mutat a Vállalati portál alkalmazásban, amely az alkalmazások kategóriáit listázza.

    ![ios-how-to-sync-device-with-intune](./media/ios-sync-comp-portal-apps.png)


###További információ
[Android-felhasználói alkalmazások letöltése](how-your-android-users-get-their-apps.md)</br>
[Windows-felhasználói alkalmazások letöltése](how-your-windows-users-get-their-apps.md)



<!--HONumber=Aug16_HO4-->


