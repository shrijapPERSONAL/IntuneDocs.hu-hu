---
title: "Wi-Fi-beállítások az Intune-ban Android-eszközök esetén"
titleSuffix: Intune on Azure
description: "Útmutató androidos és Android for Work-eszközök Wi-Fi-kapcsolati beállításaihoz az Intune-ban.”"
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e1c64730dc8bb91a0fe5e7936ed963d67be1feb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="wi-fi-settings-for-android-and-android-for-work-devices-in-microsoft-intune"></a>Wi-Fi-beállítások Android- és Android for Work-eszközökhöz a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Alapszintű és vállalati profilokban használható Wi-Fi-beállítások

Az alábbi Wi-Fi-beállítások Android- és Android for Work-eszközökhöz egyaránt elérhetőek:

- **Hálózatnév** – Adja meg a Wi-Fi-kapcsolat nevét. Ez az a név fog megjelenni a felhasználók számára, amikor a rendelkezésre álló kapcsolatok listáját böngészik az eszközeiken.
- **SSID** – A szolgáltatáskészlet-azonosító rövidítése. Ez a valódi neve a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakozni fognak. A felhasználók azonban csak a fentebb létrehozott hálózatnevet látják, amikor kiválasztják a kapcsolatot.
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
|**Tanúsítványkiszolgálók neve**|Adjon meg egy vagy több, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a végfelhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.|Ha az EAP-típus **EAP-TLS** vagy **EAP-TTLS**|
|**Főtanúsítvány kiszolgálóhitelesítéshez**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt. |Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**|
|**Identitásadatok védelme (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **PEAP**|


#### <a name="client-authentication"></a>Ügyfél-hitelesítés


|Beállítás neve|További információ|A következő esetekben használja|
|----------|--------------|----------|
|**Ügyfél-hitelesítéshez használandó ügyféltanúsítvány (identitástanúsítvány)**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt SCEP- vagy PKCS-tanúsítványprofilt.|Ha az EAP-típus **EAP-TLS**|
|**Hitelesítési módszer**|Válassza ki a kapcsolat hitelesítési módszerét:<br>- **Tanúsítványok**, ha a kiszolgálónak az identitás tanúsítványaként benyújtott SCEP- vagy PKCS-ügyféltanúsítványt szeretné kiválasztani.<br><br>- **Felhasználónév és jelszó** – ha más hitelesítési módszert szeretne megadni. <br><br>Ha a **Felhasználónév és jelszó** lehetőséget választotta, konfigurálja a következőket:<br><br>-  **Nem EAP-módszer (belső identitás)**, majd válassza ki, hogyan fogja hitelesíteni a kapcsolatot:<br>- **Nincs**<br>- **Titkosítatlan jelszó (PAP)**<br>- **Challenge Handshake Authentication Protocol (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP 2-es verzió (MS-CHAP v2)**<br>Az elérhető lehetőségek a választott EAP-típustól függnek.<br><br>**és**<br><br>- **Identitásadatok védelme (külső identitás)** – Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **EAP-TTLS** vagy **PEAP**|