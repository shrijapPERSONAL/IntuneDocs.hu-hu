---
title: Wi-Fi-kapcsolatok | Microsoft Docs
description: "A Wi-Fi profilok használatával segítséget nyújthat a felhasználóknak a Wi-Fi hálózatokhoz való csatlakozáshoz."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 65fe17c42921d2c53153dca386ea40b9dea47d04
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="configure-devices-to-connect-to-your-corporate-wi-fi-networks"></a>Az eszközök konfigurálása a vállalati Wi-Fi hálózatokhoz való csatlakozáshoz

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune Wi-Fi profiljaival vezeték nélküli hálózati beállításokat adhat meg a szervezet felhasználói és eszközei számára. Wi-Fi-profil központi telepítése esetén a felhasználók anélkül csatlakozhatnak a vállalati Wi-Fi-hálózathoz, hogy azt maguknak kellene konfigurálniuk.

Tegyük fel például, hogy egy új, **Contoso Wi-Fi** nevű vezeték nélküli hálózatot helyezett üzembe, és szeretné beállítani, hogy az összes iOS-eszköz kapcsolódjon ehhez a hálózathoz. Ennek folyamata a következő:

![A Wi-Fi profillal kapcsolatos eljárás összefoglalása](..\media\wi-fi-process-diagram.png)

1.   Hozza létre a **Contoso Wi-Fi** vezeték nélküli hálózathoz való csatlakozáshoz szükséges beállításokat tartalmazó Wi-Fi-profilt.

2.   Telepítse a profilt az iOS-eszközzel rendelkező felhasználók csoportjában.

3.   A felhasználók megtalálják az új **Contoso Wi-Fi** hálózatot a vezeték nélküli hálózatok között, és könnyedén csatlakoznak hozzá.


## <a name="create-a-wi-fi-profile"></a>Wi-Fi profil létrehozása

A Wi-Fi-profilok a következő platformokon telepíthetők:

-   Android 4.0 és újabb verziók

-    Android for Work   

-   iOS 8.0 és újabb verziók

-   Mac OS X 10.9 és újabb verziók

A Windows 8.1 vagy a Windows 10 operációs rendszer asztali vagy mobil verzióját futtató eszközökre importálhatja az előzőleg fájlba exportált Wi-Fi konfigurációs profilt. További részletek: [Windows rendszerű eszközökhöz készült Wi-Fi konfigurációs profil exportálása és importálása](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Házirend** &gt; **Házirend hozzáadása** elemet.

2.  Válassza ki a következő szabályzattípusok egyikét, majd kattintson a **Házirend létrehozása**lehetőségre:

    -   Wi-Fi profil (Android 4 és újabb)

    -   Wi-Fi profil (Android for Work)

    -   Wi-Fi profil (iOS 8.0 és újabb verziók)

    -   Wi-Fi-profil (Mac OS X 10.9 és újabb verziók)


Ehhez a házirendtípushoz nincsenek ajánlott beállítások, Egyéni házirendet kell létrehoznia.

3.  Adja meg a profil nevét és leírását.

4. Adja meg a **Hálózati kapcsolatok** beállítás értékeit.
 - **SSID (Szolgáltatáskészlet-azonosító)**: Akkor válassza ezt a lehetőséget, ha azt szeretné, hogy a felhasználók a hálózat nevét lássák, ne az SSID-t.
 - **Kapcsolódás akkor is, ha a hálózat nem teszi közzé a nevét (SSID)**: Ha azt szeretné, hogy az eszközök akkor is csatlakozhassanak a hálózathoz, ha az nem látható a hálózatok listájában (mert rejtett, és nem teszi közzé a nevét), jelölje be ezt a beállítást.

5. Konfigurálja a kijelölt platform **Biztonsági beállításait** . A rendelkezésre álló beállítások a választott biztonsági típusoktól függnek. A [Biztonsági beállítások](#security-settings) című rész ismerteti őket

6. Konfigurálja a **proxybeállításokat** (csak iOS és MAC OS X).

    |Beállítás neve|További információ|Mikor kell használni|
    |----------------|-------------------|-------------|
    |**A Wi-Fi kapcsolat proxybeállításai**|Válassza ki a proxybeállítások típusát:<br /><br />-   **Nincs** (alapértelmezett)<br />-   **Manuális** – Manuálisan adja meg a proxykiszolgáló URL-címét és portszámát.<br />-   **Automatikus** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja.|Mindig|
    |**Proxykiszolgáló címe** és **Portszám**|Adja meg a proxykiszolgáló URL-címét és portszámát.|Ha **A Wi-Fi-kapcsolat proxybeállításai** beállítás értéke **Kézi**.|
    |**Proxykiszolgáló URL-címe**|Adja meg a proxykiszolgáló beállításait tartalmazó fájl URL-címét.|Ha **A Wi-Fi-kapcsolat proxybeállításai** beállítás értéke **Automatikus**|

7.  A Wi-Fi profil mentése

Az új szabályzat a **Házirend** munkaterület **Konfigurációs szabályzatok** csomópontjában jelenik meg. A profil hatályba léptetésével kapcsolatos tudnivalókat lásd: **További lépések**.

## <a name="export-or-import-a-wi-fi-configuration-profile-for-windows-devices"></a>Windows rendszerű eszközökhöz készült Wi-Fi konfigurációs profil exportálása és importálása

A Windows 8.1 vagy a Windows 10 operációs rendszer asztali vagy mobil verzióját futtató eszközökre importálhatja az előzőleg fájlba exportált Wi-Fi konfigurációs profilt.

### <a name="export-a-wi-fi-profile"></a>Wi-Fi-profil exportálása
A Windows rendszerben a **netsh wlan** segédprogrammal az Intune által is olvasható XML-fájlba exportálhat egy meglévő Wi-Fi-profilt. A szükséges Wi-Fi-profilt már tartalmazó Windows-számítógépeken a következő lépéseket kell elvégeznie:

1.  Hozzon létre egy helyi mappát az exportált Wi-Fi-profiloknak. Hozza létre például a **c:\WiFi** nevű mappát.

2.  Nyisson meg rendszergazdaként egy parancssort.

3.  Futtassa a `netsh wlan show profiles` parancsot, és jegyezze fel az exportálni kívánt profil nevét.  Ebben a példában a profil neve: **WiFiName**.

4.  Futtassa ezt a parancsot: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Ezzel létrehozza a **Wi-Fi-WiFiName.xml** nevű Wi-Fi-profilfájlt a célmappában.

### <a name="import-a-wi-fi-profile"></a>Wi-Fi-profil importálása
A **Windows Wi-Fi házirend importálása** lehetőséggel importáljon egy Wi-FI beállításkészletet, amelyet ezután hozzárendelhet a megfelelő felhasználói vagy eszközcsoportokhoz.


1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) kattintson a **Házirend** &gt; **Házirend hozzáadása** elemre.

2.  Konfiguráljon egy **Windows** &gt; **Wi-Fi-importálás (Windows 8.1 és újabb verziók)** típusú házirendet.

    Ez a szabályzat a Windows 8.1 és a Windows 10 operációs rendszer asztali és mobil verzióját futtató eszközökre alkalmazható.

    Csak *egyéni* Windows Wi-Fi importált házirendet hozhat létre és helyezhet üzembe. Ajánlott beállítások nem állnak rendelkezésre.

3.  Adja meg az alábbi általános értékeket a Windows Wi-Fi importált házirendhez:

    |Beállítás neve|További információ|
    |----------------|--------------------|
    |**Név**|Adjon meg egy egyedi nevet a Wi-Fi profilhoz, hogy a profil könnyebben azonosítható legyen az Intune konzolon.|
    |**Leírás**|Adja meg a Wi-Fi-profil rövid leírását és egyéb kapcsolódó információkat, amelyek alapján a profil könnyen megtalálható lesz.|

4.  Az **Egyéni Wi-Fi profil** fejléc alatt adja meg a következő értékeket:

    |Beállítás neve|További információ|
    |----------------|--------------------|
    |**Konfigurációs profil fájlja**|Kattintson az **Importálás** elemre, és válassza ki azt az XML-fájlt, amely az Intune-ba importálni kívánt Wi-Fi-profilbeállításokat tartalmazza.|
    |**Egyéni konfigurációs profil neve (felhasználók láthatják)**|Válassza ki, milyen néven jelenjen meg a Wi-Fi konfigurációs profil a felhasználók eszközén.|
    |**Konfigurációs profil adatai**|Válassza ki, hogyan jelenjen meg a kiválasztott konfigurációs profil XML-kódja.|

5.  Ha elkészült, válassza a **Házirend mentése** elemet.

6.  Az új szabályzat a **Házirend** munkaterület **Konfigurációs szabályzatok** csomópontjában jelenik meg.

## <a name="deploy-the-profile"></a>A profil telepítése

A profil a szabályzatok egy fajtája, ezért a **Házirend** munkaterületen telepítheti.

1.  A **Házirend** munkaterületen válassza ki a telepíteni kívánt házirendet, majd kattintson a **Központi telepítés kezelése** elemre.

2.  A **Telepítések kezelése** párbeszédpanelen:

    -   **A szabályzat telepítése**: Válasszon ki egy vagy több olyan csoportot, amelynek telepíteni szeretné a szabályzatot. Kattintson a  **Hozzáadás** &gt; **OK** gombra.

    -   **A párbeszédpanel bezárása telepítés nélkül**: Kattintson a **Mégse** gombra.


A **Házirend** munkaterület **Áttekintés** lapján láthatók a szabályzattal kapcsolatos, beavatkozást igénylő problémák. Ezen felül egy állapotösszegzés megjelenik az Irányítópult munkaterületen is.

## <a name="security-settings"></a>Biztonsági beállítások
Az alábbi táblázatok tartalmazzák az Android-, iOS- és Mac OS X-rendszerek esetében elérhető biztonsági beállítások részleteit.

### <a name="security-settings-for-android-devices"></a>Biztonsági beállítások Android rendszerű eszközökhöz

  |Beállítás neve|További információ|Mikor kell használni|
|----------------|--------------------|-------------|
|**Biztonság típusa**|Válassza ki a vezeték nélküli hálózat biztonsági protokollját:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Nincs hitelesítés (nyílt)**, ha a hálózat nem biztonságos.|Mindig|
|**EAP-típus**|Válassza ki, hogy az EAP protokoll melyik típusát kívánja használni a biztonságos vezeték nélküli kapcsolatok hitelesítésére:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Ha a **WPA-Enterprise/WPA2-Enterprise** biztonsági típust választotta.|
|**Kiszolgálói érvényesítéshez használandó főtanúsítványok**|Válassza a **Kiválasztás** lehetőséget, majd jelölje ki a kapcsolat hitelesítéséhez használt megbízható főtanúsítvány-profilt. A megbízható főtanúsítvány-profil létrehozásáról [Az erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md) című témakörben találhat további tájékoztatást.|Ha bármelyik **EAP-típust** választotta.|
|**Hitelesítési módszer**|Válassza ki a kapcsolathoz használt hitelesítési módszert:<br /><br />-   **Tanúsítványok** , ha ügyféltanúsítványt kíván megadni<br />-   **Felhasználónév és jelszó**, ha más hitelesítési módszert szeretne megadni|Ha az **EAP-típus** **PEAP** vagy **EAP-TTLS**.|
|**Hitelesítéshez használandó nem EAP-módszer (belső identitás)**|Válassza ki, hogy miként hitelesíti a kapcsolatot:<br /><br />-   **Nincs**<br />-   **Titkosítatlan jelszó (PAP)**<br />-   **Challenge Handshake Authentication Protocol (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP 2-es verzió (MS-CHAP v2)**<br /><br />Az elérhető lehetőségek a választott EAP-típustól függenek.|Ha a **Hitelesítési módszer** a **Felhasználónév és jelszó**.|
|**Identitásadatok védelmének engedélyezése (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először ezt a névtelen identitást küldi el. Azt követően egy biztonságos alagúton küldi el a valódi azonosítót.|Ha az **EAP-típus** **PEAP** vagy **EAP-TTLS**.|
|**Válasszon ki egy, az ügyfél-hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítványt)**|Válassza a **Kiválasztás** lehetőséget, majd jelölje ki a kapcsolat hitelesítéséhez SCEP-tanúsítványprofilt. A megbízható SCEP-tanúsítványprofil létrehozásáról [Az erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md) című témakörben találhat további tájékoztatást.|Ha a biztonsági típus **WPA-Enterprise/WPA2-Enterprise**, és az egyik **EAP-típus** van megadva.|

### <a name="security-settings-for-ios-and-mac-os-x-devices"></a>Biztonsági beállítások iOS és Mac OS X rendszerű eszközökhöz

  |Beállítás neve|További információ|Mikor kell használni|
|----------------|--------------------|-------------|
|**Biztonság típusa**|Válassza ki a vezeték nélküli hálózat biztonsági protokollját:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Nincs hitelesítés (nyílt)**, ha a hálózat nem biztonságos.|Mindig|
|**EAP-típus**|Válassza ki, hogy az EAP protokoll melyik típusát kívánja használni a biztonságos vezeték nélküli kapcsolatok hitelesítésére:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Ha a **WPA-Enterprise/WPA2-Enterprise** biztonsági típust választotta.|
|**Megbízható kiszolgálók tanúsítványainak nevei**|Válassza ki a kapcsolat hitelesítéséhez használt megbízható főtanúsítvány-profilt. A megbízható főtanúsítvány-profil létrehozásáról [Az erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md) című témakörben találhat további tájékoztatást.|Ha az **EAP-TLS**, **PEAP**, **EAP-TTLS** vagy az **EAP-FAST** EAP-típusok valamelyikét választotta.|
|**PAC használata**|Akkor válassza ezt a lehetőséget, ha az ügyfél és a hitelesítési kiszolgáló között a védett hozzáférési hitelesítő adatok használatával hitelesített csatornát szeretne létrehozni. Ha van, akkor a rendszer egy már létező PAC-fájlt használ.|Ha az **EAP-típus** **EAP-FAST**.|
|**PAC kiépítése**|Beállítja a PAC-fájlt az eszközökön.<br /><br />Használata esetén a **PAC kiosztása névtelenül** lehetőséget is választhatja, ha a PAC-fájlt a kiszolgáló hitelesítése nélkül szeretné beállítani.|Ha a **Védett hozzáférési hitelesítő adatok használata (PAC)** beállítás van megadva.|
|**Hitelesítési módszer**|Válassza ki a kapcsolathoz használt hitelesítési módszert:<br /><br /><ul><li>**Tanúsítványok** , ha meg kell adni az ügyféltanúsítványt</li><li>**Felhasználónév és jelszó**, ha meg kell adni a következő nem EAP-alapú módszerek egyikét a hitelesítéshez (más néven Belső identitás):<br /><br /><ul><li>**Nincsenek**</li><li>**Titkosítatlan jelszó (PAP)**</li><li>**Challenge Handshake Authentication Protocol (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP 2-es verzió (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Ha az **EAP-típus** **PEAP** vagy **EAP-TTLS**.|
|**Válasszon ki egy, az ügyfél-hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítványt)**|Válassza ki a kapcsolat hitelesítéséhez használt SCEP-tanúsítványprofilt. A megbízható SCEP-tanúsítványprofil létrehozásáról [Az erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md) című témakörben találhat további tájékoztatást.|Ha a biztonsági típus **WPA-Enterprise/WPA2-Enterprise**, és az **EAP-típus** **EAP-TLS**, **PEAP** vagy **EAP-TTLS**.|
|**Identitásadatok védelmének engedélyezése (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet.<br /><br />A hitelesítés során a rendszer először ezt a névtelen identitást küldi el. Azt követően egy biztonságos alagúton küldi el a valódi azonosítót.|Ha az **EAP-típus** **PEAP**, **EAP-TTLS** vagy **EAP-FAST**.|


### <a name="see-also"></a>További információ
A következő cikkből megtudhatja, hogyan hozhat létre Wi-Fi-profilt egy előmegosztott kulccsal: [Wi-Fi-profil létrehozása előmegosztott kulccsal](pre-shared-key-wi-fi-profile.md).

