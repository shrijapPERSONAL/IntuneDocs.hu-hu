---
title: "Alkalmazások hozzáadása | Microsoft Intune"
description: "Mielőtt elkezdi az alkalmazások telepítését az Intune-nal, fordítson egy kis időt az ebben a témakörben bemutatott fogalmakkal való ismerkedésre."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 3b35e835634733f542b7ddaf2ede2ad2464721fd


---

# Alkalmazások hozzáadása a Microsoft Intune-nal
Mielőtt elkezdi az alkalmazások telepítését a Microsoft Intune-nal, fordítson egy kis időt az ebben a témakörben bemutatott fogalmakkal való ismerkedésre. Ezek megkönnyítik annak megértését, hogy melyik alkalmazás melyik platformra telepíthető, illetve segítenek a telepítés elvégzése előtt megismerni az előfeltételeket.

## Telepíthető alkalmazástípusok

### Szoftvertelepítő

|Alkalmazás típusa|Részletek|
|----------------|-------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|Az ilyen típusú alkalmazásnak támogatnia kell a felhasználói beavatkozás nélküli, csendes telepítést. Az alkalmazás dokumentációjának tartalmaznia kell a megfelelő parancssori kapcsolókat az alkalmazás csendes telepítéséhez (például **/q**).<br>A gyakran használt parancssori kapcsolók listája [itt](https://support.microsoft.com/en-us/kb/227091) található.<br><br>Az alkalmazás telepítőprogramja által igényelt minden további fájlnak és mappának elérhetőnek kell lennie az alkalmazás telepítési fájljai számára megadott helyen.<br><br>A legtöbb esetben a Windows Installer-fájlok (.msi) és a Windows Installer-javítófájlok (.msp) fájlok Intune általi telepítése nem igényel parancssori argumentumokat. Tanulmányozza az alkalmazás dokumentációját.<br><br>Ha parancssori argumentumokra van szükség, azokat Név=Érték párként kell megadni (például TRANSFORMS=custom_transform.mst).|
|**Alkalmazáscsomag Androidhoz (&#42;.apk file)**|Android-alkalmazások telepítéséhez egy érvényes .apk csomaggal kell rendelkeznie|
|**Alkalmazáscsomag iOS-hez (&#42;.ipa file)**|iOS-alkalmazások telepítéséhez egy érvényes .ipa csomaggal kell rendelkeznie.<br><br>Az .ipa csomagnak Apple-aláírással kell rendelkeznie, és a lejárati dátum szerint a létesítési profilnak érvényesnek kell lennie. Az Intune képes terjeszteni a vállalati tanúsítvánnyal rendelkező iOS-alkalmazásokat.<br>A szolgáltatás nem minden Apple-fejlesztői tanúsítvánnyal rendelkező alkalmazást támogat.<br><br>A vállalatnak regisztrálnia kell az iOS Developer Enterprise programban.<br><br>Győződjön meg arról, hogy a vállalati tűzfal hozzáférést biztosít az üzembe helyezési és minősítési iOS-webhelyekhez.<br><br>Nem szükséges jegyzékfájlt (.plist) telepítenie az alkalmazással.|
|**Windows Phone-alkalmazáscsomag (&#42;.xap, .appx, .appxbundle)**|Alkalmazások telepítéséhez vállalati mobil-kódaláíró tanúsítvánnyal kell rendelkeznie.<br>Részletekért olvassa el a [Windows Phone-telefonok Microsoft Intune-beli kezelésének beállítása](set-up-windows-phone-management-with-microsoft-intune.md) című cikket.|
|**Windows-alkalmazáscsomag (.appx, .appxbundle)**|Alkalmazások telepítéséhez vállalati mobil-kódaláíró tanúsítvánnyal kell rendelkeznie.<br>Részletekért olvassa el a [Windowsos eszközök Microsoft Intune-beli kezelésének beállítása](set-up-windows-device-management-with-microsoft-intune.md) című cikket.|
|**Windows Installer MDM-en keresztül (&#42;.msi)**|Lehetővé teszi a Windows Installer-alapú alkalmazások létrehozását és telepítését Windows 10 rendszert futtató, regisztrált (MDM által kezelt) eszközökön.<br /><br />Csakis egyetlen MSI-fájlt tölthet fel.<br><br>Az alkalmazások észlelése a fájl termékkódjával és termékverziójával történik.<br><br>A rendszer az alkalmazás alapértelmezett újraindítási viselkedését fogja használni. Az Intune nem szabályozza ezt.<br><br>Felhasználónkénti MSI-csomagok fognak települni egy-egy felhasználóhoz.<br><br>Gépenkénti MSI-csomagok fognak települni az eszköz minden felhasználójához.<br><br>A kettős üzemmódú MSI-csomagok jelenleg csak az eszköz összes felhasználójához telepíthetők.<br><br>Az alkalmazások frissítése akkor támogatott, ha minden verzió MSI-termékkódja ugyanaz.<br>
Minden szoftvertelepítő-alkalmazástípus feltöltése a felhőalapú tárhelybe történik.

### **Külső hivatkozás**
A következők esetében használatos:
- Olyan **URL-cím**, amely lehetővé teszi, hogy a felhasználók letöltsék az adott alkalmazást egy alkalmazás-áruházból.
- Webböngészőből futtatható, webalkalmazásra mutató **hivatkozás**.

A külső hivatkozásokon alapuló alkalmazásokat nem tárolja a rendszer az Intune felhőbeli tárhelyén.
### **Felügyelt iOS-alkalmazás az App Store-ból**
Az App Store áruházban ingyenesen elérhető iOS-alkalmazások felügyeletét és telepítését teszi lehetővé. [Mobilalkalmazás-felügyeleti szabályzatokat](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) is társíthat [kompatibilis alkalmazásokhoz](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx), és ellenőrizheti az alkalmazások állapotát a felügyeleti konzolon.<br /><br />A felügyelt iOS-alkalmazásokat nem tárolja az Intune felhőbeli tárhelye.

> [!TIP]
> A mobileszközökre vonatkozó beállítások csak azután lesznek elérhetők, ha a [Mobileszköz-felügyeleti szolgáltató megadása](get-ready-to-enroll-devices-in-microsoft-intune.md) beállítást az Intune-ra állította.

## Az Intune Software Publisher
A **Microsoft Intune Software Publisher** akkor indul el, amikor alkalmazásokat ad hozzá vagy módosít az Intune felügyeleti konzolról. Ebben a közzétételi eszközben meg kell adnia és konfigurálnia kell egy szoftvertelepítő-típust, amely feltölti az Intune felhőtárhelyén tárolni kívánt számítógép- vagy mobileszköz-alkalmazásokat, illetve kapcsolódik egy online áruházhoz vagy webalkalmazáshoz.

Mielőtt megkezdené a Software Publisher használatát, telepítenie kell a [Microsoft .NET-keretrendszer 4.0](https://www.microsoft.com/download/details.aspx?id=17851) teljes verzióját. Előfordulhat, hogy a Software Publisher csak akkor nyílik meg megfelelően, ha a telepítést követően újraindítja a számítógépet.

## Felhőtárhely
A szoftvertelepítő típusú telepítéssel létrehozott összes alkalmazás (például az üzletági alkalmazások) be vannak csomagolva, és fel vannak töltve a Microsoft Intune felhőtárhelyére. Az Intune próba-előfizetése 2 gigabájtnyi (GB) felhőtárhelyet biztosít a felügyelt alkalmazások és frissítések tárolásához. A teljes előfizetése 20 GB tárterületet tartalmaz.

A **Felügyelet** munkaterület **Tárolóhely-használat** csomópontjában tekintheti meg, hogy mekkora területet használ.

### A felhőtárhelyre vonatkozó követelmények

-   Győződjön meg róla, hogy az összes alkalmazás telepítési fájljai ugyanabban a mappában vannak-e.

-   A feltöltött fájlok legfeljebb 2 GB méretűek lehetnek.


## Az univerzális Windows-platformra épülő alkalmazások támogatása
A Windows 10-es számítógépekre közvetlen telepítésre szolgáló kulcs nélkül is telepíthetők az üzletági alkalmazások. A közvetlen telepítés azonban csak akkor lehetséges, ha a **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** beállításkulcs értéke **1**.

Ha nincs konfigurálva ez a beállításkulcs, az Intune automatikusan **1** értékre állítja, amikor először telepítenek egy alkalmazást a szóban forgó eszközre. Amennyiben **0** értékre állította ezt az értéket, az Intune nem tudja azt automatikusan módosítani, ezért sikertelen lesz az üzletági alkalmazások telepítése.

Az univerzális Windows-platformra épülő üzletági alkalmazásokat olyan kódaláíró tanúsítvánnyal kell aláírni, amely megbízhatónak minősül minden olyan eszközön, amelyre telepítik az alkalmazást. Ehhez használhatók a nyilvános kulcsokra épülő belső infrastruktúra tanúsítványai vagy az eszközre telepített, harmadik féltől származó nyilvános főtanúsítvány valamely tanúsítványa.

A Windows 10 Mobile rendszerű eszközökön nem a Symantec által kiállított kódaláíró tanúsítvánnyal is aláírhatók az univerzális **.appx** alkalmazások. Azok a Windows Phone 8.1-es **.xap** alkalmazások és **.appx** csomagok, amelyeket Windows 10 Mobile rendszerű eszközökre kíván telepíteni, csak a Symantec által kiállított kódaláíró tanúsítvánnyal írhatók alá.

## További lépések 

Ezután az alkalmazásokat fel kell vennie az Intune-konzolon, mielőtt telepíthetné őket. A [regisztrált eszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md) vagy [az Intune ügyfélszoftverével felügyelt Windows-számítógépekhez](add-apps-for-windows-pcs-in-microsoft-intune.md) is hozzáadhat alkalmazásokat.



<!--HONumber=Jul16_HO3-->


