---
title: "Az eszközhöz hiányzik egy tanúsítvány | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: d6fcfac7c8bd469f5163ec9b4017ae8c3d486428
ms.openlocfilehash: 88770ba06718a767f8229e1b5aa4d543c87bc852
ms.lasthandoff: 01/05/2017

---

# <a name="your-android-device-is-missing-a-certificate-required-by-your-it-admin"></a>Az androidos eszközhöz hiányzik egy, a rendszergazda által kért tanúsítvány

Ha az eszköz nincs regisztrálva az Intune-ban, és hiányzik róla egy, a rendszergazda által kért tanúsítvány, nem fog tudni bejelentkezni a Céges portál alkalmazásba. Amikor megpróbál bejelentkezni, a következő üzenet jelenik meg:

![képernyőfelvétel-hibaüzenet-hiányzó-tanúsítványról](./media/andr-cert_install-1-cert_missing.png)

A probléma megoldásához és a szükséges tanúsítvány beszerzéséhez hajtsa végre a következő két fő lépést:

- Azonosítsa a hiányzó tanúsítványt azáltal, hogy megtekinti egy vállalati vagy iskolai számítógépen.
- Használja az eszközt a hiányzó tanúsítvány letöltéséhez az internetről.

## <a name="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc"></a>Azonosítsa a hiányzó tanúsítványt azáltal, hogy megtekinti egy vállalati vagy iskolai számítógépen

1. Nyissa meg egy számítógépen az Internet Explorert. Ha nincs erre a célra használható számítógépe, forduljon a rendszergazdához. A rendszergazda elérhetőségét a [Céges portál webhelyén](http://portal.manage.microsoft.com) találja.

2. Lépjen a [Céges portál webhelyére](http://portal.manage.microsoft.com), és jelentkezzen be a munkahelyi vagy iskolai fiókjával.

3. A böngésző címsorának jobb szélén válassza az alábbi képernyőképen látható, lakat alakú szimbólumot.

    ![képernyőfelvétel-internet-explorer-címsor-lakat-szimbólum](./media/andr-missing-cert-ie-padlock-symbol.png)

    Ha nem látja a lakat alakú szimbólumot, ne lépjen tovább, hanem forduljon a rendszergazdához. A lakat azt jelenti, hogy biztonságosan jelentkezett be, ezért ha nem látja a szimbólumot, nem javasolt a továbblépés.

4. Válassza a **Tanúsítványok megtekintése** elemet.

    ![képernyőfelvétel-internet-explorer-tanúsítvány-megtekeintése-gomb-webhely-azonosítási-párbeszédpanelén](./media/andr-missg-cert-ie-view-cert-button.png)

5. A **Tanúsítvány** párbeszédpanelen válassza a **Tanúsítványlánc** elemet, majd azonosítsa a tanúsítványt, amelyet le kell töltenie az internetről. A szükséges tanúsítvány neve ugyanazon a helyen lesz, mint az előbbi képernyőfelvételen kiemelt tanúsítványé.

## <a name="download-and-install-the-missing-certificate-on-your-android-mobile-device"></a>Töltse le és telepítse a hiányzó tanúsítványt Android-mobileszközére

1. Ha keresőmotort, például Binget vagy Google-t használ, keressen rá az előző szakaszban azonosított hiányzó tanúsítvány nevére. A tanúsítvány különböző „kiterjesztésekkel” rendelkezhet, például „.crt”, „.pem” stb.

2. Töltse le a főtanúsítványt a webhelyről.

3. Miután a tanúsítvány letöltése befejeződött, húzza le az értesítéseket fentről, és koppintson a tanúsítvány nevére az értesítések listájában.

4. Az alábbi képernyőképen látható **Name the Certificate** (A tanúsítvány elnevezése) párbeszédpanelben fogadja el az alapértelmezett tanúsítványnevet.

5. Győződjön meg arról, hogy **Credential Use** (Hitelesítő adatok használata) beállítás értéke **Used for VPN and apps** (VPN-hez és az alkalmazásokhoz használt), és koppintson az **OK** gombra.

    ![képernyőkép-tanúsítványnevet-mutató-képernyő](./media/andr-missing-cert-cert-name.png)

6. Zárja be a Céges portál alkalmazást.

7. Nyissa ismét meg a Céges portál alkalmazást. Ekkor már be kell, hogy tudjon jelentkezni a Céges portál alkalmazásba. Ha segítségre van szüksége, lépjen kapcsolatba a rendszergazdával.

Ha ugyanazt a „Hiányzó tanúsítvány” üzenetet látja, mint amelyik fentebb is látható, és már követte a fenti lépéseket, akkor valószínűleg egy másik tanúsítvány is van, amelyet a rendszergazda segítségével telepíteni kell. Kérje a rendszergazda segítségét a [Céges portál webhelyen](http://portal.manage.microsoft.com) található elérhetőségeken.

