---
title: Android-alkalmazások burkolása az Intune Alkalmazásburkoló eszközzel
description: Megtudhatja, hogyan burkolhatja az Android-alkalmazásait anélkül, hogy módosítaná magának az alkalmazásnak a programkódját. Előkészítheti az alkalmazásokat a mobilalkalmazás-felügyeleti szabályzatok alkalmazására.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/11/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 64de72822ad8d2f8d9893e3428208ff1363d33e2
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566046"
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Android-alkalmazások előkészítése alkalmazásvédelmi szabályzatokkal való felügyeletre az Intune alkalmazásburkoló eszközével

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

A Microsoft Intune App Wrapping Tool for Android alkalmazásburkoló eszközzel módosíthatja a belső fejlesztésű Android-alkalmazások viselkedését, így az alkalmazások kódjának módosítása nélkül korlátozhatja az alkalmazások funkcióit.

Ez az eszköz egy windowsos parancssori alkalmazás, amely PowerShell-ablakban fut, és „beburkolja” az Android-alkalmazást. Az alkalmazás beburkolását követően az Intune-ban [mobilalkalmazás-kezelési szabályzatok](app-protection-policies.md) konfigurálásával módosíthatja az alkalmazás funkcióit.

Az eszköz futtatása előtt olvassa el a következő cikket: [Az alkalmazásburkoló eszköz futtatásához kapcsolódó biztonsági szempontok](#security-considerations-for-running-the-app-wrapping-tool). Az eszköz letöltéséhez keresse fel a [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) oldalát a GitHubon.

## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz használatára vonatkozó előfeltételek teljesítése

-   Az alkalmazásburkoló eszköz futtatásához egy Windows 7 vagy újabb operációs rendszerű Windows-számítógépre van szükség.

-   A bemeneti alkalmazásnak .apk kiterjesztésű érvényes Android-alkalmazáscsomagnak kell lennie, továbbá:

    -   Nem lehet titkosítva.
    -   Nem lehet már beburkolva az Intune App Wrapping Tool segítségével.
    -   Android 4.0-s vagy újabb operációs rendszerre kellett készülnie.

-   Vállalata által kifejlesztett vagy vállalata számára készült alkalmazásnak kell lennie. Az eszköz nem használható a Google Play áruházból letöltött alkalmazásokkal.

-   Az alkalmazásburkoló eszköz futtatásához telepítenie kell a [Java Runtime Environment](https://java.com/download/) legújabb verzióját, majd meg kell bizonyosodnia arról, hogy a Windows környezeti változók között a Java elérési útvonalának a következő van megadva: C:\ProgramData\Oracle\Java\javapath. További segítségért tekintse meg a [Java dokumentációt](https://java.com/download/help/).

    > [!NOTE]
    > Egyes esetekben a Java 32 bites verziója memóriaproblémákat okozhat. Tanácsos a 64 bites verziót telepíteni.

- Az Android megköveteli, hogy minden alkalmazáscsomag (.apk) alá legyen írva. Létező tanúsítványok **újbóli használatához** és az aláíró tanúsítványok teljes útmutatójához lásd: [Aláíró tanúsítványok és burkolóalkalmazások újbóli használata](https://docs.microsoft.com/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps). A keytool.exe végrehajtható Java-eszközzel létrehozhatja a kimeneti burkolt alkalmazás aláírásához szükséges **új** hitelesítő adatokat. Minden beállított jelszónak biztonságosnak kell lennie, de jegyezze fel őket, mert szükség van rájuk az alkalmazásburkoló eszköz futtatásához.

    > [!NOTE]
    > Az Intune alkalmazásburkoló eszköz nem támogatja a Google v2 és hamarosan megjelenő v3 alkalmazás-aláíró sémáit. Miután becsomagolta az .apk fájlt az Intune alkalmazásburkoló eszközzel, javasoljuk, hogy használja a [Google által biztosított Apksigner eszközt]( https://developer.android.com/studio/command-line/apksigner). Ezzel biztosíthatja, hogy miután az alkalmazás eljut a végfelhasználói eszközökre, elindítható legyen az Android szabványoknak megfelelően. 

- (Nem kötelező) Alkalmazás néha előfordulhat, hogy eléri a Dalvik Executable (DEX) méretkorlátját a burkolás során hozzáadott Intune MAM SDK osztályok miatt. A DEX-fájlok az Android-alkalmazások fordításának részei. Az Intune App Wrapping Tool DEX fájl túlcsordulás automatikusan kezeli az alkalmazások minimális API-val 21-ből vagy magasabb szintű alkalmazásburkoló során (a [v. 1.0.2501.1](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android/releases)). Legalább < 21 szintű API-alkalmazások esetén célszerű lenne, a minimális API-szintet a burkoló használatával növelheti `-UseMinAPILevelForNativeMultiDex` jelzőt. Az ügyfelek nem lehet növelni az alkalmazás minimális API-szintet a következő DEX túlcsordulás kerülő megoldások érhetők el. Egyes cégeknél előfordulhat, hogy fordítójával lefordítja az alkalmazás használatának (ie. az alkalmazás-összeállító csapattal):
* Használja a ProGuard kiküszöbölése az alkalmazás elsődleges DEX fájlnak fel nem használt osztály hivatkozásokat.
* V3.1.0 használó ügyfelek számára vagy újabb verzióját az Android Gradle beépülő modul, tiltsa le a [D8 dexer](https://android-developers.googleblog.com/2018/04/android-studio-switching-to-d8-dexer.html).  

## <a name="install-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz telepítése

1.  A [GitHub-tárházból](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) egy Windows-számítógépre töltse le az Intune App Wrapping Tool for Android InstallAWT.exe teleptőfájlját. Nyissa meg a telepítőfájlt.

2.  Fogadja el a licencszerződést, majd fejezze be a telepítést.

Jegyezze fel a mappa nevét, ahová az eszközt telepítette. Az alapértelmezett hely a következő: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz futtatása

1. Azon a Windows-számítógépen, amelyre az alkalmazásburkoló eszközt telepítette, egy PowerShell-ablak nyílik meg.

2. Az eszköz telepítési mappájából importálja az alkalmazásburkoló eszköz PowerShell-modulját:

   ```PowerShell
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. Az eszközt az **invoke-AppWrappingTool** paranccsal futtathatja, a következő szintaxissal:
   ```PowerShell
   Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
   -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
   ```

   Az alábbi táblázat az **invoke-AppWrappingTool** parancs tulajdonságait ismerteti:

|Tulajdonság|Információ|Példa|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Az Android-forrásalkalmazás (.apk) elérési útja.| |
 |**-OutputPath**&lt;String&gt;|A „kimeneti” Android-alkalmazás elérési útja. Ha ez megegyezik az InputPath értékével, a burkolás sikertelen lesz.| |
|**-KeyStorePath**&lt;String&gt;|Az aláíráshoz használt nyilvános és titkos kulcsból álló kulcspárt tartalmazó kulcstárfájl elérési útja.|A kulcstárfájlok alapértelmezés szerint a „C:\Program Files (x86)\Java\jreX.X.X_XX\bin” könyvtárban találhatók. |
|**-KeyStorePassword**&lt;SecureString&gt;|A kulcstár visszafejtésére szolgáló jelszó. Az Android elvárja, hogy minden alkalmazáscsomag (.apk) alá legyen írva. A Java keytool segítségével hozza létre a KeyStorePassword kulcsot. További információk a Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) osztályról.| |
|**-KeyAlias**&lt;String&gt;|Az aláíráshoz használt kulcs neve.| |
|**-KeyPassword**&lt;SecureString&gt;|Az aláíráshoz használt titkos kulcs visszafejtésére szolgáló jelszó.| |
|**-SigAlg**&lt;SecureString&gt;| (Nem kötelező) Az aláíráshoz használandó aláírási algoritmus neve. Az algoritmusnak kompatibilisnek kell lennie a titkos kulccsal.|Példák: SHA256withRSA, SHA1withRSA|
|**-UseMinAPILevelForNativeMultiDex**| (Nem kötelező) Ez a jelző használatával növelheti a forrás Android alkalmazás minimális API-szintet pedig 21. Ez a jelző megerősítő, előfordulhat, hogy az alkalmazás telepítéséhez, akik fogja korlátozni fogja kérni. Felhasználók a megerősítési párbeszédpanelen hagyja ki a paraméter hozzáfűzésével "-megerősítése: $false", a PowerShell-parancsot. A jelző csak az alkalmazások burkolása sikerült DEX túlcsordulás hibák miatt sikertelen minimális API-t < 21-ügyfelek által használható. | |
| **&lt;CommonParameters&gt;** | (Nem kötelező) A parancs támogatja gyakran használt PowerShell-paramétereket, mint például a verbose, a debug stb. |


- A gyakori paraméterek listáját lásd itt: [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Az eszköz használatáról részletes információt olvashat az alábbi parancs használatával:

    ```PowerShell
    Help Invoke-AppWrappingTool
    ```

**Példa:**

Importálja a PowerShell modult.
```PowerShell
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Futtassa az alkalmazásburkoló eszközt a HelloWorld.apk natív alkalmazáson.
```PowerShell
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Az eszköz kérni fogja következő információkat: **KeyStorePassword** és **KeyPassword**. Adja meg a kulcstárfájlok létrehozásánál használt hitelesítő adatokat.

Az eszköz generálja a beburkolt alkalmazást, és menti a naplófájllal együtt a megadott kimeneti elérési útra.

## <a name="how-often-should-i-rewrap-my-android-application-with-the-intune-app-wrapping-tool"></a>Milyen gyakran érdemes újraburkolni az Android-alkalmazást az Intune alkalmazásburkoló eszközével?
Általában az alábbi esetekben van szükség az alkalmazások újraburkolására:
* Maga az alkalmazás új verzióban jelent meg. Az alkalmazás előző verziója a burkolás után az Intune-konzolba lett feltöltve.
* Az Intune Androidhoz használható alkalmazásburkoló eszközének olyan új verziója jelent meg, amely lehetővé teszi a fontosabb hibajavításokat vagy meghatározott alkalmazásvédelmi szabályzatokkal kapcsolatos Intune-funkciókat. Ilyen új verzió 6-8 hetente jelenik meg, és a [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) GitHub-tárházban érhető el.

Ajánlott eljárások az újraburkoláshoz: 
* A buildelési folyamat során használt aláíró tanúsítványok megtartása – lásd: [Aláíró tanúsítványok és burkolóalkalmazások újbóli használata](https://docs.microsoft.com/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps)

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>Az aláíró tanúsítványok és a burkolóalkalmazások újbóli használata
Az Android minden alkalmazás esetében érvényes tanúsítvánnyal való aláírást követel meg ahhoz, hogy azokat Android-eszközökre lehessen telepíteni.

A beburkolt alkalmazások aláírása elvégezhető a burkolási folyamat részeként, vagy pedig a burkolás *után*, meglévő aláíró eszközökkel (ekkor a rendszer minden, a burkolás előtt az alkalmazásban található aláírási információt elvet). Amennyiben ez lehetséges, az összeállítási folyamatban már felhasznált aláírási információkat kell felhasználni a burkolás során. Egyes szervezetekben elképzelhető, hogy ehhez a kulcstároló tulajdonosával (azaz az alkalmazás-összeállító csapattal) való együttműködés szükséges. 

Ha az előző aláíró tanúsítvány nem használható, vagy ha az alkalmazás korábban még nem lett telepítve, az [Android fejlesztői útmutatójának](https://developer.android.com/studio/publish/app-signing.html#signing-manually) utasításai alapján létrehozhat egy új aláíró tanúsítványt.

Ha az alkalmazás korábban már telepítve lett egy másik aláíró tanúsítvánnyal, az alkalmazást a frissítés után nem lehet feltölteni az Intune-ba. Ha az alkalmazás egy másik tanúsítvánnyal van aláírva, mint amellyel az alkalmazás össze lett állítva, az alkalmazásfrissítési forgatókönyvek megszakadnak. Ennek megfelelően minden új aláíró tanúsítványt karban kell tartani az alkalmazásfrissítésekhez. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz futtatásához kapcsolódó biztonsági szempontok
A lehetséges hamisítási, információfelfedési és a jogok kiterjesztéséből adódó támadások megelőzése érdekében:

-   Győződjön meg róla, hogy a bemeneti üzletági (LOB) alkalmazás, a kimeneti alkalmazás és a Java KeyStore ugyanazon a Windows-számítógépen található, ahol az alkalmazásburkoló eszköz fut.

-   Importálja a kimeneti alkalmazást az Intune-ba ugyanazon a számítógépen, ahol az eszköz fut. További információ a Java kulcseszközről: [kulcseszköz](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Ha a kimeneti alkalmazás és az eszköz UNC elérési úton található, és az eszközt és a bemeneti fájlokat nem ugyanazon a számítógépen futtatja, a környezetet az [IPsec](https://wikipedia.org/wiki/IPsec) vagy [SMB-aláírás](https://support.microsoft.com/kb/887429) segítségével teheti biztonságossá.

-   Ügyeljen rá, hogy az alkalmazás megbízható forrásból származzon.

-   Tegye biztonságossá a beburkolt alkalmazást tartalmazó kimeneti könyvtárat. Fontolja meg a kimeneti oldal számára egy felhasználói szintű könyvtár használatát.

### <a name="see-also"></a>Lásd még:
- [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](apps-prepare-mobile-application-management.md)

- [A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek](app-sdk-android.md)
