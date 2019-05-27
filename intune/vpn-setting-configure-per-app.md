---
title: Alkalmazásonkénti VPN beállítása iOS eszközökhöz az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A cikk útmutatást nyújt az előfeltételek áttekintéséhez, csoport létrehozásához a virtuális magánhálózat (VPN) felhasználói számára, az SCEP-tanúsítványprofil hozzáadásához, az alkalmazásonkénti VPN-profil beállításához és alkalmazások VPN-profilhoz történő hozzáadásához iOS-eszközök esetében a Microsoft Intune-ban. Továbbá a VPN-kapcsolat eszközön történő ellenőrzéséhez szükséges lépéseket is bemutatja.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: df4a3dc5c45a909e2c56b1fd741445bc6485e1e8
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044467"
---
# <a name="set-up-per-app-virtual-private-network-vpn-for-ios-devices-in-intune"></a>Állítsa be alkalmazásonkénti virtuális magánhálózati (VPN) iOS-eszközökhöz az Intune-ban

A Microsoft Intune hozzon létre, és virtuális magánhálózatok (VPN) az alkalmazáshoz társított használja. Ez a szolgáltatás "alkalmazásonkénti VPN" nevezzük. Úgy dönt, hogy a felügyelt alkalmazások használhatják a VPN-jét az Intune által felügyelt eszközökön. Alkalmazásonkénti VPN-ek használata esetén a végfelhasználók automatikusan a VPN-kapcsolaton keresztül csatlakozzon és hozzáférhet a munkahelyi erőforrásokhoz, például dokumentumok.

Ez a funkció az alábbiakra vonatkozik:

- iOS 9-es és újabb verziók

A VPN-szolgáltató dokumentációban megtekintheti, ha a VPN-JE támogatja-e az alkalmazásonkénti VPN.

Ez a cikk bemutatja, hogyan hozhat létre alkalmazásonkénti VPN-profil, és hozzárendelni a profilt az alkalmazások. Ezek a lépések használatával hozzon létre egy zökkenőmentes alkalmazásonkénti VPN-élmény a végfelhasználók számára. A legtöbb VPN-EK, amelyek támogatják az alkalmazásonkénti VPN a felhasználó megnyitja az alkalmazást, és automatikusan csatlakozik a VPN-t.

Egyes VPN-eket felhasználónév- és jelszóalapú hitelesítés az alkalmazásonkénti VPN engedélyezése. Ami azt jelenti, felhasználók meg kell adnia egy felhasználónevet és jelszót szeretne csatlakozni a VPN-t.

## <a name="per-app-vpn-with-zscaler"></a>Alkalmazásonkénti VPN Zscaler szolgáltatással

Zscaler privát hozzáférést (ZPA) együttműködik az Azure Active Directory (Azure AD-) hitelesítés. ZPA használatakor nem kell a [megbízható tanúsítvány](#create-a-trusted-certificate-profile) vagy [SCEP- vagy PKCS-tanúsítvány](#create-a-scep-or-pkcs-certificate-profile) (ebben a cikkben ismertetett) profilok. Ha rendelkezik egy alkalmazásonkénti VPN-profil beállítása tartozó Zscaler, nyissa meg a társított alkalmazások automatikusan csatlakozni nem ZPA. Ehelyett a felhasználónak kell először jelentkezzen be a Zscaler alkalmazást. Ezt követően a távelérési korlátozva a társított alkalmazások.

## <a name="prerequisites-for-per-app-vpn"></a>Az alkalmazásonkénti VPN-re vonatkozó előfeltételek

> [!IMPORTANT]
> Előfordulhat, hogy a VPN-szállítója egyéb alkalmazásonkénti VPN-hez, például a adott hardverekhez vagy a licencelési követelményeket. Mindenképp ellenőrizze a vonatkozó dokumentációt, és gondoskodjon a követelményeknek való megfelelésről, mielőtt alkalmazásonkénti VPN-t állítana be az Intune-ban.

A VPN-kiszolgáló által identitása igazolásához bemutatott tanúsítványt az eszköznek kérdés nélkül el kell fogadnia. Erősítse meg a tanúsítvány automatikus jóváhagyásának, hozzon létre egy megbízható hitelesítésszolgáltatói tanúsítványprofilt, amely tartalmazza a VPN-kiszolgáló legfelső szintű tanúsítványát által a hitelesítésszolgáltató (CA). 

#### <a name="export-the-certificate-and-add-the-ca"></a>Exportálja a tanúsítványt, és adja hozzá a hitelesítésszolgáltató

1. A VPN-kiszolgálón nyissa meg a felügyeleti konzolon.
2. Győződjön meg arról, hogy a VPN-kiszolgáló tanúsítványalapú hitelesítést használ. 
3. Exportálja a megbízható főtanúsítvány fájlját. Ez .cer kiterjesztéssel rendelkezik, és megbízható tanúsítványprofilok létrehozásakor hozzá kell adnia.
4. Adja hozzá a VPN-kiszolgálón való hitelesítéshez használt tanúsítványt kiállító hitelesítésszolgáltató nevét.

    Ha az eszköz által bemutatott hitelesítésszolgáltató megegyezik a hitelesítésszolgáltató a megbízható Hitelesítésszolgáltatói listában a VPN-kiszolgálón, majd a VPN-kiszolgáló sikeresen hitelesíti az eszközt.

## <a name="create-a-group-for-your-vpn-users"></a>Csoport létrehozása VPN-felhasználók számára

Hozzon létre, vagy válasszon egy meglévő csoportot az Azure Active Directoryban (Azure AD) a felhasználók vagy eszközök alkalmazásonkénti VPN-használó. Új csoport létrehozásához lásd: [adja hozzá a felhasználók és eszközök rendszerezéséhez csoportok](groups-add.md).

## <a name="create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozása

Importálja az Intune-ban létrehozott profilba a VPN-kiszolgáló a CA által kiadott legfelső szintű tanúsítványát. A megbízható tanúsítványprofil arra utasítja az iOS-eszközt, hogy tekintse automatikusan megbízhatónak a VPN-kiszolgáló által bemutatott CA-t.

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:
    - **Name (Név)**
    - **Leírás**
    - **Platform**: Válassza ki **iOS**.
    - **Profil típusa**: Válassza ki **megbízható tanúsítvány**.
4. Válassza ki a mappa ikont, és keresse meg a a VPN-felügyeleti konzolból exportált VPN-tanúsítványának (.cer fájl). 
5. Válassza ki **OK** > **létrehozása**.

    ![Hozzon létre egy megbízható hitelesítésszolgáltatói tanúsítványprofilt, az iOS-eszközök Microsoft Intune-ban](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-or-pkcs-certificate-profile"></a>Egy SCEP- vagy PKCS-tanúsítványprofil létrehozása

A megbízható főtanúsítvány-profil lehetővé teszi, hogy az eszköz automatikusan megbízhatónak a VPN-kiszolgáló. Az SCEP- vagy PKCS-tanúsítvány az IOS-es VPN-ügyfél a VPN-kiszolgáló hitelesítő adatokat biztosít. A tanúsítvány lehetővé teszi, hogy az eszköz számára a felhasználónév és jelszó értesítése nélkül csendes hitelesítést. 

Konfigurálásához, és az ügyfél-hitelesítési tanúsítvány hozzárendelése, tekintse meg a következő cikkeket:

- [SCEP-tanúsítványok konfigurálása és kezelése az Intune-nal](certificates-scep-configure.md)
- [PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal](certficates-pfx-configure.md)

Mindenképpen konfigurálja a tanúsítványt az ügyfél-hitelesítéshez. Közvetlenül a SCEP-tanúsítványprofilok állíthat (**kibővített kulcshasználat** lista > **ügyfél-hitelesítés**). A PKCS használatára állítsa be a tanúsítványsablon a hitelesítésszolgáltató (CA) az ügyfél-hitelesítéshez.

![A Microsoft Intune, beleértve a tulajdonos nevének formátuma, kulcshasználat, kibővített kulcshasználat és további SCEP-tanúsítványprofil létrehozásához](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Alkalmazásonkénti VPN-profil létrehozása

A VPN-profil tanúsítványt tartalmaz, az SCEP- vagy PKCS és az ügyfél-hitelesítő adatok, a VPN-hez, a kapcsolatadatokat, és az alkalmazásonkénti VPN jelzőt az alkalmazásonkénti VPN funkció engedélyezéséhez használja az iOS-alkalmazás.

1. A **Intune**válassza **eszközkonfiguráció** > **profilok** > **profil létrehozása**. 
2. Adja meg a következő tulajdonságokat: 
    - **Name (Név)**
    - **Leírás**
    - **Platform**: Válassza ki **iOS**.
    - **Profil típusa**: Válassza ki **VPN**.
3. A **kapcsolattípus**, válassza ki a VPN-ügyfél alkalmazást.
4. Válassza az **Alapszintű VPN** lehetőséget. [iOS-es VPN-beállítások](vpn-settings-ios.md) felsorol és ismertet minden beállítást. Alkalmazásonkénti VPN használata esetén mindenképp listában állítsa be a következő tulajdonságokat: 
    
    - **Hitelesítési módszer**: Válassza ki **tanúsítványok**. 
    - **Hitelesítési tanúsítvány**: Válassza ki a meglévő SCEP- vagy PKCS-tanúsítvány > **OK**.      
    - **Vegyes Alagútkezelés**: Válassza ki **letiltása** kényszerítése minden forgalom a VPN-alagút használandó, ha a VPN-kapcsolat aktív. 

      ![Egy alkalmazásonkénti VPN-profilt adja meg a kapcsolat, IP-cím vagy teljes Tartományneve, a hitelesítési módszert, és a Microsoft Intune-ban tunning felosztása](./media/vpn-per-app-create-vpn-profile.png)

    Az egyéb beállításokkal további információkért lásd: [VPN-beállítások IOS-es](vpn-settings-ios.md).

5. Válassza ki **automatikus VPN** > **automatikus VPN típusának** > **alkalmazásonkénti VPN**

    ![Az Intune-ban állítsa be az automatikus VPN alkalmazásonkénti VPN iOS-eszközökön](./media/vpn-per-app-automatic.png)

6. Válassza ki **OK** > **OK** > **létrehozása**.

## <a name="associate-an-app-with-the-vpn-profile"></a>Alkalmazás társítása a VPN-profillal

Miután hozzáadta a VPN-profilt, társítsa az alkalmazást és a Microsoft Azure Active Directory-csoportot a profillal.

1. Az **Intune-ban** válassza az **Ügyfélalkalmazások** > **Alkalmazások** elemet.
2. Válasszon ki egy alkalmazást a listából > **hozzárendelések** > **csoport hozzáadása**.
3. A **hozzárendelés-típus**válassza **szükséges** vagy **regisztrált eszközökhöz elérhető**.
4. Válassza ki **tartalmazott csoportok** > **válassza ki a befoglalandó csoportokat** > Válassza ki azt a csoportot [létrehozott](#create-a-group-for-your-vpn-users) (a jelen cikkben) > **kiválasztása**.
5. A **VPN-eket**, válassza ki az alkalmazásonkénti VPN-profil [létrehozott](#create-a-per-app-vpn-profile) (a jelen cikkben).

    ![Egy alkalmazás a Microsoft Intune-ban az alkalmazásonkénti VPN-profil hozzárendelése](./media/vpn-per-app-app-to-vpn.png)

6. Válassza ki **OK** > **mentése**.

Alkalmazás és a egy profil közötti társítás eltávolítása során a következő eszköz bejelentkezését az alábbi feltételek mindegyikének létezik:

- Az alkalmazás meg lett jelölve kötelező telepítéshez.
- A profil és az alkalmazás ugyanazt a csoportot célozza.
- Az alkalmazásonkénti VPN-konfigurációt eltávolítja az alkalmazás-hozzárendelésből.

Alkalmazás és a egy profil közötti társítás továbbra is fennáll, addig, amíg a felhasználó kérelmezi egy újratelepítése vállalati portálról, ha az alábbi feltételek mindegyikének létezik:

- Az alkalmazás meg lett jelölve választható telepítéshez.
- A profil és az alkalmazás ugyanazt a csoportot célozza.
- A végfelhasználó kért alkalmazás telepítése a vállalati portálról, amely alkalmazás és az eszközre telepítendő profil eredményez.
- Módosítja az alkalmazásonkénti VPN-konfigurációt, illetve eltávolítja az alkalmazás-hozzárendelésből.

## <a name="verify-the-connection-on-the-ios-device"></a>A kapcsolat ellenőrzése az iOS-eszközön

Az alkalmazásonkénti VPN beállítását és az alkalmazáshoz való társítását követően ellenőrizze, hogy az internetkapcsolat megfelelően működik-e az eszközről.

### <a name="before-you-attempt-to-connect"></a>Mielőtt megpróbálna kapcsolódni

 - Ellenőrizze, hogy az összes fent említett házirend ugyanabban a csoportban üzembe. Az alkalmazásonkénti VPN élmény nem fog működni.
 - Ha a Pulse Secure VPN-alkalmazást, vagy egy egyéni VPN-ügyfél alkalmazást használ, válassza a alkalmazási rétegbeli vagy a csomag-réteg-Alagútkezelés használata. A **Szolgáltatótípus** értékét az alkalmazásrétegbeli alagútkezeléshez állítsa az **alkalmazásproxy** lehetőségre, a csomagrétegbeli alagútkezeléshez pedig állítsa a **csomagalagút** lehetőségre. A VPN-szolgáltató dokumentációban, győződjön meg arról, hogy a megfelelő értéket használja.

### <a name="connect-using-the-per-app-vpn"></a>Alkalmazásonkénti VPN-en keresztüli csatlakozás

A VPN kiválasztása vagy a hitelesítő adatok megadása nélküli csatlakozással ellenőrizze a beavatkozás nélküli működést. A beavatkozás nélküli működés azt jelenti, hogy:

 - Az eszköz nem megkérdezi, hogy bízzon meg a VPN-kiszolgáló. Ez azt jelenti, hogy a felhasználó nem jelennek meg a **dinamikus megbízhatósági** párbeszédpanel bezárásához.
 - A felhasználó nem rendelkezik beírnia a hitelesítő adatokat.
 - A felhasználó eszköze a VPN-hez csatlakoztatva van, amikor a felhasználó megnyitja a társított alkalmazások közül.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>További lépések

- Az iOS-es beállítások ellenőrzéséhez lásd: [iOS-eszközökre vonatkozó VPN-beállítások a Microsoft Intune-ban](vpn-settings-ios.md).
- VPN-beállításokkal és az Intune-nal kapcsolatos további információkért lásd: [VPN-beállítások konfigurálása a Microsoft Intune-ban](vpn-settings-configure.md).
