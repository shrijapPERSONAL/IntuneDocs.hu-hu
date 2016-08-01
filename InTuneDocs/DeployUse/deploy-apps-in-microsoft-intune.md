---
title: "Alkalmazások telepítése | Microsoft Intune"
description: "A témakörben található információk segítséget nyújtanak az alkalmazások Microsoft Intune-on keresztüli telepítésében."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ef1d2d69acfeea9670324f580d33b191001ffa9
ms.openlocfilehash: 8ab2517a11ecb6ae5395814472dfbb3e83da132b

---
# Alkalmazások telepítése a Microsoft Intune-ban

A témakörben található információk segítséget nyújtanak az alkalmazások Microsoft Intune-on keresztüli telepítésében.


## Alkalmazások telepítése
Az alábbi eljárással teheti elérhetővé az alkalmazást telepítésre az eszközök vagy felhasználók kiválasztott csoportja számára.

### Alkalmazás telepítése

1. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) kattintson az **Alkalmazások** &gt; **Alkalmazások** elemre az Ön által kezelt alkalmazások listájának megtekintéséhez.

2.  Jelölje ki a telepíteni kívánt alkalmazást, majd kattintson a **Központi telepítés kezelése** elemre.

3.  Az *&lt;alkalmazásnév&gt;* párbeszédpanel **Csoportok kiválasztása** lapján adja meg, hogy mely felhasználói vagy eszközcsoportok számára kívánja telepítésre elérhetővé tenni az alkalmazást.

4.  A **Központi telepítési művelet** lapon konfigurálja az alábbiakat:

    - **Jóváhagyás** – Adja meg a következő értékek egyikét:
        - **Kötelező** (kötelező telepítés)
        - **Rendelkezésre álló** (a felhasználók igény szerint telepíthetik a vállalati portálról)
        - **Nem alkalmazható** (az alkalmazás nincs telepítve, vagy nem jelenik meg a vállalati portálon)
        - **Eltávolítás** (az alkalmazás eltávolítása a kiválasztott eszközökről).
    - **Határidő** – A kötelező telepítések esetében adja meg, hogy mikor szeretné telepíteni az alkalmazást. Válasszon az előre meghatározott értékek közül, vagy válassza az **Egyéni** lehetőséget a kívánt határidő beállításához.

5. Ha a telepítésre elérhetővé tett alkalmazás konfigurálható mobilalkalmazás-felügyeleti szabályzattal, a **Mobilalkalmazás-kezelés** lap is megjelenik. Ezen a lapon választhatja ki az alkalmazáshoz hozzárendelni kívánt mobilalkalmazás-felügyeleti házirendet.

    [Itt megtekintheti a mobilalkalmazás-felügyeleti házirendekkel kompatibilis Microsoft-alkalmazásokat.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Ha a telepítésre elérhetővé tett alkalmazás kompatibilis az Intune VPN-profiljaival, a **VPN-profil** lap is megjelenik. Ezen a lapon hozzárendelheti az iOS-alkalmazásokat egy Ön által telepített VPN-profilhoz. A VPN-kapcsolat az alkalmazás indításakor automatikusan meg fog nyílni. Csak azok a VPN-profilok tehetők elérhetővé, amelyek **Alkalmazásonkénti VPN** profilbeállítása engedélyezve van.
 További információ a VPN-profilok konfigurálásáról, beleértve a profilok alkalmazásokhoz való társításának támogatását: [Segítség a felhasználóknak a munkájukhoz való csatlakozásban VPN-profilok használatával a Microsoft Intune-nal](vpn-connections-in-microsoft-intune.md).

## Példa

Ebben a példában az alkalmazást iOS-eszközök számára **elérhetőként** telepítette.
Az alkalmazást a felhasználók a vállalati portálról telepíthetik eszközeiken. Az ezen a képernyőfelvételen látható Bing iOS-alkalmazást például a **Külső hivatkozás** telepítési típus, egy egyéni ikon és a **Megjelenítés kiemelt alkalmazásként és kiemelés a vállalati portálon** beállítás megadásával tették elérhetővé telepítésre.  
![iOS-eszközön elérhető alkalmazás](./media/available-install-on-iOS.png)

Ha az alkalmazást iOS-eszközök számára **Kötelező**-ként telepítette, a felhasználó értesítést kap arról, hogy egy alkalmazás készen áll a telepítésre. Az ezen a képernyőfelvételen látható Work Folders iOS-alkalmazást például a **Felügyelt iOS-alkalmazás az App Store-ból** telepítési típus használatával tették elérhetővé telepítésre.  
![iOS-eszközök számára kötelező alkalmazás](./media/iOS-Required-install.PNG)

## További lépések

Miután telepített egy alkalmazást, érdemes figyelnie az előrehaladását. További információ: [Alkalmazások figyelése a Microsoft Intune-ban](monitor-apps-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


