---
title: VPN-beállítások iOS-eszközökhöz az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Az elérhető virtuális magánhálózati (VPN-) konfigurációs beállítások megtekintése, ideértve a kapcsolat adatait, a hitelesítési módszereket és a vegyes alagútkezelést az alapbeállításoknál; az egyéni VPN-beállításokat azonosítóval, és a kulcs és érték párokat; az alkalmazásonkénti VPN-beállításokat, ideértve a Safari URL-eket és az igény szerinti VPN-eket SSID-vel vagy DNS-keresési tartományokkal; valamint a proxybeállításokat konfigurációs parancsfájl, IP- vagy FQDN-cím belefoglalásához, illetve TCP-port Microsoft Intune-ban való beállításához az iOS-t futtató eszközökhöz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eb87d75512d9f04abac9db256d0d968bb85116ef
ms.sourcegitcommit: 6a9830de768dd97a0e95b366fd5d2f93980cee05
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Az iOS rendszerű eszközökre vonatkozó VPN-beállítások konfigurálása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cikk a VPN-kapcsolatoknak az iOS rendszerű eszközökön való konfigurálására használható Intune-beállításokat ismerteti.

A megadott beállításoktól függően a következő listában található értékek némelyike nem konfigurálható.

## <a name="base-vpn-settings"></a>Alapvető VPN-beállítások

- **Kapcsolat neve**: Adja meg a kapcsolat nevét. A végfelhasználók akkor látják ezt a nevet, amikor megkeresik a rendelkezésre álló VPN-kapcsolatok listáját az eszközükön.
- **IP-cím vagy teljes tartománynév**: Adja meg annak a VPN-kiszolgálónak az IP-címét vagy teljes tartománynevét (FQDN), amelyhez az eszközök csatlakoznak. Írja be például a **192.168.1.1** vagy a **vpn.contoso.com** címet.
- **Hitelesítési módszer**: Válassza ki a következő lehetőségek közül, hogy miképpen hitelesítik magukat az eszközök a VPN-kiszolgálón:
  - **Tanúsítványok**: A **Hitelesítési tanúsítvány** szakaszban válasszon egy meglévő SCEP- vagy PKCS-tanúsítványprofilt a kapcsolat hitelesítéséhez. A [Tanúsítványok konfigurálása](certificates-configure.md) című témakörben találhat útmutatást a tanúsítványprofilokról.
  - **Felhasználónév és jelszó**: A végfelhasználóknak felhasználónevet és jelszót kell megadniuk, ha szeretnének bejelentkezni a VPN-kiszolgálóra.

    > [!NOTE]
    > Ha a Cisco IPsec VPN-hez felhasználónevet és jelszót használ hitelesítési módszerként, a titkos kulcsot egy egyéni Apple Configurator-profilon keresztül kell továbbítani.
  
- **Kapcsolat típusa**: Az alábbi listából válassza ki a VPN-kapcsolat típusát:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **Cisco Legacy AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Cisco (IPsec)**
  - **Citrix**
  - **Egyéni VPN**

    > [!NOTE]
    > - A **Cisco Legacy AnyConnect VPN**-profilok a [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) alkalmazás 4.0.5x és annál régebbi verzióihoz valók
    > - A **Cisco AnyConnect VPN**-profilok a [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) alkalmazás 4.0.7x és annál újabb verzióihoz valók

- **Bújtatás megosztása**: Az **Engedélyezés** vagy a **Letiltás** beállítással szabályozhatja, hogy az eszközök választhatnak-e a forgalomtól függően a kapcsolatok közül. Egy szállodai vendég például a munkahelyi fájlok elérésére a VPN-kapcsolatot, de egyszerű böngészésre a szálloda normál hálózatát használja.

## <a name="custom-vpn-settings"></a>Egyéni VPN-beállítások

Ha a kapcsolat típusaként az **Egyéni VPN** lehetőséget választotta, konfigurálja a következő beállításokat is:

- **VPN-azonosító**: Ez az Ön által használt VPN-alkalmazás azonosítója, amelyet a VPN-szolgáltatója biztosított.
- **Adja meg a kulcs-érték párokat az egyéni VPN attribútumainak konfigurálásához**: **Kulcsok** és **Értékek** hozzáadásával vagy importálásával szabhatja testre a VPN-kapcsolatot. Rendszerint ezeket az értékeket is a VPN-szolgáltató biztosítja.

## <a name="apps-per-app-vpn-settings"></a>Alkalmazások (alkalmazásonkénti VPN) beállításai

- **Alkalmazásonkénti VPN**: Engedélyezze ezt a beállítást, ha olyan URL-címeket szeretne használni, amelyek engedélyezik a VPN-kapcsolatot a Safari böngészőből való megnyitáskor. Az alkalmazásonkénti VPN konfiguráláshoz hitelesítési módszerként a **Tanúsítványok** lehetőséget kell választania az alapvető VPN-beállításokban.
  - **A VPN-t aktiváló Safari URL-címek**: E lehetőség választásával megadhat egy vagy több webhelycímet. Ezeknek a URL-címeknek a használatakor a VPN-kapcsolat engedélyezve van.

- **Igény szerinti VPN**: Ezzel a beállítással feltételes szabályokat állíthat be, melyek a VPN-kapcsolat kezdeményezésekor lépnek érvénybe. Létrehozhat például egy olyan feltételt, amelyben a rendszer csak akkor használja a VPN-kapcsolatot, ha az eszköz nem kapcsolódik a vállalati Wi-Fi-hálózathoz. Vagy olyan feltételt is létrehozhat, amelyben ha egy eszköz nem férhet hozzá egy megadott DNS-keresési tartományhoz, akkor a rendszer nem kezdeményez VPN-kapcsolatot.

  - **SSID-k vagy DNS-keresési tartományok**: Megadhatja, hogy ez a feltétel vezeték nélküli hálózatok **SSID-it** használja, vagy **DNS-keresési tartományokat**. Válassza a **Hozzáadás** lehetőséget egy vagy több SSID vagy keresési tartomány konfigurálásához.
  - **Az URL-cím karakterláncának vizsgálata**: Nem kötelező. Adjon meg egy URL-címet, amelyet a szabály teszteléshez használhat. Ha az eszköz, amelyen a profil telepítve van, átirányítás nélkül el tudja érni ezt az URL-címet, akkor a rendszer kezdeményezi a VPN-kapcsolatot, és az eszköz kapcsolódik a célként megadott URL-címre. A felhasználó nem látja a teszthez használt URL-célhelyet. Értékként megadhat például egy naplózási webkiszolgálót, amely VPN-kapcsolat létrejötte előtt ellenőrzi az eszköz megfelelőségét. Egy másik lehetőség, hogy az URL-cím ellenőrzi a VPN webhelyhez történő kapcsolódási képességét azelőtt, hogy létrejönne a VPN-kapcsolat az eszköz és a célként megadott URL-cím között.
  - **Tartományi művelet**: Válasszon a következő lehetőségek közül:
    - Szükség esetén kapcsolódás
    - Soha ne legyen kapcsolódás
  - **Művelet**: Válasszon a következő lehetőségek közül:
    - Kapcsolódás
    - Kapcsolat kiértékelése
    - Mellőzés
    - Kapcsolat bontása

## <a name="proxy-settings"></a>Proxybeállítások

- **Automatikus konfigurációs szkript**: A proxykiszolgálót egy konfigurációs fájl segítségével konfigurálja. Adja meg a konfigurációs fájlt tartalmazó **Proxykiszolgáló URL-címét** (például **http://proxy.contoso.com**).
- **Cím**: Adja meg a proxykiszolgáló IP-címét vagy teljesen minősített állomásnevét.
- **Portszám**: Adja meg a proxykiszolgálóhoz társított portszámot.

## <a name="next-step"></a>Következő lépés
[VPN-profilok létrehozása az Intune-ban](vpn-settings-configure.md)
