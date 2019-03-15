---
title: Privát és nyilvános kulcsú tanúsítványokat használni a Microsoft Intune – Azure |} A Microsoft Docs
description: Adja hozzá, vagy nyilvános kulcs titkosítási szabványok (PKCS) tanúsítványok létrehozása a Microsoft Intune, beleértve a gyökértanúsítvány exportálása, konfigurálja a tanúsítványsablont, letöltése és telepítése az Intune tanúsítvány-összekötő (NDES), egy eszköz létrehozása konfigurációs profil, és a egy PKCS-tanúsítványprofil létrehozása az Azure és a hitelesítésszolgáltató.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3fd8ca136862db4e80ff11d31fc4860d4785ff1
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57390286"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-tanúsítványok konfigurálása és használata az Intune-nal

Az Intune támogatja a privát és nyilvános kulcsból álló kulcspárt (PKCS) tanúsítványok használatát. Ez a cikk segítségével konfigurálja a szükséges infrastruktúrát, például a helyszíni tanúsítvány-összekötőt PKCS-tanúsítványok exportálását és majd a tanúsítvány hozzáadása az Intune eszközkonfigurációs profil.

A Microsoft Intune PKCS-tanúsítványok használata a szervezetek erőforrásokhoz való hitelesítés és hozzáférés beépített beállításokat tartalmaz. Tanúsítványok hitelesítéséhez és a vállalati erőforrásokhoz való biztonságos hozzáférést, például VPN-en vagy egy Wi-Fi-hálózathoz. Eszközkonfigurációs profilok használatával az Intune-ban telepítheti ezeket a beállításokat.


## <a name="requirements"></a>Követelmények

PKCS-tanúsítványok használata az Intune-nal, a következő infrastruktúra lesz szüksége:

- **Active Directory-tartomány**: A jelen szakaszban felsorolt összes kiszolgálónak csatlakoznia kell az Active Directory-tartományához.

  Az Active Directory Domain Services (AD DS) konfigurálásával kapcsolatos további információkért lásd: [AD DS tervezése és kialakítása](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Hitelesítésszolgáltató**: Egy vállalati hitelesítésszolgáltató (CA).

  A telepítése és konfigurálása az Active Directory tanúsítványszolgáltatások (AD CS) további információért lásd: [Active Directory tanúsítványszolgáltatások részletes útmutatóját](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > Az Intune követelményei szerint az AD CS-t vállalati hitelesítésszolgáltatóval, és nem önálló hitelesítésszolgáltatóval kell futtatni.

- **Egy ügyfél**: Szeretne csatlakozni a vállalati Hitelesítésszolgáltatóból.

- **Főtanúsítvány**: Vállalati hitelesítésszolgáltatótól származó főtanúsítvány exportált másolata.

- **A Microsoft Intune tanúsítvány-összekötő**: Az Intune-portálon lépjen a **eszközkonfiguráció** > **tanúsítvány-összekötőt** > **Hozzáadás**, és kövesse a *lépések Telepítse az összekötőt a PKCS #12*. A portálon a letöltési hivatkozás segítségével indítsa el a tanúsítvány-összekötő telepítő letöltési **NDESConnectorSetup.exe**.  
- 
  Ezt az összekötőt PKCS eszköztanúsítvány-kérelmeket a hitelesítés és az S/MIME e-mail aláírási használt dolgozza fel.

  Az NDES tanúsítvány-összekötő a Federal Information Processing Standard (FIPS) módot is támogatja. A FIPS nem szükséges, de ha engedélyezve van, akkor lehetőség van tanúsítványok kibocsátására és visszavonására.

- **Importált PFX-tanúsítványok összekötő az Intune-hoz**: Ha e-mailek titkosítása S/MIME használata, akkor az Intune-portálon az összekötő letöltéséhez *importált PFX-tanúsítványok*.  Lépjen a **eszközkonfiguráció** > **tanúsítvány-összekötőt** > **Hozzáadás**, és kövesse a *-összekötő telepítésének lépései Importált PFX-tanúsítványok*. A portálon a letöltési hivatkozás segítségével indítsa el a telepítő letöltési **PfxCertificateConnectorBootstrapper.exe**. 

  Ez az összekötő e-mail titkosítási S/MIME egy adott felhasználó az Intune-ba importált PFX-fájlok kéréseket kezeli.  

  Ez az összekötő is automatikusan frissíti magát amikor új verzió elérhetővé válnak. A frissítési funkció használatához tegye a következőket:
  - Az importált PFX-tanúsítványok összekötő telepítse a Microsoft Intune-hoz a kiszolgálón.
  - Automatikusan beolvashassa az a fontos frissítések, biztosítása érdekében a tűzfalak, amelyek lehetővé teszik az összekötő kapcsolatba nyílt **autoupdate.msappproxy.net** porton **443-as**.  


- **A Windows Server**: A gazdagép Windows Server használhatja:

  - A Microsoft Intune Certificate Connector – a hitelesítéshez és az S/MIME e-mail aláírási forgatókönyvek
  - PFX-Tanúsítványösszekötő a Microsoft Intune - S/MIME e-mail titkosítási célokra.

  A két összekötő telepítése (*a Microsoft Intune tanúsítvány-összekötő* és *importált PFX-tanúsítványok összekötő*) ugyanazon a kiszolgálón.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól

Egy VPN-, Wi-Fi- vagy egyéb erőforrások eszköz hitelesítéséhez, egy eszközt egy legfelső szintű vagy köztes Hitelesítésszolgáltatói tanúsítványra van szüksége. Az alábbi lépések ismertetik a szükséges tanúsítvány beszerzését a vállalati hitelesítésszolgáltatótól.

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyisson meg rendszergazdaként egy parancssort.
3. Exportálja a hitelesítésszolgáltatói főtanúsítványt (.cer) egy olyan helyre, ahol később hozzáférhet.
4. Ha a varázsló befejeződött, még mielőtt bezárná, kattintson **Launch the Certificate Connector UI**(Certificate Connector felhasználói felületének indítása) lehetőségre.

   `certutil -ca.cert certnew.cer`

   További információkárt lásd: [Certutil-feladatok a tanúsítványok kezeléséhez](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-ca"></a>Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatón

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyissa meg a **Hitelesítésszolgáltató** konzolt, majd kattintson a jobb gombbal a **Tanúsítványsablonok** elemre, és válassza a **Kezelés** lehetőséget.
3. Keresse meg a **Felhasználó** tanúsítványsablont, kattintson rá a jobb gombbal, majd válassza a **Sablon megkettőzése** lehetőséget. Ekkor megnyílik az **Új sablon tulajdonságai** terület.

    > [!NOTE]
    > S/MIME e-mail-aláírás és titkosítás esetén sok rendszergazda külön tanúsítványt használ az aláíráshoz és a titkosításhoz. Ha a Microsoft Active Directory Tanúsítványszolgáltatást használja, akkor használhatja az **Exchange Signature Only** (csak Exchange-aláírás) sablont S/MIME e-mail-aláírási tanúsítványokhoz, és az **Exchange User** (Exchange felhasználó) sablont S/MIME titkosítási tanúsítványokhoz.  Ha 3. fél hitelesítésszolgáltatót használ, tekintse át az aláírás és titkosítás sablonok útmutatást javasolt.

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
12. A **Hitelesítésszolgáltató** konzolon kattintson a jobb gombbal a **Tanúsítványsablonok** > **Új** > **Kiállítandó tanúsítványsablon** elemre. Válassza ki az iménti lépésekben létrehozott sablont. Kattintson az **OK** gombra.
13. A regisztrált eszközökön és a felhasználói tanúsítványok kezelése a kiszolgálón kövesse az alábbi lépéseket:

    1. Kattintson a jobb gombbal a hitelesítésszolgáltatóra, majd kattintson a **Tulajdonságok** elemre.
    2. A biztonság lapon vegye fel annak a kiszolgálónak a fiókját, amelyen az összekötőket (**Microsoft Intune Tanúsítvány-összekötő** vagy **Microsoft Intune-hoz készült PFX tanúsítvány-összekötő**) futtatja. 
    3. A fiók számára adja meg a **Tanúsítványok kiadása és kezelése** és a **Tanúsítványkérés** engedélyeket.

14. Jelentkezzen ki a vállalati hitelesítésszolgáltatóból.

## <a name="download-install-and-configure-the-certificate-connectors"></a>A tanúsítvány-összekötők letöltése, telepítése és konfigurálása

### <a name="microsoft-intune-certificate-connector"></a>A Microsoft Intune Certificate Connector

> [!IMPORTANT]  
> A Microsoft Intune tanúsítvány-összekötő nem lehet telepíteni a a kiállító hitelesítésszolgáltató (CA), és ehelyett telepítenie kell egy különálló Windows-kiszolgálón.  

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás**, szűrjön az **Intune** > válassza **Intune**.
2. Válassza ki **eszközkonfiguráció** > **összekötők minősítési** > **Hozzáadás**.
3. Töltse le és mentse az összekötő fájlt olyan helyre fogjuk, ha az összekötő telepítéséhez a kiszolgálón érhető el.

    ![NDES connector letöltése](media/certificates-pfx-configure/download-ndes-connector.png)
 

4. A letöltés befejezése után jelentkezzen be a kiszolgálóra. Ha ez megvan:

    1. Győződjön meg róla, hogy telepítve van-e a .NET keretrendszer 4.5 vagy újabb verziója, mivel arra szüksége van az NDES tanúsítvány-összekötőjének. A .NET 4.5-keretrendszer automatikusan részen a Windows Server 2012 R2 és újabb verzióknak.
    2. Futtassa a telepítőprogramot (NDESConnectorSetup.exe), és fogadja el az alapértelmezett helyet. A telepítő az összekötőt a `\Program Files\Microsoft Intune\NDESConnectorUI` helyen telepíti. A Telepítőbeállítás oldalon válassza a **PFX terjesztése**, lehetőséget. Folytassa és fejezze be a telepítést.
    3. Az összekötő-szolgáltatás alapértelmezés szerint a helyi rendszerfiók alatt fut. Ha az Internet eléréséhez proxy szükséges, akkor győződjön meg arról, hogy a helyi szolgáltatásfiók hozzáfér a proxy-beállításokhoz a kiszolgálón.

5. A Hálózati eszközök tanúsítványigénylési szolgáltatásának összekötője megnyitja a **Beléptetés** lapot. Az Intune-hoz való kapcsolódás engedélyezéséhez válassza a **Bejelentkezés** lehetőséget, és adjon meg egy globális rendszergazdai engedélyekkel rendelkező fiókot.
6. Javasoljuk, hogy a **Speciális** lapon hagyja kijelölve az **E számítógép SYSTEM fiókjának a használata (alapértelmezett)** beállítást.
7. **Alkalmaz** > **Bezárás**
8. Lépjen vissza az Intune-portálon (**Intune** > **eszközkonfiguráció** > **összekötők minősítési**). Pár pillanat után egy zöld pipa jelenik meg, és a **kapcsolat állapota** van **aktív**. Az összekötő kiszolgáló mostantól kapcsolatba tud lépni az Intune-nal.
9. Ha olyan webproxyt hálózati környezetében, szükség lehet további állítani, hogy az összekötő működéséhez. További információkért lásd: [együttműködnek a meglévő helyszíni proxykiszolgálók](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) az Azure Active Directory dokumentációjában.

> [!NOTE]  
> A Microsoft Intune tanúsítvány-összekötő támogatja a TLS 1.2. Ha a TLS 1.2 az összekötőt üzemeltető kiszolgálón van telepítve, az összekötő használja a TLS 1.2. Ellenkező esetben a TLS 1.1 szolgál. Az eszközök és a kiszolgáló közötti hitelesítéshez jelenleg a TLS 1.1 van használatban.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>A Microsoft Intune-hoz készült PFX tanúsítvány-összekötő

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza ki **eszközkonfiguráció** > **összekötők minősítési** > **hozzáadása**
3. Töltse le és mentse a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőt. Mentse egy olyan helyre, amely elérhető a kiszolgálóról, amelyre az összekötő telepítve lesz.
4. A letöltés befejezése után jelentkezzen be a kiszolgálóra. Ha ez megvan:

    1. Győződjön meg róla, hogy telepítve van-e a .NET keretrendszer 4.6 vagy újabb verziója, mivel arra szüksége van a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőnek. Ha a .NET 4.6 keretrendszer nincs telepítve, akkor a telepítő automatikusan telepíti.
    2. Futtassa a telepítőt (PfxCertificateConnectorBootstrapper.exe), és fogadja el az alapértelmezett hely, amely telepíti az összekötő `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. Az összekötő-szolgáltatás a helyi rendszerfiók alatt fut. Ha proxy szükséges az Internet eléréséhez, akkor győződjön meg arról, hogy a helyi szolgáltatásfiók hozzáfér a proxy-beállításokhoz a kiszolgálón.

5. A Microsoft Intune-hoz készült PFX tanúsítvány-összekötő telepítés után megnyitja a **Regisztráció** lapot. Az Intune-hoz való kapcsolódás engedélyezéséhez **Jelentkezzen be**, és adjon meg egy globális Azure-rendszergazdai vagy Intune-rendszergazdai engedélyekkel rendelkező fiókot.
6. Zárja be az ablakot.
7. Lépjen vissza az Azure Portalon (**Intune** > **eszközkonfiguráció** > **összekötők minősítési**). Pár pillanat után egy zöld pipa jelenik meg, és a **kapcsolat állapota** van **aktív**. Az összekötő kiszolgáló mostantól kapcsolatba tud lépni az Intune-nal.

## <a name="create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozása

1. Az [Azure Portalon](https://portal.azure.com) lépjen az **Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** menüponthoz.
    ![Keresse meg az Intune-hoz, és hozzon létre egy új profilt egy megbízható tanúsítványt](media/certificates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Adja meg a következő tulajdonságokat:

    - **Név** a profil számára
    - Igény szerint hozzáadhat egy leírást
    - **Platform**, amelyen telepíteni kell a profilt
    - A **Profiltípust** állítsa **Megbízható tanúsítványra**

3. Nyissa meg a **Beállítások** lapot, és adja meg a korábban exportált hitelesítésszolgáltatói főtanúsítvány .cer fájlját.

   > [!NOTE]
   > A **3. lépésben** választott platformtól függően lehetősége lehet **Céltárolót** választani a tanúsítvány számára.

   ![Profil létrehozása és töltsön fel egy megbízható tanúsítványt](media/certificates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

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

    - **Megújítási küszöb (%)**: Ajánlott érték 20 %.
    - **Tanúsítvány érvényességi időtartama**: Ha nem módosította a tanúsítványsablont, ez a beállítás egy év lehet beállítani.
    - **Kulcstároló-szolgáltató (KSP)**: Windows válassza ki a kulcsok tárolására az eszközön.
    - **Hitelesítésszolgáltató**: Megjeleníti a vállalati hitelesítésszolgáltató belső teljes tartománynév (FQDN).
    - **Hitelesítésszolgáltató neve**: A vállalati hitelesítésszolgáltató, például "Contoso Certification Authority" nevét jeleníti meg.
    - **Tanúsítványsablon neve**: A korábban létrehozott sablon neve. Emlékeztető: a **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*.
    - **Tulajdonos nevének formátuma**: Ezt a beállítást **köznapi név** , kivéve, ha egyébként szükséges.
    - **Tulajdonos alternatív nevének**: Ezt a beállítást **egyszerű felhasználónév (UPN)** , kivéve, ha egyébként szükséges.

4. A profil mentéséhez kattintson az **OK** > **Létrehozás** gombra.
5. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Importált PKCS-tanúsítványprofil létrehozása

Egy adott felhasználó számára az Intune-hoz a CA korábban kiállított tanúsítványok importálhatók. Az importált tanúsítványok a felhasználó által regisztrált valamennyi eszközre telepítve lesznek. A leggyakrabban S/MIME e-mail-titkosításhoz importálnak meglévő PFX-tanúsítványokat az Intune-ba. Egy felhasználó jogosult az e-mailek titkosításához sok tanúsítvány. Ezen tanúsítványok titkos kulcsainak a felhasználó összes eszközén meg kell lenniük, hogy fel tudják oldani a korábban titkosított e-mailek titkosítását.

A tanúsítványok Intune-ba való importálásához használhatja [a GitHubon rendelkezésre álló PowerShell-parancsmagokat](https://github.com/Microsoft/Intune-Resource-Access).

A tanúsítványok Intune-ba importálása után hozzon létre egy **Importált PKCS-tanúsítvány** profilt, és rendelje hozzá Azure Active Directory-csoportokhoz.

1. Az [Azure Portalon](https://portal.azure.com) lépjen az **Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** menüponthoz.
2. Adja meg a következő tulajdonságokat:

    - **Név** a profil számára
    - Igény szerint hozzáadhat egy leírást
    - **Platform**, amelyen telepíteni kell a profilt
    - A **Profiltípust** állítsa **Importált PKCS-tanúsítványra**

3. Nyissa meg a **Beállítások** lapot, és adja meg a következő tulajdonságokat:

    - **Felhasználási célja**: Ehhez a profilhoz importált tanúsítványok rendeltetési célját. Előfordulhat, hogy egy rendszergazda más célra (például hitelesítésre, S/MIME-aláírásra vagy S/MIME-titkosításra) szánt tanúsítványokat importált. A tanúsítványprofilban kijelölt felhasználási cél alapján lesznek párosítva a megfelelő importált tanúsítványok.
    - **Tanúsítvány érvényességi időtartama**: Ha nem módosította a tanúsítványsablont, ez a beállítás egy év lehet beállítani.
    - **Kulcstároló-szolgáltató (KSP)**: Windows válassza ki a kulcsok tárolására az eszközön.

4. A profil mentéséhez kattintson az **OK** > **Létrehozás** gombra.
5. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

[SCEP-tanúsítványok használata](certificates-scep-configure.md), vagy [adja ki a PKCS-tanúsítványok Symantec PKI manager webszolgáltatásból](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Nyissa meg az Intune oldalt az Azure Portalon, és hozzon létre egy új profilt egy megbízható tanúsítványhoz"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Hozzon létre egy profilt, és töltsön fel egy megbízható tanúsítványt"
[ConnectorDownload]: ./media/certificates-download-connector.png "Töltse le a tanúsítvány-összekötőt az Azure Portalról"  
