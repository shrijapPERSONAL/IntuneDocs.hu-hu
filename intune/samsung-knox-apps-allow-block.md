---
title: "Intune-szabályzat alkalmazások engedélyezésére/letiltására Samsung KNOX-eszközökön"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Egyéni profil létrehozása alkalmazások engedélyezéséhez és letiltásához Samsung KNOX Standard-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: dea090e108d5ea023dc64d8d168b25d30b688cb2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017



---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Alkalmazások engedélyezése és letiltása egyéni szabályzattal Samsung KNOX Standard-eszközökön a Microsoft Intune-ban
[!INCLUDE[azure_preview](./includes/azure_preview.md)] Ennek a témakörnek az eljárásaival elkészíthet egy egyéni Microsoft Intune-szabályzatot, amellyel az alábbiak egyikét hozhatja létre:

- Az eszközön nem futtatható alkalmazások listája. A listában szereplő alkalmazások le lesznek tiltva, és nem futtathatóak még akkor sem, ha a szabályzat létrehozása előtt lettek telepítve.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Csak a listán szereplő alkalmazások telepíthetők. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung Knox Standard rendszerű eszközökön használhatók.

## <a name="create-an-allowed-or-blocked-app-list"></a>Az engedélyezett vagy tiltott alkalmazások listájának létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
2. A profilok listáját mutató panelen válassza a **Profil létrehozása** lehetőséget.
3. A **Profil létrehozása** panelen írja be az eszközprofilra vonatkozó **Név** és **Leírás** (nem kötelező) szövegét.
2. Válassza az **Android** lehetőséget a **Platformtípus** beállításnál, valamint az **Egyéni** profiltípust.
3. Kattintson a **Beállítások** elemre.
3. Az **Egyéni OMA-URI beállítások** panelen válassza a **Hozzáadás** lehetőséget.
4. Az **OMA-URI beállítás hozzáadása vagy szerkesztése** párbeszédpanelen adja meg a következőket:

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>Az eszközön nem futtatható alkalmazások listájához:

- **Név** – Írja be a következőt: **PreventStartPackages**.
- **Leírás** – Igény esetén beírhat egy leírást. Például: „Nem futtatható alkalmazások listája”.
-     **Adattípus** – A legördülő listából válassza a **Karakterlánc** elemet.
-     **OMA-URI** – Írja be a következőt: **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
-     **Érték** – Adja meg az engedélyezni kívánt alkalmazáscsomagok nevének listáját. Elválasztóként használhatja a **; : ,** vagy a **|** karaktereket. (Például csomag1;csomag2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Azon alkalmazások listájához, amelyek telepítése engedélyezett a felhasználók számára a Google Play áruházból, miközben minden más alkalmazás le van tiltva:
- **Név** – Írja be a következőt: **AllowInstallPackages**.
- **Leírás** – Igény esetén megadhat egy leírást. Például: „A Google Play áruházból telepíthető alkalmazások listája”.
- **Adattípus** – A legördülő listából válassza a **Karakterlánc** elemet.
- **OMA-URI** – Írja be a következőt: **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
- **Érték** – Adja meg az engedélyezni kívánt alkalmazáscsomagok nevének listáját. Elválasztóként használhatja a **; : ,** vagy a **|** karaktereket. (Például csomag1;csomag2;)

4. Kattintson az **OK** gombra, majd a **Profil létrehozása** panelen válassza a **Létrehozás** lehetőséget.

>[!TIP]
> Az alkalmazás csomagazonosítóját úgy tudja megtalálni, hogy a Google Play áruházban megkeresi az alkalmazás oldalát. A csomagazonosítót az alkalmazáscsomag URL-címe tartalmazza. Például a Microsoft Word alkalmazás azonosítója **com.microsoft.office.word**.

Amikor az egyes megcélzott eszközök legközelebb bejelentkeznek, az alkalmazásbeállítások érvénybe lépnek.


<!---## Assign the custom profile--->

