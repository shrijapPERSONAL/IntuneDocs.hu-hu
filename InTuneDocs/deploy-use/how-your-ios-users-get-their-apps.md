---
title: "iOS-felhasználói alkalmazások letöltése | Microsoft Intune"
description: "Módszerek az iOS-alkalmazások elérhetővé tételére végfelhasználók számára"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 3ba0a5cda91164761c4576df935c54390bc78f8c


---


# <a name="how-your-ios-users-get-their-apps"></a>iOS-felhasználói alkalmazások letöltése

Ez a témakör ismerteti, hogy végfelhasználói hol és hogyan juthatnak hozzá a Microsoft Intune-ban elérhetővé tett alkalmazásokhoz.

**Kötelező alkalmazások** – A rendszergazda által kötelezően előírt alkalmazások, amelyeknek a telepítéséhez az eszközön az adott platformtól függően minimális felhasználói beavatkozás szükséges.

**Elérhető alkalmazások** – A Vállalati portál alkalmazáslistájában szereplő azon alkalmazások, amelyeknek a telepítése nem kötelező.

**Felügyelt alkalmazások** – Az Intune által szabályzatokkal felügyelt és „burkolt”, illetve az Intune Mobile Application Management (MAM) SDK-val készített alkalmazások. Ezek az alkalmazások az Intune-nal kezelhetők, és alkalmazás-házirendekkel felügyelhetők.

**Nem felügyelt alkalmazások** – Azok a szabályzatokkal felügyelhető alkalmazások, amelyeket nem az Intune burkolt be, illetve amelyek nem foglalják magukban az Intune MAM SDK-t. Ezekre az alkalmazásokra nem alkalmazhatók alkalmazás-házirendek.

Az Apple korlátozásai tiltják az üzletági és a felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban. Ezt megkerülendő, az iOS-es Vállalati portál alkalmazás csempéi a felhasználókat valamennyi alkalmazásuk eléréséhez egyetlen hely (a Vállalati portál webhely) különböző nézeteihez irányítják.

A regisztrált felhasználók úgy jutnak hozzá az alkalmazásokhoz, hogy a következő csempékre kattintanak a Munkahelyi portál alkalmazás Alkalmazások képernyőjén:

- A **Minden alkalmazás** csempe a [Munkahelyi portál webhely](http://portal.manage.microsoft.com) ÖSSZES lapjára mutat.

- A **Kiemelt alkalmazások** csempe a Munkahelyi portál webhely KIEMELT lapjára vezet.

- A **Kategóriák** csempe a Munkahelyi portál webhely KATEGÓRIÁK lapjára vezet.

 
![iOS rendszerű Munkahelyi portál alkalmazás](./media/ios-cp-app-main-apps-screen.png)

Az alkalmazások felvételéről és ezeken a csempéken való megjelenítéséről az [Alkalmazások hozzáadása beléptetett eszközökhöz az Intune-ban](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md) című rész nyújt tájékoztatást.

### <a name="see-also"></a>További információ
[Android-felhasználói alkalmazások letöltése](how-your-android-users-get-their-apps.md)

[Windows-felhasználói alkalmazások letöltése](how-your-windows-users-get-their-apps.md)



<!--HONumber=Nov16_HO1-->


