---
title: "Intune-szabályzat alkalmazások engedélyezésére és letiltására Samsung Knox-eszközökön"
titlesuffix: Azure portal
description: "Egyéni profil létrehozása alkalmazások engedélyezéséhez és letiltásához Samsung Knox Standard-eszközökön."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 22d1e578da6a0085fd2e41ffc1d2322d01d971f1
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/03/2018
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Alkalmazások engedélyezése és letiltása egyéni szabályzattal Samsung Knox Standard-eszközökön a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ennek a témakörnek az eljárásait használva elkészíthet egy egyéni Microsoft Intune-szabályzatot, amellyel az alábbiak egyikét hozhatja létre:

- Az eszközön nem futtatható alkalmazások listája. A listában szereplő alkalmazások le lesznek tiltva, és nem futtathatóak még akkor sem, ha a szabályzat létrehozása előtt lettek telepítve.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Csak a listán szereplő alkalmazások telepíthetők. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung Knox Standard rendszerű eszközökön használhatók.

## <a name="create-an-allowed-or-blocked-app-list"></a>Az engedélyezett vagy tiltott alkalmazások listájának létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
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
-   **Adattípus** – A legördülő listából válassza a **Karakterlánc** elemet.
-   **OMA-URI** – Írja be a következőt: **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
-   **Érték** – Adja meg az engedélyezni kívánt alkalmazáscsomagok nevének listáját. Elválasztóként használhatja a **; : ,** vagy a **|** karaktereket. (Például csomag1;csomag2;)

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
