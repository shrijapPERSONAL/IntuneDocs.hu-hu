---
title: "Az Intune VPN-beállításai Windows Phone 8.1 rendszerű eszközökhöz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk a VPN-kapcsolatoknak a Windows Phone 8.1 rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aff935508551b45ee0a69f907506b0703290fddf
ms.openlocfilehash: abe6fb1a5684cbeb0b893793a1932652b7ec1c16


---

# <a name="vpn-settings-for-windows-phone-81-devices-in-intune-azure-preview"></a>VPN-beállítások Windows Phone 8.1 rendszerű eszközökhöz az Azure-os Intune előzetes verziójában

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A megadott beállításoktól függően az alábbi listában található értékek némelyike nem konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások

- **Apply all settings to Windows Phone 8.1 only** (Az összes beállítás alkalmazása csak a Windows Phone 8.1-re) – Ezt a beállítást a hagyományos Intune-portálon lehet konfigurálni. Az Azure Portalon nem módosítható. Ha ez a beállítás a **Konfigurálva** értékre van állítva, minden beállítást csak a Windows Phone 8.1-eszközökre alkalmaz a rendszer. Ha a **Nincs konfigurálva** értékre van állítva, akkor a Windows 10 Mobile rendszerű eszközökre is alkalmazza rendszer ezeket a beállításokat.
- **Kapcsolat neve** – Nevezze el a kapcsolatot. A végfelhasználók akkor látják ezt a nevet, amikor rendelkezésre álló VPN-kapcsolatokat keresnek az eszközükön.
- **Hitelesítési mód** – Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
    - **Tanúsítványok** – A **Hitelesítési tanúsítvány** szakaszban adja meg a kapcsolat hitelesítéséhez korábban létrehozott SCEP- vagy PKCS-tanúsítványprofilok valamelyikét. A tanúsítványprofilokról [a tanúsítványok konfigurálását](how-to-configure-certificates.md) ismertető cikkben talál részletesebb tájékoztatást.
    - **Felhasználónév és jelszó** – A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha be szeretnének jelentkezni a VPN-kiszolgálóra.
- **Kiszolgálók** – Itt adhat meg egy vagy több olyan VPN-kiszolgálót, amelyhez az eszközök csatlakozni fognak.
    - **Hozzáadás** – Megnyílik a **Sor hozzáadása** panel, ahol a következőket adhatja meg:
        - **Leírás** – Adjon meg egy a kiszolgálót jól jellemző nevet, például **Contoso VPN-kiszolgáló**.
        - **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
        - **Alapértelmezett kiszolgáló** – Ezt a kiszolgálót aktiválja alapértelmezett kiszolgálónként, vele fognak kapcsolatot létesíteni az eszközök. Csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
    - **Importálás** – Tallózással keresse meg a kiszolgálók vesszővel tagolt listáját tartalmazó fájlt (formátuma: leírás, IP-cím vagy teljes tartománynév, alapértelmezett kiszolgáló). Indítsa el ezeknek a **Kiszolgálók** listába való importálását az **OK** gombra kattintva.
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

- **Bújtatás megosztása**  -  Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a VPN-kapcsolatot használja a munkahelyi fájlok elérésére, de egyszerű böngészésre a szálloda normál hálózatát.




## <a name="proxy-settings"></a>Proxybeállítások

- **Proxybeállítások automatikus észlelése** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, adja meg, hogy szeretné-e, ha az eszközök automatikusan észlelnék a kapcsolatbeállításokat. További információt a Windows Server dokumentációjában talál.
- **Automatikus konfigurációs szkript** – Fájl segítségével konfigurálhatja a proxykiszolgálót. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Proxykiszolgáló használata** – Akkor engedélyezze ezt a beállítást, ha manuálisan szeretné megadni a proxykiszolgáló beállításait.
    - **Cím** – Adja meg a proxykiszolgáló címét (IP-címként).
    - **Portszám** – Adja meg a proxykiszolgálóhoz társított portszámot.
- **Proxy mellőzése helyi címek esetén** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, ha az Ön által megadott helyi címekhez nem szeretné használni a proxykiszolgálót. További információt a Windows Server dokumentációjában talál.



<!--HONumber=Feb17_HO1-->

