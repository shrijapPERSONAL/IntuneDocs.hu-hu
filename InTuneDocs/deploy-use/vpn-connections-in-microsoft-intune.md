---
title: VPN-kapcsolatok | Microsoft Docs
description: "A VPN-profilok beállításával a szervezetében lévő felhasználókra és eszközökre alkalmazhatja a VPN-beállításokat."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0154e3bfeac0457de57257045e3e7ce833325bce
ms.openlocfilehash: a462bcfa107bf1a37ea4e84bc3d88d0dd81f9fc8
ms.lasthandoff: 02/03/2017


---

# <a name="vpn-connections-in-microsoft-intune"></a>VPN-kapcsolatok a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A virtuális magánhálózatok (VPN) segítségével biztonságos távoli hozzáférést biztosíthat felhasználóinak a vállalati hálózathoz. Az eszközök egy *VPN-csatlakozási profil* használatával kezdeményeznek kapcsolatot a VPN-kiszolgálóval. A Microsoft Intune *VPN-profiljainak* beállításával a szervezet felhasználóira és eszközeire alkalmazhatja a VPN-beállításokat, így könnyedén és biztonságosan kapcsolódhatnak a hálózathoz.

Tegyük fel például, hogy minden iOS-eszközön alkalmazni szeretné azokat a beállításokat, amelyek a vállalati hálózaton lévő egyik fájlmegosztáshoz való csatlakozáshoz szükségesek. Ehhez létre kell hoznia egy, a vállalati hálózathoz való csatlakozáshoz szükséges beállításokat tartalmazó VPN-profilt, majd ezt a profilt minden iOS-eszközt használó felhasználóra alkalmaznia kell. A felhasználók látni fogják a VPN-kapcsolatot a rendelkezésre álló hálózatok listájában, és könnyen csatlakozhatnak.

VPN-profilokkal a következő típusú eszközök konfigurálhatók:

* Android 4 vagy újabb rendszerű eszközök
* Android for Work-eszközök
* iOS 8.0 vagy újabb rendszerű eszközök
* A Mac OS X 10.9-es vagy újabb rendszerű eszközök
* A Windows 8.1-es vagy újabb verzióját futtató regisztrált eszközök
* A Windows Phone 8.1-es vagy újabb verzióját futtató eszközök
* A Windows 10 asztali és mobilverzióját futtató eszközök

A VPN-profil konfigurációs beállításai a kiválasztott eszköztípustól függően eltérhetnek.

## <a name="vpn-connection-types"></a>VPN-kapcsolat típusai

Az Intune a következő kapcsolattípusokat használó VPN-profilok létrehozását támogatja:


Kapcsolat típusa |iOS és Mac OS X  |Android és Android for Work|Windows 8.1|Windows RT 8.1|Windows Phone 8.1|A Windows 10 asztali és mobilverziója |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Igen |Igen   |Nem    |Nem  |Nem    | Igen (OMA-URI, csak mobil)|     
Cisco (IPsec)|Igen |Igen   |Nem  |Nem  |Nem | Nem|
Citrix|Igen |Igen (csak Android esetén)   |Nem  |Nem  |Nem | Nem|
Pulse Secure|Igen  |Igen |Igen   |Igen  |Igen| Igen|        
F5 Edge Client|Igen |Igen |Igen |Igen  |   Igen |  Igen|   
Dell SonicWALL Mobile Connect|Igen |Igen |Igen |Igen |Igen |Igen|         
CheckPoint Mobile VPN|Igen |Igen |Igen |Igen|Igen|Igen|
Microsoft SSL (SSTP)|Nem |Nem |Nem |Nem|Nem|VPNv1 OMA-URI *|
Microsoft Automatic|Nem |Nem |Nem |Nem|Igen (OMA-URI)|Igen|
IKEv2|iOS-eszközök egyéni profilja|Nem |Nem |Nem|Igen (OMA-URI)|Igen|
PPTP|iOS-eszközök egyéni profilja|Nem |Nem |Nem|Nem|Igen|
L2TP|iOS-eszközök egyéni profilja|Nem |Nem |Nem|Igen (OMA-URI)|Igen|

\*A Windows 10-hez egyébként rendelkezésre álló további beállítások nélkül.

> [!IMPORTANT]
> Az eszközökre alkalmazott VPN-profilok használatához telepítenie kell a megfelelő VPN-alkalmazást a profilhoz. A megfelelő alkalmazás Intune-nal történő telepítéséhez a következő dokumentumban talál segítséget: [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md).  

 Az [Egyéni konfigurációk VPN-profilokhoz](create-custom-vpn-profiles.md) című szakaszból tájékozódhat arról, hogy hogyan hozhat létre egyéni VPN-profilokat URI-beállításokkal.     

## <a name="methods-of-securing-vpn-profiles"></a>A VPN-profilok védelmének biztosítása

A VPN-profilok számos különböző kapcsolattípust és különféle gyártóktól származó protokollt használhatnak. Az ilyen kapcsolatok védelmét általában az alábbi két módszer egyikével biztosítják.

### <a name="certificates"></a>Tanúsítványok

A VPN-profil létrehozásakor ki kell választania egy SCEP-vagy .PFX-tanúsítványprofilt, amelyet korábban az Intune-ban hozott létre. Ez identitástanúsítványként is ismert, és ennek segítségével hajtja végre a rendszer a hitelesítést egy olyan megbízható tanúsítványprofillal (vagy *főtanúsítvánnyal*), amelyet Ön a felhasználó eszközének a csatlakoztatásához hozott létre. A megbízható tanúsítványt a rendszer a VPN-kapcsolatot hitelesítő számítógépre alkalmazza, amely általában a VPN-kiszolgáló.

A tanúsítványprofiloknak az Intune-ban történő létrehozásáról és használatáról a következő dokumentumban olvashat bővebben: [Az erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md).

### <a name="user-name-and-password"></a>Felhasználónév és jelszó

A felhasználó a VPN-kiszolgálón felhasználónév és jelszó megadásával végzi el a hitelesítést.

## <a name="create-a-vpn-profile"></a>VPN-profil létrehozása

1. A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Házirend** > **Házirend hozzáadása** lehetőséget.
2. Válasszon sablont az új szabályzathoz a megfelelő eszköztípus kibontásával, majd válasszon VPN-profilt az eszköznek:
    * **VPN-profil (Android 4 és újabb verziók)**
    * **VPN-profil (Android for Work)**
    * **VPN-profil (iOS 8.0 és újabb verziók)**
    * **VPN-profil (Mac OS X 10.9 és újabb verziók)**
    * **VPN-profil (Windows 8.1 és újabb verziók)**
    * **VPN-profil (Windows Phone 8.1 és újabb)**
    * **VPN-profil (Windows 10 és újabb asztali és mobil verzió)**

 A VPN-profilhoz csak egyéni szabályzatot hozhat létre és alkalmazhat. Ajánlott beállítások nem állnak rendelkezésre.

> [!Note]
> Az Android for Work-eszközök VPN-profilja csak az eszköz munkahelyi profilján telepített alkalmazások számára fogja engedélyezni a VPN-kapcsolatot.
>
> A VPN-kapcsolat egyes típusai támogatják az alkalmazásonkénti VPN-t az Android for Work-eszközökön, illetve az alkalmazásonkénti VPN engedélyezését az Intune-ban elosztott alkalmazásokban.  

3. Az alábbi táblázat segítséget nyújt a VPN-profil beállításainak konfigurálásában:

Beállítás neve  |További információ  
---------|---------
**Név**     |Adjon meg egy egyedi nevet a VPN-profilhoz, amellyel az egyszerűen azonosítható az Intune konzoljában.         
**Leírás**     |Adjon meg egy olyan leírást, amely áttekintést nyújt a VPN-profilról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a profil helyének meghatározásában.         
**VPN-kapcsolat felhasználóknál megjelenő neve**     |Adja meg a VPN-profil nevét. Ez az a név, amelyet a felhasználók látni fognak a rendelkezésre álló VPN-kapcsolatok listájában az eszközükön.         
**Kapcsolat típusa**     |  Válasszon egyet a következő kapcsolattípusok közül a VPN-profilban való használathoz: **Cisco AnyConnect** (nem érhető el a Windows 8.1 vagy Windows Phone 8.1 rendszerhez), **Pulse Secure**, **Citrix**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**VPN-kiszolgáló leírása**     | Adjon meg egy leírást ahhoz a VPN-kiszolgálóhoz, amelyhez az eszközök csatlakozni fognak. Például: **Contoso VPN-kiszolgáló**. Ha a kapcsolat típusa **F5 Edge Client**, a **Kiszolgálólista** mezőben adja meg a kiszolgálóleírások és IP-címek listáját.
**Kiszolgáló IP-címe vagy teljes tartományneve**    |Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljesen minősített tartománynevét, amelyhez az eszközök csatlakozni fognak. Példák: **192.168.1.1**, **vpn.contoso.com**.  Ha a kapcsolat típusa **F5 Edge Client**, a **Kiszolgálólista** mezőben adja meg a kiszolgálóleírások és IP-címek listáját.         |         
**Kiszolgálók listája**     |A **Hozzáadás** elemre kattintva felvehet egy új VPN-kiszolgálót, amelyet aztán alkalmazhat a VPN-kapcsolat kialakításához. Azt is megadhatja, hogy melyik kiszolgáló legyen az alapértelmezett a kapcsolathoz. Ez a beállítás csak akkor látható, ha a kapcsolat típusa **F5 Edge Client**.         
**Az összes hálózati forgalom elküldése a VPN-kapcsolaton keresztül**     |Ha ezt a lehetőséget választja, azzal minden hálózati forgalmat a VPN-kapcsolaton keresztül küld el. Ha nem ezt a lehetőséget választja, az ügyfélprogram dinamikusan egyezteti a vegyes alagútkezelés útvonalait a külső VPN-kiszolgálóhoz való csatlakozáskor. Csak a vállalati hálózat kapcsolatainak küldése történik VPN-alagúton keresztül. Az interneten megtalálható erőforrásokhoz való csatlakozás esetén a program nem használ VPN-alagutat.
**Hitelesítési módszer**| Válassza ki a VPN-kapcsolat által használandó hitelesítési módszert: **Tanúsítványok** vagy **Felhasználónév és jelszó**. (A **Felhasználónév és jelszó** beállítás nem érhető el, ha a kapcsolat típusa Cisco AnyConnect.) A **Hitelesítési módszer** beállítás Windows 8.1 rendszeren nem érhető el.
**Felhasználói hitelesítő adatok megjegyzése minden bejelentkezéskor**|Ezzel a beállítással gondoskodhat arról, hogy a rendszer megjegyezze a felhasználó hitelesítő adatait, így a felhasználónak nem kell megadnia őket minden egyes alkalommal, amikor kapcsolatot létesít.
**Válasszon ki egy, az ügyfél-hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítványt)**|Válassza ki azt a korábban az ügyfélprogramhoz létrehozott SCEP-tanúsítványt, amelyet a VPN-kapcsolat hitelesítéséhez szeretne használni. A tanúsítványprofilok Intune-ban történő használatáról a következő dokumentumban olvashat bővebben: [Az erőforrások biztonságos elérése tanúsítványprofilokkal](secure-resource-access-with-certificate-profiles.md). Ez a beállítás csak akkor látható, ha a hitelesítési módszer a **Tanúsítványok**.
**Szerepkör**| Adja meg annak a felhasználói szerepkörnek a nevét, amely hozzáfér ehhez a kapcsolathoz. A felhasználói szerepkörök személyes beállításokat definiálnak, és engedélyeznek vagy letiltanak bizonyos hozzáférési funkciókat. Ez a beállítás csak akkor látható, ha a kapcsolat **Pulse Secure** vagy **Citrix** típusú.
**Tartomány**|Adja meg a használni kívánt hitelesítési tartomány nevét. A hitelesítési tartomány a Pulse Secure vagy Citrix kapcsolattípus által használt hitelesítési erőforrások csoportja. Ez a beállítás csak akkor látható, ha a kapcsolat **Pulse Secure** vagy **Citrix** típusú.
**Bejelentkezési csoport vagy tartomány**|Adja meg annak a bejelentkezési csoportnak vagy tartománynak a nevét, amelyhez csatlakozni szeretne. Ez a beállítás csak akkor látható, ha a kapcsolat típusa **Dell SonicWALL Mobile Connect**.
**Ujjlenyomat**|Adjon meg egy sztringet (például „Contoso ujjlenyomatkód”), amelyet a rendszer a VPN-kiszolgáló megbízhatóságának ellenőrzésére fog használni. Az ujjlenyomatok elküldhetők az ügyfélprogramnak, így az tudni fogja, hogy megbízhat-e az azonos ujjlenyomattal rendelkező kiszolgálókban a csatlakozáskor. Ha az eszköz még nem rendelkezik ujjlenyomattal, akkor arra fogja kérni a felhasználót, hogy bízzon meg a VPN-kiszolgálóban, amelyhez csatlakozik, miközben megjeleníti az ujjlenyomatot. (A felhasználó manuálisan ellenőrizheti az ujjlenyomatot, majd a **Megbízom benne** lehetőségre kattintva csatlakozhat.) Ez a beállítás csak akkor látható, ha a kapcsolat típusa **CheckPoint Mobile VPN**.
**Alkalmazásonkénti VPN**|Ha a VPN-kapcsolatot egy iOS- vagy Mac OS X-alkalmazással társítaná, válassza ezt a lehetőséget. A rendszer ezt a kapcsolatot fogja megnyitni az alkalmazás futtatásakor. A VPN-profilt a szoftver telepítésekor társíthatja egy alkalmazással. További információk: [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md).
**Igény szerinti VPN**|Igény szerinti VPN-t iOS 8.0 vagy újabb rendszerű eszközökhöz állíthat be. A beállításra vonatkozó utasításokat az [Igény szerinti VPN iOS-eszközökhöz](#on-demand-vpn-for-ios-devices) című szakaszban találja.
**Proxybeállítások automatikus észlelése** (csak iOS, Mac OS X, Windows 8.1 és Windows Phone 8.1 esetén)|Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, adja meg, hogy szeretné-e, ha az eszközök automatikusan észlelnék a kapcsolatbeállításokat. További információt a Windows Server dokumentációjában talál.
**Automatikus konfigurációs szkript használata** (csak iOS, Mac OS X, Windows 8.1 és Windows Phone 8.1 esetén)|Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, adja meg, hogy szeretné-e egy automatikus konfigurációs szkripttel definiálni a beállításokat, majd adja meg a beállításokat tartalmazó fájl URL-címét. További információt a Windows Server dokumentációjában talál.
**Proxykiszolgáló használata** (csak iOS, Mac OS X, Windows 8.1 és Windows Phone 8.1 esetén)|Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, majd adja meg a proxykiszolgáló címét és portszámát. További információt a Windows Server dokumentációjában talál.
**Proxybeállítások megkerülése helyi címek esetén** (csak iOS, Mac OS X, Windows 8.1 és Windows Phone 8.1 esetén)|Ha a VPN-kiszolgáló proxykiszolgálót igényel a kapcsolathoz, válassza ezt a beállítást, ha az Ön által megadott helyi címekhez nem szeretné használni a proxykiszolgálót. További információt a Windows Server dokumentációjában talál.
**Egyéni XML** (csak Windows 8.1-es és újabb, illetve Windows Phone 8.1-es és újabb verziók esetén)|Segítségével a VPN-kapcsolatot konfiguráló egyéni XML-parancsokat adhat meg. Példa a **Pulse Secure** szolgáltató használatára: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Példa egy **CheckPoint Mobile VPN**-parancsra: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" /&gt;. Példa a **Dell SonicWALL Mobile Connect** szolgáltató használatára: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Példa az **F5 Edge Client** szolgáltató használatára: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Az egyéni XML-parancsok írásával kapcsolatban további információt az egyes gyártók VPN-dokumentációjában talál.
**DNS-utótagok keresési listája** (csak Windows Phone 8.1 esetén)|Minden egyes sorban adjon meg egy DNS-utótagot. A rendszer minden egyes megadott DNS-utótagra rákeres, amikor egy rövid nevet használó webhelyhez csatlakozik. Adja meg például a **domain1.contoso.com** és **domain2.contoso.com** DNS-utótagokat, majd látogasson el a **http://sajatwebhely** URL-címre. Ekkor a **http://sajatwebhely.domain1.contoso.com** és **http://sajatwebhely.domain2.contoso.com** URL-címekre fog keresni.
**A VPN megkerülése a vállalati Wi-Fi hálózathoz való csatlakozáskor** (csak Windows Phone 8.1 esetén)|Ezzel a beállítással letilthatja a VPN-kapcsolatot, amikor az eszköz a vállalati Wi-Fi-hálózathoz csatlakozik.
**A VPN megkerülése otthoni Wi-Fi hálózathoz való csatlakozáskor** (csak Windows Phone 8.1 esetén)|Ezzel a beállítással letilthatja a VPN-kapcsolatot, amikor az eszköz a vállalati Wi-Fi-hálózathoz csatlakozik.

Az alábbi beállítások érhetők el a Windows 10 rendszerű asztali és mobileszközökhöz.

Beállítás neve  |További információ  
---------|---------
**Hálózati forgalomra vonatkozó szabályok**|Beállíthatja, hogy a VPN-kapcsolatnál mely protokollok, valamint melyik helyi és távoli portok és címtartományok lesznek engedélyezve. Ha nem hoz létre hálózati forgalmi szabályt, minden protokoll, port és címtartomány engedélyezve lesz. Ha létrehoz egy szabályt, a VPN-kapcsolat csak az Ön által a szabályban megadott protokollokat, portokat és címtartományokat fogja használni.
**Útvonalak**|A VPN-kapcsolat által használt útvonalak megadása.
**DNS-kiszolgálók**| A VPN-kapcsolat által a kapcsolat létrejötte után használt DNS-kiszolgálók megadása.         
**Társított alkalmazások**|A VPN-kapcsolatot automatikusan használó alkalmazások listájának megadása. Az alkalmazás típusa határozza meg az alkalmazás azonosítóját. Univerzális alkalmazások esetén adja meg a Csomagcsalád nevét. Asztali alkalmazások esetén adja meg az alkalmazás fájlelérési útvonalát.          


> [!IMPORTANT]
> Javasoljuk, hogy az alkalmazásonkénti VPN-konfigurációban való használat céljából összeállított alkalmazáslistákat mindig lássa el védelemmel. Ha a listát esetleg arra nem jogosult felhasználó módosítja, és Ön így importálja azt az alkalmazásonkénti VPN-alkalmazáslistába, azzal olyan alkalmazásoknak is VPN-elérést nyújthat, amelyeknek eredetileg nem szeretett volna. Az alkalmazáslisták védelmének módja lehet a hozzáférés-vezérlési lista (ACL) létrehozása.

Íme egy példa a vállalati határbeállítások használatára. Ha a VPN-t csak a Távoli asztalhoz szeretné engedélyezni, akkor létre kell hoznia egy olyan hálózati forgalmi szabályt, amely engedélyezi a 27-es számú protokollhoz tartozó forgalmat a 3996-os külső porton. A VPN-t csak ez a típusú forgalom fogja használni.

Akkor lehet hasznos útvonalakat megadni a vállalati határokban, ha a VPN-kapcsolat típusa nem engedélyezi annak meghatározását, hogy a rendszer hogyan kezelje a forgalmat vegyes alagútkezelés esetén. Ilyenkor használja az **Útvonalak** elemet a VPN-t használó útvonalak felsorolásához.

Egy egyéni OMA-URI-beállítás létrehozásával a Windows 10-es eszközök VPN-használatát adott alkalmazásokra korlátozhatja.

Az új szabályzat a **Házirend** munkaterület **Konfigurációs szabályzatok** csomópontjában jelenik meg.

### <a name="on-demand-vpn-for-ios-devices"></a>Igény szerinti VPN iOS-eszközökhöz
Igény szerinti VPN-t iOS 8.0 vagy újabb rendszerű eszközökhöz konfigurálhat.

> [!NOTE]
>  
> Alkalmazásonkénti VPN és igény szerinti VPN nem használható egyszerre ugyanabban a szabályzatban.

1. A szabályzatkonfigurációs lapon keresse ki az **A VPN-kapcsolatra vonatkozó igény szerinti szabályok** elemet. Az oszlopok címkézése: **Egyezés** – a szabályok által figyelt feltétel, és **Művelet** – a feltétel teljesülése esetén a szabályzat által elindítandó művelet.
2. Új szabály létrehozásához válassza a **Hozzáadás** lehetőséget. A szabályban kétféle egyezéstípust állíthat be. Ugyanabban a szabályban csak egyféle típust konfigurálhat.
  - Az **SSID-k** vezeték nélküli hálózatokra vonatkoznak.
  - A **DNS-keresési tartományok** .....  Használhatók teljesen minősített tartománynevek, amilyen például a *team. corp.contoso.com*, vagy használhat a *contoso.com*-hoz hasonló tartományneveket, amely megegyezik a * *.contoso.com használatával*.
3. Nem kötelező: megadhat egy URL-sztringmintát is (a szabály által tesztként használt URL-t). Ha az eszköz, amelyen ez a profil telepítve van, átirányítás nélkül el tudja érni ezt az URL-címet, akkor létrejön a VPN-kapcsolat a célként megadott URL-címmel. A felhasználó nem látja a teszthez használt URL-célhelyet. URL-sztringmintaként meg lehet adni például egy naplózási webkiszolgálót, amely VPN-kapcsolat létrejötte előtt ellenőrzi az eszköz megfelelőségét. Egy másik lehetőség, hogy az URL-cím ellenőrzi a VPN webhelyhez történő kapcsolódási képességét azlőtt, hogy létrejönne a VPN-kapcsolat az eszköz és a célként megadott URL-cím között.
4. Válassza az alábbi műveletek egyikét:
  - **Kapcsolódás**
  - **Kapcsolat kiértékelése** - ennek háromféle beállítása van; a. **Tartományi művelet** – választhatja a **Szükség esetén kapcsolódás** vagy a **Soha ne legyen kapcsolódás** lehetőségeket
    ; b. **Tartományok vesszővel elválasztott listája** – ezt csak akkor kell konfigurálnia, ha a **Tartományi műveletek** közül a **Szükség esetén kapcsolódás** lehetőséget választotta
    ; c. **Kötelező URL-sztringminta** – egy HTTP vagy HTTPS (javasolt) URL-cím, például *https://vpntestprobe.contoso.com*. Ez a szabály ellenőrzi, hogy érkezett-e válasz erről a címről. Ha nem érkezett, és a **Tartományi műveletek** közül a **Szükség esetén kapcsolódás** lehetőség lett kiválasztva, a VPN aktiválódik.
      
     > [!TIP]
     >
     >Ez a művelet használható például akkor, ha a vállalati hálózat bizonyos helyei megkövetelik a közvetlen kapcsolatot vagy a vállalati VPN-kapcsolatot, mások azonban nem. Ha a **DNS-keresési tartományok vesszővel elválasztott listájában** megadta a *corp.contoso.com* címet, választhatja a **Csatlakozás szükség esetén** lehetőséget, majd megadhatja a hálózat azon helyeinek listáját, amelyek VPN-kapcsolatot követelnek meg, például *sharepoint.corp.contoso.com*. A szabály ellenőrzi, hogy a *vpntestprobe.contoso.com* elérhető-e. Ha nem érhető el, a VPN a Sharepoint-helyre vonatkozóan aktiválódik.
  - **Figyelmen kívül hagy** – nem eredményez változást a VPN-kapcsolatokban. Ha van VPN-kapcsolat, az megmarad, ha nincs, akkor nem aktiválódik. Például létrehozhat egy olyan szabályt, amely VPN-kapcsolatot létesít minden belső vállalati webhelyre vonatkozóan, miközben egy meghatározott belső webhelyet csak akkor szeretne elérhetővé tenni, ha az illető eszköz ténylegesen csatlakozott a hálózathoz. Ebben az esetben létrehozhat egy „figyelmen kívül hagy” szabályt erre a webhelyre vonatkozóan.
  - **Kapcsolat bontása** – a feltételek teljesülése esetén bontja az eszközök VPN-kapcsolatát. Például megadhatja a vállalati vezeték nélküli hálózatok listáját az **SSID-k** mezőben, majd létrehozhat egy szabályt, amely bontja az eszközök VPN-kapcsolatát, ha azok ezekhez a hálózatokhoz kapcsolódnak.

A tartományspecifikus szabályok kiértékelése a minden tartományra vonatkozó szabályok kiértékelése előtt történik.


## <a name="deploy-the-policy"></a>A szabályzat telepítése

1.  A **Szabályzat** munkaterületen válassza ki a telepíteni kívánt szabályzatot, és kattintson a **Központi telepítés kezelése** elemre.

2.  A **Telepítések kezelése** párbeszédpanelen:

    -   A házirend telepítése – Válasszon ki egy vagy több olyan csoportot, amelynek telepíteni kívánja a házirendet, majd kattintson a **Hozzáadás** &gt; **OK** gombra.

    -   A párbeszédpanel telepítés nélküli bezárásához kattintson a **Mégse** gombra.


A sikeres alkalmazást követően a felhasználók látni fogják az eszközükön a VPN-kapcsolat Ön által megadott nevét a VPN-kapcsolatok listájában.

A **Házirend** munkaterület **Áttekintés** lapján található állapotösszegzés és riasztások segítségével azonosíthatók a szabályzattal kapcsolatos, figyelmet igénylő problémák. Ezen felül egy állapotösszegzés megjelenik az Irányítópult munkaterületen is.

