---
title: Használat StageNow bejelentkezik a Android Zebra eszközök Microsoft Intune - Azure-ban |} A Microsoft Docs
description: 'Tekintse meg a gyakori problémák és megoldásuk StageNow használata az Android-eszközökön a Microsoft Intune-nal. Is megtudhatja, hogyan naplók lekérése és példák: a sikeres, a hibák és a naplók olvasása.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36476820805c00cefafcd9f64dd2f08a014762c0
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490541"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Tekintse meg a potenciális problémákat Zebra Androidos eszközökön a Microsoft Intune-ban és hibáinak elhárítása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune, használhatja a [Zebra mobilitási bővítmények MX Android Zebra-eszközök kezeléséhez](android-zebra-mx-overview.md). Zebra eszközök használata esetén profilok létrehozása a StageNow kezelheti a beállításait, és feltölti őket az Intune-ban. Intune-ban a StageNow alkalmazást használ, alkalmazza a beállításokat az eszközökön. A StageNow alkalmazást is létrehoz egy részletes naplófájlt, amellyel hibáinak elhárítása az eszközön.

Ez a funkció az alábbiakra vonatkozik:

- Android

Ha például a profil létrehozásakor StageNow eszköz beállítása. A StageNow profilt hoz létre, amikor az utolsó lépés létrehoz egy fájlt a tesztelni a profilt. A fájlt a StageNow alkalmazást az eszközön felhasznált.

Egy másik példa StageNow hozzon létre egy profilt, és tesztelheti. Az Intune-ban a StageNow profil hozzáadásához, és rendelje hozzá a Zebra eszközök. A hozzárendelt profil állapotának ellenőrzésekor a profil egy magas szintű állapotát jeleníti meg.

Mindkét esetben a további részleteket is kérhet a StageNow naplófájlt, amely minden alkalommal, amikor egy StageNow profilt alkalmazza az eszközre mentett.

Bizonyos problémák nem kapcsolódnak a StageNow profil tartalmát, és nem kerülnek időben a naplókat.

Ez a cikk bemutatja, hogyan olvashatja be a StageNow naplókat, és megjeleníti az egyes más potenciális problémákat, Zebra eszközök, amelyek nem tükrözik a naplókban.

[Használhatja és kezelheti a Zebra eszközök Zebra mobilitási kiterjesztésű](android-zebra-mx-overview.md) funkció további részleteket tartalmaz.

## <a name="get-the-logs"></a>A naplók lekérése

### <a name="use-the-stagenow-app-on-the-device"></a>Az StageNow alkalmazás használatát az eszközön
Ha egy profil közvetlenül a StageNow használata helyett, a számítógép tesztelése [telepítse a profilt az Intune](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), a StageNow alkalmazást az eszközön a teszt menti a naplókat. A naplófájl lekéréséhez használja a **(...)**  StageNow alkalmazás lehetőséget az eszközön.

### <a name="get-logs-using-android-debug-bridge"></a>Android hibakeresési híd használata naplók lekérése
Naplók lekéréséhez a profilt az Intune-ban már üzembe helyezését követően csatlakoztassa az eszközt egy olyan számítógéppel [Android hibakeresési híd (adb)](https://developer.android.com/studio/command-line/adb) (az Android a webhely nyílik meg).

A mentett naplókat az eszközön `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Naplók lekérése az e-mailből
Szerezhet be naplófájlokat, miután a profil már telepítve van az Intune-nal, a végfelhasználók is e-mailben a naplók használatával egy e-mail alkalmazást az eszközön. A Zebra eszközön nyissa meg a vállalati portál alkalmazást, és [naplók küldése](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). A naplók küldése funkció segítségével is létrehoz egy PowerLift incidens azonosítója, amelyet hivatkozhat, ha kapcsolatba lépne a Microsoft ügyfélszolgálatával.

## <a name="read-the-logs"></a>A naplók olvasása

Ha megnézzük a naplókat, hiba történik, amikor megjelenik a `<characteristic-error>` címke. Hiba részleteinek kerüljenek a `<parm-error>` címke > `desc` tulajdonság.

## <a name="error-types"></a>Alkalmazáshiba-típusok

Zebra eszközök közé tartoznak a különböző hibajelentési szintek:

- A kriptográfiai Szolgáltató nem támogatott eszközön. Például az eszköz nem a mobil eszközök, de nem rendelkezik a mobilhálózati manager.
- A MX vagy OSX-verzió nem egyezik. Minden Felhőszolgáltató egy verzióval ellátott. Egy teljes támogatási mátrixa, lásd: [Zebra a dokumentáció](http://techdocs.zebra.com/mx/) (Zebra a webhely megnyitása).
- Az eszköz jelenti, egy másik probléma vagy hiba.

## <a name="examples"></a>Példák

Például hogy a következő bemeneti profil:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

A naplóban az XML-fájl megegyezik a bemeneti. A megfelelő kimeneti azt jelenti, hogy a profil alkalmazása sikeresen megtörtént az eszköz hiba nélkül:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

A következő bemeneti van egy másik példa:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

A napló akkor jelez hibát, mert tartalmaz egy `<characteristic-error>` címke. Ebben a forgatókönyvben a profil próbált meg telepíteni egy Android-csomag (APK-), amely nem létezik a megadott elérési úton:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## <a name="other-potential-issues-with-zebra-devices"></a>Más potenciális problémákat Zebra eszközökkel

Ez a szakasz felsorolja a további lehetséges okokat, látni az eszköz-rendszergazdai Zebra eszközök használatakor. Ezeket a problémákat a StageNow naplók nem láthatók.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView alkalmazást nem naprakész

Ha a régebbi eszközöket jelentkezzen be a vállalati portál alkalmazást, felhasználók által is látható egy üzenet, hogy a System WebView alkalmazást összetevő elavult, és meg kell frissíteni. Ha az eszköz a Google Play áruházból telepített, csatlakoztassa az internethez, és a frissítések keresése. Ha az eszköz nem rendelkezik a Google Play telepítve, töltse le a frissített verziót az összetevő, és alkalmazhatja azokat az eszközöket. Vagy, a legújabb eszköz operációs rendszere Zebra által kiadott.

### <a name="management-actions-take-a-long-time"></a>Felügyeleti műveletek hosszú ideig tarthat.

Google Play-szolgáltatások nem érhetők el, ha egyes feladatok akár 8 órát is igénybe. [Korlátozások az Intune vállalati portál alkalmazás Androidos](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (megnyílik egy másik Microsoft-webhely) jól lehet.

### <a name="device-spoofing-suspected-shows-in-intune"></a>"Az eszköz hamisítást feltételezett" bemutatja az Intune-ban

Ez a hiba, az azt jelenti, hogy az Intune gyanakszik egy nem Zebra Android-eszköz jelent a modell és a gyártó Zebra eszközt.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Vállalati portál alkalmazás a régebbi, mint a minimálisan szükséges verzió

Intune-ban előfordulhat, hogy frissítse a vállalati portál alkalmazás minimálisan szükséges verzió. Ha a Google Play áruházból az eszközön nincs telepítve, a vállalati portál alkalmazás automatikusan frissül nem beolvasása. Ha a minimálisan szükséges verzió újabb, mint a telepített verzió, a vállalati portál alkalmazás nem működik tovább. Frissítés a legújabb vállalati portál alkalmazás történő [Zebra eszközökön saját telepítési](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>További lépések

[Zebra vitafórumok](https://developer.zebra.com/community/home/discussions) (Zebra a webhely megnyitása)

[Használhatja és kezelheti a Zebra eszközök Zebra mobilitási bővítmények az Intune-ban](android-zebra-mx-overview.md)
