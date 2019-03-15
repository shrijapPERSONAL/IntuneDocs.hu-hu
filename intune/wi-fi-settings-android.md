---
title: Wi-Fi-beállítások konfigurálása Android-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: Létrehozhat vagy hozzáadhat egy eszközkonfigurációs Wi-Fi-profilt az Android-eszközökhöz. Megtekintheti a Microsoft Intune különböző beállításait, beleértve a tanúsítványok hozzáadását, az EAP-típusok kiválasztását és a hitelesítési módszer kiválasztását.
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
ms.openlocfilehash: bac109164a1e75ce14efc5d61201e829e572e502
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565978"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Android rendszerű eszközökre vonatkozó Wi-Fi-beállítások hozzáadása a Microsoft Intune-ban

Adott Wi-Fi-beállításokkal rendelkező profilt hozhat létre, majd ezt a profilt üzembe helyezheti az Android-eszközökön. A Microsoft Intune számos szolgáltatást nyújt, beleértve a hálózaton való hitelesítést, a PKS- vagy SCEP-tanúsítványok hozzáadását és egyéb lehetőségeket.

Ezek a Wi-Fi-beállítások vannak elválasztva egymástól két kategóriára: Alapvető beállítások és a vállalati szintű beállításait.

Ez a cikk ezeket a beállításokat ismerteti.

## <a name="before-you-begin"></a>Előkészületek

[Eszközprofil létrehozása](device-profile-create.md).

## <a name="basic-profile"></a>Alapszintű profil

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

    - **Kiszolgáló megbízhatósága** - **kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** - **ügyféltanúsítvány a hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítványt)**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

      Válassza ki **OK** a módosítások mentéséhez.

  - **EAP-TTLS**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

      Válassza ki **OK** a módosítások mentéséhez.

    - **Ügyfél-hitelesítés** – Válasszon egy **hitelesítési módszert**. A választható lehetőségek:

      - **Felhasználónév és jelszó**: A felhasználótól a felhasználónevet és jelszót a kapcsolat hitelesítéséhez. Ezt is adja meg:
        - **Nem EAP-módszer (belső identitás)**: Válassza ki, hogyan hitelesíti a kapcsolatot. Mindenképpen ugyanazt a protokollt válassza, amely a Wi-Fi-hálózathoz van konfigurálva.

          A választható lehetőségek: **Titkosítatlan jelszó (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)**, vagy **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Tanúsítványok**: Válassza ki az SCEP- vagy PKCS-ügyfél-profilt, amely az eszköz számára is telepíti. Az eszköz ezt a tanúsítványt adja meg identitásként a kiszolgálónak a kapcsolat hitelesítéséhez.

        Válassza ki **OK** a módosítások mentéséhez.

      - **Identitásadatok védelme (külső identitás)**: Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg bármilyen érték lehet, például `anonymous`. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

  - **PEAP**: Ezt is adja meg:

    - **Kiszolgáló megbízhatósága** - **kiszolgálói érvényesítéshez használandó főtanúsítványok**: Válasszon egy meglévő megbízható főtanúsítvány-profilt. A rendszer ezt a tanúsítványt adja meg a kiszolgálónak, amikor az ügyfél a hálózathoz csatlakozik, és ezzel hitelesíti a kapcsolatot.

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

A profil létrejön, de egyelőre nem csinál semmit. A következő lépés a [profil hozzárendelése](device-profile-assign.md).

## <a name="more-resources"></a>További források

- [Wi-Fi-beállítások áttekintése](wi-fi-settings-configure.md), beleértve a többi platformot is.

- Android Enterprise vagy Android Kiosk rendszerű eszközöket használ? Ha igen, olvassa el az [Android Enterprise és Android Kiosk rendszerű eszközökre vonatkozó Wi-Fi-beállításokat](wi-fi-settings-android-enterprise.md) ismertető cikket.
