---
title: "SCEP-tanúsítványok konfigurálása és kezelése az Intune-nal"
titlesuffix: Azure portal
description: "A cikk tájékoztatást nyújt az infrastruktúra konfigurálásáról és az Intune SCEP-tanúsítványprofiljainak ezt követő létrehozásáról és hozzárendeléséről."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d567d85f-e4ee-458e-bef7-6e275467efce
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 03c78fde793809713e630f371a02c48393b68810
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2017
---
# <a name="configure-and-manage-scep-certificates-with-intune"></a>SCEP-tanúsítványok konfigurálása és kezelése az Intune-nal
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör bemutatja az infrastruktúra konfigurálását, majd az Egyszerű tanúsítványbeiktatási protokoll (SCEP) tanúsítványprofiljainak ezt követő létrehozását és hozzárendelését az Intune-nal.

## <a name="configure-on-premises-infrastructure"></a>A helyszíni infrastruktúra konfigurálása

-    **Active Directory-tartomány**: A jelen szakaszban felsorolt összes kiszolgálónak (a webalkalmazás-proxykiszolgáló kivételével) csatlakoznia kell a szervezet Active Directory-tartományához.

-  **Hitelesítésszolgáltató** (CA): Olyan vállalati hitelesítésszolgáltató (CA), amely a Windows Server 2008 R2 vagy újabb rendszer vállalati verzióján fut. Az önálló hitelesítésszolgáltató nem támogatott. További útmutatás a [Hitelesítésszolgáltató telepítése](http://technet.microsoft.com/library/jj125375.aspx) témakörben található.
    Ha a hitelesítésszolgáltatója Windows Server 2008 R2 rendszeren fut, [telepítenie kell a KB2483564 jelű gyorsjavítást](http://support.microsoft.com/kb/2483564/).

-  **NDES-kiszolgáló**: a Windows Server 2012 R2 vagy újabb rendszeren futó kiszolgálón telepítenie kell a hálózati eszközök tanúsítványigénylési szolgáltatását (NDES). Az Intune nem támogatja az NDES használatát, ha az olyan kiszolgálón fut, amely vállalati hitelesítésszolgáltatót is futtat. Az [Útmutató a hálózati eszközök tanúsítványigénylési szolgáltatásához](http://technet.microsoft.com/library/hh831498.aspx) című cikkből tájékozódhat arról, hogyan kell konfigurálnia a Windows Server 2012 R2 rendszert az NDES futtatására.
Az NDES-kiszolgálónak csatlakoznia kell a tartományhoz, amely a hitelesítésszolgáltatót futtatja, de nem lehet ugyanazon a kiszolgálón, mint a hitelesítésszolgáltató. További információ az NDES-kiszolgáló különálló erdőben, elszigetelt hálózaton vagy belső tartományon való telepítéséről: [Házirendmodul használata a Hálózati eszközök tanúsítványigénylési szolgáltatásával](https://technet.microsoft.com/library/dn473016.aspx).

-  **Microsoft Intune Tanúsítvány-összekötő**: Az Azure Portal webhelyről töltse le a **Tanúsítvány-összekötő** telepítőjét (**ndesconnectorssetup.exe**). Ezután futtassa az **ndesconnectorssetup.exe** fájlt azon a számítógépen, amelyre telepíteni szeretné az tanúsítvány-összekötőt. 
-  1**Webalkalmazás-proxykiszolgáló** (nem kötelező): Webalkalmazás-proxykiszolgálóként (WAP) használjon olyan kiszolgálót, amelyen a Windows Server 2012 R2 vagy újabb verziójú rendszer fut. Ez a konfiguráció:
    -  Lehetővé teszi, hogy az eszközök az interneten keresztül fogadjanak tanúsítványokat.
    -  Biztonsági ajánlás olyan környezetekben, ahol az eszközök az interneten keresztül csatlakozva kapnak és újítanak meg tanúsítványokat.

 > [!NOTE]           
> -    A WAP-ot futtató kiszolgálón [telepíteni kell egy frissítést](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) ahhoz, hogy az támogassa az NDES által használt hosszú URL-eket. Ez a frissítés megtalálható a [2014. decemberi kumulatív frissítésben](http://support.microsoft.com/kb/3013769), illetve önállóan a [KB3011135-as jelű frissítésként](http://support.microsoft.com/kb/3011135).
>-  Ezenkívül a WAP-ot futtató kiszolgálónak rendelkeznie kell egy SSL-tanúsítvánnyal, amely a külső ügyfeleknek közzétett nevet egyezteti, valamint meg kell bíznia az NDES-kiszolgálón használt SSL-tanúsítványban. E tanúsítványok segítségével a WAP-kiszolgáló képes megszakítani az ügyfelek SSL-kapcsolatát, illetve új SSL-kapcsolatot létrehozni az NDES-kiszolgálóval.
    A WAP-hoz szükséges tanúsítványokkal kapcsolatos további tudnivalókért olvassa el a **Tanúsítványok megtervezése** című szakaszt a [Felkészülés az alkalmazások webalkalmazás-proxyval való közzétételére](https://technet.microsoft.com/library/dn383650.aspx) című cikkben. WAP-kiszolgálókkal kapcsolatos általános információ: [A webalkalmazás-proxy használata](http://technet.microsoft.com/library/dn584113.aspx).|

### <a name="network-requirements"></a>A hálózatra vonatkozó követelmények

Az internet és a szegélyhálózat között engedélyezze a 443-as port használatát az összes internetes állomásról/IP-címről az NDES-kiszolgálóra irányuló forgalom számára.

A peremhálózat és a megbízható hálózat között engedélyezze a tartomány eléréséhez szükséges összes portot és protokollt a tartományhoz csatlakozó NDES-kiszolgálón. Az NDES-kiszolgálónak el kell tudnia érnie a tanúsítványkiszolgálót, a DNS-kiszolgálókat, a Configuration Manager-kiszolgálókat és a tartományvezérlőket.

Az NDES-kiszolgálót egy proxyn keresztül, például az [Azure AD-alkalmazásproxyn](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), a [webalkalmazás-proxyn](https://technet.microsoft.com/library/dn584107.aspx) vagy egy külső proxyn érdemes közzétenni.


### <a name="certificates-and-templates"></a>Tanúsítványok és sablonok

|Objektum|Részletek|
|----------|-----------|
|**Tanúsítványsablon**|Ez a sablon a vállalati hitelesítésszolgáltatón konfigurálható.|
|**Ügyfél-hitelesítési tanúsítvány**|A vállalati vagy nyilvános hitelesítésszolgáltatótól lekért tanúsítvány, melyet az NDES-kiszolgálóra kell telepítenie.|
|**Kiszolgálói hitelesítési tanúsítvány**|A vállalati vagy nyilvános hitelesítésszolgáltatótól lekért tanúsítvány. Ezt az SSL-tanúsítványt az NDES-kiszolgálón futó IIS-be kell telepítenie, majd kötést kell létrehoznia.|
|**Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványa**|Ezt a tanúsítványt **.cer** fájlként kell exportálnia a legfelső szintű hitelesítésszolgáltatótól vagy bármely olyan eszközről, amely megbízik a legfelső szintű hitelesítésszolgáltatóban, majd hozzá kell rendelnie az eszközökhöz a megbízható hitelesítésszolgáltatói tanúsítványprofillal.<br /><br />Operációsrendszer-platformonként egy darab megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványt használjon, és társítsa azt az egyes létrehozott megbízható főtanúsítvány-profilokkal.<br /><br />Szükség esetén további megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványokat is használhat. Ezzel például bizalmi kapcsolatot alakíthat ki egy hitelesítésszolgáltatónak, mely aláírja a kiszolgálói hitelesítési tanúsítványokat a szervezet Wi-Fi hozzáférési pontjai számára.|

### <a name="accounts"></a>Fiókok

|Név|Részletek|
|--------|-----------|
|**NDES szolgáltatásfiók**|Adjon meg egy tartományfelhasználói fiókot NDES szolgáltatásfiókként.|

## <a name="configure-your-infrastructure"></a>Az infrastruktúra konfigurálása
A tanúsítványprofilok konfigurálása előtt végre kell hajtania az alábbi feladatokat, melyekhez a Windows Server 2012 R2 rendszerhez és az Active Directory tanúsítványszolgáltatásokhoz (ADCS) kapcsolódó ismeretek szükségesek:

**1. lépés**: NDES szolgáltatásfiók létrehozása

**2. lépés**: Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál

**3. lépés**: Előfeltételek konfigurálása az NDES-kiszolgálón

**4. lépés**: Az NDES Intune-nal való használatának konfigurálása

**5. lépés**: Az Intune Tanúsítvány-összekötő engedélyezése, telepítése és konfigurálása

#### <a name="step-1---create-an-ndes-service-account"></a>1. lépés – NDES szolgáltatásfiók létrehozása

Hozzon létre egy tartományfelhasználói fiókot, melyet NDES szolgáltatásfiókként fog használni. Ezt a fiókot kell megadnia a sablonok vállalati hitelesítésszolgáltatónál való konfigurálásakor, még mielőtt telepítené és konfigurálná az NDES-t. Gondoskodjon arról, hogy a felhasználó rendelkezzen az alapértelmezett jogokkal, valamint a következő jogokkal: **Helyi bejelentkezés engedélyezése**, **Bejelentkezés szolgáltatásként** és **Bejelentkezés kötegfájlfolyamatként**. Egyes szervezeteknél olyan korlátozási szabályzatok lehetnek érvényben, amelyek letiltják ezeket a jogokat.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>2. lépés – Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál
A feladat tartalma:

-   Tanúsítványsablon konfigurálása az NDES számára

-   Tanúsítványsablon közzététele az NDES számára

##### <a name="to-configure-the-certification-authority"></a>A hitelesítésszolgáltató konfigurálásához

1.  Jelentkezzen be vállalati rendszergazdaként.

2.  A vállalati hitelesítésszolgáltatónál a Tanúsítványsablonok beépülő modullal hozzon létre egy új egyéni sablont (vagy másoljon és szerkesszen egy meglévő sablont, például a Felhasználó sablont) az NDES szolgáltatással való használatra.

    >[!NOTE]
    > Az NDES tanúsítványsablonnak v2 tanúsítványsablonon kell alapulnia (Windows 2003-kompatibilitással).

    A sablonnak az alábbi beállításokkal kell rendelkeznie:

    -   Adjon meg egy leíró nevet a sablonnak a **Sablon megjelenítendő neve** mezőben.

    -   A **Tulajdonos neve** lapon válassza **A kérelem fogja tartalmazni**lehetőséget. (A biztonságot az Intune NDES-házirendmodulja fogja érvényesíteni.)

    -   A **Kiterjesztések** lapon győződjön meg róla, hogy az **Alkalmazás-házirendek leírása** lista tartalmazza az **Ügyfél-hitelesítés**elemet.

        > [!IMPORTANT]
        > iOS- és macOS-tanúsítványsablonok esetében a **Kiterjesztések** lapon módosítsa a **Kulcshasználat** beállítást, és ügyeljen rá, hogy **Az aláírás az eredet igazolása** jelölőnégyzet ne legyen bejelölve.

    -   A **Biztonság** lapon adja hozzá az NDES szolgáltatásfiókot, és adjon meg hozzá **Regisztrálás** engedélyt a sablonhoz. Az SCEP-profilokat létrehozó Intune-rendszergazdáknak **olvasási** jogokkal kell rendelkezniük, hogy az SCEP-profilok létrehozása során megnyithassák a sablont.

    > [!NOTE]
    > A tanúsítványok visszavonásához az NDES szolgáltatásfiók a *Tanúsítványok kiállítása és kezelése* nevű jogosultságot igényli a tanúsítványprofilok által használt összes tanúsítványprofilhoz.

3.  Ellenőrizze az **Érvényesség időtartama** beállítást a sablon **Általános** lapján. Alapértelmezés szerint az Intune a sablonban konfigurált értéket használja. Lehetősége van azonban arra is, hogy a hitelesítésszolgáltató konfigurálásával engedélyezze a kérelmezőnek egy másik érték megadását, amelyet aztán az Intune felügyeleti konzoljából tud megadni. Ha azt szeretné, hogy mindig a sablonban lévő érték legyen használva, hagyja ki ennek a lépésnek a hátralévő részét.

    > [!IMPORTANT]
    > Az iOS és a macOS mindig a sablonban beállított értéket használja, minden más konfigurációs beállítástól függetlenül.

Az alábbiakban egy meglévő konfigurációt példaként bemutató képernyőképeket láthat.

![Sablon, a kérelmek kezelésére szolgáló lap](.\media\scep_ndes_request_handling.png)

![Sablon, a tulajdonos nevének megadására szolgáló lap](.\media\scep_ndes_subject_name.jpg)

![Sablon, a biztonsági beállításokat tartalmazó lap](.\media\scep_ndes_security.jpg)

![Sablon, a bővítményeket tartalmazó lap](.\media\scep_ndes_extensions.jpg)

![Sablon, a tanúsítvány kiállításának feltételeit tartalmazó lap](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Az Alkalmazás-házirendek beállításnál csak azokat az alkalmazás-házirendeket adja hozzá, amelyekre valóban szüksége van. A kiválasztott elemekkel kapcsolatban kérje ki a biztonsági rendszergazda véleményét is.



Ha a hitelesítésszolgáltató konfigurálásával lehetővé kívánja tenni a kérelmezőnek az érvényességi időszak megadását:

1. Futtassa az alábbi parancsokat a hitelesítésszolgáltatón:
    - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
    - **net stop certsvc**
    - **net start certsvc**
2. Tegye közzé a Hitelesítésszolgáltató beépülő modullal a tanúsítványsablont a vállalati hitelesítésszolgáltatón.
    Válassza a **Tanúsítványsablonok** csomópontot, kattintson a **Művelet**-&gt; **Új** &gt; **Kiállítandó tanúsítványsablon** lehetőségre, majd válassza ki a 2. lépésben létrehozott sablont.
3. Ellenőrizze a **Tanúsítványsablonok** mappában, hogy a sablon közzététele sikerült-e.


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>3. lépés – Előfeltételek konfigurálása az NDES-kiszolgálón
A feladat tartalma:

-   Az NDES hozzáadása egy Windows Server-kiszolgálóhoz, és az IIS konfigurálása az NDES támogatására

-   Az NDES szolgáltatásfiók hozzáadása a IIS_IUSR csoporthoz

-   Az NDES szolgáltatásfiók egyszerű szolgáltatásnevének beállítása




   1.  Jelentkezzen be az NDES szolgáltatásnak helyt adó kiszolgálón **Vállalati rendszergazdaként**, és telepítse az NDES-t a [Szerepkörök és szolgáltatások hozzáadása varázslóval](https://technet.microsoft.com/library/hh831809.aspx):

    1.  A varázslóban válassza az **Active Directory tanúsítványszolgáltatások** lehetőséget az AD CS szerepkör-szolgáltatások eléréséhez. Válassza a **Hálózati eszközök tanúsítványigénylési szolgáltatása**lehetőséget, törölje a jelet a **Hitelesítésszolgáltató**jelölőnégyzetből, és fejezze be a varázslót.

        > [!TIP]
        > A varázsló **Telepítési folyamat** lapján ne kattintson a **Bezárás**gombra. Ehelyett kattintson **Az Active Directory tanúsítványszolgáltatások beállítása a célkiszolgálón**hivatkozásra. Ekkor megnyílik **Az Active Directory tanúsítványszolgáltatások beállítása** varázsló, amelyet a következő feladathoz kell használnia. Ha megnyílt Az Active Directory tanúsítványszolgáltatások beállítása varázsló, bezárhatja a Szerepkörök és szolgáltatások hozzáadása varázslót.

    2.  Az NDES kiszolgálóhoz való hozzáadásakor a varázsló az IIS-t is telepíti. Az IIS-nek az alábbi konfigurációval kell rendelkeznie:

        -   **Webkiszolgáló** &gt; **Biztonság** &gt; **Kérelemszűrés**

        -   **Webkiszolgáló** &gt; **Alkalmazásfejlesztés** &gt; **ASP.NET 3.5**. Az ASP.NET 3.5 telepítése telepíti a .NET-keretrendszer 3.5-öt is. A .NET-keretrendszer 3.5 telepítésekor a **.NET-keretrendszer 3.5** alapszolgáltatásai mellett telepítse a **HTTP-aktiválás**szolgáltatást is.

        -   **Webkiszolgáló** &gt; **Alkalmazásfejlesztés** &gt; **ASP.NET 4.5**. Az ASP.NET 4.5 telepítése telepíti a .NET-keretrendszer 4.5-öt is. A .NET-keretrendszer 4.5 telepítésekor a **.NET-keretrendszer 4.5** alapszolgáltatásai mellett telepítse az **ASP.NET 4.5** és a **WCF-szolgáltatások** &gt; **HTTP-aktiválás** szolgáltatását is.

        -   **Felügyeleti eszközök** &gt; **Kompatibilitás az IIS 6 kezelésével** &gt; **Kompatibilitás az IIS 6 metabázisával**

        -   **Felügyeleti eszközök** &gt; **Kompatibilitás az IIS 6 kezelésével** &gt; **Kompatibilitás az IIS 6 WMI-vel**

  2.  Vegye fel a kiszolgálón az NDES szolgáltatásfiókot az **IIS_IUSR** csoport tagjaként.

   3.  Futtassa egy emelt jogosultságszintű parancssorból az alábbi parancsot az NDES szolgáltatásfiók egyszerű szolgáltatásnevének beállításához:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Ha például az NDES kiszolgáló neve **Kiszolgalo01**, a tartomány **Contoso.com**és a szolgáltatásfiók **NDESSzolgaltatas**, akkor az alábbi parancsot kell használnia:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>4. lépés – Az NDES Intune-nal való használatának konfigurálása
A feladat tartalma:

-   Az NDES konfigurálása a vállalati hitelesítésszolgáltatóval való használatra

-   SSL-tanúsítvány kötésének létrehozása az IIS-ben

-   Kérelemszűrés konfigurálása az IIS-ben


1.  Nyissa meg az NDES-kiszolgálón Az Active Directory tanúsítványszolgáltatások beállítása varázslót, és végezze el az alábbi konfigurációs lépéseket:

    > [!TIP]
    > Ha az előző feladatban rákattintott a hivatkozásra, akkor ez a varázsló már meg van nyitva. Ellenkező esetben nyissa meg a Kiszolgálókezelőt az Active Directory tanúsítványszolgáltatások telepítés utáni konfigurációjának eléréséhez.

    -   A **Szerepkör-szolgáltatások** lapon válassza a **Hálózati eszközök tanúsítványigénylési szolgáltatása**lehetőséget.

    -   A **Hálózati eszközök tanúsítványigénylési szolgáltatásának szolgáltatásfiókja** lapon adja meg az NDES szolgáltatásfiókot.

    -   A **Hitelesítésszolgáltató a Hálózati eszközök tanúsítványigénylési szolgáltatásához** lapon kattintson a **Kijelölés**lehetőségre, és válassza ki azt a vállalati hitelesítésszolgáltatót, amelyen a tanúsítványsablont konfigurálta.

    -   A **Titkosítás a Hálózati eszközök tanúsítványigénylési szolgáltatása esetén** lapon adja meg a kulcshosszt a vállalati követelményeknek megfelelően.

    A **Megerősítés** lapon kattintson a **Konfigurálás** lehetőségre a varázsló befejezéséhez.

2.  Miután a varázsló befejeződött, szerkessze az NDES-kiszolgálón az alábbi beállításkulcsot:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    A kulcs szerkesztéséhez állapítsa meg a tanúsítványsablon **Kérelmek kezelése** lapján, hogy mi a sablon **célja**, majd szerkessze a beállításjegyzék megfelelő bejegyzését úgy, hogy felülírja a meglévő adatokat a tanúsítványsablon 1. feladatban megadott nevével (tehát nem a sablon megjelenített nevével). A következő táblázat a tanúsítványsablon-céloknak megfelelő beállításjegyzék-értékeket mutatja:

    |Tanúsítványsablon célja (a Kérelmek kezelése lapon)|Szerkesztendő beállításazonosító|Az SCEP-profil Intune felügyeleti konzolban látható értéke|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Aláírás|SignatureTemplate|Digitális aláírás|
    |Titkosítás|EncryptionTemplate|Kulcstitkosítás|
    |Aláírás és titkosítás|GeneralPurposeTemplate|Kulcstitkosítás<br /><br />Digitális aláírás|
    Ha például a tanúsítványsablon célja **Titkosítás**, akkor az **EncryptionTemplate** azonosító értékét kell a tanúsítványsablon nevére cserélnie.

3. Az NDES-kiszolgálóra rendkívül hosszú URL-címek (lekérdezések) érkeznek, melyekhez két beállításjegyzékbeli bejegyzést kell felvennie:

    |Tartózkodási hely|Érték|Típus|Adat|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (decimális)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (decimális)|


4. Az IIS-kezelőben válassza az **Alapértelmezett webhely** -> **Kérésszűrés** -> **Szolgáltatás beállításainak szerkesztése** lehetőséget, majd módosítsa az **URL-cím maximális hossza** és a **Lekérdezés-karakterlánc maximális hossza** beállítás értéket a következőre: *65534*, ahogy az a képen is látható.

    ![Maximális URL-hossz és lekérdezéshossz az IIS-ben](.\media\SCEP_IIS_max_URL.png)

5.  Indítsa újra a kiszolgálót. A módosítások véglegesítéséhez nem elég, ha a kiszolgálón futtatja az **iisreset** parancsot.
6. Keresse meg a következőt: http://*FQDN*/certsrv/mscep/mscep.dll. Az alábbihoz hasonló NDES-oldalnak kell megjelennie:

    ![NDES teszt](.\media\SCEP_NDES_URL.png)

    Ha **503 – A szolgáltatás nem érhető el** hibát kap, tekintse meg az eseménymegjelenítőt. Valószínű, hogy az alkalmazáskészlet azért állt le, mert az NDES-felhasználó nem rendelkezik valamelyik szükséges joggal. A szükséges jogokat az 1. feladat ismerteti.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>A tanúsítványok NDES-kiszolgálón való telepítéséhez és kötéséhez

1.  Kérelmezzen a belső vagy a nyilvános hitelesítésszolgáltatótól egy **kiszolgálóhitelesítő** tanúsítványt, és telepítse az NDES-kiszolgálón. Ezután létre kell hoznia az SSL-tanúsítvány kötését az IIS-ben.

    > [!TIP]
    > Miután létrehozta az SSL-tanúsítvány kötését az IIS-ben, telepítenie kell egy ügyfél-hitelesítési tanúsítványt. Ezt a tanúsítványt bármely olyan hitelesítésszolgáltató kibocsáthatja, amelyben az NDES-kiszolgáló megbízik. Bár ez nem ajánlott eljárás, használhatja ugyanazt a tanúsítványt a kiszolgáló és az ügyfél hitelesítéséhez mindaddig, amíg a tanúsítvány mindkét kibővített kulcshasználattal rendelkezik. Ezekről a hitelesítési tanúsítványokról az alábbi lépésekből kaphat további információt.

    1.  Miután beszerezte a kiszolgálóhitelesítő tanúsítványt, nyissa meg az **IIS-kezelőt**, válassza az **Alapértelmezett webhely** lehetőséget a **Kapcsolatok** ablaktáblán, majd kattintson a **Kötések** lehetőségre a **Műveletek** ablaktáblán.

    2.  Kattintson a **Hozzáadás**lehetőségre, adja meg a **Típus** beállításnál a **https**értéket, és győződjön meg róla, hogy a port **443-ra**van állítva. (Az önálló Intune csak a 443-as portot támogatja.)

    3.  Az **SSL-tanúsítvány**beállításnál adja meg a kiszolgálóhitelesítő tanúsítványt.

        > [!NOTE]
        > Ha az NDES-kiszolgáló külső és belső nevet is használ egyetlen hálózati címhez, akkor a kiszolgálóhitelesítő tanúsítvány **Tulajdonos neve** beállításának egy külső nyilvános kiszolgálónevet, a **Tulajdonos alternatív neve** beállításának pedig egy belső kiszolgálónevet kell tartalmaznia.

2.  Kérelmezzen a belső vagy a nyilvános hitelesítésszolgáltatótól egy **ügyfél-hitelesítő** tanúsítványt, és telepítse az NDES-kiszolgálón. Ez lehet ugyanaz, mint a kiszolgálóhitelesítő tanúsítvány, ha a tanúsítvány mindkét használati módra fel van készítve.

    Az ügyfél-hitelesítő tanúsítványnak az alábbi tulajdonságokkal kell rendelkeznie:

    **Kibővített kulcshasználat** – Tartalmaznia kell az **Ügyfél-hitelesítés** szolgáltatást.

    **Tulajdonos neve** – Meg kell egyeznie annak a kiszolgálónak a DNS-nevével, amelyen a tanúsítványt telepítette (ez az NDES-kiszolgáló).

##### <a name="to-configure-iis-request-filtering"></a>Kérelmek szűrésének konfigurálása az IIS-ben

1.  Nyissa meg az NDES-kiszolgálón az **IIS-kezelőt**, válassza az **Alapértelmezett webhely** lehetőséget a **Kapcsolatok** ablaktáblán, és nyissa meg a **Kérelmek szűrése**beállítást.

2.  Kattintson a **Szolgáltatás beállításainak szerkesztése** lehetőségre, és adja meg a következő értékeket:

    **lekérdezés-karakterlánc hossza (bájt)** = **65534**

    **URL-cím maximális hossza (bájt)** = **65534**

3.  Tekintse át a következő beállításkulcsot:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Az alábbi értékeknek Duplaszó típusú bejegyzésként kell szerepelnie:

    Név: **MaxFieldLength**, decimális **65534**

    Név: **MaxRequestBytes**, decimális **65534**

4. Indítsa újra az NDES-kiszolgálót. A kiszolgáló mostantól készen áll az tanúsítvány-összekötő támogatására.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>5. lépés – Az Intune Tanúsítvány-összekötő engedélyezése, telepítése és konfigurálása
A feladat tartalma:

- Az NDES támogatásának engedélyezése az Intune-ban.

- A tanúsítvány-összekötő letöltése, telepítése és konfigurálása az NDES-kiszolgálón.

   > [!NOTE]
   > Magas rendelkezésre állás megvalósításához telepíthet több példányt a Tanúsítvány-összekötőből.

<!--1528104 we need to flesh out the HA recommendation in the note above -->

##### <a name="to-enable-support-for-the-certificate-connector"></a>A tanúsítvány-összekötő támogatásának engedélyezése

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
4. Válassza az **Eszközök konfigurálása** panel **Hitelesítésszolgáltató** elemét.
5.  Válassza az **Tanúsítvány-összekötő engedélyezése** lehetőséget.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>A tanúsítvány-összekötő letöltése, telepítése és konfigurálása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.
4. Válassza az **Eszközök konfigurálása** panel **Hitelesítésszolgáltató** elemét.
5. Válassza **A tanúsítvány-összekötő letöltése** lehetőséget.
6.  A letöltés befejezése után futtassa a letöltött telepítőt (**ndesconnectorssetup.exe**) egy Windows Server 2012 R2-kiszolgálón. A telepítés során az NDES házirendmodulja és a CRP (tanúsítványregisztrációs pont) webszolgáltatás is települ. (A CRP webszolgáltatás, melynek neve CertificateRegistrationSvc, alkalmazásként fut az IIS-ben.)

    > [!NOTE]
    > Ha önálló Intune-hoz telepíti az NDES-t, akkor a CRP szolgáltatás automatikusan települ a tanúsítvány-összekötővel együtt. Az Intune szolgáltatásnak a Configuration Managerrel való használatakor a tanúsítványregisztrációs pontot különálló helyrendszerszerepkörként telepíti.

3.  Ha a rendszer kéri az ügyféltanúsítványt a tanúsítvány-összekötőhöz, válassza a **Kijelölés** lehetőséget, majd válassza ki az **ügyfél-hitelesítő** tanúsítványt, amelyet a 3. feladatban telepített az NDES-kiszolgálóra.

    Miután kiválasztotta az ügyfél-hitelesítési tanúsítványt, a rendszer visszairányítja az **Client Certificate for Microsoft Intune Certificate Connector** (Ügyféltanúsítvány a Microsoft Intune Certificate Connectorhoz) felületre. Bár a választott tanúsítvány nem látható, kattintson a **Tovább** gombra a tanúsítvány tulajdonságainak megtekintéséhez. Ezután kattintson ismét a **Tovább**gombra, majd a **Telepítés**gombra.

4.  Ha a varázsló befejeződött, még mielőtt bezárná, kattintson **Launch the Certificate Connector UI**(Certificate Connector felhasználói felületének indítása) lehetőségre.

    > [!TIP]
    > Ha bezárná a varázslót a tanúsítvány-összekötő felhasználói felületének megnyitása előtt, akkor az alábbi parancs futtatásával nyithatja meg:
    >
    > **&lt;telepítési_útvonal&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  A **Tanúsítvány-összekötő** felhasználói felületén:

    Kattintson a **Bejelentkezés** gombra, és írja be az Intune szolgáltatás rendszergazdai hitelesítő adatait, vagy egy bérlői rendszergazda globális felügyeleti engedéllyel rendelkező hitelesítő adatait.

    Ha a szervezet proxykiszolgálót használ, és proxy szükséges ahhoz, hogy az NDES-kiszolgáló el tudja érni az internetet, kattintson a **Proxykiszolgáló használata** lehetőségre, és adja meg a proxykiszolgáló nevét és portját, illetve a csatlakozáshoz szükséges fiókadatokat.

    Váltson a **Speciális** lapra, adja meg egy olyan fiók hitelesítő adatait, amely rendelkezik **Tanúsítványok kiállítása és kezelése** engedéllyel a vállalati hitelesítésszolgáltatónál, majd kattintson az **Alkalmaz**gombra.

    Bezárhatja a tanúsítvány-összekötő felhasználói felületét.

6.  Nyisson meg egy parancssort, írja be a **services.msc** fájlnevet, nyomja meg az **Enter** billentyűt, kattintson a jobb gombbal az **Intune-összekötő szolgáltatás** elemre, és válassza az **Újraindítás** parancsot.

A szolgáltatás futásának ellenőrzéséhez nyisson meg egy böngészőt, és írja be az alábbi URL-t, melynek egy **403-as** hibát kell visszaadnia:

**http:// &lt;NDES-kiszolgáló_teljes_tartományneve&gt;/certsrv/mscep/mscep.dll**

## <a name="how-to-create-a-scep-certificate-profile"></a>SCEP-tanúsítványprofil létrehozása

1. Az Azure-portálon válassza az **Eszközök konfigurálása** elemet.
2. Az **Eszközkonfiguráció** panelen válassza a **Felügyelet** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az SCEP-tanúsítványprofil nevét és leírását a **Név** és a **Leírás** mezőben.
5. Válassza ki az SCEP-tanúsítvány eszközplatformját a **Platform** legördülő listából. Jelenleg az alábbi platformokra vonatkozóan lehet eszközkorlátozási beállításokat megadni:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza az **SCEP-tanúsítvány** lehetőséget.
7. Az **SCEP-tanúsítvány** panelen konfigurálja a következő beállításokat:
    - **Tanúsítvány érvényességi időtartama** – Ha a kiállító hitelesítésszolgáltatón a **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** parancs futtatásával engedélyezte az egyéni érvényességi időtartamot, akkor meghatározhatja a tanúsítvány lejáratáig hátralévő időt.<br>A megadott tanúsítványsablonban meghatározott érvényességi időszaknál rövidebb értéket is beállíthat, hosszabbat azonban nem. Ha például a tanúsítványsablonban két év van meghatározva a tanúsítvány érvényességi idejeként, akkor egy évet beállíthat értékként, öt évet azonban nem. Az értéknek emellett a kiállító hitelesítésszolgáltató tanúsítványának hátralévő érvényességi időszakánál is kevesebbnek kell lennie. 
    - **Kulcstároló-szolgáltató** (Windows Phone 8.1, Windows 8.1, Windows 10) – Adja meg, hogy a rendszer hol tárolja a tanúsítvány kulcsát. Az alábbi értékek közül választhat:
        - **Regisztrálás a platformmegbízhatósági modul kulcstároló-szolgáltatójába (ha van ilyen), máskülönben regisztrálás a szoftverkulcstároló-szolgáltatóba**
        - **Regisztrálás a platformmegbízhatósági modul kulcstároló-szolgáltatójába, máskülönben a művelet sikertelen**
        - **Regisztrálás a Passportba, máskülönben a művelet sikertelen (Windows 10 és újabb verzió)**
        - **Regisztrálás szoftverkulcstároló-szolgáltatóba**
    - **Tulajdonos nevének formátuma** – Válassza ki a listáról, hogy az Intune hogyan hozza létre automatikusan a tulajdonos nevét a tanúsítványkérelemben. Ha a tanúsítvány felhasználóhoz tartozik, a felhasználó e-mail címét is feltüntetheti a tulajdonos nevében. A következő lehetőségek közül választhat:
        - **Nincs konfigurálva**
        - **Köznapi név**
        - **Köznapi név (e-mail is)**
        - **Köznapi név mint e-mail cím**
        - **IMEI (Nemzetközi mobilkészülék-azonosító)**
        - **Sorozatszám**
        - **Egyéni** – Ha erre a lehetőségre kattint, egy újabb legördülő mező jelenik meg. Ezt a mezőt egyéni tulajdonosnév-formátumok megadásához használhatja. Az egyéni formátum két változót támogat: **Egyszerű név (CN)** és **E-mail (E)**. Egy vagy több változó és statikus sztring együttes használatával a következőhöz hasonló egyéni tulajdonosnév-formátumot hozhat létre: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Ebben a példában egy olyan egyéni névformátumot hozott létre, amely a CN és az E változón kívül sztringeket használ a szervezeti egység (OU), a szervezet (O), a hely (L), az állam (ST) és az ország (C) értékeként. [Ez a témakör](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) a **CertStrToName** függvényt és annak támogatott sztringjeit ismerteti.
        
    - **Tulajdonos alternatív neve** – Határozza meg, hogy az Intune hogyan hozza létre automatikusan a tulajdonos alternatív nevének értékeit a tanúsítványkérelemben. Ha felhasználói tanúsítványtípust választott ki, akkor például az egyszerű felhasználónevet (UPN) is használhatja a tulajdonos alternatív neveként. Ha az ügyféltanúsítványt hitelesítésre használja egy hálózati házirend-kiszolgáló felé, a tulajdonos alternatív neveként az egyszerű felhasználónevet kell beállítania. 
    - **Kulcshasználat** – Adja meg a tanúsítvány kulcshasználati beállításait. Az alábbi lehetőségek közül választhat: 
        - **Kulcstitkosítás**: Csak akkor engedélyezi a kulcscserét, ha a kulcs titkosítva van. 
        - **Digitális aláírás**: Csak akkor engedélyezi a kulcscserét, ha a kulcs védelmét digitális aláírás segíti. 
    - **Kulcsméret (bit)** – Adja meg, hogy hány bitet tartalmazzon a kulcs. 
    - **Kivonatoló algoritmus** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) – Válassza ki a tanúsítvánnyal használni kívánt kivonatoló algoritmust a rendelkezésre álló típusok közül. Válassza a kapcsolódó eszközöknél használható legerősebb biztonsági szintet. 
    - **Főtanúsítvány** – Válasszon ki egy olyan legfelső szintű hitelesítésszolgáltatói tanúsítványprofilt, amelyet korábban konfigurált és hozzárendelt a felhasználóhoz vagy az eszközhöz. Ennek a hitelesítésszolgáltatói tanúsítványnak a legfelső szintű tanúsítványnak kell lennie az adott tanúsítványprofilban konfigurált tanúsítványt kiállító hitelesítésszolgáltatónál. 
    - **Kibővített kulcshasználat** – Válassza a **Hozzáadás** gombot, és vegye fel a kívánt értékeket a tanúsítvány felhasználási céljai közé. A legtöbb esetben a tanúsítványnál szükséges az **Ügyfél-hitelesítés**, hogy a felhasználó vagy az eszköz hitelesíthető legyen egy kiszolgálóval. Szükség szerint azonban tetszőleges más kulcshasználatot is felvehet. 
    - **Regisztrációs beállítások**
        - **Megújítási küszöb (%)** – Adja meg, hogy az eszköz a tanúsítvány élettartamának hány százalékos hátralévő idejénél igényelje a tanúsítvány megújítását.
        - **SCEP-kiszolgálók URL-címe** – Adja meg egy vagy több olyan NDES-kiszolgáló URL-címét, amely SCEP-tanúsítványokat bocsát ki. 
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="how-to-assign-the-certificate-profile"></a>A tanúsítványprofil eszközökhöz rendelése

Mielőtt csoportokhoz rendeli a tanúsítványprofilokat, vegye figyelembe a következőket:

- Amikor csoportokhoz rendeli a tanúsítványprofilokat, a megbízható hitelesítésszolgáltatói tanúsítványprofilból származó tanúsítványfájl települ az eszközre. Az eszköz az SCEP-tanúsítványprofilt használja tanúsítványkérelem létrehozására.
- A tanúsítványprofilok csak a profil létrehozásakor használt platformot futtató eszközökre települnek.
- Tanúsítványprofilokat rendelhet felhasználógyűjteményekhez és eszközgyűjteményekhez is.
- Ha azt szeretné, hogy a tanúsítványok gyorsan megjelenjenek az eszközökön a regisztráció után, a tanúsítványprofilt felhasználócsoporthoz és ne eszközcsoporthoz rendelje hozzá. Ha eszközcsoporthoz rendel hozzá, akkor teljes eszközregisztráció szükséges, mielőtt az eszköz megkaphatná a szabályzatokat.
- Jóllehet az egyes profilokat külön-külön rendeli hozzá, a legfelső szintű hitelesítésszolgáltató és az SCEP- vagy PKCS-profil hozzárendelésére is szükség van. Ellenkező esetben az SCEP- vagy PKCS-tanúsítványszabályzat hibát fog jelezni.

Az profilok hozzárendeléséről az [Eszközprofilok hozzárendelése](device-profile-assign.md) című cikk nyújt tájékoztatást.

