---
title: "PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Útmutató az infrastruktúra konfigurálásához és az SCEP-tanúsítványprofilok ezt követő létrehozásához és eszközökhöz rendeléséhez az Intune-ban."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 11bb2cbcf14abe5966e0b203ba3466adc12bd4dd
ms.lasthandoff: 04/24/2017



---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ez a témakör az infrastruktúra konfigurálását és az SCEP-tanúsítványprofilok ezt követő, az Intune-nal végzett létrehozását és eszközökhöz rendelését ismerteti.

Ha bármilyen tanúsítványalapú hitelesítést szeretne végrehajtani a szervezetben, szüksége lesz egy vállalati hitelesítésszolgáltatóra.

A PKCS-tanúsítványprofilok használatához a vállalati hitelesítésszolgáltatón kívül a következőkre is szüksége lesz:

-   Egy számítógép, amely képes kommunikálni a hitelesítésszolgáltatóval. Alternatív megoldásként használhatja magát a hitelesítésszolgáltató számítógépet is.

-  A hitelesítésszolgáltatóval kommunikálni képes számítógépen futó Intune Certificate Connector.

## <a name="important-terms"></a>Fontos szakkifejezések


-    **Active Directory-tartomány**: A jelen szakaszban felsorolt összes kiszolgálónak (a webalkalmazás-proxykiszolgáló kivételével) csatlakoznia kell a szervezet Active Directory-tartományához.

-  **Hitelesítésszolgáltató**: Olyan vállalati hitelesítésszolgáltató (CA), amelyen a Windows Server 2008 R2 vagy újabb rendszer Enterprise Edition verziója fut. Az önálló hitelesítésszolgáltató nem támogatott. A hitelesítésszolgáltató konfigurálásáról lásd: [Hitelesítésszolgáltató telepítése](http://technet.microsoft.com/library/jj125375.aspx).
    Ha a hitelesítésszolgáltatója Windows Server 2008 R2 rendszeren fut, [telepítenie kell a KB2483564 jelű gyorsjavítást](http://support.microsoft.com/kb/2483564/).

-  **Egy számítógép, amely képes kommunikálni a hitelesítésszolgáltatóval**: Másik megoldásként használhatja magát a hitelesítésszolgáltató számítógépet is.
-  **Microsoft Intune Tanúsítvány-összekötő**: Töltse le a **Tanúsítvány-összekötő** telepítőjét (**ndesconnectorssetup.exe**) az Azure Portalról. Ezután futtassa az **ndesconnectorssetup.exe** fájlt azon a számítógépen, amelyre telepíteni szeretné az tanúsítvány-összekötőt. A PKCS-tanúsítványprofilok esetében a hitelesítésszolgáltatóval kommunikáló számítógépre telepítse a Tanúsítvány-összekötőt.
-  **Webalkalmazás-proxykiszolgáló** (nem kötelező): Webalkalmazás-proxykiszolgálóként (WAP) olyan kiszolgálót használhat, amelyen Windows Server 2012 R2 vagy újabb verziójú rendszer fut. Ez a konfiguráció:
    -  Lehetővé teszi, hogy az eszközök az interneten keresztül fogadjanak tanúsítványokat.
    -  Biztonsági ajánlás olyan környezetekben, ahol az eszközök az interneten keresztül csatlakozva kapnak és újítanak meg tanúsítványokat.

 > [!NOTE]           
> -    A WAP-ot futtató kiszolgálón [telepíteni kell egy frissítést](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) ahhoz, hogy az támogassa a Hitelesítésszolgáltató hálózati eszközök tanúsítványigénylési szolgáltatása (NDES) által használt hosszú URL-címeket. Ez a frissítés megtalálható a [2014. decemberi kumulatív frissítésben](http://support.microsoft.com/kb/3013769), illetve önállóan a [KB3011135-as jelű frissítésként](http://support.microsoft.com/kb/3011135).
>-  Ezenkívül a WAP-ot futtató kiszolgálónak rendelkeznie kell egy SSL-tanúsítvánnyal, amely a külső ügyfeleknek közzétett nevet egyezteti, valamint meg kell bíznia az NDES-kiszolgálón használt SSL-tanúsítványban. E tanúsítványok segítségével a WAP-kiszolgáló képes megszakítani az ügyfelek SSL-kapcsolatát, illetve új SSL-kapcsolatot létrehozni az NDES-kiszolgálóval.
    A WAP-hoz szükséges tanúsítványokkal kapcsolatos további tudnivalókért olvassa el a **Tanúsítványok megtervezése** című szakaszt a [Felkészülés az alkalmazások webalkalmazás-proxyval való közzétételére](https://technet.microsoft.com/library/dn383650.aspx) című cikkben. A WAP-kiszolgálókkal kapcsolatos általános információkért tekintse meg [A webalkalmazás-proxy használata](http://technet.microsoft.com/library/dn584113.aspx) című témakört.|


## <a name="certificates-and-templates"></a>Tanúsítványok és sablonok

|Objektum|Részletek|
|----------|-----------|
|**Tanúsítványsablon**|Ezt a sablont a vállalati hitelesítésszolgáltatón tudja konfigurálni.|
|**Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványa**|Ezt a tanúsítványt **.cer** fájlként kell exportálnia a vállalati hitelesítésszolgáltatótól vagy bármely olyan eszközről, amely megbízik a vállalati hitelesítésszolgáltatóban, majd a megbízható hitelesítésszolgáltatói tanúsítványprofillal ki kell osztania az eszközöknek.<br /><br />Operációsrendszer-platformonként egy darab megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványt használjon, és társítsa azt az egyes létrehozott megbízható főtanúsítvány-profilokkal.<br /><br />Szükség esetén további megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványokat is használhat. Ezzel például bizalmi kapcsolatot alakíthat ki egy hitelesítésszolgáltatónak, mely aláírja a kiszolgálói hitelesítési tanúsítványokat a szervezet Wi-Fi hozzáférési pontjai számára.|


## <a name="configure-your-infrastructure"></a>Az infrastruktúra konfigurálása
A tanúsítványprofilok konfigurálása előtt végre kell hajtania a következő lépéseket. Ezekhez szükség van a Windows Server 2012 R2 és az Active Directory tanúsítványszolgáltatások (ADCS) ismeretére:

- **1. lépés:** tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál
- **2. lépés:** az Intune Certificate Connector engedélyezése, telepítése és konfigurálása

## <a name="step-1---configure-certificate-templates-on-the-certification-authority"></a>1. lépés: tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál

### <a name="to-configure-the-certification-authority"></a>A hitelesítésszolgáltató konfigurálásához

1.  Hozzon létre egy új egyéni sablont a vállalati hitelesítésszolgáltatón a Tanúsítványsablonok beépülő modullal, vagy másoljon és szerkesszen egy meglévő sablont (például a Felhasználó sablont) a PKCS szolgáltatással való használatra.

    A sablonnak legalább az alábbiakat kell tartalmaznia:

    -   Adjon meg egy leíró nevet a sablonnak a **Sablon megjelenítendő neve** mezőben.

    -   A **Tulajdonos neve** lapon válassza **A kérelem fogja tartalmazni**lehetőséget. (A biztonságot az Intune NDES-házirendmodulja fogja érvényesíteni.)

    -   A **Kiterjesztések** lapon győződjön meg róla, hogy az **Alkalmazás-házirendek leírása** lista tartalmazza az **Ügyfél-hitelesítés**elemet.

        > [!IMPORTANT]
        > iOS- és macOS-tanúsítványsablonok esetében a **Kiterjesztések** lapon módosítsa a **Kulcshasználat** beállítást, és ügyeljen rá, hogy **Az aláírás igazolja az eredetet** jelölőnégyzet ne legyen bejelölve.

2.  Ellenőrizze az **Érvényesség időtartama** beállítást a sablon **Általános** lapján. Alapértelmezés szerint az Intune a sablonban konfigurált értéket használja. Lehetősége van azonban arra is, hogy a hitelesítésszolgáltató konfigurálásával engedélyezze a kérelmezőnek egy másik érték megadását, amelyet aztán az Intune felügyeleti konzoljából tud megadni. Ha azt szeretné, hogy mindig a sablonban lévő érték legyen használva, hagyja ki ennek a lépésnek a hátralévő részét.

    > [!IMPORTANT]
    > Az iOS és a macOS mindig a sablonban beállított értéket használja, minden más konfigurációs beállítástól függetlenül.

    Ha a hitelesítésszolgáltató konfigurálásával lehetővé kívánja tenni a kérelmezőnek az érvényességi időszak megadását, futtassa az alábbi parancsokat a hitelesítésszolgáltatón:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Tegye közzé a Hitelesítésszolgáltató beépülő modullal a tanúsítványsablont a vállalati hitelesítésszolgáltatón.

    a.  Válassza a **Tanúsítványsablonok** csomópontot, kattintson a **Művelet**-&gt; **Új** &gt;**Kiállítandó tanúsítványsablon** lehetőségre, majd válassza ki a 2. lépésben létrehozott sablont.

    b.  Ellenőrizze a **Tanúsítványsablonok** mappában, hogy a sablon közzététele sikerült-e.

4.  A hitelesítésszolgáltató számítógépen győződjön meg róla, hogy az Intune Tanúsítvány-összekötőt futtató számítógépnek van regisztrálási engedélye, és így hozzáférhet a PKCS-tanúsítványprofil létrehozásakor használt sablonhoz. Állítsa be az engedélyt a hitelesítésszolgáltató számítógép tulajdonságainak **Biztonság** lapján.

## <a name="step-2---enable-install-and-configure-the-intune-certificate-connector"></a>2. lépés: az Intune Certificate Connector engedélyezése, telepítése és konfigurálása
Ebben a lépésben:

- A tanúsítvány-összekötő támogatásának engedélyezése
- A tanúsítvány-összekötő letöltése, telepítése és konfigurálása.

### <a name="to-enable-support-for-the-certificate-connector"></a>A tanúsítvány-összekötő támogatásának engedélyezéséhez

1.  Jelentkezzen be az Azure Portalra.
2.  Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3.  Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2.  Válassza az **Eszközök konfigurálása** panel **Beállítás** > **Hitelesítésszolgáltató** elemét.
2.  A **1. lépésnél** válassza az **Engedélyezés** lehetőséget.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>A tanúsítvány-összekötő letöltéséhez, telepítéséhez és konfigurálásához

1.  Válassza az **Eszközök konfigurálása** panel **Beállítás** > **Hitelesítésszolgáltató** elemét.
2.  Válassza **A tanúsítvány-összekötő letöltése** lehetőséget.
2.  A letöltés befejezése után futtassa a letöltött telepítőprogramot (**ndesconnectorssetup.exe**).
  Futtassa a telepítőt azon a számítógépen, amely kapcsolódni tud a hitelesítésszolgáltatóhoz. Válassza a PKCS (PFX) Distribution (PKCS (PFX) terjesztése lehetőséget, majd az **Install** (Telepítés) elemet. A telepítés befejeződése után folytassa egy tanúsítványprofil létrehozásával. Ezt a [tanúsítványprofilok konfigurálását bemutató](how-to-configure-certificates.md) cikk ismerteti.

3.  Ha a rendszer kéri az ügyféltanúsítványt a Tanúsítvány-összekötőhöz, válassza a **Kijelölés** lehetőséget, és válassza ki a telepített **ügyfél-hitelesítő** tanúsítványt.

    Miután kiválasztotta az ügyfél-hitelesítési tanúsítványt, a rendszer visszairányítja az **Client Certificate for Microsoft Intune Certificate Connector** (Ügyféltanúsítvány a Microsoft Intune Certificate Connectorhoz) felületre. Bár a választott tanúsítvány nem látható, kattintson a **Tovább** gombra a tanúsítvány tulajdonságainak megtekintéséhez. Ezután válassza a **Tovább**, majd a **Telepítés** lehetőséget.

4.  Ha a varázsló befejeződött, még mielőtt bezárná, kattintson **Launch the Certificate Connector UI**(Certificate Connector felhasználói felületének indítása) lehetőségre.

    > [!TIP]
    > Ha bezárná a varázslót a tanúsítvány-összekötő felhasználói felületének megnyitása előtt, akkor az alábbi parancs futtatásával nyithatja meg:
    >
    > **&lt;telepítési_útvonal&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  A **Certificate Connector** (Tanúsítvány-összekötő) felhasználói felületén:

    a. Válassza a **Bejelentkezés** lehetőséget, és írja be az Intune szolgáltatás rendszergazdai hitelesítő adatait, vagy egy globális felügyeleti engedéllyel rendelkező bérlői rendszergazda hitelesítő adatait.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. Váltson a **Speciális** lapra, majd adja meg egy olyan fiók hitelesítő adatait, amely rendelkezik **Tanúsítványok kiállítása és kezelése** engedéllyel a vállalati hitelesítésszolgáltatónál.

    c. Válassza az **Alkalmaz** lehetőséget.

    Bezárhatja a tanúsítvány-összekötő felhasználói felületét.

6.  Nyisson meg egy parancssort, és írja be a következőt: **services.msc**. Ezután nyomja meg az **Enter** billentyűt, a jobb egérgombbal kattintson az **Intune-összekötő szolgáltatás** elemre, majd válassza az **Újraindítás** lehetőséget.

A szolgáltatás futásának ellenőrzéséhez nyisson meg egy böngészőt, és írja be az alábbi URL-t, melynek egy **403-as** hibát kell visszaadnia:

**http:// &lt;NDES-kiszolgáló_teljes_tartományneve&gt;/certsrv/mscep/mscep.dll**


### <a name="how-to-create-a-pkcs-certificate-profile"></a>PKCS-tanúsítványprofil létrehozása

Az Azure Portalon válassza az **Eszközök konfigurálása** elemet.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
3. A profilok panelen kattintson a **Profil létrehozása** lehetőségre.
4. A **Profil létrehozása** panelen adja meg a PKCS-tanúsítványprofil nevét és leírását a **Név** és a **Leírás** mezőben.
5. Válassza ki a PKCS-tanúsítvány eszközplatformját a **Platform** legördülő lista következő elemei közül:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza a **PKCS-tanúsítvány** lehetőséget.
7. A **PKCS-tanúsítvány** panelen konfigurálja a következő beállításokat:
    - **Megújítási küszöb (%)** – Adja meg, hogy az eszköz a tanúsítvány élettartamának hány százalékos hátralévő idejénél igényelje a tanúsítvány megújítását.
    - **Tanúsítvány érvényességi időtartama** – Ha a kiállító hitelesítésszolgáltatón a **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** parancs futtatásával engedélyezte az egyéni érvényességi időtartamot, akkor meghatározhatja a tanúsítvány lejáratáig hátralévő időt.<br>A megadott tanúsítványsablonban meghatározott érvényességi időszaknál rövidebb értéket is beállíthat, hosszabbat azonban nem. Ha például a tanúsítványsablonban két év van meghatározva a tanúsítvány érvényességi idejeként, akkor egy évet beállíthat értékként, öt évet azonban nem. Az értéknek emellett a kiállító hitelesítésszolgáltató tanúsítványának hátralévő érvényességi időszakánál is kevesebbnek kell lennie.
    - **Kulcstároló-szolgáltató** (Windows 10): Itt adhatja meg, hogy a rendszer hol tárolja a tanúsítvány kulcsát. Az alábbi értékek közül választhat:
        - **Regisztrálás a platformmegbízhatósági modul kulcstároló-szolgáltatójába (ha van ilyen), máskülönben regisztrálás a szoftverkulcstároló-szolgáltatóba**
        - **Regisztrálás a platformmegbízhatósági modul kulcstároló-szolgáltatójába, máskülönben a művelet sikertelen**
        - **Regisztrálás a Passportba, máskülönben a művelet sikertelen (Windows 10 és újabb verzió)**
        - **Regisztrálás szoftverkulcstároló-szolgáltatóba**
    - **Hitelesítésszolgáltató:** Olyan vállalati hitelesítésszolgáltató (CA), amelyen a Windows Server 2008 R2 vagy újabb rendszer Enterprise kiadása fut. Az önálló hitelesítésszolgáltató nem támogatott. A hitelesítésszolgáltató konfigurálásáról lásd: [Hitelesítésszolgáltató telepítése](http://technet.microsoft.com/library/jj125375.aspx). Ha a hitelesítésszolgáltatója Windows Server 2008 R2 rendszeren fut, [telepítenie kell a KB2483564 jelű gyorsjavítást](http://support.microsoft.com/kb/2483564/).
    - **Hitelesítésszolgáltató neve** – Adja meg a hitelesítésszolgáltatója nevét.
    - **Tanúsítványsablon neve** – Válassza ki annak a tanúsítványsablonnak a nevét, amelynek használatára a Hálózati eszközök tanúsítványigénylési szolgáltatása be van állítva, és amely hozzá van adva egy kiállító hitelesítésszolgáltatóhoz.
    Ügyeljen rá, hogy a név pontosan azonos legyen a Hálózati eszközök tanúsítványigénylési szolgáltatását futtató kiszolgáló beállításjegyzékében szereplő névvel. A tanúsítványsablon valódi nevét adja meg, ne pedig a tanúsítványsablon megjelenített nevét. 
    Keresse meg a tanúsítványsablonok nevét. Ehhez nyissa meg a következő kulcsot: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. Az **EncryptionTemplate**, a **GeneralPurposeTemplate**és a **SignatureTemplate**beállítások értékei a tanúsítványsablonokat jelölik. Alapértelmezés szerint mindhárom tanúsítványsablon értéke IPSECIntermediateOffline, amely az **IPSec (offline kérelem)** megjelenített sablonnévhez tartozik. 
    - **Tulajdonos nevének formátuma** – Válassza ki a listáról, hogy az Intune hogyan hozza létre automatikusan a tulajdonos nevét a tanúsítványkérelemben. Ha a tanúsítvány felhasználóhoz tartozik, a felhasználó e-mail címét is feltüntetheti a tulajdonos nevében. A következő lehetőségek közül választhat:
        - **Nincs konfigurálva**
        - **Köznapi név**
        - **Köznapi név (e-mail is)**
        - **Köznapi név mint e-mail cím**
    - **Tulajdonos alternatív neve** – Határozza meg, hogy az Intune hogyan hozza létre automatikusan a tulajdonos alternatív nevének értékeit a tanúsítványkérelemben. Ha felhasználói tanúsítványtípust választott ki, akkor például az egyszerű felhasználónevet (UPN) is használhatja a tulajdonos alternatív neveként. Ha az ügyféltanúsítványt fogja hitelesítésre használni egy hálózati házirend-kiszolgáló felé, a tulajdonos alternatív neveként az egyszerű felhasználónevet kell beállítania.
    - **Kibővített kulcshasználat** (Android) – Válassza a **Hozzáadás** gombot, és vegye fel a kívánt értékeket a tanúsítvány felhasználási céljai közé. A legtöbb esetben a tanúsítványnál szükséges az **Ügyfél-hitelesítés** , hogy a felhasználó vagy az eszköz hitelesíthető legyen egy kiszolgálóval. Szükség szerint azonban tetszőleges más kulcshasználatot is felvehet. 
    - **Főtanúsítvány** (Android) – Válasszon ki egy olyan legfelső szintű hitelesítésszolgáltatói tanúsítványprofilt, amelyet korábban konfigurált és hozzárendelt a felhasználóhoz vagy az eszközhöz. Ennek a hitelesítésszolgáltatói tanúsítványnak a legfelső szintű tanúsítványnak kell lennie az adott tanúsítványprofilban konfigurált tanúsítványt kiállító hitelesítésszolgáltatónál. Ez a korábban létrehozott megbízható tanúsítványprofil.
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="how-to-assign-the-certificate-profile"></a>A tanúsítványprofil eszközökhöz rendelése

Mielőtt csoportokhoz rendeli a tanúsítványprofilokat, vegye figyelembe a következőket:

- Amikor csoportokhoz rendeli a tanúsítványprofilokat, a megbízható hitelesítésszolgáltatói tanúsítványprofilból származó tanúsítványfájl települ az eszközre. Az eszköz a PKCS-tanúsítványprofilt használja tanúsítványkérelem létrehozására.
- A tanúsítványprofilok csak a profil létrehozásakor használt platformot futtató eszközökre települnek.
- Tanúsítványprofilokat rendelhet felhasználógyűjteményekhez és eszközgyűjteményekhez is.
- Ha azt szeretné, hogy a tanúsítványok gyorsan megjelenjenek az eszközökön a regisztráció után, a tanúsítványprofilt felhasználócsoporthoz és ne eszközcsoporthoz rendelje hozzá. Ha eszközcsoporthoz rendeli, akkor teljes eszközregisztráció szükséges, mielőtt az eszköz megkaphatná a szabályzatokat.
- Jóllehet az egyes profilokat külön-külön rendeli hozzá, a legfelső szintű hitelesítésszolgáltató és a PKCS-profil hozzárendelésére is szükség van. Ellenkező esetben a PKCS-tanúsítványszabályzat hibát fog jelezni.

A profilok hozzárendeléséről az [Eszközprofilok hozzárendelése](how-to-assign-device-profiles.md) című cikk nyújt általános tájékoztatást.

