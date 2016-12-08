---
title: "Alkalmazásonkénti VPN Android-eszközökhöz a Pulse Secure használatával | Microsoft Intune"
description: "Az Intune által felügyelt Android-eszközökhöz alkalmazásonkénti VPN-profilt hozhat létre."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4cab83c3d1a63a0e4f16ee838443ec032bcf1532
ms.openlocfilehash: ace975b8a53e3ccd8b754019ec7f155c563339b5


---

# <a name="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices"></a>Egyéni szabályzat használata az Android-eszközök alkalmazásonkénti VPN-profiljainak létrehozásához

Az Intune által felügyelt Android 5.0-s és újabb rendszerű eszközökhöz alkalmazásonkénti VPN-profilt hozhat létre. Először hozzon létre egy olyan VPN-profit, amely a Pulse Secure vagy a Citrix kapcsolattípust használja. Ezután hozzon létre egy olyan egyéni szabályzatot, amely a VPN-profilt meghatározott alkalmazásokkal társítja. 

Miután érvénybe lépteti a szabályzatot az Android rendszerű eszközre vagy felhasználócsoportokra vonatkozóan, a felhasználóknak el kell indítaniuk a PulseSecure vagy a Citrix VPN-t. A kapcsolat ezután csak a megadott alkalmazások adatforgalma számára engedélyezi a nyitott VPN-kapcsolat használatát.

> [!NOTE]
>
> Ez a profil csak a Pulse Secure kapcsolattípust támogatja.


### <a name="step-1-create-a-vpn-profile"></a>1. lépés: VPN-profil létrehozása

1. A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Házirend** > **Házirend hozzáadása** lehetőséget.
2. Az új szabályzathoz használandó sablon kiválasztásához bontsa ki az **Android** elemet, majd válassza a **VPN-profil (Android 4 és újabb verziók)** lehetőséget.
3. A sablonban a **Kapcsolat típusa** beállításnál válassza a **Pulse Secure** vagy a **Citrix** lehetőséget.
4. Fejezze be a beállítást, és mentse a VPN-profilt. A VPN-profilokról bővebben lásd a [VPN-kapcsolatok](../deploy-use/vpn-connections-in-microsoft-intune.md) témakört.

> [!NOTE]
>
> Jegyezze fel a VPN-profil nevét a következő lépéshez. Például: AlkVpnProfil.

### <a name="step-2-create-a-custom-configuration-policy"></a>2. lépés: Egyéni konfigurációs szabályzat létrehozása

   1. Az Intune felügyeleti konzolján válassza a **Házirend** > **Házirend hozzáadása** > **Android** > **Egyéni konfiguráció** > **Házirend létrehozása** lehetőséget.
   2. Adja meg a szabályzat nevét.
   3. Az **OMA-URI** beállítások területén válassza a **Hozzáadás** elemet.
   4. Adja meg a beállítás nevét.
   5. Az **Adattípus** mezőben válassza a **Karakterlánc** lehetőséget.
   6. Az **OMA-URI** mezőbe írja be a következő karakterláncot: **./Vendor/MSFT/VPN/Profile/*Név*/PackageList**, ahol a *Név* az 1. lépésben feljegyzett VPN-profil neve. A fenti példában a karakterlánc a következő lenne: **./Vendor/MSFT/VPN/Profile/AlkVpnProfil/PackageList**.
   7.   Az **Érték** területen adja meg azoknak a csomagoknak a pontosvesszővel tagolt listáját, amelyeket a profilhoz társít. Ha például azt szeretné, hogy az Excel és a Google Chrome böngésző VPN-kapcsolatot használjon, írja be a következőt: **com.microsoft.office.excel;com.android.chrome**.

![Példa Android rendszerű, alkalmazásonkénti VPN-hez létrehozott egyéni szabályzatra](./media/android_per_app_vpn_oma_uri.png)

#### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Az alkalmazáslista Blacklist (Letiltott) vagy Whitelist (Engedélyezett) értékre állítása (nem kötelező)
  A **BLACKLIST** (LETILTOTT) érték kiválasztásával megadhatja azoknak az alkalmazásoknak a listáját, amelyek *nem* használhatják a VPN-kapcsolatot. Minden más alkalmazás VPN-kapcsolaton keresztül fog csatlakozni az internethez.
Másik megoldásként használhatja a **WHITELIST** (ENGEDÉLYEZETT) értéket, és megadhatja azon alkalmazások listáját, amelyek *használhatják* a VPN-kapcsolatot. A listán nem szereplő alkalmazások nem csatlakozhatnak az internethez a VPN-kapcsolaton keresztül.
  1.    Az **OMA-URI** beállítások területén válassza a **Hozzáadás** elemet.
  2.    Adja meg a beállítás nevét.
  3.    Az **Adattípus** mezőben válassza a **Karakterlánc** lehetőséget.
  4.    Az **OMA-URI** mezőbe írja be a következő karakterláncot: **./Vendor/MSFT/VPN/Profile/*Név*/Mode**, ahol a *Név* az 1. lépésben feljegyzett VPN-profil neve. A fenti példában a karakterlánc a következő lenne: **./Vendor/MSFT/VPN/Profile/AlkVpnProfil/Mode**.
  5.    Az **Érték** mezőbe írja be a **BLACKLIST** (LETILTOTT) vagy a **WHITELIST** (ENGEDÉLYEZETT) értéket.



### <a name="step-3-deploy-both-policies"></a>3. lépés: Mindkét szabályzat telepítése

*Mindkét* szabályzatot *azonos* Intune-csoport számára kell telepítenie.

1.  A **Szabályzat** munkaterületen válassza ki a telepíteni kívánt szabályzatot, és kattintson a **Központi telepítés kezelése** elemre.
2.  A **Telepítések kezelése** párbeszédpanelen:
    -   **A szabályzat érvénybe léptetése** – Válasszon ki egy vagy több olyan csoportot, amelyhez érvénybe szeretné léptetni a szabályzatot, majd kattintson a **Hozzáadás** > **OK** gombra.
    -   **Ha a szabályzat érvénybe léptetése nélkül kívánja bezárni a párbeszédpanelt**, kattintson a **Mégse** gombra.

A **Házirend** munkaterület **Áttekintés** lapján található állapotösszegzés és riasztások segítségével azonosíthatók a szabályzattal kapcsolatos, figyelmet igénylő problémák. Emellett egy állapotösszegzés is megjelenik az **Irányítópult** munkaterületen.



<!--HONumber=Nov16_HO2-->


