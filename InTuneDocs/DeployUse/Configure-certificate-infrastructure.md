---
# required metadata

title: Tanúsítványinfrastruktúra konfigurálása | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a435650-3891-4754-8abc-4bbac244f33b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Tanúsítványinfrastruktúra konfigurálása
Ez a témakör a tanúsítványprofilok létrehozásával és telepítésével kapcsolatos tudnivalókat ismerteti.

Ha bármilyen tanúsítványalapú hitelesítést szeretne végrehajtani a szervezetben, szüksége lesz egy vállalati hitelesítésszolgáltatóra.

Az SCEP-tanúsítványprofilok használatához a vállalati hitelesítésszolgáltatón kívül a következőkre is szüksége lesz:

-   Hálózati eszközök tanúsítványigénylési szolgáltatását futtató kiszolgáló

-   Az NDES-t futtató Windows Server 2012 R2 kiszolgálóra települő Intune Certificate Connector

A PFX-tanúsítványprofilok használatához a vállalati hitelesítésszolgáltatón kívül a következőkre is szüksége lesz:

-  Egy olyan számítógép, amely képes kommunikálni a hitelesítésszolgáltatóval, vagy képes magát a hitelesítésszolgáltató számítógépet használni.

-  A hitelesítésszolgáltatóval kommunikálni képes számítógépen futó Intune Certificate Connector.

## Helyszíni infrastruktúra


-    **Active Directory-tartomány**: A jelen szakaszban felsorolt összes kiszolgálónak (a webalkalmazás-proxykiszolgáló kivételével) csatlakoznia kell a szervezet Active Directory-tartományához.

-  **Hitelesítésszolgáltató** (CA): Olyan vállalati hitelesítésszolgáltató (CA), amely a Windows Server 2008 R2 vagy újabb rendszer vállalati verzióján fut. Az önálló hitelesítésszolgáltató nem támogatott. A hitelesítésszolgáltató konfigurálásáról lásd: [Hitelesítésszolgáltató telepítése](http://technet.microsoft.com/library/jj125375.aspx).
    Ha a hitelesítésszolgáltatója Windows Server 2008 R2 rendszeren fut, [telepítenie kell a KB2483564 jelű gyorsjavítást](http://support.microsoft.com/kb/2483564/).

-  **NDES-kiszolgáló** (csak SCEP esetén): A Windows Server 2012 R2 vagy újabb rendszeren futó kiszolgálón telepítenie kell a hálózati eszközök tanúsítványigénylési szolgáltatását (NDES). Az Intune nem támogatja az NDES használatát, ha az olyan kiszolgálón fut, amely vállalati hitelesítésszolgáltatót is futtat. Az [Útmutató a hálózati eszközök tanúsítványigénylési szolgáltatásához](http://technet.microsoft.com/library/hh831498.aspx) című cikkben tájékozódhat arról, hogyan kell konfigurálnia a Windows Server 2012 R2 rendszert az NDES futtatására.
-  **Egy olyan számítógép, amely képes kommunikálni a hitelesítésszolgáltatóval** (csak PFX esetén): Másik megoldásként használhatja magát a hitelesítésszolgáltató számítógépet is.
-  **Microsoft Intune Certificate Connector**: Az Intune felügyeleti konzollal töltse le a **Certificate Connector** (Tanúsítvány-összekötő) telepítőjét (**ndesconnectorssetup.exe**). Ezután futtassa az **ndesconnectorssetup.exe** fájlt azon a számítógépen, amelyre telepíteni szeretné az tanúsítvány-összekötőt. A . PFX-tanúsítványprofilok esetében a hitelesítésszolgáltatóval kommunikáló számítógépre telepítse a tanúsítvány-összekötőt.
-  **Webalkalmazás-proxykiszolgáló** (nem kötelező): Webalkalmazás-proxykiszolgálóként (WAP) használhat olyan kiszolgálót, amelyen a Windows Server 2012 R2 vagy újabb verziójú rendszer fut. Ez a konfiguráció:
    -  Lehetővé teszi, hogy az eszközök az interneten keresztül fogadjanak tanúsítványokat.
    -  Biztonsági ajánlás olyan környezetekben, ahol az eszközök az interneten keresztül csatlakozva kapnak és újítanak meg tanúsítványokat.

> [!NOTE]           
> -    A WAP-ot futtató kiszolgálón [telepíteni kell egy frissítést](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) ahhoz, hogy az támogassa az NDES által használt hosszú URL-eket. Ez a frissítés megtalálható a [2014. decemberi kumulatív frissítésben](http://support.microsoft.com/kb/3013769), illetve önállóan a [KB3011135-as jelű frissítésként](http://support.microsoft.com/kb/3011135).
>-  Ezenkívül a WAP-ot futtató kiszolgálónak rendelkeznie kell egy SSL-tanúsítvánnyal, amely a külső ügyfeleknek közzétett nevet egyezteti, valamint meg kell bíznia az NDES-kiszolgálón használt SSL-tanúsítványban. E tanúsítványok segítségével a WAP-kiszolgáló képes megszakítani az ügyfelek SSL-kapcsolatát, illetve új SSL-kapcsolatot létrehozni az NDES-kiszolgálóval.
A WAP-hoz szükséges tanúsítványokkal kapcsolatos további tudnivalókért olvassa el a **Tanúsítványok megtervezése** című szakaszt a [Felkészülés az alkalmazások webalkalmazás-proxyval való közzétételére](https://technet.microsoft.com/library/dn383650.aspx) című cikkben. A WAP-kiszolgálókkal kapcsolatos általános információkért tekintse meg [A webalkalmazás-proxy használata](http://technet.microsoft.com/library/dn584113.aspx) című témakört.


### Tanúsítványok és sablonok

|Objektum|Részletek|
|----------|-----------|
|**Tanúsítványsablon**|Ezt a sablont a vállalati hitelesítésszolgáltatón tudja konfigurálni.|
|**Ügyfél-hitelesítési tanúsítvány**|A vállalati vagy nyilvános hitelesítésszolgáltatótól lekért tanúsítvány, melyet az NDES-kiszolgálóra kell telepítenie.|
|**Kiszolgálói hitelesítési tanúsítvány**|A vállalati vagy nyilvános hitelesítésszolgáltatótól lekért tanúsítvány. Ezt az SSL-tanúsítványt az NDES-kiszolgálón futó IIS-be kell telepítenie, majd kötést kell létrehoznia.|
|**Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványa**|Ezt a tanúsítványt **.cer** fájlként kell exportálnia a vállalati hitelesítésszolgáltatótól vagy bármely olyan eszközről, amely megbízik a vállalati hitelesítésszolgáltatóban, majd központilag telepítenie kell az eszközökre a megbízható hitelesítésszolgáltatói tanúsítványprofillal.<br /><br />Operációsrendszer-platformonként egy darab megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványt használjon, és társítsa azt az egyes létrehozott megbízható főtanúsítvány-profilokkal.<br /><br />Szükség esetén további megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványokat is használhat. Ezzel például bizalmi kapcsolatot alakíthat ki egy hitelesítésszolgáltatónak, mely aláírja a kiszolgálói hitelesítési tanúsítványokat a szervezet Wi-Fi hozzáférési pontjai számára.|

### Fiókok

|Név|Részletek|
|--------|-----------|
|**NDES szolgáltatásfiók**|Meg kell adnia egy tartományfelhasználói fiókot NDES szolgáltatásfiókként.|

## Az infrastruktúra konfigurálása
A tanúsítványprofilok konfigurálása előtt végre kell hajtania az alábbi feladatokat, melyekhez a Windows Server 2012 R2 rendszerhez és az Active Directory tanúsítványszolgáltatásokhoz (ADCS) kapcsolódó ismeretek szükségesek:

**1. feladat** – Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatón

**2. feladat**, csak SCEP-profilok esetén – Előfeltételek konfigurálása az NDES-kiszolgálón

**3. feladat**, csak SCEP-profilok esetén – NDES konfigurálása az Intune-nal való használatra

**4. feladat** – Az Intune Certificate Connector engedélyezése, telepítése és konfigurálása

## 1. feladat – Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál
A feladat tartalma:

-   NDES szolgáltatásfiók létrehozása

    > [!NOTE] A tanúsítványok visszavonásához az NDES szolgáltatásfiók a *Tanúsítványok kiállítása és kezelése* nevű jogosultságot igényli a tanúsítványprofilok által használt összes tanúsítványprofilhoz.

-   Tanúsítványsablon konfigurálása az NDES számára

-   Tanúsítványsablon közzététele az NDES számára

##### A hitelesítésszolgáltató konfigurálásához

1.  Hozzon létre egy tartományfelhasználói fiókot, melyet NDES szolgáltatásfiókként fog használni. Ezt a fiókot kell megadnia a sablonok vállalati hitelesítésszolgáltatónál való konfigurálásakor, még mielőtt telepítené és konfigurálná az NDES-t.

2.  A vállalati hitelesítésszolgáltatónál a Tanúsítványsablonok beépülő modullal hozzon létre egy új egyéni sablont (vagy másoljon és szerkesszen egy meglévő sablont, például a Felhasználó sablont) az NDES szolgáltatással való használatra.

    A sablonnak az alábbi beállításokkal kell rendelkeznie:

    -   Adjon meg egy leíró nevet a sablonnak a **Sablon megjelenítendő neve** mezőben.

    -   A **Tulajdonos neve** lapon válassza **A kérelem fogja tartalmazni**lehetőséget. (A biztonságot az Intune NDES-házirendmodulja fogja érvényesíteni.)

    -   A **Kiterjesztések** lapon győződjön meg róla, hogy az **Alkalmazás-házirendek leírása** lista tartalmazza az **Ügyfél-hitelesítés**elemet.

        > [!IMPORTANT] iOS- és Mac OS X-tanúsítványsablonok esetében a **Kiterjesztések** lapon szerkessze a **Kulcshasználat** beállítást, és ellenőrizze, hogy **Az aláírás az eredet igazolása** lehetőség nincs-e kiválasztva.

    -   A **Biztonság** lapon adja hozzá az NDES szolgáltatásfiókot, és adjon meg hozzá **Regisztrálás** engedélyt a sablonhoz.

3.  Ellenőrizze az **Érvényesség időtartama** beállítást a sablon **Általános** lapján. Alapértelmezés szerint az Intune a sablonban konfigurált értéket használja. Lehetősége van azonban arra is, hogy a hitelesítésszolgáltató konfigurálásával engedélyezze a kérelmezőnek egy másik érték megadását, amelyet aztán az Intune felügyeleti konzoljából tud megadni. Ha azt szeretné, hogy mindig a sablonban lévő érték legyen használva, hagyja ki ennek a lépésnek a hátralévő részét.

    > [!IMPORTANT] Az iOS és a Mac OS X platform mindig a sablonban beállított értéket használja, minden más konfigurációs beállítástól függetlenül.

    Ha a hitelesítésszolgáltató konfigurálásával lehetővé kívánja tenni a kérelmezőnek az érvényességi időszak megadását, futtassa az alábbi parancsokat a hitelesítésszolgáltatón:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Tegye közzé a Hitelesítésszolgáltató beépülő modullal a tanúsítványsablont a vállalati hitelesítésszolgáltatón.

    1.  Válassza a **Tanúsítványsablonok** csomópontot, kattintson a **Művelet**-&gt; **Új** &gt; **Kiállítandó tanúsítványsablon** lehetőségre, majd válassza ki a 2. lépésben létrehozott sablont.

    2.  Ellenőrizze a **Tanúsítványsablonok** mappában, hogy a sablon közzététele sikerült-e.

5.  .PFX-profilok esetében: a hitelesítésszolgáltató számítógépen győződjön meg arról, hogy az Intune Certificate Connector gazdagépe rendelkezik regisztrálási engedéllyel, így hozzáférhet a .PFX-profil létrehozásakor használt sablonhoz. Állítsa be az engedélyt a hitelesítésszolgáltató számítógép tulajdonságainak **Biztonság** lapján.

## 2. feladat (csak SCEP-profilok esetén) – Előfeltételek konfigurálása az NDES-kiszolgálón
A feladat tartalma:

-   Az NDES hozzáadása egy Windows Server-kiszolgálóhoz, és az IIS konfigurálása az NDES támogatására

-   Az NDES szolgáltatásfiók hozzáadása a IIS_IUSR csoporthoz

-   Az NDES szolgáltatásfiók egyszerű szolgáltatásnevének beállítása

##### Az előfeltételek NDES-kiszolgálón való konfigurálásához

1.  Jelentkezzen be az NDES szolgáltatásnak helyt adó kiszolgálón **Vállalati rendszergazdaként**, és telepítse az NDES-t a [Szerepkörök és szolgáltatások hozzáadása varázslóval](https://technet.microsoft.com/library/hh831809.aspx) :

    1.  A varázslóban válassza az **Active Directory tanúsítványszolgáltatások** lehetőséget az AD CS szerepkör-szolgáltatások eléréséhez. Válassza a **Hálózati eszközök tanúsítványigénylési szolgáltatása**lehetőséget, törölje a jelet a **Hitelesítésszolgáltató**jelölőnégyzetből, és fejezze be a varázslót.

        > [!TIP]
        > A varázsló **Telepítési folyamat** lapján ne kattintson a **Bezárás**gombra. Ehelyett kattintson **Az Active Directory tanúsítványszolgáltatások beállítása a célkiszolgálón**hivatkozásra. Ekkor megnyílik **Az Active Directory tanúsítványszolgáltatások beállítása** varázsló, amelyet a következő feladathoz kell használnia. Ha megnyílt Az Active Directory tanúsítványszolgáltatások beállítása varázsló, bezárhatja a Szerepkörök és szolgáltatások hozzáadása varázslót.

    2.  Az NDES kiszolgálóhoz való hozzáadásakor a varázsló az IIS-t is telepíti. Az IIS-nek az alábbi konfigurációval kell rendelkeznie:

        -   **Webkiszolgáló** &gt; **Biztonság** &gt; **Kérelemszűrés**

        -   **Webkiszolgáló** &gt; **Alkalmazásfejlesztés** &gt; **ASP.NET 3.5**. Az ASP.NET 3.5 telepítése telepíti a .NET-keretrendszer 3.5-öt is. A .NET-keretrendszer 3.5 telepítésekor a **.NET-keretrendszer 3.5** alapszolgáltatásai mellett telepítse a **HTTP-aktiválás**szolgáltatást is.

        -   **Webkiszolgáló** &gt; **Alkalmazásfejlesztés** &gt; **ASP.NET 4.5**. Az ASP.NET 4.5 telepítése a .NET-keretrendszer 4.5-ös verzióját is telepíti. A .NET-keretrendszer 4.5 telepítésekor a **.NET-keretrendszer 4.5** alapszolgáltatásai mellett telepítse az **ASP.NET 4.5** és a **WCF-szolgáltatások** &gt; **HTTP-aktiválás** szolgáltatást is.

        -   **Felügyeleti eszközök** &gt; **Kompatibilitás az IIS 6 kezelésével** &gt; **Kompatibilitás az IIS 6 metabázisával**

        -   **Felügyeleti eszközök** &gt; **Kompatibilitás az IIS 6 kezelésével** &gt; **Kompatibilitás az IIS 6 WMI-vel**

2.  Vegye fel a kiszolgálón az NDES szolgáltatásfiókot az **IIS_IUSR** csoport tagjaként.

3.  Futtassa az alábbi parancsot az NDES szolgáltatásfiók egyszerű szolgáltatásnevének beállításához:

    -   **setspn -s http/&lt;NDES-kiszolgáló DNS-neve&gt; &lt;Tartománynév&gt;\&lt;NDES-szolgáltatásfiók neve&gt;**

    Ha például az NDES kiszolgáló neve **Kiszolgalo01**, a tartomány **Contoso.com**és a szolgáltatásfiók **NDESSzolgaltatas**, akkor az alábbi parancsot kell használnia:

    -   **setspn –s http/Kiszolgalo01.contoso.com contoso\NDESSzolgaltatas**

## 3. feladat (csak SCEP-profilok esetén) – NDES konfigurálása a Microsoft Intune-nal való használatra 
A feladat tartalma:

-   Az NDES konfigurálása a vállalati hitelesítésszolgáltatóval való használatra

-   SSL-tanúsítvány kötésének létrehozása az IIS-ben

-   Kérelemszűrés konfigurálása az IIS-ben

##### Az NDES Intune-nal való használatának konfigurálásához

1.  Nyissa meg az NDES-kiszolgálón Az Active Directory tanúsítványszolgáltatások beállítása varázslót, és végezze el az alábbi konfigurációs lépéseket.

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

3.  A beállításjegyzék módosítása után futtassa az **iisreset** parancsot a konfigurációs módosítások kiszolgálón való életbe léptetéséhez.

##### A tanúsítványok NDES-kiszolgálón való telepítéséhez és kötéséhez

1.  Kérelmezzen a belső vagy a nyilvános hitelesítésszolgáltatótól egy **kiszolgálóhitelesítő** tanúsítványt, és telepítse az NDES-kiszolgálón. Ezután létre kell hoznia az SSL-tanúsítvány kötését az IIS-ben.

    > [!TIP]
    > Miután létrehozta az SSL-tanúsítvány kötését az IIS-ben, telepítenie kell egy ügyfél-hitelesítési tanúsítványt. Ezt a tanúsítványt bármely olyan hitelesítésszolgáltató kibocsáthatja, amelyben az NDES-kiszolgáló megbízik. Bár ez nem ajánlott eljárás, használhatja ugyanazt a tanúsítványt a kiszolgáló és az ügyfél hitelesítéséhez mindaddig, amíg a tanúsítvány mindkét kibővített kulcshasználattal rendelkezik. Ezekről a hitelesítési tanúsítványokról az alábbi lépésekből kaphat további információt.

    1.  Miután beszerezte a kiszolgálóhitelesítő tanúsítványt, nyissa meg az **IIS-kezelőt**, válassza az **Alapértelmezett webhely** lehetőséget a **Kapcsolatok** ablaktáblán, majd kattintson a **Kötések** lehetőségre a **Műveletek** ablaktáblán.

    2.  Kattintson a **Hozzáadás**lehetőségre, adja meg a **Típus** beállításnál a **https**értéket, és győződjön meg róla, hogy a port **443-ra**van állítva. (Az önálló Intune csak a 443-as portot támogatja.)

    3.  Az **SSL-tanúsítvány**beállításnál adja meg a kiszolgálóhitelesítő tanúsítványt.

        > [!NOTE] Ha az NDES-kiszolgáló külső és belső nevet is használ egyetlen hálózati címhez, akkor a kiszolgálóhitelesítő tanúsítvány **Tulajdonos neve** beállításának egy külső nyilvános kiszolgálónevet, a **Tulajdonos alternatív neve** beállításának pedig egy belső kiszolgálónevet kell tartalmaznia.

2.  Kérelmezzen a belső vagy a nyilvános hitelesítésszolgáltatótól egy **ügyfél-hitelesítő** tanúsítványt, és telepítse az NDES-kiszolgálón. Ez lehet ugyanaz, mint a kiszolgálóhitelesítő tanúsítvány, ha a tanúsítvány mindkét használati módra fel van készítve.

    Az ügyfél-hitelesítő tanúsítványnak az alábbi tulajdonságokkal kell rendelkeznie:

    **Kibővített kulcshasználat** – Tartalmaznia kell az **Ügyfél-hitelesítés** szolgáltatást.

    **Tulajdonos neve** – Meg kell egyeznie annak a kiszolgálónak a DNS-nevével, amelyen a tanúsítványt telepítette (ez az NDES-kiszolgáló).

##### A kérelmek szűrésének IIS-ben való konfigurálásához

1.  Nyissa meg az NDES-kiszolgálón az **IIS-kezelőt**, válassza az **Alapértelmezett webhely** lehetőséget a **Kapcsolatok** ablaktáblán, és nyissa meg a **Kérelmek szűrése**beállítást.

2.  Kattintson a **Szolgáltatás beállításainak szerkesztése**lehetőségre, és adja meg a következőket:

    **lekérdezés-karakterlánc hossza (bájt)** = **65534**

    **URL-cím maximális hossza (bájt)** = **65534**

3.  Tekintse át a következő beállításkulcsot:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Az alábbi értékeknek Duplaszó típusú bejegyzésként kell szerepelnie:

    Név: **MaxFieldLength**, decimális **65534**

    Név: **MaxRequestBytes**, decimális **65534**

4.  Indítsa újra az NDES-kiszolgálót. A kiszolgáló mostantól készen áll az tanúsítvány-összekötő támogatására.

## 4. feladat – Az Intune Certificate Connector engedélyezése, telepítése és konfigurálása – SCEP- és .PFX-tanúsítványok esetén.
A feladat tartalma:

Az NDES támogatásának engedélyezése az Intune-ban

A tanúsítvány-összekötő letöltése, telepítése és konfigurálása az NDES-kiszolgálón

##### A tanúsítvány-összekötő támogatásának engedélyezéséhez

1.  Nyissa meg az [Intune felügyeleti konzolját](https://manage.microsoft.com), és válassza a **Felügyelet** &gt; **Tanúsítvány-összekötő** lehetőséget.

2.  Kattintson a **Helyszíni tanúsítvány-összekötő konfigurálása** elemre.

3.  Válassza az **Enable Certificate Connector**(Certificate Connector engedélyezése) lehetőséget, és kattintson az **OK**gombra.

##### A tanúsítvány-összekötő letöltéséhez, telepítéséhez és konfigurálásához

1.  Nyissa meg az [Intune felügyeleti konzolját](https://manage.microsoft.com), és kattintson a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Tanúsítvány-összekötő** &gt; **Tanúsítvány-összekötő letöltése** lehetőségre.

2.  A letöltés befejezése után futtassa a letöltött telepítőt (**ndesconnectorssetup.exe**):

    -   .PFX-tanúsítványok esetén azon a számítógépen futtassa a telepítőt, amely kapcsolódni tud a hitelesítésszolgáltatóhoz. Válassza a .PFX típusú tanúsítványt terjesztő beállítást, és kattintson a Telepítés elemre. A telepítés befejezése után következő lépésként hozzon létre egy tanúsítványprofilt a [Tanúsítványprofilok konfigurálása](configure-intune-certificate-profiles.md) című témakörben leírtaknak megfelelően.

    -   SCEP-tanúsítványok esetén a telepítőt futtassa egy Windows Server 2012 R2-kiszolgálón

    Az SCEP lehetőségnél a telepítés során az NDES házirendmodulja és a CRP (tanúsítványregisztrációs pont) webszolgáltatás is települ. (A CRP webszolgáltatás, melynek neve CertificateRegistrationSvc, alkalmazásként fut az IIS-ben.)

    > [!NOTE]
    > Ha önálló Intune-hoz telepíti az NDES-t, akkor a CRP szolgáltatás automatikusan települ a tanúsítvány-összekötővel együtt. Az Intune szolgáltatásnak a Configuration Managerrel való használatakor a tanúsítványregisztrációs pontot különálló helyrendszerszerepkörként telepíti.

3.  Ha a rendszer kéri az ügyféltanúsítványt a tanúsítvány-összekötőhöz, válassza a **Kijelölés**lehetőséget, és válassza ki az **ügyfél-hitelesítő** tanúsítványt, amelyet a 3. feladatban telepített az NDES-kiszolgálóra.

    Miután kiválasztotta az ügyfél-hitelesítési tanúsítványt, a rendszer visszairányítja az **Client Certificate for Microsoft Intune Certificate Connector** (Ügyféltanúsítvány a Microsoft Intune Certificate Connectorhoz) felületre. Bár a választott tanúsítvány nem látható, kattintson a **Tovább** gombra a tanúsítvány tulajdonságainak megtekintéséhez. Ezután kattintson ismét a **Tovább**gombra, majd a **Telepítés**gombra.

4.  Ha a varázsló befejeződött, még mielőtt bezárná, kattintson **Launch the Certificate Connector UI**(Certificate Connector felhasználói felületének indítása) lehetőségre.

    > [!TIP] Ha bezárta volna a varázslót a tanúsítvány-összekötő felhasználói felületének megnyitása előtt, az alábbi parancs futtatásával újra megnyithatja:
    >
    > **&lt;telepítési_útvonal&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  A **Certificate Connector** (Tanúsítvány-összekötő) felhasználói felületén:

    Kattintson a **Bejelentkezés** gombra, és írja be az Intune szolgáltatás rendszergazdai hitelesítő adatait, vagy egy bérlői rendszergazda globális felügyeleti engedéllyel rendelkező hitelesítő adatait.

    Ha a szervezet proxykiszolgálót használ, és proxy szükséges ahhoz, hogy az NDES-kiszolgáló el tudja érni az internetet, kattintson a **Proxykiszolgáló használata** lehetőségre, és adja meg a proxykiszolgáló nevét és portját, illetve a csatlakozáshoz szükséges fiókadatokat.

    Váltson a **Speciális** lapra, adja meg egy olyan fiók hitelesítő adatait, amely rendelkezik **Tanúsítványok kiállítása és kezelése** engedéllyel a vállalati hitelesítésszolgáltatónál, majd kattintson az **Alkalmaz**gombra.

    Bezárhatja a tanúsítvány-összekötő felhasználói felületét.

6.  Nyisson meg egy parancssort, írja be a **services.msc** fájlnevet, nyomja le az **Enter** billentyűt, kattintson a jobb gombbal az **	Intune-összekötő szolgáltatás** elemre, és válassza az **Újraindítás** parancsot.

A szolgáltatás futásának ellenőrzéséhez nyisson meg egy böngészőt, és írja be az alábbi URL-t, melynek egy **403-as** hibát kell visszaadnia:

**http:// &lt;NDES-kiszolgáló_teljes_tartományneve&gt;/certsrv/mscep/mscep.dll**

### További lépések
Ezzel készen áll a tanúsítványprofilok konfigurálására, amelyről a következő témakörben olvashat: [Tanúsítványprofilok konfigurálása](configure-intune-certificate-profiles.md).


<!--HONumber=Jun16_HO1-->


