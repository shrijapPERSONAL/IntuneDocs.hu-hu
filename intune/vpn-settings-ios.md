---
title: VPN-beállítások iOS-eszközökhöz az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Az elérhető virtuális magánhálózati (VPN-) konfigurációs beállítások megtekintése, ideértve a kapcsolat adatait, a hitelesítési módszereket és a vegyes alagútkezelést az alapbeállításoknál; az egyéni VPN-beállításokat azonosítóval, és a kulcs és érték párokat; az alkalmazásonkénti VPN-beállításokat, ideértve a Safari URL-eket és az igény szerinti VPN-eket SSID-vel vagy DNS-keresési tartományokkal; valamint a proxybeállításokat konfigurációs parancsfájl, IP- vagy FQDN-cím belefoglalásához, illetve TCP-port Microsoft Intune-ban való beállításához az iOS-t futtató eszközökhöz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: deb6a230573ff20237e6eee386052baba472832a
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313870"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Az iOS rendszerű eszközökre vonatkozó VPN-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cikk a VPN-kapcsolatoknak az iOS rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti.

A megadott beállításoktól függően a következő listában található értékek némelyike nem konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások
Az alábbi listában ténylegesen látható beállításokat a választott VPN-kapcsolattípus határozza meg.  
- **Kapcsolat neve**: A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **Egyéni tartománynév** (csak Zscaler): Előre kitölti a Zscaler alkalmazás bejelentkezési mezőit azzal a tartománnyal, amelyhez felhasználója tartozik. Ha a felhasználónév például **Joe@contoso.net**, akkor az alkalmazás megnyílásakor a mezőben statikusan a **contoso.net** tartomány jelenik meg. Ha nem ír be tartománynevet, akkor az Azure Active Directoryban tárolt egyszerű felhasználónév tartomány-része lesz használva.
- **IP-cím vagy teljes tartománynév**: Annak a VPN-kiszolgálónak az IP-címe vagy teljes tartományneve (FQDN), amelyhez az eszközök csatlakoznak. Írja be például a **192.168.1.1** vagy a **vpn.contoso.com** címet. 
- **Vállalati felhő neve** (csak Zscaler): Írja be annak a felhőnek a nevét, amelyben a vállalata ki van építve. A nevet megtalálhatja a Zscalerbe való bejelentkezéshez használt URL-címben.  
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
  - **Zscaler**: Megköveteli a Zscaler Private Access (ZPA) integrálását az Azure Active Directory-fiókjával. A lépések részletezését a [Zscaler dokumentációja](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO) tartalmazza. 
  - **Egyéni VPN**    

    > [!NOTE]
    > A Cisco, a Citrix, az F5 és a Palo Alto bejelentette, hogy régebbi ügyfeleik nem fognak működni az iOS 12 soron következő kiadásán. Ajánlott a lehető leghamarabb áttérni az új alkalmazásokra. További információkat a [Microsoft Intune blogjában](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409) talál.

* **Kizárt URL-címek** (csak Zscaler): A Zscaler VPN-hez csatlakozva a felsorolt URL-címek érhetők el a Zscaler-felhőn kívülről. 

- **Bújtatás megosztása**: Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.   

## <a name="custom-vpn-settings"></a>Egyéni VPN-beállítások

Ha a kapcsolat típusaként az **Egyéni VPN** lehetőséget választotta, konfigurálnia kell a következő beállításokat. Ezek a beállítások a Zscaler- és Citrix-kapcsolatokhoz is megjelennek.

- **VPN-azonosító**: Ez az Ön által használt VPN-alkalmazás azonosítója, amelyet a VPN-szolgáltatója biztosított.
- **Kulcs-érték párok megadása vállalata egyéni VPN attribútumainak konfigurálásához**: **Kulcsok** és **Értékek** hozzáadásával vagy importálásával szabhatja testre a VPN-kapcsolatot. Rendszerint ezeket az értékeket is a VPN-szolgáltató biztosítja.

## <a name="automatic-vpn-settings"></a>Automatikus VPN-beállítások

- **Alkalmazásonkénti VPN**: Ezt a beállítást választva engedélyezi az alkalmazásonkénti VPN, ezáltal a VPN-kapcsolat bizonyos alkalmazások megnyitásakor automatikusan aktiválódni fog. A beállítás kiválasztása mellett az alkalmazásokat is társítania kell ehhez a VPN-profilhoz. További információt az [Útmutató alkalmazásonkénti VPN beállításához iOS rendszeren](vpn-setting-configure-per-app.md) című cikkben találhat. 
  - A **Szolgáltatótípus** beállítás csak a Pulse Secure és egyéni VPN esetén elérhető.
  - Az iOS-es **alkalmazásonkénti VPN**-profilok Pulse Secure-ral vagy egyéni VPN-nel való használatakor választhat az alkalmazásrétegbeli (alkalmazásproxy) és csomagszintű (csomagalagút) alagútkezelés között. Alkalmazásrétegbeli alagútkezeléshez adja meg az **alkalmazásproxy**, csomagszintű alagútkezeléshez a **csomagalagút** értéket **Szolgáltatótípusként**. Ha nem biztos abban, hogy melyiket kell használnia, tanulmányozza VPN-szolgáltatója dokumentációját. 
  - **A VPN-t aktiváló Safari URL-címek**: E lehetőség választásával megadhat egy vagy több webhelycímet. Ezeket az URL-címeket az eszköz Safari böngészőjében megnyitva a VPN-kapcsolat automatikusan létrejön.

- **Igény szerinti VPN**: Ezzel a beállítással feltételes szabályokat állíthat be, melyek a VPN-kapcsolat kezdeményezésekor lépnek érvénybe. Létrehozhat például egy olyan feltételt, amelyben a rendszer csak akkor használja a VPN-kapcsolatot, ha az eszköz nem kapcsolódik a vállalati Wi-Fi-hálózathoz. Vagy olyan feltételt is létrehozhat, amelyben ha egy eszköz nem férhet hozzá egy megadott DNS-keresési tartományhoz, akkor a rendszer nem kezdeményez VPN-kapcsolatot.

  - **SSID-k vagy DNS-keresési tartományok**: Megadhatja, hogy ez a feltétel vezeték nélküli hálózatok **SSID-it** használja, vagy **DNS-keresési tartományokat**. Válassza a **Hozzáadás** lehetőséget egy vagy több SSID vagy keresési tartomány konfigurálásához.
  - **Az URL-cím sztringjének vizsgálata**: Nem kötelező. Adjon meg egy URL-címet, amelyet a szabály teszteléshez használhat. Ha az eszköz, amelyen a profil telepítve van, átirányítás nélkül el tudja érni ezt az URL-címet, akkor a rendszer kezdeményezi a VPN-kapcsolatot, és az eszköz kapcsolódik a célként megadott URL-címre. A felhasználó nem látja a teszthez használt URL-célhely sztringjét. Értékként megadhat például egy naplózási webkiszolgálót, amely VPN-kapcsolat létrejötte előtt ellenőrzi az eszköz megfelelőségét. Egy másik lehetőség, hogy az URL-cím ellenőrzi a VPN webhelyhez történő kapcsolódási képességét azelőtt, hogy létrejönne a VPN-kapcsolat az eszköz és a célként megadott URL-cím között.
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

- **Automatikus konfigurációs szkript**: A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Cím**: Adja meg a proxykiszolgáló IP-címét vagy teljesen minősített állomásnevét.
- **Portszám**: Adja meg a proxykiszolgálóhoz társított portszámot.

## <a name="next-step"></a>Következő lépés
[VPN-profilok létrehozása az Intune-ban](vpn-settings-configure.md)  
