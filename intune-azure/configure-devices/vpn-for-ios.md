---
title: "VPN-beállítások az Intune-ban iOS-eszközök esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes:További tudnivalók a VPN-kapcsolatok iOS-eszközökön való konfigurálásához használható Intune-beállításokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 5b450c74a5c6353219393e10acf69ba9e61a2ccb
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-ios-devices-in-microsoft-intune"></a>iOS-eszközökre vonatkozó VPN-beállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A megadott beállításoktól függően az alábbi listában található értékek némelyike nem konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások


**Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
- **Hitelesítési módszer** – Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
    - **Tanúsítványok** – A **Hitelesítési tanúsítvány** szakaszban adja meg a kapcsolat hitelesítéséhez korábban létrehozott SCEP- vagy PKCS-tanúsítványprofilok valamelyikét. A tanúsítványprofilokról [a tanúsítványok konfigurálását](how-to-configure-certificates.md) ismertető cikkben talál részletesebb tájékoztatást.
    - **Felhasználónév és jelszó** – A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha szeretnének bejelentkezni a VPN-kiszolgálóra.
- **Kapcsolat típusa** – Az alábbi listából válassza ki a VPN-kapcsolat típusát:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPsec)**
    - **Citrix**
    - **Egyéni VPN**
- **Bújtatás megosztása** - Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.


## <a name="custom-vpn-settings"></a>Egyéni VPN-beállítások

Ha a kapcsolat típusaként az **Egyéni VPN** lehetőséget állította be, konfigurálja a következő további beállításokat:

- **VPN-azonosító** Ez az Ön által használt VPN-alkalmazás azonosítója, amelyet a VPN-szolgáltatója biztosított.
- **Adja meg a kulcs-érték párokat az egyéni VPN attribútumainak konfigurálásához** **Kulcsok** és **Értékek** hozzáadásával vagy importálásával szabhatja testre a VPN-kapcsolatot. Ezeket az értékeket is rendszerint a VPN-szolgáltató biztosítja.

## <a name="apps-per-app-vpn-settings"></a>Alkalmazások (alkalmazásonkénti VPN) beállításai

- **Alkalmazásonkénti VPN** – Igény szerint engedélyezheti ezt a beállítást olyan URL-címekhez, melyek engedélyezik a VPN-kapcsolatot, ha megnyitják őket a Safari böngészőből. Ennek konfiguráláshoz hitelesítési módszerként a **Tanúsítványok** lehetőséget kellett választania az alapvető VPN-beállításokban.
- **Adja meg azokat az URL-címeket, amelyek a Safari böngésző használata közben lehetővé teszik a VPN-kapcsolat létrehozását** – A Hozzáadás elemre kattintva hozzáadhatja egy vagy több webhely URL-címét. A rendszer ezen URL-címek megnyitásakor engedélyezi a VPN-kapcsolatot.

- **Igény szerinti szabályok** – Ezzel a beállítással feltételes szabályokat állíthat be, melyek VPN-kapcsolat kezdeményezésekor lépnek érvénybe. Létrehozhat például egy olyan feltételt, amelyben a rendszer csak akkor használja a VPN-kapcsolatot, ha az eszköz nem kapcsolódik valamelyik vállalati Wi-Fi-hálózathoz. Másik lehetőségként olyan feltételt is létrehozhat, amelyben ha egy eszköz nem férhet hozzá egy megadott DNS-keresési tartományhoz, akkor a rendszer nem kezdeményez VPN-kapcsolatot.

    - **SSID-k vagy DNS-keresési tartományok** – Megadhatja, hogy a feltétel vezeték nélküli hálózatok **SSID-it** vagy **DNS-keresési tartományokat** használjon. Egy vagy több SSID vagy keresési tartomány konfigurálásához válassza a Hozzáadás lehetőséget.
    - **URL-sztringminta** – Igény szerint megadhat egy szabály által tesztként használt URL-címet is. Ha az eszköz, amelyen a profil telepítve van, átirányítás nélkül el tudja érni az URL-címet, a rendszer kezdeményezi a VPN-kapcsolatot, és az eszköz kapcsolódik a célként megadott URL-címre. A felhasználó nem látja a teszthez használt URL-célhelyet. URL-sztringmintaként meg lehet adni például egy naplózási webkiszolgálót, amely VPN-kapcsolat létrejötte előtt ellenőrzi az eszköz megfelelőségét. Egy másik lehetőség, hogy az URL-cím ellenőrzi a VPN webhelyhez történő kapcsolódási képességét azlőtt, hogy létrejönne a VPN-kapcsolat az eszköz és a célként megadott URL-cím között.
    - **Tartományi művelet** – Válasszon a következő lehetőségek közül:
        - Szükség esetén kapcsolódás – 
        - Soha ne legyen kapcsolódás – 
    - **Művelet** – Válasszon a következő lehetőségek közül:
        - Kapcsolódás – 
        - Kapcsolat kiértékelése – 
        - Figyelmen kívül hagyás – 
        - Kapcsolat bontása – 


## <a name="proxy-settings"></a>Proxybeállítások

- **Automatikus konfigurációs szkript** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Cím** – Adja meg a proxykiszolgáló címét (IP-címként).
- **Portszám** – Adja meg a proxykiszolgálóhoz társított portszámot.

