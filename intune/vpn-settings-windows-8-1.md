---
title: "Az Intune-hoz szükséges VPN-beállítások Windows 8.1-es eszközök esetén"
titleSuffix: Intune on Azure
description: "Útmutató a VPN-kapcsolatok Windows 8.1-eszközökön való konfigurálásához használható Intune-beállításokhoz."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d851a8900ae1e164cb22f1878b352c3e90096f73
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="vpn-settings-for-windows-81-devices-in-microsoft-intune"></a>A Microsoft Intune-ban regisztrált Windows 8.1-eszközök VPN-beállításai

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A megadott beállításoktól függően az alábbi listában található értékek némelyike nem konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások


- **Az összes beállítás alkalmazása csak a Windows Phone 8.1-re** – Ezt a beállítást a hagyományos Intune-portálon lehet konfigurálni. Ez a beállítás az Azure Portalon nem módosítható. Ha ez a beállítás a **Konfigurálva** értékre van állítva, minden beállítást csak a Windows 8.1-eszközökre alkalmaz a rendszer. Ha a **Nincs konfigurálva** értékre van állítva, akkor a Windows 10 rendszerű eszközökre is alkalmazza rendszer ezeket a beállításokat.
- **Kapcsolat neve** – Nevezze el a kapcsolatot. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **Kiszolgálók** – Adjon meg egy vagy több olyan VPN-kiszolgálót, amelyhez az eszközök csatlakozni fognak.
    - **Hozzáadás** – Megnyitja a **Sor hozzáadása** panelt, melyen a következőket adhatja meg:
        - **Leírás** – Adja meg a kiszolgáló leíró nevét (például **Contoso VPN-kiszolgáló**).
        - **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
        - **Alapértelmezett kiszolgáló** – Ezt a kiszolgálót engedélyezi alapértelmezett kiszolgálóként, melyet az eszközök kapcsolat létesítéséhez fognak használni. Csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
    - **Importálás** – Tallózással keresse meg a kiszolgálók vesszővel tagolt listáját tartalmazó fájlt (formátuma: leírás, IP-cím vagy teljes tartománynév, alapértelmezett kiszolgáló). Indítsa el ezeknek a **Kiszolgálók** listába való importálását az **OK** gombra kattintva.
    - **Exportálás** – Exportálja a kiszolgálók listáját egy vesszővel tagolt (CSV-) fájlba.

- **Kapcsolat típusa** – Az alábbi szállítólistából válassza ki a VPN-kapcsolat típusát:
- **Check Point Capsule VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Bejelentkezési csoport vagy tartomány** (csak Dell SonicWALL Mobile Connect) – Adja meg annak a bejelentkezési csoportnak vagy tartománynak a nevét, amelyhez csatlakozni szeretne.

- **Szerepkör** (csak Pulse Secure) – Adja meg annak a felhasználói szerepkörnek a nevét, amely hozzáfér ehhez a kapcsolathoz. A felhasználói szerepkörök személyes beállításokat definiálnak, és engedélyeznek vagy letiltanak bizonyos hozzáférési funkciókat.

- **Tartomány** (csak Pulse Secure) – Adja meg a használni kívánt hitelesítési tartomány nevét. A hitelesítési tartomány a Pulse Secure kapcsolattípus által használt hitelesítési erőforrások csoportja.


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


## <a name="proxy-settings"></a>Proxybeállítások

- **Proxybeállítások automatikus észlelése** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, adja meg, hogy szeretné-e, ha az eszközök automatikusan észlelnék a kapcsolatbeállításokat. További információt a Windows Server dokumentációjában talál.
- **Automatikus konfigurációs szkript** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Proxykiszolgáló használata** – Ha manuálisan szeretné megadni a proxykiszolgáló beállításait, akkor engedélyezze ezt a beállítást.
    - **Cím** – Adja meg a proxykiszolgáló címét (IP-címként).
    - **Portszám** – Adja meg a proxykiszolgálóhoz társított portszámot.
- **Proxy mellőzése helyi címek esetén** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, ha a megadott helyi címekhez nem szeretné használni a proxykiszolgálót. További információt a Windows Server dokumentációjában talál.
