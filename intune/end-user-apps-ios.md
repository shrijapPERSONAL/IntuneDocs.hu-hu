---
title: "iOS-felhasználói alkalmazások letöltése"
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
ms.custom: intune-classic
ms.openlocfilehash: 72291be81df5e0358c9477a2749fb7d9d7cb8fdc
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2017
---
# <a name="how-your-ios-users-get-their-apps"></a>iOS-felhasználói alkalmazások letöltése

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ez a témakör ismerteti, hogy végfelhasználói hol és hogyan juthatnak hozzá a Microsoft Intune-ban elérhetővé tett alkalmazásokhoz.

**Kötelező alkalmazások** – A rendszergazda által kötelezően előírt alkalmazások, amelyeknek a telepítéséhez az eszközön az adott platformtól függően minimális felhasználói beavatkozás szükséges.

**Elérhető alkalmazások** – A Vállalati portál alkalmazáslistájában szereplő azon alkalmazások, amelyeknek a telepítése nem kötelező.

**Felügyelt alkalmazások** –  Azok a szabályzatokkal felügyelhető alkalmazások, amelyeket az Intune „burkolt be”, vagy az Intune App szoftverfejlesztői készlettel (SDK) készültek. Ezek az alkalmazások az Intune-nal felügyelhetők, és azokra alkalmazásvédelmi szabályzatok alkalmazhatók.

**Nem felügyelt alkalmazások** – Azok a szabályzatokkal felügyelhető alkalmazások, amelyeket nem az Intune burkolt be, illetve amelyek nem foglalják magukban az Intune App SDK-t. Ezekre az alkalmazásokra nem alkalmazhatók alkalmazás-házirendek.

Az Apple korlátozásai tiltják az üzletági és a felügyelt App Store-alkalmazások listázását a Vállalati portál alkalmazásban. Ezt megkerülendő, az iOS-es Vállalati portál alkalmazás csempéi a felhasználókat valamennyi alkalmazásuk eléréséhez egyetlen hely (a Vállalati portál webhely) különböző nézeteihez irányítják.

A regisztrált felhasználók úgy jutnak hozzá az alkalmazásokhoz, hogy a következő csempékre kattintanak a Munkahelyi portál alkalmazás Alkalmazások képernyőjén:

- A **Minden alkalmazás** csempe a [Munkahelyi portál webhely](https://portal.manage.microsoft.com) ÖSSZES lapjára mutat.

- A **Kiemelt alkalmazások** csempe a Munkahelyi portál webhely KIEMELT lapjára vezet.

- A **Kategóriák** csempe a Munkahelyi portál webhely KATEGÓRIÁK lapjára vezet.


![iOS rendszerű Munkahelyi portál alkalmazás](./media/ios-cp-app-main-apps-screen.png)

Az alkalmazások felvételéről és ezeken a csempéken való megjelenítéséről az [Alkalmazások hozzáadása beléptetett eszközökhöz az Intune-ban](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md) című rész nyújt tájékoztatást.

### <a name="see-also"></a>További információ
[Android-felhasználói alkalmazások letöltése](end-user-apps-android.md)

[Windows-felhasználói alkalmazások letöltése](end-user-apps-windows.md)
