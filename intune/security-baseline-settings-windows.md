---
title: Windows biztonsági alapterveket beállítások az Intune-hoz
titleSuffix: Microsoft Intune
description: Windows biztonsági Alapterv beállítások suported Intune-nal
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2dce0b743cd2944569e19a8106327f6735b1d6b
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231706"
---
# <a name="windows-security-baseline-settings-for-intune"></a>Windows biztonsági Alapterv beállítások az Intune-hoz  

Nézet a [Windows biztonsági Alapterv beállítások](security-baselines.md) , amely a Microsoft Intune által támogatott.  

> [!NOTE]  
> A Windows biztonsági Alapterv beállítások vannak előzetes verzióban érhető el. Az előzetes verzió, a rendelkezésre álló beállítások, valamint a sorrendet, amelyben ez a tartalom megadja ezeket a beállításokat listája gyártmányától mi érhető el a portálon.  
>  
> Amikor alapvető beállítások verziója, ezt a tartalmat a rendszer ekkor frissíti a biztonsági alapkonfiguráció beállítások az Intune által támogatott-az előzetes verzió listájában.  

## <a name="above-lock"></a>Zárolási felett  
További információkért lásd: [házirend CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) a Windows dokumentációjában.  

- **Bejelentési értesítések megjelenítésének letiltása**  
  Ez a házirend-beállítással megakadályozhatja, hogy a zárolási képernyőn megjelenő alkalmazás értesítéseit. Ha ez a szabályzatbeállítás engedélyezi, nem alkalmazásbeli értesítések jelennek meg a zárolási képernyőn. Ha letiltja vagy nem konfigurálja ezt a beállítást, felhasználók eldönthetik, hogy mely alkalmazások jelenít meg értesítéseket, a zárolási képernyőn.
  - **Alapértelmezett**: Igen  

## <a name="app-runtime"></a>Alkalmazás-modul    
További információkért lásd: [házirend CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) a Windows dokumentációjában.  

- **Windows Store apps esetén nem kötelező Microsoft-fiókok**  
  Ez a házirend-beállítással szabályozhatja, hogy Microsoft-fiókok megadása nem kötelező, jelentkezzen be a fiók szükséges Windows Store-alkalmazások. Ez a szabályzat csak az azt támogató Windows Store apps van hatással. Ha ez a szabályzatbeállítás engedélyezi, amely általában egy Microsoft-fiókkal való bejelentkezéshez szükséges Windows Store apps segítségével a felhasználók ehelyett jelentkezzen be vállalati fiók. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználóknak kell Microsoft-fiókkal.  
  - **Alapértelmezett**: Engedélyezve  

## <a name="application-management"></a>Alkalmazáskezelés   
További információkért lásd: [házirend CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) a Windows dokumentációjában.  

- **Játékvideó letiltása (csak asztali verzió)**  
  Annak konfigurálása, rögzítése és közvetítése játékok engedélyezett-e.
  - **Alapértelmezett**: Igen  

## <a name="auto-play"></a>Automatikus lejátszás   
További információkért lásd: [házirend CSP - lejátszás](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay
) a Windows dokumentációjában.  

- **Automatikus lejátszás alapértelmezett automatikus futtatási viselkedés**  
  Ez a beállítás hatással van az alapértelmezett viselkedést automatikus futtatási parancsok. Automatikus futtatási parancsok autorun.inf fájlokban van tárolva, és programokat vagy más módon indíthatja el. Amikor *engedélyezve*, a rendszergazdák módosíthatják az alapértelmezett automatikus futtatási viselkedés egy eszközön, amelyen a Windows Vista vagy újabb. Viselkedés értékre lehet beállítani: a) teljesen automatikus futtatási parancsok letiltja, vagy (b) térhet vissza a korábbi Windows Vista működése automatikusan a futtatási parancs végrehajtása. Ha a beállítása *letiltott* vagy *nincs konfigurálva*, Windows Vista rendszerű eszközök, vagy később kérdezzen rá, hogy a felhasználó egy automatikus futtatási parancs futtatva.
  - **Alapértelmezett**: Nem hajtható végre  
  
- **Automatikus lejátszás üzemmódban**  
  A házirend-beállítás lehetővé teszi, hogy az automatikus lejátszás szolgáltatás kikapcsolása. Automatikus lejátszás megkezdi az adatok egy meghajtóról, amint helyezze adathordozót a meghajtóba. Ennek eredményeképpen a telepítőfájl a programok és a music hanganyag azonnali indítása. Windows XP SP2-t előtt automatikus lejátszás a cserélhető meghajtók, például a hajlékonylemez-meghajtó (de nem a CD-ROM-meghajtó) és a hálózati meghajtókon lévő alapértelmezés szerint le van tiltva. Windows XP SP2 verziótól kezdődően automatikus lejátszás engedélyezve van a cserélhető meghajtók, például a Zip-meghajtók és a egy USB-háttértár eszközök. Ha ez a szabályzatbeállítás engedélyezi, az automatikus lejátszás, a CD-ROM-ról és a cserélhető adathordozó meghajtó le van tiltva vagy le van tiltva az összes meghajtón. A házirend-beállítás letiltja az automatikus lejátszás további típusú meghajtókon. Ez a beállítás bekapcsolása a meghajtón, amelyen le van tiltva alapértelmezés szerint nem használható. Ha letiltja vagy nem konfigurálja ezt a beállítást, az automatikus lejátszás engedélyezve van. Megjegyezés: A házirend-beállítás jelenik meg a számítógép konfigurációja-és felhasználói konfigurációt. Ha a házirend-beállításokat ütközés lép fel, akkor a házirend-beállítás a számítógép konfigurációja élvez a házirend-beállítás a felhasználói konfigurációt.
  - **Alapértelmezett**: Letiltva

- **Automatikus lejátszás a nem mennyiségi eszközök letiltása**  
  A házirend-beállítás tiltja a lejátszás MTP eszközökhöz, például fényképezőgépek vagy telefonok. Ha ez a szabályzatbeállítás engedélyezi, automatikus lejátszás MTP eszközök például fényképezőgépek vagy telefonok esetén nem engedélyezett. Ha letiltja vagy nem konfigurálja ezt a beállítást, az automatikus lejátszás nem mennyiségi eszközök engedélyezve van.
  - **Alapértelmezett**: Engedélyezve  

## <a name="bitlocker"></a>A BitLocker    
További információkért lásd: [házirend CSP - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) a Windows dokumentációjában.  

- **Bit széfjét a cserélhető meghajtót házirend**  
  A titkosítási módszer vezérlőelemet, és cipher erőssége a házirend-beállítás szolgál. Az a szabályzat határozza meg, hogy a titkosítás a BitLocker titkosítási használó erősségét. Vállalatok előfordulhat, hogy kívánják vezérelni a titkosítás szintjét, a biztonság fokozása érdekében (AES-256-ot az AES-128-nál nagyobb). Ha engedélyezi ezt a beállítást, lesz egy titkosítási algoritmus és a fő erőssége a rögzített adatmeghajtók, operációsrendszer-meghajtók és a cserélhető adatmeghajtók külön-külön konfigurálni. A rögzített és operációs rendszert tartalmazó meghajtókon azt javasoljuk az XTS-AES algoritmus használata. A cserélhető meghajtók használjon AES-CBC 128 bites vagy AES-CBC 256 bites, ha a meghajtó egyéb Windows 10-es, 1511-es vagy újabb rendszert futtató eszközökön használható. A titkosítási mód módosítása nem befolyásolja, ha a meghajtó már titkosítva van, vagy ha a titkosítás folyamatban van. Ebben az esetben figyelmen kívül ezt a beállítást.

    - **Titkosítás megkövetelése az írási hozzáférés**
      - **Alapértelmezett**: Igen  

    - **Titkosítási módszer**
      - **Alapértelmezett**: AES 256bit CBC  

- **Rögzített meghajtó házirend bit széfjének**  
  A titkosítási módszer vezérlőelemet, és cipher erőssége a házirend-beállítás szolgál. Az a szabályzat határozza meg, hogy a titkosítás a BitLocker titkosítási használó erősségét. Vállalatok előfordulhat, hogy kívánják vezérelni a titkosítás szintjét, a biztonság fokozása érdekében (AES-256-ot az AES-128-nál nagyobb). Ha engedélyezi ezt a beállítást, lesz egy titkosítási algoritmus és a fő erőssége a rögzített adatmeghajtók, operációsrendszer-meghajtók és a cserélhető adatmeghajtók külön-külön konfigurálni. A rögzített és operációs rendszert tartalmazó meghajtókon azt javasoljuk az XTS-AES algoritmus használata. A cserélhető meghajtók használjon AES-CBC 128 bites vagy AES-CBC 256 bites, ha a meghajtó egyéb Windows 10-es, 1511-es vagy újabb rendszert futtató eszközökön használható. A titkosítási mód módosítása nem befolyásolja, ha a meghajtó már titkosítva van, vagy ha a titkosítás folyamatban van. Ebben az esetben figyelmen kívül ezt a beállítást.  
 
  - **Titkosítási módszer**
    - **Alapértelmezett**: AES 256bit XTS  

- **Bit széfjének Rendszerházirend meghajtó**  
  A titkosítási módszer vezérlőelemet, és cipher erőssége a házirend-beállítás szolgál. Az a szabályzat határozza meg, hogy a titkosítás a BitLocker titkosítási használó erősségét. Vállalatok előfordulhat, hogy kívánják vezérelni a titkosítás szintjét, a biztonság fokozása érdekében (AES-256-ot az AES-128-nál nagyobb). Ha engedélyezi ezt a beállítást, lesz egy titkosítási algoritmus és a fő erőssége a rögzített adatmeghajtók, operációsrendszer-meghajtók és a cserélhető adatmeghajtók külön-külön konfigurálni. A rögzített és operációs rendszert tartalmazó meghajtókon azt javasoljuk az XTS-AES algoritmus használata. A cserélhető meghajtók használjon AES-CBC 128 bites vagy AES-CBC 256 bites, ha a meghajtó egyéb Windows 10-es, 1511-es vagy újabb rendszert futtató eszközökön használható. A titkosítási mód módosítása nem befolyásolja, ha a meghajtó már titkosítva van, vagy ha a titkosítás folyamatban van. Ebben az esetben figyelmen kívül ezt a beállítást.  

  - **Titkosítási módszer**  
    - **Alapértelmezett**: AES 256bit XTS  

## <a name="browser"></a>Böngésző  
További információkért lásd: [házirend CSP - böngésző](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) a Windows dokumentációjában.  

- **A Microsoft Edge SmartScreen megkövetelése**  
  A Microsoft Edge felhasználók megvédeni a potenciális adathalászattal és a kártevő szoftverek alapértelmezés szerint a Windows Defender SmartScreen (bekapcsolva) használja. Továbbá alapértelmezés szerint felhasználók nem tiltható le (kapcsolja ki) a Windows Defender SmartScreen. A szabályzat engedélyezése a Windows Defender SmartScreen kikapcsolja, és megakadályozza, hogy a felhasználók ne tudják bekapcsolni a. Ne konfigurálja ezt a házirendet, hogy a felhasználó, hogy a Windows defender SmartScreen engedélyezése vagy letiltása.  
  - **Alapértelmezett**: Igen  
  
- **Rosszindulatú webhelyelérés letiltása**  
  Alapértelmezés szerint a Microsoft Edge lehetővé teszi a felhasználók kihagyhatják (figyelmen kívül hagyása) a Windows Defender SmartScreen-figyelmeztetések potenciálisan rosszindulatú webhelyekről, lehetővé téve számukra az, hogy a hely. Az ehhez a szabályzathoz, konfigurálhatja a Microsoft Edge megakadályozza, hogy a felhasználók a figyelmeztetések mellőzése letiltják őket a továbbra is a hely.
  - **Alapértelmezett**: Igen  
  
- **Ellenőrizetlen fájlletöltés letiltása**  </br>
  Alapértelmezés szerint a Microsoft Edge lehetővé teszi a felhasználók kihagyhatják (figyelmen kívül hagyása) a Windows Defender SmartScreen-figyelmeztetések potenciálisan kártékony fájlokkal, lehetővé teheti, hogy továbbra is a nem ellenőrzött fájlok letöltésével kapcsolatos. E szabályzat engedélyezésével megakadályozza, hogy felhasználók letiltják őket a nem ellenőrzött fájlok letöltése a figyelmeztetések mellőzése.
  - **Alapértelmezett**: Igen  
  
- **Jelszókezelő letiltása**  </br>
  Alapértelmezés szerint a Microsoft Edge jelszókezelő automatikusan használja, így a felhasználók helyi manager jelszavak. Jelszókezelő használatával a Microsoft Edge letiltja ezt a szabályzatot korlátozza. Ne konfigurálja ezt a házirendet, ha azt szeretné, hogy a felhasználók menteni, és jelszavak használatával helyben jelszókezelő kezelése.
  - **Alapértelmezett**: Igen  
  
- **Tanúsítvány hiba felülbírálások megakadályozása**  </br>
  A házirend-beállítás megakadályozza, hogy a felhasználó Secure Sockets Layer/Transport Layer Security (SSL/TLS) tanúsítványt hibák működését zavaró, az Internet Explorer programban (mint például a "lejárt", "Visszavonva" vagy "neve tér" hibák) böngészés figyelmen kívül hagyásával. Ha ez a szabályzatbeállítás engedélyezi, a felhasználó böngészés nem folytatható. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználó választhat figyelmen kívül a hitelesítési hibák, és folytassa a böngészést.
  - **Alapértelmezett**: Igen  

## <a name="connectivity"></a>Kapcsolat  
További információkért lásd: [házirend CSP - kapcsolat](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) a Windows dokumentációjában.  

- **Közzététel a weben és internetes rendelés varázsló blokk internetes letöltés**  
  A házirend-beállítás megadja a Windows letöltse-e a webes közzététel és az Internetes rendelés varázsló szolgáltatók listáját. Ezek a varázslók engedélyezése a felhasználók számára, például az online tárhelyen és photographic nyomtatási szolgáltatásokat nyújtó cégek listájából válassza ki. Alapértelmezés szerint a Windows a beállításjegyzékben megadott szolgáltatók mellett egy Windows webhelyéről letöltött szolgáltatókat jelenít meg. Ha ez a szabályzatbeállítás engedélyezi, a Windows nem tölt le szolgáltatókat, és csak a lettek gyorsítótárazva, a helyi beállításjegyzékben szolgáltatók jelennek meg. Ha letiltja vagy nem konfigurálja ezt a beállítást, a szolgáltatók listáját, amikor a felhasználó használja a webes közzététel vagy az Internetes rendelés varázsló letöltődik. Részletes információk megadása a szolgáltatók a beállításjegyzékben a további információkért lásd: a dokumentáció a webes közzététel és az Internetes rendelés varázsló számára.  
  - **Alapértelmezett**: Engedélyezve  

- **Nyomtatóillesztők HTTP protokollon keresztüli letöltésének letiltása**  
  A házirend-beállítás megadja, hogy az ügyfél nyomtató-illesztőprogram-csomagok letöltése HTTP protokollon keresztül történő engedélyezéséhez. Állítsa be a HTTP-nyomtatás, nem beépített illesztőprogramokat kell HTTP protokollon keresztül tölthetők. Megjegyezés: A házirend-beállítás nem akadályozza meg az ügyfél a nyomtatást az intraneten vagy az interneten nyomtatókhoz HTTP protokollon keresztül. Csak tiltja az illesztőprogramok nem telepített már helyileg letöltését. Ha ez a szabályzatbeállítás engedélyezi, nyomtatóillesztők HTTP protokollon keresztül nem lehet letölteni. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználók letölthetik nyomtatóillesztők HTTP protokollon keresztül.
  - **Alapértelmezett**: Engedélyezve  

## <a name="credentials-delegation"></a>Hitelesítő adatok delegálása  
További információkért lásd: [házirend CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) a Windows dokumentációjában.  

- **Távoli állomás nem exportálható hitelesítő adatok delegálása**  
  Távoli állomás lehetővé teszi, hogy nem exportálható hitelesítő adatok delegálását. Hitelesítő adatok delegálása használatakor az eszközök a távoli gazdagéphez adja meg hitelesítő adatokat egy exportálható verzióját. Ez a távoli gazdagépen a támadók a hitelesítő adatok ellopásának kockázata közzététele felhasználók. Ha ez a szabályzatbeállítás engedélyezi, a gazdagép támogatja a távoli Credential Guard vagy a korlátozott rendszergazdai mód. Ha letiltja vagy nem konfigurálja ezt a beállítást, korlátozott felügyeleti és a távoli Credential Guard mód nem támogatott. Felhasználói mindig kell megadnia a hitelesítő adataikat a gazdagépre.  

  - **Alapértelmezett**: Engedélyezve  

## <a name="credentials-ui"></a>Credentials UI  
További információkért lásd: [házirend CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) a Windows dokumentációjában.  

- **A rendszergazdák számbavétele**    
  Ez a házirend-beállítással megadható, hogy ha egy felhasználó megpróbál egy futó alkalmazás jogosultságszintjének rendszergazdai fiókok jelennek meg. Alapértelmezés szerint rendszergazdai fiókok nem jelennek meg, amikor a felhasználó megpróbál egy futó alkalmazás jogosultságszintjének. Ha ez a szabályzatbeállítás engedélyezi, a számítógép összes helyi rendszergazdai fiókot fog megjelenni, így a felhasználó válasszon egyet, és adja meg a helyes jelszót. Ha letiltja ezt a beállítást, felhasználók mindig kell adjon meg egy felhasználónevet és a jelszó megszerzését.  

  - **Alapértelmezett**: Letiltva  

## <a name="data-protection"></a>Adatvédelem  
További információkért lásd: [házirend CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) a Windows dokumentációjában.  

- **Közvetlen memória-hozzáférés letiltása**   
  A házirend-beállítás lehetővé teszi, hogy, hogy közvetlen memória-hozzáférés (DMA) letiltása az összes gyakran használt adatok moduláris PCI alsóbb rétegbeli port mindaddig, amíg a felhasználó bejelentkezik a Windows. Miután egy felhasználó bejelentkezik, a Windows enumerálnia a PCI-eszköz csatlakozik a gazdagép beépülő PCI portokat. Minden alkalommal, amikor a felhasználó a gép zárolja, DMA le lesz tiltva a gyakori elérésű beépülő PCI portokon gyermekek eszközökkel nem rendelkező mindaddig, amíg a felhasználó újra bejelentkezik. Már enumerálták, amikor a számítógép zárolása fel lett oldva eszközök továbbra is működni, amíg nem választható le. A házirend-beállítás csak akkor lép érvénybe, ha a BitLocker vagy az eszköztitkosítás engedélyezve van.
  
  - **Alapértelmezett**: Igen  

## <a name="device-guard"></a>A Device Guard  
További információkért lásd: [házirend CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) a Windows dokumentációjában.  

- **Credential Guard**  
  Ez a beállítás lehetővé teszi, hogy a felhasználók bekapcsolása a Credential Guard virtualizálás-alapú biztonság a következő rendszerindításkor hitelesítő adatok védelme érdekében.
  
  - **Alapértelmezett**: UEFI-zárolással engedélyezése 

- **A virtualizálás-alapú biztonság engedélyezése**  </br>
  Bekapcsolja a virtualizálás-alapú biztonság (VBS) a következő újraindításkor. A virtualizálás-alapú biztonság a Windows hipervizorral nyújt támogatást biztonsági szolgáltatásokhoz.
  - **Alapértelmezett**: Igen  

<!-- not yet available 
- **Enable secure boot with DMA**  
  Among the commands that follow, you can choose settings for Secure Boot and Secure Boot with DMA. In most situations, we recommend that you choose Secure Boot. This option provides Secure Boot with as much protection as is supported by a given computer’s hardware. A computer with input/output memory management units (IOMMUs) will have Secure Boot with DMA protection. A computer without IOMMUs will simply have Secure Boot enabled. In contrast, with Secure Boot with DMA, the setting will enable Secure Boot—and VBS itself—only on a computer that supports DMA, that is, a computer with IOMMUs. With this setting, any computer without IOMMUs will not have VBS or HVCI protection, although it can still have WDAC enabled.
  
  - **Default**: Yes  
  -->
- **Indítsa el a rendszer őrfeltétel**  
  - **Alapértelmezett**: Engedélyezve  

## <a name="device-installation"></a>Eszköz telepítése  
További információkért lásd: [házirend CSP - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) a Windows dokumentációjában.  

- **A készülékazonosítók hardver eszköz telepítése**  
  A házirend-beállítás lehetővé teszi, hogy adja meg a Plug and Play hardverazonosítók és, hogy Windows rendszer akadályozza eszközökhöz kompatibilis azonosítók listáját. A házirend-beállítás élvez bármely más házirend-beállítás lehetővé teszi, hogy a Windows eszköz telepítése. Ha ez a szabályzatbeállítás engedélyezi, Windows van akadályozza egy eszközt, amelynek hardveres vagy kompatibilis azonosítója megjelenik a listában hoz létre. Ha engedélyezi ezt a beállítást, a távoli asztali kiszolgálón, a házirend-beállítást befolyásolja irányíthassa át a megadott eszközök, a távoli asztali ügyfélhez a távoli asztali kiszolgálónak. Ha letiltja vagy nem konfigurálja ezt a beállítást, eszközök telepíthetők és engedélyezett vagy egyéb házirend-beállítás megakadályozta abban frissíteni.
  - **Alapértelmezett**: Blokk hardveres eszköz telepítése  
  
    - **Megfelelő hardveres eszközök eltávolítása**  
      Ez a beállítás nem érhető el, csak ha *hardveres eszköz telepítése által készülékazonosítók* értékre van állítva *hardveres eszköz telepítést*.
      - **Alapértelmezett**: Igen
  
    - **Hardver eszközök azonosítói nem futtatható**  </br>
      Ez a beállítás nem érhető el, csak ha *hardveres eszköz telepítése által készülékazonosítók* értékre van állítva *hardveres eszköz telepítést*.
      - **Alapértelmezett**: Igen  
  
- **A telepítő osztályok hardveres eszköz telepítése**  
  A házirend-beállítás lehetővé teszi, hogy az eszköz beállítása osztály globálisan egyedi azonosítóra (GUID, hogy Windows rendszer akadályozza az eszközillesztők) egy listában megadhatja a. A házirend-beállítás élvez bármely más házirend-beállítás lehetővé teszi, hogy a Windows eszköz telepítése. Ha ez a szabályzatbeállítás engedélyezi, Windows van ebben az esetben telepítésekor vagy frissítésekor az eszköz-illesztőprogramokat, amelyek osztályát GUID szerepelnek a listán hoz létre. Ha engedélyezi ezt a beállítást, a távoli asztali kiszolgálón, a házirend-beállítást befolyásolja irányíthassa át a megadott eszközök, a távoli asztali ügyfélhez a távoli asztali kiszolgálónak. Ha letiltja vagy nem konfigurálja ezt a beállítást, telepítheti a Windows és a frissítési eszközök engedélyezett, vagy egyéb házirend-beállítás megakadályozza.
  - **Alapértelmezett**: Blokk hardveres eszköz telepítése  
  
    - **Megfelelő hardveres eszközök eltávolítása**  </br>
      Ez a beállítás nem érhető el, csak ha *hardveres eszköz telepítése a telepítő osztályok* értékre van állítva *hardveres eszköz telepítést*.
      - **Alapértelmezett**: *Alapértelmezett konfiguráció nélkül*  
  
    - **Hardver eszközök azonosítói nem futtatható**  </br>
      Ez a beállítás nem érhető el, csak ha *hardveres eszköz telepítése a telepítő osztályok* értékre van állítva *hardveres eszköz telepítést*.
      - **Alapértelmezett**: *Alapértelmezett konfiguráció nélkül*  

## <a name="device-lock"></a>Device Lock  
További információkért lásd: [házirend CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) a Windows dokumentációjában.  

- **Kamera használatának megakadályozása**  
  Letilthatja a zárolási képernyő kamera váltógomb kapcsolót a számítógép beállításait, és megakadályozza, hogy a fényképezőgép a zárolási képernyőn elindításának. Alapértelmezés szerint a felhasználók engedélyezhetik a zárolási képernyőn egy elérhető kamera lett meghívva. Ha engedélyezi ezt a beállítást, a felhasználók többé nem fognak tudni engedélyezése vagy letiltása a zárolási képernyő kamera-hozzáférés a PC-beállítások, és a kamera nem hívható meg a zárolási képernyőn.  
  - **Alapértelmezett**: Engedélyezve  

- **Jelszó kérése**  
  Itt adhatja meg, hogy engedélyezve van-e az eszköz zárolása.
  - **Alapértelmezett**: Igen  
  
  - **Jelszó minimális karakterkészlet száma**  
    Összetett elemtípusok (kis-és nagybetűk, számok és központozási), erős PIN-kód vagy jelszó szükséges számát. PIN-kód kikényszeríti a következő viselkedés, asztali és mobil eszközökhöz: 1 – számjegyek csak 2 - számokat és kisbetűket szükséges 3 - kisbetűk, számjegyek és nagybetűk szükség. Az asztali Microsoft-fiókok és a tartományi fiókok nem támogatott. 4 – számjegy, kisbetűk, nagybetűk és speciális karakterek szükség. Nem támogatott a desktopban. Az alapértelmezett érték az 1. 
    - **Alapértelmezett**: 3  
  
  - **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat**  
    Megengedett, mielőtt az eszköz törlődik a hitelesítési hibák száma. A 0 érték letiltja az eszköz törlési funkciót.
    - **Alapértelmezett**: 10  
  
  - **Jelszó lejárata (nap)**  
    A maximális jelszó kora házirend-beállítás meghatározza, hogy az időszakot (napokban), amely egy jelszót is lehet használni, mielőtt a rendszer a felhasználónak a módosításhoz. Beállíthatja a jelszavak lejárnak egy 1 és 999 közötti napok számát, vagy megadhatja, hogy jelszavuk Sose járjon le a napok számát állítsa 0-ra. Ha jelszó maximális kora 1 és 999 nap közötti, a jelszó minimális kora jelszó maximális kora kisebbnek kell lennie. Ha a jelszó maximális kora 0 értékre van állítva, a jelszó minimális kora 0 és 998 nap között bármilyen érték lehet.
    - **Alapértelmezett**: 60  
  
  - **Kötelező jelszótípus**  
    Határozza meg a PIN-kód vagy jelszó megadása kötelező.
    - **Alapértelmezett**: Alfanumerikus karakterek  
  
  - **Jelszó minimális hossza**  
    A minimális jelszó hossza házirend-beállítás meghatározza, hogy legalább hány karakterből kell állnia egy felhasználói fiók jelszavát is alkotó. Beállíthatja a egy értéke 1 és 14 karakter között, vagy hozhat létre, hogy a karakterek száma 0-ra állításával jelszavát nem szükséges.
    - **Alapértelmezett**: 8  
  
  - **Egyszerű jelszavak blokkolása**  
    Itt adhatja meg, hogy a PIN-kód vagy jelszó például a "1111" vagy "1234" engedélyezettek. Az asztal a képjelszavak használatát is meghatározza.
    - **Alapértelmezett**: Igen  
       *Igen, egy beállítás megakadályozza, hogy az egyszerű jelszavak használatát.* 

  - **Korábbi jelszavak újbóli használatának tiltása**  
    Itt adhatja meg, hány jelszó tárolható az előzményeket, amely nem használható. Az érték a felhasználó jelenlegi jelszavának tartalmazza. Ez azt jelenti, hogy a egy értéke 1 a felhasználó nem használhat újra az aktuális jelszó egy új jelszó beállítása közben kiválasztásakor *5* azt jelenti, hogy a felhasználó nem állíthatja be az új jelszóval való a jelenlegi jelszavát, illetve bármely az előző négy a jelszavakat.
    - **Alapértelmezett**: 24  

- **Diavetítés megakadályozása**  
  Letiltása a zárolási képernyő diavetítés beállításai a számítógép beállításait, és megakadályozza, hogy Diavetítés lejátszása a zárolási képernyőn. Alapértelmezés szerint a felhasználók engedélyezhetik a diavetítés, akkor zárolja a gép után fog futni. Ha engedélyezi ezt a beállítást, felhasználók már nem tudja módosítani a gépház diavetítés beállításait, és nincs diavetítés minden eddiginél indul.
  - **Alapértelmezett**: Engedélyezve  
    *Engedélyezett beállítás megakadályozza, hogy a diavetítések futását.* 

- **Jelszó minimális kora napokban**  
  A minimális jelszó kora házirend-beállítás határozza meg azt a időszakot (napokban), amely egy jelszónak kell lennie, mielőtt a felhasználó módosíthatná. Beállíthat egy 1 és 998 nap közötti értéket, vagy közvetlenül engedélyezheti a jelszó módosítására a napok száma 0-ra állításával. A jelszó minimális kora kisebbnek kell lennie a jelszó maximális kora, kivéve, ha a jelszó maximális kora értéke 0, amely azt jelzi, hogy jelszavuk Sose járjon le. Jelszó maximális kora értéke 0, ha a jelszó minimális kora 0 és 998 között bármilyen érték lehet állítani.
  - **Alapértelmezett**: 1  

## <a name="event-log-service"></a>Event Log Service  
További információkért lásd: [házirend CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) a Windows dokumentációjában.  

- **Biztonsági napló maximális mérete KB-ban**  
  A házirend-beállítás meghatározza a naplófájl maximális méretét kilobájtban. Ha engedélyezi ezt a beállítást, konfigurálhatja a naplófájl maximális mérete 1 megabájt (1024 kilobájt) és 2 terabájt (2147483647 kilobájt) kilobájtoktól a petabájtokig lépésekben kell esnie. Ha letiltja vagy nem konfigurálja ezt a beállítást, a naplófájl maximális méretét a helyileg konfigurált értékre állítani. A helyi rendszergazda, a napló tulajdonságai párbeszédpanelen módosíthatja ezt az értéket, és a rendszer alapértelmezés szerint 20 MB.
  - **Alapértelmezett**: 196608  

- **Rendszernapló fájl maximális mérete KB-ban**  
  A házirend-beállítás meghatározza a naplófájl maximális méretét kilobájtban. Ha engedélyezi ezt a beállítást, konfigurálhatja a naplófájl maximális mérete 1 megabájt (1024 kilobájt) és 2 terabájt (2147483647 kilobájt) kilobájtoktól a petabájtokig lépésekben kell esnie. Ha letiltja vagy nem konfigurálja ezt a beállítást, a naplófájl maximális méretét a helyileg konfigurált értékre állítani. A helyi rendszergazda, a napló tulajdonságai párbeszédpanelen módosíthatja ezt az értéket, és a rendszer alapértelmezés szerint 20 MB.
  - **Alapértelmezett**: 32768  

- **Alkalmazás log fájl maximális mérete KB-ban**  
  A házirend-beállítás meghatározza a naplófájl maximális méretét kilobájtban. Ha engedélyezi ezt a beállítást, konfigurálhatja a naplófájl maximális mérete 1 megabájt (1024 kilobájt) és 2 terabájt (2147483647 kilobájt) kilobájtoktól a petabájtokig lépésekben kell esnie. Ha letiltja vagy nem konfigurálja ezt a beállítást, a naplófájl maximális méretét a helyileg konfigurált értékre állítani. A helyi rendszergazda, a napló tulajdonságai párbeszédpanelen módosíthatja ezt az értéket, és a rendszer alapértelmezés szerint 20 MB.
  - **Alapértelmezett**: 32768  

## <a name="experience"></a>Élmény  
További információkért lásd: [házirend CSP - élmény](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) a Windows dokumentációjában.  

- **Windows reflektorfény blokkolása**  
  Lehetővé teszi a rendszergazdáknak, hogy kapcsolja ki az összes Windows reflektorfény szolgáltatások - ablak reflektorfény a zárolási képernyő, Windows-tippek a Microsoft fogyasztói funkciók, és az egyéb kapcsolódó funkciókat.
  - **Alapértelmezett**: Igen  
  
  - **Harmadik féltől származó javaslatok a Windows Reflektorfényben letiltása**  
    Itt adhatja meg, hogy a külső alkalmazások és tartalmak javaslatok engedélyezése a közzétevők a Windows reflektorfény szolgáltatások, mint például a reflektorfény a zárolási képernyő, a javasolt alkalmazások megjelenítése a Start menübe, és a Windows-tippek. Előfordulhat, hogy továbbra is látnak javaslatok Microsoft szolgáltatások, alkalmazások és szolgáltatások.
     - **Alapértelmezett**: Igen  
  - **Fogyasztói funkciók letiltása**  
    Lehetővé teszi a rendszergazdáknak, hogy kapcsolja be, amelyek jellemzően a fogyasztók számára, például a kezdőképernyőn megjelenő javaslatok, a tagsági értesítések, a Kezdőélmény futtatása után alkalmazás telepítése, és átirányítási csempék.
    - **Alapértelmezett**: Igen  


## <a name="exploit-guard"></a>Biztonsági rés kiaknázása  
További információkért lásd: [házirend CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) a Windows dokumentációjában.  

- **Biztonsági rés kiaknázása elleni védelem XML**  
  Lehetővé teszi a rendszergazda leküldenie egy kívánt rendszer és alkalmazás kockázatcsökkentési beállításokat a szervezet összes eszközre jelölő konfigurációt. A konfigurációs XML képviseli. Biztonsági rés kiaknázása elleni védelem segít vonatkozik eszközök védelme a kártevők, amelyek a biztonsági rések használatával elosztani és fertőznek. A Windows biztonsági alkalmazás vagy a PowerShell használatával létrehozhat egy csoportot (más néven a konfigurációs) megoldások. Ez a konfiguráció exportálása XML-fájlba, majd ossza meg több gépet a hálózaton úgy, hogy az összes ugyanazokat a kockázatcsökkentési beállításokat. Képes konvertálni, és egy meglévő EMET konfigurációs XML-fájl importálása egy biztonsági rés kiaknázása elleni védelem konfigurációs XML-jét.
  - **Alapértelmezett**: *A megadott minta xml* 
 
## <a name="file-explorer"></a>Fájlkezelő  
További információkért lásd: [házirend CSP - fájlkezelő](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) a Windows dokumentációjában.  

- **Adatvégrehajtás-megakadályozási letiltása**  
  Gyakori letiltása bizonyos örökölt beépülő modul alkalmazások nélküli megszakítást Explorer lehetővé teszi.
  - **Alapértelmezett**: Letiltva  
   
- **Sérülés blokk halommemória-lezárás**  
  Halommemória-lezárás sérülés letiltása bizonyos örökölt beépülő modul alkalmazások Explorer leállítása nélkül, azonnal működni engedélyezheti, bár Explorer továbbra is felmondhatja váratlanul később.
  - **Alapértelmezett**: Letiltva  
    

## <a name="internet-explorer"></a>Internet Explorer  
További információkért lásd: [házirend CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) a Windows dokumentációjában.  
<!-- not yet available 
- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  - **Default**: Disabled  
  
- **Office apps launch child process type**  
  Office apps will not be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  - **Default**: Disable  
  
- **Defender sample submission consent type**  
  Checks for the user consent level in Windows Defender to send data. If the required consent has already been granted, Windows Defender submits them. If not (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  - **Default**: Disable  
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  - **Default**: Disabled  
 -->
- **Az Internet Explorer internetes zóna hozzáférést az adatforrásokhoz**  
  Ez a házirend-beállítással kezelheti, hogy az Internet Explorer érhessék el az adatokat a Microsoft XML Parser (MSXML) vagy ActiveX Data Objects (ADO) használatával egy másik biztonsági zónából. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók betölthetnek egy oldal, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez a zónában. Kérdés a legördülő mezőben válassza ki, ha a rendszer megkérdezi a felhasználókat, döntse el, hogy egy oldalon kell betölteni a zónában, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez. Ha letiltja ezt a beállítást, a felhasználók nem tudják betölteni egy oldal, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez a zónában. Ha nem konfigurálja ezt a beállítást, a felhasználók nem tudják betölteni egy oldal, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez a zónában.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna tartalom húzza az eltérő tartományokban időkereten belül**  
  A házirend-beállítás lehetővé teszi a húzással tartalom egyik tartományból egy másik tartományba Ha a forrás- és ugyanabban az ablakban beállításainak megadása. Ha engedélyezi ezt a házirend-beállítást, és kattintson az engedélyezés, felhasználók húzhatja tartalom egyik tartományából egy másik tartományba, ha a forrás- és a rendszer ugyanabban az ablakban. Felhasználók nem módosíthatják ezt a beállítást. Ha engedélyezi ezt a házirend-beállítást, és kattintson a Letiltás elemre, felhasználók nem húzható tartalom egyik tartományából egy másik tartományba, ha a forrás- és a rendszer ugyanabban az ablakban. Felhasználók nem módosíthatják ezt a beállítást az Internetbeállítások párbeszédpanelt. Az Internet Explorer 10 Ha ezt a beállítást letiltja vagy nem konfigurálja, felhasználók nem húzható tartalom egyik tartományából egy másik tartományba Ha a forrás- és ugyanabban az ablakban. A felhasználók módosíthatják ezt a beállítást az Internetbeállítások párbeszédpanelt. Az Internet Explorer 9 és korábbi verzióiban Ha ezt a beállítást letiltja vagy nem konfigurálja, felhasználók húzza tartalom egyik tartományból egy másik tartományba Ha a forrás- és ugyanabban az ablakban. Felhasználók nem módosíthatják ezt a beállítást az Internetbeállítások párbeszédpanelt.
  - **Alapértelmezett**: Letiltva
  
- **Az Internet Explorer tanúsítvány cím eltérés figyelmeztetés**  
  A házirend-beállítás lehetővé teszi, hogy kapcsolja be a tanúsítvány cím eltérő biztonsági figyelmeztetést. Ha a házirend-beállítás be van kapcsolva, a rendszer figyelmezteti a felhasználót szolgálhassanak HTTP Secure (HTTPS) webhelyek a jelenlegi, egy másik webhely címét kiállított tanúsítványok. Ez a figyelmeztetés megakadályozható, hogy olyan hamisítási támadásokat. Ha ez a szabályzatbeállítás engedélyezi, a tanúsítvány cím eltérés figyelmeztetés mindig megjelenik. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználó dönthet úgy, hogy megjelenik-e a tanúsítvány cím eltérés figyelmeztetés (a Speciális lap használatával az Internet Vezérlőpult).
  - **Alapértelmezett**: Engedélyezve 
  
- **Az Internet Explorer korlátozott zóna kevesebb jogosultsággal rendelkező helyek**  
  Ez a házirend-beállítással kezelheti, hogy kevesebb jogosultsággal rendelkező zónák, internetes webhelyekre, például a webhelyek navigálni a zóna. Ha ez a szabályzatbeállítás engedélyezi, kevesebb jogosultsággal rendelkező zónákban lévő webhelyekről nyissa meg az új windows vagy is ebbe a zónába lépjen. A biztonsági zóna a biztonsági réteggel is a zóna jogosultságszint-emelési biztonsági funkció védelmet által biztosított nélkül fog futni. Kérdés választja a legördülő mezőben, ha a rendszer figyelmezteti a felhasználót, hogy potenciálisan veszélyes navigációs arra készül, hogy történnek. Ha letiltja ezt a beállítást, a potenciálisan veszélyes műveleteket ebben az esetben. Az Internet Explorer biztonsági szolgáltatása lesz az ebben a zónában a zóna jogosultságszint-emelési szolgáltatásvezérlő Protection által beállított. Ha nem konfigurálja ezt a beállítást, a potenciálisan veszélyes műveleteket ebben az esetben. Az Internet Explorer biztonsági szolgáltatása lesz az ebben a zónában a zóna jogosultságszint-emelési szolgáltatásvezérlő Protection által beállított.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna automatikus kérése fájl letöltése**  </br>
  A házirend-beállítás határozza meg, hogy a rendszer kérni fogja a fájl nem felhasználó által kezdeményezett letöltéseket. Ezt a beállítást, függetlenül a felhasználók kapnak a fájl letöltése párbeszédpanel letöltéseit felhasználó által kezdeményezett. Ha engedélyezi ezt a beállítást, a felhasználók kapnak a fájl letöltése párbeszédpanel automatikus letöltési kísérletek. Ha letiltja vagy nem konfigurálja ezt a beállítást, a letöltéseket, amelyek nem felhasználó által kezdeményezett le lesz tiltva, és felhasználók az értesítési sávban helyett a fájl letöltése párbeszédpanel jelenik meg. Felhasználók ezután kattintson az értesítési sávban, hogy a fájl letöltése használatával.
  - **Alapértelmezett**: Letiltva
  
- **Az Internet Explorer internetes zóna .NET-keretrendszer tartománybeli összetevők**  
  Ez a házirend-beállítással kezelheti, hogy a .NET-keretrendszer összetevők, az Authenticode aláírással nem rendelkező hajthat végre az Internet Explorer. Ezen összetevők közé tartozik egy objektum címke és a egy hivatkozást a hivatkozott felügyelt végrehajtható fájlok a hivatkozott felügyelt szabályozza. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer végrehajtja a aláíratlan felügyelt összetevőket. Kérdés a legördülő mezőben válassza ki, ha az Internet Explorer kéri a felhasználó határozza meg, hogy végrehajtásához előjel nélküli felügyelt összetevőket. Ha letiltja ezt a beállítást, az Internet Explorer nem hajtható végre aláíratlan felügyelt összetevőket. Ha nem adja meg a házirend-beállítás, az Internet Explorer végrehajtja a aláíratlan felügyelt összetevőket.
  - **Alapértelmezett**: Letiltás 
  
- **Az Internet Explorer internetes zóna engedélyezése csak a jóváhagyott tartományok tdc ActiveX-vezérlők használata**  </br>
  A házirend-beállítás szabályozza-e a felhasználó számára engedélyezett futtatása a webhelyeken a TDC ActiveX-vezérlőt. Ha ez a szabályzatbeállítás engedélyezi, a websites, a zóna nem futtatható a TDC ActiveX-vezérlőt. Ha letiltja ezt a beállítást, a TDC Active X-vezérlés a zónában lévő összes webhelyről fog futni.
  - **Alapértelmezett**: Engedélyezve 
  
- **Az Internet Explorer korlátozott zóna parancsfájl indított windows**  
  A házirend-beállítás lehetővé teszi, hogy korlátozásokat előugró ablakok parancsfájl által kezdeményezett, és a title és az állapot sávok tartalmazó windows kezelheti. Ha ez a szabályzatbeállítás engedélyezi, a Windows korlátozások security nem érvényesül ebben a zónában. A biztonsági zónában, ez a szolgáltatás által biztosított biztonsági réteggel nélkül futtatja. Ha letiltja ezt a beállítást, a parancsfájl által kezdeményezett előugró ablakok és a title és az állapot sávok tartalmazó windows lehetséges káros műveleteket nem lehet futtatni. Az Internet Explorer biztonsági szolgáltatása lesz az ebben a zónában által a Windows biztonsági korlátozások parancsfájlalapú funkció vezérlő beállításának. Ha nem konfigurálja ezt a beállítást, a parancsfájl által kezdeményezett előugró ablakok és a title és az állapot sávok tartalmazó windows lehetséges káros műveleteket nem lehet futtatni. Az Internet Explorer biztonsági szolgáltatása lesz az ebben a zónában által a Windows biztonsági korlátozások parancsfájlalapú funkció vezérlő beállításának.
  - **Alapértelmezett**: Letiltva 
  
- **A fájlok feltöltése a kiszolgáló szerepeljen az Internet Explorer az internet zóna helyi elérési útja**  </br>
  A házirend-beállítás szabályozza-e helyi elérési úttal kapcsolatos információkat küldött-e, amikor a felhasználó tölti fel egy fájlt egy HTML-űrlapot. A helyi elérési út adatokat küld, ha néhány információt előfordulhat, hogy véletlenül is megjeleníthetők a kiszolgálóhoz. Például a felhasználó asztali küldött fájlokat tartalmazhat az elérési út részeként a felhasználó nevét. Amikor a felhasználó tölti fel egy fájlt egy HTML-űrlapot, ha ez a szabályzatbeállítás engedélyezi, a rendszer elküldi az elérési út adatokat. Amikor a felhasználó egy HTML-űrlapot egy fájlt tölt, ha letiltja ezt a beállítást, a rendszer eltávolítja az elérési úttal kapcsolatos információkat. Ha nem konfigurálja ezt a beállítást, a felhasználó dönthet úgy, hogy küld-e elérési úttal kapcsolatos információkat, amikor egy fájl egy HTML-űrlaphoz keresztül töltenek. Alapértelmezés szerint az útvonal-információinak zajlik.
  - **Alapértelmezett**: Letiltva 
  
- **Az Internet Explorer fokozott védett módban folyamatok letiltása**  
  A házirend-beállítás meghatározza, hogy a Internet Explorer 11 Ha 64 bites folyamatokat (a nagyobb biztonság), vagy 32 bites folyamatok (a nagyobb kompatibilitás) használjon a fokozottan védett üzemmódban futó Windows 64 bites verziói. Fontos: Egyes ActiveX-vezérlők és eszköztárak előfordulhat, hogy nem érhető el 64 bites folyamatokat használatakor. Ha ez a szabályzatbeállítás engedélyezi, akkor amikor fokozottan védett üzemmód a Windows 64 bites verzióin futó Internet Explorer 11 64 bites fül folyamatai fogja használni. Ha letiltja ezt a beállítást, az Internet Explorer 11 32 bites fül folyamatai készítésére használ a fokozottan védett üzemmód Windows 64 bites verzióiban. Ha nem konfigurálja ezt a beállítást, a felhasználók bekapcsolják ezt a szolgáltatást, és ki az Internet Explorer beállításainak használatával. Ez a funkció alapértelmezés szerint ki van kapcsolva.
  - **Alapértelmezett**: Engedélyezve 
  
- **Az Internet Explorer figyelmen kívül hagyja a tanúsítvánnyal kapcsolatos hiba**  </br>
  A házirend-beállítás megakadályozza, hogy a felhasználó Secure Sockets Layer/Transport Layer Security (SSL/TLS) tanúsítványt hibák működését zavaró, az Internet Explorer programban (mint például a "lejárt", "Visszavonva" vagy "neve tér" hibák) böngészés figyelmen kívül hagyásával. Ha ez a szabályzatbeállítás engedélyezi, a felhasználó böngészés nem folytatható. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználó választhat figyelmen kívül a hitelesítési hibák, és folytassa a böngészést.
  - **Alapértelmezett**: Letiltva 
  
- **Az Internet Explorer internetes zóna betöltése XAML-fájlok**  
  Ezzel a szabályzatbeállítással kezelése Extensible Application Markup Language (XAML) a fájlok betöltését teszi lehetővé. XAML egy XML-alapú deklaratív jelölőnyelv gazdag felhasználói felületek és a grafikai, amelyek kihasználják a Windows Presentation Foundation létrehozása gyakran használják. Ha engedélyezi ezt a házirend-beállítást, és állítsa be a legördülő listában annak érdekében, XAML fájlok automatikusan betöltődnek az Internet Explorerben. A felhasználó nem módosíthatja ezt a viselkedést. Kérdés beállította a legördülő listából, ha a felhasználó a rendszer XAML fájlok betöltése. Ha letiltja ezt a beállítást, XAML-fájlok nincsenek betöltve az Internet Explorerben. A felhasználó nem módosíthatja ezt a viselkedést. Ha nem konfigurálja ezt a beállítást, a felhasználó eldöntheti XAML betölteni az Internet Explorerben.
  - **Alapértelmezett**: Letiltás 
  
- **Az Internet Explorer internetes zóna automatikus kérdés fájl letöltése**  </br>
  A házirend-beállítás határozza meg, hogy a rendszer kérni fogja a fájl nem felhasználó által kezdeményezett letöltéseket. Ezt a beállítást, függetlenül a felhasználók kapnak a fájl letöltése párbeszédpanel letöltéseit felhasználó által kezdeményezett. Ha engedélyezi ezt a beállítást, a felhasználók kapnak a fájl letöltése párbeszédpanel automatikus letöltési kísérletek. Ha letiltja vagy nem konfigurálja ezt a beállítást, a letöltéseket, amelyek nem felhasználó által kezdeményezett le lesz tiltva, és felhasználók az értesítési sávban helyett a fájl letöltése párbeszédpanel jelenik meg. Felhasználók ezután kattintson az értesítési sávban, hogy a fájl letöltése használatával.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer korlátozott zóna biztonsági figyelmeztetés a potenciálisan nem biztonságos fájlok**  
  A házirend-beállítás szabályozza-e a "Nyissa meg a fájl – biztonsági figyelmeztetés" üzenet jelenik meg, ha a felhasználó megpróbálja megnyitni a végrehajtható fájlok vagy más potenciálisan nem biztonságos fájlok (az intranetes a Fájlkezelővel, például fájlmegosztások). Ha engedélyezi ezt a házirend-beállítást, és állítsa be a legördülő listában annak érdekében, ezek a fájlok nyissa meg a biztonsági figyelmeztetés nélkül. Ha a legördülő listából a kérdés, biztonsági figyelmeztetés jelenik meg, a fájlok megnyitása előtt. Ha letiltja ezt a beállítást, nyissa meg ezeket a fájlokat. Ha nem konfigurálja ezt a beállítást, a felhasználó konfigurálhat a fájlok kezelésének. Alapértelmezés szerint ezeket a fájlokat a Tiltott helyek zónához, az intranetes és a helyi számítógép zónában, engedélyezve van a blokkolt és állítsa be az Internet és megbízható zónában kéréséhez.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer az internet zóna keresztszűrő hely parancsfájl-kezelési**  
  Ez az irányelv szabályozza-e a többhelyes parancsfájl-kezelési (XSS) szűrő érzékeli, és webhelyek ebben a zónában, a webhelyközi parancsprogramot injektálások megakadályozása. Ha ez a szabályzatbeállítás engedélyezi, a XSS szűrő zónában is engedélyezve van, és a XSS-szűrő megpróbálja webhelyközi parancsprogramot injektálások letiltása. Ha letiltja ezt a beállítást, a XSS szűrő ki van kapcsolva a zónában, és az Internet Explorer lehetővé teszi a webhelyközi parancsprogramot injektálások.
  - **Alapértelmezett**: Engedélyezve 
  
- **Az Internet Explorer tartalék SSL3**  
  A házirend-beállítás lehetővé teszi, hogy egy nem biztonságos tartalék SSL 3.0 letiltása. Ha ez a szabályzat engedélyezve van, az Internet Explorer megkísérli SSL 3.0-t használó helyek vagy alatt, ha sikertelen a TLS 1.0-s vagy nagyobb. Azt javasoljuk, hogy nincs engedélyezve a biztonságos tartalék a man-in-the-middle támadások megelőzése érdekében. Ez a szabályzat nem befolyásolja, mely biztonsági protokollok engedélyezettek. Ha letiltja ezt a házirendet, a rendszer alapértelmezett értékeket fogja.
  - **Alapértelmezett**: Nincsenek helyek 
  
- **Az Internet Explorer, az internet zóna intelligens képernyő zárolva**  
  Ez a házirend-beállítással megadható, hogy a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha ez a szabályzatbeállítás engedélyezi, a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha letiltja ezt a beállítást, a SmartScreen szűrő nem ellenőrzi a lapok rosszindulatú zónában. Ha nem konfigurálja ezt a beállítást, a felhasználó választhat megvizsgálja-e a SmartScreen szűrő az oldalakat a rosszindulatú zóna. Megjegyezés: Az Internet Explorer 7 a házirend-beállítás meghatározza, hogy megvizsgálja-e adathalász szűrő oldalak rosszindulatú zónában.
  - **Alapértelmezett**: Engedélyezve 
  
- **Az Internet Explorer korlátozott zóna indítási alkalmazásokat és fájlokat egy IFRAME elembe**  
  Ez a házirend-beállítással kezelheti, hogy futtatható alkalmazások és a egy IFRAME-referencia a HTML-lapok ebben a zónában lévő fájlok letölthetők. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók alkalmazásokat futtathat és IFRAME fájlok letöltése a zónában lévő lapok a felhasználói beavatkozás nélkül. Kérdés választja a legördülő mezőben, ha a rendszer megkérdezi a felhasználókat, hogy az alkalmazások futtatásához és IFRAME fájlok letöltése a zóna oldalain e. Ha letiltja ezt a beállítást, a rendszer megakadályozza a felhasználókat a futó alkalmazások és IFRAME fájlok letöltése a zóna oldalain. Ha nem konfigurálja ezt a beállítást, a rendszer megakadályozza a felhasználókat a futó alkalmazások és fájlok letöltése IFRAME a zónában lévő lapok a.
  - **Alapértelmezett**: Letiltás 
  
- **Az Internet Explorer SmartScreen-figyelmeztetések nem szokványos fájlokkal kapcsolatos megkerülése** a házirend-beállítás azt határozza meg, hogy a felhasználó elkerülheti a SmartScreen szűrő figyelmeztetéseit. A SmartScreen szűrő figyelmezteti a felhasználót a végrehajtható fájlokat, az Internet Explorer felhasználók ne gyakran töltse le az internetről. Ha ez a szabályzatbeállítás engedélyezi, a SmartScreen szűrő figyelmeztetéseit letiltása a felhasználó. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználó elkerülheti a SmartScreen szűrő figyelmeztetéseit.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer internetes zóna előugró ablakok blokkolása**  
  Ez a házirend-beállítással kezelheti, hogy nemkívánatos előugró ablak jelenik meg. Előugró ablakok nyílnak meg, amikor a végfelhasználó egy hivatkozásra kattint, nincs letiltva. Ha ez a szabályzatbeállítás engedélyezi, leggyakrabban nemkívánatos előugró ablakok ebben az esetben jelennek meg. Ha letiltja ezt a beállítást, az előugró windows nem ebben az esetben a parancsot. Ha nem adja meg a házirend-beállítás, leggyakrabban nemkívánatos előugró ablakok ebben az esetben jelennek meg.
  - **Alapértelmezett**: Engedélyezés  
  
- **Az Internet Explorer dolgozza fel a konzisztens MIME-kezelés**  
  Az Internet Explorer tartalmaz dinamikus bináris viselkedéseket: összetevők, amely magába foglalja az adott funkciót a HTML-elemek, amelyhez csatlakozik. Ez a házirend-beállítással megadható, hogy a bináris viselkedés biztonsági korlátozása beállítást. Ebben az esetben, vagy engedélyezett. Ha ez a szabályzatbeállítás engedélyezi, a rendszer letiltja a bináris viselkedést a Fájlkezelőben és az Internet Explorer folyamatokat. Ha letiltja ezt a beállítást, a bináris viselkedéseket a Fájlkezelőben és az Internet Explorer-folyamatokhoz történő használata engedélyezett. Ha letiltja ezt a beállítást, a rendszer letiltja a bináris viselkedést a Fájlkezelőben és az Internet Explorer-folyamatokhoz történő.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer zóna java engedélyei korlátozottak** a házirend-beállítás lehetővé teszi, hogy kisalkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha nem konfigurálja ezt a beállítást, a Java-alkalmazások le vannak tiltva.
  - **Alapértelmezett**: Tiltsa le a java  
    
  
- **Az Internet Explorer Active X-vezérlők védett módban**  
  A házirend-beállítás megakadályozza, hogy az ActiveX-vezérlők védett módban fut, amikor a fokozottan védett üzemmód engedélyezve van. Rendelkező ActiveX-vezérlő telepítve van, amely nem kompatibilis a fokozottan védett üzemmóddal és webhely megkísérli betölteni a vezérlőt, az Internet Explorer értesíti a felhasználót, és lehetőséget ad arra, hogy a webhely rendszeres védett módban fusson. Ezzel a szabályzatbeállítással letiltja ezt az értesítést, és arra kényszeríti az összes webhely futtathat a fokozottan védett üzemmód. Fokozottan védett üzemmód rosszindulatú webhelyekre elleni további védelmet biztosít a 64 bites Windows 64 bites folyamatokat használatával. Vagy újabb rendszert futtató számítógépek Windows 8, a fokozottan védett üzemmóddal is korlátozza a helyeken, az Internet Explorer is olvasható, és a beállításjegyzék és a fájlrendszerhez. Fokozottan védett üzemmód engedélyezve van, és a egy felhasználó olyan webhely, amely megpróbálja az olyan ActiveX-vezérlőt, amely nem kompatibilis a fokozottan védett üzemmóddal fordul elő, ha az Internet Explorer értesíti a felhasználót, és lehetőséget ad arra, hogy a fokozottan védett üzemmód letiltása adott webhely. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer nem biztosít a felhasználó fokozottan védett üzemmód letiltását. Minden védett mód webhelyek fokozottan védett üzemmódban fog futni. Ha letiltja vagy nem konfigurálja ezt a beállítást, az Internet Explorer értesíti a felhasználókat, és futtassa a webhelyek rendszeres védett módban nem kompatibilis ActiveX-vezérlők lehetőséget biztosít. Ez az az alapértelmezett viselkedést.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna betöltése XAML-fájlok**  
  Ezzel a szabályzatbeállítással kezelése Extensible Application Markup Language (XAML) a fájlok betöltését teszi lehetővé. XAML egy XML-alapú deklaratív jelölőnyelv gazdag felhasználói felületek és a grafikai, amelyek kihasználják a Windows Presentation Foundation létrehozása gyakran használják. Ha engedélyezi ezt a házirend-beállítást, és állítsa be a legördülő listában annak érdekében, XAML fájlok automatikusan betöltődnek az Internet Explorerben. A felhasználó nem módosíthatja ezt a viselkedést. Kérdés beállította a legördülő listából, ha a felhasználó a rendszer XAML fájlok betöltése. Ha letiltja ezt a beállítást, XAML-fájlok nincsenek betöltve az Internet Explorerben. A felhasználó nem módosíthatja ezt a viselkedést. Ha nem konfigurálja ezt a beállítást, a felhasználó eldöntheti XAML betölteni az Internet Explorerben.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer parancsfájlalapú ablak biztonsági korlátozások dolgozza fel.**  
  Az Internet Explorer lehetővé teszi a parancsfájlok programozott módon megnyitásához, átméretezése és áthelyezése a windows a különféle fenyegetési típusokat. Az ablak korlátozó biztonsági szolgáltatás korlátozza az előugró ablakok, és megakadályozza, hogy a parancsfájlok, amelyben a title és az állapot sávok nem láthatók a felhasználó számára, vagy más Windows' címet és állapotsorairól rejtse windows megjelenítése. Ha ez a szabályzatbeállítás engedélyezi, parancsfájlalapú windows korlátozza a rendszer az összes folyamat. Ha letiltja vagy nem konfigurálja ezt a beállítást, a windows parancsfájlalapú nem korlátozódnak.
  - **Alapértelmezett**: Engedélyezve   
  
- **Az Internet Explorer korlátozott zóna futtathat ActiveX-vezérlők és beépülő modulok**  
  Ez a házirend-beállítással kezelheti-e az ActiveX-vezérlők és a megadott zónában található modulok is futtatható a lapokon. Ha ez a szabályzatbeállítás engedélyezi, vezérlők és beépülő modulok futtathatók, felhasználói beavatkozás nélkül. A legördülő listában kiválasztott kérése, ha a felhasználók, döntse el, hogy a vezérlőelemek a gyakori vagy a beépülő modul futtatása. Ha letiltja ezt a beállítást, vezérlők és beépülő modulok nem futtathatók. Ha nem adja meg a házirend-beállítás, vezérlők és beépülő modulok nem futtathatók.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna parancsfájl Active X szabályozza biztonságosként megjelölt futtatása**  
  A házirend-beállítás lehetővé teszi, hogy kezelheti, hogy egy parancsfájl kommunikálhatnak a biztonságosként megjelölt ActiveX-vezérlőt. Ha ez a szabályzatbeállítás engedélyezi, parancsfájl interakció automatikusan történik, felhasználói beavatkozás nélkül. Kérdés választja a legördülő mezőben, ha a rendszer megkérdezi a felhasználókat, hogy a parancsfájl beavatkozás engedélyezése e. Ha letiltja ezt a beállítást, parancsfájl van megakadályozza a való együttműködést. Ha nem adja meg a házirend-beállítás, parancsfájl van megakadályozza a való együttműködést.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna bejelentkezési beállítások**  
  Ez a házirend-beállítással kezelheti a bejelentkezési beállításokat. Ha ez a szabályzatbeállítás engedélyezi, az alábbi lehetőségek közül választhat. Névtelen bejelentkezés letiltása a HTTP-hitelesítést, és a Vendég fiók csak a Common Internet File System (CIFS) protokollt használja. Felhasználónév és jelszó kérése tartozó felhasználói azonosítók és jelszavak. Miután egy felhasználó kérdeznek le, ezeket az értékeket használható csendes a munkamenet hátralévő részére. Automatikus bejelentkezés csak az Intranet zónába tartozó felhasználói azonosítók és jelszavak a más zónákban lekérdezés felhasználóinak. Miután egy felhasználó kérdeznek le, ezeket az értékeket használható csendes a munkamenet hátralévő részére. Automatikus bejelentkezés a jelenlegi felhasználónevét és jelszavát: bejelentkezés Windows NT kérdés-válasz (más néven az NTLM-hitelesítés) megkísérlése. Ha a kiszolgáló által támogatott Windows NT kérdés-válasz, a bejelentkezési használja a felhasználó hálózati felhasználónevet és jelszót bejelentkezési. Ha a kiszolgáló által nem támogatott a Windows NT kérdés-válasz, a felhasználó lekérdezése követi, adja meg a felhasználónevet és jelszót. Ha letiltja ezt a beállítást, csak az Intranet zónában bejelentkezési beállítás automatikus bejelentkezésre. Ha letiltja ezt a beállítást, a felhasználónév és jelszó bejelentkezési beállítás kérdés.
  - **Alapértelmezett**: Névtelen  
  
- **Az Internet Explorer megbízható zóna inicializálása és parancsfájl Active X-vezérlők nem biztonságosként megjelölt**  
  Ez a szabályzatbeállítás nem biztonságosként megjelölt ActiveX-vezérlők kezelését teszi lehetővé. Ha ez a szabályzatbeállítás engedélyezi, az ActiveX-vezérlők futnak, betöltött paraméterekkel, és a parancsfájlalapú objektum nem megbízható adatok vagy parancsfájlok biztonságának beállítása nélkül. Ezt a beállítást nem ajánlott, kivéve a biztonságos és felügyelt zónák. A beállítás hatására nem biztonságos, és a biztonságos vezérlők inicializálása és parancsprogrammal létrehozva, a rendszer figyelmen kívül hagyja az ActiveX-vezérlők biztonságosnak lehetőséget. Ha engedélyezi ezt a házirend-beállítást, és a legördülő mezőben válassza ki a kérdés, felhasználók kérdezhető le, hogy a vezérlőelem betöltését paraméterekkel engedélyezi-e, vagy parancsprogram. Ha letiltja ezt a beállítást, ActiveX-vezérlők nem tehető nem paraméterekkel betöltése vagy parancsprogrammal létrehozva. Ha nem konfigurálja ezt a beállítást, a felhasználók kérdezhető le, hogy a vezérlőelem betöltését paraméterekkel engedélyezi-e vagy parancsprogrammal létrehozva.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer ellenőrzés kiszolgálói tanúsítvány-visszavonás**  
  Ez a házirend-beállítással kezelheti-e az Internet Explorer-kiszolgálók tanúsítványok visszavonási állapotát ellenőrzi. Tanúsítványok visszavonódnak, amikor biztonsága sérült, vagy a már nem érvényesek, és érvényességük bizalmas adatokat, amelyek rosszindulatú vagy nem biztonságos helyre küldjön. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer ellenőrzi, ha a kiszolgálói tanúsítványok visszavonták. Ha letiltja ezt a beállítást, az Internet Explorer nem ellenőrzi a kiszolgálói tanúsítványok megtekintéséhez, ha azok visszavonták. Ha nem konfigurálja ezt a beállítást, az Internet Explorer nem ellenőrzi a kiszolgálói tanúsítványok megtekintéséhez, ha azok visszavonták.
  - **Alapértelmezett**: Engedélyezve 
  
- **Az Internet Explorer az internet zóna kevesebb jogosultsággal rendelkező helyek**  
  Ez a házirend-beállítással kezelheti, hogy kevesebb jogosultsággal rendelkező zónák, például a Tiltott helyek, a webhelyek navigálni a zóna. Ha ez a szabályzatbeállítás engedélyezi, kevesebb jogosultsággal rendelkező zónákban lévő webhelyekről nyissa meg az új windows vagy is ebbe a zónába lépjen. A biztonsági zóna a biztonsági réteggel is a zóna jogosultságszint-emelési biztonsági funkció védelmet által biztosított nélkül fog futni. Kérdés választja a legördülő mezőben, ha a rendszer figyelmezteti a felhasználót, hogy potenciálisan veszélyes navigációs arra készül, hogy történnek. Ha letiltja ezt a beállítást, a potenciálisan veszélyes műveleteket ebben az esetben. Az Internet Explorer biztonsági szolgáltatása lesz az ebben a zónában a zóna jogosultságszint-emelési szolgáltatásvezérlő Protection által beállított. Ha letiltja ezt a beállítást, kevesebb jogosultsággal rendelkező zónákban lévő webhelyekről is nyissa meg az új windows, vagy lépjen ebbe a zónába.
  - **Alapértelmezett**: Letiltás  

- **Az Internet Explorer korlátozott zóna fájlletöltések**  </br>
  A házirend-beállítás lehetővé teszi, hogy kezelheti a fájlok letöltése a zónából engedélyezettek-e. Ez a beállítás határozza meg a zónát, az oldal okoz a letöltést, nem a zónában, amelyről a fájl kézbesíti a rendszer a hivatkozást tartalmazó. Ha ez a szabályzatbeállítás engedélyezi, fájlok, a zóna letölthető. Ha letiltja ezt a beállítást, a rendszer megakadályozza a fájlok letöltését a zónából. Ha nem adja meg a házirend-beállítás, fájlokat ebben az esetben a zóna letöltését.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer az internet zóna futtatása a .NET-keretrendszer Authenticode aláírással rendelkező tartománybeli összetevők**  
  Ez a házirend-beállítással kezelheti, hogy a .NET-keretrendszer összetevők, az Authenticode aláírással rendelkező hajthat végre az Internet Explorer. Ezen összetevők közé tartozik egy objektum címke és a egy hivatkozást a hivatkozott felügyelt végrehajtható fájlok a hivatkozott felügyelt szabályozza. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer végrehajtja a aláírt felügyelt összetevőket. Kérdés a legördülő mezőben válassza ki, ha az Internet Explorer kéri a felhasználó határozza meg, hogy aláírt felügyelt összetevőket végrehajtásához. Ha letiltja ezt a beállítást, az Internet Explorer nem hajtható végre aláírt felügyelt összetevőket. Ha nem adja meg a házirend-beállítás, az Internet Explorer nem hajtható végre aláírt felügyelt összetevőket.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer minden felhasználó telepítéshez az ActiveX-vezérlők megakadályozása**  </br>
  Ez a házirend-beállítással megakadályozhatja, hogy a telepítés, az ActiveX-vezérlők, felhasználónkénti alapon. Ha ez a szabályzatbeállítás engedélyezi, az ActiveX-vezérlők nem lehet telepíteni, felhasználónkénti alapon. Ha letiltja vagy nem konfigurálja ezt a beállítást, az ActiveX-vezérlők felhasználónkénti alapon is telepíthető.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer a SmartScreen szűrő kezelésének megakadályozása**  </br>
  A házirend-beállítás megakadályozza, hogy a felhasználó kezelje a SmartScreen szűrő, amely figyelmezteti a felhasználót, ha ismert rosszindulatú kísérletek "adathalász" személyes információt gyűjthet felkeresni a webhelyet, vagy a gazdagép kártevő ismert. Ha ez a szabályzatbeállítás engedélyezi, a rendszer nem kéri a felhasználót, a SmartScreen szűrő bekapcsolására. Az összes webhely címét, amely nem a Szűrő engedélyezése listája automatikusan elküld a Microsoft a felhasználó értesítése nélkül. Ha letiltja vagy nem konfigurálja ezt a beállítást, kéri a felhasználót, hogy az első rendszerindítás során a SmartScreen szűrő bekapcsolására kell-e.
  - **Alapértelmezett**: Engedélyezés  
  
- **Az Internet Explorer MIME elemzés biztonsági szolgáltatás dolgozza fel.**  
  A házirend-beállítás meghatározza, hogy e az Internet Explorer MIME-elemzése megakadályozza, hogy egy adott típusú fájl több veszélyes fájl típusra. Ha ez a szabályzatbeállítás engedélyezi, MIME-elemzése soha nem lépteti elő egy adott típusú fájlt egy több veszélyes fájl típusra. Ha letiltja ezt a beállítást, az Internet Explorer folyamatok lehetővé teszi egy adott típusú fájlt egy több veszélyes fájl típusra való előléptetése másikká. Ha nem adja meg a házirend-beállítás, MIME-elemzése soha nem lépteti elő egy adott típusú fájlt egy több veszélyes fájl típusra.
  - **Alapértelmezett**: Engedélyezve  
  
- **Aláírt ActiveX-vezérlők az Internet Explorer korlátozott zóna letöltése**  </br>
  Ez a házirend-beállítással kezelheti, hogy a felhasználók letölthetnek aláírt ActiveX-vezérlők a zónában lévő oldal. Ha engedélyezi ezt a házirendet, a felhasználók letölthetik aláírt vezérlők felhasználói beavatkozás nélkül. Kérdés a legördülő mezőben válassza ki, ha a felhasználók dönthetik töltse le a nem megbízható közzétevők által aláírt szabályozza-e. Csendes letöltődik a megbízható közzétevők által aláírt kód. Ha letiltja a házirend-beállítást, az aláírt vezérlők nem lehet letölteni. Ha nem konfigurálja ezt a beállítást, a felhasználók dönthetik töltse le a nem megbízható közzétevők által aláírt szabályozza-e. Csendes letöltődik a megbízható közzétevők által aláírt kód.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer automatikus kiegészítés**  </br>
  Az automatikus kiegészítés funkció ne felejtse el és a felhasználónevek és jelszavak űrlapokon javaslat. Ha engedélyezi ezt a beállítást, a felhasználó nem módosíthatja, "felhasználónevet és jelszót" vagy "Rákérdezés is menthetik a jelszavakat". A felhasználónevek és jelszavak űrlapokon a szolgáltatások automatikus teljes lesz kapcsolva. Akkor válassza a "Rákérdezés is menthetik a jelszavakat" kell-e. Ha letiltja ezt a beállítást a nem módosítható az a felhasználó a "felhasználónevet és jelszót" vagy "Rákérdezés is menthetik a jelszavakat". A felhasználónevek és jelszavak űrlapokon automatikus teljes szolgáltatás ki van kapcsolva. A felhasználó még nem tilthatók le is menthetik a jelszavakat kéri. Ha nem konfigurálja ezt a beállítást, a felhasználók számára az, hogy automatikusan teljes felhasználónevet és a jelszavakat a képernyők és kéri a felhasználót, jelszavak mentése egyszerű lehetőséget szabadon. Megjelenítéséhez ezt a beállítást, a felhasználók az Internetbeállítások párbeszédpanel megnyitásához kattintson a tartalom lap és a beállítások gombra.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer az internet zóna VBScript-parancsprogramot futtatni engedélyezése**  </br>
  A házirend-beállítás lehetővé teszi, hogy Ön döntse el, hogy a VBScript futtatható-e az adott Internet Explorer zónákban oldalain. Ha engedélyezi ezt a házirend-beállítást (alapértelmezett), az alábbi lehetőségek közül is az elemet az lehetőségeket kell választania: Engedélyezze a. VBScript lapok adott zónákban, felhasználói beavatkozás nélkül futtatja. Kérni. Az alkalmazottak a rendszer kéri-e, hogy a VBScript-parancsprogramot a zónában. Tiltsa le. VBScript megakadályozta a zóna fut. Ha letiltja vagy nem konfigurálja ezt a beállítást, VBScript parancsfájlt futtat a megadott zónában felhasználói beavatkozás nélkül
  - **Alapértelmezett**: Letiltás  
  
- **Tiltott helyek zónához engedélyezése az Internet Explorer csak a jóváhagyott tartományok tdc ActiveX-vezérlők használata**  </br>
  A házirend-beállítás szabályozza-e a felhasználó számára engedélyezett futtatása a webhelyeken a TDC ActiveX-vezérlőt. Ha ez a szabályzatbeállítás engedélyezi, a websites, a zóna nem futtatható a TDC ActiveX-vezérlőt. Ha letiltja ezt a beállítást, a TDC Active X-vezérlés a zónában lévő összes webhelyről fog futni.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer Megbízható helyek zónájába nem futtathatnak kártevőirtó ActiveX-vezérlők**   </br>
  A házirend-beállítás meghatározza, hogy az Internet Explorer fut-e kártevőirtó-programok ellen ActiveX-vezérlők annak ellenőrzéséhez, hogy azok biztonságos voltát oldalain betölteni. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer nem egyeztessen a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha letiltja ezt a beállítást, az Internet Explorer mindig ellenőrzi a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha nem konfigurálja ezt a beállítást, az Internet Explorer mindig ellenőrzi a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Bármikor ezt a viselkedést be- vagy kikapcsolása az Internet Explorer biztonsági beállításokkal.
  - **Alapértelmezett**: Letiltva 
  
- **Az Internet Explorer helyi gép zóna java-engedélyek**  
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha letiltja ezt a beállítást, az engedély értéke közepes biztonsági.
  - **Alapértelmezett**: Tiltsa le a java 
  
- **Az Internet Explorer intranetes zóna nem futtathatnak kártevőirtó ActiveX-vezérlők**  </br>
  A házirend-beállítás meghatározza, hogy az Internet Explorer fut-e kártevőirtó-programok ellen ActiveX-vezérlők annak ellenőrzéséhez, hogy azok biztonságos voltát oldalain betölteni. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer nem egyeztessen a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha letiltja ezt a beállítást, az Internet Explorer mindig ellenőrzi a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha nem konfigurálja ezt a beállítást, az Internet Explorer nem egyeztessen a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Bármikor ezt a viselkedést be- vagy kikapcsolása az Internet Explorer biztonsági beállításokkal.
  - **Alapértelmezett**: Letiltva  

- **Az Internet Explorer korlátozott zóna Szkriptletek**  
  Ez a házirend-beállítással kezelheti, hogy a felhasználó futtathatja a Szkriptletek. Ha ez a szabályzatbeállítás engedélyezi, akkor a felhasználó Szkriptletek futtathatja. Ha letiltja ezt a beállítást, a felhasználó Szkriptletek nem futtatható. Ha nem konfigurálja ezt a beállítást, a felhasználó engedélyezheti vagy letilthatja a Szkriptletek.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer folyamatok értesítési sáv**  </br>  
  Ez a házirend-beállítással kell kezelni az értesítési sáv jelenik meg az Internet Explorer folyamatok, ha a fájl-vagy kód korlátozva-e. Alapértelmezés szerint az értesítési sáv jelenik meg az Internet Explorer folyamatok. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer folyamatok az értesítési sáv jelenik meg. Ha letiltja ezt a beállítást, az értesítési sávban nem jelennek az Internet Explorer folyamatok. Ha nem adja meg a házirend-beállítás, az Internet Explorer folyamatok az értesítési sáv jelenik meg.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer internetes zóna letöltés aláírt ActiveX-vezérlők**  </br>
  Ez a házirend-beállítással kezelheti, hogy a felhasználók letölthetnek aláírt ActiveX-vezérlők a zónában lévő oldal. Ha engedélyezi ezt a házirendet, a felhasználók letölthetik aláírt vezérlők felhasználói beavatkozás nélkül. Kérdés a legördülő mezőben válassza ki, ha a felhasználók dönthetik töltse le a nem megbízható közzétevők által aláírt szabályozza-e. Csendes letöltődik a megbízható közzétevők által aláírt kód. Ha letiltja a házirend-beállítást, az aláírt vezérlők nem lehet letölteni. Ha nem konfigurálja ezt a beállítást, a felhasználók dönthetik töltse le a nem megbízható közzétevők által aláírt szabályozza-e. Csendes letöltődik a megbízható közzétevők által aláírt kód.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna SmartScreen**  
  Ez a házirend-beállítással megadható, hogy a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha ez a szabályzatbeállítás engedélyezi, a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha letiltja ezt a beállítást, a SmartScreen szűrő nem ellenőrzi a lapok rosszindulatú zónában. Ha nem konfigurálja ezt a beállítást, a felhasználó választhat megvizsgálja-e a SmartScreen szűrő az oldalakat a rosszindulatú zóna. Megjegyezés: Az Internet Explorer 7 a házirend-beállítás meghatározza, hogy megvizsgálja-e adathalász szűrő oldalak rosszindulatú zónában.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer, távolítsa el az elavult ActiveX-vezérlők következő idő gomb futtatására**  </br>
  A házirend-beállítás lehetővé teszi, hogy a felhasználók lássák a "Futtatás most" gomb és az Internet Explorer adott elavult ActiveX-vezérlők futását. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók láthatják a "Futtatás most" gombra a figyelmeztető üzenet jelenik meg, amikor az Internet Explorer blokkolja az elavult ActiveX-vezérlők a. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználók látják a "Futtatás most" gombra a figyelmeztető üzenet jelenik meg, amikor az Internet Explorer blokkolja az elavult ActiveX-vezérlők a. Erre a gombra kattintva lehetővé teszi, hogy a felhasználó egyszeri futtatás a elavult ActiveX-vezérlőt. További információkért lásd: "Elavult ActiveX-vezérlők" az Internet Explorer TechNet könyvtárban.
  - **Alapértelmezett**: Engedélyezve 
  
- **Az Internet Explorer internetes zóna indítási alkalmazásokat és fájlokat egy IFRAME elembe**  
  Ez a házirend-beállítással kezelheti, hogy futtatható alkalmazások és a egy IFRAME-referencia a HTML-lapok ebben a zónában lévő fájlok letölthetők. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók alkalmazásokat futtathat és IFRAME fájlok letöltése a zónában lévő lapok a felhasználói beavatkozás nélkül. Kérdés választja a legördülő mezőben, ha a rendszer megkérdezi a felhasználókat, hogy az alkalmazások futtatásához és IFRAME fájlok letöltése a zóna oldalain e. Ha letiltja ezt a beállítást, a rendszer megakadályozza a felhasználókat a futó alkalmazások és IFRAME fájlok letöltése a zóna oldalain. Ha nem adja meg a házirend-beállítás, megkérdezi a felhasználót, hogy az alkalmazások futtatásához és IFRAME fájlok letöltése a zóna oldalain e
  - **Alapértelmezett**: Letiltás 
  
- **Keresse meg a windows és a keretek az Internet Explorer korlátozott zóna különböző tartományokban**  </br>
  A házirend-beállítás lehetővé teszi a húzással tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows beállításainak megadása. Ha engedélyezi ezt a házirend-beállítást, és kattintson az engedélyezés, felhasználók húzza tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást. Ha engedélyezi ezt a házirend-beállítást, és kattintson a Letiltás elemre, felhasználók nem húzható tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást. Az Internet Explorer 10 Ha ezt a beállítást letiltja vagy nem konfigurálja, felhasználók nem húzható tartalom egyik tartományából egy másik tartományba Ha a forrás- és a különböző windows. A felhasználók módosíthatják ezt a beállítást az Internetbeállítások párbeszédpanelt. Az Internet Explorer 9 és korábbi verzióiban Ha letiltja ezt a házirendet, vagy nem konfigurálja, felhasználók húzhatja tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer internetes zóna SmartScreen**  
  Ez a házirend-beállítással megadható, hogy a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha ez a szabályzatbeállítás engedélyezi, a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha letiltja ezt a beállítást, a SmartScreen szűrő nem ellenőrzi a lapok rosszindulatú zónában. Ha nem konfigurálja ezt a beállítást, a felhasználó választhat megvizsgálja-e a SmartScreen szűrő az oldalakat a rosszindulatú zóna. Megjegyezés: Az Internet Explorer 7 a házirend-beállítás meghatározza, hogy megvizsgálja-e adathalász szűrő oldalak rosszindulatú zónában.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer Megbízható helyek zónájába java engedélyek zárolva**  
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha nem konfigurálja ezt a beállítást, a Java-alkalmazások le vannak tiltva.
  - **Alapértelmezett**: Tiltsa le a java 
  
- **Az Internet Explorer letöltött programok aláírásának ellenőrzése**  
  Ez a házirend-beállítással kezelheti-e az Internet Explorer ellenőrzi a digitális aláírások (amely azonosítja a szoftver gyártóját, és ellenőrzi a még nem lettek módosítva vagy illetéktelenül) a felhasználó számítógépén végrehajtható programok letöltése előtt. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer végrehajtható programok a digitális aláírások ellenőrzése és előtt a felhasználó számítógépére történő letöltésük megjelenítéséhez. Ha letiltja ezt a beállítást, az Internet Explorer nem a végrehajtható programok a digitális aláírások ellenőrzése vagy identitásuk megjelenítése előtt felhasználó számítógépére történő. Ha nem konfigurálja ezt a házirendet, az Internet Explorer nem a végrehajtható programok a digitális aláírások ellenőrzése vagy identitásuk megjelenítése előtt felhasználó számítógépére történő.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer korlátozott webes böngészővezérlők parancsprogramok zóna**  
  A házirend-beállítás meghatározza, hogy e lap szabályozhatja a beágyazott WebBrowser vezérlők parancsfájl használatával. Ha ez a szabályzatbeállítás engedélyezi, a parancsfájl hozzáférést ovládací prvek WebBrowser engedélyezett. Ha letiltja ezt a beállítást, ovládací prvek WebBrowser parancsfájlok hozzáférése nem engedélyezett. Nem konfigurálja ezt a beállítást, ha a felhasználó engedélyezheti vagy letilthatja ovládací prvek WebBrowser parancsfájl-hozzáférését. Alapértelmezés szerint csak az intranetes zónák és helyi számítógép ovládací prvek WebBrowser parancsfájl hozzáférést engedélyezett.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna keresztszűrő hely parancsfájl-kezelési**  
  Ez az irányelv szabályozza-e a többhelyes parancsfájl-kezelési (XSS) szűrő érzékeli, és webhelyek ebben a zónában, a webhelyközi parancsprogramot injektálások megakadályozása. Ha ez a szabályzatbeállítás engedélyezi, a XSS szűrő zónában is engedélyezve van, és a XSS-szűrő megpróbálja webhelyközi parancsprogramot injektálások letiltása. Ha letiltja ezt a beállítást, a XSS szűrő ki van kapcsolva a zónában, és az Internet Explorer lehetővé teszi a webhelyközi parancsprogramot injektálások.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer korlátozott zóna bináris vagy parancsfájl viselkedések**  
  A házirend-beállítás lehetővé teszi, hogy a dinamikus bináris és parancsfájl viselkedéseinek kezeléséhez: magába foglalja a HTML-elemek, amelyhez csatolva vannak bizonyos funkciók összetevőket. Ha ez a szabályzatbeállítás engedélyezi, bináris és parancsfájl viselkedések érhetők el. Ha jóvá a legördülő listából a rendszergazda, csak a rendszergazda által jóváhagyott viselkedéseket a bináris viselkedéseket házirend szereplő viselkedések érhetők el. Ha letiltja ezt a beállítást, bináris és parancsfájl viselkedések nem érhető el csak alkalmazások rendelkeznek egy egyéni biztonsági manager. Ha nem adja meg a házirend-beállítás, bináris és parancsfájl viselkedések nem érhető el csak alkalmazások rendelkeznek egy egyéni biztonsági manager.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer biztonsági beállítások ellenőrzése**  </br>
  A házirend-beállítás a biztonsági beállítások ellenőrzése szolgáltatást, amely ellenőrzi az Internet Explorer biztonsági beállításokat határozza meg, amikor a beállítások veszélynek az Internet Explorer kikapcsolása. Ha ez a szabályzatbeállítás engedélyezi, a funkció ki van kapcsolva. Ha letiltja vagy nem konfigurálja ezt a beállítást, a funkció be van kapcsolva.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer az internet zóna biztonsági figyelmeztetés a potenciálisan nem biztonságos fájlok**  
  A házirend-beállítás szabályozza-e a "Nyissa meg a fájl – biztonsági figyelmeztetés" üzenet jelenik meg, ha a felhasználó megpróbálja megnyitni a végrehajtható fájlok vagy más potenciálisan nem biztonságos fájlok (az intranetes a Fájlkezelővel, például fájlmegosztások). Ha engedélyezi ezt a házirend-beállítást, és állítsa be a legördülő listában annak érdekében, ezek a fájlok nyissa meg a biztonsági figyelmeztetés nélkül. Ha a legördülő listából a kérdés, biztonsági figyelmeztetés jelenik meg, a fájlok megnyitása előtt. Ha letiltja ezt a beállítást, nyissa meg ezeket a fájlokat. Ha nem konfigurálja ezt a beállítást, a felhasználó konfigurálhat a fájlok kezelésének. Alapértelmezés szerint ezeket a fájlokat a Tiltott helyek zónához, az intranetes és a helyi számítógép zónában, engedélyezve van a blokkolt és állítsa be az Internet és megbízható zónában kéréséhez.
  - **Alapértelmezett**: Kérdés  
  
- **Az Internet Explorer intranetes zóna java-engedélyek**  
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha letiltja ezt a beállítást, az engedély értéke közepes biztonsági.
  - **Alapértelmezett**: Magas biztonsági 
  
- **Az Internet Explorer elavult blokk ActiveX-vezérlők**  </br>
  A házirend-beállítás határozza meg, hogy az Internet Explorer blokkolja adott elavult ActiveX-vezérlők. Elavult ActiveX-vezérlők a rendszer soha nem blokkolja az Intranet zóna. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer nem blokkolja az elavult ActiveX-vezérlőket. Ha letiltja vagy nem konfigurálja ezt a beállítást, az Internet Explorer továbbra is adott elavult ActiveX-vezérlők letiltása. További információkért lásd: "Elavult ActiveX-vezérlők" az Internet Explorer TechNet könyvtárban.
  - **Alapértelmezett**: Engedélyezve  
  
- **Internet Explorer restricted zone popup blocker**  
  Ez a házirend-beállítással kezelheti, hogy nemkívánatos előugró ablak jelenik meg. Előugró ablakok nyílnak meg, amikor a végfelhasználó egy hivatkozásra kattint, nincs letiltva. Ha ez a szabályzatbeállítás engedélyezi, leggyakrabban nemkívánatos előugró ablakok ebben az esetben jelennek meg. Ha letiltja ezt a beállítást, az előugró windows nem ebben az esetben a parancsot. Ha nem adja meg a házirend-beállítás, leggyakrabban nemkívánatos előugró ablakok ebben az esetben jelennek meg.
  - **Alapértelmezett**: Engedélyezés  
  
- **Az Internet Explorer folyamatok MK protokoll biztonsági korlátozása**  
  Az MK protokoll biztonsági korlátozása a házirend-beállítást csökkenti a támadási felület megakadályozzák, hogy az MK protokollt. Az MK protokollon sikertelen lesz. Ha ez a szabályzatbeállítás engedélyezi, a fájlkezelő és az Internet Explorer számára letiltja az MK protokollt, és az MK protokollon sikertelen lesz. Ha letiltja ezt a beállítást, az alkalmazások használhatják az MK-protokoll API-t. Az MK protokollon a Fájlkezelőben és az Internet Explorer folyamatok esetében működnek. Ha nem adja meg a házirend-beállítás, fájlkezelő és az Internet Explorer számára letiltja az MK protokollt, és az MK protokollon sikertelenek lesznek.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer megbízható zóna java-engedélyek**  </br>
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha letiltja ezt a beállítást, az engedély értéke alacsony biztonsági.
  - **Alapértelmezett**: Magas biztonsági  
  
- **Az Internet Explorer korlátozott kisalkalmazások parancsprogramok zóna**  
  A házirend-beállítás lehetővé teszi, hogy e kisalkalmazások érhetők el a zóna parancsfájlok kezelését. Ha ez a szabályzatbeállítás engedélyezi, a parancsfájlok kisalkalmazások automatikusan, felhasználói beavatkozás nélkül hozzáférhetnek. Kérdés választja a legördülő mezőben, ha a rendszer megkérdezi a felhasználókat, döntse el, hogy engedélyezi a parancsprogramokat alkalmazások eléréséhez. Ha letiltja ezt a beállítást, parancsfájlokat ebben az esetben a az alkalmazásainak elérését. Ha nem adja meg a házirend-beállítás, parancsfájlokat ebben az esetben alkalmazások elérése.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer zárolja a Tiltott helyek zónához java-engedélyek**  </br>
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha nem konfigurálja ezt a beállítást, a Java-alkalmazások le vannak tiltva.
  - **Alapértelmezett**: Tiltsa le a java 
  
- **Az Internet Explorer internetes zóna engedélyezése csak a jóváhagyott tartományok ActiveX-vezérlők használata**  </br>
  A házirend-beállítás szabályozza-e kéri a felhasználót, hogy futtathatók a webhelyeken a webhely, amelyen telepítve van az ActiveX-vezérlő nem ActiveX-vezérlők. Ha ez a szabályzatbeállítás engedélyezi, kéri a felhasználót, az ActiveX-vezérlők a zóna webhelyekről futtatása előtt. A felhasználó választhat, hogy a vezérlő az aktuális helyről, vagy az összes helyről. Ha letiltja ezt a beállítást, a felhasználó nem látja a helyenként ActiveX-parancssort, és a zónában lévő összes webhely ActiveX-vezérlők futtatható.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer minden hálózati elérési**  
  Az Internet Explorer minden hálózati elérési
  - **Alapértelmezett**: Letiltva 
  
- **Az Internet Explorer internetes zóna a védett mód**  
  A házirend-beállítás lehetővé teszi, hogy a védett mód bekapcsolása. A védett mód megvédi az Internet Explorer a kihasznált biztonsági réseket a helyeken, amelyek az Internet Explorer a beállításjegyzék és a fájlrendszerhez írhat csökkentésével. Ha ez a szabályzatbeállítás engedélyezi, védett üzemmód be van kapcsolva. A felhasználó nem a védett mód kikapcsolása. Ha letiltja ezt a beállítást, a védett mód ki van kapcsolva. A felhasználó nem a védett mód bekapcsolása. Ha nem konfigurálja ezt a beállítást, a felhasználó kapcsolja be, vagy kapcsolja ki a védett mód.
  - **Alapértelmezett**: Engedélyezés 
  
- **Az Internet Explorer az internet zóna inicializálása és parancsfájl Active X-vezérlők nem biztonságosként megjelölt**  
  Ez a szabályzatbeállítás nem biztonságosként megjelölt ActiveX-vezérlők kezelését teszi lehetővé. Ha ez a szabályzatbeállítás engedélyezi, az ActiveX-vezérlők futnak, betöltött paraméterekkel, és a parancsfájlalapú objektum nem megbízható adatok vagy parancsfájlok biztonságának beállítása nélkül. Ezt a beállítást nem ajánlott, kivéve a biztonságos és felügyelt zónák. A beállítás hatására nem biztonságos, és a biztonságos vezérlők inicializálása és parancsprogrammal létrehozva, a rendszer figyelmen kívül hagyja az ActiveX-vezérlők biztonságosnak lehetőséget. Ha engedélyezi ezt a házirend-beállítást, és a legördülő mezőben válassza ki a kérdés, felhasználók kérdezhető le, hogy a vezérlőelem betöltését paraméterekkel engedélyezi-e, vagy parancsprogram. Ha letiltja ezt a beállítást, ActiveX-vezérlők nem tehető nem paraméterekkel betöltése vagy parancsprogrammal létrehozva. Ha nem adja meg a házirend-beállítás, ActiveX-vezérlők nem tehető nem paraméterekkel betöltése vagy parancsprogrammal létrehozva.
  - **Alapértelmezett**: Letiltás 
  
- **Az Internet Explorer SmartScreen tiltott helyek zónához zárolva**  </br>
  Ez a házirend-beállítással megadható, hogy a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha ez a szabályzatbeállítás engedélyezi, a SmartScreen szűrő megvizsgálja a rosszindulatú zóna oldalak. Ha letiltja ezt a beállítást, a SmartScreen szűrő nem ellenőrzi a lapok rosszindulatú zónában. Ha nem konfigurálja ezt a beállítást, a felhasználó választhat megvizsgálja-e a SmartScreen szűrő az oldalakat a rosszindulatú zóna. Megjegyezés: Az Internet Explorer 7 a házirend-beállítás meghatározza, hogy megvizsgálja-e adathalász szűrő oldalak rosszindulatú zónában.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer összeomlási észlelése**  
  A házirend-beállítás lehetővé teszi, hogy az összeomlási észlelési funkcióját kiegészítő felügyeleti kezelheti. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer összeomlás verziójának megfelelően viselkedik a Windows XP Professional Service Pack 1 és korábbi verzióiban, nevezetesen meghívni a Windows hibajelentés. Az összes házirend-beállítások a Windows hibajelentés továbbra is a alkalmazni. Ha letiltja vagy nem konfigurálja ezt a beállítást, az összeomlási duplikálásészlelési szolgáltatását a kiegészítő felügyeleti fognak működni.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer internetes zóna java-engedélyek**  
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha letiltja ezt a beállítást, az engedély értéke magas biztonsági.
  - **Alapértelmezett**: Tiltsa le a java  
  
- **Az Internet Explorer korlátozott zóna active scripting**  
  Ez a házirend-beállítással kezelheti, hogy fut a zónában lévő lapok a parancsfájl kód. Ha ez a szabályzatbeállítás engedélyezi, a zónában lévő lapok szkriptkódot automatikusan futtathatók. Kérdés a legördülő mezőben válassza ki, ha a rendszer megkérdezi a felhasználókat, hogy a parancsfájl kód futtatásához a zónában lévő lapok teszi lehetővé e. Ha letiltja a beállítást, a szkriptkód a lapok zónában nem futtathatók. Ha nem konfigurálja ezt a beállítást, a zónában lévő lapok szkriptkódot nem futtathatók.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer internetes zóna bejelentkezési beállítások**  
  A házirend-beállítás lehetővé teszi a bejelentkezési beállítások beállításainak kezelésére. Ha ez a szabályzatbeállítás engedélyezi, a következő bejelentkezési lehetőségek közül választhat. Tiltsa le a HTTP-hitelesítést és -felhasználási névtelen bejelentkezés a Vendég fiók csak a Common Internet File System (CIFS) protokollhoz. Felhasználónév és jelszó kérése tartozó felhasználói azonosítók és jelszavak. Miután egy felhasználó kérdeznek le, ezeket az értékeket használható csendes a munkamenet hátralévő részére. Automatikus bejelentkezés csak az Intranet zónába tartozó felhasználói azonosítók és jelszavak a más zónákban lekérdezés felhasználóinak. Miután egy felhasználó kérdeznek le, ezeket az értékeket használható csendes a munkamenet hátralévő részére. Automatikus bejelentkezés az aktuális felhasználónevet és jelszót megpróbálja bejelentkezés Windows NT kérdés-válasz (más néven az NTLM-hitelesítés) használatával. Windows NT kérdés-válasz a kiszolgáló által támogatott, ha a bejelentkezés a felhasználó hálózati felhasználónevet és jelszót használja is bejelentkezhet. Ha a kiszolgáló által nem támogatott a Windows NT kérdés-válasz, a felhasználó lekérdezése követi, adja meg a felhasználónevet és jelszót. Ha letiltja ezt a beállítást, bejelentkezési értéke napló automatikus a csak az Intranet zónában. Ha nem konfigurálja ezt a beállítást, a log értéke napló automatikus a csak az Intranet zónában.
  - **Alapértelmezett**: Kérdés  
  
- **Internet Explorer restricted zone allow vbscript to run**  </br>  
  Ez a házirend-beállítással kezelheti, hogy VBScript futtathatja a lapokon az Internet Explorerben a megadott zónában. A legördülő listában kiválasztott engedélyezése, ha a VBScript felhasználói beavatkozás nélkül futtatható. A legördülő listában kiválasztott kérése, ha rendszer kéri a felhasználóktól, hogy a VBScript futtatását engedélyezi-e. A legördülő listában kiválasztott tiltsa le, ha VBScript nem futtathatók. Ha nem konfigurálja, vagy tiltsa le ezt a beállítást, VBScript nem futtathatók.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer az internet zóna húzza tartalmat más tartományokból keresztül windows**  
  A házirend-beállítás lehetővé teszi a húzással tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows beállításainak megadása. Ha engedélyezi ezt a házirend-beállítást, és kattintson az engedélyezés, felhasználók húzza tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást. Ha engedélyezi ezt a házirend-beállítást, és kattintson a Letiltás elemre, felhasználók nem húzható tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást. Az Internet Explorer 10 Ha ezt a beállítást letiltja vagy nem konfigurálja, felhasználók nem húzható tartalom egyik tartományából egy másik tartományba Ha a forrás- és a különböző windows. A felhasználók módosíthatják ezt a beállítást az Internetbeállítások párbeszédpanelt. Az Internet Explorer 9 és korábbi verzióiban Ha letiltja ezt a házirendet, vagy nem konfigurálja, felhasználók húzhatja tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást.
  - **Alapértelmezett**: Letiltva 
  
- **Az Internet Explorer intranetes zóna inicializálása és parancsfájl Active X-vezérlők nem biztonságosként megjelölt**  
  Ez a szabályzatbeállítás nem biztonságosként megjelölt ActiveX-vezérlők kezelését teszi lehetővé. Ha ez a szabályzatbeállítás engedélyezi, az ActiveX-vezérlők futnak, betöltött paraméterekkel, és a parancsfájlalapú objektum nem megbízható adatok vagy parancsfájlok biztonságának beállítása nélkül. Ezt a beállítást nem ajánlott, kivéve a biztonságos és felügyelt zónák. A beállítás hatására nem biztonságos, és a biztonságos vezérlők inicializálása és parancsprogrammal létrehozva, a rendszer figyelmen kívül hagyja az ActiveX-vezérlők biztonságosnak lehetőséget. Ha engedélyezi ezt a házirend-beállítást, és a legördülő mezőben válassza ki a kérdés, felhasználók kérdezhető le, hogy a vezérlőelem betöltését paraméterekkel engedélyezi-e, vagy parancsprogram. Ha letiltja ezt a beállítást, ActiveX-vezérlők nem tehető nem paraméterekkel betöltése vagy parancsprogrammal létrehozva. Ha nem adja meg a házirend-beállítás, ActiveX-vezérlők nem tehető nem paraméterekkel betöltése vagy parancsprogrammal létrehozva.
  - **Alapértelmezett**: Letiltás 
  
- **Az Internet Explorer letöltési ház**  
  A házirend-beállítás megakadályozza, hogy a felhasználó kellene (fájlmellékletek) házak letöltve az hírcsatorna a felhasználó számítógépén. Ha ez a szabályzatbeállítás engedélyezi, a felhasználó nem állítható be a hírcsatorna-szinkronizálási motor letölteni egy ház hírcsatorna tulajdonságok oldalán keresztül. A fejlesztő nem módosítható a letöltési beállítását a hírcsatorna-API-kon keresztül. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználó beállíthat egy ház hírcsatorna tulajdonságok oldalán keresztül letöltéséhez a hírcsatorna-szinkronizálási motor. A fejlesztők a letöltési beállítást a hírcsatorna-API-k segítségével módosíthatja.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna töltse le a nem aláírt ActiveX-vezérlők**  </br>
  Ez a házirend-beállítással kezelheti, hogy a felhasználók letölthetnek aláíratlan ActiveX-vezérlők a zónából. Az ilyen kódja potenciálisan káros, különösen akkor, ha egy nem megbízható zóna származik. Ha ez a szabályzatbeállítás engedélyezi, az aláírás nélküli vezérlők felhasználói beavatkozás nélkül futtathatók. Kérdés a legördülő mezőben válassza ki, ha a rendszer megkérdezi a felhasználókat, döntse el, hogy az adott vezérlőt futtatásához. Ha letiltja ezt a beállítást, a felhasználók nem futtathatnak aláíratlan vezérlőket. Ha nem konfigurálja ezt a beállítást, a felhasználók nem futtathatnak aláíratlan vezérlőket.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer az internet zóna tartalom húzza az eltérő tartományokban időkereten belül**  
  Ez a házirend-beállítással kezelheti, hogy a felhasználók letölthetnek aláíratlan ActiveX-vezérlők a zónából. Az ilyen kódja potenciálisan káros, különösen akkor, ha egy nem megbízható zóna származik. Ha ez a szabályzatbeállítás engedélyezi, az aláírás nélküli vezérlők felhasználói beavatkozás nélkül futtathatók. Kérdés a legördülő mezőben válassza ki, ha a rendszer megkérdezi a felhasználókat, döntse el, hogy az adott vezérlőt futtatásához. Ha letiltja ezt a beállítást, a felhasználók nem futtathatnak aláíratlan vezérlőket. Ha nem konfigurálja ezt a beállítást, a felhasználók nem futtathatnak aláíratlan vezérlőket.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer folyamatok korlátozása Active X-telepítés**  </br>
  A házirend-beállítás lehetővé teszi, hogy a webböngésző vezérlőt tartalmazó alkalmazások letiltása, az ActiveX-vezérlő telepítésére kérő üzenet automatikus. Ha ez a szabályzatbeállítás engedélyezi, a webböngésző vezérlő letiltja az összes folyamat ActiveX-vezérlő telepítésére kérő üzenet automatikus. Ha letiltja vagy nem konfigurálja ezt a beállítást, a webböngésző vezérlőelem nem blokkolja az összes folyamat ActiveX-vezérlő telepítésére kérő üzenet automatikus.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer internetes zóna Szkriptletek** a házirend-beállítás lehetővé teszi, hogy kezelheti, hogy a felhasználó futtathatja a Szkriptletek. Ha ez a szabályzatbeállítás engedélyezi, akkor a felhasználó Szkriptletek futtathatja. Ha letiltja ezt a beállítást, a felhasználó Szkriptletek nem futtatható. Ha nem konfigurálja ezt a beállítást, a felhasználó engedélyezheti vagy letilthatja a Szkriptletek.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna húzza és dobja el, vagy másolja és illessze be a fájlokat**  
  Ez a házirend-beállítással kezelheti, hogy a felhasználók húzással vagy másolással illessze be a zónán belüli forrásból származó fájlokat. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók vagy másolással húzza át és illessze be a zóna fájlok automatikusan. Kérdés a legördülő mezőben válassza ki, ha a rendszer megkérdezi a felhasználókat, hogy e húzással, vagy a fájlok másolása a zóna. Ha letiltja ezt a beállítást, a rendszer megakadályozza a felhasználókat a fájlok húzással másolással és beillesztéssel fájlokat ebben a zónában. Ha nem konfigurálja ezt a beállítást, a rendszer megkérdezi a felhasználókat, hogy e húzással, vagy a fájlok másolása a zóna.
  - **Alapértelmezett**: Letiltás  
  
- **Ha az aláírás érvénytelen az Internet Explorer szoftver** </br>
  Ez a házirend-beállítással kezelheti, hogy a szoftverek, például az ActiveX-vezérlők és letöltéseket, telepítve van, vagy a felhasználó által futtatott, annak ellenére, hogy az aláírás érvénytelen. Az érvénytelen aláírása jelezheti, hogy valaki módosította a fájlt. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók telepíteni, vagy az érvénytelen aláírással rendelkező fájlok futtatásának kéri. Ha letiltja ezt a beállítást, a felhasználók nem futtatásához vagy az érvénytelen aláírással rendelkező fájlok telepítése. Ha nem konfigurálja ezt a házirendet, felhasználók eldönthetik, vagy az érvénytelen aláírással rendelkező fájlok telepítése.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna másolja be a parancsfájl-n keresztül** </br> Ez a házirend-beállítással kezelheti-e parancsfájlokat egy vágólapi műveletet (például a kivágási, másolási és beillesztési) hajthat végre egy meghatározott régióban. Ha ez a szabályzatbeállítás engedélyezi, akkor a parancsfájl egy vágólapra művelet hajtható végre. Ha a parancssorban a legördülő mezőben válassza ki, a rendszer megkérdezi a felhasználókat, hogy a vágólap műveletek végrehajtásához. Ha letiltja ezt a beállítást, akkor a parancsfájl egy vágólapra operaci nelze provést. Ha nem adja meg a házirend-beállítás, az a parancsfájl egy vágólapra művelet nem hajtható végre.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna húzza tartalmat más tartományokból keresztül windows**  
  A házirend-beállítás lehetővé teszi a húzással tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows beállításainak megadása. Ha engedélyezi ezt a házirend-beállítást, és kattintson az engedélyezés, felhasználók húzza tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást. Ha engedélyezi ezt a házirend-beállítást, és kattintson a Letiltás elemre, felhasználók nem húzható tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást. Az Internet Explorer 10 Ha ezt a beállítást letiltja vagy nem konfigurálja, felhasználók nem húzható tartalom egyik tartományából egy másik tartományba Ha a forrás- és a különböző windows. A felhasználók módosíthatják ezt a beállítást az Internetbeállítások párbeszédpanelt. Az Internet Explorer 9 és korábbi verzióiban Ha letiltja ezt a házirendet, vagy nem konfigurálja, felhasználók húzhatja tartalom egyik tartományból egy másik tartományba Ha a forrás- és a különböző windows. Felhasználók nem módosíthatják ezt a beállítást.
  - **Alapértelmezett**: Letiltva  
  
- **Webhelyek hozzáadása az Internet Explorer-felhasználók**  
  Megakadályozza, hogy a felhasználók hozzáadásának vagy eltávolításának a helyek biztonsági zónából. A biztonsági zóna egy azonos biztonsági szintű webhelyek csoportja. Ha engedélyezi ezt a házirendet, a biztonsági zónák a hely felügyeleti beállítások le vannak tiltva. (Megtekintéséhez a hely felügyeleti biztonsági zónák Internetbeállítások párbeszédpanelen beállításait a biztonság lapon, és kattintson a helyek gombra.) Ha letiltja ezt a házirendet, vagy nem konfigurálja, a felhasználók adhat hozzá vagy távolíthat el azokból a megbízható helyek és a Tiltott helyek zóna, és módosítsa a beállításokat a Helyi Intranet zóna webhelyek. Ez a szabályzat megakadályozza, hogy a felhasználók megváltoztassák a hely felügyeleti beállításait a rendszergazda által létrehozott biztonsági zónák. Megjegyezés: A "Tiltsa le a Biztonság lap" házirend (\User Configuration\Administrative sablonok\Windows-összetevők\Internet Explorer\Internet Vezérlőpulton található), amely eltávolítja a biztonság lapon a felhasználói felületről, elsőbbséget élvez a szabályzat. Ha engedélyezve van, a rendszer figyelmen kívül hagyja ezt a házirendet. Lásd még a "biztonsági zónák: A szabályzat csak a számítógép beállításainak használata".
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer internetes zóna parancsfájl indított windows**  
  A házirend-beállítás lehetővé teszi, hogy korlátozásokat előugró ablakok parancsfájl által kezdeményezett, és a title és az állapot sávok tartalmazó windows kezelheti. Ha ez a szabályzatbeállítás engedélyezi, a Windows korlátozások security nem érvényesül ebben a zónában. A biztonsági zónában, ez a szolgáltatás által biztosított biztonsági réteggel nélkül futtatja. Ha letiltja ezt a beállítást, a parancsfájl által kezdeményezett előugró ablakok és a title és az állapot sávok tartalmazó windows lehetséges káros műveleteket nem lehet futtatni. Az Internet Explorer biztonsági szolgáltatása lesz az ebben a zónában által a Windows biztonsági korlátozások parancsfájlalapú funkció vezérlő beállításának. Ha nem konfigurálja ezt a beállítást, a parancsfájl által kezdeményezett előugró ablakok és a title és az állapot sávok tartalmazó windows lehetséges káros műveleteket nem lehet futtatni. Az Internet Explorer biztonsági szolgáltatása lesz az ebben a zónában által a Windows biztonsági korlátozások parancsfájlalapú funkció vezérlő beállításának.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer biztonsági zónák használata csak a gép beállításait**  
  Információ a biztonsági zóna, az adott számítógép minden felhasználóra vonatkozik. A biztonsági zóna egy azonos biztonsági szintű webhelyek csoportja. Ha engedélyezi ezt a házirendet, a biztonsági zóna a felhasználó által végrehajtott módosítások az adott számítógép minden felhasználóra vonatkozni fog. Ha letiltja ezt a házirendet, vagy nem konfigurálja, ugyanazon a számítógépen a felhasználók a saját biztonsági zónájának beállításai is létrehozhat. Ez a szabályzat célja, hogy a biztonsági zónájának beállításai alkalmazása egységesen ugyanazon a számítógépen, és nem változhat a felhasználó felhasználói. Lásd még a "biztonsági zónák: A házirend nem engedélyezi a felhasználók számára a szabályzatok módosítása".
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer zárolja a helyi gép zóna java-engedélyek**  
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha nem konfigurálja ezt a beállítást, a Java-alkalmazások le vannak tiltva
  - **Alapértelmezett**: Tiltsa le a java 
  
- **Az Internet Explorer korlátozott zóna nem futtatásához kártevőirtó ActiveX-vezérlők**  </br>
  A házirend-beállítás meghatározza, hogy az Internet Explorer fut-e kártevőirtó-programok ellen ActiveX-vezérlők annak ellenőrzéséhez, hogy azok biztonságos voltát oldalain betölteni. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer nem egyeztessen a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha letiltja ezt a beállítást, az Internet Explorer mindig ellenőrzi a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha nem konfigurálja ezt a beállítást, az Internet Explorer mindig ellenőrzi a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Bármikor ezt a viselkedést be- vagy kikapcsolása az Internet Explorer biztonsági beállításokkal.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna futtatása a .NET-keretrendszer authenticode aláírással rendelkező tartománybeli összetevők**  
  Ez a házirend-beállítással kezelheti, hogy a .NET-keretrendszer összetevők, az Authenticode aláírással rendelkező hajthat végre az Internet Explorer. Ezen összetevők közé tartozik egy objektum címke és a egy hivatkozást a hivatkozott felügyelt végrehajtható fájlok a hivatkozott felügyelt szabályozza. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer végrehajtja a aláírt felügyelt összetevőket. Kérdés a legördülő mezőben válassza ki, ha az Internet Explorer kéri a felhasználó határozza meg, hogy aláírt felügyelt összetevőket végrehajtásához. Ha letiltja ezt a beállítást, az Internet Explorer nem hajtható végre aláírt felügyelt összetevőket. Ha nem adja meg a házirend-beállítás, az Internet Explorer nem hajtható végre aláírt felügyelt összetevőket.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer korlátozott zóna hozzáférés adatforrásokhoz**  
  Ez a házirend-beállítással kezelheti, hogy az Internet Explorer érhessék el az adatokat a Microsoft XML Parser (MSXML) vagy ActiveX Data Objects (ADO) használatával egy másik biztonsági zónából. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók betölthetnek egy oldal, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez a zónában. Kérdés a legördülő mezőben válassza ki, ha a rendszer megkérdezi a felhasználókat, döntse el, hogy egy oldalon kell betölteni a zónában, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez. Ha letiltja ezt a beállítást, a felhasználók nem tudják betölteni egy oldal, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez a zónában. Ha nem konfigurálja ezt a beállítást, a felhasználók nem tudják betölteni egy oldal, amely az MSXML vagy ADO használ a zóna egy másik helyről származó adatok eléréséhez a zónában.
  - **Alapértelmezett**: Letiltás 
  
- **Az Internet Explorer az internet zóna nem futtatásához kártevőirtó ActiveX-vezérlők**  </br>
  A házirend-beállítás meghatározza, hogy az Internet Explorer fut-e kártevőirtó-programok ellen ActiveX-vezérlők annak ellenőrzéséhez, hogy azok biztonságos voltát oldalain betölteni. Ha ez a szabályzatbeállítás engedélyezi, az Internet Explorer nem egyeztessen a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha letiltja ezt a beállítást, az Internet Explorer mindig ellenőrzi a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Ha nem konfigurálja ezt a beállítást, az Internet Explorer mindig ellenőrzi a kártevőirtó programot, hogy hozzon létre egy példányt az ActiveX-vezérlő való biztonságos megtekintéséhez. Bármikor ezt a viselkedést be- vagy kikapcsolása az Internet Explorer biztonsági beállításokkal.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer internetes zóna másolja be a parancsfájl-n keresztül** </br> Ez a házirend-beállítással kezelheti-e parancsfájlokat egy vágólapi műveletet (például a kivágási, másolási és beillesztési) hajthat végre egy meghatározott régióban. Ha ez a szabályzatbeállítás engedélyezi, akkor a parancsfájl egy vágólapra művelet hajtható végre. Ha a parancssorban a legördülő mezőben válassza ki, a rendszer megkérdezi a felhasználókat, hogy a vágólap műveletek végrehajtásához. Ha letiltja ezt a beállítást, akkor a parancsfájl egy vágólapra operaci nelze provést. Ha nem konfigurálja ezt a beállítást, a parancsfájl hajthatják végre egy vágólapra műveletet.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer Active X-telepítő szolgáltatás használata**  </br>
  A házirend-beállítás lehetővé teszi, hogy adja meg, hogyan legyenek telepítve a ActiveX-vezérlőket. Ha ez a szabályzatbeállítás engedélyezi, az ActiveX-vezérlők települnek, csak akkor, ha az ActiveX Telepítőszolgáltatás jelen, és az ActiveX-vezérlők telepítésének engedélyezésére van konfigurálva. Ha letiltja vagy nem konfigurálja ezt a beállítást, a ActiveX-vezérlők, felhasználónkénti vezérlőiket, beleértve a szabványos telepítési folyamat során lesz telepítve.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer dolgozza fel a zóna jogok kiterjesztése elleni védelem**  
  Az Internet Explorer korlátozásokat minden lap nyílik meg. A korlátozások vonatkoznak (az Internet, intranetes, helyi zónán és így tovább) weblap helyétől. Például weblapok a helyi számítógépen a legkevesebb biztonsági korlátozások vonatkoznak, és a helyi számítógép zónában találhatók, ezek a helyi gép zónában egy rosszindulatú felhasználók a legkevesebb. Ha ez a szabályzatbeállítás engedélyezi, minden zónában is védeni kell az összes folyamat zóna jogosultságszint-emelési. Ha letiltja vagy nem konfigurálja ezt a beállítást, az Internet Explorer és a folyamat listán lévő folyamatok nincs ilyen védelem jelenik meg.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer az internet zóna előjel nélküli ActiveX-vezérlők letöltése**  </br>
  Ez a házirend-beállítással kezelheti, hogy a felhasználók letölthetnek aláíratlan ActiveX-vezérlők a zónából. Az ilyen kódja potenciálisan káros, különösen akkor, ha egy nem megbízható zóna származik. Ha ez a szabályzatbeállítás engedélyezi, az aláírás nélküli vezérlők felhasználói beavatkozás nélkül futtathatók. Kérdés a legördülő mezőben válassza ki, ha a rendszer megkérdezi a felhasználókat, döntse el, hogy az adott vezérlőt futtatásához. Ha letiltja ezt a beállítást, a felhasználók nem futtathatnak aláíratlan vezérlőket. Ha nem konfigurálja ezt a beállítást, a felhasználók nem futtathatnak aláíratlan vezérlőket.
  - **Alapértelmezett**: Letiltás  
  
- **Keresse meg a windows és a keretek az Internet Explorer az internet zóna különböző tartományokban**  </br>
  A házirend-beállítás lehetővé teszi a különböző tartományokban nyithatja meg a windows és a keretek és alkalmazások kezelését. Ha ez a szabályzatbeállítás engedélyezi, a felhasználók a windows és a keretek nyissa meg a Küldés más helyre tartományokból és más tartományokból alkalmazások eléréséhez. Ha kérdés választja a legördülő mezőben, megkérdezi a felhasználót, hogy a windows és más tartományokból alkalmazások eléréséhez keretek-e. Ha letiltja ezt a beállítást, a felhasználók nem tudják megnyitni, windows és bármely más tartományokból alkalmazások eléréséhez. Ha nem adja meg a házirend-beállítás, felhasználó meg tudja nyitni a windows és a keretek más tartományok és más tartományokból alkalmazásokat.
  - **Alapértelmezett**: Letiltás  
  
- **Az Internet Explorer internetes zóna frissítések állapotsor parancsfájl használatával**  
  A házirend-beállítás lehetővé teszi, hogy kezelheti, hogy a parancsfájl engedélyezett a zónán belül az állapotsor frissítése. Ha ez a szabályzatbeállítás engedélyezi, parancsfájl engedélyezett az állapotsor frissítése. Ha letiltja vagy nem konfigurálja ezt a beállítást, parancsfájl nem engedélyezett az állapotsor frissítése.
  - **Alapértelmezett**: Letiltva  
  
- **A fájlok feltöltése a kiszolgáló szerepeljen az Internet Explorer korlátozott zóna helyi elérési útja**  </br> A házirend-beállítás szabályozza-e helyi elérési úttal kapcsolatos információkat küldött-e, amikor a felhasználó tölti fel egy fájlt egy HTML-űrlapot. A helyi elérési út adatokat küld, ha néhány információt előfordulhat, hogy véletlenül is megjeleníthetők a kiszolgálóhoz. Például a felhasználó asztali küldött fájlokat tartalmazhat az elérési út részeként a felhasználó nevét. Amikor a felhasználó tölti fel egy fájlt egy HTML-űrlapot, ha ez a szabályzatbeállítás engedélyezi, a rendszer elküldi az elérési út adatokat. Amikor a felhasználó egy HTML-űrlapot egy fájlt tölt, ha letiltja ezt a beállítást, a rendszer eltávolítja az elérési úttal kapcsolatos információkat. Ha nem konfigurálja ezt a beállítást, a felhasználó dönthet úgy, hogy küld-e elérési úttal kapcsolatos információkat, amikor egy fájl egy HTML-űrlaphoz keresztül töltenek. Alapértelmezés szerint az útvonal-információinak zajlik.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer folyamatok korlátozása fájl letöltése**  </br> A házirend-beállítás lehetővé teszi, hogy a webböngésző vezérlőt tartalmazó alkalmazás blokkolja a fájlok letöltése, amelyek nem a felhasználó által kezdeményezett automatikus kérő üzenet. Ha ez a szabályzatbeállítás engedélyezi, a webböngésző vezérlő blokkolja a fájlok letöltése, amelyek nem a felhasználó által kezdeményezett összes folyamat automatikus kérő üzenet. Ha letiltja ezt a beállítást, a webböngésző vezérlőelem nem blokkolja a letöltéseket, amelyek nem a felhasználó által kezdeményezett összes folyamat automatikus kérő üzenet.
  - **Alapértelmezett**: Engedélyezve  
  
- **Tiltott helyek zónához engedélyezése az Internet Explorer csak a jóváhagyott tartományok ActiveX-vezérlők használata**  </br>
  A házirend-beállítás szabályozza-e kéri a felhasználót, hogy futtathatók a webhelyeken a webhely, amelyen telepítve van az ActiveX-vezérlő nem ActiveX-vezérlők. Ha ez a szabályzatbeállítás engedélyezi, kéri a felhasználót, az ActiveX-vezérlők a zóna webhelyekről futtatása előtt. A felhasználó választhat, hogy a vezérlő az aktuális helyről, vagy az összes helyről. Ha letiltja ezt a beállítást, a felhasználó nem látja a helyenként ActiveX-parancssort, és a zónában lévő összes webhely ActiveX-vezérlők futtatható.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer korlátozott zóna inicializálása és parancsfájl Active X-vezérlők nem biztonságosként megjelölt**  
  Ez a szabályzatbeállítás nem biztonságosként megjelölt ActiveX-vezérlők kezelését teszi lehetővé. Ha ez a szabályzatbeállítás engedélyezi, az ActiveX-vezérlők futnak, betöltött paraméterekkel, és a parancsfájlalapú objektum nem megbízható adatok vagy parancsfájlok biztonságának beállítása nélkül. Ezt a beállítást nem ajánlott, kivéve a biztonságos és felügyelt zónák. A beállítás hatására nem biztonságos, és a biztonságos vezérlők inicializálása és parancsprogrammal létrehozva, a rendszer figyelmen kívül hagyja az ActiveX-vezérlők biztonságosnak lehetőséget. Ha engedélyezi ezt a házirend-beállítást, és a legördülő mezőben válassza ki a kérdés, felhasználók kérdezhető le, hogy a vezérlőelem betöltését paraméterekkel engedélyezi-e, vagy parancsprogram. Ha letiltja ezt a beállítást, ActiveX-vezérlők nem tehető nem paraméterekkel betöltése vagy parancsprogrammal létrehozva. Ha nem adja meg a házirend-beállítás, ActiveX-vezérlők nem tehető nem paraméterekkel betöltése vagy parancsprogrammal létrehozva.
  - **Alapértelmezett**: Letiltás  
  
- **Internet Explorer felhasználói házirendek módosítása**  
    A felhasználók nem módosíthatják a biztonsági zóna beállításait. A biztonsági zóna egy azonos biztonsági szintű webhelyek csoportja. Ha engedélyezi ezt a házirendet, az Egyéni szint gombra, és a biztonság lapon az Internetbeállítások párbeszédpanelen biztonsági szintű csúszka le vannak tiltva. Ha letiltja ezt a házirendet, vagy nem konfigurálja, a felhasználók megváltoztathatják a beállításokat a biztonsági zónák. Ez a szabályzat megakadályozza, hogy a felhasználók a rendszergazda által létrehozott biztonsági zónájának beállításai megváltoztassa. Megjegyezés: A "Letiltás a Biztonság lap" házirend (\User Configuration\Administrative sablonok\Windows-összetevők\Internet Explorer\Internet Vezérlőpult), amely eltávolítja a biztonság lapon a Vezérlőpult Internet Explorer, elsőbbséget élvez Ez a házirend. Ha engedélyezve van, a rendszer figyelmen kívül hagyja ezt a házirendet. Lásd még a "biztonsági zónák: A szabályzat csak a számítógép beállításainak használata".
    - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna a védett mód**  
  A házirend-beállítás lehetővé teszi, hogy a védett mód bekapcsolása. A védett mód megvédi az Internet Explorer a kihasznált biztonsági réseket a helyeken, amelyek az Internet Explorer a beállításjegyzék és a fájlrendszerhez írhat csökkentésével. Ha ez a szabályzatbeállítás engedélyezi, védett üzemmód be van kapcsolva. A felhasználó nem a védett mód kikapcsolása. Ha letiltja ezt a beállítást, a védett mód ki van kapcsolva. A felhasználó nem a védett mód bekapcsolása. Ha nem konfigurálja ezt a beállítást, a felhasználó kapcsolja be, vagy kapcsolja ki a védett mód.
  - **Alapértelmezett**: Engedélyezés  
  
- **Az Internet Explorer internetes zóna felhasználói adatmegőrzés**  
  Ez a házirend-beállítással kezelheti az a böngészési előzményeket, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti az adatok megőrzését. Amikor egy felhasználó egy megőrzött oldalhoz adja vissza, az oldal állapotát visszaállíthatók, ha megfelelően van-e konfigurálva a házirend-beállítás. Ha ez a szabályzatbeállítás engedélyezi, a felhasználó a böngészési előzményeket, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti az adatokat megőrizheti. Ha letiltja ezt a beállítást, a felhasználók nem megőrzése a böngészési előzményeket, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti az adatokat. Ha nem adja meg a házirend-beállítás, felhasználók megőrizheti az adatokat a böngésző Előzmények, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer internetes zóna parancsprogramok webes böngészővezérlők**  
 
  A házirend-beállítás meghatározza, hogy e lap szabályozhatja a beágyazott WebBrowser vezérlők parancsfájl használatával. Ha ez a szabályzatbeállítás engedélyezi, a parancsfájl hozzáférést ovládací prvek WebBrowser engedélyezett. Ha letiltja ezt a beállítást, ovládací prvek WebBrowser parancsfájlok hozzáférése nem engedélyezett. Nem konfigurálja ezt a beállítást, ha a felhasználó engedélyezheti vagy letilthatja ovládací prvek WebBrowser parancsfájl-hozzáférését. Alapértelmezés szerint csak az intranetes zónák és helyi számítógép ovládací prvek WebBrowser parancsfájl hozzáférést engedélyezett.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna felhasználói adatok megőrzése**  
    Ez a házirend-beállítással kezelheti az a böngészési előzményeket, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti az adatok megőrzését. Amikor egy felhasználó egy megőrzött oldalhoz adja vissza, az oldal állapotát visszaállíthatók, ha megfelelően van-e konfigurálva a házirend-beállítás. Ha ez a szabályzatbeállítás engedélyezi, a felhasználó a böngészési előzményeket, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti az adatokat megőrizheti. Ha letiltja ezt a beállítást, a felhasználók nem megőrzése a böngészési előzményeket, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti az adatokat. Ha nem konfigurálja ezt a beállítást, a felhasználó nem őrizheti meg a böngészési előzményeket, a Kedvencek, XML-tárolóban, vagy közvetlenül egy weblap, lemezre menti az adatokat.  
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer intranetes zóna java engedélyek zárolva**  
  A házirend-beállítás lehetővé teszi a Java-alkalmazások engedélyeinek kezelése. Ha ez a szabályzatbeállítás engedélyezi, beállítások választhat a legördülő listából. Egyéni engedélyek beállításait szabályozhatja a külön-külön. Alacsony biztonsági lehetővé teszi, hogy az alkalmazások összes műveletek végrehajtásához. Közepes biztonsági plusz szolgáltatásokat, például az ideiglenes terület (egy megbízható és biztonságos tároló terület az ügyfélszámítógépen) és a felhasználó általi fájl i/o lehetővé teszi alkalmazások futtatását a védőfal (egy területen kívül, ami a program nem hívásokat a memóriában). Magas biztonsági lehetővé teszi, hogy az alkalmazások futtatását a tesztkörnyezetben. Tiltsa le a Java használatával bármilyen kisalkalmazások tiltsa le a futását. Ha letiltja ezt a beállítást, a Java-alkalmazások nem futtatható. Ha nem konfigurálja ezt a beállítást, a Java-alkalmazások le vannak tiltva.
  - **Alapértelmezett**: Tiltsa le a java  
  
- **Az Internet Explorer fokozott védett mód**  
  Fokozottan védett üzemmód rosszindulatú webhelyekre elleni további védelmet biztosít a 64 bites Windows 64 bites folyamatokat használatával. Vagy újabb rendszert futtató számítógépek Windows 8, a fokozottan védett üzemmóddal is korlátozza a helyeken, az Internet Explorer is olvasható, és a beállításjegyzék és a fájlrendszerhez. Ha ez a szabályzatbeállítás engedélyezi, fokozottan védett üzemmód be kell kapcsolni. Minden zóna, amely a védett mód engedélyezve van a fokozottan védett üzemmód fogja használni. Felhasználók nem fognak tudni fokozottan védett üzemmód letiltása. Ha letiltja ezt a beállítást, fokozottan védett üzemmód ki lesz kapcsolva. Minden zóna, amely a védett mód engedélyezve van a védett mód a Windows Vista Internet Explorer 7-ben bevezetett verzióját fogja használni. Ha nem konfigurálja ezt a házirendet, felhasználók fognak tudni kapcsolja be vagy fokozottan védett üzemmód kikapcsolása az Internetbeállítások párbeszédpanel Speciális lapján.
  - **Alapértelmezett**: Engedélyezve  
  
- **Az Internet Explorer SmartScreen-figyelmeztetések mellőzése**  
  Ez a szabályzatbeállítás határozza meg, hogy a felhasználó elkerülheti a SmartScreen szűrő figyelmeztetéseit. A SmartScreen szűrő figyelmezteti a felhasználót a végrehajtható fájlokat, az Internet Explorer felhasználók ne gyakran töltse le az internetről. Ha ez a szabályzatbeállítás engedélyezi, a SmartScreen szűrő figyelmeztetéseit letiltása a felhasználó. Ha letiltja vagy nem konfigurálja ezt a beállítást, a felhasználó elkerülheti a SmartScreen szűrő figyelmeztetéseit.
  - **Alapértelmezett**: Letiltva  
  
- **Az Internet Explorer korlátozott zóna metaadat-frissítés**  
  Ez a házirend-beállítással kezelheti, hogy a felhasználók egy másik weblapon átirányíthatóak, ha a szerző, a weblap a metaadat-frissítési beállítást (címke) használ a böngésző átirányítja egy másik weblapon. Ha ez a szabályzatbeállítás engedélyezi, a felhasználó böngészője aktív metaadat-frissítési beállítást tartalmazó oldal betöltésekor átirányíthatóak egy másik weboldalra. Ha letiltja ezt a beállítást, a felhasználó böngészője aktív metaadat-frissítési beállítást tartalmazó oldal betöltésekor nem irányítható át egy másik weblapon. Ha nem konfigurálja ezt a beállítást, a felhasználó böngészője aktív metaadat-frissítési beállítást tartalmazó oldal betöltésekor nem irányítható át egy másik weblapon.
  - **Alapértelmezett**: Letiltva  
  
## <a name="local-policies-security-options"></a>A helyi házirendek-biztonsági beállítások
További információkért lásd: [házirend CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) a Windows dokumentációjában. 

- **Nevesített csövekhez és megosztások való névtelen hozzáférés korlátozása**  
  Ha engedélyezve van, ez a beállítás korlátozza a névtelen hozzáférés-megosztásokat és -csövek beállításai: (1) named pipe-ok lehet névtelenül elérhető (2) megosztások névtelenül elérhető
  - **Alapértelmezett**: Igen  
  
- **Munkamenet minimális biztonság az NTLM SSP alapú kiszolgálókról**  
  Ez a beállítás lehetővé teszi, hogy megkövetelje az 128 bites titkosítás és/vagy NTLMv2 munkamenet egy kiszolgálót. Ezeket az értékeket a LAN-kezelő hitelesítési szintje biztonsági beállítás értéke függenek. Az alábbi lehetőségek állnak rendelkezésére: NTLMv2 munkamenet megkövetelése: A kapcsolat nem jön létre, ha az üzenet sértetlenségének nem egyeztetett. 128 bites titkosítás használata. A kapcsolat nem jön létre, ha nem egyeztetett erős titkosítást (128 bites).
  - **Alapértelmezett**: Az NTLM V2 és 128 bites titkosítás megkövetelése  
  
- **Percek száma zárolási képernyőn a képernyőkímélő**  
  A Windows észleli a bejelentkezési munkamenetek tétlenségét, és ha a tétlenség ideje túllépi a tétlenségi korlátot, a rendszer futtatja a képernyőkímélőt és lezárja a munkamenetet.
  - **Alapértelmezett**: 15
  
- **Szükséges ügyfél-kommunikációhoz mindig digitális aláírására** a biztonsági beállítás határozza meg, hogy a tartományi tag által kezdeményezett összes biztonságos csatorna forgalmat kell kell aláírva vagy titkosítva. Ha a számítógép tartományhoz csatlakozik, egy számítógép-fiók jön létre. Ezt követően a rendszer indításakor használ a számítógép fiók jelszavát a hozzá tartozó tartomány tartományvezérlő biztonságos csatornát létrehozni. A biztonságos csatorna segítségével műveleteket, mint például az NTLM továbbítja a hitelesítést, LSA SID/neve keresés stb. Ez a beállítás meghatározza, hogy-e a tartomány tagja által kezdeményezett összes biztonságos csatorna forgalom megfelel-e a minimális biztonsági követelményeknek. Konkrétan meghatározza, hogy e a tartomány tagja által kezdeményezett összes biztonságos csatorna forgalmat kell legyen aláírva vagy titkosítva. Ha ez a szabályzat engedélyezve van, majd a biztonságos csatorna nem létrejön, ha aláírást vagy az összes biztonságos csatorna forgalom titkosítása egyeztetve van-e. Ha ez a házirend le van tiltva, akkor a titkosítási és aláírási biztonságos csatorna összes forgalom egyeztetve van-e a tartományvezérlővel, amely esetben aláírás és titkosítás szintjét attól függ, a tartományvezérlő verziója és a beállításokat a következő két házirendek: Tartományi tag: (Ha lehet) biztonságos csatornák adatainak digitális titkosítása tartományi tag: (Ha ez lehetséges) digitális aláírása
  - **Alapértelmezett**: Igen
  
- **Hitelesítési szint**  
  Ez a beállítás meghatározza, hogy mely kérdés-válasz hitelesítési protokollt használják a hálózati bejelentkezést. Ez a választás hatással van a hitelesítési protokoll, amelyet az ügyfelek egyeztetett munkamenet biztonsági szintjét és a következőképpen fogadja el a kiszolgálók hitelesítési szintet szintje: Az LM- és NTLM-válaszok küldésére: Ügyfelek LM és az NTLM-hitelesítés használatára, és soha ne használja az NTLMv2 munkamenet; tartományvezérlők fogadja el az LM, NTLM és NTLMv2-alapú hitelesítést. Az LM és az NTLM NTLMv2-munkamenet - egyeztetés esetén: Ügyfelek LM és az NTLM-hitelesítés használatára, és NTLMv2 munkamenet használja, ha a kiszolgáló támogatja azt. tartományvezérlők fogadja el az LM, NTLM és NTLMv2-alapú hitelesítést. Csak NTLM-válasz küldése: Csak NTLM-hitelesítés használata az ügyfelek és a NTLMv2 munkamenet használja, ha a kiszolgáló támogatja azt. tartományvezérlők fogadja el az LM, NTLM és NTLMv2-alapú hitelesítést. Csak az NTLMv2-válasz küldése: Az ügyfelek csak NTLMv2-alapú hitelesítést használ, és NTLMv2 munkamenet használja, ha a kiszolgáló támogatja azt. tartományvezérlők fogadja el az LM, NTLM és NTLMv2-alapú hitelesítést. Az NTLMv2 válaszok küldése\LM LM küldése: Az ügyfelek csak NTLMv2-alapú hitelesítést használ, és NTLMv2 munkamenet használja, ha a kiszolgáló támogatja azt. a tartományvezérlők elutasítják LM (Elfogadás csak NTLMv2- és NTLM-hitelesítés). Az NTLMv2 válaszok küldése\LM LM és az NTLM: Az ügyfelek csak NTLMv2-alapú hitelesítést használ, és NTLMv2 munkamenet használja, ha a kiszolgáló támogatja azt. a tartományvezérlők elutasítják LM és az NTLM (Elfogadás csak NTLMv2-alapú hitelesítést).
  - **Alapértelmezett**: Csak az NTLMv2-válasz küldése. Az LM- és NTLM utasítania
  
- **Megakadályozza a titkosítatlan jelszavak küldése külső SMB-kiszolgálóknak**  
  Ha ez a beállítás engedélyezve van, a Server Message Block (SMB) átirányító egyszerű szöveges jelszavakat küldhet nem Microsoft SMB-kiszolgálókra, amelyek nem támogatják a titkosítási jelszó a hitelesítés során engedélyezett. Titkosítatlan jelszavak küldése biztonsági kockázatot jelent.
  - **Alapértelmezett**: Igen
  
- **Digitális aláírás mindig kommunikációs kiszolgáló letiltása**  
  Ez a beállítás határozza meg, hogy az SMB-ügyfél megpróbálja-e egyeztetni az SMB-csomagaláírást. A server message block (SMB) protokoll a Microsoft-fájl- és nyomtatómegosztás alapját, és számos más hálózati műveletek, például a távoli Windows-felügyelet biztosít. SMB-csomagok továbbításához módosító man-in-the-middle támadások megelőzése érdekében az SMB protokoll támogatja az SMB-csomagokat digitális aláírását. A házirend-beállítás határozza meg, hogy az SMB-ügyfél összetevő megpróbál-e egyeztetni az SMB-csomagaláírás, amikor csatlakozik a SMB-kiszolgálón. Ha ez a beállítás engedélyezve van, a Microsoft hálózati ügyfél kéri a kiszolgálót az SMB-csomagaláírás munkamenet telepítés végrehajtásához. Csomagaláírás engedélyezve van a kiszolgálón, ha a csomagaláírás egyeztetve lesz. Ez a házirend le van tiltva, ha az SMB-ügyfél a soha nem egyezteti az SMB-csomagaláírást.
  - **Alapértelmezett**: Igen
  
- **Rendszergazda jogosultságszint-emelési kérés működése**  
  Ez a szabályzatbeállítás a jogosultságszint-emelési kérés rendszergazdák számára viselkedését szabályozza. Az alábbi lehetőségek állnak rendelkezésére: 0 – jogosultságszint-emelés rákérdezés nélkül: Lehetővé teszi a kiemelt jogosultságú fiókok jogosultságszint-emelési anélkül, hogy a hozzájárulási vagy hitelesítő adatokat igénylő művelet végrehajtásához. Megjegyezés: Használja ezt a beállítást csak a legnagyobb mértékben korlátozott környezetben. 1 – a biztonsági asztal hitelesítő adatok kérése: Egy műveletet igényel a jogok kiterjesztése, a felhasználó a rendszer kér a biztonsági asztalon, egy rendszergazdai engedéllyel rendelkező felhasználó nevét és jelszavát adja meg. Ha a felhasználó sikeresen Megadja, hogy érvényes hitelesítő adatokat, a művelet a felhasználó a elérhető legmagasabb szintű jogosultsággal rendelkező továbbra is. 2 – a biztonsági asztalon beleegyezés kérése: Amikor-művelet megköveteli a jogok kiterjesztése, válassza ki, vagy engedélyezze a felhasználó kéri a biztonsági asztal. Ha a felhasználó engedélyt választja, a művelet a felhasználó a elérhető legmagasabb szintű jogosultsággal rendelkező továbbra is. 3 – hitelesítő adatok kérése: -Művelet megköveteli a jogok kiterjesztése, amikor a rendszer kéri a felhasználót, hogy adjon meg egy rendszergazdai felhasználónevet és jelszót. Ha a felhasználó sikeresen Megadja, hogy érvényes hitelesítő adatokat, a megfelelő jogosultságokkal a művelet továbbra is. 4 – beleegyezés kérése: Egy műveletet igényel a jogok kiterjesztése, a felhasználó a rendszer kér, válassza ki, vagy engedélyezze. Ha a felhasználó engedélyt választja, a művelet a felhasználó a elérhető legmagasabb szintű jogosultsággal rendelkező továbbra is. 5 – nem Windows bináris fájlok jóváhagyás kérése: (Alapértelmezett) Amikor egy művelet egy nem Microsoft-alkalmazáshoz szükséges megszerzését, válassza ki, vagy engedélyezze a felhasználó kéri a biztonsági asztal. Ha a felhasználó engedélyt választja, a művelet továbbra is a felhasználó a elérhető legmagasabb szintű jogosultsággal rendelkező
  - **Alapértelmezett**: Beleegyezés a biztonsági asztalon
  
- **Munkamenet minimális biztonság az NTLM SSP alapú ügyfelek**  
  Ez a beállítás lehetővé teszi, hogy az ügyfelek számára a 128 bites titkosítás és/vagy NTLMv2 munkamenet az egyeztetés. Ezeket az értékeket a LAN-kezelő hitelesítési szintje biztonsági beállítás értéke függenek. Az alábbi lehetőségek állnak rendelkezésére: NTLMv2 munkamenet megkövetelése: A kapcsolat nem jön létre, ha NTLMv2 protokoll nem egyeztetett. 128 bites titkosítás megkövetelése: A kapcsolat nem jön létre, ha nem egyeztetett erős titkosítást (128 bites).
  - **Alapértelmezett**: Az NTLM V2 128-titkosítás megkövetelése
  
- **Viselkedés az intelligens kártya eltávolításakor**  
  Ez a beállítás határozza meg, mi történik, ha a bejelentkezett felhasználó intelligens kártyáját eltávolítják az intelligenskártya-olvasó. Az alábbi lehetőségek állnak rendelkezésére: Nincs művelet zárolási munkaállomás kényszerített kijelentkezési bontása a távoli asztali szolgáltatások munkamenet, ha munkaállomás zárolása tulajdonságai párbeszédpanel a házirend, a munkaállomás zárolva van, az intelligens kártya eltávolításakor, így a felhasználók területen hagyja igénybe azok intelligens kártya velük, és a egy védett munkamenet fenntartásához. Ha a szabályzat a Tulajdonságok párbeszédpanelen kötelező kijelentkezés gombra kattint, a felhasználó automatikusan ki van jelentkezve az intelligens kártya eltávolításakor. Ha a kapcsolat bontása, ha egy távoli asztali szolgáltatások munkamenet kattint, az intelligens kártya eltávolítása anélkül, hogy a felhasználó kijelentkeztetése leválasztja a munkamenetet. Ez lehetővé teszi a felhasználó az intelligens kártya Beszúrás, és folytatni a munkamenetet később, vagy egy másik intelligens kártyát olvasó felszerelt számítógép, anélkül, hogy jelentkezzen be újra kellene. Helyi munkamenet esetén ez a szabályzat pontosan úgy működik, mint a Munkaállomás zárolása.
  - **Alapértelmezett**: Munkaállomás zárolása
  
- **SAM-fiókok és -megosztások névtelen felsorolása letiltása**  
  Ez a beállítás határozza meg, hogy engedélyezve van-e a SAM-fiókok és-megosztások névtelen felsorolása. Windows lehetővé teszi a névtelen felhasználók számára bizonyos műveletek végrehajtását, például a tartományi fiókok és a hálózati megosztások nevének felsorolását. Ez akkor hasznos, például, ha a rendszergazda hozzáférést szeretne biztosítani egy megbízható tartományhoz, amely nem tart fenn a kölcsönös megbízhatósági kapcsolat a felhasználók számára. Ha nem szeretné, hogy névtelen felsorolása a SAM-fiókok és a megosztások, engedélyezze ezt a házirendet.
  - **Alapértelmezett**: Igen
  
- **Távoli bejelentkezés blokkolása üres jelszót**  
  Ez a beállítás határozza meg, hogy használható-e a helyi fiókok, amelyek nem jelszóval védett, jelentkezzen be a fizikai számítógép-konzolt eltérő helyekről. Ha engedélyezve van, a helyi fiókok, amelyek nem jelszóval védett csak lesz jelentkezhetnek be, a számítógép. Figyelmeztetés: Számítógépek, amelyek nem fizikailag biztonságos helyen kell mindig erős jelszót szabályzatok érvényesítését a minden helyi felhasználói fiókokhoz. Ellenkező esetben a számítógéphez fizikai hozzáféréssel rendelkező felhasználók jelentkezhetnek be a jelszót nem rendelkező felhasználói fiókkal. Ez különösen fontos a hordozható számítógépekhez. Ha a biztonsági házirendet a Mindenki csoportra alkalmazza, senki nem tud bejelentkezni a távoli asztali szolgáltatások használatával. Ez a beállítás nem befolyásolja a bejelentkezések, amelyek tartományi fiókokat használ. Ezzel a beállítással megkerülésére távoli interaktív bejelentkezést használó alkalmazások számára lehetőség.
  - **Alapértelmezett**: Igen
  
- **Jogosultságszint-emelési kérés működése általános jogú felhasználó**  
  Ez a szabályzatbeállítás a jogosultságszint-emelési kérés működése általános jogú felhasználók esetében viselkedését szabályozza. 0 - emelési kérések automatikus megtagadása: Egy műveletet igényel a jogok kiterjesztése, ha egy konfigurálható hozzáférés megtagadva, hibaüzenet jelenik meg. Vállalati futtató asztali számítógépek, az általános jogú felhasználó dönthet ezzel a beállítással csökkentheti a segélyszolgálatra beérkező hívások. 1 – a biztonsági asztal hitelesítő adatok kérése: Egy műveletet igényel a jogok kiterjesztése, a felhasználó a rendszer kér a biztonsági asztalon, egy másik felhasználónevet és jelszót adjon meg. Ha a felhasználó sikeresen Megadja, hogy érvényes hitelesítő adatokat, a megfelelő jogosultságokkal a művelet továbbra is. 3 (alapértelmezett) – kérdezzen rá a hitelesítő adatokat: -Művelet megköveteli a jogok kiterjesztése, amikor a rendszer kéri a felhasználót, hogy adjon meg egy rendszergazdai felhasználónevet és jelszót. Ha a felhasználó sikeresen Megadja, hogy érvényes hitelesítő adatokat, a megfelelő jogosultságokkal a művelet továbbra is.
  - **Alapértelmezett**: Jogosultságszint-emelési kérések automatikus megtagadása
  
- **A rendszergazdák rendszergazdai engedélyezéses mód megkövetelése**  
  A házirend-beállítás a felhasználói fiókok felügyelete (UAC) szabályzatok minden beállítását, a számítógép viselkedését szabályozza. Ha módosítja ezt a beállítást, újra kell indítani a számítógépet. Az alábbi lehetőségek állnak rendelkezésére: 0 – Letiltva: Rendszergazdai engedélyezéses mód és az összes kapcsolódó felhasználói fiókok Felügyeletének házirend-beállítások le vannak tiltva. Megjegyezés: Ha a házirend-beállítás le van tiltva, a Security Center értesíti, hogy a teljes biztonsági az operációs rendszer e-mailjeiket. 1 – engedélyezett: (Alapértelmezett) Rendszergazdai engedélyezéses mód engedélyezve van. Ez a szabályzat engedélyezve kell lennie, és a kapcsolódó felhasználói fiókok felügyelete házirend-beállításokat is megfelelően kell megadni, hogy a beépített Rendszergazda fiók és minden egyéb felhasználó rendszergazdai engedélyezéses módban futtatásához a Rendszergazdák csoport tagjai.
  - **Alapértelmezett**: Igen
  
- **Megakadályozza a SAM-fiókok névtelen felsorolása**  
  Ez a beállítás határozza meg, milyen további engedélyeket fog kapni a névtelen kapcsolódást a számítógéphez. Windows lehetővé teszi a névtelen felhasználók számára bizonyos műveletek végrehajtását, például a tartományi fiókok és a hálózati megosztások nevének felsorolását. Ez akkor hasznos, például, ha a rendszergazda hozzáférést szeretne biztosítani egy megbízható tartományhoz, amely nem tart fenn a kölcsönös megbízhatósági kapcsolat a felhasználók számára. Ez a beállítás lehetővé teszi, hogy a névtelen kapcsolatok a következőképpen elhelyezését további korlátozások: Engedélyezve: Enumerálás a SAM-fiókok nem engedélyezett. Ez a beállítás lecseréli mindenki hitelesített felhasználók a biztonsági engedélyek az erőforrások. Letiltva: Nincsenek további korlátozásokat. Alapértelmezett engedélyek támaszkodnak. Alapértelmezett munkaállomásokon: Engedélyezve van. Alapértelmezett kiszolgáló: Engedélyezve van.
  - **Alapértelmezett**: Igen
  
- **Lehetővé teszi a biztonsági fiókkezelő távoli hívások**  
  Ez a házirend-beállítással korlátozhatja a távoli rpc-kapcsolatok Sándornak. Ha nincs bejelölve, az alapértelmezett biztonsági leíró használható.
  - **Alapértelmezett**: *O:BAG:BAD:(A;; RC;; BA)*

- **Rendszergazdai engedélyezéses mód használata**  
  A házirend-beállítás szabályozza a rendszergazdai engedélyezéses mód a beépített rendszergazdai fiók viselkedését. A lehetőségek a következők: • engedélyezve: A beépített Rendszergazda fiók rendszergazdai engedélyezéses módban használja. Alapértelmezés szerint minden művelet, amely megköveteli a jogok kiterjesztése fogja kérni a felhasználót, hogy hagyja jóvá a műveletet. • Le van tiltva: (Alapértelmezett) A beépített rendszergazdai fiók teljes körű rendszergazdai jogosultságokkal rendelkező összes alkalmazásokat futtat.
  - **Alapértelmezett**: Igen
  
- **Felhasználói felület alkalmazásokat biztonságos hely engedélyezése**  
  Ez a házirend-beállítással megadható, hogy a felhasználói felület kisegítő (UIAccess vagy UIA) programok automatikusan letilthatják a jogosultságszint-emelési általános jogú felhasználók által használt biztonsági asztalt. Engedélyezve: Az UIA-programok, beleértve a Windows Távsegítség automatikusan letilthatják a jogosultságszint-emelési kérések asztalt. Ha nem tiltja le a "felhasználói fiókok felügyelete: Jogosultságszint-emelési kérés során átváltás biztonsági asztalra"házirend-beállítás, a kérések a biztonsági asztal helyett az interaktív felhasználó asztalán jelennek meg. Letiltva: (Alapértelmezett) A biztonsági asztalt csak az interaktív asztal felhasználója vagy letiltásával tiltható a "felhasználói fiókok felügyelete: Jogosultságszint-emelési kérés során átváltás biztonsági asztalra"házirend-beállítást.
  - **Alapértelmezett**: Igen

- **Észlelheti és figyelmeztetés a jogosultságszint-emeléshez**  
  Ezzel a szabályzatbeállítással az alkalmazások telepítésének észlelése a számítógép viselkedését szabályozza. Az alábbi lehetőségek állnak rendelkezésére: Engedélyezve: (Alapértelmezett) Észlelésekor alkalmazás telepítési csomagot, amely megköveteli a jogok kiterjesztése, a rendszer kéri a felhasználót, hogy adjon meg egy rendszergazdai felhasználónevet és jelszót. Ha a felhasználó sikeresen Megadja, hogy érvényes hitelesítő adatokat, a megfelelő jogosultságokkal a művelet továbbra is. Letiltva: Alkalmazáscsomagok telepítési nem észlelhető, és kéri a jogosultságszint-emeléshez. Olyan vállalatok, amelyek általános jogú felhasználók futnak, és használja a telepítési technológiák, például a csoportházirend szoftvertelepítési meghatalmazott, vagy a Systems Management Server (SMS) tiltsa le a házirend-beállítás. Ebben az esetben a telepítő észlelése nem szükséges.
  - **Alapértelmezett**: Igen
  
- **A következő jelszómódosításkor tárolja a LAN-kezelő üzenetkivonatát megakadályozása**  
  Ez a beállítás határozza meg, ha jelenleg a következő jelszómódosításkor az új jelszó LAN Manager-(LM-) ujjlenyomat értékét tárolja. Az LM-kivonat viszonylag gyenge, és a titkosítási szempontból erősebb Windows NT-kivonat szemben a hibalehetőség. Mivel az LM-kivonat a biztonsági adatbázisban a helyi számítógépen tárolt jelszavak is sérülhet, ha a biztonsági adatbázis megtámadott.
  - **Alapértelmezett**: Igen

- **Fájl- és beállításjegyzék-írási hibák száma a felhasználó tartózkodási helye virtualizálása**  
  Ez a házirend-beállítással megadható, hogy az alkalmazás-írási hibák a rendszer átirányítja megadott beállításjegyzékbeli és fájlrendszerbeli helyekre. Ezzel a szabályzatbeállítással megszünteti a Futtatás rendszergazdaként, és az alkalmazás adatokat írni: % ProgramFiles %, % Windir %, % Windir%\system32 vagy HKLM\Software alkalmazásokhoz.
  - **Alapértelmezett**: Igen

## <a name="ms-security-guide"></a>MS biztonsági útmutató  
További információkért lásd: [házirend CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) a Windows dokumentációjában.  

- **A felhasználói fiókok Felügyeletének korlátozásokat lehessen alkalmazni a hálózati bejelentkezés helyi fiókhoz**  
    - **Alapértelmezett**: Engedélyezve
  
- **SMB v1 ügyfél illesztőprogram kezdő konfigurálása**  
  - **Alapértelmezett**: Letiltott illesztőprogram
  
- **SMB-kiszolgáló v1**  
  - **Alapértelmezett**: Letiltva
  
- **Kivonatoló hitelesítés**  
  - **Alapértelmezett**: Letiltva
  
- **Strukturált kivételkezelés védelmi felülírása**  
  - **Alapértelmezett**: Engedélyezve
  
## <a name="mss-legacy"></a>MSS örökölt  
További információkért lásd: [házirend CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) a Windows dokumentációjában.  

- **Hálózati IP-forrás védelmi szint Útválasztás**  
  - **Alapértelmezett**: Legmagasabb szintű védelme 
  
- **Hálózati figyelmen kívül hagyja a NetBIOS név kiadás kivételével érkező kérelmeket a WINS-kiszolgálók**  
  - **Alapértelmezett**: Engedélyezve
  
- **Hálózati IPv6 forrás útválasztási védelmi szint**  
  - **Alapértelmezett**: Legmagasabb szintű védelme

- **Hálózati ICMP átirányítások generált OSPF felülbírálása**  
  - **Alapértelmezett**: Letiltva
  
## <a name="power"></a>Energiagazdálkodási  
További információkért lásd: [házirend CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) a Windows dokumentációjában.  

- **Az ébresztési áramforráshoz jelszó kérése**  
  A házirend-beállítás megadja-e a felhasználó kéri a jelszót, amikor a rendszer visszatér az alvó állapotból. Engedélyezi, vagy nem konfigurálja ezt a beállítást, ha a felhasználó értesítése a jelszót a rendszer visszatér az alvó állapotból. Ha letiltja ezt a beállítást, a felhasználó nem kéri a jelszó, amikor a rendszer visszatér az alvó állapotból.
  - **Alapértelmezett**: Engedélyezve
  
- **Az akkumulátor alvó állapotba helyezésekor készenléti állapotok**  
  Ezzel a szabályzatbeállítással kezeli a Windows a számítógép alvó állapotba helyezésekor készenléti állapotok használata engedélyezett-e. Engedélyezi, vagy nem konfigurálja ezt a beállítást, ha Windows alvó állapotba helyezni a számítógép készenléti állapotok használja. Ha letiltja ezt a beállítást, a készenléti állapotok (S1-S3) nem engedélyezettek.
  - **Alapértelmezett**: Letiltva
  
- **Készenléti állapotok áramforráshoz alvó állapotba helyezésekor**  
  Ezzel a szabályzatbeállítással kezeli a Windows a számítógép alvó állapotba helyezésekor készenléti állapotok használata engedélyezett-e. Engedélyezi, vagy nem konfigurálja ezt a beállítást, ha Windows alvó állapotba helyezni a számítógép készenléti állapotok használja. Ha letiltja ezt a beállítást, a készenléti állapotok (S1-S3) nem engedélyezettek.
  - **Alapértelmezett**: Letiltva
  
- **Az akkumulátor jelszót igényel**  
  A házirend-beállítás megadja-e a felhasználó kéri a jelszót, amikor a rendszer visszatér az alvó állapotból. Engedélyezi, vagy nem konfigurálja ezt a beállítást, ha a felhasználó értesítése a jelszót a rendszer visszatér az alvó állapotból. Ha letiltja ezt a beállítást, a felhasználó nem kéri a jelszó, amikor a rendszer visszatér az alvó állapotból.
  - **Alapértelmezett**: Engedélyezve
  
## <a name="remote-desktop-services"></a>Távoli asztali szolgáltatások  
További információkért lásd: [házirend CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) a Windows dokumentációjában.  

- **Jelszó mentésének letiltása**  
  Azt szabályozza, hogy jelszavakat menthetők-e ezen a számítógépen a távoli asztali kapcsolat. Ha engedélyezi ezt a beállítást a jelszó mentése jelölőnégyzetet a távoli asztali kapcsolat le lesz tiltva, és a felhasználók többé nem tudják menteni a jelszavakat. Ha egy felhasználó megnyitja a távoli asztali kapcsolattal egy RDP-fájlt, és menti a beállításokat, minden jelszót, amely korábban már létezett az RDP-fájlt az törlődik. Ha letiltja ezt a beállítást, vagy hagyja üresen a nincs konfigurálva, a felhasználó fogja tudni menteni a távoli asztali kapcsolattal jelszavakat.
  - **Alapértelmezett**: Engedélyezve
  
- **Biztonságos RPC-kommunikációhoz**  
  Itt adhatja meg, hogy egy távoli asztali munkamenetgazda-kiszolgáló összes ügyfél a biztonságos RPC-kommunikáció vagy lehetővé teszi a biztonságos kommunikációt. Ez a beállítás segítségével RPC-kommunikáció az ügyfelek biztonságának fokozását azáltal, hogy csak hitelesített és titkosított kérelmeket. Ha a beállítás engedélyezve van, a távoli asztali szolgáltatások, amelyek támogatják a biztonságos kérelmek RPC-ügyfelektől érkező kéréseket fogad, és nem biztonságos kommunikáció engedélyezése a nem megbízható ügyfeleket. Ha a beállítás le van tiltva, a távoli asztali szolgáltatások mindig kérelmek biztonsági minden RPC-forgalom. Azonban nem biztonságos kommunikáció engedélyezett RPC-ügyfelek, amelyek nem válaszolnak a kérelmet. Ha a beállítás nincs konfigurálva, nem biztonságos kommunikáció engedélyezve van. Megjegyezés: Az RPC felület felügyelete és konfigurálása a távoli asztali szolgáltatások szolgál.
  - **Alapértelmezett**: Engedélyezve
  
- **Meghajtó blokkátirányítás**  
  A házirend-beállítás megadja, hogy a leképezés egy távoli asztali szolgáltatások munkamenet (meghajtón átirányítást) ügyfélmeghajtók elkerülése érdekében. Alapértelmezés szerint egy távoli asztali munkamenetgazda-kiszolgálóhoz kapcsolódáskor automatikusan ügyfélmeghajtók képezi le. Csatlakoztatott meghajtók munkamenet ebben a mappafában levő a fájlkezelő vagy a számítógép a következő formátumban jelenik meg  *\<meghajtóbetűjel >* a  *\<számítógép_neve >*. A házirend-beállítás használatával bírálja felül ezt a viselkedést. Ha ez a szabályzatbeállítás engedélyezi, ügyfél meghajtón átirányítást nem engedélyezett a távoli asztali munkamenetekhez és vágólapra másolás-átirányítási fájlt a Windows Server 2003, Windows 8 és Windows XP rendszert futtató számítógépeken nem engedélyezett. Ha letiltja ezt a beállítást, az ügyfél meghajtón átirányítást mindig engedélyezve van. Vágólapra másolás-átirányítási fájlt Ezenkívül mindig engedélyezett, ha a vágólapra átirányítás használata engedélyezett. Ha nem adja meg a házirend-beállítás, ügyfél meghajtón átirányítást, vágólapra másolás-átirányítási fájlt nincs megadva a csoportházirend szintjén.
  - **Alapértelmezett**: Engedélyezve
  
- **Jelszó kérése**  
  A házirend-beállítás megadja-e a távoli asztali szolgáltatások mindig kérni fogja az ügyfél egy a jelszót. Ezzel a beállítással használhatja a kényszerítéséhez a felhasználók a távoli asztali szolgáltatásokhoz, a bejelentkezés jelszó megadására, akkor is, ha már megadta a jelszót a távoli asztali kapcsolat-ügyfél. Alapértelmezés szerint a távoli asztali szolgáltatások lehetővé teszi a felhasználóknak a jelszó beírásával a távoli asztali kapcsolat-ügyfél automatikus bejelentkezésre. Ha ez a szabályzatbeállítás engedélyezi, felhasználók nem lehet automatikusan jelentkezzen be a távoli asztali szolgáltatások a távoli asztali kapcsolat ügyfél jelszavuk megadásával. Jelentkezzen be a jelszót kérni. Ha letiltja ezt a beállítást, felhasználók is mindig jelentkezzen be a távoli asztali szolgáltatások automatikusan a távoli asztali kapcsolat ügyfél jelszavuk megadásával. Ha letiltja ezt a beállítást, az automatikus bejelentkezés nincs megadva a csoportházirend szintjén. 
  - **Alapértelmezett**: Engedélyezve
  
- **A távoli asztali szolgáltatások ügyfél kapcsolat titkosítási szint**  
  Megadja, hogy az ügyfélszámítógépek és a távoli asztali munkamenetgazda-kiszolgálók közötti kommunikáció biztonságossá tételéhez a távoli asztal protokoll (RDP) kapcsolatokat során egy adott titkosítási szint használata szükséges. Ez a szabályzat csak akkor érvényes, ha natív RDP-titkosítást használ. Natív RDP-titkosítást (nem SSL-titkosítást) azonban nem ajánlott. Ez a szabályzat nem vonatkozik az SSL-titkosítást. Ha ez a szabályzatbeállítás engedélyezi, távoli kapcsolatok során az ügyfelek és távoli asztali munkamenetgazda-kiszolgálók közötti minden kommunikáció ebben a beállításban megadott titkosítási módszert kell használnia. Alapértelmezés szerint a magas titkosítási szint van beállítva. Az alábbi titkosítási módszerek érhetők el:  
  - *Magas*: A magas beállítást titkosítja az adatokat, az ügyfél és a kiszolgáló és a kiszolgáló az ügyfélnek küldött erős 128 bites titkosítás segítségével. A titkosítási szint csak 128 bites ügyfeleket (például futtató ügyfelek távoli asztali kapcsolat) környezetekben használható. Ügyfelek, amelyek nem támogatják a titkosítási szint nem tud kapcsolódni a távoli asztali munkamenetgazda-kiszolgálók.  
  - *Az ügyfél kompatibilis*: Az ügyfél-kompatibilis beállítás az ügyfél és a kiszolgáló, az ügyfél által támogatott legerősebb között küldött adatok titkosítására. A titkosítási szint környezetekben, beleértve az ügyfelek, amelyek nem támogatják a 128 bites titkosítás használata.  
  - *Alacsony*: Az alacsony beállítással csak az ügyfél által küldött a kiszolgálónak 56-bites titkosítás segítségével adatokat titkosítja.  
  
  Ha letiltja vagy nem konfigurálja ezt a beállítást, a távoli asztali munkamenetgazda-kiszolgálók távoli kapcsolatokhoz használt titkosítási szint nincs alkalmazva csoportházirend segítségével. A FIPS fontos a rendszer-kriptográfia keresztül konfigurálhatók. A FIPS előírásainak megfelelő algoritmusok használata titkosításhoz, kivonatoláshoz és aláíráshoz (a Számítógép konfigurációja\A Windows beállításai\Biztonsági beállítások\Helyi házirend\Biztonsági beállítások.) a csoportházirend beállításai A FIPS előírásainak megfelelő beállítás titkosítja, és mindig visszafejti az adatokat az ügyfél és a kiszolgáló és a kiszolgáló az ügyfélnek a Federal Information Processing Standard (FIPS) 140 titkosítási algoritmussal küldött Microsoft titkosítási modulok használatával. Ügyfelek és a távoli asztali munkamenetgazda-kiszolgálók közötti kommunikációhoz szükséges a legmagasabb szintű titkosítást használni a titkosítási szint.
  - **Alapértelmezett**: Magas
  
## <a name="remote-management"></a>Távfelügyelet  
További információkért lásd: [házirend CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) a Windows dokumentációjában.  

- **A Blokkblob tárolás futtató tartozó hitelesítő adatok**  
  Ügyfél alapszintű hitelesítés
  - **Alapértelmezett**: Engedélyezve
  
- **Alapszintű hitelesítés**  
  A házirend-beállítás lehetővé teszi, hogy kezelheti-e a Windows Rendszerfelügyeleti (webszolgáltatások WinRM) szolgáltatás fogad el az alapszintű hitelesítés, a távoli ügyfélhez. Ha ez a szabályzatbeállítás engedélyezi, a WinRM szolgáltatás alapszintű hitelesítés, a távoli ügyfélhez fogad el. Ha letiltja vagy nem konfigurálja ezt a beállítást, a WinRM szolgáltatás nem fogadja el a távoli ügyfélhez egyszerű hitelesítést.
  - **Alapértelmezett**: Letiltva
  
- **Ügyfél-kivonatoló hitelesítés letiltása**  
  Ez a házirend-beállítással kezelheti, hogy a Windows Rendszerfelügyeleti (webszolgáltatások WinRM) ügyfél használja a kivonatoló hitelesítés. Ha ez a szabályzatbeállítás engedélyezi, a WinRM-ügyfél nem használja a kivonatoló hitelesítés. Ha letiltja vagy nem konfigurálja ezt a beállítást, a WinRM-ügyfél használja a kivonatoló hitelesítés.
  - **Alapértelmezett**: Engedélyezve
  
- **Nem titkosított forgalmat**  
  A házirend-beállítás lehetővé teszi, hogy szabályozhatja, hogy a Windows Rendszerfelügyeleti (webszolgáltatások WinRM) szolgáltatás elküldi a hálózaton keresztül nem titkosított üzeneteket fogad. Ha ez a szabályzatbeállítás engedélyezi, a WinRM-ügyfél küld, és nem titkosított üzeneteket fogad a hálózaton keresztül. Ha letiltja vagy nem konfigurálja ezt a beállítást, a WinRM-ügyfél üzeneteket küldő vagy fogadó csak titkosított a hálózaton keresztül.  
  - **Alapértelmezett**: Letiltva
  
- **Titkosítatlan ügyfél forgalmát**  
  Ez a házirend-beállítással kezelheti, hogy a Windows Rendszerfelügyeleti (webszolgáltatások WinRM) ügyfél küld, és nem titkosított üzeneteket fogad a hálózaton keresztül. Ha ez a szabályzatbeállítás engedélyezi, a WinRM-ügyfél küld, és nem titkosított üzeneteket fogad a hálózaton keresztül. Ha letiltja vagy nem konfigurálja ezt a beállítást, a WinRM-ügyfél üzeneteket küldő vagy fogadó csak titkosított a hálózaton keresztül.
  - **Alapértelmezett**: Letiltva
  
- **Ügyfél alapszintű hitelesítés**  
  A házirend-beállítás lehetővé teszi, hogy kezelheti-e a Windows Rendszerfelügyeleti (webszolgáltatások WinRM) ügyfél egyszerű hitelesítést használ. Ha ez a szabályzatbeállítás engedélyezi, a WinRM-ügyfél alapszintű hitelesítést használ. Ha a Rendszerfelügyeleti webszolgáltatások HTTP protokollon használatára van konfigurálva, a felhasználónév és jelszó érkeznek a hálózaton egyszerű szövegként. Ha letiltja vagy nem konfigurálja ezt a beállítást, a WinRM-ügyfél nem használja az egyszerű hitelesítés.
  - **Alapértelmezett**: Letiltva
  

## <a name="remote-procedure-call"></a>A távoli eljáráshívás  
További információkért lásd: [házirend CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) a Windows dokumentációjában.  

- **Nem hitelesített RPC-ügyfél beállításai**  
  A házirend-beállítás határozza meg, hogyan kezeli az RPC-kiszolgáló modul a nem hitelesített RPC-ügyfelekhez RPC-kiszolgálók. A házirend-beállítás hatással van minden RPC-alkalmazást. Tartományi környezetben a házirend-beállítás használandó legyen körültekintő, számos különféle funkcióit, többek között a Csoportházirend általi feldolgozás maga hatással lehet. Visszaállítás a házirend-beállítás módosítása az összes érintett manuális beavatkozásra lehet szükség. A házirend-beállítás egy olyan tartományvezérlőre, amely soha nem kell alkalmazni. Ha letiltja ezt a beállítást, az RPC-kiszolgáló modul a Windows ügyfél és az értéke "None", amely támogatja a házirend-beállítás a Windows Server-verziók a "Hitelesített" értékét használja. Ha nem adja meg a házirend-beállítás érvényben marad. A kiszolgáló távoli Eljáráshívás futásideje fog viselkedni, mintha a következő értékkel: "Hitelesített" Windows ügyfél és az értéke "None" használt kiszolgáló SKU-k, amelyek támogatják a házirend-beállítás engedélyezve lett. Ha ez a szabályzatbeállítás engedélyezi, a távoli Eljáráshívás kiszolgálói futásideje korlátozása a nem hitelesített RPC-ügyfelekhez gépen futó RPC-kiszolgálók irányítja. Egy ügyfél akkor minősül egy hitelesített ügyfél, ha egy nevesített csövet a kiszolgálóval való kommunikációra használ, vagy ha eljáráshívást használ. Lehet, hogy kifejezetten kérte nem hitelesített ügyfelek számára érhető el RPC-interfészek kiválasztott házirend-beállítás értékétől függően ez a korlátozás alól.  
  - *Nincs* lehetővé teszi, hogy az összes RPC-ügyfelek, amelyeken a házirend-beállítást alkalmazza, a gépen futó RPC-kiszolgálókhoz való kapcsolódáshoz. 
  - *Hitelesített* lehetővé teszi, hogy csak hitelesített RPC-ügyfelek száma (a fenti definíció) RPC-kiszolgálóhoz csatlakozzon, amelyen a házirend-beállítást alkalmazza, a gépen futó. Kivételek megadott felületek, amelyek a kért őket. 
  - *Kivételek nélkül hitelesített* lehetővé teszi, hogy csak hitelesített RPC-ügyfelek száma (a fenti definíció) RPC-kiszolgálóhoz csatlakozzon, amelyen a házirend-beállítást alkalmazza, a gépen futó. Nincsenek kivételek engedélyezettek. Megjegyezés: Ez a szabályzatbeállítás nem lépnek érvénybe, amíg a rendszer újraindítása.  

  - **Alapértelmezett**: Hitelesített

## <a name="search"></a>Keresés 
További információkért lásd: [házirend CSP - keresés](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) a Windows dokumentációjában.  

- **Titkosított elemek-indexelés letiltása**  
  Engedélyezi vagy tiltja az elemek indexelését. Ez a kapcsoló aktiválva van a Windows Search indexelő, amely meghatározza, hogy az indexeli a Windows Information Protection (WIP) által védett fájlok például olyan titkosított elemeket. A szabályzat engedélyezésekor a WIP által védett elemek indexelve lesznek, a velük kapcsolatos metaadatok pedig titkosítatlan helyen lesznek tárolva. A metaadatok között szerepel egyebek között a fájl elérési útja és módosításának dátuma. A szabályzat tiltásakor a WIP által védett elemek nem lesznek indexelve és nem jelennek meg a Cortana vagy a fájlkezelő eredményei között. Is lehet a teljesítményre gyakorolt hatás a fényképek és a Groove alkalmazás van-e nagy mennyiségű WIP-védelemmel ellátott médiafájl az eszközön.
  - **Alapértelmezett**: Igen
  
## <a name="smart-screen"></a>SmartScreen  
További információkért lásd: [házirend CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) a Windows dokumentációjában.  

- **Nem ellenőrzött fájlok futtatásának letiltása**  
  A felhasználó nem futtathat ellenőrizetlen fájlokat. 0 – alkalmazottak figyelmen kívül hagyhatja a SmartScreen-figyelmeztetések és futtatási kártevő fájlokat. 1 – az alkalmazottak nem SmartScreen vonatkozó figyelmeztetések mellőzése és a rosszindulatú fájlok futtatásának.
  - **Alapértelmezett**: Igen

- **Ellenőrizetlen fájlletöltés letiltása**  
  Alapértelmezés szerint a Microsoft Edge lehetővé teszi a felhasználók kihagyhatják (figyelmen kívül hagyása) a Windows Defender SmartScreen-figyelmeztetések potenciálisan kártékony fájlokkal, lehetővé teheti, hogy továbbra is a nem ellenőrzött fájlok letöltésével kapcsolatos. E szabályzat engedélyezésével megakadályozza, hogy felhasználók letiltják őket a nem ellenőrzött fájlok letöltése a figyelmeztetések mellőzése.
  - **Alapértelmezett**: Igen
  
- **SmartScreen-üzenetek szükséges alkalmazások és fájlok**  
  Lehetővé teszi a rendszergazdáknak, hogy a Windows SmartScreen konfigurálása.
  - **Alapértelmezett**: Igen
  
## <a name="system"></a>Rendszer  
További információkért lásd: [házirend CSP - rendszer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) a Windows dokumentációjában.  

- **A rendszer rendszerindító kezdő illesztőprogram inicializációja**  
  A házirend-beállítás lehetővé teszi, hogy adja meg, milyen rendszerindítás illesztőprogramok inicializálása alapján határozza meg a rendszerindítás korai indítsa el a kártevőirtó vezető besorolást. A rendszerindítás korai indítsa el a kártevőirtó illesztőprogram adhat vissza minden egyes rendszerindítás illesztőprogram a következő besorolásokkal: – hasznos: Az illesztőprogram aláírással rendelkezik, és nem módosították.  
  - *Hibás* – az illesztőprogramot, kártevő szoftverek lett azonosítva. Javasoljuk, hogy nem engedélyezi az ismert hibás illesztőprogramok inicializálása. – Hibás, de a rendszerindításhoz szükséges: Az illesztőprogram kártevő néven azonosított, de a számítógép nem tudja sikeresen rendszerindítást anélkül, hogy az illesztőprogram betöltése. 
  - *Ismeretlen* – Ez az illesztőprogram a kártevő szoftverek észlelése alkalmazás nem igazolják, és a rendszerindítás korai indítsa el a kártevőirtó illesztőprogram nincs besorolva.  

  Ha ez a szabályzatbeállítás engedélyezi, választhat, mely rendszerindítás illesztőprogramok inicializálása a számítógép következő indításakor fogjuk. Ha letiltja vagy nem konfigurálja ezt a házirendet beállítást, a rendszerindító kezdő illesztőprogramokkal minősül jó, ismeretlen vagy hibás, de rendszerindító kritikus inicializálva és minősül hibás illesztőprogramok inicializálása a rendszer kihagyta. Ha a kártevő-észlelési alkalmazását nem tartalmaz egy rendszerindítás korai indítsa el a kártevőirtó illesztőprogram, vagy ha a korai indítási kártevőirtó rendszerindítás illesztőprogram le van tiltva, ez a beállítás nem befolyásolja, és minden rendszerindítás illesztőprogramok inicializálása.  
  - **Alapértelmezett**: Jó ismeretlen és a kritikus fontosságú hibás

## <a name="wi-fi"></a>Wi-Fi  
További információkért lásd: [házirend CSP - Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) a Windows dokumentációjában.  

- **Wi-Fi**  
  Megadja, hogy internetmegosztást az eszközön.
  - **Alapértelmezett**: Igen  

- **Blokk automatikus csatlakozás Wi-Fi elérési pontokhoz**  
  Engedélyezése vagy letiltása az eszközön való automatikus csatlakozás Wi-Fi elérési pontokhoz.  
  - **Alapértelmezett**: Igen  
  
## <a name="windows-connection-manager"></a>Windows Connection Manager  
További információkért lásd: [házirend CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) a Windows dokumentációjában.  

- **Kapcsolat blokkolása, nem tartományi hálózatokon**  
  A házirend-beállítás megakadályozza, hogy a számítógép csatlakozik egy tartományalapú hálózattal és a egy tartományon kívüli alapú hálózati egyszerre. Ha a házirend-beállítás engedélyezve van, a számítógép válaszoljon a következő esetekben alapján automatikus és manuális hálózati csatlakozási kísérletek: 
  - Ha a számítógép tartományi hálózathoz, minden automatikus kapcsolódási kísérletek nem tartományi hálózathoz már csatlakoztatva van az automatikus csatlakozási kísérletek le vannak tiltva. Amikor a számítógép már csatlakozik egy tartományon kívüli alapú hálózati, tartományi hálózatokhoz automatikus csatlakozási kísérletek le lesznek tiltva. 
  - Manuális csatlakozási kísérletek, amikor a számítógép már csatlakozik vagy egy tartományhoz nem hálózati vagy a tartományi hálózaton keresztül media eltérő Ethernet és a egy felhasználó megpróbál egy további hálózathoz való manuális kapcsolat létrehozása ezen a jelen szabályzat megsértése beállítás, a meglévő hálózati kapcsolat megszakad, és a manuális kapcsolódás engedélyezett. Amikor a számítógép már csatlakozik vagy egy nem tartományi alapú hálózati vagy a tartományi hálózaton over Ethernet, és a egy felhasználó megpróbál egy további hálózathoz való manuális kapcsolat létrehozása szabályzatsértéséről, a házirend-beállítás, a meglévő Ethernet-kapcsolat szigorúan betartja, és a manuális csatlakozási kísérlet le van tiltva.  

  Ha a házirend-beállítás nincs konfigurálva, vagy le van tiltva, a számítógépek csatlakozni egyszerre a tartomány és a nem tartományi hálózatokon is engedélyezettek.
  - **Alapértelmezett**: Engedélyezve
  
## <a name="windows-defender"></a>Windows Defender  
További információkért lásd: [házirend CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) a Windows dokumentációjában.  

- **A bejövő e-mailek vizsgálata**  
  Engedélyezi vagy letiltja az e-mailek vizsgálata.
  - **Alapértelmezett**: Igen  

- **Office-alkalmazások indítsa el a gyermek-folyamat típusa**  
  Office-alkalmazások nem lesz engedélyezett szükséges gyermekelemek létrehozásához a folyamatokat. Ez magában foglalja a Word, Excel, PowerPoint, a OneNote és a hozzáférés. Ez az egy tipikus kártevő szoftverek, különösen a makró-alapú támadásokkal szemben, amelyek az Office-alkalmazások elindításához, vagy letöltheti a rosszindulatú végrehajtható fájlok.
  - **Alapértelmezett**: Letiltás
  
- **Defender minta küldésének jóváhagyás típusa**  
  A felhasználó hozzájárul a szint a Windows Defender adatküldéshez. Ha már rendelkezik a szükséges feltételeket, a Windows Defender küldi el őket. Ha nem, (és ha a felhasználó soha nem szeretne feltenni által megadott), a felhasználói felület a felhasználó hozzájárulását (amikor a Defender/AllowCloudProtection engedélyezett) az adatok küldésének kérjen indul el.
  - **Alapértelmezett**: Biztonságos minták automatikus küldése 
  
- **Aláírás-frissítési időköz (óra)**  
  Defender aláírás-frissítési időköz (óra)
  - **Alapértelmezett**: 4
  
- **Parancsfájl letöltött tartalom végrehajtási típusa**  
  Defender parancsfájl letöltött tartalom végrehajtási típusa
  - **Alapértelmezett**: Letiltás
  
- **Hitelesítő adatok lopásának megjelölése típus megakadályozása**  
  Windows Defender Credential Guard virtualizálás-alapú biztonsági használatával elkülöníteni a titkos kódok, hogy csak a kiemelt jogosultságú rendszerszoftverek férhessenek hozzá őket. A titkos kódokhoz való illetéktelen hozzáférés a hitelesítési adatok ellopását okozó (például pass-the-hash vagy pass-the-ticket típusú) támadásokhoz vezethetnek. Windows Defender Credential Guard megakadályozza, hogy ezeket a támadásokat NTLM-jelszókivonatok, a Kerberos jegymegadási jegyek és a tartományi hitelesítő adatok, alkalmazások által tárolt hitelesítő adatok ellenőrzését.
  - **Alapértelmezett**: Engedélyezés

- **E-mailek tartalmának végrehajtási típus**  
  Ez a szabály letiltja a legyenek a következő fájltípusokat, futtatása vagy a Microsoft Outlook vagy a webes levelezésben (például Gmail.com vagy Outlook.com) látható e-mailt indított: Végrehajtható fájl (például .exe, .dll vagy .scr) fájlok, parancsfájlok (például egy PowerShell .ps, Basic .vbs vagy .js JavaScript-fájl) parancsfájl archív fájlokban.
  - **Alapértelmezett**: Letiltás
  
- **Hálózati védelem típusa**  
  Ez a szabályzat lehetővé teszi a hálózatvédelem (blokk vagy naplózási) kapcsolja be vagy ki a Windows Defender Exploit Guard. Hálózatvédelem funkciója a Windows Defender Exploit Guard, amely védelmet biztosít az alkalmazottak az Internet elérésére folytathatnak, a biztonsági rés kiaknázása elleni futtató helyek és a rosszindulatú bármilyen alkalmazást használja. Ez magában foglalja, megakadályozza, hogy a külső böngészők veszélyes helyekre csatlakozzanak. Értéktípus: egész szám. Ha engedélyezi ezt a beállítást, hálózati védelem be van kapcsolva, és az alkalmazottak nem kapcsolhatja ki. A következő beállítások szabályozhatók működését: Blokk- és naplózási. Ha engedélyezi ezt a házirendet, a "Letiltás" beállítás, felhasználók vagy alkalmazások lesznek letiltva veszélyes tartományokhoz csatlakozzon. Ezt a tevékenységet, a Windows Defender biztonsági központban látni fogja. Ha engedélyezi ezt a házirendet, a "Naplózási" beállítással, felhasználók vagy alkalmazások nem lesznek letiltva veszélyes tartományokhoz csatlakozzon. Azonban továbbra is látni fogja ezt a tevékenységet, a Windows Defender biztonsági központban. Ha letiltja ezt a házirendet, felhasználók vagy alkalmazások nem lesznek letiltva veszélyes tartományokhoz csatlakozzon. Nem láthatja a Windows Defender biztonsági központ semmilyen hálózati tevékenységet. Ha nem konfigurálja ezt a házirendet, hálózati blokkolás letiltjuk alapértelmezés szerint.
  - **Alapértelmezett**: Engedélyezés
  
- **Defender vizsgálat napjának ütemezése**  
  Defender a vizsgálat napjának ütemezése.
  - **Alapértelmezett**: mindennap
  
- **Felhőalapú védelem**  
  Legmagasabb szintű védelme érdekében a számítógépen, a Windows Defender küld adatokat a Microsoft kapcsolatos esetleges problémákról talál. A Microsoft elemzi ezt az információt, többet megtudhat, illetve más ügyfelek számára, és továbbfejlesztett megoldásokat kínálnak.
  - **Alapértelmezett**:  Igen  

- **Defender potenciálisan nemkívánatos alkalmazás**  
  A Windows Defender víruskereső vélhetően nemkívánatos alkalmazások (elleni) védelmi szolgáltatása is azonosíthatja és letiltása végpontjaira való letöltését és telepítését a hálózaton. Ezek az alkalmazások nem lesznek figyelembe véve vírusok, kártevők vagy egyéb fenyegetések típusú, de előfordulhat, hogy műveleteket hajthat végre, amelyek hátrányosan érintik a teljesítményük, vagy használjon végpontok. ELLENI is tekintse meg az alkalmazásokat, amelyek gyenge, hogy tekintendő. Tipikus elleni működés tartalmazza: Különböző típusú hozzákapcsolása Ad-injektálás, a szoftverek webböngészőhöz illesztőprogram, és a beállításjegyzék optimalizálókat, amely észleli a problémákat, javítsa a hibákat, a kérelem fizetési azonban továbbra is a végponton, és győződjön megváltozik, vagy optimalizálások (más néven "engedélyezetlen víruskereső" programok) ezek alkalmazások növelheti a kockázat kártevő szoftverrel fertőzött folyamatban van a hálózati vezethetnek kártevőszoftver-fertőzések kell nehezebben azonosításához, és is éveim informatikai erőforrásokat az alkalmazások karbantartása.  
  - **Alapértelmezett**: Letiltás  

- **Parancsfájl rejtjelezett makró kód típusa**  
  Kártevők és más fenyegetések ellen megkísérelheti rejtse, és a rosszindulatú kódot az egyes parancsfájl fájlok elrejtése. Ez a szabály megakadályozza a parancsfájlok, amelyek futtatását úgy tűnik, hogy rejtjelezett lehet.
  - **Alapértelmezett**: Letiltás
  
- **Cserélhető adathordozók vizsgálata teljes vizsgálat során**  
  Lehetővé teszi, hogy a Windows Defender egy teljes vizsgálatok során a cserélhető meghajtókon (például flash meghajtók) rosszindulatú vagy nemkívánatos szoftverek vizsgálata. A Windows Defender víruskereső USB-eszközök végrehajtása előtt az összes fájlt megvizsgálja.
  - **Alapértelmezett**: Igen  
  
- **Archív fájlok ellenőrzése**  
  Defender vizsgálat archív fájlokban.
  - **Alapértelmezett**: Igen
  
- **Viselkedésfigyelés engedélyezése**  
  Engedélyezi vagy tiltja a funkciót a Windows Defender Viselkedésfigyelés engedélyezése. Beágyazott Windows 10, érzékelőktől gyűjtése és az operációs rendszer viselkedési jelek feldolgozni és érzékelő elküldi azokat a Windows Defender ATP, elkülönített, privát felhő példányát.
  - **Alapértelmezett**: Igen

- **Hálózati mappákból megnyitott fájlok vizsgálata**  
  Ha a fájlok írásvédettek, a felhasználó nem lesz képes eltávolítani az észlelt kártevőket.
  - **Alapértelmezett**: Igen

- **Nem megbízható USB-folyamat típusa**  
  Erről a szabályról a rendszergazdák megakadályozhatják nem aláírt vagy nem megbízható végrehajtható fájlok USB cserélhető meghajtók, például SD-kártyán futtatja.
  - **Alapértelmezett**: Letiltás
  
- **Egyéb Office-alkalmazások feldolgozásához injektálási típusa**  
  Office-alkalmazásokban, beleértve a Word, Excel, PowerPoint és OneNote-ban, nem lesz képes injektovat kód más folyamatokba. Ez általában kártevő futtatására szolgál rosszindulatú kódot próbál a víruskereső vizsgálati motorokból tevékenység elrejtéséhez.
  - **Alapértelmezett**:  Letiltás
  
- **Office-makrók letiltására szolgáló kód engedélyezése Win32 importálás típusa**  
  Kártevő használatával makró kódot az Office-fájlok importálása és a Win32 dll-fájlok, amelyek ezután felhasználhatók az API-hívásokat, hogy további fertőzéstől során a rendszer betöltése. Ez a szabály megpróbálja letiltása az Office-fájlokat tartalmaz, amely képes Win32 dll-fájlok importálása a makró-kódot. Ez magában foglalja a Word, Excel, PowerPoint és OneNote-ban.
  - **Alapértelmezett**: Letiltás  
  
- **Defender felhőalapú blokkblob szintje**  
  Defender felhőalapú blokkblob szintje.
  - **Alapértelmezett**: Nincs konfigurálva

- **Valós idejű figyelés**  
  Defender megkövetelése, valós idejű figyelését.
  - **Alapértelmezett**: Igen
  
- **Office alkalmazások végrehajtható tartalom létrehozása vagy az indítási típusa**  
  Ez a szabály a gyanús és kártékony bővítményeket és parancsfájlokat (bővítmények), hogy hozzon létre, vagy indítsa el a végrehajtható fájlok által használt jellemző viselkedés célozza. Ez a jellemző kártevő technika. Bővítmények az Office-alkalmazások által használt le lesz tiltva. Általában ezek használja a Windows Scripting Host (.wsh fájlok), amely bizonyos feladatok automatizálására, vagy adja meg a felhasználó által létrehozott bővítmény szolgáltatásai parancsfájlok futtatása
  - **Alapértelmezett**: Letiltás

## <a name="windows-ink-workspace"></a>Windows Ink-munkaterület  
További információkért lásd: [házirend CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) a Windows dokumentációjában.  

- **Ink-munkaterület**  
  Itt adhatja meg, hogy a felhasználó számára az ink-munkaterület elérését engedélyezi-e. 0 – a szabadkézi munkaterület való hozzáférés le van tiltva. A funkció ki van kapcsolva. 1 - ink-munkaterület engedélyezett (a funkció be van kapcsolva), de a zárolási képernyőn a felhasználó nem tud hozzáférni. 2 (alapértelmezett) – ink-munkaterület engedélyezett (a funkció be van kapcsolva), és a felhasználó számára engedélyezett a használatára a zárolási képernyője felett.
  - **Alapértelmezett**: Engedélyezve
 
## <a name="windows-powershell"></a>Windows PowerShell  
További információkért lásd: [házirend CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) a Windows dokumentációjában.  

- **A Power shell héjparancsfájlt naplózás letiltása**  
  A házirend-beállítás lehetővé teszi, hogy az összes PowerShell-parancsfájl bemenetében a Microsoft-Windows-PowerShell/műveleti eseménynaplóba naplózását. Ha ez a szabályzatbeállítás engedélyezi, Windows PowerShell parancsok, parancsfájl-blokkokban, funkciók és - szkriptek feldolgozása projekttárolóba interaktív módon vagy az automatizálás hív-e. Ha letiltja ezt a beállítást, a PowerShell parancsfájl bemenetében naplózása le van tiltva. A parancsfájl blokk meghívása a naplózás engedélyezése, a PowerShell emellett naplók eseményeket egy parancs, parancsfájl-blokkon, függvény vagy parancsfájl meghívását elindul vagy leáll. Eseménynaplók nagy mennyiségű meghívási naplózásának engedélyezéséről állít elő. Megjegyezés: A házirend-beállítás létezik, a számítógép konfigurációja és a felhasználói beállítást a csoportházirend-szerkesztőben. A számítógép-konfigurációs házirend-beállítás élvez a felhasználó-konfigurációs házirend-beállítást.
  - **Alapértelmezett**: Engedélyezve
 
