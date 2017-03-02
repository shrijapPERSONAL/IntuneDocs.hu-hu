---
title: "VPN-beállítások Windows 10-es eszközökhöz az Intune-ban | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A VPN-kapcsolatok a Windows 10-es eszközökön való konfigurálásához használható Intune-beállítások ismertetése."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 7f09fa9bb8a9817aaad40c6452cff2a866a926d9
ms.lasthandoff: 02/16/2017


---

# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Windows 10-es eszközökre vonatkozó VPN-beállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

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
- **Pulse Secure**
- **F5 Edge Client**
- **Dell SonicWALL Mobile Connect**
- **Check Point Capsule VPN**
- **Automatikus**
- **IKEv2**
- **L2TP**
- **PPTP**

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

**Feltételes hozzáférés használata e VPN-kapcsolat esetében** -
** Egyszeri bejelentkezés (SSO) helyettesítő tanúsítvánnyal** -
**Kibővített kulcshasználat** -
**Kibocsátó kivonata** -

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

