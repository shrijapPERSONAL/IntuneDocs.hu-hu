---
title: "VPN-beállítások az Intune-ban Windows 10-es eszközök esetén"
titlesuffix: Azure portal
description: "Útmutató a VPN-kapcsolatok Windows 10-eszközökön való konfigurálásához használható Intune-beállításokhoz."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 54ff681c96dc01587cd9a2770dacc5bb9a54d134
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2017
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Windows 10-es eszközökre vonatkozó VPN-beállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A megadott beállításoktól függően az alábbi listában található értékek némelyike nem konfigurálható.


## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások


- **Kapcsolat neve** – Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **Kiszolgálók** – Adjon meg egy vagy több olyan VPN-kiszolgálót, amelyhez az eszközök csatlakozni fognak.
    - **Hozzáadás** – Megnyitja a **Sor hozzáadása** panelt, melyen a következőket adhatja meg:
        - **Leírás** – Adja meg a kiszolgáló leíró nevét (például **Contoso VPN-kiszolgáló**).
        - **IP-cím vagy teljes tartománynév** – Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.
        - **Alapértelmezett kiszolgáló** – Ezt a kiszolgálót engedélyezi alapértelmezett kiszolgálóként, melyet az eszközök kapcsolat létesítéséhez fognak használni. Mindenképpen csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
    - **Importálás** – Tallózással keressen meg egy, a kiszolgálók vesszővel tagolt listáját tartalmazó fájlt, melynek formátuma a következő: leírás, IP-cím vagy teljes tartománynév, alapértelmezett kiszolgáló. Az **OK** gombra kattintva indíthatja el ezek importálását a **Kiszolgálók** listába.
    - **Exportálás** – Exportálja a kiszolgálók listáját egy vesszővel tagolt (CSV-) fájlba.

**Kapcsolat típusa** – Az szállítók alábbi listájából válassza ki a VPN-kapcsolat típusát:
- **Automatikus**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**


**Bejelentkezési csoport vagy tartomány** (csak Dell SonicWALL Mobile Connect esetén) – Adja meg annak a bejelentkezési csoportnak vagy tartománynak a nevét, amelyhez csatlakozni szeretne.

**Egyéni XML**/**EAP XML** – Itt a VPN-kapcsolatot konfiguráló egyéni XML-parancsokat adhat meg.

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

**Bújtatás megosztása**  -  Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a VPN-kapcsolatot használja a munkahelyi fájlok elérésére, de egyszerű böngészésre a szálloda normál hálózatát.
- **A VPN-kapcsolat megosztott protokollbújtatási útvonalai** – Választható útvonalak hozzáadása külső VPN-szolgáltatók számára. Mindhez adja meg a célelőtagot és az előtag méretét.

## <a name="apps-and-traffic-rules"></a>Alkalmazások és adatforgalmi szabályok

**A VPN-kapcsolat ezekre az alkalmazásokra korlátozódjon** – Engedélyezze ezt a beállítást, ha azt szeretné, hogy csak a megadott alkalmazások használják a VPN-kapcsolatot.
**Társított alkalmazások** – Megadhatja a VPN-kapcsolatot automatikusan használó alkalmazások listáját. Az alkalmazás típusa határozza meg az alkalmazás azonosítóját. Univerzális alkalmazások esetén adja meg a Csomagcsalád nevét. Asztali alkalmazások esetén adja meg az alkalmazás fájlelérési útvonalát.

>[!IMPORTANT]
>Javasoljuk, hogy az alkalmazásonkénti VPN-konfigurációban való használat céljából összeállított alkalmazáslistákat mindig lássa el védelemmel. Ha a listát esetleg arra nem jogosult felhasználó módosítja, és Ön így importálja azt az alkalmazásonkénti VPN-alkalmazáslistába, azzal olyan alkalmazásoknak is VPN-elérést nyújthat, amelyeknek eredetileg nem szeretett volna. Az alkalmazáslisták védelmének módja lehet a hozzáférés-vezérlési lista (ACL) létrehozása.

**A VPN-kapcsolat hálózati forgalmi szabályai** – Beállíthatja, hogy a VPN-kapcsolatnál mely protokollok, valamint melyik helyi és távoli portok és címtartományok lesznek engedélyezve. Ha nem hoz létre hálózati forgalmi szabályt, minden protokoll, port és címtartomány engedélyezve lesz. Ha létrehoz egy szabályt, a VPN-kapcsolat csak az Ön által a szabályban megadott protokollokat, portokat és címtartományokat fogja használni.


## <a name="conditional-access"></a>Feltételes hozzáférés

**Feltételes hozzáférés használata e VPN-kapcsolat esetében** – Lehetővé teszi az ügyféltől származó eszközmegfelelőségi adatok továbbítását. Ha a beállítás engedélyezve van, a VPN-ügyfél megpróbál kommunikálni az Azure Active Directoryval, hogy megszerezze a hitelesítéshez használandó tanúsítványt. A VPN-t tanúsítványalapú hitelesítés használatára kell beállítani, és a VPN-kiszolgálónak megbízhatóként kell felismernie az Azure Active Directory által visszaadott kiszolgálót.

**Egyszeri bejelentkezés (SSO) helyettesítő tanúsítvánnyal** – A Kerberos-hitelesítéshez használttól eltérő tanúsítvány használata az eszközmegfelelőség igazolásához. A tanúsítványhoz a következő beállításokat adja meg: 

- **Kibővített kulcshasználat** – A kibővített kulcshasználat (EKU) megnevezése.
- **Objektumazonosító** – Az EKU objektumazonosítója.
- **Kibocsátó kivonata** – Az SSO-tanúsítvány ujjlenyomata.

## <a name="dns-settings"></a>DNS-beállítások

**A VPN-kapcsolat DNS-nevei és -kiszolgálói** – A VPN-kapcsolat által a kapcsolat létrejötte után használt DNS-kiszolgálók megadása.
Minden egyes kiszolgáló esetén. adja meg a következőket:
- **DNS-név**
- **DNS-kiszolgáló**
- **Proxy**

## <a name="proxy-settings"></a>Proxybeállítások

- **Proxybeállítások automatikus észlelése** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, adja meg, hogy szeretné-e, ha az eszközök automatikusan észlelnék a kapcsolatbeállításokat. További információt a Windows Server dokumentációjában talál.
- **Automatikus konfigurációs szkript** – A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Proxykiszolgáló használata** – Ha manuálisan szeretné megadni a proxykiszolgáló beállításait, akkor engedélyezze ezt a beállítást.
    - **Cím** – Adja meg a proxykiszolgáló címét (IP-címként).
    - **Portszám** – Adja meg a proxykiszolgálóhoz társított portszámot.
- **Proxy mellőzése helyi címek esetén** – Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, ha a megadott helyi címekhez nem szeretné használni a proxykiszolgálót. További információt a Windows Server dokumentációjában talál.
