---
title: A Windows 10 VPN-beállításainak konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: Részletesebben megismerheti a Microsoft Intune elérhető VPN-beállításait, ezek használati módjait és működését, beleértve a forgalomra vonatkozó szabályokat, a feltételes hozzáférést, valamint a Windows 10- és Windows Holographic for Business-eszközök DNS- és proxybeállításait.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 61310f5baa64c43d2e818df6c61a36d232922c1c
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744737"
---
# <a name="windows-10-vpn-settings-in-intune"></a>A Windows 10 VPN-beállításai az Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A VPN-kapcsolatokat az Intune-nal konfigurálhatja. Ez a cikk ezeket a beállításokat, a forgalomra vonatkozó szabályokat, a feltételes hozzáférést, valamint a DNS- és proxybeállításokat ismerteti.

Ezek a beállítások a következőkre vonatkoznak:

- Windows 10 rendszerű eszközök
- Windows Holographic for Business rendszerű eszközök

A kiválasztott beállításoktól függően előfordulhat, hogy nem minden érték konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **Kiszolgálók**: Adjon meg egy vagy több olyan VPN-kiszolgálót, amelyhez az eszközök csatlakozni fognak. Kiszolgáló hozzáadásakor az alábbi információkat adhatja meg:
  - **Leírás**: Adja meg a kiszolgáló leíró nevét (például **Contoso VPN-kiszolgáló**)
  - **IP-cím vagy teljes tartománynév**: Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakoznak, például **192.168.1.1** vagy **vpn.contoso.com**
  - **Alapértelmezett kiszolgáló**: Ezt a kiszolgálót engedélyezi alapértelmezett kiszolgálóként, melyet az eszközök kapcsolat létesítéséhez fognak használni. Csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
  - **Importálás**: Tallózással keressen meg egy, a kiszolgálók vesszővel tagolt listáját tartalmazó fájlt, melynek formátuma a következő: leírás, IP-cím vagy teljes tartománynév, alapértelmezett kiszolgáló. A kiszolgálók a **Kiszolgálók** listába történő importálásához kattintson az **OK** gombra.
  - **Exportálás**: Exportálja a kiszolgálók listáját egy vesszővel tagolt (CSV-) fájlba

- **Kapcsolat típusa**: Az alábbi listából válassza ki a VPN-kapcsolat típusát:

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
    - **Mindig bekapcsolva**: Ezzel a beállítással automatikusan csatlakozik a VPN-kapcsolathoz a következő esetekben: 
      - Felhasználói bejelentkezés az eszközre
      - Hálózatváltozás az eszközön
      - Az eszköz képernyője ismét bekapcsol, miután ki volt kapcsolva 

    - **Hitelesítési módszer**: Adja meg, hogy hogyan szeretné hitelesíteni a felhasználókat a VPN-kiszolgálón. A **tanúsítványok** fejlett funkciókkal szolgálnak, például beavatkozás nélküli működés, igény szerinti VPN és alkalmazásonkénti VPN.
    - **Hitelesítő adatok megjegyzése minden bejelentkezéskor**: Ezzel a beállítással gyorsítótárazhatja a hitelesítő adatokat.
    - **Egyéni XML**: Adja meg a VPN-kapcsolatot konfiguráló egyéni XML-parancsokat.
    - **EAP XML**: Adja meg a VPN-kapcsolatot konfiguráló EAP XML-parancsokat

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

Például:

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

- **WIP vagy alkalmazások társítása ezzel a VPN-nel**: Engedélyezze ezt a beállítást, ha azt szeretné, hogy csak bizonyos használják a VPN-kapcsolatot. A választható lehetőségek:

  - **WIP társítása ezzel a kapcsolattal**: Adjon meg egy **WIP-tartományt ehhez a kapcsolathoz**
  - **Alkalmazások társítása ezzel a kapcsolattal**: **Korlátozhatja a VPN-kapcsolat ezekhez az alkalmazásokhoz**, majd hozzáadhat **társított alkalmazásokat**. A megadott alkalmazások automatikusan a VPN-kapcsolatot használják. Az alkalmazás típusa határozza meg az alkalmazás azonosítóját. Univerzális alkalmazások esetén adja meg a Csomagcsalád nevét. Asztali alkalmazások esetén adja meg az alkalmazás fájlelérési útvonalát.
  >[!IMPORTANT]
  >Azt javasoljuk, hogy tegyen biztonságossá minden, alkalmazásonkénti VPN-ekhez létrehozott alkalmazáslistát. Ha a listát esetleg arra nem jogosult felhasználó módosítja, és Ön így importálja azt az alkalmazásonkénti VPN-alkalmazáslistába, azzal olyan alkalmazásoknak is VPN-elérést nyújthat, amelyeknek eredetileg nem szeretett volna. Az alkalmazáslisták védelmének módja lehet a hozzáférés-vezérlési lista (ACL) létrehozása.

- **A VPN-kapcsolat hálózati forgalmi szabályai**: Állítsa be, hogy a VPN-kapcsolatnál mely protokollok, valamint melyik helyi és távoli portok és címtartományok lesznek engedélyezve. Ha nem hoz létre hálózati forgalmi szabályt, minden protokoll, port és címtartomány engedélyezve lesz. Egy szabály létrehozása után a VPN-kapcsolat csak az Ön által a szabályban megadott protokollokat, portokat és címtartományokat használja.

## <a name="conditional-access"></a>Feltételes hozzáférés

- **Feltételes hozzáférés használata e VPN-kapcsolat esetében**: Lehetővé teszi az ügyféltől származó eszközmegfelelőségi adatok továbbítását. Ha a beállítás engedélyezve van, a VPN-ügyfél megpróbál kommunikálni az Azure Active Directoryval (AD), hogy megszerezze a hitelesítéshez használandó tanúsítványt. A VPN-t tanúsítványalapú hitelesítés használatára kell beállítani, és a VPN-kiszolgálónak megbízhatóként kell felismernie az Azure AD által visszaadott kiszolgálót.

- **Egyszeri bejelentkezés (SSO) helyettesítő tanúsítvánnyal**: A Kerberos-hitelesítéshez használttól eltérő tanúsítvány használata az eszközmegfelelőség igazolásához. A következő beállításokkal rendelkező tanúsítványt adja meg:

  - **Név**: A kibővített kulcshasználat (EKU) neve
  - **Objektumazonosító**: Az EKU objektumazonosítója
  - **Kibocsátó kivonata**: Az SSO-tanúsítvány ujjlenyomata

## <a name="dns-settings"></a>DNS-beállítások

**A VPN-kapcsolat tartománya és kiszolgálói**: Megadhat egy tartományt és DNS-kiszolgálót a VPN-nek. Megadhatja, hogy a kapcsolat létrejötte után a VPN-kapcsolat mely DNS-kiszolgálókat használja. Minden egyes kiszolgálóhoz adja meg az alábbi adatokat:
- **Tartomány**
- **DNS-kiszolgáló**
- **Proxy**

## <a name="proxy-settings"></a>Proxybeállítások

- **Automatikus konfigurációs szkript**: A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét**, például `http://proxy.contoso.com`.
- **Cím**: Adja meg a proxykiszolgáló címét, amely egy IP-cím vagy egy `vpn.contoso.com`
- **Portszám** – Adja meg a proxykiszolgáló TCP-portszámát.
- **Proxy megkerülése helyi címeknél**: Ha nem szeretne proxykiszolgálót használni a helyi címekhez, válassza az Engedélyezés lehetőséget. Ez a beállítás akkor lép érvénybe, ha a VPN-kiszolgálónak proxykiszolgálóra van szüksége a kapcsolathoz.

## <a name="split-tunneling"></a>Vegyes alagútkezelés

- **Bújtatás megosztása**: Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.
- **A VPN-kapcsolat megosztott protokollbújtatási útvonalai**: Választható útvonalak hozzáadása külső VPN-szolgáltatók számára. Minden kapcsolathoz adja meg a célelőtagot és az előtag méretét.
