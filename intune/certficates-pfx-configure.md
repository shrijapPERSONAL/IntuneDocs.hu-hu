---
title: PKCS-tanúsítványok használata az Azure-beli Microsoft Intune-nal | Micrososft Docs
description: 'Nyílt kulcsú titkosításiszabvány- (PKCS-) tanúsítványok hozzáadása vagy létrehozása a Microsoft Intune-nal a következő lépésekben: gyökértanúsítvány exportálása, tanúsítványsablon konfigurálása, Microsoft Intune Tanúsítvány-összekötő (NDES) letöltése és telepítése, eszközkonfigurációs profil létrehozása, PKCS-tanúsítványprofil létrehozása az Azure-ban és a saját hitelesítésszolgáltatónál.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573cdf8746b9eaf593a33cd943b69a2dd83030ae
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49391603"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-tanúsítványok konfigurálása és használata az Intune-nal

> [!IMPORTANT]
> A jelen cikkben ismertetett S/MIME funkció jelenleg fejlesztés alatt áll. Emiatt az S/MIME funkciót ideiglenesen eltávolítottuk az Intune-ból. A funkció újbóli kibocsátását követően ez a megjegyzés törlésre kerül.

A tanúsítványok hitelesítik és védik az olyan céges forrásokhoz történő hozzáférést, mint a VPN és a saját WiFi-hálózat. Ez a cikk a PKCS-tanúsítványok exportálását, majd Intune-profilhoz történő hozzáadását ismerteti.

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

  Az összekötő dolgozza fel a hitelesítéshez vagy S/MIME e-mail-aláíráshoz használt PKCS-tanúsítványkérelmeket.

  Az NDES tanúsítvány-összekötő a Federal Information Processing Standard (FIPS) módot is támogatja. A FIPS nem kötelező, de lehet tanúsítványokat kibocsátani és visszavonni, ha engedélyezve van.

- **Microsoft Intune-hoz készült PFX tanúsítvány-összekötő**: Ha S/MIME e-mail-titkosítás használatát tervezi, akkor töltse le a **Microsoft Intune-hoz készült PFX tanúsítvány-összekötő** telepítőjét (**PfxCertificateConnectorBootstrapper.exe**) az Azure Portal használatával. Az összekötő az Intune-ba importált PFX-fájlokra vonatkozó kérelmeket dolgozza fel S/MIME e-mail-titkosításhoz egy adott felhasználó számára.

- **Windows Server**: gazdaszámítógép a következőkhöz:

  - Microsoft Intune Tanúsítvány-összekötő (NDESConnectorSetup.exe) hitelesítéshez és S/MIME e-mail-aláíráshoz
  - A Microsoft Intune-hoz készült PFX tanúsítvány-összekötő (PfxCertificateConnectorBootstrapper.exe) S/MIME e-mail-titkosításhoz.

  A két összekötőt (**Microsoft Intune Tanúsítvány-összekötő** és **A Microsoft Intune-hoz készült PFX tanúsítvány-összekötő**) futtathatja ugyanazon a kiszolgálón.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól

VPN-, WiFi- vagy egyéb erőforrással történő hitelesítéshez minden eszköz esetében fő vagy köztes hitelesítésszolgáltatói tanúsítványra van szükség. Az alábbi lépések ismertetik a szükséges tanúsítvány beszerzését a vállalati hitelesítésszolgáltatótól.

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyisson meg rendszergazdaként egy parancssort.
3. Exportálja a hitelesítésszolgáltatói főtanúsítványt (.cer) egy olyan helyre, ahol később hozzáférhet.
4. Ha a varázsló befejeződött, még mielőtt bezárná, kattintson **Launch the Certificate Connector UI**(Certificate Connector felhasználói felületének indítása) lehetőségre.

   `certutil -ca.cert certnew.cer`

   További információkárt lásd: [Certutil-feladatok a tanúsítványok kezeléséhez](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyissa meg a **Hitelesítésszolgáltató** konzolt, majd kattintson a jobb gombbal a **Tanúsítványsablonok** elemre, és válassza a **Kezelés** lehetőséget.
3. Keresse meg a **Felhasználó** tanúsítványsablont, kattintson rá a jobb gombbal, majd válassza a **Sablon megkettőzése** lehetőséget. Ekkor megnyílik az **Új sablon tulajdonságai** terület.

    > [!NOTE]
    > S/MIME e-mail-aláírás és titkosítás esetén sok rendszergazda külön tanúsítványt használ az aláíráshoz és a titkosításhoz. Ha a Microsoft Active Directory Tanúsítványszolgáltatást használja, akkor használhatja az **Exchange Signature Only** (csak Exchange-aláírás) sablont S/MIME e-mail-aláírási tanúsítványokhoz, és az **Exchange User** (Exchange felhasználó) sablont S/MIME titkosítási tanúsítványokhoz.  Külső hitelesítésszolgáltató igénybe vétele esetén ajánlott áttekinteni a tőlük kapott útmutatót az aláírási és titkosítási sablonok beállításához.

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
11. A tanúsítvány mentéséhez válassza ki az **Alkalmaz** > **OK** elemet. Zárja be a **Tanúsítvány-sablonok konzolt**.
12. A **Hitelesítésszolgáltató** konzolon kattintson a jobb gombbal a **Tanúsítványsablonok** > **Új** > **Kiállítandó tanúsítványsablon** elemre. Válassza ki az iménti lépésekben létrehozott sablont. Válassza az **OK** gombot.
13. Ahhoz, hogy a kiszolgáló az Intune-ban regisztrált eszközök és felhasználók nevében kezelhesse a tanúsítványokat, kövesse az alábbi lépéseket:

    1. Kattintson a jobb gombbal a hitelesítésszolgáltatóra, majd kattintson a **Tulajdonságok** elemre.
    2. A biztonság lapon vegye fel annak a kiszolgálónak a fiókját, amelyen az összekötőket (**Microsoft Intune Tanúsítvány-összekötő** vagy **Microsoft Intune-hoz készült PFX tanúsítvány-összekötő**) futtatja. A fiók számára adja meg a **Tanúsítványok kiadása és kezelése** és a **Tanúsítványkérés** engedélyeket.

14. Jelentkezzen ki a vállalati hitelesítésszolgáltatóból.

## <a name="download-install-and-configure-the-certificate-connectors"></a>A tanúsítvány-összekötők letöltése, telepítése és konfigurálása

### <a name="microsoft-intune-certificate-connector"></a>A Microsoft Intune Certificate Connector

> [!IMPORTANT] 
> A Microsoft Intune Tanúsítvány-összekötőt külön Windows-kiszolgálóra **kell** telepíteni. A vállalati hitelesítésszolgáltatóra (CA) nem telepíthető.

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Hitelesítésszolgáltató** > **Hozzáadás** lehetőséget.
3. Töltse le és mentse az összekötő fájlt. Mentse egy olyan helyre, amely elérhető a kiszolgálóról, amelyre az összekötő telepítve lesz.

    ![ConnectorDownload][ConnectorDownload]

4. A letöltés befejezése után jelentkezzen be a kiszolgálóra. Ha ez megvan:

    1. Győződjön meg róla, hogy telepítve van-e a .NET keretrendszer 4.5 vagy újabb verziója, mivel arra szüksége van az NDES tanúsítvány-összekötőjének. A .NET 4.5-keretrendszer automatikusan részen a Windows Server 2012 R2 és újabb verzióknak.
    2. Futtassa a telepítőprogramot (NDESConnectorSetup.exe), és fogadja el az alapértelmezett helyet. A telepítő az összekötőt a `\Program Files\Microsoft Intune\NDESConnectorUI` helyen telepíti. A Telepítőbeállítás oldalon válassza a **PFX terjesztése**, lehetőséget. Folytassa és fejezze be a telepítést.
    3. Az összekötő-szolgáltatás alapértelmezés szerint a helyi rendszerfiók alatt fut. Ha az Internet eléréséhez proxy szükséges, akkor győződjön meg arról, hogy a helyi szolgáltatásfiók hozzáfér a proxy-beállításokhoz a kiszolgálón.

5. A Hálózati eszközök tanúsítványigénylési szolgáltatásának összekötője megnyitja a **Beléptetés** lapot. Az Intune-hoz való kapcsolódás engedélyezéséhez válassza a **Bejelentkezés** lehetőséget, és adjon meg egy globális rendszergazdai engedélyekkel rendelkező fiókot.
6. Javasoljuk, hogy a **Speciális** lapon hagyja kijelölve az **E számítógép SYSTEM fiókjának a használata (alapértelmezett)** beállítást.
7. **Alkalmaz** > **Bezárás**
8. Lépjen vissza az Azure Portalra (**Intune** > **Eszközkonfiguráció** > **Hitelesítésszolgáltató**). Néhány pillanat múlva egy zöld pipajel jelenik meg, és a **Kapcsolat állapota** **Aktív** lesz. Az összekötő kiszolgáló mostantól kapcsolatba tud lépni az Intune-nal.

> [!NOTE]
> A Microsoft Intune Tanúsítvány-összekötő tartalmazza a TLS 1.2 támogatását. Ha tehát a kiszolgáló, amelyen a Microsoft Intune Tanúsítvány-összekötő telepítve van, támogatja a TLS 1.2-t, akkor a TLS 1.2 lesz használva. Amennyiben a kiszolgáló nem támogatja a TLS 1.2 verziót, a TLS 1.1 lesz használva. Az eszközök és a kiszolgáló közötti hitelesítéshez jelenleg a TLS 1.1 van használatban.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>A Microsoft Intune-hoz készült PFX tanúsítvány-összekötő

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Hitelesítésszolgáltató** > **Hozzáadás** lehetőséget.
3. Töltse le és mentse a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőt. Mentse egy olyan helyre, amely elérhető a kiszolgálóról, amelyre az összekötő telepítve lesz.
4. A letöltés befejezése után jelentkezzen be a kiszolgálóra. Ha ez megvan:

    1. Győződjön meg róla, hogy telepítve van-e a .NET keretrendszer 4.6 vagy újabb verziója, mivel arra szüksége van a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőnek. Ha a .NET 4.6 keretrendszer nincs telepítve, akkor a telepítő automatikusan telepíti.
    2. Futtassa a telepítőt (PfxCertificateConnectorBootstrapper.exe), és fogadja el az alapértelmezett helyet. A telepítő az összekötőt a `Program Files\Microsoft Intune\PFXCertificateConnector` helyen telepíti.
    3. Az összekötő-szolgáltatás a helyi rendszerfiók alatt fut. Ha proxy szükséges az Internet eléréséhez, akkor győződjön meg arról, hogy a helyi szolgáltatásfiók hozzáfér a proxy-beállításokhoz a kiszolgálón.

5. A Microsoft Intune-hoz készült PFX tanúsítvány-összekötő telepítés után megnyitja a **Regisztráció** lapot. Az Intune-hoz való kapcsolódás engedélyezéséhez **Jelentkezzen be**, és adjon meg egy globális Azure-rendszergazdai vagy Intune-rendszergazdai engedélyekkel rendelkező fiókot.
6. Zárja be az ablakot.
7. Lépjen vissza az Azure Portalra (**Intune** > **Eszközkonfiguráció** > **Hitelesítésszolgáltató**). Néhány pillanat múlva egy zöld pipajel jelenik meg, és a **Kapcsolat állapota** **Aktív** lesz. Az összekötő kiszolgáló mostantól kapcsolatba tud lépni az Intune-nal.

## <a name="create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozása

1. Az [Azure Portalon](https://portal.azure.com) lépjen az **Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** menüponthoz.

   ![NavigateIntune][NavigateIntune]

2. Adja meg a következő tulajdonságokat:

    - **Név** a profil számára
    - Igény szerint hozzáadhat egy leírást
    - **Platform**, amelyen telepíteni kell a profilt
    - A **Profiltípust** állítsa **Megbízható tanúsítványra**

3. Nyissa meg a **Beállítások** lapot, és adja meg a korábban exportált hitelesítésszolgáltatói főtanúsítvány .cer fájlját.

   > [!NOTE]
   > A **3. lépésben** választott platformtól függően lehetősége lehet **Céltárolót** választani a tanúsítvány számára.

   ![ProfileSettings][ProfileSettings]

4. A profil mentéséhez kattintson az **OK** > **Létrehozás** gombra.
5. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS-tanúsítványprofil létrehozása

1. Az [Azure Portalon](https://portal.azure.com) lépjen az **Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** menüponthoz.
2. Adja meg a következő tulajdonságokat:

    - **Név** a profil számára
    - Igény szerint hozzáadhat egy leírást
    - **Platform**, amelyen telepíteni kell a profilt
    - A **Profiltípust** állítsa **PKCS-tanúsítványra**

3. Nyissa meg a **Beállítások** lapot, és adja meg a következő tulajdonságokat:

    - **Megújítási küszöb (%)** – Az ajánlott érték 20%.
    - **Tanúsítvány érvényességi időtartama** – Ha nem módosította a tanúsítványsablont, akkor a megadott beállítás valószínűleg egy év.
    - **Kulcstároló-szolgáltató (KSP)**: Windows rendszer esetén válasszon helyet a kulcsok tárolására az eszközön.
    - **Hitelesítésszolgáltató** – A vállalati hitelesítésszolgáltató belső teljes tartományneve (FQDN).
    - **Hitelesítésszolgáltató neve** – A vállalati hitelesítésszolgáltató neve, például „Contoso hitelesítésszolgáltató”.
    - **Tanúsítványsablon neve** – A korábban létrehozott sablon neve. Emlékeztető: a **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*.
    - **Tulajdonos nevének formátuma** – Ennél a beállításnál, ha nincs eltérő követelmény, a **Köznapi nevet** adja meg.
    - **Tulajdonos alternatív neve** – Ennél a beállításnál, ha nincs eltérő követelmény, az **Egyszerű felhasználónevet (UPN)** adja meg.

4. A profil mentéséhez kattintson az **OK** > **Létrehozás** gombra.
5. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Importált PKCS-tanúsítványprofil létrehozása

Importálhatja az Intune-ba a korábban bármely hitelesítésszolgáltató által egy adott felhasználó számára kiadott tanúsítványokat. Az importált tanúsítványok a felhasználó által regisztrált valamennyi eszközre telepítve lesznek. A leggyakrabban S/MIME e-mail-titkosításhoz importálnak meglévő PFX-tanúsítványokat az Intune-ba. Egy felhasználó több tanúsítvánnyal is rendelkezhet ez e-mailek titkosításához. Ezen tanúsítványok titkos kulcsainak a felhasználó összes eszközén meg kell lenniük, hogy fel tudják oldani a korábban titkosított e-mailek titkosítását.

A tanúsítványok Intune-ba való importálásához használhatja [a GitHubon rendelkezésre álló PowerShell-parancsmagokat](https://github.com/Microsoft/Intune-Resource-Access).

A tanúsítványok Intune-ba importálása után hozzon létre egy **Importált PKCS-tanúsítvány** profilt, és rendelje hozzá Azure Active Directory-csoportokhoz.

1. Az [Azure Portalon](https://portal.azure.com) lépjen az **Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** menüponthoz.
2. Adja meg a következő tulajdonságokat:

    - **Név** a profil számára
    - Igény szerint hozzáadhat egy leírást
    - **Platform**, amelyen telepíteni kell a profilt
    - A **Profiltípust** állítsa **Importált PKCS-tanúsítványra**

3. Nyissa meg a **Beállítások** lapot, és adja meg a következő tulajdonságokat:

    - **Felhasználási cél**: Az ehhez a profilhoz importált tanúsítványok rendeltetése. Előfordulhat, hogy egy rendszergazda más célra (például hitelesítésre, S/MIME-aláírásra vagy S/MIME-titkosításra) szánt tanúsítványokat importált. A tanúsítványprofilban kijelölt felhasználási cél alapján lesznek párosítva a megfelelő importált tanúsítványok.
    - **Tanúsítvány érvényességi időtartama** – Ha nem módosította a tanúsítványsablont, akkor a megadott beállítás valószínűleg egy év.
    - **Kulcstároló-szolgáltató (KSP)**: Windows rendszer esetén válasszon helyet a kulcsok tárolására az eszközön.

4. A profil mentéséhez kattintson az **OK** > **Létrehozás** gombra.
5. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="next-steps"></a>További lépések
[SCEP-tanúsítványok használata](certificates-scep-configure.md), vagy [PKCS-tanúsítványok kibocsátása egy Symantec PKI-kezelő webszolgáltatásból](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Nyissa meg az Intune oldalt az Azure Portalon, és hozzon létre egy új profilt egy megbízható tanúsítványhoz"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Hozzon létre egy profilt, és töltsön fel egy megbízható tanúsítványt"
[ConnectorDownload]: ./media/certificates-download-connector.png "Töltse le a tanúsítvány-összekötőt az Azure Portalról"  
