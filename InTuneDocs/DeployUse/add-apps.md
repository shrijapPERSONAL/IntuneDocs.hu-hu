---
title: "Alkalmazások hozzáadása | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: a3af42343f1ec2c5af3dda4828f8840bb76c4d5f
ms.openlocfilehash: 2a76daee73f0dd3c6219a4cf42f9bb00fd83f257


---

# Alkalmazások hozzáadása a Microsoft Intune-nal
Mielőtt elkezdi az alkalmazások telepítését a Microsoft Intune-nal, fordítson egy kis időt az ebben a témakörben bemutatott fogalmakkal való ismerkedésre. Ezek megkönnyítik annak megértését, hogy melyik alkalmazás melyik platformra telepíthető, illetve segítenek a telepítés elvégzése előtt megismerni az előfeltételeket.

## Az Intune-nal telepíthető alkalmazástípusok
Az Intune által támogatott összes eszköztípusra telepíthetők alkalmazások. A folyamatok és a támogatott eszközök a telepíteni kívánt alkalmazás típusától függően eltérnek. Az alábbi részek a telepíthető és a nem telepíthető alkalmazásokat ismertetik:


### **Windows Installer (&#42;.exe, &#42;.msi)**
- Az ilyen típusú alkalmazásnak támogatnia kell a felhasználói beavatkozás nélküli, csendes telepítést. Az alkalmazás dokumentációjának tartalmaznia kell a megfelelő parancssori kapcsolókat az alkalmazás csendes telepítéséhez (például **/q**). A gyakran használt parancssori kapcsolók listája [itt](https://support.microsoft.com/en-us/kb/227091) található.
- Az alkalmazás telepítőprogramja által igényelt minden további fájlnak és mappának elérhetőnek kell lennie az alkalmazás telepítési fájljai számára megadott helyen.
- A legtöbb esetben a Windows Installer-fájlok (.msi) és a Windows Installer-javítófájlok (.msp) fájlok Intune általi telepítése nem igényel parancssori argumentumokat. Tanulmányozza az alkalmazás dokumentációját. Ha parancssori argumentumokra van szükség, azokat Név=Érték párként kell megadni (például TRANSFORMS=custom_transform.mst).

Az ilyen típusú alkalmazást feltölti a rendszer a felhőalapú tárhelyre.
### **Alkalmazáscsomag Androidhoz (&#42;.apk file)**
Az ilyen típusú alkalmazást feltölti a rendszer a felhőalapú tárhelyre.
### **Alkalmazáscsomag iOS-hez (&#42;.ipa file)**
- iOS-alkalmazások telepítéséhez egy érvényes .ipa csomaggal kell rendelkeznie.
- Az .ipa csomagnak Apple-aláírással kell rendelkeznie, és a lejárati dátum szerint a létesítési profilnak érvényesnek kell lennie. Az Intune képes terjeszteni a vállalati tanúsítvánnyal rendelkező iOS-alkalmazásokat. A szolgáltatás nem minden Apple-fejlesztői tanúsítvánnyal rendelkező alkalmazást támogat.
- A vállalatnak regisztrálnia kell az iOS Developer Enterprise programban.
- Győződjön meg arról, hogy a vállalati tűzfal hozzáférést biztosít az üzembe helyezési és minősítési iOS-webhelyekhez.
- A jegyzékfájlt (.plist) nem szükséges az alkalmazással együtt telepíteni.

Az ilyen típusú alkalmazást feltölti a rendszer a felhőalapú tárhelyre.

A végfelhasználók jelenleg nem tudnak közvetlenül telepíteni vállalati alkalmazásokat az iOS rendszerhez készült Intune Vállalati portál alkalmazásból. A telepítés az iOS App Store-ban közzétett alkalmazásokra vonatkozó korlátozások miatt nem lehetséges (lásd az [App Store felülvizsgálati irányelveit](https://developer.apple.com/app-store/review/guidelines/)). A felhasználók úgy férhetnek hozzá a vállalati alkalmazásokhoz (beleértve a felügyelt App Store-alkalmazásokat és az üzletági alkalmazáscsomagokat is), ha elindítják a Vállalati portál alkalmazást az eszközükön, majd a Vállalati alkalmazások csempére koppintanak, amely megnyitja a böngészőt, és átirányítja őket az Intune webportáljára.

### **Windows Phone-alkalmazáscsomag (&#42;.xap, .appx, .appxbundle)**
- Alkalmazások telepítéséhez vállalati mobil-kódaláíró tanúsítvánnyal kell rendelkeznie. Részletekért olvassa el a [Windows Phone-telefonok Microsoft Intune-beli kezelésének beállítása](set-up-windows-phone-management-with-microsoft-intune.md) című cikket.

Az ilyen típusú alkalmazást feltölti a rendszer a felhőalapú tárhelyre.

Lentebb információkat talál az Univerzális Windows-platformra épülő üzletági alkalmazások Intune-beli telepítéséről.

### **Windows-alkalmazáscsomag (.appx, .appxbundle)**
- Alkalmazások telepítéséhez vállalati mobil-kódaláíró tanúsítvánnyal kell rendelkeznie. Részletekért olvassa el a [Windowsos eszközök Microsoft Intune-beli kezelésének beállítása](set-up-windows-device-management-with-microsoft-intune.md) című cikket.

Az ilyen típusú alkalmazást feltölti a rendszer a felhőalapú tárhelyre.
### **Windows Installer MDM-en keresztül (&#42;.msi)**
Ez a telepítő lehetővé teszi a Windows Installer-alapú alkalmazások létrehozását és telepítését Windows 10-et futtató, regisztrált számítógépeken.<br /><br />Ennek a telepítőtípusnak a használatakor a következőket kell figyelembe venni:
- Csakis egyetlen MSI-fájlt tölthet fel.
- Az alkalmazások észlelése a fájl termékkódjával és termékverziójával történik.
- A rendszer az alkalmazás alapértelmezett újraindítási viselkedését fogja használni. Az Intune nem szabályozza ezt.
- Felhasználónkénti MSI-csomagok fognak települni egy-egy felhasználóhoz.
- Gépenkénti MSI-csomagok fognak települni az eszköz minden felhasználójához.
- A kettős üzemmódú MSI-csomagok jelenleg csak az eszköz összes felhasználójához telepíthetők.
- Az alkalmazások frissítése akkor támogatott, ha minden verzió MSI-termékkódja ugyanaz.

Az ilyen típusú alkalmazást feltölti a rendszer a felhőalapú tárhelyre.
### **Külső hivatkozás**
A következők esetében használatos:
- Olyan **URL-cím**, amely lehetővé teszi, hogy a felhasználók letöltsék az adott alkalmazást egy alkalmazás-áruházból.
- Webböngészőből futtatható, webalkalmazásra mutató **hivatkozás**.

A külső hivatkozásokon alapuló alkalmazásokat nem tárolja a rendszer az Intune felhőbeli tárhelyén.
### **Felügyelt iOS-alkalmazás az App Store-ból**
Az App Store áruházban ingyenesen elérhető iOS-alkalmazások felügyeletét és telepítését teszi lehetővé. [Mobilalkalmazás-felügyeleti szabályzatokat](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) is társíthat [kompatibilis alkalmazásokhoz](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx), és ellenőrizheti az alkalmazások állapotát a felügyeleti konzolon.<br /><br />A felügyelt iOS-alkalmazásokat nem tárolja az Intune felhőbeli tárhelye.
> [!TIP] A mobileszközökre vonatkozó beállítások csak azt követően válnak elérhetővé, hogy a [Mobileszköz-kezelő szolgáltató megadása beállítást](get-ready-to-enroll-devices-in-microsoft-intune.md) az Intune-ra állította.

## Az univerzális Windows-platformra épülő alkalmazások támogatása
A Windows 10-es számítógépekre közvetlen telepítésre szolgáló kulcs nélkül is telepíthetők az üzletági alkalmazások. A közvetlen telepítés azonban csak akkor lehetséges, ha a **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** beállításkulcs értéke **1**.

Ha nincs konfigurálva ez a beállításkulcs, az Intune automatikusan **1** értékre állítja, amikor először telepítenek egy alkalmazást a szóban forgó eszközre. Amennyiben **0** értékre állította ezt az értéket, az Intune nem tudja azt automatikusan módosítani, ezért sikertelen lesz az üzletági alkalmazások telepítése.

Az univerzális Windows-platformra épülő üzletági alkalmazásokat olyan kódaláíró tanúsítvánnyal kell aláírni, amely megbízhatónak minősül minden olyan eszközön, amelyre telepítik az alkalmazást. Ehhez használhatók a nyilvános kulcsokra épülő belső infrastruktúra tanúsítványai vagy az eszközre telepített, harmadik féltől származó nyilvános főtanúsítvány valamely tanúsítványa.

A Windows 10 Mobile rendszerű eszközökön nem a Symantec által kiállított kódaláíró tanúsítvánnyal is aláírhatók az univerzális **.appx** alkalmazások. Azok a Windows Phone 8.1-es **.xap** alkalmazások és **.appx** csomagok, amelyeket Windows 10 Mobile rendszerű eszközökre kíván telepíteni, csak a Symantec által kiállított kódaláíró tanúsítvánnyal írhatók alá.

## További lépések 

Ezután az alkalmazásokat fel kell vennie az Intune-konzolon, mielőtt telepíthetné őket. A [regisztrált eszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md) vagy [az Intune ügyfélszoftverével felügyelt Windows-számítógépekhez](add-apps-for-windows-pcs-in-microsoft-intune.md) is hozzáadhat alkalmazásokat.


<!--HONumber=Jun16_HO2-->


