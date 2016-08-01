---
title: Wi-Fi-kapcsolatok | Microsoft Intune
description: "A VPN-profilok beállításával a szervezetében lévő felhasználókra és eszközökre alkalmazhatja a VPN-beállításokat."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 3a59d69be920012b3faa6ea5420b4a96d9c63f46


---

# Wi-Fi-kapcsolatok a Microsoft Intune-ban
A Microsoft Intune Wi-Fi profiljaival vezeték nélküli hálózati beállításokat adhat meg a szervezet felhasználói és eszközei számára. A beállításokkal a felhasználók egyszerűbben csatlakozhatnak a vezeték nélküli hálózatokhoz.

Tegyük fel például, hogy egy új, **Contoso Wi-Fi** nevű vezeték nélküli hálózatot helyezett üzembe, és szeretné beállítani, hogy az összes iOS-eszköz kapcsolódjon ehhez a hálózathoz. Ennek folyamata a következő:

1.   Hozza létre a **Contoso Wi-Fi** vezeték nélküli hálózathoz való csatlakozás beállításait tartalmazó Wi-Fi profilt.

2. Telepítse a profilt az iOS-eszközzel rendelkező felhasználók csoportjában.

3.   A felhasználók megtalálják az új **Contoso Wi-Fi** hálózatot a vezeték nélküli hálózatok között, és könnyedén csatlakoznak hozzá.

A Wi-Fi-profilok a következő platformokon telepíthetők:

-   Android 4.0 és újabb verziók

-   iOS 7.1-es és újabb verziók

-   Mac OS X 10.9 és újabb verziók

A Windows 8.1, vagy a Windows 10 asztali vagy mobilverzióját futtató eszközökre importálhatja az előzőleg fájlba exportált Wi-Fi konfigurációs profilt. Részletekért tekintse meg a jelen témakör **Wi-Fi-profil importálása** című szakaszát.

## Wi-Fi profil létrehozása

1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) kattintson a **Házirend** &gt; **Házirend hozzáadása** elemre.

2.  Válassza ki a következő házirendtípusok egyikét, majd kattintson a **Házirend létrehozása**lehetőségre:

    -   **Wi-Fi profil (Android 4 és újabb)**

    -   **Wi-Fi profil (iOS 7.1 és újabb)**

    -   **Wi-Fi-profil (Mac OS X 10.9 és újabb verziók)**

    Ehhez a házirendtípushoz nincsenek ajánlott beállítások, Egyéni házirendet kell létrehoznia.

3.  Adja meg a profil nevét és leírását.

4. Adja meg a **Hálózati kapcsolatok** beállítás értékeit:

  |Beállítás|További információ|
|-----------|--------------------|
|**Hálózati név**|Adjon meg egy leíró nevet a vezeték nélküli hálózathoz. Ez a név fog megjelenni a felhasználó eszközén, amikor vezeték nélküli hálózatot választ.|
|**SSID (Szolgáltatáskészlet-azonosító)**|Adja meg a vezeték nélküli hálózat SSID azonosítóját, amelyhez szeretné, hogy az eszközök csatlakozzanak. Az SSID megkülönbözteti a kis-és nagybetűket, és a felhasználók számára nem jelenik meg.|
|**Automatikus kapcsolódás, ha a hálózat hatótávolságon belül van**|Ha megadja ezt beállítást, az eszközök automatikusan csatlakoznak a vezeték nélküli hálózathoz, ha az hatótávolságon belül van.|
|**Csatlakozás, ha nem látható a hálózat neve (SSID)**|Ezt a lehetőséget választva az eszközök akkor is csatlakozhatnak a hálózathoz, ha az nem látható a hálózatok listájában (mert rejtett, és nem látható a neve).|

5. Konfigurálja a kijelölt platform **Biztonsági beállításait** . A rendelkezésre álló beállítások a választott biztonsági típusoktól függnek.

  #### Android eszközök esetén

  |Beállítás neve|További információ|A következő esetekben használja:|
|----------------|--------------------|-------------|
|**Biztonság típusa**|Válassza ki a vezeték nélküli hálózat biztonsági protokollját:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Nincs hitelesítés (nyílt)**, ha a hálózat nem biztonságos.|Mindig|
|**EAP-típus**|Válassza ki az EAP protokoll biztonságos vezeték nélküli kapcsolatok hitelesítéséhez használni kívánt típusát:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Ha a **WPA-Enterprise/WPA2-Enterprise** biztonsági típust választotta.|
|**Válassza ki a kiszolgáló ellenőrzésére szolgáló főtanúsítványokat**|Kattintson a **Kiválasztás**lehetőségre, majd válassza ki a kapcsolat hitelesítéséhez használt megbízható főtanúsítvány-profilt. **Fontos:** Megbízható főtanúsítvány-profil létrehozásához lásd: [Erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md).|Bármely **EAP-típus** választása esetén.|
|**Hitelesítési módszer**|Válassza ki a kapcsolat hitelesítési módszerét:<br /><br />-   **Tanúsítványok** , ha meg kell adni az ügyféltanúsítványt<br />-   **Felhasználónév és jelszó**, ha más hitelesítési módszert szeretne megadni|Ha az **EAP-típus** **PEAP** vagy **EAP-TTLS**.|
|**Nem EAP-alapú hitelesítési módszer választása (Belső identitás)**|Válassza ki, hogy miként hitelesíti a kapcsolatot:<br /><br />-   **Nincsenek**<br />-   **Titkosítatlan jelszó (PAP)**<br />-   **Challenge Handshake Authentication Protocol (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP 2-es verzió (MS-CHAPV2)**<br /><br />Az elérhető lehetőségek a választott EAP-típustól függnek.|Ha a **Hitelesítési módszer** a **Felhasználónév és jelszó**.|
|**Identitásvédelem engedélyezése (Külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az **EAP-típus** **PEAP** vagy **EAP-TTLS**.|
|**Ügyféltanúsítvány kiválasztása ügyfél-hitelesítéshez (identitástanúsítvány)**|Kattintson a **Kiválasztás**lehetőségre, majd válassza ki a kapcsolat hitelesítéséhez használt megbízható SCEP-tanúsítványprofilt. **Fontos:** SCEP-tanúsítványprofil létrehozása: [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Erőforrások biztonságos elérése tanúsítványprofilokkal).|A biztonsági típus **WPA-Enterprise/WPA2-Enterprise**, és az egyik **EAP-típus** van megadva.|

  #### iOS- és Mac OS X-eszközök esetén

  |Beállítás neve|További információ|A következő esetekben használja:|
|----------------|--------------------|-------------|
|**Biztonság típusa**|Válassza ki a vezeték nélküli hálózat biztonsági protokollját:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Nincs hitelesítés (nyílt)**, ha a hálózat nem biztonságos.|Mindig|
|**EAP-típus**|Válassza ki az EAP protokoll biztonságos vezeték nélküli kapcsolatok hitelesítéséhez használni kívánt típusát:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Ha a **WPA-Enterprise/WPA2-Enterprise** biztonsági típust választotta.|
|**Megbízható kiszolgálótanúsítvány-nevek**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt. **Fontos:** Megbízható főtanúsítvány-profil létrehozásához lásd: [Erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md).|Ha az **EAP-TLS**, **PEAP**, **EAP-TTLS** vagy az **EAP-FAST** EAP-típusok valamelyikét választotta.|
|**Védett hozzáférési hitelesítő adatok (PAC) használata**|Akkor válassza ezt a lehetőséget, ha az ügyfél és a hitelesítési kiszolgáló között a védett hozzáférési hitelesítő adatok használatával hitelesített csatornát szeretne létrehozni. Ha van, akkor a rendszer egy már létező PAC-fájlt használ.|Ha az **EAP-típus** **EAP-FAST**.|
|**PAC kiosztása**|A PAC-fájl kiosztása az eszközöknek.<br /><br />Használatakor a **PAC kiosztása névtelenül** lehetőséget is választhatja, ha a PAC-fájlt a kiszolgáló hitelesítése nélkül szeretné kiosztani.|Ha a**Védett hozzáférési hitelesítő adatok használata (PAC)** beállítás van megadva.|
|**Hitelesítési módszer**|Válassza ki a kapcsolathoz használt hitelesítési módszert:<br /><br /><ul><li>**Tanúsítványok** , ha meg kell adni az ügyféltanúsítványt</li><li>**Felhasználónév és jelszó**, ha meg kell adni a következő nem EAP-alapú módszerek egyikét a hitelesítéshez (más néven Belső identitás):<br /><br /><ul><li>**Nincsenek**</li><li>**Titkosítatlan jelszó (PAP)**</li><li>**Challenge Handshake Authentication Protocol (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP 2-es verzió (MS-CHAPV2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Ha az **EAP-típus** **PEAP** vagy **EAP-TTLS**.|
|**Ügyféltanúsítvány kiválasztása ügyfél-hitelesítéshez (identitástanúsítvány)**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt SCEP-tanúsítványprofilt. **Fontos:** SCEP-tanúsítványprofil létrehozása: [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Erőforrások biztonságos elérése tanúsítványprofilokkal).|Ha a biztonsági típus **WPA-Enterprise/WPA2-Enterprise**, és az **EAP-típus** **EAP-TLS**, **PEAP** vagy **EAP-TTLS**.|
|**Identitásvédelem engedélyezése (Külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet.<br /><br />A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az **EAP-típus** **PEAP**, **EAP-TTLS** vagy **EAP-FAST**.|

6. **Proxybeállítások** konfigurálása (csak iOS és MAC OS X)

    |Beállítás neve|További információ|A következő esetekben használja:|
    |----------------|-------------------|-------------|
    |**Proxybeállítások a Wi-Fi kapcsolathoz**|Válassza ki a proxybeállítások típusát:<br /><br />-   **Nincs** (alapértelmezett)<br />-   **Kézi** – Manuálisan adja meg a proxykiszolgáló URL-címét és portszámát.<br />-   **Automatikus** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja.|Mindig|
    |**Proxykiszolgáló címe** és **Portszám**|Adja meg a proxykiszolgáló URL-címét és portszámát.|**A Wi-Fi kapcsolat proxybeállításai** beállítás értéke **Kézi**|
    |**Proxykiszolgáló URL-címe**|Adja meg a proxykiszolgáló beállításait tartalmazó fájl URL-címét.|**A Wi-Fi kapcsolat proxybeállításai** beállítás értéke **Automatikus**|

7.  A Wi-Fi profil mentése

Az új szabályzat a **Házirend** munkaterület **Konfigurációs szabályzatok** csomópontjában jelenik meg. A profil hatályba léptetésével kapcsolatos tudnivalókat lásd: **További lépések**.

## Wi-Fi konfigurációs profil exportálása importálása (csak Windows 8.1 vagy újabb verzió esetén)

### Wi-Fi-profil exportálása
A Windows rendszerben a **netsh wlan** segédprogrammal az Intune által is olvasható XML-fájlba exportálhat egy meglévő Wi-Fi profilt. A szükséges Wi-Fi profillal már rendelkező Windows-számítógépen kövesse az alábbi eljárást.

1.  Hozzon létre egy helyi mappát az exportált W-Fi-profilokhoz, például a c:\WiFi mappát

2.  Nyisson meg egy parancssort rendszergazdaként.

3.  Futtassa a `netsh wlan show profiles` parancsot, és jegyezze fel az exportálni kívánt profil nevét.  Ebben a példában a profil neve: *WiFiName*.

4.  Futtassa ezt a parancsot: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Ezzel létrehozza a „Wi-Fi-WiFiName.xml” nevű Wi-Fi-profilfájlt a célmappában.

### Wi-Fi-profil importálása
A **Windows Wi-Fi házirend importálása** lehetőséggel importáljon egy Wi-FI beállításkészletet, amelyet ezután hozzárendelhet a megfelelő felhasználói vagy eszközcsoportokhoz.


1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) kattintson a **Házirend** &gt; **Házirend hozzáadása** elemre.

2.  Konfiguráljon egy **Windows** &gt; **Wi-Fi-importálás (Windows 8.1 és újabb verziók)** típusú házirendet.

    Ez a házirend a Windows 8.1 és a Windows 10 asztali és mobil verziójára alkalmazható. 
    
    Csak *egyéni* Windows Wi-Fi importált házirendet hozhat létre és helyezhet üzembe. Ajánlott beállítások nem állnak rendelkezésre.

3.  Adja meg az alábbi általános értékeket a Windows Wi-Fi importált házirendhez:

    |Beállítás neve|További információ|
    |----------------|--------------------|
    |**Név**|Adjon meg egy egyedi nevet a Wi-Fi profilhoz, hogy a profil könnyebben azonosítható legyen az Intune konzolon.|
    |**Leírás**|Adja meg a Wi-Fi profil rövid leírását és egyéb kapcsolódó információkat, amelyek alapján a profil könnyen megtalálható lesz.|

4.  Az **Egyéni Wi-Fi profil** fejléc alatt adja meg a következő értékeket:

    |Beállítás neve|További információ|
    |----------------|--------------------|
    |**Konfigurációs profilfájl**|Az **Importálás** elemre kattintva válassza ki azt az XML-fájlt, amely az Intune-ba importálni kívánt Wi-Fi profilbeállításokat tartalmazza.|
    |**Egyéni konfigurációs profil neve (megjelenik a felhasználók számára)**|A Wi-Fi konfigurációs profil nevének megjelenítése abban a formában, ahogy a felhasználók eszközén is megjelenik majd.|
    |**Konfigurációs profil részletei**|Megjeleníti a kiválasztott konfigurációs profil XML-kódját.|

5.  Ha elkészült, kattintson a **Házirend mentése**gombra.

6.  Az új szabályzat a **Házirend** munkaterület **Konfigurációs szabályzatok** csomópontjában jelenik meg.

## A szabályzat telepítése

1.  A **Házirend** munkaterületen válassza ki a telepíteni kívánt házirendet, majd kattintson a **Központi telepítés kezelése**lehetőségre.

2.  A **Telepítések kezelése** párbeszédpanelen:

    -   **A szabályzat telepítése** – Válasszon ki egy vagy több olyan csoportot, amelynek telepíteni kívánja a szabályzatot, majd kattintson a **Hozzáadás** &gt; **OK** gombra.

    -   **A párbeszédpanel bezárása telepítés nélkül** – Kattintson a **Mégse** gombra.


A **Házirend** munkaterület **Áttekintés** lapján található állapotösszegzés és riasztások segítségével azonosíthatók a szabályzattal kapcsolatos, figyelmet igénylő problémák. Ezen felül egy állapotösszegzés megjelenik az Irányítópult munkaterületen is.

### További információ
Ismerje meg, hogyan hozhat létre Wi-Fi-profilt egy előmegosztott kulccsal: [Wi-Fi-profil létrehozása előmegosztott kulccsal](pre-shared-key-wi-fi-profile.md)



<!--HONumber=Jul16_HO3-->


