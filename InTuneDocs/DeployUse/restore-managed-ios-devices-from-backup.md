---
title: "Az Intune által felügyel iOS-eszközök visszaállítása biztonsági másolatból | Microsoft Intune"
description: "Útmutatás végfelhasználók számára arról, hogy hogyan regisztrálhatják újra a biztonsági másolatból visszaállított eszközüket."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 612b0954a81de1ee8d4a1e96c7440239437dec14
ms.openlocfilehash: 5fc4423f8fd0c5829be5fe6c96949e126991e430


---

# Az Intune által felügyelt iOS-eszközök visszaállítása biztonsági másolatból

Előfordulhatnak olyan esetek, amikor Önnek vagy az Ön felhasználóinak biztonsági másolatból kell visszaállítania egy iOS-eszközt, például amikor a felhasználó egy új eszközt kap. Jelen témakör ismerteti az Intune felügyelet beállítása során felmerülő további lépéseket az eszköz visszaállítását követően.

## Biztonsági mentések visszaállítása ugyanazon az eszközön

Ha a biztonsági mentés ugyanazon az eszközön kerül visszaállításra, akkor az eszköz regisztrációs állapota szintén visszaállításra kerül. Nincs szükség további műveletekre.

## Biztonsági mentések visszaállítása egy másik eszközön

Ha a biztonsági mentés egy másik eszközön kerül visszaállításra, akkor az eszköz regisztrációs állapota nem kerül automatikusan visszaállításra. [Az iOS-eszköz Intune-ban való regisztrálásához](/Intune/EndUser/enroll-your-device-in-intune-ios) a felhasználóknak a szabványos regisztrációs lépéseket kell követniük a Vállalati portál alkalmazás 2.1.22 vagy újabb verziójában.

> [!NOTE]
> Ha feltételes hozzáférési szabályzattokkal célozza meg a végfelhasználóit, akkor addig nem fognak tudni hozzáférni a vállalati e-mailekhez, amíg újra nem regisztrálnak.

> [!TIP]
> A következőképpen kommunikálhatja ezt a felhasználók felé: Az új eszköz regisztrációja előtt győződjön meg arról, hogy a Vállalati Portál alkalmazás 2.1.22 vagy újabb verziójú. A verzió ellenőrzéséhez nyissa meg a Vállalati alkalmazást, koppintson a menügombra a jobb felső sarokban, majd koppintson a Névjegy gombra. Ha egy korábbi verziót használ, akkor lépjen ki a Vállalati portál alkalmazásból, és nyissa meg az App Store-t. Koppintson a Frissítések gombra a jobb alsó sarokban, majd koppintson a listában a Vállalati portál elem mellett lévő Frissítés gombra. A frissítés befejeződése után indítsa el a Vállalati portál alkalmazást, és [regisztrálja eszközét az Intune-ban](/Intune/EndUser/enroll-your-device-in-intune-ios).



<!--HONumber=Oct16_HO2-->


