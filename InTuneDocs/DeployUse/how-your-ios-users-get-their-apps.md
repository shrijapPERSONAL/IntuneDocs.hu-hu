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
ms.sourcegitcommit: 52b9e786fe22b04081441db88a3629062fc85668
ms.openlocfilehash: a215d547507dcc460e83009cc6a04baf3fd8f4a4


---


# iOS-felhasználói alkalmazások letöltése

Ez a témakör ismerteti, hogy végfelhasználói hol és hogyan juthatnak hozzá a Microsoft Intune-ban elérhetővé tett alkalmazásokhoz.

**Kötelező alkalmazások** – A rendszergazda által kötelezően előírt alkalmazások, amelyeknek a telepítéséhez az adott platformtól függően minimális felhasználói beavatkozás szükséges.

**Elérhető alkalmazások** – A Vállalati portál alkalmazáslistájában szereplő azon alkalmazások, amelyeknek a telepítése nem kötelező.

**Felügyelt alkalmazások** – Az Intune által szabályzatokkal felügyelt és „becsomagolt”, illetve az Intune Mobile Application Management (MAM) SDK-val készített alkalmazások. Ezek az alkalmazások az Intune-nal kezelhetők, és alkalmazás-házirendekkel felügyelhetők.

**Nem felügyelt alkalmazások** – Azok az alkalmazások, amelyeket nem az Intune csomagolt be, illetve amelyek nem foglalják magukban az Intune MAM SDK-t. Ezekre az alkalmazásokra nem alkalmazhatók alkalmazás-házirendek.

Az Apple korlátozásai tiltják az üzletági és a felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban. Ezt megkerülendő, az iOS-es Vállalati portál alkalmazás alkalmazáscsempéi a felhasználókat valamennyi alkalmazásuk eléréséhez egyetlen hely (a Vállalati portál webhely) különböző nézeteihez irányítják a következők szerint:

- A **Vállalati alkalmazások** csempe korábban az összes alkalmazás listájára mutatott a [Vállalati portál webhely](http://portal.manage.microsoft.com) ÖSSZES lapján, és ez a jövőben is így marad. A csempe neve **Minden alkalmazás**-ra változott.

- Az **Egyéb alkalmazások** csempe korábban a Vállalati portál alkalmazás azon alkalmazásokat listázó nézetére mutatott, amelyek megjelenítését az Apple engedélyezi a Vállalati portál alkalmazás számára. A csempe új neve **Kiemelt alkalmazások**-ra változott, és rákoppintás esetén a felhasználót a Vállalati portál webhely KIEMELT lapjára irányítja.

-  A **Kategóriák** csempe korábban egy olyan nézetre mutatott a Vállalati portál alkalmazásban, amely az alkalmazások kategóriáit listázza. A csempe neve nem változott, most azonban a Vállalati portál webhely KATEGÓRIÁK nézetére mutat.
[Itt](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) talál frissített képernyőképeket.



###További információ
[Android-felhasználói alkalmazások letöltése](how-your-android-users-get-their-apps.md)</br>
[Windows-felhasználói alkalmazások letöltése](how-your-windows-users-get-their-apps.md)



<!--HONumber=Sep16_HO3-->


