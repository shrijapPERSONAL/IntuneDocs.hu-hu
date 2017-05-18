---
title: "Engedélyezett és letiltott alkalmazások KNOX-hoz | Microsoft Docs"
description: "Egyéni profil engedélyezett és letiltott alkalmazások listájának létrehozásához KNOX-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: adf7e2d0f76e63f67b7cf3d26d26df0da0e50bd0
ms.openlocfilehash: 933a47163ccc66a1bab636982ca422c4a704656d
ms.lasthandoff: 03/31/2017



---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Egyéni szabályzat használata alkalmazások engedélyezéséhez és letiltásához Samsung Knox Standard-eszközökön

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ennek a témakörnek az eljárásait használva elkészíthet egy egyéni Microsoft Intune-szabályzatot, amellyel az alábbiak egyikét hozhatja létre:

- Az eszközön nem futtatható alkalmazások listája. A listában szereplő alkalmazások le lesznek tiltva, és nem futtathatóak még akkor sem, ha a szabályzat létrehozása előtt lettek telepítve.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Csak a listán szereplő alkalmazások telepíthetők. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung Knox Standard rendszerű eszközökön használhatók.

## <a name="to-create-an-allowed-or-blocked-app-list"></a>Az engedélyezett vagy tiltott alkalmazások listájának létrehozása:

1. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com/) válassza a **Házirend** &gt; **Konfigurációs szabályzatok** &gt; **Hozzáadás** lehetőséget.
2. Az **Új házirend létrehozása** párbeszédpanelen bontsa ki az **Android** elemet, majd válassza az **Egyéni konfiguráció**, majd a **Házirend létrehozása** lehetőséget.
3. Adja meg a szabályzat nevét és leírását (az utóbbi nem kötelező), majd az **OMA-URI beállítások** szakaszban válassza a **Hozzáadás** lehetőséget.
4. Az **OMA-URI beállítás hozzáadása vagy szerkesztése** párbeszédpanelen adja meg a következő információkat. Az eszközön nem futtatható alkalmazások listájához:
    
    - **A beállítás neve:** Írja be a következőt: **PreventStartPackages**.
    - **A beállítás leírása:** Ha szeretné, beírhat egy leírást. Például: „Nem futtatható alkalmazások listája”.
    -     **Adattípus:** A legördülő listából válassza a **Karakterlánc** elemet.
    -     **OMA-URI:** Írja be a következőt: **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
    -     **Érték:** Adja meg a letiltani kívánt alkalmazáscsomagok nevének listáját. Elválasztóként használhatja a **; : ,** vagy a **|** karaktereket. (Például csomag1;csomag2;)

    Azon alkalmazások listájához, amelyek telepítése engedélyezett a felhasználók számára a Google Play áruházból, miközben minden más alkalmazás le van tiltva:

    - **A beállítás neve:** Írja be a következőt: **AllowInstallPackages**.
    - **A beállítás leírása:** Ha szeretné, beírhat egy leírást. Például: „A Google Play áruházból telepíthető alkalmazások listája”.
    - **Adattípus:** A legördülő listából válassza a **Karakterlánc** elemet.
    - **OMA-URI:** Írja be a következőt: **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
    - **Érték:** Adja meg az engedélyezni kívánt alkalmazáscsomagok nevének listáját. Elválasztóként használhatja a **; : ,** vagy a **|** karaktereket. (Például csomag1;csomag2;)

4. Kattintson az **OK**, majd a **Szabályzat mentése** gombra. 

>[!TIP]
> Az alkalmazás csomagazonosítóját úgy tudja megtalálni, hogy a Google Play áruházban megkeresi az alkalmazás oldalát. A csomagazonosítót az alkalmazáscsomag URL-címe tartalmazza. Például a Microsoft Word alkalmazás azonosítója **com.microsoft.office.word**.

Amikor az egyes megcélzott eszközök legközelebb bejelentkeznek, az alkalmazásbeállítások érvénybe lépnek.


## <a name="deploy-the-policy"></a>A szabályzat telepítése

1.  A **Házirend** munkaterületen válassza ki a telepíteni kívánt házirendet, majd kattintson a **Központi telepítés kezelése**lehetőségre.

2.  A **Központi telepítés kezelése** párbeszédpanelen válasszon egy vagy több csoportot, amelyhez a házirendet telepíteni szeretné, majd kattintson a **Hozzáadás** &gt; **OK** elemre.

 
Ha egy már telepített házirendet választ ki, a házirendlista alsó részén további információkat láthat róla.

### <a name="see-also"></a>További információ
[Android- és Samsung KNOX-eszközök konfigurációs szabályzatának beállításai a Microsoft Intune-ban](android-policy-settings-in-microsoft-intune.md)

