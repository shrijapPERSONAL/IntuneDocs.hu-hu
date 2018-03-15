---
title: "A Microsoft Intune Android rendszerű eszközökre vonatkozó VPN-beállításai"
titlesuffix: 
description: "Útmutató a VPN-kapcsolatok Android rendszerű eszközökön való konfigurálásához használható Intune-beállításokhoz"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3fe05b5fdd87e92f5acc35c0a750287f8fd01b92
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-android"></a>Az Android rendszerű eszközökre vonatkozó VPN-beállítások konfigurálása a Microsoft Intune-ban 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A következő platformokhoz konfigurálhat VPN-beállításokat:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

A megadott beállításoktól függően az alábbi értékek közül nem mind konfigurálható.

## <a name="android-vpn-settings"></a>Android VPN-beállítások
**Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakoznak. Példák: **192.168.1.1**, **vpn.contoso.com**.
- **Hitelesítési módszer** – Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
    - **Tanúsítványok** – Adjon meg egy, a kapcsolat hitelesítéséhez korábban létrehozott SCEP- vagy PKCS-tanúsítványprofilt. A tanúsítványprofilokról további információt a [How to configure certificates](certificates-configure.md) (Tanúsítványok konfigurálása) című cikkben találhat.
    - **Felhasználónév és jelszó** – A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha szeretnének bejelentkezni a VPN-kiszolgálóra.
- **Kapcsolat típusa** – Az alábbi listából válassza ki a VPN-kapcsolat típusát:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Ujjlenyomat** (Kizárólag Check Point Capsule VPN esetén) – Adjon meg egy sztringet (például „Contoso-ujjlenyomatkód”), amelyet a rendszer a VPN-kiszolgáló megbízhatóságának ellenőrzésére használ. Az ujjlenyomatok elküldhetők az ügyfélprogramnak, így az tudni fogja, hogy megbízhat-e az azonos ujjlenyomattal rendelkező kiszolgálókban a csatlakozáskor. Ha az eszköz még nem rendelkezik ujjlenyomattal, akkor arra kéri a felhasználót, hogy bízzon meg a VPN-kiszolgálóban, amelyhez csatlakozik, miközben megjeleníti az ujjlenyomatot (a felhasználó manuálisan ellenőrizheti az ujjlenyomatot, majd a Megbízom benne elemet választva csatlakozhat).
- **Adja meg a kulcs-érték párokat a Citrix VPN attribútumainak konfigurálásához** (Kizárólag Citrix esetén) – A Citrix által biztosított kulcs-érték párok megadásával konfigurálhatja a VPN-kapcsolat tulajdonságait.

## <a name="android-for-work-vpn-settings"></a>Az Android for Work VPN-beállításai

**Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakoznak. Példák: **192.168.1.1**, **vpn.contoso.com**.
- **Hitelesítési módszer** – Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
    - **Tanúsítványok** – Adjon meg egy, a kapcsolat hitelesítéséhez korábban létrehozott SCEP- vagy PKCS-tanúsítványprofilt. A tanúsítványprofilokról további információt a [How to configure certificates](certificates-configure.md) (Tanúsítványok konfigurálása) című cikkben találhat.
    - **Felhasználónév és jelszó** – A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha szeretnének bejelentkezni a VPN-kiszolgálóra.
- **Kapcsolat típusa** – Az alábbi listából válassza ki a VPN-kapcsolat típusát:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

