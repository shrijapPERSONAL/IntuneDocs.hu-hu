---
title: "A VPN-beállítások megtekintése a Microsoft Intune-ban – Azure | Microsoft Docs"
description: "Részletesebben megismerheti a Microsoft Intune elérhető VPN-beállításait, ezek használati módjait és működését, beleértve a forgalomra vonatkozó szabályokat, a feltételes hozzáférést, valamint a Windows 10- és Windows Holographic for Business-eszközök DNS- és proxybeállításait."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 1c1ed2946782f92313aacec05a65a80b2704ddaa
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2018
---
# <a name="read-about-the-vpn-settings-in-intune"></a>Információ az Intune VPN-beállításairól

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A VPN-kapcsolatokat az Intune-nal konfigurálhatja. Ez a cikk ezeket a beállításokat, a forgalomra vonatkozó szabályokat, a feltételes hozzáférést, valamint a DNS- és proxybeállításokat ismerteti.

Ezek a beállítások a következőkre vonatkoznak:

- Windows 10 rendszerű eszközök
- Windows Holographic for Business rendszerű eszközök

A kiválasztott beállításoktól függően előfordulhat, hogy nem minden érték konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **Kiszolgálók**: Adjon meg egy vagy több olyan VPN-kiszolgálót, amelyhez az eszközök csatlakozni fognak.
  - **Hozzáadás**: Megnyitja a **Sor hozzáadása** panelt, ahol az alábbi információkat adhatja meg:
    - **Leírás**: Adja meg a kiszolgáló leíró nevét (például **Contoso VPN-kiszolgáló**)
    - **IP-cím vagy teljes tartománynév**: Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét, amelyhez az eszközök csatlakoznak, például **192.168.1.1** vagy **vpn.contoso.com**
    - **Alapértelmezett kiszolgáló**: Ezt a kiszolgálót engedélyezi alapértelmezett kiszolgálóként, melyet az eszközök kapcsolat létesítéséhez fognak használni. Csak egy kiszolgálót állítson be alapértelmezett kiszolgálóként.
  - **Importálás**: Tallózással keressen meg egy, a kiszolgálók vesszővel tagolt listáját tartalmazó fájlt, melynek formátuma a következő: leírás, IP-cím vagy teljes tartománynév, alapértelmezett kiszolgáló. Az **OK** gombra kattintva indíthatja el a kiszolgálók importálását a **Kiszolgálók** listába.
  - **Exportálás**: Exportálja a kiszolgálók listáját egy vesszővel tagolt (CSV-) fájlba

**Kapcsolat típusa**: Az alábbi listából válassza ki a VPN-kapcsolat típusát:

- **Automatikus**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Bejelentkezési csoport vagy tartomány** (csak SonicWALL Mobile Connect esetén): Ez a tulajdonság nem állítható be a VPN-profilban. Ehelyett a Mobile Connect akkor elemzi ezt az értéket, ha a felhasználónév és a tartomány `username@domain` vagy `DOMAIN\username` formátumban van megadva.

**Egyéni XML**/**EAP XML**: Adja meg a VPN-kapcsolatot konfiguráló egyéni XML-parancsokat.

**Példa a Pulse Secure esetére:**

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Példa a CheckPoint Mobile VPN esetére:**

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Példa a SonicWALL Mobile Connect esetére:**

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Példa az F5 Edge Client esetére:**

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Az egyéni XML-parancsok írásával kapcsolatban további információt az egyes gyártók VPN-dokumentációjában talál.

További információ az egyéni EAP XML-ek létrehozásáról: [EAP-konfiguráció](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

**Bújtatás megosztása**: Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.
- **A VPN-kapcsolat megosztott protokollbújtatási útvonalai**: Választható útvonalak hozzáadása külső VPN-szolgáltatók számára. Mindhez adja meg a célelőtagot és az előtag méretét.

## <a name="apps-and-traffic-rules"></a>Alkalmazások és adatforgalmi szabályok

**A VPN-kapcsolat ezekre az alkalmazásokra korlátozódjon**: Engedélyezze ezt a beállítást, ha azt szeretné, hogy csak bizonyos használják a VPN-kapcsolatot.
**Társított alkalmazások**: Adja meg a VPN-kapcsolatot automatikusan használó alkalmazások listáját. Az alkalmazás típusa határozza meg az alkalmazás azonosítóját. Univerzális alkalmazások esetén adja meg a Csomagcsalád nevét. Asztali alkalmazások esetén adja meg az alkalmazás fájlelérési útvonalát.

>[!IMPORTANT]
>Azt javasoljuk, hogy tegyen biztonságossá minden, alkalmazásonkénti VPN-ekhez létrehozott alkalmazáslistát. Ha a listát esetleg arra nem jogosult felhasználó módosítja, és Ön így importálja azt az alkalmazásonkénti VPN-alkalmazáslistába, azzal olyan alkalmazásoknak is VPN-elérést nyújthat, amelyeknek eredetileg nem szeretett volna. Az alkalmazáslisták védelmének módja lehet a hozzáférés-vezérlési lista (ACL) létrehozása.

**A VPN-kapcsolat hálózati forgalmi szabályai**: Állítsa be, hogy a VPN-kapcsolatnál mely protokollok, valamint melyik helyi és távoli portok és címtartományok lesznek engedélyezve. Ha nem hoz létre hálózati forgalmi szabályt, minden protokoll, port és címtartomány engedélyezve lesz. Egy szabály létrehozása után a VPN-kapcsolat csak az Ön által a szabályban megadott protokollokat, portokat és címtartományokat használja.

## <a name="conditional-access"></a>Feltételes hozzáférés

**Feltételes hozzáférés használata e VPN-kapcsolat esetében**: Lehetővé teszi az ügyféltől származó eszközmegfelelőségi adatok továbbítását. Ha a beállítás engedélyezve van, a VPN-ügyfél megpróbál kommunikálni az Azure Active Directoryval, hogy megszerezze a hitelesítéshez használandó tanúsítványt. A VPN-t tanúsítványalapú hitelesítés használatára kell beállítani, és a VPN-kiszolgálónak megbízhatóként kell felismernie az Azure Active Directory által visszaadott kiszolgálót.

**Egyszeri bejelentkezés (SSO) helyettesítő tanúsítvánnyal**: A Kerberos-hitelesítéshez használttól eltérő tanúsítvány használata az eszközmegfelelőség igazolásához. A következő beállításokkal rendelkező tanúsítványt adja meg:

- **Kibővített kulcshasználat**: A kibővített kulcshasználat (EKU) megnevezése
- **Objektumazonosító**: Az EKU objektumazonosítója
- **Kibocsátó kivonata**: Az SSO-tanúsítvány ujjlenyomata

## <a name="dns-settings"></a>DNS-beállítások

**A VPN-kapcsolat DNS-nevei és -kiszolgálói**: A VPN-kapcsolat által a kapcsolat létrejötte után használt DNS-kiszolgálók megadása.
Minden egyes kiszolgálóhoz adja meg az alábbi adatokat:
- **DNS-név**
- **DNS-kiszolgáló**
- **Proxy**

## <a name="proxy-settings"></a>Proxybeállítások

- **Proxybeállítások automatikus észlelése**: Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, adja meg, hogy szeretné-e, ha az eszközök automatikusan észlelnék a kapcsolatbeállításokat.
- **Automatikus konfigurációs szkript**: A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét**, például `http://proxy.contoso.com`.
- **Proxykiszolgáló használata**: Ha manuálisan szeretné megadni a proxykiszolgáló beállításait, akkor engedélyezze ezt a beállítást.
  - **Cím**: Adja meg a proxykiszolgáló címét (IP-címként)
  - **Portszám**: Adja meg a proxykiszolgálóhoz társított portszámot
- **Proxy mellőzése helyi címek esetén**: Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, ha a megadott helyi címekhez nem szeretné használni a proxykiszolgálót.
