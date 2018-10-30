---
title: Wi-Fi-beállítások konfigurálása Android-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: Létrehozhat vagy hozzáadhat egy eszközkonfigurációs Wi-Fi-profilt az Android-eszközökhöz. Megtekintheti a Microsoft Intune különböző beállításait, beleértve a tanúsítványok hozzáadását, az EAP-típusok kiválasztását és a hitelesítési módszer kiválasztását.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7c0d11e7670134c6a2cd9ce2eb72714ba64aa03
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2018
ms.locfileid: "49424985"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Android rendszerű eszközökre vonatkozó Wi-Fi-beállítások hozzáadása a Microsoft Intune-ban

Adott Wi-Fi-beállításokkal rendelkező profilt hozhat létre, majd ezt a profilt üzembe helyezheti az Android-eszközökön. A Microsoft Intune számos szolgáltatást nyújt, beleértve a hálózaton való hitelesítést, a PKS- vagy SCEP-tanúsítványok hozzáadását és egyéb lehetőségeket.

Ezek a Wi-Fi-beállítások két kategóriára vannak osztva, alapszintű és vállalati szintű beállításokra.

Ez a cikk ezeket a beállításokat ismerteti.

## <a name="before-you-begin"></a>Előkészületek

[Eszközprofil létrehozása](device-profile-create.md).

## <a name="basic-profile"></a>Alapszintű profil

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

      A módosítások mentéséhez válassza az **OK** gombot.

    - **Ügyfél-hitelesítés** - **Ügyféltanúsítvány az ügyfél hitelesítéséhez (identitástanúsítvány)**: Válassza ki azt az SCEP vagy PKCS ügyféltanúsítvány-profilt, amely szintén üzembe lesz helyezve az eszközön. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

      A módosítások mentéséhez válassza az **OK** gombot.

  - **EAP-TTLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **Főtanúsítvány a kiszolgálóérvényesítéshez**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      A módosítások mentéséhez válassza az **OK** gombot.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: Felhasználónév és jelszó kérése a felhasználótól a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP-módszer (belső identitás)**: Válassza ki a kapcsolat hitelesítési módját. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Titkosítatlan jelszó (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)** vagy **Microsoft CHAP 2-es verzió (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki azt az SCEP vagy PKCS ügyféltanúsítvány-profilt, amely szintén üzembe lesz helyezve az eszközön. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        A módosítások mentéséhez válassza az **OK** gombot.

      - **Identitásvédelem (külső identitás)**: Adja meg az EAP-identitáskérésre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

  - **PEAP**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **Főtanúsítvány a kiszolgálóérvényesítéshez**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      A módosítások mentéséhez válassza az **OK** gombot.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: Felhasználónév és jelszó kérése a felhasználótól a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP hitelesítési módszer (belső identitás)**: Válassza ki a kapcsolat hitelesítési módját. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Nincs** vagy **Microsoft CHAP 2-es verzió (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki azt az SCEP vagy PKCS ügyféltanúsítvány-profilt, amely szintén üzembe lesz helyezve az eszközön. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        A módosítások mentéséhez válassza az **OK** gombot.

      - **Identitásvédelem (külső identitás)**: Adja meg az EAP-identitáskérésre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="next-steps"></a>További lépések

A profil létrejön, de egyelőre nem csinál semmit. A következő lépés a [profil hozzárendelése](device-profile-assign.md).

## <a name="more-resources"></a>További források

- [Wi-Fi-beállítások áttekintése](wi-fi-settings-configure.md), beleértve a többi platformot is.

- Android Enterprise vagy Android Kiosk rendszerű eszközöket használ? Ha igen, olvassa el az [Android Enterprise és Android Kiosk rendszerű eszközökre vonatkozó Wi-Fi-beállításokat](wi-fi-settings-android-enterprise.md) ismertető cikket.
