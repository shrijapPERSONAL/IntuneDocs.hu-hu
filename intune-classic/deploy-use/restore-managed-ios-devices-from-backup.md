---
title: "Az Intune által felügyelt iOS-eszközök visszaállítása biztonsági másolatból"
description: "Útmutatás végfelhasználók számára arról, hogy hogyan regisztrálhatják újra a biztonsági másolatból visszaállított eszközüket."
keywords: "visszaállítás, felügyelt, iOS"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 7fc99a944000a8d5ecfc09ebc2e956e7c0f201c9
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---

# <a name="restore-intune-managed-ios-devices-from-backup"></a>Az Intune által felügyelt iOS-eszközök visszaállítása biztonsági másolatból

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Előfordulhatnak olyan esetek, amikor Önnek vagy az Ön felhasználóinak biztonsági másolatból kell visszaállítania egy iOS-eszközt, például amikor a felhasználó egy új eszközt kap. Jelen témakör ismerteti az Intune felügyelet beállítása során felmerülő további lépéseket az eszköz visszaállítását követően.

## <a name="restoring-backups-onto-the-same-device"></a>Biztonsági mentések visszaállítása ugyanazon az eszközön

Ha a biztonsági mentés ugyanazon az eszközön kerül visszaállításra, akkor az eszköz regisztrációs állapota szintén visszaállításra kerül. Nincs szükség további műveletekre.

## <a name="restoring-backups-onto-different-devices"></a>Biztonsági mentések visszaállítása egy másik eszközön

Ha a biztonsági mentés egy másik eszközön kerül visszaállításra, akkor az eszköz regisztrációs állapota nem kerül automatikusan visszaállításra. [Az iOS-eszköz Intune-ban való regisztrálásához](/intune-user-help/enroll-your-device-in-intune-ios) a felhasználóknak a szabványos regisztrációs lépéseket kell követniük a Vállalati portál alkalmazás 2.1.22 vagy újabb verziójában.

> [!NOTE]
> Ha feltételes hozzáférési szabályzattokkal célozza meg a végfelhasználóit, akkor addig nem fognak tudni hozzáférni a vállalati e-mailekhez, amíg újra nem regisztrálnak.

> [!TIP]
> A következőképpen kommunikálhatja ezt a felhasználók felé: Az új eszköz regisztrációja előtt győződjön meg arról, hogy a Vállalati Portál alkalmazás 2.1.22 vagy újabb verziójú. A verzió ellenőrzéséhez nyissa meg a Vállalati alkalmazást, koppintson a menügombra a jobb felső sarokban, majd koppintson a Névjegy gombra. Ha egy korábbi verziót használ, akkor lépjen ki a Vállalati portál alkalmazásból, és nyissa meg az App Store-t. Koppintson a Frissítések gombra a jobb alsó sarokban, majd koppintson a listában a Vállalati portál elem mellett lévő Frissítés gombra. A frissítés befejeződése után indítsa el a Vállalati portál alkalmazást, és [regisztrálja eszközét az Intune-ban](/intune-user-help/enroll-your-device-in-intune-ios).

## <a name="resolving-known-issues-with-restores"></a>Ismert problémák megoldása visszaállítással

A felhasználók nehézségekbe ütközhetnek, ha az eszköz visszaállítása után elindítják a Vállalati portál alkalmazást, miközben továbbra is a Vállalati portál 2.1.21 vagy annál régebbi verzióját használják. Ezeket a nehézségeket a felhasználó helyzetét figyelembe vevő, megfelelő lépésekkel lehet orvosolni.

### <a name="for-users-who-will-only-use-their-new-device"></a>Olyan felhasználók esetében, akik csak új eszközt fognak használni
Indítsa el a Vállalati portál alkalmazást, és a jelenlegi eszköz csempéjét kiválasztva, majd az __Eltávolítás__ gombra koppintva végezze el a regisztráció visszavonását. Eltávolítás után kövesse a normál regisztrációs lépéseket az [iOS-eszközök Intune-ban való regisztrációjához](/intune-user-help/enroll-your-device-in-intune-ios).

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a>Olyan felhasználók esetében, akik egyszerre fogják használni a régi és az új eszközeiket
Törölje a cookie-kat a Safari böngészőből a __Beállítások__ > __Safari__ > __Előzm. és webhelyadatok törlése__ elemre koppintva. A cookie-k törlése után távolítsa el és telepítse újra a Vállalati portál alkalmazást, majd kövesse a normál regisztrációs lépéseket az [iOS-eszközök Intune-ban való regisztrációjához](/intune-user-help/enroll-your-device-in-intune-ios).

