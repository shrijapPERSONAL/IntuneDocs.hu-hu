---
title: VPN-beállítások konfigurálása Android-eszközökön a Microsoft Intune-ban – Azure | Microsoft Docs
description: Ha Android- vagy Android for Work-eszközön hoz létre VPN konfigurációs profilt, adja meg a kapcsolat nevét, a VPN-kiszolgáló IP-címét vagy teljes tartománynevét (FQDN), válassza ki a felhasználók hitelesítésének módját a VPN-kiszolgálón, majd válassza ki a Citrix, SonicWall, Check Point Capsule, Pulse Secure vagy Microsoft Edge kapcsolat típusát.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b90c9462ab41dcb03d131601e456c6c783aeb0ed
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57399140"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>VPN-beállítások konfigurálása Android rendszerű eszközökön az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cikk a VPN-kapcsolatoknak az Android rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti.

A következő platformokhoz konfigurálhat VPN-beállításokat:

- [Android](#android-vpn-settings)
- [Vállalati Android](#android-enterprise-vpn-settings)

A megadott beállításoktól függően az alábbi értékek közül nem mind konfigurálható.

## <a name="android-vpn-settings"></a>Android VPN-beállítások

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatokat az eszközükön.
- **IP-cím vagy FQDN**: Adja meg az IP-cím vagy teljes tartománynevét (FQDN), a VPN-kiszolgálóban, amelyhez az eszközök csatlakoznak. Írja be például a **192.168.1.1** vagy a **vpn.contoso.com** címet.

  - **Hitelesítési módszer**: Válassza ki, hogyan hitelesítik magukat az eszközök a VPN-kiszolgáló. A választható lehetőségek:

    - **Tanúsítványok**: Válassza ki egy meglévő SCEP- vagy PKCS-tanúsítványprofilt a kapcsolat hitelesítéséhez. [Tanúsítványok konfigurálása](certificates-configure.md): felsorolja a tanúsítványprofil létrehozásának lépéseit.
    - **Felhasználónév és jelszó**: Amikor bejelentkezik a VPN-kiszolgáló, a adjon meg egy felhasználónevet és jelszót a rendszer kéri a végfelhasználók számára.

- **Kapcsolat típusa**: Válassza ki a VPN-kapcsolat típusát. A választható lehetőségek:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Ujjlenyomattal történő** (Ellenőrizze a pont Capsule VPN esetén): Írjon be egy karakterláncot, például **Contoso-Ujjlenyomatkód**, ellenőrzésére, hogy a VPN-kiszolgáló is. Az ujjlenyomatok elküldhetők az ügyfélprogramnak, így az tudni fogja, hogy csatlakozáskor megbízhat-e az azonos ujjlenyomattal rendelkező kiszolgálókban. Ha az eszköz még nem rendelkezik ujjlenyomattal, akkor arra kéri a felhasználót, hogy bízzon meg a VPN-kiszolgálóban, miközben megjeleníti az ujjlenyomatot. A felhasználó manuálisan ellenőrizheti az ujjlenyomatot, és a kapcsolódáshoz választhatja, hogy megbízik benne.
- **Adja meg a kulcs-érték párokat a Citrix VPN attribútumainak** (kizárólag Citrix esetén): Adja meg a kulcs-érték párokat a Citrix által biztosított. Ezek az értékek konfigurálják a VPN-kapcsolat tulajdonságait.

## <a name="android-enterprise-vpn-settings"></a>VPN-beállítások Android enterprise

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatokat az eszközükön.
- **IP-cím vagy FQDN**: Adja meg az IP-cím vagy teljes tartománynevét (FQDN), a VPN-kiszolgálóban, amelyhez az eszközök csatlakoznak. Írja be például a **192.168.1.1** vagy a **vpn.contoso.com** címet.

  - **Hitelesítési módszer**: Válassza ki, hogyan hitelesítik magukat az eszközök a VPN-kiszolgáló. A választható lehetőségek:
  
    - **Tanúsítványok**: Válassza ki egy meglévő SCEP- vagy PKCS-tanúsítványprofilt a kapcsolat hitelesítéséhez. [Tanúsítványok konfigurálása](certificates-configure.md): felsorolja a tanúsítványprofil létrehozásának lépéseit.
    - **Felhasználónév és jelszó**: Amikor bejelentkezik a VPN-kiszolgáló, a adjon meg egy felhasználónevet és jelszót a rendszer kéri a végfelhasználók számára.

- **Kapcsolat típusa**: Válassza ki a VPN-kapcsolat típusát. A választható lehetőségek:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Access**
  - **Pulse Secure**

## <a name="next-steps"></a>További lépések
[VPN-profilok az Intune-ban](vpn-settings-configure.md)
