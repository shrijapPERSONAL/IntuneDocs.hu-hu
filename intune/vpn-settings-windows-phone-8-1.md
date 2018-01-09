---
title: "VPN-beállítások az Intune-ban Windows Phone 8.1-es eszközök esetén"
titleSuffix: Azure portal
description: "A cikk a VPN-kapcsolatoknak a Windows Phone 8.1 rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti.”"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e14f694ee1008766483736933c2ccdf22ee3881
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/30/2017
---
# <a name="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Windows Phone 8.1-es eszközökre vonatkozó VPN-beállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A megadott beállításoktól függően az alábbi listában található értékek némelyike nem konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások

- **Az összes beállítás alkalmazása csak Windows Phone 8.1 rendszeren** – Ez a beállítás a klasszikus Intune-portálon konfigurálható. Ez a beállítás az Azure Portal webhelyen nem módosítható. Ha ez a beállítás a **Konfigurálva** értékre van állítva, a rendszer minden beállítást csak a Windows Phone 8.1 rendszerű eszközökre alkalmaz. Ha a **Nincs konfigurálva** értékre van állítva, akkor a Windows 10 Mobile rendszerű eszközökre is alkalmazza rendszer ezeket a beállításokat.
- **Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor rendelkezésre álló VPN-kapcsolatokat keresnek az eszközükön.
- **Hitelesítési mód** – Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
    - **Tanúsítványok** – A **Hitelesítési tanúsítvány** szakaszban adja meg a kapcsolat hitelesítéséhez korábban létrehozott SCEP- vagy PKCS-tanúsítványprofilok valamelyikét. A tanúsítványprofilokról [a tanúsítványok konfigurálását](certificates-configure.md) ismertető cikkben talál részletesebb tájékoztatást.
    - **Felhasználónév és jelszó** – A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha be szeretnének jelentkezni a VPN-kiszolgálóra.
- **Kiszolgálók** – Itt adhat meg egy vagy több olyan VPN-kiszolgálót, amelyhez az eszközök csatlakozni fognak.
    - **Hozzáadás** – Megnyitja a **Sor hozzáadása** panelt, melyen a következőket adhatja meg:
        - **Leírás** – Adja meg a kiszolgáló leíró nevét (például **Contoso VPN-kiszolgáló**).
        - **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
        - **Alapértelmezett kiszolgáló** – Ezt a kiszolgálót engedélyezi alapértelmezett kiszolgálóként, melyet az eszközök kapcsolat létesítéséhez fognak használni. Mindenképpen csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
    - **Importálás** – Tallózással keressen meg egy, a kiszolgálók vesszővel tagolt listáját tartalmazó fájlt, melynek formátuma a következő: leírás, IP-cím vagy teljes tartománynév, alapértelmezett kiszolgáló. Az **OK** gombra kattintva indíthatja el ezek importálását a **Kiszolgálók** listába.
    - **Exportálás** – Exportálja a kiszolgálók listáját egy vesszővel tagolt (CSV-) fájlba.

- **VPN mellőzése a céges Wi-Fi-hálózatban** – Ezzel a beállítással letilthatja a VPN-kapcsolatot, amikor az eszköz a vállalati Wi-Fi-hálózathoz csatlakozik.
- **VPN mellőzése az otthoni Wi-Fi-hálózatban** – Ezzel a beállítással letilthatja a VPN-kapcsolatot, amikor az eszköz az otthoni Wi-Fi-hálózathoz csatlakozik.

- **Kapcsolat típusa** – Az alábbi szállítólistából válassza ki a VPN-kapcsolat típusát:
    - **Check Point Capsule VPN**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Bejelentkezési csoport vagy tartomány** (csak Dell SonicWALL Mobile Connect) – Adja meg annak a bejelentkezési csoportnak vagy tartománynak a nevét, amelyhez csatlakozni szeretne.
- **Szerepkör** (csak Pulse Secure) – Adja meg annak a felhasználói szerepkörnek a nevét, amely hozzáfér ehhez a kapcsolathoz. A felhasználói szerepkörök személyes beállításokat definiálnak, és engedélyeznek vagy letiltanak bizonyos hozzáférési funkciókat.
- **Tartomány** (csak Pulse Secure) – Adja meg a használni kívánt hitelesítési tartomány nevét. A hitelesítési tartomány a Pulse Secure kapcsolattípus által használt hitelesítési erőforrások csoportja.

- **DNS-utótagok keresési listája**  -  Vegyen fel egy vagy több DNS-utótagot a **Hozzáadás** gombra kattintva. A rendszer minden egyes megadott DNS-utótagra rákeres, amikor egy rövid nevet használó webhelyhez csatlakozik. Adja meg például a **domain1.contoso.com** és a **domain2.contoso.com** DNS-utótagot, majd látogasson el a **http://sajatwebhely** URL-címre. Ekkor a **http://sajatwebhely.domain1.contoso.com** és a **http://sajatwebhely.domain2.contoso.com** URL-címre fog keresni a rendszer.

- **Egyéni XML** – Itt a VPN-kapcsolatot konfiguráló egyéni XML-parancsokat adhat meg.

    **Példa a Pulse Secure esetére:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**Példa a CheckPoint Mobile VPN esetére:**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Példa a Dell SonicWALL Mobile Connect esetére:**
```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**Példa az F5 Edge Client esetére:**
```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Az egyéni XML-parancsok írásával kapcsolatban további információt az egyes gyártók VPN-dokumentációjában talál.

- **Bújtatás megosztása**  -  Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.




## <a name="proxy-settings"></a>Proxybeállítások

- **Proxybeállítások automatikus észlelése** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, adja meg, hogy szeretné-e, ha az eszközök automatikusan észlelnék a kapcsolatbeállításokat. További információt a Windows Server dokumentációjában talál.
- **Automatikus konfigurációs szkript** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Proxykiszolgáló használata** – Ha manuálisan szeretné megadni a proxykiszolgáló beállításait, akkor engedélyezze ezt a beállítást.
    - **Cím** – Adja meg a proxykiszolgáló címét (IP-címként).
    - **Portszám** – Adja meg a proxykiszolgálóhoz társított portszámot.
- **Proxy mellőzése helyi címek esetén** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, ha a megadott helyi címekhez nem szeretné használni a proxykiszolgálót. További információt a Windows Server dokumentációjában talál.
