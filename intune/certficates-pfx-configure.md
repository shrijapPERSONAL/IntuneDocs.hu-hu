---
title: PKCS-tanúsítványok használata az Azure-beli Microsoft Intune-nal | Micrososft Docs
description: 'Nyílt kulcsú titkosításiszabvány- (PKCS-) tanúsítványok hozzáadása vagy létrehozása a Microsoft Intune-nal a következő lépésekben: gyökértanúsítvány exportálása, tanúsítványsablon konfigurálása, Microsoft Intune Tanúsítvány-összekötő (NDES) letöltése és telepítése, eszközkonfigurációs profil létrehozása, PKCS-tanúsítványprofil létrehozása az Azure-ban és a saját hitelesítésszolgáltatónál.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b3bfe76173eff76a3175952bef5c6e23ad5e429
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271541"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-tanúsítványok konfigurálása és használata az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A tanúsítványok az olyan céges forrásokhoz történő hozzáférés hitelesítését és biztonságossá tételét szolgálják, mint a VPN és a saját WiFi hálózat. Ez a cikk a PKCS-tanúsítványok exportálását, majd Intune-profilhoz történő hozzáadását ismerteti. 

## <a name="requirements"></a>Követelmények

A PKCS-tanúsítványok Intune-beli használata előtt ellenőrizze, hogy rendelkezik-e az alábbi infrastruktúrával:

- **Active Directory-tartomány**: A jelen szakaszban felsorolt összes kiszolgálónak csatlakoznia kell az Active Directory-tartományához.

  Az AD DS telepítéséről és konfigurálásáról [Az AD DS tervezése és előkészítése](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) című témakörben talál további információt.

- **Hitelesítésszolgáltató** (CA): vállalati hitelesítésszolgáltató (CA)

  Az Active Directory tanúsítványszolgáltatások (AD CS) telepítéséről és konfigurálásáról a [Lépésenkénti útmutató az Active Directory tanúsítványszolgáltatásokhoz](https://technet.microsoft.com/library/cc772393) című témakörben talál további információt.

  > [!WARNING]
  > Az Intune követelményei szerint az AD CS-t vállalati hitelesítésszolgáltatóval, és nem önálló hitelesítésszolgáltatóval kell futtatni.

- **Egy ügyfél**: a vállalati hitelesítésszolgáltatóhoz való csatlakozáshoz

- **Főtanúsítvány**: a vállalati hitelesítésszolgáltatótól származó főtanúsítvány exportált másolata

- **Microsoft Intune Tanúsítvány-összekötő**: Az Azure Portal webhelyről töltse le a **Tanúsítvány-összekötő** telepítőjét (**NDESConnectorSetup.exe**). 

  Az NDES tanúsítvány-összekötő a Federal Information Processing Standard (FIPS) módot is támogatja. A FIPS nem kötelező, de lehet tanúsítványokat kibocsátani és visszavonni, ha engedélyezve van.

- **Windows Server**: a Microsoft Intune Tanúsítvány-összekötőt üzemelteti (NDESConnectorSetup.exe)

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól

VPN-, WiFi- és egyéb erőforrással történő hitelesítéshez minden eszköz esetében fő vagy köztes hitelesítésszolgáltatói tanúsítványra van szükség. Az alábbi lépések ismertetik a szükséges tanúsítvány beszerzését a vállalati hitelesítésszolgáltatótól.

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyisson meg rendszergazdaként egy parancssort.
3. Exportálja a hitelesítésszolgáltatói főtanúsítványt (.cer) egy olyan helyre, ahol később hozzáférhet.

   Például:

4. Ha a varázsló befejeződött, még mielőtt bezárná, kattintson **Launch the Certificate Connector UI**(Certificate Connector felhasználói felületének indítása) lehetőségre.

   `certutil -ca.cert certnew.cer`

   További információkárt lásd: [Certutil-feladatok a tanúsítványok kezeléséhez](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyissa meg a **Hitelesítésszolgáltató** konzolt, majd kattintson a jobb gombbal a **Tanúsítványsablonok** elemre, és válassza a **Kezelés** lehetőséget.
3. Keresse meg a **Felhasználói** tanúsítványsablont, kattintson rá a jobb gombbal, majd válassza a **Sablon duplikálása** elemet. Ekkor megnyílik az **Új sablon tulajdonságai** terület.
4. A **Kompatibilitás** lapon:

  - Állítsa a **Hitelesítésszolgáltató** beállítást **Windows Server 2008 R2** értékre.
  - Állítsa a **Tanúsítvány kezdeményezettje** beállítást **Windows 7 / Server 2008 R2** értékre.

5. Állítsa be az **Általános** lapon a **Sablon megjelenítendő neve** beállítást egy aktuális névre.

   > [!WARNING]
   > A **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*. Jegyezze fel a sablon nevét, mert később szüksége lesz rá.

6. A **Kérelmek kezelése** lapon válassza **A titkos kulcs exportálható** beállítást.
7. A **Titkosítás** lapon ellenőrizze, hogy a **Minimális kulcshossz** értéke 2048.
8. A **Tulajdonos neve** lapon válassza a **Kérelemben megadva** lehetőséget.
9. A **Bővítmények** lapon ellenőrizze, hogy az **Alkalmazásszabályzatok** területen láthatók-e a következő elemek: Titkosított fájlrendszer, Biztonságos e-mail, Ügyfél-hitelesítés.

    > [!IMPORTANT]
    > iOS-tanúsítványsablonok esetén a **Kiterjesztések** lapon frissítse a **Kulcshasználat** beállítást, és ügyeljen rá, hogy **Az aláírás igazolja az eredetet** jelölőnégyzet ne legyen bejelölve.

10. A **Biztonság** lapon vegye fel annak a kiszolgálónak a fiókját, amelyen telepíti a Microsoft Intune Tanúsítvány-összekötőt. Adja meg a fiók számára az **Olvasás** és **Beléptetés** engedélyeket.
11. A tanúsítvány mentéséhez kattintson az **Alkalmaz**, majd az **OK** elemre.
12. Zárja be a **Tanúsítvány-sablonok konzolt**.
13. A **Hitelesítésszolgáltató** konzolon kattintson a jobb gombbal a **Tanúsítványsablonok**, az **Új**, majd a **Kiállítandó tanúsítványsablon** elemekre. Válassza ki az iménti lépésekben létrehozott sablont, majd kattintson az **OK** gombra.
14. Ahhoz, hogy a kiszolgáló az Intune-ban regisztrált eszközök és felhasználók nevében kezelhesse a tanúsítványokat, kövesse az alábbi lépéseket:

    1. Kattintson a jobb gombbal a hitelesítésszolgáltatóra, majd kattintson a **Tulajdonságok** elemre.
    2. A biztonság lapon vegye fel annak a kiszolgálónak a fiókját, amelyen futtatja a Microsoft Intune Tanúsítvány-összekötőt. A fiók számára adja meg a **Tanúsítványok kiadása és kezelése** és a **Tanúsítványkérés** engedélyeket.

15. Jelentkezzen ki a vállalati hitelesítésszolgáltatóból.

## <a name="download-install-and-configure-the-certificate-connector"></a>A tanúsítvány-összekötő letöltése, telepítése és konfigurálása

![ConnectorDownload][ConnectorDownload]

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközök konfigurálása**, majd a **Hitelesítésszolgáltató** lehetőséget.
4. Válassza a **Hozzáadás**, majd az **Összekötőfájl letöltése** lehetőséget. Mentse a letöltést egy olyan helyre, amelyhez hozzá tud férni a telepítéshez használt kiszolgálón.
5. A letöltés befejezése után jelentkezzen be a kiszolgálóra. Ha ez megvan:

    1. Győződjön meg róla, hogy telepítve van-e a .NET 4.5-keretrendszer, mivel arra szüksége van az NDES tanúsítvány-összekötőjének. A .NET 4.5-keretrendszer automatikusan részen a Windows Server 2012 R2 és újabb verzióknak.
    2. Futtassa a telepítőprogramot (NDESConnectorSetup.exe), és fogadja el az alapértelmezett helyet. A telepítő az összekötőt a `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe` helyen telepíti. A Telepítőbeállítás oldalon válassza a **PFX terjesztése**, lehetőséget. Folytassa és fejezze be a telepítést.

6. A Hálózati eszközök tanúsítványigénylési szolgáltatásának összekötője megnyitja a **Beléptetés** lapot. Az Intune-hoz való kapcsolódás engedélyezéséhez válassza a **Bejelentkezés** lehetőséget, és adjon meg egy globális rendszergazdai engedélyekkel rendelkező fiókot.
7. A **Speciális** lapon kijelölve hagyhatja a **Use this computer's SYSTEM account (default)** (A számítógép SYSTEM fiókjának használata (alapértelmezett)) feliratú választógombot.
8. Kattintson az **Alkalmaz**, majd a **Bezárás** gombra.
9. Lépjen vissza az Azure Portalra (**Intune** > **Eszközkonfiguráció** > **Hitelesítésszolgáltató**). Néhány pillanat múlva egy zöld pipajel jelenik meg, és a **Kapcsolat állapota** **Aktív** lesz. Az összekötő kiszolgáló mostantól kapcsolatba tud lépni az Intune-nal.

> [!NOTE]
> Az NDES tanúsítvány-összekötő tartalmazza a TLS 1.2 támogatását. Ha tehát a kiszolgáló, amelyen az NDES tanúsítvány-összekötő telepítve van, támogatja a TLS 1.2-t, akkor a TLS 1.2 lesz használva. Amennyiben a kiszolgáló nem támogatja a TLS 1.2 verziót, a TLS 1.1 lesz használva. Az eszközök és a kiszolgáló közötti hitelesítéshez jelenleg a TLS 1.1 van használatban.

## <a name="create-a-device-configuration-profile"></a>Eszközkonfigurációs profil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza az **Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.

   ![NavigateIntune][NavigateIntune]

3. Adja meg a következő tulajdonságokat:

  - **Név** a profil számára
  - Igény szerint hozzáadhat egy leírást
  - **Platform**, amelyen telepíteni kell a profilt
  - A **Profiltípust** állítsa **Megbízható tanúsítványra**

4. Nyissa meg a **Beállítások** lapot, és adja meg a korábban exportált hitelesítésszolgáltatói főtanúsítvány .cer fájlját.

   > [!NOTE]
   > A **3. lépésben** választott platformtól függően lehetősége lehet **Céltárolót** választani a tanúsítvány számára.

   ![ProfileSettings][ProfileSettings]

5. A profil mentéséhez kattintson az **OK**, majd a **Létrehozás** elemre.
6. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS-tanúsítványprofil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza az **Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

  - **Név** a profil számára
  - Igény szerint hozzáadhat egy leírást
  - **Platform**, amelyen telepíteni kell a profilt
  - A **Profiltípust** állítsa **PKCS-tanúsítványra**

4. Nyissa meg a **Beállítások** lapot, és adja meg a következő tulajdonságokat:

  - **Megújítási küszöb (%)** – Az ajánlott érték 20%.
  - **Tanúsítvány érvényességi időtartama** – Ha nem módosította a tanúsítványsablont, akkor a megadott beállítás valószínűleg egy év.
  - **Hitelesítésszolgáltató** – A vállalati hitelesítésszolgáltató belső teljes tartományneve (FQDN).
  - **Hitelesítésszolgáltató neve** – A vállalati hitelesítésszolgáltató neve, ami nem feltétlenül azonos az előző elemmel.
  - **Tanúsítványsablon neve** – A korábban létrehozott sablon neve. Emlékeztető: a **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*.
  - **Tulajdonos nevének formátuma** – Ennél a beállításnál, ha nincs eltérő követelmény, a **Köznapi nevet** adja meg.
  - **Tulajdonos alternatív neve** – Ennél a beállításnál, ha nincs eltérő követelmény, az **Egyszerű felhasználónevet (UPN)** adja meg.
  - **Kibővített kulcshasználat** – Ha a jelen cikk [Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál](#configure-certificate-templates-on-the-certification-authority) szakaszának 10. lépésében ismertetett alapértelmezett beállításokat használta, adja meg a következő **Előre meghatározott értékeket** a kijelölt területről:
    - **Általános felhasználás**
    - **Ügyfél-hitelesítés**
    - **Biztonságos e-mail**
  - **Főtanúsítvány** – (Androidos profilokhoz) A jelen cikk [Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól](#export-the-root-certificate-from-the-enterprise-ca) szakaszának 3. lépésében exportált .cer fájl.

5. A profil mentéséhez kattintson az **OK**, majd a **Létrehozás** elemre.
6. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="next-steps"></a>További lépések
[SCEP-tanúsítványok használata](certificates-scep-configure.md), vagy [PKCS-tanúsítványok kibocsátása egy Symantec PKI-kezelő webszolgáltatásból](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Nyissa meg az Intune oldalt az Azure Portalon, és hozzon létre egy új profilt egy megbízható tanúsítványhoz"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Hozzon létre egy profilt, és töltsön fel egy megbízható tanúsítványt"
[ConnectorDownload]: ./media/certificates-download-connector.png "Töltse le a tanúsítvány-összekötőt az Azure Portalról"  
