---
title: "Az alkalmazások üzembe helyezése"
description: "A témakörben található információk segítséget nyújtanak az alkalmazások Microsoft Intune-on keresztüli telepítésében."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fdabe983c4306bd7deba7cb600ff0bdb1c27e4a8
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/14/2017
---
# <a name="deploy-apps-in-microsoft-intune"></a>Alkalmazások telepítése a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A témakörben található információk segítséget nyújtanak az alkalmazások Microsoft Intune-on keresztüli telepítésében.


## <a name="deploy-an-app"></a>Alkalmazások telepítése
Az alábbi eljárással teheti elérhetővé az alkalmazást telepítésre az eszközök vagy felhasználók kiválasztott csoportja számára.

### <a name="to-deploy-an-app"></a>Alkalmazás telepítése

1. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) kattintson az **Alkalmazások** &gt; **Alkalmazások** elemre az Ön által kezelt alkalmazások listájának megtekintéséhez.

2.  Jelölje ki a telepíteni kívánt alkalmazást, majd kattintson a **Központi telepítés kezelése** elemre.

3.  Az *&lt;alkalmazásnév&gt;* párbeszédpanel **Csoportok kiválasztása** lapján adja meg, hogy mely felhasználói vagy eszközcsoportok számára kívánja telepítésre elérhetővé tenni az alkalmazást.

4.  A **Központi telepítési művelet** lapon konfigurálja az alábbiakat:

    - **Jóváhagyás** – Adja meg a következő értékek egyikét:
        - **Kötelező** (kötelező telepítés)
        - **Rendelkezésre álló** (a felhasználók igény szerint telepíthetik a vállalati portálról)
        - **Nem alkalmazható** (az alkalmazás nincs telepítve, vagy nem jelenik meg a vállalati portálon)
        - **Eltávolítás** (az alkalmazás eltávolítása a kiválasztott eszközökről)
    - **Határidő** – A kötelező telepítések esetében adja meg, hogy mikor szeretné telepíteni az alkalmazást. Válasszon az előre meghatározott értékek közül, vagy válassza az **Egyéni** lehetőséget a kívánt határidő beállításához.

5. Ha a telepítésre elérhetővé tett alkalmazás konfigurálható mobilalkalmazás-felügyeleti szabályzattal, a **Mobilalkalmazás-kezelés** lap is megjelenik. Ezen a lapon választhatja ki az alkalmazáshoz hozzárendelni kívánt mobilalkalmazás-felügyeleti szabályzatot.

    [Itt megtekintheti a mobilalkalmazás-felügyeleti szabályzatokkal kompatibilis Microsoft-alkalmazásokat.](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. Ha a telepítésre elérhetővé tett alkalmazás kompatibilis az Intune VPN-profiljaival, a **VPN-profil** lap is megjelenik. Ezen a lapon hozzárendelheti az iOS-alkalmazásokat egy Ön által telepített VPN-profilhoz. A VPN-kapcsolat az alkalmazás indításakor automatikusan meg fog nyílni. Csak azok a VPN-profilok tehetők elérhetővé, amelyek **Alkalmazásonkénti VPN** profilbeállítása engedélyezve van.
 További információ a VPN-profilok konfigurálásáról, beleértve a profilok alkalmazásokhoz való társítását is: [ VPN-kapcsolatok a Microsoft Intune-ban](vpn-connections-in-microsoft-intune.md).

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a>Példa

Ebben a példában az alkalmazást iOS-eszközök számára **elérhetőként** telepítette.
Az alkalmazás megjelenik a felhasználók eszközein a vállalati portálon, és a felhasználók onnan telepíthetik azt.

Az ezen a képernyőfelvételen látható Bing iOS-alkalmazást például a **Külső hivatkozás** telepítési típussal tették elérhetővé telepítésre egyéni ikonnal. A **Megjelenítés kiemelt alkalmazásként és kiemelés a vállalati portálon** beállítás lett kiválasztva.  
![iOS-eszközön elérhető alkalmazás](./media/available-install-on-iOS.png)

Ha az alkalmazást iOS-eszközök számára **Kötelező**-ként telepítette, a felhasználó értesítést kap arról, hogy egy alkalmazás készen áll a telepítésre. Az ezen a képernyőfelvételen látható Work Folders iOS-alkalmazást például a **Felügyelt iOS-alkalmazás az App Store-ból** telepítési típus használatával tették elérhetővé telepítésre.  
![iOS-eszközök számára kötelező alkalmazás](./media/iOS-Required-install.PNG)

## <a name="next-steps"></a>További lépések

Miután telepít egy alkalmazást, érdemes figyelnie a telepítés előrehaladását. További információ: [Alkalmazások figyelése a Microsoft Intune-ban](monitor-apps-in-microsoft-intune.md).
