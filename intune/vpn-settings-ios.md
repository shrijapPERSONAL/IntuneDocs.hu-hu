---
title: VPN-beállítások hozzáadása iOS-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: VPN-konfigurációs profil hozzáadása vagy létrehozása virtuális magánhálózati (VPN) konfigurációs beállításokkal, ideértve a kapcsolat adatait, a hitelesítési módszereket és a vegyes alagútkezelést az alapbeállításoknál; az egyéni VPN-beállításokat azonosítóval, és a kulcs és érték párokat; az alkalmazásonkénti VPN-beállításokat, ideértve a Safari URL-eket és az igény szerinti VPN-eket SSID-vel vagy DNS-keresési tartományokkal; valamint a proxybeállításokat konfigurációs parancsfájl, IP- vagy FQDN-cím belefoglalásához, illetve TCP-port Microsoft Intune-ban való beállításához az iOS-t futtató eszközökhöz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b794ec40d05358ddd1aa3179c2f4060b2cd6fe1d
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236509"
---
# <a name="configure-vpn-settings-on-ios-devices-in-microsoft-intune"></a>VPN-beállítások konfigurálása iOS-eszközökön a Microsoft Intune-ban

A Microsoft Intune számos VPN-beállítást tartalmaz, amelyek telepíthetők az iOS-eszközére. Ezek a beállítások VPN-kapcsolatok létrehozására és konfigurálására használhatók a szervezet hálózatához. Ez a cikk ezeket a beállításokat ismerteti. Egyes beállítások csak egyes VPN-ügyfelekhez állnak rendelkezésre, például a Citrix, Zscaler és másokhoz.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások

Az alábbi listában látható beállításokat a kiválasztott VPN-kapcsolat típusa határozza meg.  

- **Kapcsolat neve**: A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **Egyéni tartománynév** (csak Zscaler): Előre kitölti a Zscaler alkalmazás bejelentkezési mezőit azzal a tartománnyal, amelyhez felhasználója tartozik. Ha a felhasználónév például `Joe@contoso.net`, akkor az alkalmazás megnyílásakor a mezőben statikusan a `contoso.net` tartomány jelenik meg. Ha nem ír be tartománynevet, akkor az Azure Active Directoryban tárolt egyszerű felhasználónév tartomány-része lesz használva.
- **IP-cím vagy teljes tartománynév**: Annak a VPN-kiszolgálónak az IP-címe vagy teljes tartományneve (FQDN), amelyhez az eszközök csatlakoznak. Például írja be a következőt: `192.168.1.1` vagy `vpn.contoso.com`.
- **Felhőbeli cégnév** (csak Zscaler): Írja be annak a felhőnek a nevét, amelyben a vállalata ki van építve. A nevet megtalálhatja a Zscalerbe való bejelentkezéshez használt URL-címben.  
- **Hitelesítési mód**: Válassza ki, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón. 
  - **Tanúsítványok**: A **Hitelesítési tanúsítvány** szakaszban válasszon egy meglévő SCEP- vagy PKCS-tanúsítványprofilt a kapcsolat hitelesítéséhez. A [Tanúsítványok konfigurálása](certificates-configure.md) című témakörben találhat útmutatást a tanúsítványprofilokról.
  - **Felhasználónév és jelszó**: A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha szeretnének bejelentkezni a VPN-kiszolgálóra.  

    > [!NOTE]
    > Ha a Cisco IPsec VPN-hez felhasználónevet és jelszót használ hitelesítési módszerként, a titkos kulcsot egy egyéni Apple Configurator-profilon keresztül kell továbbítani.
  
- **Kapcsolat típusa**: Az alábbi listából válassza ki a VPN-kapcsolat típusát:
  - **Check Point Capsule VPN**
  - **Cisco Legacy AnyConnect**: A [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) alkalmazás 4.0.5x és annál korábbi verzióihoz használható.
  - **Cisco AnyConnect**: A [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) alkalmazás 4.0.7x és annál újabb verzióihoz használható.
  - **SonicWall Mobile Connect**
  - **F5 Access Legacy**: Az F5 Access alkalmazás 2.1 és annál korábbi verzióihoz használható.
  - **F5 Access**: Az F5 Access alkalmazás 3.0 és annál újabb verzióihoz használható.
  - **Palo Alto Networks GlobalProtect (Legacy)**: A Palo Alto Networks GlobalProtect alkalmazás 4.1 és annál korábbi verzióihoz használható.
  - **Palo Alto Networks GlobalProtect**: A Palo Alto Networks GlobalProtect alkalmazás 5.0 és annál újabb verzióihoz használható.
  - **Pulse Secure**
  - **Cisco (IPsec)**
  - **Citrix VPN**
  - **Citrix SSO**
  - **Zscaler**: Kötelező a Zscaler Private Access (ZPA) integrálása az Azure AD-fiókjával. A lépések részletezését a [Zscaler dokumentációja](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO) tartalmazza. 
  - **Egyéni VPN**    

    > [!NOTE]
    > A Cisco, a Citrix, az F5 és a Palo Alto bejelentette, hogy régebbi ügyfeleik nem fognak működni az iOS 12-es verziójával. Ajánlott a lehető leghamarabb áttérni az új alkalmazásokra. További információkat a [Microsoft Intune blogjában](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409) talál.

* **Kizárt URL-címek** (csak Zscaler): A Zscaler VPN-hez csatlakozva a felsorolt URL-címek érhetők el a Zscaler-felhőn kívülről. 

- **Bújtatás megosztása**: Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.

- **Hálózati hozzáférés-vezérlés (NAC) engedélyezése**: Ez a beállítás egy helyőrző VPN-ügyfelekhez, például a Citrixhez, hogy lehetővé tegye az eszközazonosító megadását a VPN-profilban a hálózati hozzáférés-vezérléssel (NAC) való használathoz. Ha az **Elfogadom** lehetőséget választja, az eszköz azonosítója bekerül a VPN-profilba. Jelenleg nincs olyan VPN-ügyfél, vagy NAC-partnermegoldás, amely támogatná ezt az új azonosítót, ezért az eszközök számára engedélyezett lesz a VPN-hez való csatlakozás, a megfelelőségi állapottól függetlenül. Frissítjük ezt a dokumentumot, amint a partnereink támogatni fogják az azonosítót.

  Fontos részletek:  

  - Ha ez a beállítás engedélyezve van, a VPN 24 óránként le lesz csatlakoztatva.
  - Az eszköz azonosítója a profil része, de az nem látható az Intune-ban vagy a profilban. Ezt az azonosítót a Microsoft sehol sem tárolja és nem osztja meg. Amint ezt a VPN-partnerek támogatni fogják, a VPN-ügyfél, például a Citrix SSO lekérheti az azonosítót, és lekérdezheti az Intune-tól, hogy az eszköz regisztrálva van-e, és hogy a VPN-profil megfelelő-e vagy sem.
  - A beállítás eltávolításához hozza létre újra a profilt, és ne válassza ki az **Elfogadom** lehetőséget. Ezt követően végezze el a profil újbóli hozzárendelését.

## <a name="custom-vpn-settings"></a>Egyéni VPN-beállítások

Ha a kapcsolat típusaként az **Egyéni VPN** lehetőséget választotta, konfigurálnia kell a következő beállításokat. Ezek a beállítások a Zscaler- és Citrix-kapcsolatokhoz is megjelennek.

- **VPN-azonosító**: Ez az Ön által használt VPN-alkalmazás azonosítója, amelyet a VPN-szolgáltatója biztosított.
- **Kulcs-érték párok megadása vállalata egyéni VPN attribútumainak konfigurálásához**: **Kulcsok** és **Értékek** hozzáadásával vagy importálásával szabhatja testre a VPN-kapcsolatot. Ne feledje, rendszerint ezeket az értékeket is a VPN-szolgáltató biztosítja.

## <a name="automatic-vpn-settings"></a>Automatikus VPN-beállítások

- **Alkalmazásonkénti VPN**: Engedélyezi az alkalmazásonkénti VPN használatát. Lehetővé teszi a VPN-kapcsolat automatikus aktiválását bizonyos alkalmazások megnyitásakor. Ezenkívül társítja az alkalmazásokat ehhez a VPN-profilhoz. További információért lásd az [alkalmazásonkénti VPN beállítására vonatkozó utasításokat iOS-hez](vpn-setting-configure-per-app.md).
  - **Szolgáltatótípus**: Csak a Pulse Secure-hoz és az egyéni VPN-hez érhető el.
  - Az iOS-es **alkalmazásonkénti VPN**-profilok Pulse Secure-ral vagy egyéni VPN-nel való használatakor választhat az alkalmazásrétegbeli (alkalmazásproxy) és csomagszintű (csomagalagút) alagútkezelés között. A **Szolgáltatótípus** értékét az alkalmazásrétegbeli alagútkezeléshez állítsa az **alkalmazásproxy** lehetőségre, a csomagrétegbeli alagútkezeléshez pedig állítsa a **csomagalagút** lehetőségre. Ha nem biztos a megfelelő értékben, tekintse meg a VPN-szolgáltató dokumentációját.
  - **A VPN-t aktiváló Safari URL-címek**: Megadhat egy vagy több webhelycímet. Ezeket az URL-címeket az eszköz Safari böngészőjében megnyitva a VPN-kapcsolat automatikusan létrejön.

- **Igény szerinti VPN**: Ezzel a beállítással feltételes szabályokat állíthat be, melyek a VPN-kapcsolat indítását vezérlik. Létrehozhat például egy olyan feltételt, amelyben a rendszer csak akkor használja a VPN-kapcsolatot, ha az eszköz nem kapcsolódik a vállalati Wi-Fi-hálózathoz. Vagy olyan feltételt is létrehozhat, amelyben ha egy eszköz nem férhet hozzá egy megadott DNS-keresési tartományhoz, akkor a rendszer nem indítja el a VPN-kapcsolatot.

  - **SSID-k vagy DNS-keresési tartományok**: Megadhatja, hogy ez a feltétel vezeték nélküli hálózatok **SSID-it** használja, vagy **DNS-keresési tartományokat**. Válassza a **Hozzáadás** lehetőséget egy vagy több SSID vagy keresési tartomány konfigurálásához.
  - **Az URL-cím sztringjének vizsgálata**: Nem kötelező. Adjon meg egy URL-címet, amelyet a szabály teszteléshez használhat. Ha az ezzel a profillal rendelkező eszköz átirányítás nélkül hozzáfér ehhez az URL-címhez, akkor a VPN-kapcsolat kezdeményezése megtörtént. És az eszköz csatlakozik a célként megadott URL-címhez. A felhasználó nem látja a teszthez használt URL-célhely sztringjét. Értékként megadhat például egy naplózási webkiszolgálót, amely VPN-kapcsolat létrejötte előtt ellenőrzi az eszköz megfelelőségét. Egy másik lehetőség, hogy az URL-cím ellenőrzi a VPN webhelyhez történő kapcsolódási képességét azelőtt, hogy létrejönne a VPN-kapcsolat az eszköz és a célként megadott URL-cím között.
  - **Tartományi művelet**: Válasszon a következő lehetőségek közül:
    - Szükség esetén kapcsolódás
    - Soha ne legyen kapcsolódás
  - **Művelet**: Válasszon a következő lehetőségek közül:
    - Kapcsolódás
    - Kapcsolat kiértékelése
    - Mellőzés
    - Kapcsolat bontása

## <a name="proxy-settings"></a>Proxybeállítások

Ha proxyt használ, konfigurálja a következő beállításokat. A proxybeállítások Zscaler VPN-kapcsolatokhoz nem érhetők el.  

- **Automatikus konfigurációs szkript**: A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **proxykiszolgáló URL-címét** (például: `http://proxy.contoso.com`).
- **Cím**: Adja meg a proxykiszolgáló IP-címét vagy teljesen minősített állomásnevét.
- **Portszám**: Adja meg a proxykiszolgálóhoz társított portszámot.

## <a name="next-step"></a>Következő lépés
[VPN-profilok létrehozása az Intune-ban](vpn-settings-configure.md)  
