---
title: Wi-Fi-beállítások Android Enterprise és a teljes képernyős eszközökhöz
titleSuffix: Microsoft Intune
description: Wi-Fi eszközkonfigurációs profilokat hozhat létre vagy adhat hozzá az Android Enterprise és Android kioszk rendszerhez. Megtekintheti a Microsoft Intune különböző beállításait, beleértve a tanúsítványok hozzáadását, az EAP-típusok kiválasztását és a hitelesítési módszer kiválasztását. Kioszkeszközök esetén adja meg a hálózat előre megosztott kulcsát is.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 1424cd43c6ccde17724a4165fe74def4da291e29
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112357"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Android Enterprise és Android kioszk rendszerű eszközökre vonatkozó Wi-Fi-beállítások hozzáadása a Microsoft Intune-ban

Adott Wi-Fi-beállításokkal rendelkező profilt hozhat létre, majd ezt a profilt üzembe helyezheti az Android Enterprise- és androidos kioszkeszközökön. A Microsoft Intune számos szolgáltatást nyújt, beleértve a hálózaton való hitelesítést, az előmegosztott kulcsok használatát és egyebeket.

Ez a cikk ezeket a beállításokat ismerteti.

## <a name="before-you-begin"></a>Előkészületek

[Eszközprofil létrehozása](device-profile-create.md).

## <a name="device-owner-only---kiosk"></a>Csak az eszköz tulajdonosa – kioszk

Válassza ezt a lehetőséget, ha Android Enterprise-eszközt használ kioszk üzemmódban.

- **Hálózat neve**: Adja meg a Wi-Fi-kapcsolat nevét. Ez a név jelenik meg a felhasználók számára, amikor az eszközön rendelkezésre álló kapcsolatok listáját böngészik.
- **SSID**: A **szolgáltatáskészlet-azonosító** rövidítése. Ez a beállítás annak a vezeték nélküli hálózatnak a valódi neve, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált **hálózatnevet** látják, amikor kiválasztják a kapcsolatot.
- **Automatikus csatlakozás**: Válassza az **Engedélyezés** lehetőséget, hogy automatikusan csatlakozzon ehhez a hálózathoz, amikor az eszköz hatótávolságon belül van. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válassza az **Engedélyezés** lehetőséget, hogy a hálózat ne jelenjen meg az eszközön elérhető hálózatok listájában. A rendszer ilyenkor nem továbbítja az SSID-t. Válassza a **Letiltás** lehetőséget, ha meg szeretné jeleníteni a hálózatot az eszközön elérhető hálózatok listájában.
- **Wi-Fi típusa**: Válassza ki a Wi-Fi-hálózat hitelesítéséhez használt biztonsági protokollt. A választható lehetőségek:

  - **Nyitott (nincs hitelesítés)**: Csak akkor válassza ezt a lehetőséget, ha a hálózat nem védett.
  - **WEP előmegosztott kulcs**: Írja be a jelszót az **Előmegosztott kulcs** mezőbe. A cég hálózatának beállítása vagy konfigurálása során a rendszer egy jelszót vagy egy hálózati kulcsot is konfigurál. Adja meg ezt a jelszót vagy hálózati kulcsot a PSK értékeként.
  - **WPA előre megosztott kulcs**: Írja be a jelszót az **Előmegosztott kulcs** mezőbe. A cég hálózatának beállítása vagy konfigurálása során a rendszer egy jelszót vagy egy hálózati kulcsot is konfigurál. Adja meg ezt a jelszót vagy hálózati kulcsot a PSK értékeként.

Válassza ki **OK** a módosítások mentéséhez.

## <a name="work-profile-only"></a>Csak munkahelyi profil

### <a name="basic-settings"></a>Alapbeállítások

- **Wi-Fi típusa**: válassza az **Alapszintű** lehetőséget.
- **SSID**: A **szolgáltatáskészlet-azonosító** rövidítése. Ez a beállítás annak a vezeték nélküli hálózatnak a valódi neve, amelyhez az eszközök csatlakoznak.
- **Automatikus csatlakozás**: Válassza az **Engedélyezés** lehetőséget, hogy automatikusan csatlakozzon ehhez a hálózathoz, amikor az eszköz hatótávolságon belül van. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válassza az **Engedélyezés** lehetőséget, hogy a hálózat ne jelenjen meg az eszközön elérhető hálózatok listájában. A rendszer ilyenkor nem továbbítja az SSID-t. Válassza a **Letiltás** lehetőséget, ha meg szeretné jeleníteni a hálózatot az eszközön elérhető hálózatok listájában.

## <a name="enterprise-profile"></a>Vállalati profil

- **Wi-Fi típusa**: Válassza a **Vállalati** elemet.
- **SSID**: A **szolgáltatáskészlet-azonosító** rövidítése. Ez a beállítás annak a vezeték nélküli hálózatnak a valódi neve, amelyhez az eszközök csatlakoznak.
- **Automatikus csatlakozás**: Válassza az **Engedélyezés** lehetőséget, hogy automatikusan csatlakozzon ehhez a hálózathoz, amikor az eszköz hatótávolságon belül van. Válassza a **Letiltás** lehetőséget, ha meg szeretné akadályozni az eszközök automatikus csatlakozását.
- **Rejtett hálózat**: Válassza az **Engedélyezés** lehetőséget, hogy a hálózat ne jelenjen meg az eszközön elérhető hálózatok listájában. A rendszer ilyenkor nem továbbítja az SSID-t. Válassza a **Letiltás** lehetőséget, ha meg szeretné jeleníteni a hálózatot az eszközön elérhető hálózatok listájában.
- **EAP típusa**: Válassza ki azt az EAP-protokollt, amelyet használni szeretne a biztonságos vezeték nélküli kapcsolatok hitelesítéséhez. A választható lehetőségek: 

  - **EAP-TLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **Főtanúsítvány a kiszolgálóérvényesítéshez**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** - **Ügyféltanúsítvány az ügyfél hitelesítéséhez (identitástanúsítvány)**: Válassza ki azt az SCEP vagy PKCS ügyféltanúsítvány-profilt, amely szintén üzembe lesz helyezve az eszközön. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

      Válassza ki **OK** a módosítások mentéséhez.

  - **EAP-TTLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **Főtanúsítvány a kiszolgálóérvényesítéshez**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: Felhasználónév és jelszó kérése a felhasználótól a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP-módszer (belső identitás)**: Válassza ki a kapcsolat hitelesítési módját. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Titkosítatlan jelszó (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)** vagy **Microsoft CHAP 2-es verzió (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki azt az SCEP vagy PKCS ügyféltanúsítvány-profilt, amely szintén üzembe lesz helyezve az eszközön. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Identitásvédelem (külső identitás)**: Adja meg az EAP-identitáskérésre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

  - **PEAP**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **Főtanúsítvány a kiszolgálóérvényesítéshez**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: Felhasználónév és jelszó kérése a felhasználótól a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP hitelesítési módszer (belső identitás)**: Válassza ki a kapcsolat hitelesítési módját. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Nincs** vagy **Microsoft CHAP 2-es verzió (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki azt az SCEP vagy PKCS ügyféltanúsítvány-profilt, amely szintén üzembe lesz helyezve az eszközön. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Identitásvédelem (külső identitás)**: Adja meg az EAP-identitáskérésre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="next-steps"></a>További lépések

A profil létrejön, de egyelőre nem csinál semmit. A következő lépés a [profil hozzárendelése](device-profile-assign.md).

## <a name="more-resources"></a>További források

- Az Android-eszközökhöz elérhető beállításokat az [Android rendszerű eszközök Wi-Fi-beállításait ismertető szakaszban](wi-fi-settings-android.md) találja.
- [Wi-Fi-beállítások áttekintése](wi-fi-settings-configure.md), beleértve a többi platformot is.