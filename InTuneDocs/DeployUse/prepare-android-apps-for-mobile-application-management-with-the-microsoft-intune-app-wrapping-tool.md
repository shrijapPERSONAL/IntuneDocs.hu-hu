---
title: "Android-alkalmazások burkolása az Alkalmazásburkoló eszközzel | Microsoft Intune"
description: "Ebből a témakörből megtudhatja, hogyan burkolhatja az Android-alkalmazásait anélkül, hogy módosítaná az alkalmazás programkódját. Előkészítheti az alkalmazásokat a mobilalkalmazás-felügyeleti szabályzatok alkalmazására."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe3a9f2fd9ce9a3c3f776dcfd9ad3347a63d0fc1
ms.openlocfilehash: e623755cf926020bcb66d8a6d40e5cce9b46b0ae


---

# Android-alkalmazások előkészítése mobilalkalmazás-felügyelethez az Intune App Wrapping Tool eszközével
A **Microsoft Intune App Wrapping Tool for Android** alkalmazásburkoló eszközzel módosíthatja a belső fejlesztésű Android-alkalmazások viselkedését, így az alkalmazások kódjának módosítása nélkül korlátozhatja az alkalmazások funkcióit.

Ez az eszköz egy windowsos parancssori alkalmazás, amely PowerShell ablakban fut, és „beburkolja” az Android-alkalmazást. Az alkalmazás beburkolását követően az Intune-ban [mobilalkalmazás-kezelési szabályzatok](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) konfigurálásával módosíthatja az alkalmazás funkcióit.


Az eszköz futtatása előtt olvassa el a következő cikket: [Az alkalmazásburkoló eszköz futtatásához kapcsolódó biztonsági szempontok](#security-considerations-for-running-the-app-wrapping-tool). Az eszköz letöltéséhez keresse fel a [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) oldalát a GitHubon.



## 1. lépés: Az alkalmazásburkoló eszköz használatára vonatkozó előfeltételek teljesítése

-   Az alkalmazásburkoló eszköz futtatásához egy Windows 7 vagy újabb operációs rendszerrel ellátott Windows számítógépre van szükség.

-   A bemeneti alkalmazásnak **.apk** kiterjesztésű érvényes Android alkalmazáscsomagnak kell lennie, továbbá:

    -   Nem lehet titkosított

    -   Nem lehet már beburkolva az Intune App Wrapping Tool által
    -   Android 4.0 vagy újabb operációs rendszerre készült

-   Vállalata által kifejlesztett vagy annak számára készült alkalmazás. Az eszköz nem használható a Google Play áruházból letöltött alkalmazásokkal.

-   Az alkalmazásburkoló eszköz futtatásához telepítenie kell a [Java Runtime Environment](http://java.com/download/) legújabb verzióját, majd meg kell bizonyosodnia arról, hogy a Windows környezeti változók között a Java elérési útvonalának a következő van megadva: **C:\ProgramData\Oracle\Java\javapath**. További segítségért tekintse meg a [Java dokumentációt](http://java.com/download/help/).

    > [!NOTE]
    > Egyes esetekben a Java 32 bites verziója memóriaproblémákat okozhat. Javasoljuk, hogy telepítse a 64 bites verziót.

- Az Android megköveteli, hogy minden alkalmazáscsomag (.apk) alá legyen írva. A Java Key Tool használatával létrehozhatja a kimeneti burkolt alkalmazás aláírásához szükséges hitelesítő adatokat. Az alábbi parancs például a **keytool.exe** végrehajtható fájlt használja olyan kulcsok előállításához, amelyeket az alkalmazásburkoló eszköz használhat a kimeneti burkolt alkalmazás aláírásához.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Ez a példa az RSA algoritmus használatával létrehoz egy kulcspárt (egy nyilvános kulcsot és egy hozzá kapcsolódó 2048 bites titkos kulcsot), majd a nyilvános kulcsot egy X.509 v3 verziójú önaláírt tanúsítványba burkolja, amelyet egyelemű tanúsítványláncként tárol. A tanúsítványlánc és a titkos kulcs egy új, "mykeystorefile" nevű kulcstárban lesz tárolva, és a "mykeyalias" aliasszal azonosítható. A kulcstárbejegyzés érvényessége 50.000 nap.

    A parancs használatánál meg kell majd adnia a kulcstárhoz és a kulcshoz tartozó jelszavakat. Használjon biztonságos és nehezen kitalálható jelszavakat, de fontos, hogy megjegyezze őket, mert a későbbiekben az alkalmazásburkoló eszköz használatánál még szüksége lesz rájuk.

    Az Oracle-dokumentáció honlapján részletes információkat talál a Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) és a Java [Keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) témakörökben.

## 2. lépés: Az alkalmazásburkoló eszköz telepítése

1.  A [GitHub-tárházból](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) egy Windows-számítógépre töltse le, majd nyissa meg az Intune App Wrapping Tool for Android **InstallAWT.exe** teleptőfájlját.

2.  Fogadja el a licencszerződést, majd fejezze be a telepítést.

Jegyezze fel a mappa nevét, ahová az eszközt telepítette. Az alapértelmezett hely a következő: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## 3. lépés: Az alkalmazásburkoló eszköz futtatása

1.  Azon a Windows-számítógépen, amelyre az alkalmazásburkoló eszközt telepítette, nyisson meg egy rendszergazdai jogú PowerShell-ablakot.

2.  Az eszköz telepítési mappájából importálja az alkalmazásburkoló eszköz PowerShell-modulját:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Az eszközt az **invoke-AppWrappingTool** paranccsal futtathatja, az alábbi szintaxis használatával:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 Az alábbi táblázat az **invoke-AppWrappingTool** parancs tulajdonságait ismerteti:

|Tulajdonság|Információ|Példa|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Az Android-forrásalkalmazás (.apk) elérési útja.| |
|**-OutputPath**&lt;String&gt;|A „kimeneti” Android-alkalmazás elérési útja. Ha ez megegyezik az InputPath értékével, a burkolás sikertelen lesz.| |
|**-KeyStorePath**&lt;karaktersor&gt;|Az aláíráshoz használt nyilvános és titkos kulcsból álló kulcspárt tartalmazó kulcstárfájl elérési útja.|A kulcstárfájlok alapértelmezés szerint a "C:\Program Files (x86)\Java\jreX.X.X_XX\bin" könyvtárban találhatók. |
|**-KeyStorePassword**&lt;SecureString&gt;|A kulcstár visszafejtésére szolgáló jelszó. Az Android elvárja, hogy minden alkalmazáscsomag (.apk) alá legyen írva. A Java Key Tool segítségével hozza létre a KeyStorePassword kulcsot. További információk a Java [kulcstárról](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).| |
|**-KeyAlias**&lt;String&gt;|Az aláíráshoz használt kulcs neve.| |
|**-KeyPassword**&lt;SecureString&gt;|Az aláíráshoz használt titkos kulcs visszafejtésére szolgáló jelszó.| |
|**-SigAlg**&lt;SecureString&gt;| (Nem kötelező) Az aláíráshoz használandó aláírási algoritmus neve. Az algoritmusnak kompatibilisnek kell lennie a titkos kulccsal.|Példák: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Nem kötelező) A parancs olyan gyakori PowerShell-paramétereket támogat, mint például a verbose, a debug stb. |


- A gyakori paraméterek listáját lásd itt: [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Az eszköz használatáról részletes információt olvashat az alábbi parancs használatával:

    ```
    Help Invoke-AppWrappingTool
    ```

**Például:**

Importálja a PowerShell modult.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1" 
```
Futtassa az alkalmazásburkoló eszközt a **HelloWorld.apk** natív alkalmazáson. 
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

A rendszer a következő információkat fogja kérni: **KeyStorePassword** és **KeyPassword**. Adja meg a kulcstárfájlok létrehozásánál használt hitelesítő adatokat.

A beburkolt alkalmazás létrehozása és mentése egy naplófájllal együtt, a megadott kimeneti elérési úton történik.

## Az alkalmazásburkoló eszköz futtatásához kapcsolódó biztonsági szempontok
A lehetséges hamisítási, információfelfedési és a jogok kiterjesztéséből adódó támadások megelőzése érdekében:

-   Győződjön meg róla, hogy a bemeneti üzletági (LOB) alkalmazás, a kimeneti alkalmazás és a Java KeyStore ugyanazon a Windows-számítógépen található, ahol az alkalmazásburkoló eszköz fut.

-   Importálja a kimeneti alkalmazást az Intune-konzolra ugyanazon a számítógépen, ahol az eszköz fut. További információk a Java kulcseszközről: [kulcseszköz](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Ha a kimeneti alkalmazás és az eszköz univerzális elnevezési konvenció (UNC) szerinti elérési útvonalon található, és az eszközt és a bemeneti fájlokat nem ugyanazon a számítógépen futtatja, a környezet biztonságos beállításait az [Internet Protocol Security (IPsec)](http://en.wikipedia.org/wiki/IPsec) vagy a [Server Message Block (SMB) aláírás](https://support.microsoft.com/en-us/kb/887429)használatával adhatja meg.

-   Ügyeljen rá, hogy az alkalmazás megbízható forrásból származzon.

-   Tegye biztonságossá a beburkolt alkalmazást tartalmazó kimeneti könyvtárat. Fontolja meg a kimeneti oldal számára egy felhasználói szintű könyvtár használatát.



### További információ
- [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Alkalmazások előkészítése a mobilalkalmazás-felügyeletre az SDK segítségével](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


