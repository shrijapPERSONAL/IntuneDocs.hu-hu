---
title: VPN-beállítások konfigurálása Android-eszközökön a Microsoft Intune-ban – Azure | Microsoft Docs
description: Ha Android- vagy Android for Work-eszközön hoz létre VPN konfigurációs profilt, adja meg a kapcsolat nevét, a VPN-kiszolgáló IP-címét vagy teljes tartománynevét (FQDN), válassza ki a felhasználók hitelesítésének módját a VPN-kiszolgálón, majd válassza ki a Citrix, SonicWall, Check Point Capsule, Pulse Secure vagy Microsoft Edge kapcsolat típusát.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ac4b7821f132c92b247538e4ea6131f517da7698
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187688"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>VPN-beállítások konfigurálása Android rendszerű eszközökön az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cikk a VPN-kapcsolatoknak az Android rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti.

A következő platformokhoz konfigurálhat VPN-beállításokat:

- [Android](#android-vpn-settings)
- [Android for work](#android-for-work-vpn-settings)

A megadott beállításoktól függően az alábbi értékek közül nem mind konfigurálható.

## <a name="android-vpn-settings"></a>Android VPN-beállítások

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatokat az eszközükön.
- **IP-cím vagy teljes tartománynév**: Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét (FQDN), amelyhez az eszközök csatlakoznak. Írja be például a **192.168.1.1** vagy a **vpn.contoso.com** címet.

  - **Hitelesítési mód**: Válassza ki, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón. A választható lehetőségek:

    - **Tanúsítványok**: Válasszon egy meglévő SCEP- vagy PKCS-tanúsítványprofilt a kapcsolat hitelesítéséhez. [Tanúsítványok konfigurálása](certificates-configure.md): felsorolja a tanúsítványprofil létrehozásának lépéseit.
    - **Felhasználónév és jelszó**: Amikor a végfelhasználó bejelentkezik a VPN-kiszolgálóra, felszólítást kap, hogy adjon meg egy felhasználónevet és egy jelszót.

- **Kapcsolat típusa**: Válassza ki a VPN-kapcsolat típusát. A választható lehetőségek:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Ujjlenyomat** (Csak Check Point Capsule VPN esetén): Adjon meg egy karakterláncot, mint például a **Contoso-ujjlenyomatkód**, a VPN-kiszolgáló megbízhatóságának ellenőrzéséhez. Az ujjlenyomatok elküldhetők az ügyfélprogramnak, így az tudni fogja, hogy csatlakozáskor megbízhat-e az azonos ujjlenyomattal rendelkező kiszolgálókban. Ha az eszköz még nem rendelkezik ujjlenyomattal, akkor arra kéri a felhasználót, hogy bízzon meg a VPN-kiszolgálóban, miközben megjeleníti az ujjlenyomatot. A felhasználó manuálisan ellenőrizheti az ujjlenyomatot, és a kapcsolódáshoz választhatja, hogy megbízik benne.
- **Adja meg a kulcs-érték párokat a Citrix VPN attribútumaihoz** (Csak Citrix esetén): Adja meg a Citrix által megadott kulcs-érték párokat. Ezek az értékek konfigurálják a VPN-kapcsolat tulajdonságait.

## <a name="android-for-work-vpn-settings"></a>Az Android for Work VPN-beállításai

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatokat az eszközükön.
- **IP-cím vagy teljes tartománynév**: Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét (FQDN), amelyhez az eszközök csatlakoznak. Írja be például a **192.168.1.1** vagy a **vpn.contoso.com** címet.

  - **Hitelesítési mód**: Válassza ki, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón. A választható lehetőségek:
  
    - **Tanúsítványok**: Válasszon egy meglévő SCEP- vagy PKCS-tanúsítványprofilt a kapcsolat hitelesítéséhez. [Tanúsítványok konfigurálása](certificates-configure.md): felsorolja a tanúsítványprofil létrehozásának lépéseit.
    - **Felhasználónév és jelszó**: Amikor a végfelhasználó bejelentkezik a VPN-kiszolgálóra, felszólítást kap, hogy adjon meg egy felhasználónevet és egy jelszót.

- **Kapcsolat típusa**: Válassza ki a VPN-kapcsolat típusát. A választható lehetőségek:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

## <a name="next-steps"></a>További lépések
[VPN-profilok az Intune-ban](vpn-settings-configure.md)
