---
title: "VPN-beállítások az Intune-ban Android-eszközök esetén"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt a VPN-kapcsolatok Android-eszközökön való konfigurálásához használható Intune-beállításokról"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31d1e40c3cd352c00dd7a659f716b5690ea64ea1
ms.sourcegitcommit: 5877b650d93fc9a5e8f058f845acbdbfdff828b7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Androidos eszközökre vonatkozó VPN-beállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune-rendszergazdaként a következő platformokhoz konfigurálhat VPN-beállításokat:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

A kiválasztott beállításoktól függően nem minden, az alábbiakban felsorolt érték konfigurálható.

## <a name="android-vpn-settings"></a>Android VPN-beállítások
**Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
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

- **Ujjlenyomat** (Kizárólag Check Point Capsule VPN esetén) – Adjon meg egy sztringet (például „Contoso-ujjlenyomatkód”), amelyet a rendszer a VPN-kiszolgáló megbízhatóságának ellenőrzésére fog használni. Az ujjlenyomatok elküldhetők az ügyfélprogramnak, így az tudni fogja, hogy megbízhat-e az azonos ujjlenyomattal rendelkező kiszolgálókban a csatlakozáskor. Ha az eszköz még nem rendelkezik ujjlenyomattal, akkor arra fogja kérni a felhasználót, hogy bízzon meg a VPN-kiszolgálóban, amelyhez csatlakozik, miközben megjeleníti az ujjlenyomatot (a felhasználó manuálisan ellenőrizheti az ujjlenyomatot, majd a Megbízom benne elemet választva csatlakozhat).
- **Adja meg a kulcs-érték párokat a Citrix VPN attribútumainak konfigurálásához** (Kizárólag Citrix esetén) – A Citrix által biztosított kulcs-érték párok megadásával konfigurálhatja a VPN-kapcsolat tulajdonságait.

## <a name="android-for-work-vpn-settings"></a>Az Android for Work VPN-beállításai

**Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
- **Hitelesítési módszer** – Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
    - **Tanúsítványok** – Adjon meg egy, a kapcsolat hitelesítéséhez korábban létrehozott SCEP- vagy PKCS-tanúsítványprofilt. A tanúsítványprofilokról további információt a [How to configure certificates](certificates-configure.md) (Tanúsítványok konfigurálása) című cikkben találhat.
    - **Felhasználónév és jelszó** – A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha szeretnének bejelentkezni a VPN-kiszolgálóra.
- **Kapcsolat típusa** – Az alábbi listából válassza ki a VPN-kapcsolat típusát:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

