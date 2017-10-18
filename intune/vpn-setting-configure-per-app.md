---
title: "Alkalmazásonkénti VPN beállítása a Microsoft Intune-ban iOS-eszközökhöz"
titleSuffix: Intune on Azure
description: "Megadhatja, hogy mely felügyelt alkalmazások használhatják VPN-jét az Intune által felügyelt iOS-eszközökön."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/5/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c883ab2b96618502be20583908a4caa52ac5432b
ms.sourcegitcommit: 6004fe51e3cee6fb34514ed0d56e20587ecafeb4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/17/2017
---
# <a name="set-up-per-app-vpn-in-microsoft-intune-for-ios-devices"></a>Alkalmazásonkénti VPN beállítása a Microsoft Intune-ban iOS-eszközökhöz

Megadhatja, hogy mely felügyelt alkalmazások használhatják virtuális magánhálózatát (VPN-jét) az Intune által felügyelt iOS-eszközökön. Alkalmazásonkénti VPN Intune-beli megadása esetén a felhasználó a céges dokumentumok elérésekor automatikusan az Ön VPN-jén keresztül csatlakozik.

## <a name="prerequisites-for-the-per-app-vpn"></a>Az alkalmazásonkénti VPN-re vonatkozó előfeltételek

A VPN-kiszolgáló által identitása igazolásához bemutatott tanúsítványt az eszköznek kérdés nélkül el kell fogadnia. A tanúsítvány automatikus jóváhagyásának biztosításához létre kell hoznia a VPN-kiszolgáló a hitelesítésszolgáltató (CA) által kiadott főtanúsítványát tartalmazó megbízható tanúsítványprofilt. 

Exportálja a tanúsítványt, és adja hozzá a CA-hoz.

1. Nyissa meg a felügyeleti konzolt, a VPN-kiszolgálón.
2. Győződjön meg arról, hogy a VPN-kiszolgáló tanúsítványalapú hitelesítést használ. 
3. Exportálja a megbízható főtanúsítvány fájlját. Ez .cer kiterjesztéssel rendelkezik, és megbízható tanúsítványprofilok létrehozásakor hozzá kell adnia.
4. Adja hozzá a VPN-kiszolgálón való hitelesítéshez használt tanúsítványt kiállító hitelesítésszolgáltató nevét.
    Ha az eszköz által bemutatott hitelesítésszolgáltató szerepel a megbízható hitelesítésszolgáltatóknak a VPN-kiszolgálón található listáján, a VPN-kiszolgáló sikeresen hitelesíti az eszközt.

## <a name="create-a--group-for-your-vpn-users"></a>A VPN-felhasználók csoportjának létrehozása

Válasszon egy meglévő csoportot az Azure Active Directoryban (Azure AD), illetve hozzon létre egy újat, amely az alkalmazásonkénti VPN-hez hozzáféréssel rendelkező tagokat tartalmazza.

1. Nyissa meg az Azure Portalt. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
2. Kattintson a **Csoportok**, majd az **Új csoport** elemre.
3. Adja meg a csoport **nevét**. 
4. Adja meg a csoport **leírását**. 
5. Adja meg a **Hozzárendelt** beállítást a **Tagság típusa** elemhez.
6. Az **Engedélyezi az Office-funkciókat?** kérdésnél válassza a **Nem** lehetőséget.
7. A VPN-felhasználókat név vagy e-mail cím alapján keresheti a **Tagok** panelen.
8. Jelöljön ki minden felhasználót, és kattintson a **Kiválasztás** lehetőségre.
9. Kattintson a **Létrehozás** gombra.

## <a name="create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozása

Importálja az Intune-ban létrehozott profilba a VPN-kiszolgáló a CA által kiadott legfelső szintű tanúsítványát. A megbízható tanúsítványprofil arra utasítja az iOS-eszközt, hogy tekintse automatikusan megbízhatónak a VPN-kiszolgáló által bemutatott CA-t.

1. Nyissa meg az Azure Portalt. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
2. Válassza az **Eszközkonfiguráció**, majd a **Profilok** lehetőséget.
3. Kattintson a **Profil létrehozása** gombra. A **Profil létrehozása** párbeszédpanelen:
    1. Adja meg a **nevet**.
    2. Adja meg a **leírást**.
    3. A **Platform** beállításban válassza az **iOS** lehetőséget.
    4. A **Profil típusa** beállításban válassza a **Megbízható tanúsítvány** a lehetőséget.
4. Kattintson a mappa ikonra, és keresse meg a VPN-felügyeleti konzolból exportált VPN-tanúsítványát (.cer-fájl). Kattintson az OK gombra.
5. Kattintson a **Create** (Létrehozás) gombra.

    ![Megbízható tanúsítványprofil létrehozása](media\vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>SCEP-tanúsítványprofil létrehozása

A megbízható főtanúsítvány-profil lehetővé teszi, hogy az iOS automatikusan megbízhatónak tekintse a VPN-kiszolgálót. Az SCEP-tanúsítvány biztosítja az iOS VPN-ügyfél hitelesítő adatait a VPN-kiszolgálónak. A tanúsítvány lehetővé teszi az iOS-eszközök számára a felhasználó értesítése nélkül csendes hitelesítést a felhasználónév és a jelszó bekérése nélkül. 

1. Nyissa meg az Azure Portalt. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. 
2. Válassza az **Eszközkonfiguráció**, majd a **Profilok** lehetőséget.
3. Kattintson a **Profil létrehozása** gombra. A **Profil létrehozása** párbeszédpanelen:
    1. Adja meg a **nevet**.
    2. Adja meg a **leírást**.
    3. A **Platform** beállításban válassza az **iOS** lehetőséget.
    4. A **Profil típusa** beállításban válassza az **SCEP-tanúsítvány** a lehetőséget.
4. Válassza az **év** lehetőséget, és a **Tanúsítvány érvényességi időtartama** mezőbe írja be a `2` értéket.
5. A **Tulajdonos nevének formátuma** beállításban válassza a **Köznapi név** lehetőséget.
6. A **Tulajdonos alternatív neve** beállításban válassza a **Felhasználói egyszerű név (UPN)** lehetőséget.
7. A **Kulcshasználat** beállításban válassza a **Digitális aláírás** és **Kulcstitkosítás** lehetőséget.
8. A **Kulcsméret (bit)** beállításban válassza a **2048** lehetőséget.
9. Kattintson a Főtanúsítvány elemre, és válasszon egy SCEP-tanúsítványt. Kattintson az OK** gombra.
10. A **Kibővített kulcshasználat** **Név** beállításában adja meg a `Client Authentication` értéket.
11. Az **objektum azonosítójaként** adja meg az `1.3.6.1.5.5.7.3.2` értéket.
12. Kattintson a **Hozzáadás** gombra.
13. Adja meg a ***kiszolgáló URL-címét***, majd kattintson a **Hozzáadás** gombra.
14. Kattintson az OK** gombra.
15. Kattintson a **Create** (Létrehozás) gombra.

    ![SCEP-tanúsítványprofil létrehozása](media\vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Alkalmazásonkénti VPN-profil létrehozása

A VPN-profil tartalmazza az ügyfél-hitelesítő adatokat tartalmazó SCEP-tanúsítványt, a VPN-hez tartozó kapcsolati adatokat és az Alkalmazásonkénti VPN jelzőt az Alkalmazásonkénti VPN funkció használatának engedélyezéséhez az iOS alkalmazásban.

1. Nyissa meg az Azure Portalt. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
2. Válassza az **Eszközkonfiguráció**, majd a **Profilok** lehetőséget.
3. Kattintson a **Profil létrehozása** gombra. A **Profil létrehozása** párbeszédpanelen:
    1. Adja meg a **nevet**.
    2. Adja meg a **leírást**.
    3. A **Platform** beállításban válassza az **iOS** lehetőséget.
    4. A **Profil típusa** beállításban válassza a **VPN** lehetőséget.
4. Válassza az **Alapszintű VPN** lehetőséget. Az **Alapszintű VPN** párbeszédpanelen:
    1. Adja meg a **kapcsolat nevét**.
    2. Adja meg a **kiszolgáló IP-címét vagy teljes tartománynevét**.
    3. A **Hitelesítési módszer** beállításban válassza a **Tanúsítványok** lehetőséget.
    4. Válassza ki az SCEP-tanúsítványt a **Hitelesítési tanúsítvány** területen, és kattintson az **OK** gombra.
    5. A **kapcsolat típusaként** válassza a VPN-t.
    6. Ha szükséges, konfigurálja a VPN jellemzőit.
    7. Válassza a **Megosztott protokollbújtatás** letiltását.
5. Kattintson az **Automatikus VPN** elemre. Az **Automatikus VPN** párbeszédpanelen:
    1. Az **Automatikus VPN típusa** beállításban válassza az **Alkalmazásonkénti VPN** lehetőséget.
    2. Írja be a VPN URL-címét, majd kattintson a **Hozzáadás** gombra.
    3. Kattintson az OK** gombra.
6. Kattintson az OK** gombra.
7. Kattintson a **Create** (Létrehozás) gombra.

    ![Alkalmazásonkénti VPN-profil létrehozása](media\vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Alkalmazás társítása a VPN-profillal

Miután hozzáadta a VPN-profilt, társítsa az alkalmazást és a Microsoft Azure Active Directory-csoportot a profillal.

1. Nyissa meg az Azure Portalt. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
2. Válassza a **Mobilalkalmazások** lehetőséget.
3. Kattintson az **Alkalmazások** elemre.
4. Válassza ki az alkalmazást az alkalmazások listájából.
5. Kattintson a **Hozzárendelések** lehetőségre
6. Kattintson a **Csoportok kiválasztása**, elemre a korábban meghatározott csoportok kijelöléséhez. Kattintson a **Kiválasztás** lehetőségre.
7. A **Hozzárendelések** panelen válassza a **Típus** beállításban a **Szükséges** értéket.
8. Válassza ki a VPN-definíciót a **VPN-ekhez**.
 
    > [!NOTE]  
    > Egyes esetekben akár egy percig is eltarthat, amíg a VPN-definíció kikeresi az értéket. Várjon 3–5 percet, mielőtt a **Mentésre** kattintana.

9. Kattintson a **Save** (Mentés) gombra.

    ![Alkalmazás társítása a VPN-nel](media\vpn-per-app-app-to-vpn.png)

## <a name="verify-the-connection-on-the-ios-device"></a>A kapcsolat ellenőrzése az iOS-eszközön

Az alkalmazásonkénti VPN beállítását és az alkalmazáshoz való társítását követően ellenőrizze, hogy az internetkapcsolat megfelelően működik-e az eszközről.

### <a name="before-you-attempt-to-connect"></a>Mielőtt megpróbálna kapcsolódni

 - Az iOS 7-es vagy újabb verziójának kell futnia.
 - Győződjön meg arról, hogy az *összes* fent említett szabályzatot üzembe helyezte ugyanazon felhasználói csoporthoz. Ennek elmulasztása mindenképpen meggátolja az alkalmazásonkénti VPN működését.  
 - Győződjön meg róla, hogy a támogatott külső VPN-alkalmazás telepítve van. A rendszer a következő VPN-alkalmazásokat támogatja:
    - Pulse Secure
    - Checkpoint
    - F5
    - SonicWall

### <a name="connect-using-the-per-app-vpn"></a>Alkalmazásonkénti VPN-en keresztüli csatlakozás

A VPN kiválasztása vagy a hitelesítő adatok megadása nélküli csatlakozással ellenőrizze a beavatkozás nélküli működést. A beavatkozás nélküli működés azt jelenti, hogy:

 - Az eszköz nem kéri Önt, hogy minősítse megbízhatónak a VPN-kiszolgálót. Ez azt jelenti, hogy nem jelenik meg a **dinamikus megbízhatósági** párbeszédpanel.
 - Nem kell beírnia a hitelesítő adatokat.
 - Amint a Csatlakozás gombra koppint, csatlakozik a VPN-hez.

Ellenőrizze a kapcsolatot egy iOS-eszközön.

1. Koppintson a VPN-alkalmazásra.
2. Koppintson a **Csatlakozás** gombra.  
A VPN további kérdések megjelenítése nélkül sikeresen kapcsolódik.

<!-- ## Troubleshooting the Per-App VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>További lépések

- Az iOS-es beállítások ellenőrzéséhez lásd: [iOS-eszközökre vonatkozó VPN-beállítások a Microsoft Intune-ban](vpn-settings-ios.md).
-  A VPN-beállításokkal és az Intune-nal kapcsolatos további információkért lásd: [A VPN-beállítások konfigurálása a Microsoft Intune-ban](vpn-settings-configure.md).