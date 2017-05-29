---
title: "Android-alkalmazások burkolása az Alkalmazásburkoló eszközzel | Microsoft Docs"
description: "Ebből a cikkből megtudhatja, hogyan burkolhatja az Android-alkalmazásait anélkül, hogy módosítaná magának az alkalmazásnak a programkódját. Előkészítheti az alkalmazásokat a mobilalkalmazás-felügyeleti szabályzatok alkalmazására."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a89c2b26daf2b3b4da57e0c190f772e078681bee
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Android-alkalmazások előkészítése mobilalkalmazás-felügyelethez az Intune App Wrapping Tool eszközével

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune App Wrapping Tool for Android alkalmazásburkoló eszközzel módosíthatja a belső fejlesztésű Android-alkalmazások viselkedését, így az alkalmazások kódjának módosítása nélkül korlátozhatja az alkalmazások funkcióit.

Ez az eszköz egy windowsos parancssori alkalmazás, amely PowerShell-ablakban fut, és „beburkolja” az Android-alkalmazást. Az alkalmazás beburkolását követően az Intune-ban [mobilalkalmazás-kezelési szabályzatok](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) konfigurálásával módosíthatja az alkalmazás funkcióit.


Az eszköz futtatása előtt olvassa el a következő cikket: [Az alkalmazásburkoló eszköz futtatásához kapcsolódó biztonsági szempontok](#security-considerations-for-running-the-app-wrapping-tool). Az eszköz letöltéséhez keresse fel a [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) oldalát a GitHubon.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz használatára vonatkozó előfeltételek teljesítése

-   Az alkalmazásburkoló eszköz futtatásához egy Windows 7 vagy újabb operációs rendszerű Windows-számítógépre van szükség.

-   A bemeneti alkalmazásnak .apk kiterjesztésű érvényes Android-alkalmazáscsomagnak kell lennie, továbbá:

    -   Nem lehet titkosítva.
    -   Nem lehet már beburkolva az Intune App Wrapping Tool segítségével.
    -   Android 4.0-s vagy újabb operációs rendszerre kellett készülnie.

-   Vállalata által kifejlesztett vagy vállalata számára készült alkalmazásnak kell lennie. Az eszköz nem használható a Google Play áruházból letöltött alkalmazásokkal.

-   Az alkalmazásburkoló eszköz futtatásához telepítenie kell a [Java Runtime Environment](http://java.com/download/) legújabb verzióját, majd meg kell bizonyosodnia arról, hogy a Windows környezeti változók között a Java elérési útvonalának a következő van megadva: C:\ProgramData\Oracle\Java\javapath. További segítségért tekintse meg a [Java dokumentációt](http://java.com/download/help/).

    > [!NOTE]
    > Egyes esetekben a Java 32 bites verziója memóriaproblémákat okozhat. Tanácsos a 64 bites verziót telepíteni.

- Az Android megköveteli, hogy minden alkalmazáscsomag (.apk) alá legyen írva. A Java keytool eszközzel létrehozhatja a kimeneti burkolt alkalmazás aláírásához szükséges hitelesítő adatokat. Az alábbi parancs például olyan kulcsokat állít elő a keytool.exe végrehajtható fájllal, amelyeket az alkalmazásburkoló eszköz használhat a kimeneti burkolt alkalmazás aláírásához.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Ez a példa az RSA algoritmuson alapuló kulcspárt generál (egy 2048 bites nyilvános kulcsot és a hozzá tartozó titkos kulcsot). Ezután a nyilvános kulcsot egy X.509 v3 verziójú önaláírt tanúsítványba burkolja, és azt egyelemű tanúsítványláncként tárolja. A tanúsítványlánc és a titkos kulcs egy új, "mykeystorefile" nevű kulcstárban lesz tárolva, és a "mykeyalias" aliasszal azonosítható. A kulcstárbejegyzés érvényessége 50.000 nap.

    A parancs használatánál meg kell majd adnia a kulcstárhoz és a kulcshoz tartozó jelszavakat. Használjon biztonságos jelszavakat, de fontos, hogy feljegyezze őket, mert később szüksége lesz rá az alkalmazásburkoló eszköz futtatásához.

    Az Oracle-dokumentáció honlapján részletes információkat talál a Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) és a Java [Keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) témakörökben.

## <a name="install-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz telepítése

1.  A [GitHub-tárházból](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) egy Windows-számítógépre töltse le az Intune App Wrapping Tool for Android InstallAWT.exe teleptőfájlját. Nyissa meg a telepítőfájlt.

2.  Fogadja el a licencszerződést, majd fejezze be a telepítést.

Jegyezze fel a mappa nevét, ahová az eszközt telepítette. Az alapértelmezett hely a következő: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz futtatása

1.  Azon a Windows-számítógépen, amelyre az alkalmazásburkoló eszközt telepítette, nyisson meg egy rendszergazdai jogú PowerShell-ablakot.

2.  Az eszköz telepítési mappájából importálja az alkalmazásburkoló eszköz PowerShell-modulját:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Az eszközt az **invoke-AppWrappingTool** paranccsal futtathatja, a következő szintaxissal:
    ```
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
|**-SigAlg**&lt;SecureString&gt;| (Nem kötelező) Az aláíráshoz használandó aláírási algoritmus neve. Az algoritmusnak kompatibilisnek kell lennie a titkos kulccsal.|Példák: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Nem kötelező) A parancs támogatja gyakran használt PowerShell-paramétereket, mint például a verbose, a debug stb. |


- A gyakori paraméterek listáját lásd itt: [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Az eszköz használatáról részletes információt olvashat az alábbi parancs használatával:

    ```
    Help Invoke-AppWrappingTool
    ```

**Példa:**

Importálja a PowerShell modult.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Futtassa az alkalmazásburkoló eszközt a HelloWorld.apk natív alkalmazáson.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Az eszköz kérni fogja következő információkat: **KeyStorePassword** és **KeyPassword**. Adja meg a kulcstárfájlok létrehozásánál használt hitelesítő adatokat.

Az eszköz generálja a beburkolt alkalmazást, és menti a naplófájllal együtt a megadott kimeneti elérési útra.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Az alkalmazásburkoló eszköz futtatásához kapcsolódó biztonsági szempontok
A lehetséges hamisítási, információfelfedési és a jogok kiterjesztéséből adódó támadások megelőzése érdekében:

-   Győződjön meg róla, hogy a bemeneti üzletági (LOB) alkalmazás, a kimeneti alkalmazás és a Java KeyStore ugyanazon a Windows-számítógépen található, ahol az alkalmazásburkoló eszköz fut.

-   Importálja a kimeneti alkalmazást az Intune-konzolra ugyanazon a számítógépen, ahol az eszköz fut. A Java keytool eszközről a [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) ismertetőjéből tájékozódhat részletesebben.

-   Ha a kimeneti alkalmazás és az eszköz UNC elérési úton található, és az eszközt és a bemeneti fájlokat nem ugyanazon a számítógépen futtatja, a környezetet az [IPsec](http://wikipedia.org/wiki/IPsec) vagy [SMB-aláírás](https://support.microsoft.com/kb/887429) segítségével teheti biztonságossá.

-   Ügyeljen rá, hogy az alkalmazás megbízható forrásból származzon.

-   Tegye biztonságossá a beburkolt alkalmazást tartalmazó kimeneti könyvtárat. Fontolja meg a kimeneti oldal számára egy felhasználói szintű könyvtár használatát.

### <a name="see-also"></a>További információ
- [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Alkalmazások előkészítése a mobilalkalmazás-felügyeletre az SDK segítségével](use-the-sdk-to-enable-apps-for-mobile-application-management.md)

