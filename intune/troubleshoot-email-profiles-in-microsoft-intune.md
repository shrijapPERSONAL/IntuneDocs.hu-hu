---
title: E-mail profilok hibaelhárítása a Microsoft Intune – Azure |} A Microsoft Docs
description: Az e-mail-profilokkal kapcsolatos problémák, valamint az elhárításuk és megoldásuk ismertetése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 228f4fd64cb8f09f18579225b271c31894bd1df4
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235565"
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>E-mail profilok hibaelhárítása a Microsoft Intune-ban

Tekintse át az e-mail profil gyakori problémákat, és hogyan elhárításuk és megoldásuk.

Ha ezek az információk nem segítettek, akkor [támogatást kérhet a Microsoft Intune-hoz](get-support.md).

## <a name="unable-to-send-images-from--email-account"></a>Nem sikerül képeket küldeni az e-mail fiókból
Az Intune-ra vonatkozik a klasszikus Azure portálon.

Az automatikusan konfigurált e-mail fiókkal rendelkező felhasználók nem tudnak képeket küldeni az eszközeikről. Ez akkor fordulhat elő, ha **engedélyezése harmadik féltől származó alkalmazásokból küldendő e-mail** nincs engedélyezve.

### <a name="intune-solution"></a>Intune-megoldás

1. Válassza ki a Microsoft Intune felügyeleti konzol megnyitása **házirend** számítási feladatok > **konfigurációs szabályzat**.

2. Válassza ki a kívánt e-mail-profilt, majd válassza a **Szerkesztés** lehetőséget.

3. Válassza ki a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** beállítást.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Intune-megoldással integrált Configuration Manager

1. Nyissa meg a Configuration Manager-konzol > **eszközök és megfelelőség**.

2. Bontsa ki a **áttekintése** > **megfelelőségi beállítások** > **hozzáférés a vállalati erőforrásokhoz**, és válassza ki **E-mail profilok**.

3. Kattintson a jobb gombbal az e-mail-profilra, és nyissa meg a **Tulajdonságok** menüt.

4. A **Szinkronizációs beállítások** lapon válassza a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** lehetőséget.

## <a name="device-already-has-an-email-profile-installed"></a>Az eszköz már rendelkezik telepített e-mail profillal

Ha a felhasználó egy e-mail-profilt az Intune-profil provisionining előtt telepítette, az Intune e-mail profil telepítésének eredménye az eszköz platformjától függ:

- **iOS**: Intune az állomásnév és az e-mail-cím alapján egy meglévő, duplikált e-mail profilt észlel. A felhasználó által létrehozott, duplikált e-mail profil meggátolja az Intune-rendszergazda által létrehozott profil telepítését. Mivel az iOS-felhasználók általában létre egy e-mail-profilt a regisztráció Ez a gyakran okoz problémát. A vállalati portál frissül a felhasználót, hogy nem megfelelő, mert az manuálisan beállított e-mail-profilt, és kéri a felhasználót, távolítsa el a profilt. A felhasználónak ekkor törölnie kell az e-mail-profilt, hogy az Intune-profilt telepíthesse. A probléma elkerülése érdekében kérje meg a felhasználók regisztráljanak, és telepítse a profilt az Intune lehetővé teszi. Ezután telepítse a felhasználó által létrehozott e-mail-profilt.

- **Windows**: Intune az állomásnév és az e-mail-cím alapján egy meglévő, duplikált e-mail profilt észlel. Az Intune felülírja a felhasználó által létrehozott meglévő e-mail profilt.

- **Samsung KNOX Standard**: Intune-ban azonosítja a duplikált e-mail fiókot az e-mail cím alapján, és felülírja azt az Intune-profillal. Ha a felhasználó a fiókot konfigurál, hogy ismételten felülírja az Intune-profillal. Emiatt előfordulhat, hogy egyértelműek a felhasználónak, amelynek a fiók konfigurációját felülíródik.

Samsung KNOX nem használja az állomásnevet a profil azonosításához. Azt javasoljuk, hogy nem hoz létre több e-mail-profilok központi telepítése ugyanazt az e-mail címet a különböző gazdagépeken, mivel ezek felülírják egymást.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>KNOX Standard-eszköz 0x87D1FDE8-as hibája
**A probléma**: Miután létrehozta és üzembe helyezése egy Exchange Active Sync e-mail-profilt a Samsung KNOX Standard különféle Androidos eszközökhöz, a hiba **0x87D1FDE8** vagy **sikertelen szervizelés** az eszköz a jelentett Tulajdonságok > szabályzat lapján.

Ellenőrizze a Samsung KNOX EAS-profil és a forrásszabályzat konfigurációját. A Samsung Note eszközök szinkronizálási lehetősége a továbbiakban nem támogatott, és ez a lehetőség nem választható a profilban. Győződjön meg arról, hogy eszközök nincs elég ideje feldolgozni a házirendet, akár 24 óra.

## <a name="next-steps"></a>További lépések
Ha ezek az információk nem segítettek, akkor [támogatást kérhet a Microsoft Intune-hoz](get-support.md).
