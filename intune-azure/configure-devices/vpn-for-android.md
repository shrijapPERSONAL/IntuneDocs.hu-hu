---
title: "Az Intune VPN-beállításai androidos eszközökhöz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: További tudnivalók a VPN-kapcsolatok androidos eszközökön való konfigurálásához használható Intune-beállításokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: f93ab44889837fe8acc5dd5287b63f3b30678159


---

# <a name="vpn-settings-for-android-devices-in-intune-azure-preview"></a>Az androidos eszközökre vonatkozó VPN-beállítások a következőben: Intune az Azure-on – előzetes

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A megadott beállításoktól függően az alábbi listában található értékek némelyike nem konfigurálható.

**Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
- **Hitelesítési módszer** – Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
    - **Tanúsítványok** – Adjon meg egy, a kapcsolat hitelesítéséhez korábban létrehozott SCEP- vagy PKCS-tanúsítványprofilt. A tanúsítványprofilokról további információt a [How to configure certificates](how-to-configure-certificates.md) (Tanúsítványok konfigurálása) című cikkben találhat.
    - **Felhasználónév és jelszó** – A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha szeretnének bejelentkezni a VPN-kiszolgálóra.
- **Kapcsolat típusa** – Az szállítók alábbi listájából válassza ki a VPN-kapcsolat típusát:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Ujjlenyomat** (Kizárólag Check Point Capsule VPN esetén) – Adjon meg egy sztringet (például „Contoso-ujjlenyomatkód”), amelyet a rendszer a VPN-kiszolgáló megbízhatóságának ellenőrzésére fog használni. Az ujjlenyomatok elküldhetők az ügyfélprogramnak, így az tudni fogja, hogy megbízhat-e az azonos ujjlenyomattal rendelkező kiszolgálókban a csatlakozáskor. Ha az eszköz még nem rendelkezik ujjlenyomattal, akkor arra fogja kérni a felhasználót, hogy bízzon meg a VPN-kiszolgálóban, amelyhez csatlakozik, miközben megjeleníti az ujjlenyomatot (a felhasználó manuálisan ellenőrizheti az ujjlenyomatot, majd a Megbízom benne elemet választva csatlakozhat).
- **Adja meg a kulcs-érték párokat a Citrix VPN attribútumainak konfigurálásához** (Kizárólag Citrix esetén) – A Citrix által biztosított kulcs-érték párok megadásával konfigurálhatja a VPN-kapcsolat tulajdonságait.



<!--HONumber=Feb17_HO2-->


