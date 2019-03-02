---
title: Symantec PKCS-tanúsítványok kiállítása a Microsoft Intune-nal
titlesuffix: ''
description: Az Intune Tanúsítvány-összekötő telepítése és konfigurálása PKCS-tanúsítványok kiállításához az Intune által kezelt eszközök számára a Symantec PKI Manager webszolgáltatásból.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f038ce17e544871f0842df050770f9b78e7710f9
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236024"
---
# <a name="set-up-intune-certificate-connector-for-symantec-pki-manager-web-service"></a>Az Intune Tanúsítvány-összekötő beállítása a Symantec PKI Manager webszolgáltatáshoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk ismerteti az Intune Tanúsítvány-összekötő telepítésének és konfigurálásának menetét PKCS-tanúsítványok kiállításához az Intune által kezelt eszközök számára a Symantec PKI Manager webszolgáltatásból.

A cikk a továbbiakban a Symantec PKI Manager webszolgáltatásra Symantec hitelesítésszolgáltatóként hivatkozik. Ha már konfigurálta az Intune Tanúsítvány-összekötőt PKCS- és SCEP-tanúsítványok kiállításához Microsoft hitelesítésszolgáltatóval (CA), ugyanez az összekötő konfigurálható PKCS-tanúsítványok kiállításához a Symantec hitelesítésszolgáltató használatával is. Ebben az esetben az Intune Tanúsítvány-összekötővel a következő tanúsítványok állíthatók ki:

* PKCS-tanúsítványok Microsoft hitelesítésszolgáltatótól
* SCEP-tanúsítványok Microsoft hitelesítésszolgáltatótól
* PKCS-tanúsítványok Symantec hitelesítésszolgáltatótól

Ha az Intune Tanúsítvány-összekötőt szeretné használni a Microsoft hitelesítésszolgáltatókkal és a Symantec hitelesítésszolgáltatókkal is, akkor először végezze el az Intune Tanúsítvány-összekötő beállítását Microsoft hitelesítésszolgáltató használatához, majd kövesse az alábbi lépéseket a Symantec hitelesítésszolgáltató használatának konfigurálásához.  Az Intune Tanúsítvány-összekötő Microsoft hitelesítésszolgáltatóhoz való konfigurálásáról a [Tanúsítványok konfigurálása a Microsoft Intune-ban](certificates-configure.md) című cikkben olvashat bővebben.

## <a name="prepare-to-install-intune-certificate-connector"></a>A Microsoft Intune Tanúsítvány-összekötő telepítésének előkészítése

Ha az Intune Tanúsítvány-összekötőt korábban már beállította egy meglévő Microsoft hitelesítésszolgáltató használatához, és most be szeretné állítani a Symantec hitelesítésszolgáltatók támogatását is, ezt a lépést kihagyhatja, és miután telepítette a legújabb Intune Tanúsítvány-összekötőt az Intune felügyeleti portálról, folytassa a fennmaradó lépésekkel. Ezt a lépést csak akkor kell elvégeznie, ha az Intune Tanúsítvány-összekötőt egy önálló Symantec hitelesítésszolgáltatóval szeretné használni.

1. Az alábbi listából válasszon ki egy Windows operációs rendszert, és telepítse a számítógépére:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Hozzon létre egy rendszergazdai jogosultságokkal rendelkező felhasználót, és végezze el az alábbi lépéseket.

3. Ellenőrizze, hogy elérhetők-e új Windows-frissítések, és ha igen, telepítse azokat.

   > [!IMPORTANT]
   > A Windows-frissítések telepítése után indítsa újra a számítógépet.

4. Telepítse a .NET keretrendszer 3.5-ös verzióját:

    a. Nyissa meg **Vezérlőpult** > **Programok és szolgáltatások** > **Windows-szolgáltatások be- és kikapcsolása** lehetőséget.

    b. Válassza ki **.NET-keretrendszer 3.5** elemet, és telepítése azt.

## <a name="install-the-symantec-registration-authorization-certificate"></a>A Symantec regisztrációszolgáltató tanúsítvány telepítése

Az alábbi lépéseket követve szerezze be a regisztrációszolgáltató (RA) tanúsítványt a Symantec hitelesítésszolgáltatótól. Az RA-tanúsítvány beszerzéséhez aktív előfizetéssel kell rendelkeznie a Symantec hitelesítésszolgáltatónál.

1. Az alábbi kódrészlet nevű fájlba mentése **certreq.ini** és szükség szerint módosítsa (például: *Tulajdonos neve CN-formátumban*).

   ```
    [Version] 
    Signature="$Windows NT$" 

    [NewRequest] 
    ;Change to your,country code, company name and common name 
    Subject = "Subject Name in CN format"

    KeySpec = 1 
    KeyLength = 2048 
    Exportable = TRUE 
    MachineKeySet = TRUE 
    SMIME = False 
    PrivateKeyArchive = FALSE 
    UserProtected = FALSE 
    UseExistingKeySet = FALSE 
    ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
    ProviderType = 12 
    RequestType = PKCS10 
    KeyUsage = 0xa0 

    [EnhancedKeyUsageExtension] 
    OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication

    ;----------------------------------------------- 
   ```

2. Nyisson meg egy rendszergazda jogú parancssort, és hozzon létre CSR-tartalmat a következő paranccsal:

   `Certreq.exe -new certreq.ini request.csr`

3. Nyissa meg a request.csr fájlt a Jegyzettömbben, és másolja le a CSR-tartalmat. A CSR-tartalom formátuma a következő:

    ```
    -----BEGIN NEW CERTIFICATE REQUEST-----
    MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
    …
    …
    fzpeAWo=
    -----END NEW CERTIFICATE REQUEST-----
    ```

4. Jelentkezzen be a Symantec hitelesítésszolgáltatóra, és a feladatok között keresse meg a **Get an RA Cert** (RA-tanúsítvány beszerzése) lehetőséget.

   a. Illessze a megfelelő szövegmezőbe a 3. lépésben lemásolt CSR-tartalmat.

   b. A megfelelő szövegmezőben adja meg a tanúsítvány rövid nevét.

   c. Kattintson a **Folytatás** gombra.

      Ekkor megjelenik egy hivatkozás, melyre kattintva letöltheti az RA-tanúsítványt.

   d. Töltse le az RA-tanúsítványt a helyi számítógépre.

5. Importálja a regisztrációszolgáltató tanúsítványt a Windows tanúsítványtárolójába:

    a. Nyisson meg egy MMC konzolt.

    b. Kattintson a **Fájl** > **Beépülő modul hozzáadása/eltávolítása** > **Tanúsítvány** lehetőségre, majd kattintson a **Hozzáadás** gombra.

    c. Válassza a **Számítógépfiók** lehetőséget, majd kattintson a **Tovább** gombra.

    d. Válassza a **Helyi számítógép** lehetőséget, majd kattintson a **Befejezés** gombra.

    e. A **Beépülő modul hozzáadása/eltávolítása** ablakban kattintson az **OK** lehetőségre. Bontsa ki a **Tanúsítványok (Helyi számítógép)** > **Személyes** > **Tanúsítványok** elemet.

    f. A jobb egérgombbal kattintson a **Tanúsítványok** csomópontra, és válassza a **Minden feladat** > **Importálás** lehetőséget.

    g. Válassza ki a Symantec hitelesítésszolgáltatóról letöltött RA-tanúsítvány helyét, és kattintson a **Tovább** gombra.

    h. Válassza a **Személyes tanúsítványtároló** lehetőséget, majd kattintson a **Tovább** gombra.

    i. Kattintson a **Befejezés**gombra. Ekkor a rendszer importálja az RA-tanúsítványt a helyi számítógép személyes tanúsítványtárolójába a titkos kulccsal együtt.  

6. A titkos kulcsú tanúsítvány exportálása és importálása:

    a. Bontsa ki a **Tanúsítványok (Helyi számítógép)** > **Személyes** > **Tanúsítványok** csomópontot.

    b. Válassza ki az előző lépésben importált tanúsítványt.

    c. Kattintson a jobb egérgombbal a tanúsítványra, és válassza a **Minden feladat** > **Exportálás** lehetőséget.

    d. Kattintson a **Tovább** gombra, és írja be a jelszót.

    e. Adja meg, hogy hová szeretné exportálni a tanúsítványt, majd kattintson a **Befejezés** gombra.

    f. Az 5. lépésben ismertetett eljárást követve importálja a titkos kulcsú tanúsítványt a helyi számítógép személyes tanúsítványtárolójába.

7. Szóközök nélkül másolja le az RA-tanúsítvány ujjlenyomatát.  Lent egy példát láthat a tanúsítványok ujjlenyomatára:

   ```
   RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
   ```


   > [!NOTE]
   > Ha probléma merül fel az RA-tanúsítvány lekérésekor a Symantec hitelesítésszolgáltatótól, forduljon a Symantec ügyfélszolgálatához.

## <a name="install-intune-certificate-connector"></a>Az Intune Tanúsítvány-összekötő telepítése

Ha már a legújabb Intune Tanúsítvány-összekötőt használja egy meglévő Microsoft hitelesítésszolgáltató kezeléséhez, és emellett be szeretné állítani egy Symantec hitelesítésszolgáltató támogatását, ugorja át ezt a lépést. Ellenkező esetben töltse le a legújabb Intune Tanúsítvány-összekötőt az Intune felügyeleti portálról, és kövesse az alábbi utasításokat.

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
4. Válassza az **Eszközök konfigurálása** panel **Hitelesítésszolgáltató** elemét.
5. Kattintson a **Hozzáadás** elemre, és válassza az **Összekötői fájl letöltése** lehetőséget. Mentse a letöltést egy olyan helyre, amelyhez hozzá tud férni a telepítéshez használt kiszolgálón. 
3. Futtassa az NDESConnectorSetup.exe fájlt emelt szintű jogosultságokkal.

    a. A **Telepítési beállítások** képernyőn válassza ki a **PFX terjesztés** lehetőséget az alábbi képernyőfelvételen látható módon.  A telepítés további részében használja az alapértelmezett értékeket.

   > [!IMPORTANT]
   > Ha az Intune Tanúsítvány-összekötőt úgy szeretné beállítani, hogy Microsoft hitelesítésszolgáltatótól és Symantec hitelesítésszolgáltatótól származó tanúsítványokat is kibocsásson, jelölje be az **SCEP- és PFX-profilok terjesztése** lehetőséget. A telepítés további részében használja az alapértelmezett értékeket.

   ![InstallConnector][InstallConnector]
 
## <a name="configure-intune-certificate-connector"></a>A Intune Tanúsítvány-összekötő konfigurálása

A rendszer az Intune Tanúsítvány-összekötőt alapértelmezés szerint a következő mappába telepíti: `%ProgramFiles%\Microsoft Intune`

1. A Jegyzettömbbel nyissa meg a %ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config fájlt.

    a. Frissítse az RACertThumbprint kulcs értékét a tanúsítvány előző részben kimásolt ujjlenyomat értékével.  Például:

   ```
   <add key="RACertThumbprint"
   value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   ```

    b. Mentse és zárja be a fájlt.

2. Nyissa meg a services.msc programot.

    a. Válassza ki az **Intune Connector Service** lehetőséget.

    b. Állítsa le, majd indítsa el újra a szolgáltatást.

    c. Zárja be a Szolgáltatások ablakot.

## <a name="setup-the-intune-administrator-account"></a>Az Intune rendszergazdafiók beállítása

Ha már az Intune Tanúsítvány-összekötőt használja egy meglévő Microsoft hitelesítésszolgáltató kezeléséhez, és emellett be szeretné állítani egy Symantec hitelesítésszolgáltató támogatását, ugorja át ezt a lépést és folytassa a hátralévő lépésekkel. 

1. Indítsa el az NDES-összekötő felhasználói felületét a következő helyről: ` %ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe `

    a. Kattintson a **Beléptetés** fülre, majd a **Bejelentkezés** lehetőségre.

    b. Adja meg Intune-bérlői rendszergazdai hitelesítő adatait a kijelölt szövegmezőkben.

    c. Kattintson a **Bejelentkezés** elemre.  Ekkor megjelenik az alábbi képernyőfelvételen látható megerősítő párbeszédpanel a **Sikeresen regisztrálva** üzenettel.
2. Zárja be az NDES-összekötő felhasználói felületét.

![ConfigureConnector][ConfigureConnector]
 
## <a name="create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozása

Az Intune-ban kezelt eszközökhöz kiadott PKCS-tanúsítványoknak megbízható főtanúsítványhoz kell kapcsolódniuk. Ehhez a Symantec hitelesítésszolgáltatótól beszerzett főtanúsítvánnyal létre kell hoznia egy Intune megbízható tanúsítványprofilt.

1. Megbízható főtanúsítvány beszerzése a Symantec hitelesítésszolgáltatótól:

    a. Jelentkezzen be a Symantec hitelesítésszolgáltató felügyeleti portáljára.

    b. A feladatok között kattintson a Manage CAs (Hitelesítésszolgáltatók kezelése) lehetőségre:

    c. A hitelesítésszolgáltatók listájáról válassza ki a megfelelő hitelesítésszolgáltatót.

    d. Kattintson a Download root certificate (Főtanúsítvány letöltése) lehetőségre a megbízható főtanúsítvány letöltéséhez.

2. Megbízható tanúsítványprofil létrehozása az Intune felügyeleti portálon:

    a. Jelentkezzen be az [Azure Portalra](https://portal.azure.com) az Intune-bérlői rendszergazdai hitelesítő adataival, majd keresse meg a Intune forrásanyagokat.

    b. A **Microsoft Intune** > **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőségre kattintva hozzon létre egy megbízható tanúsítványprofilt.

    c. Adja meg a szükséges információkat a **Név** és **Leírás** mezőkben, majd válassza ki a célplatformot. 

    d. Válassza ki a Megbízható tanúsítványprofil lehetőséget a Profil típusa legördülő listán.

    e. Töltse fel a Symantec hitelesítésszolgáltatótól az előző lépésben beszerzett megbízható főtanúsítványt.

    f. Hajtsa végre a profil létrehozásához szükséges hátralévő lépéseket. 

    g. Kattintson a **Hozzárendelések** lehetőségre, és válassza ki a megfelelő csoportot.  A hozzárendelt csoport legalább egy felhasználót vagy eszközt kell, hogy tartalmazzon.

## <a name="get-the-certificate-profile-oid"></a>A tanúsítványprofil objektumazonosítójának beszerzése

A tanúsítványprofil objektumazonosítója egy a Symantec hitelesítésszolgáltatón található tanúsítványprofil-sablonhoz van hozzárendelve.  Ahhoz, hogy az Intune felügyeleti portálon létrehozzon egy PKCS-tanúsítványprofilt, meg kell adnia a tanúsítványsablon nevét. Ez a név egy a Symantec hitelesítésszolgáltatón található tanúsítványsablonhoz hozzárendelt tanúsítványprofil objektumazonosítója.

1. Jelentkezzen be a Symantec hitelesítésszolgáltató felügyeleti portáljára.
2. Kattintson a Manage Certificate Profiles (Tanúsítványprofilok kezelése) lehetőségre.
3. Válassza ki a használni kívánt tanúsítványprofilt.
4. Másolja le a tanúsítványprofil objektumazonosítóját. Az objektumazonosító az alábbi példához hasonlóan néz ki:

   ```
   Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
   ```

   > [!NOTE]
   > Ha probléma merül fel a tanúsítványprofil objektumazonosítójának beszerzése során, forduljon a Symantec ügyfélszolgálathoz.

## <a name="create-a-pkcs-certificate-profile"></a>PKCS-tanúsítványprofil létrehozása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com) az Intune bérlői rendszergazdai hitelesítő adataival, majd keresse meg a Intune-forrásanyagokat.
2. A **Microsoft Intune** > **Eszközkonfiguráció>Profilok** > **Profil létrehozása** lehetőségre kattintva hozzon létre egy PKCS-tanúsítványprofilt.

    a. Adja meg a szükséges információkat a **Név** és **Leírás** mezőkben, majd válassza ki a célplatformot.

    b. Válassza ki a **PKCS-tanúsítványprofil** lehetőséget a **Profil típusa** legördülő listán.  

    c. Hajtsa végre a profil létrehozáshoz szükséges, hátralévő lépéseket.

   ![ConfigureProfile][ConfigureProfile]

   > [!IMPORTANT]
   > Ahhoz, hogy az Intune Tanúsítvány-összekötő használatával a Symantec hitelesítésszolgáltatótól származó PKCS-tanúsítványokat adhasson ki, a PKCS-tanúsítványprofil következő paramétereinél az alábbi táblázatban megadott, illetve a képernyőfelvételen látható értékeket kell beállítani. 

    |PKCS-tanúsítvány paraméterei | Érték | Leírás |
    | --- | --- | --- |
    | Hitelesítésszolgáltató | pki-ws.symauth.com | Ez az érték a Symantec CA alapszolgáltatásának FQDN neve, záró perjelek nélkül.  Ha nem biztos abban, hogy ez a Symantec CA-előfizetéséhez tartozó alapszolgáltatás FQDN neve, érdeklődjön a Symantec ügyfélszolgálatánál. <br><br> Ha az FQDN helytelen, az Intune Tanúsítvány-összekötő nem tudja kiállítani a Symantec hitelesítésszolgáltatótól származó PKCS-tanúsítványokat.| 
    | Hitelesítésszolgáltató neve | Symantec | Ennek az értéknek a **Symantec** sztringnek kell lennie. <br><br> Ha itt bármilyen más érték szerepel, az Intune Tanúsítvány-összekötő nem fogja tudni kiállítani a Symantec hitelesítésszolgáltatótól származó PKCS-tanúsítványokat.|
    | Tanúsítványsablon neve | A tanúsítványprofil Symantec hitelesítésszolgáltatótól beszerzett objektumazonosítója <br><br> Pl.:`2.16.840.1.113733.1.16.1.2.3.1.1.61904612`| Ez az érték a Symantec hitelesítésszolgáltatón található tanúsítványprofil-sablonból az előző részben ismertetett módon beszerzett objektumazonosító. <br><br> Ha az Intune Tanúsítvány-összekötő nem találja a Symantec hitelesítésszolgáltatón a tanúsítványprofil objektumazonosítójához társított tanúsítványsablont, nem fogja tudni kiállítani a Symantec hitelesítésszolgáltatótól származó PKCS-tanúsítványokat.|

   > [!NOTE]
   > Windows platformok esetében nem szükséges, hogy a PKCS-tanúsítványprofilok megbízható tanúsítványprofilhoz legyenek társítva. Nem Windows platformú profilok (pl. Android profilok) esetén azonban szükséges a hozzárendelés.

3. Kattintson a **Hozzárendelések** lehetőségre, és válassza ki a megfelelő csoportot.  A hozzárendelt csoport legalább egy felhasználót vagy eszközt kell, hogy tartalmazzon.
 
Az előző lépések végrehajtását követően az Intune Tanúsítvány-összekötő képes lesz a Symantec-hitelesítésszolgáltatótól származó PKCS-tanúsítványokat kiállítani a hozzárendelt csoportba tartozó, Intune által felügyelt eszközök számára. A kiállított tanúsítványok az Intune által felügyelt eszközökön az aktuális felhasználó tanúsítványtárolóján belüli személyes tanúsítványtárolóban lesznek elérhetők.

### <a name="pkcs-certificate-profile-supported-attributes"></a>A PKCS-tanúsítványprofil által támogatott attribútumok

|Attribútum | Az Intune által támogatott formátumok | Symantec felhőalapú hitelesítésszolgáltató által támogatott formátumok | Eredmény |
| --- | --- | --- | --- |
| Tulajdonos neve |Az Intune az alábbi három formátumban támogatja a tulajdonos nevének megadását: <br><br> 1. Köznapi név <br> 2. Köznapi név e-mail-címmel együtt <br> 3. Köznapi név mint e-mail-cím <br><br> Például: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | Symantec hitelesítésszolgáltató további attribútumokat is támogat.  Ha további attribútumokat szeretne kiválasztani, akkor azokhoz rögzített értéket kell definiálni a Symantec tanúsítványprofil sablonjában.| A tulajdonos neveként a PKCS-tanúsítványkérelmekben található köznapi nevet vagy e-mail-címet használjuk. <br><br> Ha a kiválasztott attribútumok értékei nem egyeznek az Intune tanúsítványprofilban és a Symantec tanúsítványprofil sablonjában, akkor a Symantec hitelesítésszolgáltató által kiállított tanúsítvány nem lesz elérhető.|
| Tulajdonos alternatív neve (SAN) | Az Intune a következő SAN-mezőértékeket támogatja: <br><br> AltNameTypeEmail <br><br> AltNameTypeUpn <br><br> AltNameTypeOtherName (kódolt érték) | A Symantec felhőalapú hitelesítésszolgáltató is támogatja ezeket a paramétereket. Ha további attribútumokat szeretne kiválasztani, akkor azokhoz rögzített értéket kell definiálni a Symantec tanúsítványprofil sablonjában. <br><br> AltNameTypeEmail: Ez a típus nem található az SAN, ha az AltNameTypeUpn értékét használja.  Ha az AltNameTypeUpn sem található az SAN-ben, a program a tulajdonosnév értékét használja, hogyha az e-mail-cím formátumú.  Ha az érték továbbra sem található, az Intune Tanúsítvány-összekötő nem tud kiállítani tanúsítványt. <br><br> Pl.: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> AltNameTypeUpn: Ez a típus nem található az SAN, ha az AltNameTypeEmail értékét használja. Ha az AltNameTypeEmail sem található a SAN-ben, a program a tulajdonosnév értékét használja, hogyha az e-mail-cím formátumú.  Ha az érték továbbra sem található, az Intune Tanúsítvány-összekötő nem tud kiállítani tanúsítványt.  <br><br> Pl.: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> AltNameTypeOtherName: Ez a típus nem található az SAN, ha az Intune tanúsítvány-összekötő nem tudja kiállítani tanúsítványt. <br><br> Pl.: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  **Fontos megjegyzés:** Ez a mező értékét a Symantec hitelesítésszolgáltató csak kódolt formátumban (hexadecimális értékként) támogatja. Ezért a mezőben megadott értéket az Intune Tanúsítvány-összekötő Base 64 kódolású értékké alakítja, mielőtt elküldi a tanúsítványkérelmet. **Az Intune Tanúsítvány-összekötő nem ellenőrzi, hogy az érték már kódolva van-e.** | Nincsenek |

## <a name="troubleshooting"></a>Hibaelhárítás

Az Intune Tanúsítvány-összekötő szolgáltatásnaplói az NDES-összekötőt futtató számítógép `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs` könyvtárában érhetők el. Nyissa meg a naplókat az [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) alkalmazással, és keresse meg a kivételeket vagy hibaüzeneteket.

| Probléma/hibaüzenet | A megoldás lépései |
| --- | --- |
| Nem sikerül bejelentkezni az Intune-bérlői rendszergazdai fiókkal az NDES-összekötő felhasználói felületére | Ez akkor fordulhat elő, ha a helyi tanúsítvány-összekötő nincs engedélyezve az Intune felügyeleti portálon. A probléma megoldásához kövesse az alábbi lépéseket: <br><br> A Silver Light felhasználói felületén: <br> 1. Jelentkezzen be az [Intune felügyeleti portálra](https://admin.manage.microsoft.com). <br> 2. Kattintson a FELÜGYELET lehetőségre. <br> 3. Válassza a Mobileszköz-kezelés > Tanúsítvány-összekötő lehetőséget. <br> 4. Kattintson a **Helyszíni tanúsítvány-összekötő konfigurálása** elemre. <br> 5. Jelölje be a **Tanúsítvány-összekötő engedélyezése** jelölőnégyzetet. <br> 6. Kattintson az **OK** gombra. <br><br>Vagy <br><br> Az Azure Portal felhasználói felületén: <br> 1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com) <br> 2. Lépjen a Microsoft Intune-hoz. <br> 3. Válassza az **Eszközkonfiguráció** > **Hitelesítésszolgáltató** lehetőséget. <br> 4. Kattintson az **Engedélyezés** lehetőségre. <br><br> Miután a Silver Light felhasználói felületen vagy az Azure Portalon elvégezte az előző lépéseket, próbáljon meg ismét bejelentkezni az Intune-bérlői rendszergazdai fiókjával az NDES-összekötő felhasználói felületén. |
| Az NDES-összekötő tanúsítványa nem található. <br><br> System.ArgumentNullException: Értéke nem lehet null értékű. | Az Intune Tanúsítvány-összekötő akkor jeleníti meg ezt a hibát, ha az Intune-bérlői rendszergazdai fiókkal még sosem jelentkeztek be az NDES-összekötő felhasználói felületére. <br><br> Ha a hiba nem szűnik meg, indítsa újra az Intune Connector Service szolgáltatást. <br><br> 1. Nyissa meg a services.msc programot. <br> 2. Válassza ki az **Intune Connector Service** lehetőséget. <br> 3. Kattintson rá a jobb egérgombbal, majd válassza az **Újraindítás** lehetőséget.|
| NDES Connector - IssuePfx -Generic Exception: (NDES-összekötő - IssuePfx - Általános kivétel:) <br> System.NullReferenceException: Objektumhivatkozás nincs beállítva az objektum egy példányát. | Ez a hiba átmeneti. Indítsa újra az Intune Connector Service szolgáltatást. <br><br> 1. Nyissa meg a services.msc programot. <br> 2. Válassza ki az **Intune Connector Service** lehetőséget. <br> 3. Kattintson rá a jobb egérgombbal, majd válassza az **Újraindítás** lehetőséget. |
| Symantec Provider - Failed to get Symantec policy “The operation has timed out” (Symantec-szolgáltató – Nem sikerült beolvasni a Symantec házirendet. „A művelet túllépte az időkorlátot.”) | Az Intune Tanúsítvány-összekötő időtúllépési hibát észlelt a Symantec hitelesítésszolgáltatóval folytatott kommunikáció közben. Ha ez a hiba többször előfordul, növelje a kapcsolódási időtúllépés értékét, és próbálkozzon újra. <br><br> A kapcsolódási időtúllépés értékének növeléséhez: <br> 1. Lépjen az NDES-összekötő számítógépére. <br>2. Nyissa meg a `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config` fájlt a Jegyzettömbben. <br> 3. Növelje az időkorlát értékét a következő paraméternél: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Indítsa újra az Intune Connector Service szolgáltatást. <br><br> Ha a probléma továbbra is fennáll, forduljon a Symantec ügyfélszolgálathoz. |
| Symantec Provider - Failed to get client certificate (Symantec szolgáltató - Nem sikerült beolvasni az ügyféltanúsítványt.) | Az Intune Tanúsítvány-összekötőnek nem sikerült beolvasni az erőforrás-engedélyezési tanúsítványt a helyi számítógép személyes tanúsítványtárolójából. A probléma megoldásához, győződjön meg arról, hogy az erőforrás-engedélyezési tanúsítványt és annak titkos kulcsát a helyi számítógép személyes tanúsítványtárolójába telepítette. <br><br> **Megjegyzés:** Az erőforrás-engedélyezési tanúsítványt a Symantec hitelesítésszolgáltatótól kell beszerezni. További részletekért forduljon a Symantec ügyfélszolgálathoz. | 
| A Symantec szolgáltató – nem sikerült beolvasni a Symantec házirendet "a kérelem megszakadt: Nem sikerült létrehozni az SSL/TLS biztonságos csatornát." | Ez a hiba a következő esetekben jelentkezhet: <br><br> 1. Az Intune Tanúsítvány-összekötő szolgáltatás nem rendelkezik a szükséges engedéllyel az erőforrás-engedélyezési tanúsítvány és a hozzá tartozó titkos kulcs beolvasásához a helyi számítógép személyes tanúsítványtárolójából. A probléma megoldásához ellenőrizze az összekötő szolgáltatást futtatási környezeteként használt fiókot a services.msc alkalmazással. Az összekötő szolgáltatást az NT AUTHORITY\SYSTEM környezetben kell futni. <br><br> 2. Az Intune felügyeleti portálon érvénytelen teljes tartománynevet állítottak be a PKCS-tanúsítványprofilban a Symantec hitelesítésszolgáltató alapszolgáltatásánál. A teljes tartománynév a következőre hasonlít: `pki-ws.symauth.com`. A probléma megoldásához érdeklődjön a Symantec ügyfélszolgálatánál, hogy az előfizetéséhez megfelelő URL-cím van-e beállítva. <br><br> 3. Az Intune Tanúsítvány-összekötőnek nem sikerül hitelesítenie magát az Symantec hitelesítésszolgáltatónál az erőforrás-engedélyezési tanúsítvánnyal, mert nem tudja beolvasni a tanúsítványhoz tartozó titkos kulcsot. A probléma megoldásához, győződjön meg arról, hogy az erőforrás-engedélyezési tanúsítványt és annak titkos kulcsát a helyi számítógép személyes tanúsítványtárolójába telepítette. <br><br> Ha a probléma továbbra is fennáll, forduljon a Symantec ügyfélszolgálathoz. |
| Symantec Provider - Failed to get Symantec policy “A request element is not understood.” (Symantec szolgáltató – Nem sikerült beolvasni a Symantec szabáyzatot. „A kérelem egy eleme nem értelmezhető.”) | Az Intune Tanúsítvány-összekötőnek nem sikerült beolvasni a Symantec tanúsítványprofil sablonját, mert az ügyfélprofil objektumazonosítója nem felel meg az Intune tanúsítványprofilnak. A hiba akkor is jelentkezhet, ha az Intune Tanúsítvány-összekötő nem találja az adott ügyfélprofil objektumazonosítójához társított tanúsítványprofil-sablont a Symantec hitelesítésszolgáltatón. <br><br> A probléma megoldásához szerezze be az ügyfélprofil helyes objektumazonosítóját a Symantec hitelesítésszolgáltatótól elérhető Symantec-tanúsítványsablonból. Ezután frissítse a PKCS-tanúsítványprofilt az Intune felügyeleti portálon. <br><br> Szerezze be az ügyfélprofil objektumazonosítóját a Symantec hitelesítésszolgáltatótól: <br> 1. Jelentkezzen be Symantec hitelesítésszolgáltató felügyeleti portáljára. <br> 2. Kattintson a Manage Certificate Profiles (Tanúsítványprofilok kezelése) lehetőségre. <br> 3. Válassza ki a használni kívánt tanúsítványprofilt. <br> 4. Jegyezze fel a tanúsítványprofil objektumazonosítóját. Az objektumazonosító a következő példához hasonlóan néz ki: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Frissítse a PKCS-tanúsítványprofilt a megfelelő objektumazonosítóval: <br>1. Jelentkezzen be az Intune felügyeleti portálra. <br> 2. Keresse meg a PKCS-tanúsítványprofilt, és kattintson a **Szerkesztése** lehetőségre. <br> 3. Frissítse a tanúsítványprofil objektumazonosítóját a tanúsítványsablon nevének mezőjében. <br> 4. Mentse a PKCS-tanúsítványprofilt. |
| Symantec Provider - Policy Verification failed. (Symantec szolgáltató - A szabáyzat ellenőrzése nem sikerült.) <br><br> Attribute does not fall under Symantec supported Certificate template attributes list (Az attribútum nem szerepel a Symantec által támogatott tanúsítványsablonok attribútumlistáján.) | A Symantec hitelesítésszolgáltató akkor jeleníti meg ezt az üzenetet, ha különbséget észlel a Symantec tanúsítványprofil sablonja és az Intune tanúsítványprofil között. A problémát valószínűleg egy eltérő attribútum okozza a SubjectName vagy a SubjectAltName beállításoknál. <br><br> A probléma megoldásához, ügyeljen arra, hogy a Symantec tanúsítványprofil sablonjában az Intune által támogatott attribútumokat válasszon ki a SubjectName és SubjectAltName beállításokhoz. További részletekért tekintse meg az Intune által támogatott attribútumok listáját a tanúsítványok paramétereit ismertető részben. |
| Néhány felhasználói eszköz nem kap PKCS-tanúsítványt a Symantec hitelesítésszolgáltatótól. | Ez a hiba akkor fordul elő, ha az egyszerű felhasználónév különleges karaktereket, például aláhúzásjelet, tartalmaz (például: `global_admin@intune.onmicrosoft.com`). <br><br> A Symantec hitelesítésszolgáltató nem támogatja a speciális karakterek használatát a mail_firstname és mail_lastname értékekben. <br><br> A problémát az alábbi lépésekkel oldhatja meg: <br><br> 1.   Jelentkezzen be Symantec hitelesítésszolgáltató felügyeleti portáljára. <br> 2. Lépjen a Manage Certificate Profiles (Tanúsítványprofilok kezelése) lehetőségre. <br> 3.   Kattintson az Intune-hoz használt tanúsítványprofilra. <br> 4.  Kattintson a Customize options (Beállítások testreszabása) hivatkozásra. <br> 5.   Kattintson az Advanced options (Speciális beállítások) gombra. <br> 6.  A Certificate fields – Subject DN (Tanúsítványmezők – Tulajdonos tartományneve) alatt hozzon létre egy Common Name (CN) mezőt, és törölje a meglévő Common Name (CN) mezőt. A mező hozzáadását és törlését együtt kell végrehajtani. <br> 7.    Kattintson a Mentés gombra. <br><br> A fenti módosítás után a Symantec tanúsítványprofil a „CN =<upn>” értéket kéri a mail_firstname és mail_lastname helyett. |
| A felhasználó manuálisan törölt egy már telepített tanúsítványt az eszközéről. | Az Intune újból telepíti ugyanazt a tanúsítvány a következő bejelentkezéskor vagy a házirendek érvényesítésekor. Ebben az esetben az NDES-összekötő nem kapja meg a PKCS-tanúsítványkérelmet. |

## <a name="next-steps"></a>További lépések

- Az ebben és a [Mik azok a Microsoft Intune eszközprofilok?](device-profiles.md) című cikkben olvasható információkra támaszkodva kezelheti szervezete eszközeit és a rajtuk található tanúsítványokat.

[InstallConnector]:  ./media/certificates-symantec-connector-install.png "Az Intune Tanúsítvány-összekötő telepítése és a PFX terjesztés kiválasztása"
[ConfigureConnector]: ./media/certificates-symantec-configure-connector-configure.png "Az Intune Tanúsítvány-összekötő konfigurálása"
[ConfigureProfile]: ./media/certificates-symantec-pkcs-example.png "PKCS-tanúsítványprofil létrehozása az Azure Portalon"
