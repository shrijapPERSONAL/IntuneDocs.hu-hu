---
title: "Engedélyezett és letiltott alkalmazások KNOX-hoz | Microsoft Intune"
description: "Egyéni profil engedélyezett és letiltott alkalmazások listájának létrehozásához KNOX-eszközökön."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/09/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65d2c9c1f5d81dae33422bd4bf7c0e2e21bb96e4
ms.openlocfilehash: 937e291f193f61329598395baa63c24d7fefa25f



---
# Egyéni szabályzat használata alkalmazások engedélyezéséhez és letiltásához Samsung KNOX-eszközökön

Ennek a témakörnek az eljárásait használva elkészíthet egy egyéni Microsoft Intune-szabályzatot, amellyel az alábbiak egyikét hozhatja létre:

- Az eszközön nem futtatható alkalmazások listája. Más alkalmazás nem lesz futtatható. A listában szereplő alkalmazások le lesznek tiltva, és nem futtathatóak még akkor sem, ha a szabályzat létrehozása előtt lettek telepítve.
- Azon alkalmazások listája, amelyek telepítése engedélyezett az eszköz felhasználói számára a Google Play áruházból. Csak a listán szereplő alkalmazások telepíthetők. Az áruházból más alkalmazások nem telepíthetők.

Ezek a beállítások kizárólag a Samsung KNOX-ot futtató eszközökön használhatók.

## Az engedélyezett vagy tiltott alkalmazások listájának létrehozása:

1. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com/) válassza a **Házirend** &gt; **Konfigurációs szabályzatok** &gt; **Hozzáadás** lehetőséget.
2. Az **Új házirend létrehozása** párbeszédpanelen bontsa ki az **Android** elemet, majd válassza az **Egyéni konfiguráció**, majd a **Házirend létrehozása** lehetőséget.
3. Adja meg a szabályzat nevét és leírását (az utóbbi nem kötelező), majd az **OMA-URI beállítások** szakaszban válassza a **Hozzáadás** lehetőséget.
4. Az **OMA-URI beállítás hozzáadása vagy szerkesztése** párbeszédpanelen adja meg a következő információkat. Az eszközön nem futtatható alkalmazások listájához:
    
    - **A beállítás nevét.** Írja be a következőt: **PreventStartPackages**.
    - **A beállítás leírását.** Ha szeretné, beírhat egy leírást. Például: „Nem futtatható alkalmazások listája”.
    -   **Az adattípust.** A legördülő listából válassza a **Karakterlánc** elemet.
    -   **Az OMA-URI-t.** Írja be a következőt: **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
    -   **Az értéket.** Adja meg az engedélyezni kívánt alkalmazáscsomagok nevének listáját. Elválasztóként használhatja a **; : ,** vagy a **|** karaktereket. (Például csomag1;csomag2;)

    Azon alkalmazások listájához, amelyek telepítése engedélyezett a felhasználók számára a Google Play áruházból, miközben minden más alkalmazás le van tiltva:

    - **A beállítás nevét.** Írja be a következőt: **AllowInstallPackages**.
    - **A beállítás leírását.** Ha szeretné, beírhat egy leírást. Például: „A Google Play áruházból telepíthető alkalmazások listája”.
    - **Az adattípust.** A legördülő listából válassza a **Karakterlánc** elemet.
    - **Az OMA-URI-t.** Írja be a következőt: **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
    - **Az értéket.** Adja meg az engedélyezni kívánt alkalmazáscsomagok nevének listáját. Elválasztóként használhatja a **; : ,** vagy a **|** karaktereket. (Például csomag1;csomag2;)

4. Kattintson az **OK**, majd a **Szabályzat mentése** gombra. 

>[TIPP] Az alkalmazás csomagazonosítóját megtalálja, ha a Google Play áruházban tallózással kikeresi az alkalmazást. A csomagazonosítót az alkalmazáscsomag URL-címe tartalmazza. Például a Microsoft Word alkalmazás azonosítója **com.microsoft.office.word**.

Amikor az egyes megcélzott eszközök legközelebb bejelentkeznek, az alkalmazásbeállítások érvénybe lépnek.


## A szabályzat telepítése

1.  A **Házirend** munkaterületen válassza ki a telepíteni kívánt házirendet, majd kattintson a **Központi telepítés kezelése**lehetőségre.

2.  A **Központi telepítés kezelése** párbeszédpanelen válasszon egy vagy több csoportot, amelyhez a házirendet telepíteni szeretné, majd kattintson a **Hozzáadás** &gt; **OK** elemre.

 
Ha egy már telepített házirendet választ ki, a házirendlista alsó részén további információkat láthat róla.

### További információ
[Android- és Samsung KNOX-eszközök konfigurációs házirendjének beállításai a Microsoft Intune-ban](android-policy-settings-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


