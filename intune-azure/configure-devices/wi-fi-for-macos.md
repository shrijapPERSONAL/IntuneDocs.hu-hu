---
title: "Az Intune Wi-Fi-beállításai macOS-eszközökhöz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató a Wi-Fi-kapcsolatok macOS-eszközökön való konfiguráláshoz használható Intune-beállításokhoz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 322a38d5-21f5-48ee-bc59-0a4f9da78d38
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac907e4cb63e4175dafc4c50239d3e0cbe581ad9
ms.openlocfilehash: 46c567dbcbfb84d4e0f8e3c3e8567cc6498befcf


---

# <a name="intune-wi-fi-settings-for-macos-devices-in-intune-azure-preview"></a>Az Intune Wi-Fi-beállításai macOS-eszközökhöz az Intune az Azure-on – előzetesben

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Wi-Fi-beállítások alapszintű és vállalati profilok esetén

- **Hálózat neve** – Nevezze el a Wi-Fi-kapcsolatot. Ez az a név, amelyet a felhasználók látni fognak, amikor a rendelkezésre álló kapcsolatok listáját böngészik az eszközeiken.
- **SSID** – Szolgáltatáskészlet-azonosító rövidítése. Ez a valódi neve annak a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakozni fognak. A felhasználók azonban csak a fentebb létrehozott hálózatnevet látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás** – Az eszköz automatikusan csatlakozik, ha a hálózat hatókörében van.
- **Rejtett hálózat** – A hálózat nem jelenik meg a rendelkezésre álló hálózatok listájában az eszközön.
- **Proxybeállítások** – A következő lehetőségek közül választhat:
    - **Nincs** – Semmilyen proxybeállítás nem lesz konfigurálva.
    - **Manuális** – Adja meg a **proxykiszolgáló címét** (IP-címként) és a hozzá tartozó **portszámot**.
    - **Automatikus** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).

## <a name="wi-fi-settings-for-basic-profiles-only"></a>Wi-Fi-beállítások csak alapszintű profilok esetén

- **Biztonság típusa** – Válassza ki a Wi-Fi-hálózat hitelesítéséhez használt biztonsági protokollt:
    - **Nyitott (nincs hitelesítés)** – Csak akkor használja ezt a lehetőséget, ha a hálózat nem védett.
    - **WPA/WPA2 – személyes**
    - **Adattitkosítás**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Wi-Fi-beállítások csak vállalati profilok esetén

- **EAP típusa** – Válassza ki az EAP protokoll biztonságos vezeték nélküli kapcsolatok hitelesítéséhez használni kívánt típusát:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>További lehetőségek az EAP típusának kiválasztásakor


|Beállítás neve|További információ|A következő esetekben használja|
|--------------|-------------|----------|
|**Védett hozzáférési hitelesítő adatok (PAC) beállításai**|Akkor válassza ezt a lehetőséget, ha az ügyfél és a hitelesítési kiszolgáló között a védett hozzáférési hitelesítő adatok használatával hitelesített csatornát szeretne létrehozni. Az alábbiak közül válasszon egyet:<br>- **PAC használata** – Ha van, akkor a rendszer egy már létező PAC-fájlt használ.<br>- **PAC használata és kiosztása** – A PAC-fájl kiosztása az eszközöknek.<br>- **PAC kiosztása és használata névtelenül** – A PAC-fájl kiosztása az eszközöknek a kiszolgáló hitelesítése nélkül.|Ha az EAP-típus **EAP-FAST**|

#### <a name="server-trust"></a>Kiszolgáló megbízhatósága


|Beállítás neve|További információ|A következő esetekben használja|
|--------------|-------------|----------|
|**Tanúsítványkiszolgálók neve**|Adjon meg egy vagy több, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a végfelhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.|Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**.|
|**Főtanúsítvány kiszolgálóhitelesítéshez**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt. |Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**|
|**Identitásadatok védelme (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **PEAP**|


#### <a name="client-authentication"></a>Ügyfél-hitelesítés


|Beállítás neve|További információ|A következő esetekben használja|
|--------------|-------------|----------|
|**Ügyfél-hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítvány)**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt SCEP- vagy PKCS-tanúsítványprofilt.|Ha az EAP-típus **EAP-TLS**|
|**Hitelesítési módszer**|Válassza ki a kapcsolat hitelesítési módszerét:<br>- **Tanúsítványok** ha az SCEP-t vagy PKCS-t szeretné kiválasztani ügyféltanúsítványként, amely a kiszolgálónak benyújtott identitástanúsítvány.<br><br>- **Felhasználónév és jelszó**, ha más hitelesítési módszert szeretne megadni. <br><br>Ha kiválasztotta a **Felhasználónevet és jelszót**, konfigurálja:<br><br>-  **Nem EAP-módszer (belső identitás)**, majd válassza ki, hogyan fogja hitelesíteni a kapcsolatot:<br>- **Nincs**<br>- **Titkosítatlan jelszó (PAP)**<br>- **Challenge Handshake Authentication Protocol (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP 2-es verzió (MS-CHAP v2)**<br>Az elérhető lehetőségek a választott EAP-típustól függnek.<br><br>**és**<br><br>- **Identitásadatok védelme (külső identitás)** – Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **EAP-TTLS** vagy **PEAP**|



<!--HONumber=Feb17_HO1-->


