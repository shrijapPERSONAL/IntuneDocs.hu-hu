---
title: "Alkalmazások hozzáadása"
description: "Mielőtt elkezdi az alkalmazások telepítését az Intune-nal, fordítson egy kis időt az ebben a témakörben bemutatott fogalmakkal való ismerkedésre."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 18272f21799253128cfe0ad6aa66e108b24a0b50
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---

# <a name="add-apps-with-microsoft-intune"></a>Alkalmazások hozzáadása a Microsoft Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Mielőtt elkezdi az alkalmazások telepítését a Microsoft Intune-nal, fordítson egy kis időt az ebben a témakörben bemutatott fogalmakkal való ismerkedésre. Ezek a fogalmak segítenek annak megértésében, hogy mely alkalmazásokat mely platformra telepítheti. Továbbá az alkalmazások telepítéséhez szükséges előfeltételek megismerésében is segítenek.

## <a name="app-types-that-you-can-deploy"></a>Telepíthető alkalmazástípusok

### <a name="software-installer"></a>Szoftvertelepítő

|Alkalmazás típusa|Részletek|
|----------------|-------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|Az ilyen típusú alkalmazásnak támogatnia kell a felhasználói beavatkozás nélküli, csendes telepítést. Az alkalmazás dokumentációjának tartalmaznia kell a megfelelő parancssori kapcsolókat az alkalmazás csendes telepítéséhez (például **/q**). Az általános parancssori kapcsolók listája a [Microsoft Windows Installer eszköz parancssori kapcsolói](https://support.microsoft.com/kb/227091) című dokumentumban találhatók.<br><br>Az alkalmazás telepítőprogramja által igényelt minden további fájlnak és mappának elérhetőnek kell lennie az alkalmazás telepítési fájljai számára megadott helyen.<br><br>A legtöbb esetben a Windows Installer-fájlok (.msi) és a Windows Installer-javítófájlok (.msp) fájlok Intune általi telepítése nem igényel parancssori argumentumokat. Tanulmányozza az alkalmazás dokumentációját.<br><br>Ha parancssori argumentumokra van szükség, azokat Név=Érték párként kell megadni (például TRANSFORMS=custom_transform.mst).<br><br>Ez az alkalmazástípus csak az Intune szoftverügyfelet futtató számítógépekre vonatkozik.|
|**Alkalmazáscsomag az Androidhoz (&#42;.apk)**|Android-alkalmazások telepítéséhez egy érvényes .apk csomaggal kell rendelkeznie.|
|**Alkalmazáscsomag az iOS-hez (&#42;.ipa)**|iOS-alkalmazások telepítéséhez egy érvényes .ipa csomaggal kell rendelkeznie.<br><br>Az .ipa csomagnak Apple-aláírással kell rendelkeznie, és a kiépítési profilban lévő lejárati dátumnak érvényesnek kell lennie. Az Intune képes terjeszteni a vállalati tanúsítvánnyal rendelkező iOS-alkalmazásokat.<br><br>A szolgáltatás nem minden Apple-fejlesztői tanúsítvánnyal rendelkező alkalmazást támogat.<br><br>A vállalatnak regisztrálnia kell az iOS Developer Enterprise programban.<br><br>Győződjön meg arról, hogy a szervezet tűzfala lehetővé teszi a hozzáférést az iOS üzembe helyezési és hitelesítő webhelyeihez.<br><br>Nem szükséges jegyzékfájlt (.plist) telepítenie az alkalmazással.|
|**Windows Phone-alkalmazáscsomag (&#42;.xap, .appx, .appxbundle)**|Alkalmazások telepítéséhez vállalati mobil-kódaláíró tanúsítvánnyal kell rendelkeznie. Részletekért olvassa el a [Windows Phone-telefonok Microsoft Intune-beli kezelésének beállítása](set-up-windows-device-management-with-microsoft-intune.md) című cikket.|
|**Windows-alkalmazáscsomag (.appx, .appxbundle)**|Alkalmazások telepítéséhez vállalati mobil-kódaláíró tanúsítvánnyal kell rendelkeznie. Részletekért olvassa el a [Windowsos eszközök Microsoft Intune-beli kezelésének beállítása](set-up-windows-device-management-with-microsoft-intune.md) című cikket.|
|**Windows Installer MDM-en keresztül (&#42;.msi)**|Az alkalmazás lehetővé teszi a Windows Installer-alapú alkalmazások létrehozását és telepítését Windows 10-et futtató, regisztrált számítógépeken. A számítógépek kezelése a mobileszköz-kezelési szolgáltatáson keresztül történik.<br /><br />Csak egyetlen, .msi kiterjesztéssel rendelkező fájlt tölthet fel.<br><br>Az alkalmazások észlelése a fájl termékkódjával és termékverziójával történik.<br><br>A rendszer az alkalmazás alapértelmezett újraindítási viselkedését fogja használni. Az Intune nem szabályozza ezt.<br><br>Felhasználónkénti MSI-csomagok fognak települni egy-egy felhasználóhoz.<br><br>Gépenkénti MSI-csomagok fognak települni az eszköz minden felhasználójához.<br><br>A kettős üzemmódú MSI-csomagok jelenleg csak az eszköz összes felhasználójához telepíthetők.<br><br>Az alkalmazások frissítése akkor támogatott, ha minden verzió MSI-termékkódja ugyanaz.<br>
Minden szoftvertelepítő-alkalmazástípus feltöltése a felhőalapú tárhelybe történik.

### <a name="external-link"></a>**Külső hivatkozás**
Külső hivatkozás használata, ha az alábbiakkal rendelkezik:
- Olyan URL-cím, amely lehetővé teszi, hogy a felhasználók letöltsék az adott alkalmazást egy alkalmazás-áruházból.
- Webböngészőből futtatható, webalkalmazásra mutató hivatkozás.

A külső hivatkozásokon alapuló alkalmazásokat nem tárolja a rendszer az Intune felhőbeli tárhelyén.
### <a name="managed-ios-app-from-the-app-store"></a>**Felügyelt iOS-alkalmazás az App Store-ból**
A felügyelt iOS-alkalmazásokkal az App Store áruházban ingyenesen elérhető iOS-alkalmazások felügyeletét és telepítését végezheti el. A felügyelt iOS-alkalmazásokkal [mobilalkalmazás-felügyeleti szabályzatokat](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) is hozzárendelhet a [kompatibilis alkalmazásokhoz](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx), és ellenőrizheti az alkalmazások állapotát a felügyeleti konzolon.<br /><br />A felügyelt iOS-alkalmazásokat nem tárolja az Intune felhőbeli tárhelye.

> [!TIP]
> A mobileszközökre vonatkozó beállítások csak azután lesznek elérhetők, ha a [Mobileszköz-kezelő szolgáltató megadása](prerequisites-for-enrollment.md) beállítást az Intune-ra állította.

## <a name="intune-software-publisher"></a>Intune Software Publisher
Ha alkalmazásokat vesz fel vagy módosít az Intune felügyeleti konzol használatával, elindul a Microsoft Intune Software Publisher. A Publisher alkalmazásban elvégezheti az alábbi szoftvertelepítő-típusok kijelölését és konfigurálását:

- Alkalmazások (számítógépes programok vagy mobileszközökre szánt alkalmazások) feltöltése tárolás céljából az Intune felhőalapú tárhelyére.
- Online áruházbeli alkalmazásra vagy webalkalmazásra mutató hivatkozás.

Mielőtt megkezdené a Software Publisher használatát, telepítenie kell a [Microsoft .NET-keretrendszer 4.0](https://www.microsoft.com/download/details.aspx?id=17851) teljes verzióját. Előfordulhat, hogy a Software Publisher csak akkor nyílik meg megfelelően, ha a telepítést követően újraindítja a számítógépet.

## <a name="cloud-storage-space"></a>Felhőtárhely
A szoftvertelepítő típusú telepítéssel létrehozott összes alkalmazást (például az üzletági alkalmazásokat) a rendszer becsomagolja és feltölti a Microsoft Intune felhőtárhelyére. Az Intune próba-előfizetése 2 gigabájtnyi (GB) felhőtárhelyet biztosít a felügyelt alkalmazások és frissítések tárolásához. A teljes előfizetése 20 GB tárterületet tartalmaz.

A **Felügyelet** munkaterület **Tárolóhely-használat** csomópontjában tekintheti meg, hogy mekkora területet használ. Az eredeti vásárlási móddal vásárolhat további tárterületet az Intune számára.  Ha számla ellenében vagy hitelkártyával fizetett, keresse fel az [Előfizetés-kezelési portált](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Más esetben forduljon vállalatának partnercégéhez vagy értékesítési kapcsolattartójához.

A felhőtárhelyre vonatkozó követelmények az alábbiak:

-   Az összes alkalmazás telepítési fájljainak ugyanabban a mappában kell lenniük.
-   A feltöltött fájlok legfeljebb 2 GB méretűek lehetnek.


## <a name="support-for-universal-windows-platform-uwp-apps"></a>Az univerzális Windows-platformra épülő alkalmazások támogatása
A Windows 10-es számítógépekre közvetlen telepítésre szolgáló kulcs nélkül is telepíthetők az üzletági alkalmazások. A közvetlen telepítés azonban csak akkor lehetséges, ha a **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** beállításkulcs értéke **1**.

Ha nincs konfigurálva ez a beállításkulcs, az Intune automatikusan **1** értékre állítja, amikor először telepítenek egy alkalmazást a szóban forgó eszközre. Amennyiben **0** értékre állította ezt az értéket, az Intune nem tudja azt automatikusan módosítani, ezért sikertelen lesz az üzletági alkalmazások telepítése.

Az univerzális Windows-platformra épülő üzletági alkalmazásokat olyan kódaláíró tanúsítvánnyal kell aláírni, amely megbízhatónak minősül minden olyan eszközön, amelyre telepítik az alkalmazást. Ehhez használhatók a belső fejlesztésű, nyilvános kulcsokra épülő infrastruktúra tanúsítványai vagy az eszközre telepített, harmadik féltől származó nyilvános főtanúsítvány valamely tanúsítványa.

A Windows 10 Mobile rendszerű eszközökön nem a Symantec által kiállított kódaláíró tanúsítvánnyal is aláírhatók az univerzális **.appx** alkalmazások. Azok a Windows Phone 8.1-es **.xap** alkalmazások és **.appx** csomagok, amelyeket Windows 10 Mobile rendszerű eszközökre kíván telepíteni, csak a Symantec által kiállított kódaláíró tanúsítvánnyal írhatók alá.

### <a name="dependencies-for-uwp-apps"></a>Az UWP-alkalmazások függőségei

Ha Windows 10-es Universal appxbundle csomagot ad hozzá az Intune-hoz, mindig töltse fel egyben az alkalmazás függőségeit is.
Ehhez helyezze az alkalmazás buildjének elkészítésekor létrehozott **Dependencies** mappa ugyanabban a mappában legyen, mint maga az .appxbundle-fájl.
Ebben az esetben, amikor feltölti az alkalmazást az Intune-ba, a rendszer a **Dependencies** mappában található fájlokat is feltölti. A következő képernyőkép ezt mutatja be:


![A Windows 10 UWP appxbundle függőségeinek kiválasztása](./media/w10-dependencies.png)


## <a name="next-steps"></a>További lépések

Az alkalmazásokat fel kell vennie az Intune-konzolon, mielőtt telepíthetné őket. A [regisztrált eszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md) vagy [az Intune ügyfélszoftverével felügyelt Windows-számítógépekhez](add-apps-for-windows-pcs-in-microsoft-intune.md) is hozzáadhat alkalmazásokat.

