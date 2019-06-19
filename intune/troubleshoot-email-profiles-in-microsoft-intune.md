---
title: E-mail profilok hibaelhárítása a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg a gyakori problémák és megoldások e-mail-profilokkal a Microsoft Intune, beleértve a duplikált e-mail-profilok és a hibákat a Samsung KNOX Standard Android-eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/17/2019
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
ms.openlocfilehash: 2246e3f6faa853f620327558a7faf4dc9d6a6e85
ms.sourcegitcommit: 43ba5a05b2e1dc1997126d3574884f65cde449c7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/18/2019
ms.locfileid: "67197513"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Gyakori problémák és megoldásuk e-mail-profilokkal a Microsoft Intune-ban

Tekintse át az e-mail profil gyakori problémákat, és hogyan elhárításuk és megoldásuk.

## <a name="what-you-need-to-know"></a>Amit még tudnia kell

- E-mail profil van telepítve, a felhasználó, aki regisztrálta az eszközt. Az e-mail-profil konfigurálásához az Intune az Azure Active Directory (AD) tulajdonságokat használja az e-mail profilban, a felhasználó regisztráció során. [E-mail-beállításokat adhat hozzá az eszközökhöz](email-settings-configure.md) jól lehet.
- Az áttelepítés után a Configuration Manager – hibrid Intune önálló verziója, az e-mail profilt a Configuration Manager – hibrid marad az eszközön 7 napon. Ez az elvárt működés. Ha az e-mail-profil eltávolítása hamarabb van szüksége, forduljon a [Intune támogatási](get-support.md).
- Android Enterprise a Gmail vagy a kilenc használatához a felügyelt Google Play Store for üzembe helyezéséhez. [Felügyelt Google Play-alkalmazások hozzáadása](apps-add-android-for-work.md) felsorolja azokat a lépéseket.
- IOS-hez készült Microsoft Outlook és az Android nem támogatja az e-mail-profilok. Ehelyett az alkalmazás-konfigurációs házirend telepíteni. További információkért lásd: [Outlook konfigurációs beállítás](app-configuration-policies-outlook.md).
- Megcélzott eszközcsoportokat (nem a felhasználói csoportok), az e-mail-profilok nem lehet kézbesíteni az eszköz. Ha az eszköz elsődleges felhasználóval rendelkezik, majd eszköz célzó működnie kell. Ha az e-mail-profil tartalmazza a felhasználói tanúsítványok, mindenképpen felhasználói célcsoportok számára.
- Felhasználók, a jelszavát adja meg az e-mail-profil ismételten kérheti. Ebben az esetben ellenőrizze az e-mail profil által hivatkozott összes tanúsítvány. Ha a tanúsítványok nem rendel hozzá felhasználókhoz, majd Intune újrapróbálkozik az e-mail-profil központi telepítése.

## <a name="device-already-has-an-email-profile-installed"></a>Az eszköz már rendelkezik telepített e-mail profillal

Ha a felhasználók az Intune vagy Office 365 Mobileszköz regisztrálása előtt hozzon létre egy e-mail-profilt, az Intune által telepített e-mail profil előfordulhat, hogy nem várt módon működik:

- **iOS**: Intune az állomásnév és az e-mail-cím alapján egy meglévő, duplikált e-mail profilt észlel. A felhasználó által létrehozott e-mail-profil megakadályozza az Intune által létrehozott profil telepítését. Mivel az iOS-felhasználók általában létre egy e-mail-profilt a regisztráció Ez a gyakran okoz problémát. A vállalati portál alkalmazást, hogy a felhasználó nem megfelelő, és előfordulhat, hogy kérni a felhasználót, hogy az e-mail-profil eltávolítása az államokhoz.

  A felhasználónak ekkor törölnie az e-mail-profilt, így az Intune-profilt. Ez a probléma elkerülése érdekében kérje meg a felhasználók regisztráljanak, és engedélyezzék az Intune az e-mail-profil központi telepítése. Ezt követően a felhasználók hozhatnak létre az e-mail-profilt.

- **Windows**: Intune az állomásnév és az e-mail-cím alapján egy meglévő, duplikált e-mail profilt észlel. Az Intune felülírja a felhasználó által létrehozott meglévő e-mail profilt.

- **Samsung KNOX Standard**: Intune-ban azonosítja a duplikált e-mail fiókot az e-mail cím alapján, és felülírja azt az Intune-profillal. Ha a felhasználó a fiókot konfigurál, hogy ismételten felülírja az Intune-profillal. Emiatt előfordulhat, hogy egyértelműek a felhasználónak, amelynek a fiók konfigurációját felülíródik.

Samsung KNOX nem használja az állomásnevet a profil azonosításához. Azt javasoljuk, hogy ne hozzon létre több e-mail-profilok központi telepítése a különböző gazdagépeken, ugyanazt az e-mail címet, mivel ezek felülírják egymást.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>KNOX Standard-eszköz 0x87D1FDE8 hiba

**A probléma**: Miután létrehozott és az Exchange Active Sync e-mail-profilt a Samsung KNOX Standard különböző Android-eszközökön a **0x87D1FDE8** vagy **sikertelen szervizelés** hiba megjelenítése az eszközön Tulajdonságok > szabályzat lapján.

Ellenőrizze a Samsung KNOX EAS-profil és a forrásszabályzat konfigurációját. A Samsung Note eszközök szinkronizálási lehetősége már nem támogatott, és ezt a lehetőséget nem választható a profilban. Győződjön meg arról, hogy eszközök nincs elég ideje feldolgozni a házirendet, akár 24 óra.

## <a name="unable-to-send-images-from--email-account"></a>Nem sikerül képeket küldeni az e-mail fiókból

Automatikusan konfigurált e-mail fiókkal rendelkező felhasználók számára a képek nem tud küldeni az eszközeikről. Ez akkor fordulhat elő, ha **engedélyezése harmadik féltől származó alkalmazásokból küldendő e-mail** nincs engedélyezve.

### <a name="intune-solution"></a>Intune-megoldás

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Válassza ki **eszközkonfiguráció** > **profilok**.
3. Válassza ki az e-mail-profil > **tulajdonságok** > **beállítások**.
4. Állítsa be a **engedélyezése harmadik féltől származó alkalmazásokból küldendő e-mail** beállítást **engedélyezése**.

### <a name="configuration-manager-hybrid"></a>Configuration Manager – hibrid

1. Nyissa meg a Configuration Manager-konzol > **eszközök és megfelelőség**.

2. Bontsa ki a **áttekintése** > **megfelelőségi beállítások** > **hozzáférés a vállalati erőforrásokhoz**, és válassza ki **E-mail profilok**.

3. Kattintson a jobb gombbal az e-mail-profilra, és nyissa meg a **Tulajdonságok** menüt.

4. A **Szinkronizációs beállítások** lapon válassza a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** lehetőséget.

## <a name="next-steps"></a>További lépések

Első [segítséget a Microsoft támogatási](get-support.md), vagy használja a [közösségi fórumokat is talál](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
