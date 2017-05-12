---
title: "E-mail-beállítások konfigurálása az Intune-ban"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk bemutatja, hogyan konfigurálható az Intune arra, hogy a felügyelt eszközöket csatlakoztassa a vállalati levelezéshez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 37bfb7c9c35e5da5a346c822ed9d4252b5fff0e4
ms.contentlocale: hu-hu
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Az e-mail-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

E-mail-profilok segítségével konfigurálhatók a felügyelt eszközökön azok a beállítások, amelyek a vállalati levelezőrendszerhez való csatlakozáshoz és szinkronizáláshoz szükségesek. Ezáltal garantálható, hogy minden eszközön egységesek legyenek a beállítások, ráadásul kevesebbszer igényelnek segítséget olyan felhasználók, akik nem tudják a helyes e-mail-beállításokat.

A beépített levelezési ügyfélprogram a legtöbb platformon támogatott. A legtöbb külső levelezési alkalmazás egyelőre nem támogatott.

A következő eszköztípusokon konfigurálható a natív e-mail-ügyfélprogram e-mail-profilok segítségével:

- Android Samsung KNOX Standard (4.0-s és újabb verzió)
- Android for Work
- iOS 8.0 és újabb verziók
- Windows Phone 8.1 és újabb verziók
- Windows 10 (asztali rendszer) és Windows 10 Mobile

A témakörben található információk alapján megismerheti az e-mail-profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-email-settings"></a>Az e-mail-beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be az egyéni e-mail-profil nevét és leírását a **Név** és a **Leírás** mezőbe.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre alkalmazni szeretné az e-mail-beállításokat. Jelenleg az alábbi platformokra vonatkozóan lehet e-mail-eszközbeállításokat megadni:
    - **Android**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza az **E-mail** lehetőséget.
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Android-beállítások](email-profile-settings-for-android.md)
    - [iOS-beállítások](email-profile-settings-for-ios.md)
    - [Windows Phone 8.1-beállítások](email-profile-settings-for-windows-phone-8-1.md)
    - [Windows 10-beállítások](email-profile-settings-for-windows-10.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](how-to-assign-device-profiles.md) ismertető cikk nyújt tájékoztatást.

## <a name="further-information"></a>További információ

### <a name="remove-an-email-profile"></a>E-mail-profil eltávolítása

Ha egy eszközről törölni szeretne egy e-mail-profilt, módosítsa a hozzárendelését, és távolítson el minden olyan csoportot, amelynek tagja az eszköz. Megjegyzendő, hogy ha ez az egy e-mail-profil van az eszközön, nem lehet ezzel a módszerrel eltávolítani.

### <a name="securing-email-access"></a>Az e-mail-elérés védelme

Az e-mail-profilok biztonságossága az alábbi két módszer valamelyikével fokozható:

1. **Tanúsítványok** – Az e-mail-profil létrehozásakor válassza ki a korábban az Intune-ban már létrehozott tanúsítványprofilt. Ez identitástanúsítványként is ismert. Ezt hitelesíti a rendszer egy megbízható tanúsítványprofil (vagy főtanúsítvány) segítségével, hogy ellenőrizze a felhasználó eszközének csatlakozásra való jogosultságát. A megbízható tanúsítvány az e-mail-kapcsolatot hitelesítő számítógéphez van rendelve, amely általában a natív levelezési kiszolgáló.
A tanúsítványprofiloknak az Intune-ban történő létrehozásáról és használatáról a következő dokumentumban olvashat bővebben: [Tanúsítványok konfigurálása az Intune-nal](how-to-configure-certificates.md).
2. **Felhasználónév és jelszó** – A felhasználó a natív levelezési kiszolgálón a felhasználónév és a jelszó megadásával hitelesíti magát.
A jelszó nem szerepel az e-mail profilban, így a felhasználónak ezt minden alkalommal meg kell adnia, amikor az e-mail szolgáltatáshoz csatlakozik.


### <a name="how-intune-handles-existing-email-accounts"></a>Hogyan kezeli az Intune a meglévő e-mail-fiókokat?

Ha a felhasználó már konfigurálta az e-mail-fiókot, az eszközplatformtól függ az Intune-beli e-mail-profil hozzárendelésének eredménye:

- **iOS**: A rendszer az állomásnév és az e-mail-cím alapján egy már meglévő e-mail-profilt észlel. Az ugyanezeket az adatokat tartalmazó e-mail-profil megakadályozza az Intune-profil hozzárendelését. Ebben az esetben a Munkahelyi portál tájékoztatja a felhasználót, hogy nem felel meg a szabályoknak, és felkéri a manuálisan konfigurált profil törlésére. A probléma megelőzése érdekében kérje meg a felhasználókat, hogy az e-mail-profil telepítése előtt regisztrálják az eszközeiket, mert ez engedélyezi az Intune-nak a profil telepítését.
- **Windows**: A rendszer az állomásnév és az e-mail-cím alapján egy már meglévő e-mail profilt észlel. Az Intune felülírja a felhasználó által létrehozott meglévő e-mail profilt.
- **Android**: A rendszer az e-mail-cím alapján egy már meglévő e-mail-profilt észlel, és felülírja az Intune-profillal.
Mivel az Android nem használja az állomásnevet a profil azonosításához, ezért azt javasoljuk, hogy ne hozzon létre több e-mail-profilt azért, hogy ugyanahhoz az e-mail-címhez használja őket a különböző gazdagépeken, ezek ugyanis felülírják egymást.

### <a name="update-an-email-profile"></a>E-mail-profil frissítése

Ha egy már hozzárendelt e-mail-profilt módosít, a végfelhasználókat a rendszer arra kérheti, hogy fogadják el az e-mail-beállítások újrakonfigurálását.

