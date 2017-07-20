---
title: "Wi-Fi-beállítások az Intune-ban iOS-eszközök esetén"
titleSuffix: Intune on Azure
description: "Útmutató a Wi-Fi-kapcsolatok iOS-eszközökön való konfiguráláshoz használható Intune-beállításokhoz.”"
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89229a5e-3421-4221-a62f-fa800620cc0d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 001a65733d3565df8f4aea485c5a7488f2756a88
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>iOS-eszközökre vonatkozó Wi-Fi-beállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Alapszintű és vállalati profilokban használható Wi-Fi-beállítások

- **Hálózatnév** – Adja meg a Wi-Fi-kapcsolat nevét. Ez az a név fog megjelenni a felhasználók számára, amikor a rendelkezésre álló kapcsolatok listáját böngészik az eszközeiken.
- **SSID** – A szolgáltatáskészlet-azonosító rövidítése. Ez a valódi neve a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakozni fognak. A felhasználók azonban csak a fentebb létrehozott hálózatnevet látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás** – Az eszköz automatikusan csatlakozik, ha a hálózat hatókörében van.
- **Rejtett hálózat** – A hálózat nem jelenik meg a rendelkezésre álló hálózatok listájában az eszközön.
- **Proxybeállítások** – A következő lehetőségek közül választhat:
    - **Nincs** – Semmilyen proxybeállítás nem lesz konfigurálva.
    - **Manuális** – Adja meg a **Proxykiszolgáló címét** (IP-címként), és a hozzá társított **Portszámot**.
    - **Automatikus** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).

## <a name="wi-fi-settings-for-basic-profiles-only"></a>Csak alapszintű profilokban használható Wi-Fi-beállítások

- **Biztonság típusa** – Válassza ki a Wi-Fi-hálózat hitelesítéséhez használt biztonsági protokollt a következő lehetőségek közül:
    - **Nyitott (nincs hitelesítés)** – Csak akkor válassza ezt a lehetőséget, ha a hálózat nem védett.
    - **WPA/WPA2 – személyes**
    - **Adattitkosítás**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Csak vállalati profilokban használható Wi-Fi-beállítások

- **EAP típusa** – Válassza ki az EAP protokoll biztonságos vezeték nélküli kapcsolatok hitelesítéséhez használni kívánt típusát a következő lehetőségek közül:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>További lehetőségek az EAP típusának kiválasztásakor


|Beállítás neve|További információ|A következő esetekben használja|
|--------------|-------------|----------|
|**Védett hozzáférési hitelesítő adatok (PAC) beállításai**|Akkor válassza ezt a lehetőséget, ha az ügyfél és a hitelesítési kiszolgáló között a védett hozzáférési hitelesítő adatok használatával hitelesített csatornát szeretne létrehozni. Válassza ki az alábbi lehetőségek egyikét:<br>- **PAC használata** – Ha van, akkor a rendszer egy már létező PAC-fájlt használ.<br>- **PAC használata és kiépítése** – A PAC-fájl kiépítése az eszközökön.<br>- **PAC használata és kiépítése névtelenül** – A PAC-fájl kiépítése az eszközökön és a PAC-fájl kiépítésének ellenőrzése a kiszolgáló hitelesítése nélkül.|Ha az EAP-típus **EAP-FAST**|

#### <a name="server-trust"></a>Kiszolgáló megbízhatósága


|Beállítás neve|További információ|A következő esetekben használja|
|--------------|-------------|----------|
|**Tanúsítványkiszolgálók neve**|Adjon meg egy vagy több, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a végfelhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.|Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**.|
|**Kiszolgálói érvényesítéshez használandó főtanúsítvány**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt. |Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**|
|**Identitásadatok védelme (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **PEAP**|


#### <a name="client-authentication"></a>Ügyfél-hitelesítés


|Beállítás neve|További információ|A következő esetekben használja|
|--------------|-------------|----------|
|**Ügyfél-hitelesítéshez használandó ügyféltanúsítvány (identitástanúsítvány)**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt SCEP- vagy PKCS-tanúsítványprofilt.|Ha az EAP-típus **EAP-TLS**|
|**Hitelesítési módszer**|Válassza ki a kapcsolat hitelesítési módszerét:<br>- **Tanúsítványok**, ha a kiszolgálónak az identitás tanúsítványaként benyújtott SCEP- vagy PKCS-ügyféltanúsítványt szeretné kiválasztani.<br><br>- **Felhasználónév és jelszó** – ha más hitelesítési módszert szeretne megadni. <br><br>Ha a **Felhasználónév és jelszó** lehetőséget választotta, konfigurálja a következőket:<br><br>-  **Nem EAP-módszer (belső identitás)**, majd válassza ki, hogyan fogja hitelesíteni a kapcsolatot:<br>- **Nincs**<br>- **Titkosítatlan jelszó (PAP)**<br>- **Challenge Handshake Authentication Protocol (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP 2-es verzió (MS-CHAP v2)**<br>Az elérhető lehetőségek a választott EAP-típustól függnek.<br><br>**és**<br><br>- **Identitásadatok védelme (külső identitás)** – Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **EAP-TTLS** vagy *