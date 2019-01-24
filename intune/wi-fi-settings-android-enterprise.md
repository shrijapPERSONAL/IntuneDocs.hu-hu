---
title: Wi-Fi-beállítások Android Enterprise és a teljes képernyős eszközökhöz – Microsoft Intune |} A Microsoft Docs
description: Wi-Fi eszközkonfigurációs profilokat hozhat létre vagy adhat hozzá az Android Enterprise és Android kioszk rendszerhez. Megtekintheti a Microsoft Intune különböző beállításait, beleértve a tanúsítványok hozzáadását, az EAP-típusok kiválasztását és a hitelesítési módszer kiválasztását. Kioszkeszközök esetén adja meg a hálózat előre megosztott kulcsát is.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: ea72cda4cb72af9028c52078e2215619bb2bef3c
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831479"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Android Enterprise és Android kioszk rendszerű eszközökre vonatkozó Wi-Fi-beállítások hozzáadása a Microsoft Intune-ban

Adott Wi-Fi-beállításokkal rendelkező profilt hozhat létre, majd ezt a profilt üzembe helyezheti az Android Enterprise- és androidos kioszkeszközökön. A Microsoft Intune számos szolgáltatást nyújt, beleértve a hálózaton való hitelesítést, az előmegosztott kulcsok használatát és egyebeket.

Ez a cikk ezeket a beállításokat ismerteti. [Az eszközök Wi-Fi használata](wi-fi-settings-configure.md) magában foglalja a Wi-Fi-szolgáltatással kapcsolatos további információk a Microsoft Intune-ban.

## <a name="before-you-begin"></a>Előkészületek

[Eszközprofil létrehozása](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only---kiosk"></a>Csak az eszköz tulajdonosa – kioszk

Válassza ezt a lehetőséget, ha Android Enterprise-eszközt használ kioszk üzemmódban.

- **Hálózati név**: Adjon meg egy nevet a Wi-Fi kapcsolat. Ez a név jelenik meg a felhasználók számára, amikor az eszközön rendelkezésre álló kapcsolatok listáját böngészik.
- **SSID**: Rövid a **szolgáltatáskészlet-azonosító**. Ez a beállítás annak a vezeték nélküli hálózatnak a valódi neve, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált **hálózatnevet** látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás**: Válasszon **engedélyezése** való automatikus csatlakozás ehhez a hálózathoz, ha hatótávolságon belül van az eszközön. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válasszon **engedélyezése** elrejtheti ezt a hálózatot az eszközön rendelkezésre álló hálózatok listájában. A rendszer ilyenkor nem továbbítja az SSID-t. Válassza a **Letiltás** lehetőséget, ha meg szeretné jeleníteni a hálózatot az eszközön elérhető hálózatok listájában.
- **Wi-Fi típusa**: Válassza ki a biztonsági protokollt, a Wi-Fi hálózathoz való hitelesítéséhez. A választható lehetőségek:

  - **Nyissa meg a (nincs hitelesítés)**: Csak akkor használja ezt a beállítást, ha a hálózat nem biztonságos.
  - **WEP-előmegosztott kulcs**: Adja meg a jelszót az **előre megosztott kulcs**. A cég hálózatának beállítása vagy konfigurálása során a rendszer egy jelszót vagy egy hálózati kulcsot is konfigurál. Adja meg ezt a jelszót vagy hálózati kulcsot a PSK értékeként.
  - **WPA-előmegosztott kulcs**: Adja meg a jelszót az **előre megosztott kulcs**. A cég hálózatának beállítása vagy konfigurálása során a rendszer egy jelszót vagy egy hálózati kulcsot is konfigurál. Adja meg ezt a jelszót vagy hálózati kulcsot a PSK értékeként.

Válassza ki **OK** a módosítások mentéséhez.

## <a name="work-profile-only"></a>Csak munkahelyi profil

### <a name="basic-settings"></a>Alapbeállítások

- **Wi-Fi típusa**: Válassza a **Basic** (Egyszerű) lehetőséget.
- **SSID**: Rövid a **szolgáltatáskészlet-azonosító**. Ez a beállítás annak a vezeték nélküli hálózatnak a valódi neve, amelyhez az eszközök csatlakoznak.
- **Automatikus csatlakozás**: Válasszon **engedélyezése** való automatikus csatlakozás ehhez a hálózathoz, ha hatótávolságon belül van az eszközön. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válasszon **engedélyezése** elrejtheti ezt a hálózatot az eszközön rendelkezésre álló hálózatok listájában. A rendszer ilyenkor nem továbbítja az SSID-t. Válassza a **Letiltás** lehetőséget, ha meg szeretné jeleníteni a hálózatot az eszközön elérhető hálózatok listájában.

## <a name="enterprise-profile"></a>Vállalati profil

- **Wi-Fi típusa**: Válasszon **vállalati**.
- **SSID**: Rövid a **szolgáltatáskészlet-azonosító**. Ez a beállítás annak a vezeték nélküli hálózatnak a valódi neve, amelyhez az eszközök csatlakoznak.
- **Automatikus csatlakozás**: Válasszon **engedélyezése** való automatikus csatlakozás ehhez a hálózathoz, ha hatótávolságon belül van az eszközön. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válasszon **engedélyezése** elrejtheti ezt a hálózatot az eszközön rendelkezésre álló hálózatok listájában. A rendszer ilyenkor nem továbbítja az SSID-t. Válassza a **Letiltás** lehetőséget, ha meg szeretné jeleníteni a hálózatot az eszközön elérhető hálózatok listájában.
- **EAP-típus**: Válassza ki az Extensible Authentication Protocol (EAP) biztonságos vezeték nélküli kapcsolatok hitelesítéséhez. A választható lehetőségek: 

  - **EAP-TLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. Az ügyfél csatlakozik a hálózathoz, ha ezt a tanúsítványt a kiszolgáló számára, és hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** - **ügyféltanúsítvány a hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítványt)**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

      Válassza ki **OK** a módosítások mentéséhez.

  - **EAP-TTLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. Az ügyfél csatlakozik a hálózathoz, ha ezt a tanúsítványt a kiszolgáló számára, és hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: A felhasználótól a felhasználónevet és jelszót a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP-módszer (belső identitás)**: Válassza ki, hogyan hitelesíti a kapcsolatot. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Titkosítatlan jelszó (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)**, vagy **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Identitásadatok védelme (külső identitás)**: Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

  - **PEAP**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. Az ügyfél csatlakozik a hálózathoz, ha ezt a tanúsítványt a kiszolgáló számára, és hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: A felhasználótól a felhasználónevet és jelszót a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP alapú hitelesítési (belső identitás) módszer**: Válassza ki, hogyan hitelesíti a kapcsolatot. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Nincs** vagy **Microsoft CHAP 2-es verzió (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Identitásadatok védelme (külső identitás)**: Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="next-steps"></a>További lépések

A profil létrejön, de egyelőre nem csinál semmit. Ezután [hozzárendeli ezt a profilt](device-profile-assign.md) és [monitorozhatja az alkalmazás állapotát.](device-profile-monitor.md).

A Wi-Fi profilok is létrehozhat [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10-es](wi-fi-settings-windows.md), és [Windows 8.1](wi-fi-settings-import-windows-8-1.md)eszközök.