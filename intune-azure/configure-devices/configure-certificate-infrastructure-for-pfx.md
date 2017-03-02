---
title: "Az Intune tanúsítvány-infrastruktúrájának konfigurálása a PKCS használatára | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk bemutatja, hogyan konfigurálhatja infrastruktúráját arra, hogy PKCS-tanúsítványokat használjon az Intune-nal."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 6f08dc63a9afaa5e92b188883d160d0b76f3631f
ms.lasthandoff: 02/16/2017



---
# <a name="configure-your-microsoft-intune-certificate-infrastructure-for-pkcs"></a>A Microsoft Intune tanúsítványinfrastruktúrájának konfigurálása a PKCS használatára
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ez a témakör a PKCS-tanúsítványprofiloknak az Intune-nal való létrehozásával és telepítésével kapcsolatos tudnivalókat ismerteti.

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
|**Megbízható legfelső szintű hitelesítésszolgáltató tanúsítványa**|Ezt a tanúsítványt **.cer** fájlként kell exportálnia a vállalati hitelesítésszolgáltatótól vagy bármely olyan eszközről, amely megbízik a vállalati hitelesítésszolgáltatóban, majd központilag telepítenie kell az eszközökre a megbízható hitelesítésszolgáltatói tanúsítványprofillal.<br /><br />Operációsrendszer-platformonként egy darab megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványt használjon, és társítsa azt az egyes létrehozott megbízható főtanúsítvány-profilokkal.<br /><br />Szükség esetén további megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványokat is használhat. Ezzel például bizalmi kapcsolatot alakíthat ki egy hitelesítésszolgáltatónak, mely aláírja a kiszolgálói hitelesítési tanúsítványokat a szervezet Wi-Fi hozzáférési pontjai számára.|


## <a name="configure-your-infrastructure"></a>Az infrastruktúra konfigurálása
A tanúsítványprofilok konfigurálása előtt végre kell hajtania a következő feladatokat. E feladatokhoz szükség van a Windows Server 2012 R2 és az Active Directory tanúsítványszolgáltatások (ADCS) ismeretére:

- **1. feladat** – Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál.
- **2. feladat** – Az Intune Certificate Connector engedélyezése, telepítése és konfigurálása.

## <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a>1. feladat – Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál
Ebben a feladatban teszi közzé a tanúsítványsablont.

### <a name="to-configure-the-certification-authority"></a>A hitelesítésszolgáltató konfigurálásához

1.  Hozzon létre egy új egyéni sablont a vállalati hitelesítésszolgáltatón a Tanúsítványsablonok beépülő modullal, vagy másoljon és szerkesszen egy meglévő sablont (például a Felhasználó sablont) a PKCS szolgáltatással való használatra.

    A sablonnak legalább az alábbiakat kell tartalmaznia:

    -   Adjon meg egy leíró nevet a sablonnak a **Sablon megjelenítendő neve** mezőben.

    -   A **Tulajdonos neve** lapon válassza **A kérelem fogja tartalmazni**lehetőséget. (A biztonságot az Intune NDES-házirendmodulja fogja érvényesíteni.)

    -   A **Kiterjesztések** lapon győződjön meg róla, hogy az **Alkalmazás-házirendek leírása** lista tartalmazza az **Ügyfél-hitelesítés**elemet.

        > [!IMPORTANT]
        > iOS- és Mac OS X-tanúsítványsablonok esetében a **Kiterjesztések** lapon szerkessze a **Kulcshasználat** beállítást, és győződjön meg arról, hogy **Az aláírás igazolja az eredetet** lehetőség nincs kiválasztva.

2.  Ellenőrizze az **Érvényesség időtartama** beállítást a sablon **Általános** lapján. Alapértelmezés szerint az Intune a sablonban konfigurált értéket használja. Lehetősége van azonban arra is, hogy a hitelesítésszolgáltató konfigurálásával engedélyezze a kérelmezőnek egy másik érték megadását, amelyet aztán az Intune felügyeleti konzoljából tud megadni. Ha azt szeretné, hogy mindig a sablonban lévő érték legyen használva, hagyja ki ennek a lépésnek a hátralévő részét.

    > [!IMPORTANT]
    > Az iOS és a Mac OS X platform mindig a sablonban beállított értéket használja, minden más konfigurációs beállítástól függetlenül.

    Ha a hitelesítésszolgáltató konfigurálásával lehetővé kívánja tenni a kérelmezőnek az érvényességi időszak megadását, futtassa az alábbi parancsokat a hitelesítésszolgáltatón:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Tegye közzé a Hitelesítésszolgáltató beépülő modullal a tanúsítványsablont a vállalati hitelesítésszolgáltatón.

    a.  Válassza a **Tanúsítványsablonok** csomópontot, kattintson a **Művelet**-&gt; **Új** &gt;**Kiállítandó tanúsítványsablon** lehetőségre, majd válassza ki a 2. lépésben létrehozott sablont.

    b.  Ellenőrizze a **Tanúsítványsablonok** mappában, hogy a sablon közzététele sikerült-e.

4.  A hitelesítésszolgáltató számítógépen győződjön meg róla, hogy az Intune Tanúsítvány-összekötőt futtató számítógépnek van regisztrálási engedélye, és így hozzáférhet a PKCS-tanúsítványprofil létrehozásakor használt sablonhoz. Állítsa be az engedélyt a hitelesítésszolgáltató számítógép tulajdonságainak **Biztonság** lapján.

## <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a>2. feladat – Az Intune tanúsítvány-összekötő engedélyezése, telepítése és konfigurálása
A feladat tartalma:

A tanúsítvány-összekötő letöltése, telepítése és konfigurálása.

### <a name="to-enable-support-for-the-certificate-connector"></a>A tanúsítvány-összekötő támogatásának engedélyezéséhez

1.  Jelentkezzen be az Azure Portal webhelyre.
2.  Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3.  Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2.  Válassza az **Eszközök konfigurálása** panel **Beállítás** > **Hitelesítésszolgáltató** elemét.
2.  A **1. lépésnél** válassza az **Engedélyezés** lehetőséget.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>A tanúsítvány-összekötő letöltéséhez, telepítéséhez és konfigurálása

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

### <a name="next-steps"></a>További lépések
Ezzel készen áll a tanúsítványprofilok létrehozására. Arról a [tanúsítványoknak a Microsoft Intune-nal történő konfigurálását ismertető cikk](how-to-configure-certificates.md) nyújt tájékoztatást.

