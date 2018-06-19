---
title: A Microsoft Intune Wi-Fi-beállításai macOS rendszerű eszközökhöz
titleSuffix: ''
description: Útmutató a Wi-Fi-kapcsolatok macOS-eszközökön való konfiguráláshoz használható Intune-beállításokhoz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 81bd3cb54a1490732083b52a1fe242146183eebc
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
ms.locfileid: "31834982"
---
# <a name="wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>macOS-eszközökre vonatkozó Wi-Fi-beállítások a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk bemutatja a Microsoft Intune-ban a macOS rendszerű eszközökhöz konfigurálható Wi-Fi-beállításokat.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Alapszintű és vállalati profilokban használható Wi-Fi-beállítások

- **Hálózatnév** – Adja meg a Wi-Fi-kapcsolat nevét. Ez a név jelenik meg a felhasználók számára, amikor a rendelkezésre álló kapcsolatok listáját böngészik az eszközeiken.
- **SSID** – A szolgáltatáskészlet-azonosító rövidítése. Ez a valódi neve a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált hálózatnevet látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás** – Az eszköz automatikusan csatlakozik, ha a hálózat hatókörében van.
- **Rejtett hálózat** – A hálózat nem jelenik meg a rendelkezésre álló hálózatok listájában az eszközön.
- **Proxybeállítások** – A következő lehetőségek közül választhat:
    - **Nincs** – Semmilyen proxybeállítás nincs konfigurálva.
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
|**Tanúsítványkiszolgálók neve**|Adjon meg egy vagy több, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a felhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.|Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**.|
|**Kiszolgálói érvényesítéshez használandó főtanúsítvány**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt. |Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**|
|**Identitásadatok védelme (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **PEAP**|


#### <a name="client-authentication"></a>Ügyfél-hitelesítés


|                                     Beállítás neve                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       További információ                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            A következő esetekben használja                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Ügyfél-hitelesítéshez használandó ügyféltanúsítvány (identitástanúsítvány)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Válassza ki a kapcsolat hitelesítéséhez használni kívánt SCEP- vagy PKCS-tanúsítványprofilt.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              Ha az EAP-típus <strong>EAP-TLS</strong>              |
|                        <strong>Hitelesítési módszer</strong>                        | Válassza ki a kapcsolat hitelesítési módszerét:<br>- <strong>Tanúsítványok</strong>, ha a kiszolgálónak az identitás tanúsítványaként benyújtott SCEP- vagy PKCS-ügyféltanúsítványt szeretné kiválasztani.<br><br>- <strong>Felhasználónév és jelszó</strong> – ha más hitelesítési módszert szeretne megadni. <br><br>Ha a <strong>Felhasználónév és jelszó</strong> lehetőséget választotta, konfigurálja a következőket:<br><br>-  <strong>Nem EAP-módszer (belső identitás)</strong>, majd válassza ki, hogyan hitelesíti a kapcsolatot:<br>- <strong>Nincs</strong><br>- <strong>Titkosítatlan jelszó (PAP)</strong><br>- <strong>Challenge Handshake Authentication Protocol (CHAP)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP 2-es verzió (MS-CHAP v2)</strong><br>Az elérhető lehetőségek a választott EAP-típustól függnek.<br><br><strong>és</strong><br><br>- <strong>Identitásadatok védelme (külső identitás)</strong> – Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót. | Ha az EAP-típus <strong>EAP-TTLS</strong> vagy <strong>PEAP</strong> |

