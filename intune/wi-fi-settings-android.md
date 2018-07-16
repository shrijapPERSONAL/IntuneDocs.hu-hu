---
title: A Microsoft Intune Wi-Fi-beállításainak konfigurálása Android rendszerű eszközökhöz
titleSuffix: ''
description: Az Android rendszerű eszközök Intune-beli Wi-Fi-konfigurációs beállításainak ismertetése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0157815322488525a4ce7a3d6d2c90cbb8d3ff2a
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905665"
---
# <a name="configure-wi-fi-settings-in-microsoft-intune-for-devices-running-android-android-work-profiles-and-android-kiosk-devices"></a>Az Android, androidos munkahelyi profilos és kioszk módú Android rendszerű eszközök Intune-beli Wi-Fi-konfigurációs beállításainak ismertetése

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk bemutatja a Microsoft Intune-ban az Android rendszerű és androidos munkahelyi profilos eszközökhöz konfigurálható Wi-Fi-beállításokat.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Alapszintű és vállalati profilokban használható Wi-Fi-beállítások

Az alábbi Wi-Fi-beállítások Android rendszerű és androidos munkahelyi profilos eszközökhöz egyaránt elérhetőek:

- **Hálózatnév** – Adja meg a Wi-Fi-kapcsolat nevét. Ez a név jelenik meg a felhasználók számára, amikor a rendelkezésre álló kapcsolatok listáját böngészik az eszközeiken.
- **SSID** – A szolgáltatáskészlet-azonosító rövidítése. Ez a valódi neve a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált hálózatnevet látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás** – Az eszköz automatikusan csatlakozik, ha a hálózat hatókörében van.
- **Rejtett hálózat** – A hálózat nem jelenik meg a rendelkezésre álló hálózatok listájában az eszközön.

## <a name="wi-fi-settings-available-for-enterprise-kiosk-profiles"></a>A vállalati kioszk profilokhoz elérhető Wi-Fi-beállítások
- **Wi-Fi-típus**: Ezek a Wi-Fi-típusbeállítások csak akkor érhetőek el, ha a **Profiltípus** > **Csak az eszköz tulajdonosa** > **Wi-Fi** beállítást választja.
    - **Nyílt (nincs hitelesítés)**
    - **WEP-előmegosztott kulcs**: A jelszót az **Előmegosztott kulcs** területen kell megadnia.
    - **WPA-előmegosztott kulcs**: A jelszót az **Előmegosztott kulcs** területen kell megadnia

## <a name="wi-fi-settings-for-android-legacy-and-android-work-profiles-only"></a>Wi-Fi-beállítások csak az örökölt Android rendszerű és az androidos munkahelyi profilos eszközökhöz

- **EAP típusa** – Válassza ki az EAP protokoll biztonságos vezeték nélküli kapcsolatok hitelesítéséhez használni kívánt típusát a következő lehetőségek közül:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>További lehetőségek az EAP típusának kiválasztásakor

#### <a name="server-trust"></a>Kiszolgáló megbízhatósága



|Beállítás neve|További információ|A következő esetekben használja|
|-------------|---------------|-----------|
|**Tanúsítványkiszolgálók neve**|Adjon meg egy vagy több, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a felhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.|Ha az EAP-típus **EAP-TLS** vagy **EAP-TTLS**|
|**Főtanúsítvány kiszolgálóhitelesítéshez**|Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt. |Ha az EAP-típus **EAP-TLS**, **EAP-TTLS**, vagy **PEAP**|
|**Identitásadatok védelme (külső identitás)**|Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.|Ha az EAP-típus **PEAP**|


#### <a name="client-authentication"></a>Ügyfél-hitelesítés


|                                     Beállítás neve                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       További információ                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            A következő esetekben használja                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Ügyfél-hitelesítéshez használandó ügyféltanúsítvány (identitástanúsítvány)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Válassza ki a kapcsolat hitelesítéséhez használni kívánt SCEP- vagy PKCS-tanúsítványprofilt.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              Ha az EAP-típus <strong>EAP-TLS</strong>              |
|                        <strong>Hitelesítési módszer</strong>                        | Válassza ki a kapcsolat hitelesítési módszerét:<br>- <strong>Tanúsítványok</strong>, ha a kiszolgálónak az identitás tanúsítványaként benyújtott SCEP- vagy PKCS-ügyféltanúsítványt szeretné kiválasztani.<br><br>- <strong>Felhasználónév és jelszó</strong> – ha más hitelesítési módszert szeretne megadni. <br><br>Ha a <strong>Felhasználónév és jelszó</strong> lehetőséget választotta, konfigurálja a következőket:<br><br>-  <strong>Nem EAP-módszer (belső identitás)</strong>, majd válassza ki, hogyan hitelesíti a kapcsolatot:<br>- <strong>Nincs</strong><br>- <strong>Titkosítatlan jelszó (PAP)</strong><br>- <strong>Challenge Handshake Authentication Protocol (CHAP)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP 2-es verzió (MS-CHAP v2)</strong><br>Az elérhető lehetőségek a választott EAP-típustól függnek.<br><br><strong>és</strong><br><br>- <strong>Identitásadatok védelme (külső identitás)</strong> – Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót. | Ha az EAP-típus <strong>EAP-TTLS</strong> vagy <strong>PEAP</strong> |

