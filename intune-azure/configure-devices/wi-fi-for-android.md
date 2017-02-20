---
title: "Az Intune Wi-Fi-beállításai androidos eszközökhöz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató a Wi-Fi-kapcsolatok androidos eszközökön való konfiguráláshoz használható Intune-beállításokhoz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac907e4cb63e4175dafc4c50239d3e0cbe581ad9
ms.openlocfilehash: 03227912dd8a51342c71505746f087bf6b6a4da0


---

# <a name="intune-wi-fi-settings-for-android-devices-in-intune-azure-preview"></a>Az Intune Wi-Fi-beállításai androidos eszközökhöz az Azure-beli Intune előzetesében

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Wi-Fi-beállítások alapszintű és vállalati profilok esetén

- **Hálózat neve** – Nevezze el a Wi-Fi-kapcsolatot. Ez az a név, amelyet a felhasználók látni fognak, amikor a rendelkezésre álló kapcsolatok listáját böngészik az eszközeiken.
- **SSID** – Szolgáltatáskészlet-azonosító rövidítése. Ez a valódi neve annak a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakozni fognak. A felhasználók azonban csak a fentebb létrehozott hálózatnevet látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás** – Az eszköz automatikusan csatlakozik, ha a hálózat hatókörében van.
- **Rejtett hálózat** – A hálózat nem jelenik meg a rendelkezésre álló hálózatok listájában az eszközön.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Csak vállalati profilokban használható Wi-Fi-beállítások

- **EAP típusa** – Válassza ki az EAP protokoll biztonságos vezeték nélküli kapcsolatok hitelesítéséhez használni kívánt típusát:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>További lehetőségek az EAP típusának kiválasztásakor

#### <a name="server-trust"></a>Kiszolgáló megbízhatósága



|Beállítás neve|További információ|A következő esetekben használja|
|-------------|---------------|-----------|
|**Tanúsítványkiszolgálók neve**|Adjon meg legalább egy, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a végfelhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.|Ha az EAP-típus **EAP-TLS** vagy **EAP-TTLS**|
|**Főtanúsítvány kiszolgálóhitelesítéshez**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt. |Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**|
|**Identitásadatok védelme (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **PEAP**|


#### <a name="client-authentication"></a>Ügyfél-hitelesítés


|Beállítás neve|További információ|A következő esetekben használja|
|----------|--------------|----------|
|**Ügyfél-hitelesítéshez használandó ügyféltanúsítvány (identitástanúsítvány)**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt SCEP- vagy PKCS-tanúsítványprofilt.|Ha az EAP-típus **EAP-TLS**|
|**Hitelesítési módszer**|Válassza ki a kapcsolat hitelesítési módszerét:<br>- **Tanúsítványok** – ha azt az SCEP-t vagy PKCS-t szeretné kiválasztani ügyféltanúsítványként, amely a kiszolgálónak benyújtott identitástanúsítvány.<br><br>- **Felhasználónév és jelszó** – ha más hitelesítési módszert szeretne megadni. <br><br>Ha kiválasztotta a **Felhasználónevet és jelszót**, konfigurálja a következőket:<br><br>-  **Nem EAP-módszer (belső identitás)**, majd válassza ki, hogyan fogja hitelesíteni a kapcsolatot:<br>- **Nincs**<br>- **Titkosítatlan jelszó (PAP)**<br>- **Challenge Handshake Authentication Protocol (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP 2-es verzió (MS-CHAP v2)**<br>Az elérhető lehetőségek a választott EAP-típustól függnek.<br><br>**és**<br><br>- **Identitásadatok védelme (külső identitás)** – Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **EAP-TTLS** vagy **PEAP**|



<!--HONumber=Feb17_HO1-->


