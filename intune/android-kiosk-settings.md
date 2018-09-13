---
title: Kioszkbeállítások Android rendszerhez a Microsoft Intune-ban – Azure | Microsoft Docs
description: Androidos kioszkeszközeit egyalkalmazásos és többalkalmazásos kioszkként is konfigurálhatja.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cef98527ee2c281547f8046f3c6f08275d8f0807
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329383"
---
# <a name="kiosk-settings-for-android-devices-in-intune"></a>Android-eszközök kioszkbeállításai az Intune-ban

Az eszközöket egy- vagy többalkalmazásos kioszkmódra is konfigurálhatja az eszközkonfigurációs beállítások használatával. Amikor egy eszköz kioszkmódban van, az eszköz használata a korlátozó profilban meghatározott alkalmazás(ok)ra vagy webes hivatkozásokra van korlátozva. 

## <a name="restrict-an-android-kiosk-device-to-a-single-app"></a>Androidos kioszkeszköz korlátozása egyetlen alkalmazásra

Ha egy kioszkeszköz korlátozó profiljának beállítása **Kioszkmód** = **Egyalkalmazásos kioszk**, akkor a felhasználók csak egy alkalmazáshoz férnek hozzá. Egy így konfigurált eszköz indulásakor elindul a megadott alkalmazás. A felhasználók nem nyithatnak meg új alkalmazásokat, és nem módosíthatják a futó alkalmazást.

1. Gondoskodjon arról, hogy a kioszkeszközön használni kívánt alkalmazás [telepítve legyen az eszközön](apps-deploy.md), és hogy az alkalmazás hozzá legyen rendelve a kioszkeszközökhöz létrehozott eszközcsoporthoz.
2. Nyissa meg az [Intune portált](https://portal.azure.com), és válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. A **Profil létrehozása** panelen töltse ki a következő mezőket:
     - **Név**
     - **Platform**: Vállalati Android
     - **Profiltípus**: Csak az eszköz tulajdonosa > Eszközkorlátozások
4. Válassza a **Beállítások** > **Kioszk** lehetőséget.
5. A **Kioszkmód** értékének válassza az **Egyalkalmazásos kioszk** értéket.
6. Válassza a **Felügyelt alkalmazás kijelölése** lehetőséget, majd válassza ki azt a felügyelt Google Play-alkalmazást, amelyet a profilt használó eszközökön egyedül elérhető alkalmazásként kíván beállítani.
7. Válassza az **OK** > **OK** > **OK** > **Létrehozás** lehetőségeket.
8. Válassza ki a most létrehozott profilt > **Hozzárendelések**.
9. A **Hozzárendelés a következőhöz** alatt válassza a **Kijelölt csoportok** lehetőséget.
10. Válassza a **Belefoglalandó csoportok kijelölése** lehetőséget, jelölje ki a kioszkeszközeihez létrehozott eszközcsoportot, majd válassza a **Kiválasztás** lehetőséget.

## <a name="restrict-a-kiosk-device-to-a-set-of-apps-or-web-links"></a>Kioszkeszköz korlátozása alkalmazások vagy webes hivatkozások egy csoportjára

Ha egy kioszkeszköz korlátozó profiljának beállítása **Kioszkmód** = **Többalkalmazásos kioszk**, akkor a felhasználók csak a konfigurációban megadott korlátozott számú alkalmazáshoz férnek hozzá. Megadhat webes hivatkozásokat is, amelyeket a felhasználók megnyithatnak. Ennek a szabályzatnak az alkalmazásakor a felhasználók az engedélyezett alkalmazások ikonjait látják a kezdőképernyőn.

Androidos kioszkeszköz több alkalmazásra való beállításához kövesse az alábbi fő lépéseket:

1. [A Managed Home Screen alkalmazás importálása és telepítése a Google Play Áruházból](#import-and -deploy-the-managed-home-screen-app)
2. [A kioszkmódban használható alkalmazások hozzáadása és hozzárendelése](#add-and-assign-apps-that-can-be-used-in-kiosk-mode)
3. (Nem kötelező) [A kioszkmódban használható webes hivatkozások hozzáadása](#add-web-links-that-can-be-used-in-kiosk-mode)

### <a name="import-and-deply-the-managed-home-screen-app"></a>A Managed Home Screen alkalmazás importálása és telepítése

1. Nyissa meg a [Google Play Managed Home Screen oldalát](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) és jelentkezzen be a többi felügyelt Google Play-alkalmazáshoz használt fiókkal.
2. Válassza a **Jóváhagyás** lehetőséget.
3. Nyissa meg az [Intune-portált](https://portal.azure.com), és válassza az **Ügyfélalkalmazások** > **Felügyelt Google Play** > **Szinkronizálás** lehetőséget.
4. Válassza az **Alkalmazások** > **Managed Home Screen** > **Hozzárendelések** > **Csoport hozzáadása** lehetőséget.
5. A **Hozzárendelés típusa** alatt válassza a **Kötelező** lehetőséget.
6. Válassza a **Belefoglalt csoportok** > **Belefoglalandó csoportok kijelölése** lehetőséget, jelölje ki a kioszkeszközeihez létrehozott eszközcsoportot, majd válassza a **Kiválasztás** > **OK** > **OK** > **Mentés** lehetőséget.

### <a name="add-and-assign-apps-that-can-be-used-in-kiosk-mode"></a>A kioszkmódban használható alkalmazások hozzáadása és hozzárendelése

A kioszkmódban elérhetővé tenni kívánt alkalmazások mindegyikénél hajtsa végre a következő lépéseket:

1. [Adja hozzá az alkalmazást az Intune-hoz](store-apps-android.md).
2. Válassza az **Ügyfélalkalmazások** > **Alkalmazások** > jelölje ki az alkalmazást > **Hozzárendelések** > **Csoport hozzáadása** lehetőséget.
3. A **Hozzárendelés típusa** alatt válassza a **Kötelező** lehetőséget.
4. Válassza a **Belefoglalt csoportok** > **Belefoglalandó csoportok kijelölése** lehetőséget, jelölje ki a kioszkeszközeihez létrehozott eszközcsoportot, majd válassza a **Kiválasztás** > **OK** > **OK** > **Mentés** lehetőséget.

### <a name="add-web-links-that-can-be-used-in-kiosk-mode"></a>A kioszkmódban használható webes hivatkozások hozzáadása

1. Nyissa meg az [Intune-portált](https://portal.azure.com), és válassza az **Ügyfélalkalmazások** > **Alkalmazások** > **Hozzáadás** lehetőséget.
2. Az **Alkalmazástípus** alatt válassza a **Webes hivatkozás** lehetőséget.
3. Válassza a **Konfigurálás** lehetőséget, és adja meg a szükséges információkat. Logót nem kell hozzáadnia, mert az automatikusan ki lesz nyerve a webhely favicon.ico fájljából.
4. Válassza az **OK** > **Hozzáadás** lehetőséget.

Győződjön meg róla, hogy üzembe helyezett egy böngészőalkalmazást a kioszkmódban lévő eszközökön a [Mobile Apps](apps-add.md) használatával.

### <a name="create-a-multi-app-kiosk-profile"></a>Többalkalmazásos kioszkprofil létrehozása

1. Nyissa meg az [Intune portált](https://portal.azure.com), és válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. A **Profil létrehozása** panelen töltse ki a következő mezőket:
     - **Név**: Írjon be egy beszédes nevet
     - **Platform**: Vállalati Android
     - **Profiltípus**: Csak az eszköz tulajdonosa > Eszközkorlátozások
4. Válassza a **Beállítások** > **Kioszk** lehetőséget.
5. A **Kioszkmód** értékének válassza a **Többalkalmazásos kioszk** értéket.
6. Válassza a **Hozzáadás** lehetőséget, majd jelölje ki azokat az alkalmazásokat és webes hivatkozásokat, amelyeket az ezt a profilt használó eszközökön elérhetővé kíván tenni.
7. Válassza az **OK** > **OK** > **OK** > **Létrehozás** lehetőségeket.
8. Válassza ki a most létrehozott profilt > **Hozzárendelések**.
9. A **Hozzárendelés a következőhöz** alatt válassza a **Kijelölt csoportok** lehetőséget.
10. Válassza a **Belefoglalandó csoportok kijelölése** lehetőséget, jelölje ki a kioszkeszközeihez létrehozott eszközcsoportot, majd válassza a **Kiválasztás** > **Mentés** lehetőséget.

## <a name="next-steps"></a>További lépések
[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
