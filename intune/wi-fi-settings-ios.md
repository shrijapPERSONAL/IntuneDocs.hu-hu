---
title: Wi-Fi-beállítások konfigurálása iOS-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: Létrehozhat vagy hozzáadhat egy eszközkonfigurációs Wi-Fi-profilt az iOS-eszközökhöz. Megtekintheti a Microsoft Intune különböző beállításait, beleértve a tanúsítványok hozzáadását, az EAP-típusok kiválasztását és a hitelesítési módszer kiválasztását.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 91e69fed37f9a6171ef72d3c01e2de9a31bbcaed
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514956"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>iOS-eszközökre vonatkozó Wi-Fi-beállítások hozzáadása a Microsoft Intune-ban

Adott Wi-Fi-beállításokkal rendelkező profilt hozhat létre, majd ezt a profilt üzembe helyezheti az iOS-eszközökön. A Microsoft Intune számos szolgáltatást nyújt, beleértve a hálózaton való hitelesítést, a PKS- vagy SCEP-tanúsítványok hozzáadását és egyéb lehetőségeket.

Ezek a Wi-Fi-beállítások vannak elválasztva egymástól két kategóriára: Alapvető beállítások és a vállalati szintű beállításait.

Ez a cikk ezeket a beállításokat ismerteti.

## <a name="before-you-begin"></a>Előkészületek

[Eszközprofil létrehozása](device-profile-create.md).

## <a name="basic-profiles"></a>Alapszintű profilok

- **Wi-Fi típusa**: Válassza a **Basic** (Egyszerű) lehetőséget.
- **Hálózati név**: Adjon meg egy nevet a Wi-Fi kapcsolat. Ez a név jelenik meg a felhasználók számára, amikor az eszközön rendelkezésre álló kapcsolatok listáját böngészik.
- **SSID**: Rövid a **szolgáltatáskészlet-azonosító**. Ez a tulajdonság azon vezeték nélküli hálózat valódi neve, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált hálózatnevet látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás**: Válasszon **engedélyezése** való automatikus csatlakozás ehhez a hálózathoz, ha hatótávolságon belül van az eszközön. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válasszon **engedélyezése** , ha az SSID-t, a hálózat nem küldött. Válasszon **letiltása** az SSID-t, a hálózat e terjesztve, és látható.
- **Biztonság típusa**: Válassza ki a biztonsági protokollt, a Wi-Fi hálózathoz való hitelesítéséhez. A választható lehetőségek:

  - **Nyissa meg a (nincs hitelesítés)**: Csak akkor használja ezt a beállítást, ha a hálózat nem biztonságos.
  - **WPA/WPA2 - Personal**: Adja meg a jelszót az **előre megosztott kulcs**. A cég hálózatának beállítása vagy konfigurálása során a rendszer egy jelszót vagy egy hálózati kulcsot is konfigurál. Adja meg ezt a jelszót vagy hálózati kulcsot a PSK értékeként.
  - **Adattitkosítás**

- **Proxybeállítások**: A választható lehetőségek:
  - **Nincs**: Semmilyen proxybeállítás nincs konfigurálva.
  - **Manuális**: Adja meg a **proxykiszolgáló címe** IP-címként, és a hozzá tartozó **portszám**.
  - **Automatikus**: Egy fájl segítségével konfigurálhatja a proxykiszolgálót. Adja meg a konfigurációs fájlt tartalmazó **proxykiszolgáló URL-címét** (például: `http://proxy.contoso.com`).

## <a name="enterprise-profiles"></a>Vállalati profilok

- **Wi-Fi típusa**: Válasszon **vállalati**.
- **SSID**: Rövid a **szolgáltatáskészlet-azonosító**. Ez a tulajdonság azon vezeték nélküli hálózat valódi neve, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált hálózatnevet látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás**: Válasszon **engedélyezése** való automatikus csatlakozás ehhez a hálózathoz, ha hatótávolságon belül van az eszközön. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válasszon **engedélyezése** elrejtheti ezt a hálózatot az eszközön rendelkezésre álló hálózatok listájában. A rendszer ilyenkor nem továbbítja az SSID-t. Válassza a **Letiltás** lehetőséget, ha meg szeretné jeleníteni a hálózatot az eszközön elérhető hálózatok listájában.

- **EAP-típus**: Válassza ki az Extensible Authentication Protocol (EAP) biztonságos vezeték nélküli kapcsolatok hitelesítéséhez. A választható lehetőségek:

  - **EAP-FAST**: Adja meg a **védett hozzáférési hitelesítő adatok (PAC) beállításai**. Ez a lehetőség védett hozzáférési hitelesítő adatok használatával hoz létre egy hitelesített csatornát az ügyfél és a hitelesítési kiszolgáló között. A választható lehetőségek:
    - **Ne használja (PAC)**
    - **PAC használata**: Ha létezik egy már létező PAC-fájlt, használja azt.
    - **PAC használata és kiépítése**: Hozzon létre, és adja hozzá az eszközök a PAC-fájl.
    - **PAC használata és kiépítése névtelenül**: Hozzon létre, és adja hozzá a PAC-fájl az eszközök, a kiszolgáló hitelesítése nélkül.

  - **EAP-SIM**

  - **EAP-TLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **tanúsítvány-kiszolgálók nevei**: **Adjon hozzá** a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt egy vagy több köznapi nevet. Ha megadja ezt az információt, elkerülheti azt a dinamikus megbízhatósági ablakot, amely akkor jelenik meg a felhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.
    - **Kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** - **ügyféltanúsítvány a hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítványt)**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

      Válassza ki **OK** a módosítások mentéséhez.

  - **EAP-TTLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **tanúsítvány-kiszolgálók nevei**: **Adjon hozzá** a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt egy vagy több köznapi nevet. Ha megadja ezt az információt, elkerülheti azt a dinamikus megbízhatósági ablakot, amely akkor jelenik meg a felhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.
    - **Kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: A felhasználótól a felhasználónevet és jelszót a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP-módszer (belső identitás)**: Válassza ki, hogyan hitelesíti a kapcsolatot. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Titkosítatlan jelszó (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)**, vagy **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Identitásadatok védelme (külső identitás)**: Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

  - **LEAP**

  - **PEAP**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **tanúsítvány-kiszolgálók nevei**: **Adjon hozzá** a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt egy vagy több köznapi nevet. Ha megadja ezt az információt, elkerülheti azt a dinamikus megbízhatósági ablakot, amely akkor jelenik meg a felhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.
    - **Kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: A felhasználótól a felhasználónevet és jelszót a kapcsolat hitelesítéséhez. 

      - **Tanúsítványok**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Identitásadatok védelme (külső identitás)**: Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

- **Proxybeállítások**: A választható lehetőségek:
  - **Nincs**: Semmilyen proxybeállítás nincs konfigurálva.
  - **Manuális**: Adja meg a **proxykiszolgáló címe** IP-címként, és a hozzá tartozó **portszám**.
  - **Automatikus**: Egy fájl segítségével konfigurálhatja a proxykiszolgálót. Adja meg a konfigurációs fájlt tartalmazó **proxykiszolgáló URL-címét** (például: `http://proxy.contoso.com`).

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="next-steps"></a>További lépések

A profil létrejön, de egyelőre nem csinál semmit. A következő lépés a [profil hozzárendelése](device-profile-assign.md).

## <a name="more-resources"></a>További források

[Wi-Fi-beállítások áttekintése](wi-fi-settings-configure.md), beleértve a többi rendelkezésre álló platformot is.
