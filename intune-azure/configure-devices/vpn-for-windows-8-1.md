---
title: "Az Intune VPN-beállításai Windows 8.1 rendszerű eszközökhöz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk a VPN-kapcsolatoknak a Windows 8.1 rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aff935508551b45ee0a69f907506b0703290fddf
ms.openlocfilehash: 31a7779537062a63fac1fb512a7cf4b9033368f7


---

# <a name="vpn-settings-for-windows-81-devices-in-intune-azure-preview"></a>VPN-beállítások Windows 8.1 rendszerű eszközökhöz az Intune az Azure-on előzetes verziójában

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A megadott beállításoktól függően az alábbi listában található értékek némelyike nem konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások


- **Az összes beállítás alkalmazása csak a Windows Phone 8.1-re** – Ezt a beállítást a hagyományos Intune-portálon lehet konfigurálni. Ez a beállítás az Azure Portalon nem módosítható. Ha ez a beállítás a **Konfigurálva** értékre van állítva, minden beállítást csak a Windows 8.1-eszközökre alkalmaz a rendszer. Ha a **Nincs konfigurálva** értékre van állítva, akkor a Windows 10 rendszerű eszközökre is alkalmazza rendszer ezeket a beállításokat.
- **Kapcsolat neve** – Nevezze el a kapcsolatot. A végfelhasználók akkor látják ezt a nevet, amikor rendelkezésre álló VPN-kapcsolatokat keresnek az eszközükön.
- **Kiszolgálók** – Itt adhat meg egy vagy több olyan VPN-kiszolgálót, amelyhez az eszközök csatlakozni fognak.
    - **Hozzáadás** – Megnyílik a **Sor hozzáadása** panel, ahol a következőket adhatja meg:
        - **Leírás** – Adjon meg egy a kiszolgálót jól jellemző nevet, például **Contoso VPN-kiszolgáló**.
        - **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
        - **Alapértelmezett kiszolgáló** – Ezt a kiszolgálót aktiválja alapértelmezett kiszolgálónként, ezzel fognak kapcsolatot létesíteni az eszközök. Csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
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
- **Automatikus konfigurációs szkript** – Fájl segítségével konfigurálhatja a proxykiszolgálót. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Proxykiszolgáló használata** – Akkor engedélyezze ezt a beállítást, ha manuálisan szeretné megadni a proxykiszolgáló beállításait.
    - **Cím** – Adja meg a proxykiszolgáló címét (IP-címként).
    - **Portszám** – Adja meg a proxykiszolgálóhoz társított portszámot.
- **Proxy mellőzése helyi címek esetén** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, ha az Ön által megadott helyi címekhez nem szeretné használni a proxykiszolgálót. További információt a Windows Server dokumentációjában talál.



<!--HONumber=Feb17_HO1-->


