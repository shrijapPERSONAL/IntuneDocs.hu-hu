---
title: "Tanúsítványok konfigurálása az Intune-nal | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk bemutatja, hogyan lehet az Intune segítségével olyan tanúsítványokat létrehozni és kiosztani, amelyek segítenek a Wi-Fi-, VPN- és egyéb kapcsolatok védelmében."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: a0183f2a170ed458b19c7688b20ee5ba5c2c696e


---

# <a name="how-to-configure-certificates-with-intune-azure-preview"></a>Tanúsítványok konfigurálása az Azure-os Intune előzetes verziójával

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Amikor a felhasználóknak engedélyezi a vállalati erőforrások VPN-, Wi-Fi- vagy e-mail-profilokon keresztüli elérését, a hozzáférés biztonságosságáról az egyes felhasználói eszközökre telepített tanúsítványokkal gondoskodhat. A munkafolyamat fő lépései a következők:

1. Ha még nem működik a megfelelő tanúsítványinfrastruktúra, helyezze üzembe. [SCEP-tanúsítványokat](configure-certificate-infrastructure-for-scep.md) és [PKCS-tanúsítványokat](configure-certificate-infrastructure-for-pfx.md) használhat.
2. Telepítsen egy főtanúsítványt vagy köztes hitelesítésszolgáltatói tanúsítványt minden eszközön, hogy az eszköz felismerje a hitelesítésszolgáltató (CA) érvényességét. Ehhez hozzon létre és rendeljen hozzá egy **megbízható tanúsítványprofilt**. A profil hozzárendelésekor az Intune-nal felügyelt eszközök lekérik és megkapják a főtanúsítványt. Mindegyik platformhoz különálló profilt kell létrehoznia. A megbízható tanúsítványprofilok a következő platformokhoz érhetők el:
    - iOS 8.0 és újabb verziók
    - macOS 10.9 és újabb verziók
    - Android 4.0 és újabb verziók <!--Android for Work --->
    - Windows 8.1 és újabb
    - Windows Phone 8.1 és újabb verziók
    - Windows 10 és újabb
3. Hozza létre a VPN-, Wi-Fi- és e-mail-hozzáférés hitelesítésére szolgáló tanúsítványprofilokat. A következő platformú eszközökre **PKCS-** vagy **SCEP**-tanúsítványprofilt telepíthet:
    - iOS 8.0 és újabb verziók
    - Android 4.0 és újabb verziók
    - Android for Work
    - Windows 10 (asztali és mobilverzió), illetve újabb

    A következő platformok esetében csak SCEP-tanúsítványprofil használható:

-   macOS 10.9 és újabb verziók
-   Windows Phone 8.1 és újabb verziók

Mindegyik eszközplatformhoz külön profilt kell létrehoznia. Létrehozásakor társítsa a profilt a már létrehozott megbízható főtanúsítvány-profilhoz.

### <a name="further-considerations"></a>További szempontok

- Ha nem rendelkezik vállalati hitelesítésszolgáltatóval, létre kell hoznia egyet.
- Ha az eszközplatformjai alapján úgy dönt, hogy SCEP-profilt használ, egy NDES-kiszolgálót is konfigurálnia kell.
- Mind az SCEP-, mind a PKCS-profilok használatához le kell töltenie és konfigurálnia kell a Microsoft Intune Tanúsítvány-összekötőt.

## <a name="before-you-start"></a>Előkészületek


### <a name="if-you-want-to-use-scep-certificates"></a>Ha SCEP-tanúsítványokat szeretne használni

Gondoskodjon az [SCEP-tanúsítványinfrastruktúra konfigurálása](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep) című részben ismertetett előfeltételek meglétéről.

### <a name="if-you-want-to-use-pkcs-certificates"></a>Ha PKCS-tanúsítványokat szeretne használni

Gondoskodjon a [PKCS-tanúsítványinfrastruktúra konfigurálását](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx) bemutató részben ismertetett előfeltételek meglétéről.

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>1. feladat: A megbízható legfelső szintű hitelesítésszolgáltató tanúsítványának exportálása
Exportálja a megbízható legfelső szintű hitelesítésszolgáltató (CA) tanúsítványát **.cer** kiterjesztésű fájlként a kibocsátó hitelesítésszolgáltatóról vagy a vállalati hitelesítésszolgáltatóban megbízó bármelyik eszközről. A titkos kulcsot ne exportálja.

Ezt a tanúsítványt a megbízható tanúsítványprofil konfigurálásakor kell importálnia.

## <a name="task-2-create-trusted-certificate-profiles"></a>2. feladat: Megbízható tanúsítványprofilok létrehozása
Ahhoz, hogy SCEP- vagy PKCS-tanúsítványprofilt hozhasson létre, először létre kell hoznia egy megbízható tanúsítványprofilt. Minden mobileszközplatformhoz külön megbízható tanúsítványprofil, illetve és SCEP- vagy PKCS-profil szükséges.

### <a name="to-create-a-trusted-certificate-profile"></a>Megbízható tanúsítványprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen adja meg az megbízható tanúsítványprofil nevét és leírását a **Név** és a **Leírás** mezőben.
5. Válassza ki a megbízható tanúsítvány eszközplatformját a **Platform** legördülő listából. Jelenleg az alábbi platformokra vonatkozóan lehet eszközkorlátozási beállításokat megadni:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 és újabb**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza a **Megbízható tanúsítvány** lehetőséget.
7. Tallózással keresse meg az 1. feladatban mentett tanúsítványt, majd kattintson az **OK** gombra.
8. Válassza ki – csak a Windows 8.1- és Windows 10-eszközök esetében – a megbízható tanúsítvány céltárolóját a **Céltároló** mezőben, a következő lehetőségek közül:
    - **Számítógép tanúsítványtárolója – fő**
    - **Számítógép tanúsítványtárolója – köztes**
    - **Felhasználói tanúsítványtároló – köztes**
8. Ha elkészült, válassza az **OK** gombot, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** gombot.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha folytatni szeretné az eszközprofil csoportokhoz való hozzárendelésével, erről az [eszközprofilok hozzárendelését](how-to-assign-device-profiles.md) ismertető cikk nyújt tájékoztatást.


> [!Note]
> Az androidos eszközök megjelenítenek egy üzenetet arról, hogy egy harmadik fél megbízható tanúsítványt telepített.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>3. feladat: SCEP- vagy PKCS-tanúsítványprofilok létrehozása
Miután létrehozott egy megbízható hitelesítésszolgáltatói tanúsítványprofilt, létre kell hoznia a használni kívánt platformok SCEP- vagy PKCS-tanúsítványprofilját is. Az SCEP-tanúsítványprofil létrehozásakor meg kell adnia egy ugyanarra a platformra vonatkozó megbízható tanúsítványprofilt. Ez a művelet összeköti a két tanúsítványprofilt, de az egyes profilok hozzárendelését külön-külön kell elvégeznie.

### <a name="to-create-an-scep-certificate-profile"></a>SCEP-tanúsítványprofil létrehozása

1. Az Azure Portalon válassza az **Eszközök konfigurálása** elemet.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
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
    - **Tulajdonos alternatív neve** – Határozza meg, hogy az Intune hogyan hozza létre automatikusan a tulajdonos alternatív nevének értékeit a tanúsítványkérelemben. Ha felhasználói tanúsítványtípust választott ki, akkor például az egyszerű felhasználónevet (UPN) is használhatja a tulajdonos alternatív neveként. Ha az ügyféltanúsítványt fogja hitelesítésre használni egy hálózati házirend-kiszolgáló felé, a tulajdonos alternatív neveként az egyszerű felhasználónevet kell beállítania. 
    - **Kulcshasználat** – Adja meg a tanúsítvány kulcshasználati beállításait. Az alábbi lehetőségek közül választhat: 
        - **Kulcstitkosítás**: Csak akkor engedélyezi a kulcscserét, ha a kulcs titkosítva van. 
        - **Digitális aláírás**: Csak akkor engedélyezi a kulcscserét, ha a kulcs védelmét digitális aláírás segíti. 
    - **Kulcsméret (bit)** – Adja meg, hogy hány bitet tartalmazzon a kulcs. 
    - **Kivonatoló algoritmus** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) – Válassza ki a tanúsítvánnyal használni kívánt kivonatoló algoritmust a rendelkezésre álló típusok közül. Válassza a kapcsolódó eszközöknél használható legerősebb biztonsági szintet. 
    - **Főtanúsítvány** – Válasszon ki egy olyan legfelső szintű hitelesítésszolgáltatói tanúsítványprofilt, amelyet korábban konfigurált és hozzárendelt a felhasználóhoz vagy az eszközhöz. Ennek a hitelesítésszolgáltatói tanúsítványnak a legfelső szintű tanúsítványnak kell lennie az adott tanúsítványprofilban konfigurált tanúsítványt kiállító hitelesítésszolgáltatónál. 
    - **Kibővített kulcshasználat** – Válassza a **Hozzáadás** gombot, és vegye fel a kívánt értékeket a tanúsítvány felhasználási céljai közé. A legtöbb esetben a tanúsítványnál szükséges az **Ügyfél-hitelesítés** , hogy a felhasználó vagy az eszköz hitelesíthető legyen egy kiszolgálóval. Szükség szerint azonban tetszőleges más kulcshasználatot is felvehet. 
    - **Regisztrációs beállítások**
        - **Megújítási küszöb (%)** – Adja meg, hogy az eszköz a tanúsítvány élettartamának hány százalékos hátralévő idejénél igényelje a tanúsítvány megújítását.
        - **SCEP-kiszolgálók URL-címe** – Adja meg egy vagy több olyan NDES-kiszolgáló URL-címét, amely SCEP-tanúsítványokat fog kibocsátani. 
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

A profilkonfigurációs oldalon szereplő utasításokat követve végezze el az SCEP-tanúsítványprofil beállítását.
>[!Note]
> Csak iOS-eszközök esetében: Ha egyéni névformátumot kíván megadni, válassza a Tulajdonosnév formátuma legördülő lista Egyéni elemét.
> Az egyéni formátum jelenleg két változót támogat: **Egyszerű név (CN)** és **E-mail (E)**. A változók és a statikus karakterláncok együttes használatával a következőhöz hasonló egyéni tulajdonosnév-formátumot hozhat létre: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Ebben a példában egy olyan egyéni névformátumot hozott létre, amely a CN és az E változón kívül sztringeket használ a szervezeti egység (OU), a szervezet (O), a hely (L), az állam (ST) és az ország (C) értékeként. [Ez a témakör](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) bemutatja a **CertStrToName** függvényt és az általa támogatott sztringeket.


### <a name="to-create-a-pkcs-certificate-profile"></a>PKCS-tanúsítványprofil létrehozása

Az Azure Portalon válassza az **Eszközök konfigurálása** elemet.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
3. A profilok panelen kattintson a **Profil létrehozása** lehetőségre.
4. A **Profil létrehozása** panelen adja meg a PKCS-tanúsítványprofil nevét és leírását a **Név** és a **Leírás** mezőben.
5. Válassza ki a PKCS-tanúsítvány eszközplatformját a **Platform** legördülő lista következő elemei közül:
    - **Android**
    - **iOS**
    - **Windows 10 és újabb**
6. A **Profil típusa** legördülő listában válassza a **PKCS-tanúsítvány** lehetőséget.
7. A **PKCS-tanúsítvány** panelen konfigurálja a következő beállításokat:
    - **Megújítási küszöb (%)** – Adja meg, hogy az eszköz a tanúsítvány élettartamának hány százalékos hátralévő idejénél igényelje a tanúsítvány megújítását.
    - **Tanúsítvány érvényességi időtartama** – Ha a kiállító hitelesítésszolgáltatón a **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** parancs futtatásával engedélyezte az egyéni érvényességi időtartamot, akkor meghatározhatja a tanúsítvány lejáratáig hátralévő időt.<br>A megadott tanúsítványsablonban meghatározott érvényességi időszaknál rövidebb értéket is beállíthat, hosszabbat azonban nem. Ha például a tanúsítványsablonban két év van meghatározva a tanúsítvány érvényességi idejeként, akkor egy évet beállíthat értékként, öt évet azonban nem. Az értéknek emellett a kiállító hitelesítésszolgáltató tanúsítványának hátralévő érvényességi időszakánál is kevesebbnek kell lennie.
    - **Kulcstároló-szolgáltató** (Windows 10) –
    - **Hitelesítésszolgáltató** -
    - **Hitelesítésszolgáltató neve** -
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
    - **Főtanúsítvány** (Android) – Válasszon ki egy olyan legfelső szintű hitelesítésszolgáltatói tanúsítványprofilt, amelyet korábban konfigurált és hozzárendelt a felhasználóhoz vagy az eszközhöz. Ennek a hitelesítésszolgáltatói tanúsítványnak a legfelső szintű tanúsítványnak kell lennie az adott tanúsítványprofilban konfigurált tanúsítványt kiállító hitelesítésszolgáltatónál.
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.

## <a name="task-4-assign-certificate-profiles"></a>4. feladat: Tanúsítványprofilok hozzárendelése

Mielőtt csoportokhoz rendeli a tanúsítványprofilokat, vegye figyelembe a következőket:

- Amikor csoportokhoz rendeli a tanúsítványprofilokat, a megbízható hitelesítésszolgáltatói tanúsítványprofilból származó tanúsítványfájl települ az eszközre. Az eszköz az SCEP- vagy a PKCS-tanúsítványprofilt használja tanúsítványkérelem létrehozására.
- A tanúsítványprofilok csak a profil létrehozásakor használt platformot futtató eszközökre települnek.
- Tanúsítványprofilokat telepíthet felhasználógyűjteményekre és eszközgyűjteményekre is.
- Ahhoz, hogy a tanúsítványok gyorsan megjelenjenek az eszközökön azok regisztrálását követően, a tanúsítványprofilt felhasználócsoportra és ne eszközcsoportra telepítse. Ha eszközcsoportra telepít, akkor teljes eszközregisztráció szükséges, mielőtt az eszköz megkaphatná a házirendeket.
- Jóllehet az egyes profilokat külön-külön telepíti, a legfelső szintű hitelesítésszolgáltató és az SCEP- vagy PKCS-profil telepítésére is szükség van. Ellenkező esetben az SCEP- vagy PKCS-tanúsítványszabályzat hibát fog jelezni.

## <a name="next-steps"></a>További lépések
Az eszközprofilok hozzárendeléséről az [eszközprofilok hozzárendelését](how-to-assign-device-profiles.md) ismertető cikk nyújt általános tájékoztatást.



<!--HONumber=Feb17_HO1-->


