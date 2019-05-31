---
title: E-mail profilok hibaelhárítása a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg a gyakori problémák és megoldások e-mail-profilokkal a Microsoft Intune, beleértve a duplikált e-mail-profilok és a hibákat a Samsung KNOX Standard Android-eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0fe37deb63457fef869df0f7263970a4e53cb29
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402707"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Gyakori problémák és megoldásuk e-mail-profilokkal a Microsoft Intune-ban

Tekintse át az e-mail profil gyakori problémákat, és hogyan elhárításuk és megoldásuk.

## <a name="device-already-has-an-email-profile-installed"></a>Az eszköz már rendelkezik telepített e-mail profillal

Ha a felhasználók e-mail-profil létrehozása előtt az Intune-ban, az Intune e-mail profil előfordulhat, hogy nem várt módon működik:

- **iOS**: Intune az állomásnév és az e-mail-cím alapján egy meglévő, duplikált e-mail profilt észlel. A felhasználó által létrehozott e-mail-profil megakadályozza az Intune által létrehozott profil telepítését. Mivel az iOS-felhasználók általában létre egy e-mail-profilt a regisztráció Ez a gyakran okoz problémát. A vállalati portál alkalmazást, hogy a felhasználó nem megfelelő, és előfordulhat, hogy kérni a felhasználót, hogy az e-mail-profil eltávolítása az államokhoz.

  A felhasználónak ekkor törölnie az e-mail-profilt, így az Intune-profilt. Ez a probléma elkerülése érdekében kérje meg a felhasználók regisztráljanak, és engedélyezzék az Intune az e-mail-profil központi telepítése. Ezt követően a felhasználók hozhatnak létre az e-mail-profilt.

- **Windows**: Intune az állomásnév és az e-mail-cím alapján egy meglévő, duplikált e-mail profilt észlel. Az Intune felülírja a felhasználó által létrehozott meglévő e-mail profilt.

- **Samsung KNOX Standard**: Intune-ban azonosítja a duplikált e-mail fiókot az e-mail cím alapján, és felülírja azt az Intune-profillal. Ha a felhasználó a fiókot konfigurál, hogy ismételten felülírja az Intune-profillal. Emiatt előfordulhat, hogy egyértelműek a felhasználónak, amelynek a fiók konfigurációját felülíródik.

Samsung KNOX nem használja az állomásnevet a profil azonosításához. Azt javasoljuk, hogy ne hozzon létre több e-mail-profilok központi telepítése a különböző gazdagépeken, ugyanazt az e-mail címet, mivel ezek felülírják egymást.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>KNOX Standard-eszköz 0x87D1FDE8 hiba

**A probléma**: Miután létrehozott és az Exchange Active Sync e-mail-profilt a Samsung KNOX Standard különböző Android-eszközökön a **0x87D1FDE8** vagy **sikertelen szervizelés** hiba megjelenítése az eszközön Tulajdonságok > szabályzat lapján.

Ellenőrizze a Samsung KNOX EAS-profil és a forrásszabályzat konfigurációját. A Samsung Note eszközök szinkronizálási lehetősége már nem támogatott, és ezt a lehetőséget nem választható a profilban. Győződjön meg arról, hogy eszközök nincs elég ideje feldolgozni a házirendet, akár 24 óra.

## <a name="unable-to-send-images-from--email-account"></a>Nem sikerül képeket küldeni az e-mail fiókból

Az Intune-ra vonatkozik a klasszikus Azure portálon.

Automatikusan konfigurált e-mail fiókkal rendelkező felhasználók számára a képek nem tud küldeni az eszközeikről. Ez akkor fordulhat elő, ha **engedélyezése harmadik féltől származó alkalmazásokból küldendő e-mail** nincs engedélyezve.

### <a name="intune-solution"></a>Intune-megoldás

1. Válassza ki a Microsoft Intune felügyeleti konzol megnyitása **házirend** számítási feladatok > **konfigurációs szabályzat**.

2. Válassza ki a kívánt e-mail-profilt, majd válassza a **Szerkesztés** lehetőséget.

3. Válassza ki a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** beállítást.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Intune-megoldással integrált Configuration Manager

1. Nyissa meg a Configuration Manager-konzol > **eszközök és megfelelőség**.

2. Bontsa ki a **áttekintése** > **megfelelőségi beállítások** > **hozzáférés a vállalati erőforrásokhoz**, és válassza ki **E-mail profilok**.

3. Kattintson a jobb gombbal az e-mail-profilra, és nyissa meg a **Tulajdonságok** menüt.

4. A **Szinkronizációs beállítások** lapon válassza a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** lehetőséget.

## <a name="next-steps"></a>További lépések

Első [segítséget a Microsoft támogatási](get-support.md), vagy használja a [közösségi fórumokat is talál](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).