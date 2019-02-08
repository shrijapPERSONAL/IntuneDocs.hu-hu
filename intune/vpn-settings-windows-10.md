---
title: A Windows 10-es VPN-beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Ismerje meg, és olvassa el a rendelkezésre álló VPN beállításai a Microsoft Intune-ban, hogy mire szolgálnak a, és mit tesznek, például forgalomra vonatkozó szabályokat, a feltételes hozzáférés és az eszközök a Windows 10 és Windows Holographic for Business DNS és a proxykiszolgáló beállításait.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: tycast
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e38d5e68e79facfd270de64c79708b74aa460189
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838189"
---
# <a name="windows-10-and-windows-holographic-device-settings-to-add-vpn-connections-using-intune"></a>Eszközbeállítások Windows 10 és Windows Holographic hozzáadása az Intune-nal VPN-kapcsolatok

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Adja hozzá, és konfigurálja a VPN-kapcsolatok a Microsoft Intune használatával. Ez a cikk és a gyakran használt beállításokat és funkciókat ismerteti, amikor létrehozza a virtuális magánhálózatok (VPN). E VPN-beállítások és funkciók az Intune-ban, amelyek leküldött vagy eszközökre telepített eszközkonfigurációs profilok használatban vannak. 

A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat engedélyezi vagy letiltja a funkciókat, például egy VPN-szolgáltató használatával, így mindig a, DNS-sel, proxy, és további.

Ezek a beállítások futó eszközökre vonatkoznak:

- Windows 10
- Windows Holographic for Business

A kiválasztott beállításoktól függően előfordulhat, hogy nem minden érték konfigurálható.

## <a name="before-you-begin"></a>Előkészületek

[Hozzon létre egy VPN-eszköz konfigurációs profil](vpn-settings-configure.md).

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **Kiszolgálók**: Adjon hozzá egy vagy több olyan VPN-kiszolgálót, amely az eszközök csatlakoznak. Kiszolgáló hozzáadásakor az alábbi információkat adhatja meg:
  - **Description** (Leírás): Adja meg egy leíró nevet a kiszolgáló esetében például **Contoso VPN-kiszolgáló**
  - **IP-cím vagy FQDN**: Adja meg az IP-címét vagy teljesen minősített tartománynevét (FQDN), amely az eszközök csatlakoznak, például a VPN-kiszolgáló **192.168.1.1** vagy **vpn.contoso.com**
  - **Alapértelmezett kiszolgáló**: Ezt a kiszolgálót engedélyezi alapértelmezett kiszolgálóként, melyet az eszközök kapcsolat létesítéséhez fognak használni. Csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
  - **Importálás**: Keresse meg egy vesszővel tagolt fájlt, amely tartalmazza a kiszolgálók listáját a következő formátumban: leírás, IP-cím vagy teljes tartománynév, alapértelmezett kiszolgáló. A kiszolgálók a **Kiszolgálók** listába történő importálásához kattintson az **OK** gombra.
  - **Exportálás**: Exportálja a kiszolgálók listáját egy vesszővel tagolt (csv) fájl

- **Regisztráció IP-címek belső DNS-ben**: Válassza ki **engedélyezése** a Windows 10-es VPN-profil dinamikusan regisztrálja a VPN-interfészhez a belső DNS-ben rendelt IP-címek konfigurálásához. Ha a **Tiltás** lehetőséget választja, akkor az IP-címek nem lesznek dinamikusan regisztrálva.

- **Kapcsolat típusa**: A szállítók az alábbi listából válassza ki a VPN-kapcsolat típusa:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWall Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Palo Alto Hálózatok GlobalProtect**
  - **Automatikus**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  Amikor kiválasztja a VPN-kapcsolat típusát, előfordulhat, hogy az alábbi beállításokat is meg kell adnia:  
    - **Always On**: Válasszon **engedélyezése** való automatikus csatlakozás a VPN-kapcsolat a következő események bekövetkezése esetén: 
      - Felhasználói bejelentkezés az eszközre
      - Hálózatváltozás az eszközön
      - Az eszköz képernyője ismét bekapcsol, miután ki volt kapcsolva 

    - **Hitelesítési módszer**: Válassza ki, hogyan felhasználók hitelesíthetik magukat a VPN-kiszolgáló. A **tanúsítványok** fejlett funkciókkal szolgálnak, például beavatkozás nélküli működés, igény szerinti VPN és alkalmazásonkénti VPN.
    - **Hitelesítő adatok megjegyzése minden bejelentkezéskor**: Válassza ki a hitelesítő adatok gyorsítótárazásához.
    - **Egyéni XML**: Adja meg a VPN-kapcsolatot konfiguráló egyéni XML-parancsokat.
    - **Az EAP Xml**: Adjon meg bármilyen EAP XML-parancsokat, amelyek a VPN-kapcsolat konfigurálása

#### <a name="pulse-secure-example"></a>Pulse Secure-példa

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### <a name="f5-edge-client-example"></a>F5 Edge Client-példa

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### <a name="sonicwall-mobile-connect-example"></a>SonicWall Mobile Connect-példa
**Bejelentkezési csoport vagy tartomány**: Ez a tulajdonság nem állítható be a VPN-profilban. Ehelyett a Mobile Connect akkor elemzi ezt az értéket, ha a felhasználónév és a tartomány `username@domain` vagy `DOMAIN\username` formátumban van megadva.

Példa:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

#### <a name="checkpoint-mobile-vpn-example"></a>CheckPoint Mobile VPN-példa

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

#### <a name="writing-custom-xml"></a>Egyéni XML írása
Az egyéni XML-parancsok írásával kapcsolatban további információt az egyes gyártók VPN-dokumentációjában talál.

További információ az egyéni EAP XML-ek létrehozásáról: [EAP-konfiguráció](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

## <a name="apps-and-traffic-rules"></a>Alkalmazások és adatforgalmi szabályok

- **WIP vagy alkalmazások társítása a VPN-t**: Engedélyezze ezt a beállítást, ha csak néhány alkalmazás VPN-kapcsolatot használjon. A választható lehetőségek:

  - **WIP társítása ehhez a kapcsolathoz**: Enter a **WIP domain for this connection**
  - **Alkalmazások társítása ehhez a kapcsolathoz**: Is **korlátozása VPN-kapcsolat ezekre az alkalmazásokra**, majd adja hozzá **társított alkalmazások**. A megadott alkalmazások automatikusan a VPN-kapcsolatot használják. Az alkalmazás típusa határozza meg az alkalmazás azonosítóját. Univerzális alkalmazások esetén adja meg a Csomagcsalád nevét. Asztali alkalmazások esetén adja meg az alkalmazás fájlelérési útvonalát.
  >[!IMPORTANT]
  >Azt javasoljuk, hogy tegyen biztonságossá minden, alkalmazásonkénti VPN-ekhez létrehozott alkalmazáslistát. Ha a listát esetleg arra nem jogosult felhasználó módosítja, és Ön így importálja azt az alkalmazásonkénti VPN-alkalmazáslistába, azzal olyan alkalmazásoknak is VPN-elérést nyújthat, amelyeknek eredetileg nem szeretett volna. Az alkalmazáslisták védelmének módja lehet a hozzáférés-vezérlési lista (ACL) létrehozása.

- **Hálózati forgalmi szabályai a VPN-kapcsolat**: Akkor válassza ki a VPN-kapcsolat engedélyezve vannak a protokollokat, és melyik helyi és távoli portok és címtartományok. Ha nem hoz létre hálózati forgalmi szabályt, minden protokoll, port és címtartomány engedélyezve lesz. Egy szabály létrehozása után a VPN-kapcsolat csak az Ön által a szabályban megadott protokollokat, portokat és címtartományokat használja.

## <a name="conditional-access"></a>Feltételes hozzáférés

- **Feltételes hozzáférés használata e VPN-kapcsolat esetében**: Lehetővé teszi az ügyféltől származó eszközmegfelelőségi adatok. Ha a beállítás engedélyezve van, a VPN-ügyfél kommunikál az Azure Active Directoryval (AD), hogy megszerezze a hitelesítéshez használandó tanúsítványt. A VPN-t tanúsítványalapú hitelesítés használatára kell beállítani, és a VPN-kiszolgálónak megbízhatóként kell felismernie az Azure AD által visszaadott kiszolgálót.

- **Egyszeri bejelentkezés (SSO) helyettesítő tanúsítvánnyal**: Eszközmegfelelőség használja a VPN-hitelesítési tanúsítvány eltérő Kerberos-hitelesítéshez. A következő beállításokkal rendelkező tanúsítványt adja meg:

  - **Név**: A kibővített kulcshasználat (EKU) neve
  - **Object Identifier**: Az EKU Objektumazonosítója
  - **Kibocsátó kivonata**: Az SSO-tanúsítvány ujjlenyomata

## <a name="dns-settings"></a>DNS-beállítások

- **DNS-utótagkeresési lista**: A **DNS-utótagok**, DNS-utótag megadása, és **Hozzáadás**. Számos utótagok adhat hozzá.

  A DNS-utótagok használatakor a rendszer a hálózati erőforrások rövid nevére keres rá a teljes tartománynév (FQDN) helyett. A rövid névvel történő kereséskor az utótagot automatikusan meghatározza a DNS-kiszolgáló. A `utah.contoso.com` például szerepel a DNS-utótagok listájában. Ön pingeli a következőt: `DEV-comp`. Ebben a forgatókönyvben ez a következőt eredményezi: `DEV-comp.utah.contoso.com`.

  A DNS-utótagok a megadott sorrendben oldódnak fel, amely módosítható. Például a `colorado.contoso.com` és a `utah.contoso.com` is szerepel a DNS-utótagok listájában, és mindkettő rendelkezik `DEV-comp` erőforrással. Mivel a `colorado.contoso.com` az első a listában, ez a következőképp oldódik fel: `DEV-comp.colorado.contoso.com`.
  
  A sorrend módosításához kattintson a DNS-utótag bal oldalán található pontokra, majd húzza az utótagot felülre:

  ![Válassza ki a három pontot, majd húzással helyezze át a DNS-utótagot](./media/vpn-settings-windows10-move-dns-suffix.png)

- **Neve a névfeloldási házirend táblája (NRPT) szabályok**: Név névfeloldási házirend táblája (NRPT) szabályai határozzák meg, hogyan oldja fel a DNS neve, ha a VPN-Kapcsolatot létesített. A VPN-kapcsolat létrejötte után válassza ki a VPN-kapcsolat DNS-kiszolgálók.

  A tábla, amely tartalmazza a tartományhoz, a DNS kiszolgáló, proxy és egyéb részletek feloldásához, adja meg a tartomány szabályokat adhat hozzá. A VPN-kapcsolatot használja ezeket a szabályokat, ha felhasználók csatlakoznak a tartományok, adja meg.

  Válassza ki **Hozzáadás** egy új szabály hozzáadásához. Minden egyes kiszolgálóhoz adja meg az alábbi adatokat:

  - **Tartomány**: Adja meg a teljesen minősített tartománynevét (FQDN) vagy egy DNS-utótagot, hogy alkalmazza a szabályt. A DNS-utótag elején is megadhat egy pontot (.). Például írja be a következőt: `contoso.com` vagy `.allcontososubdomains.com`.
  - **DNS-kiszolgálók**: Adja meg az IP-cím vagy oldja fel a tartomány DNS-kiszolgálót. Például írja be a következőt: `10.0.0.3` vagy `vpn.contoso.com`.
  - **Proxy**: Adja meg a proxy-webkiszolgáló, amely megszünteti a tartományhoz. Például írja be a következőt: `http://proxy.com`.
  - **Automatikus csatlakozás**: Amikor **engedélyezve**, az eszköz automatikusan csatlakozik a VPN-t, amikor egy eszköz csatlakozik a tartományhoz, akkor adja meg, például: `contoso.com`. Amikor **nincs konfigurálva** (alapértelmezett), az eszköz nem automatikusan csatlakoznak a VPN-hez
  - **Állandó**: Ha a beállítása **engedélyezve**, a szabály a névfeloldási házirend táblája (NRPT) marad, amíg a szabályt kézzel el van távolítva az eszközről, még akkor is, a VPN után bontja a kapcsolatot. Ha a beállítása **nincs konfigurálva** (alapértelmezett), a VPN-profil az NRPT-szabályok törlődnek az eszközről, ha bontja a kapcsolatot a VPN-t.

## <a name="proxy-settings"></a>Proxybeállítások

- **Automatikus konfigurációs szkript**: Egy fájl segítségével konfigurálhatja a proxykiszolgálót. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét**, például `http://proxy.contoso.com`.
- **Cím**: Adja meg a proxykiszolgáló címét, például az IP-címet, vagy `vpn.contoso.com`
- **Portszám**: Adja meg a proxykiszolgáló által használt TCP-port száma
- **Proxy mellőzése helyi címek**: Ha nem szeretné használni a proxykiszolgálót helyi címek esetén, majd válassza ki a engedélyezése. Ez a beállítás akkor lép érvénybe, ha a VPN-kiszolgálónak proxykiszolgálóra van szüksége a kapcsolathoz.

## <a name="split-tunneling"></a>Vegyes alagútkezelés

- **Vegyes Alagútkezelés**: **Engedélyezése** vagy **letiltása** , hogy az eszközök választhatnak-e a forgalomtól függően. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.
- **Megosztott protokollbújtatási útvonalai a VPN-kapcsolat**: Választható útvonalak hozzáadása külső VPN-szolgáltatók. Minden kapcsolathoz adja meg a célelőtagot és az előtag méretét.

## <a name="trusted-network-detection"></a>Megbízható hálózatok észlelése

**Megbízható hálózat DNS-utótagok**: Amikor a felhasználók már megbízható hálózathoz csatlakoznak, megakadályozhatja a eszközök automatikusan csatlakozzanak a más VPN-kapcsolatok.

A **DNS-utótagok**, megbízható, például a contoso.com, és válassza ki a kívánt DNS-utótag megadása **Hozzáadás**. A kívánt számú utótagok adhat hozzá.

Ha egy felhasználó csatlakozik egy DNS-utótagot a listában, majd a felhasználó nem fog automatikusan csatlakozni egy másik VPN-kapcsolat. A felhasználó továbbra is használja, adja meg a DNS-utótagokat megbízható listáját. A megbízható hálózatok továbbra is használni, még akkor is, ha bármely autotriggers vannak beállítva.

Például ha a felhasználó már csatlakozik egy megbízható DNS-utótagot, majd a következő autotriggers figyelmen kívül hagyja. Pontosabban a DNS-utótagokat a listában visszavonása minden egyéb kapcsolati autotriggers, beleértve:

- Always on
- Alkalmazás-alapú eseményindító
- DNS-autotrigger

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Ezután [rendelje hozzá a profilt](device-profile-assign.md), és [állapotát nyomon](device-profile-monitor.md).

VPN-beállítások konfigurálása a [Android](vpn-settings-android.md), [iOS](vpn-settings-ios.md), és [macOS](vpn-settings-macos.md) eszközök.
