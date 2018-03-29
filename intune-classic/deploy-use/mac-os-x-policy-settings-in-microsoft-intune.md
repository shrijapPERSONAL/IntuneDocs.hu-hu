---
title: Mac OS X-szabályzatbeállítások
description: Az Intune számos beépített beállítási lehetőséget kínál Mac OS X-eszközökön, amelyeket konfigurálhat. Ezen kívül használhatja az Apple Configurator eszközt is olyan egyéni beállítások létrehozására, amelyek nem érhetők el az Intune-ban.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 873b1041ec7f5a993195e4a988580fd88100b282
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="mac-os-x-configuration-policy-settings-in-microsoft-intune"></a>A Mac OS X-konfigurációs házirendek beállításai a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Intune számos beépített beállítási lehetőséget kínál Mac OS X-eszközökön, amelyeket konfigurálhat. Ezen kívül használhatja az Apple Configurator eszközt is olyan egyéni beállítások létrehozására, amelyek nem érhetők el az Intune-ban.

## <a name="general-configuration-policy-settings"></a>Az általános konfigurációs szabályzat beállításai

A Microsoft Intune **Mac OS X-hez készült általános konfigurációs szabályzatát** a következő beállítások konfigurálásához használhatja:

-   **Az eszköz biztonsági beállításai**. Az előre meghatározott beállítások listájából választva számos szolgáltatást és funkciót szabályozhat az eszközökön.

-   **Megfelelő és nem megfelelő alkalmazások**. Adja meg a vállalatnál megfelelőnek vagy nem megfelelőnek ítélt alkalmazások listáját. A szabályzatoknak nem megfelelő alkalmazásokról készült jelentésben ellenőrizhető, hogy a listában megadott alkalmazás kompatibilis-e a felhasználók által telepített alkalmazásokkal (az alkalmazás telepítése azonban nem tiltható le).

Ha ez a lista nem tartalmazza a keresett beállítást, próbálja meg létrehozni egy egyéni Mac OS X-szabályzattal, amely lehetővé teszi az Apple Configurator eszközzel létrehozott beállítások importálását. További információkért lásd a jelen témakörben alább található „Egyéni szabályzatbeállítások” című részt.

### <a name="password-settings"></a>Jelszóbeállítások

|Beállítás neve|Részletek|
|----------------|---------------|
|**Jelszó kérése az eszközzárolás feloldásához**|Adja meg, hogy a felhasználónak kötelező legyen-e jelszót használnia Mac-számítógépe eléréséhez. **Fontos:** Az IOS-eszközöktől eltérően a Mac OS X-eszközökön a felhasználó nem azonnal kap jelszófrissítési értesítést a beállításnak való megfelelés érdekében.|
|**Kötelező jelszótípus**|Adja meg, hogy a jelszó csak **numerikus** lehet-e, vagy **alfanumerikusnak** kell lennie (azaz betűket és számokat is tartalmaznia kell). **Fontos:** Ezt a beállítást csak a Mac OS X 10.10.3-as és újabb verziói támogatják.|
|**Jelszó speciális karaktereinek minimális száma**|Adja meg a jelszóban használandó speciális karakterek minimális számát (**0** - **4**).<br /><br />A speciális karakterek szimbólumok, mint például a kérdőjel (**?**).|
|**Jelszó minimális hossza**|Adja meg a jelszó minimális hosszát (**4** - **14** karakter).|
|**Egyszerű jelszavak engedélyezése**|Az egyszerű jelszavak (például a **0000**vagy az**1234**) használatának engedélyezése.|
|**Jelszó kérése ennyi perc inaktivitás után**|Adja meg, hogy mennyi ideig legyen a számítógép inaktív ahhoz, hogy bekapcsoljon a jelszavas zárolás.|
|**Jelszó lejárata (nap)**|Adja meg, hogy hány nap telhet el a kötelező jelszómódosításig (**1** **255** nap).|
|**Jelszóelőzmények megjegyzése**|Ez a beállítás megakadályozza, hogy a felhasználó egy korábban már használt jelszót adjon meg újra. A beállítás engedélyezése esetén a **Korábbi jelszavak újbóli használatának tiltása** beállítással megadhatja, hogy hány korábbi jelszó ne legyen újra felhasználható (**1** - **24**).|
|**Képernyőkímélő bekapcsolása ennyi perc inaktivitás után**|Adja meg, hogy a számítógépnek mennyi ideig kell inaktívnak lennie a képernyőkímélő aktiválásához.|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>A szabályzatnak megfelelő és nem megfelelő alkalmazásokra vonatkozó beállítások
A **Szabályzatnak megfelelő és nem megfelelő alkalmazások Mac OS X-es eszközökhöz** listában engedélyezze az **Eszközök felügyelt beállításai** beállítást, majd adja meg a megfelelő vagy nem megfelelő alkalmazások listáját az alábbi információk alapján.

> [!NOTE]
> Egyazon szabályzatban csak a megfelelő vagy a nem megfelelő alkalmazások listája szerepelhet. Mindkét típusú lista nem adható meg ugyanabban a házirendben.
>
> Az Intune lehetővé teszi, hogy jelentést készítsen a nem megfelelő alkalmazásokat futtató eszközökről. Ezzel nem tiltja le a nem megfelelő alkalmazások telepítését, és nem is távolítja el azokat.

|Beállítás neve|Részletek|
|----------------|---------------|
|**Meg nem felelésről szóló jelentés küldése, ha a felhasználók telepítik a listán szereplő alkalmazások valamelyikét**|Azon Mac OS X-alkalmazások felsorolása, amelyek telepítésére a felhasználók nem jogosultak. Ha a felhasználók ilyen alkalmazást telepítenek, az megjelenik a **szabályzatoknak nem megfelelő alkalmazásokról készült jelentésekben**.|
|**Meg nem felelésről szóló jelentés küldése, ha a felhasználók a listán nem szereplő alkalmazásokat telepítenek**|Azon Mac OS X-alkalmazások felsorolása, amelyek telepítésére a felhasználók jogosultak. Ha a felhasználók bármilyen más alkalmazást telepítenek, az megjelenik a **szabályzatoknak nem megfelelő alkalmazásokról készült jelentésekben**.|
|**Hozzáadás**|Hozzáadhat egy alkalmazást a kijelölt listához. Meg kell adnia egy szabadon választott nevet, valamint opcionálisan megadhatja az alkalmazás kiadóját és csomagazonosítóját. **Tipp:** Az alkalmazás csomagazonosítóját az alábbi lépésekkel keresheti meg a telepített alkalmazást futtató Mac számítógépen:<ol><li>Nyissa meg az alkalmazás telepítési mappáját (például **/Applications**).</li><li>Jelölje ki az *&lt;alkalmazásnév&gt;***.app** csomagot, és válassza a **Show Package Contents** (Csomag tartalmának megjelenítése) lehetőséget.</li><li>Nyissa meg az **Info.plist** fájlt.</li><li>Ellenőrizze a **CFBundleIdentifier** kulcshoz hozzárendelt értéket.</li></ol>A csomagazonosító formátuma: **com.contoso.alkalmazásnév**.|
|**Alkalmazások importálása**|Importálja a saját maga által egy vesszővel tagolt fájlban megadott alkalmazásokat. A fájlban ezt a formátumot használja: alkalmazásnév, kiadó, alkalmazáscsomag-azonosító.|
|**Szerkesztés**|A kiválasztott alkalmazás nevének, kiadójának és alkalmazáscsomag-azonosítójának szerkesztése.|
|**Törlés**|A kijelölt alkalmazás törlése a listából.|
> [!TIP]
> Az Intune-jelentésekkel kapcsolatos további információkért lásd: [A Microsoft Intune-műveletek értelmezése jelentések segítségével](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Ha egy Mac OS X-eszköz alvó állapotban van, a házirendek és profilok nem kézbesíthetők, és nem naplózhatók. Ennek következtében előfordulhat, hogy az Intune konzolján ideiglenesen a **Hibás házirend-beállítások** állapotüzenet jelenik meg mindaddig, amíg az eszköz fel nem ébred az alvó üzemmódból.

### <a name="monitor-compliant-and-noncompliant-apps"></a>A szabályzatnak megfelelő és nem megfelelő alkalmazások figyelése
A **szabályzatnak nem megfelelő alkalmazásokról készült jelentésben** megtekintheti a megadott alkalmazások megfelelőségét.

#### <a name="to-run-a-report"></a>Jelentés futtatása

1.  A [Microsoft Intune felügyeleti konzolban](https://manage.microsoft.com) válassza a **Jelentések** &gt; **Szabályzatoknak nem megfelelő alkalmazások – jelentések** elemet.

2.  Jelölje ki az ellenőrizni kívánt eszközcsoportokat, adja meg, hogy a megfelelő vagy a nem megfelelő alkalmazásokat vagy mindkettőt szeretné-e ellenőrizni, majd válassza a **Jelentés megtekintése**elemet.

## <a name="mac-os-x-custom-policy-settings-in-microsoft-intune"></a>Egyéni Mac OS X-házirendbeállítások a Microsoft Intune-ban
A Microsoft Intune **egyéni Mac OS X-konfigurációs szabályzatával** telepítheti az [Apple Configurator eszközzel](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) létrehozott beállításokat a Mac OS X-eszközökre. Ezzel az eszközzel számos olyan beállítást készíthet, amelyek ezen eszközök működését vezérlik, és egy konfigurációs profilba exportálhatja őket. Ezt a konfigurációs profilt később egy Intune-beli egyéni Mac OS X-szabályzatba importálhatja, és a beállításokat telepítheti a szervezetben lévő felhasználók és eszközök számára.

E funkció révén olyan Mac OS X-beállításokat telepíthet, amelyek nem konfigurálhatók az Intune általános Mac OS X-konfigurációs szabályzatával.

### <a name="prerequisites"></a>Előfeltételek
Mielőtt elkezdené, telepítenie kell az Apple Configurator eszközt, és létre kell hoznia a felhasználók vagy eszközök számára telepíteni kívánt beállításokat tartalmazó konfigurációs fájlt. Az Apple Configurator eszköz letöltése és az azzal kapcsolatos információk a [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) áruházban érhetők el.

> [!NOTE]
> Az Intune nem készít jelentést az egyéni Mac OS X-szabályzatok egyes beállításainak betartásáról, a teljes házirend betartásáról azonban igen.

### <a name="general-settings"></a>Általános beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    |**Név**|Az egyéni Mac OS X-szabályzatnak egyéni nevet adjon, hogy könnyebben azonosíthassa az Intune konzolján.|
    |**Leírás**|Adjon meg egy leírást, amely áttekintést nyújt az egyéni Mac OS X-házirendről, és olyan releváns információkat tartalmaz, amelyek megkönnyítik a keresését.|


### <a name="custom-settings"></a>Egyéni beállítások

|Beállítás neve|Részletek|
    |----------------|--------------------|
    |**Egyéni konfigurációs profil neve (felhasználók láthatják)**|Nevezze el a szabályzatot. Ez a név jelenik majd meg az eszközön és az Intune szabályzatjelentéseiben.|
    |**Konfigurációs profil fájlja**|Válassza az **Importálás** elemet, majd keresse meg az Apple Configurator eszközzel létrehozott konfigurációs profilt. **Tipp:** A „Konfigurációs profilfájl létrehozása” című témakörben talál segítséget a konfigurációs profil létrehozásához.|
    |**Konfigurációs profil adatai**|Megjeleníti az importált konfigurációs profil XML-kódját.|



### <a name="how-to-create-a-configuration-profile-file"></a>Konfigurációs profilfájl létrehozása
Az egyéni házirend által használt konfigurációs profilfájlt kétféleképpen hozhatja létre:

-   A fájl Apple Configurator eszközből történő exportálásával ( **.mobileconfig**kiterjesztéssel).

-   A fájlt Ön is létrehozhatja, ha az [Apple konfigurációs profilok készítésére szolgáló útmutatójának](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html) megfelelő sémáját használja.


### <a name="see-also"></a>Lásd még:
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
