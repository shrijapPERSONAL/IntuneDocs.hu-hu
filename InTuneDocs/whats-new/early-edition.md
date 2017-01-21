---
title: "Előzetes kiadás | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>A Microsoft Intune előzetes kiadása – január

Ez az **Előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
> A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="actions-for-non-compliance---730266--"></a>Meg nem felelés esetén végrehajtandó műveletek <!--730266-->
A _Meg nem felelés esetén végrehajtandó műveletek_ a megfelelési szabályzatokkal kapcsolatos új funkció, amellyel a nem megfelelő eszközökön lehet műveleteket végezni. Akár több műveletet is megadhat végrehajtásuk időpontjával együtt. E-mailben értesítheti például a nem megfelelő eszközök felhasználóit abban a pillanatban, amikor az eszköz nem megfelelővé válik, vagy a Feltételes hozzáférés funkcióval 3 napos türelmi időszak után letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>MAM-jelentések a konzolon a nem regisztrált eszközökről <!--677961-->
Új alkalmazásvédelmi jelentések érhetők el mind a regisztrált, mind a nem regisztrált eszközökkel kapcsolatban. További információ [a mobilalkalmazás-felügyeleti szabályzatok Intune-nal történő figyeléséről](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>Feltételes hozzáférés a SharePort Online-hoz a mobilalkalmazás-felügyelet (MAM) segítségével <!--679339-->
Megakadályozhatja, hogy olyan alkalmazások érjék el a SharePoint Online-t, amelyeket nem támogatnak az Intune mobilalkalmazás-felügyeleti (MAM) szabályzatai.  Az Intune mobilalkalmazás-felügyelettel az Azure Portalon ismerkedhet meg. Ehhez keresse a __Beállítások__ panelen a __Feltételes hozzáférés__ területet. Ezen megtalálja a SharePoint Online-ra vonatkozó beállítást is. Ezt a funkciót a szolgáltatás mostani kiadásától külön fogjuk biztosítani. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1-támogatás <!--694397-->
Az Intune mostantól teljes mértékben támogatja és képes felügyelni az Android 7.1.1-es verzióját.

## <a name="notices"></a>Értesítések

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>A windowsos asztali eszközök felügyelete alapértelmezés szerint a Windows beállításain keresztül történik <!--663050-->
Megváltozik a Windows 10-es asztali rendszerek regisztrációjának alapértelmezett működése. Az új regisztrációk a tipikus MDM-ügynöki regisztrációs folyamatot követik, nem a PC-s ügynökön keresztül zajlanak.

A Munkahelyi portál webhely olyan instrukciókat szolgáltat az asztali Windows 10-es felhasználóknak, amelyek alapján asztali Windows 10-es számítógépeiket mobileszközként regisztrálhatják. Ez nem érinti a korábban regisztrált PC-ket, és a cég továbbra is felügyelheti a Windows 10-es asztali rendszereket a PC-s ügynökkel, [ha erre van igény](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Az iOS-es Munkahelyi portál hivatkozásai az alkalmazáson belül nyílnak meg <!--665954-->
Az iOS-re készült Munkahelyi portál alkalmazásban látható hivatkozások (köztük a dokumentációra és az alkalmazásokra mutatók is) közvetlenül Munkahelyi portál alkalmazásban nyílnak meg, a Safari beágyazott nézetében. Ez a frissítés a januári szolgáltatásfrissítéstől külön jelenik meg.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Jobb MAM-támogatás a szelektív törléshez <!--581242-->
A végfelhasználók részletes útmutatást kapnak, amely alapján visszaszerezhetik hozzáférésüket az „Offline időszak az alkalmazásadatok törlése előtt” szabályzat által automatikusan törölt munkahelyi vagy iskolai adataikhoz.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Új dokumentáció az alkalmazásvédelmi szabályzatokhoz <!--583398-->
Frissítettük a dokumentációnkat azon rendszergazdákra és alkalmazásfejlesztőkre gondolva, akik az Intune App Wrapping Tool eszközzel vagy az Intune App SDK-val szeretnék iOS-es és androidos alkalmazásaikban elérhetővé tenni az alkalmazásvédelmi szabályzatokat (más néven MAM-szabályzatokat).

A következő cikkek frissültek:

* [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [iOS-alkalmazások mobilalkalmazás-felügyeletre való előkészítése az alkalmazásburkoló eszközzel](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Bevezetés a Microsoft Intune App SDK használatába](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [iOS-hoz készült Intune App SDK – fejlesztői útmutató](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

A következő cikkek most jelentek meg a dokumentumtárban:

* [Intune App SDK Cordova beépülő modul](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK Xamarin összetevő](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Folyamatjelző sáv a Munkahelyi portál indításakor iOS-en <!--665978-->
Az iOS-re készült Munkahelyi portál alkalmazás indítóképernyőjén folyamatjelző sáv tájékoztatja a felhasználót a betöltési folyamatok menetéről. A számlálót fokozatosan váltja le a folyamatjelző sáv: bizonyos felhasználóknál már megjelenik, míg mások még a számlálót fogják látni.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója <!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="january-2017"></a>2017. január

#### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->
Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Üzletági alkalmazások kiosztása nem regisztrált eszközökre is <!--748803-->
Mostantól attól függetlenül kioszthat üzletági alkalmazásokat a felhasználóknak, hogy az eszközeik regisztrálva vannak-e az Intune-ban. Ha valamely felhasználó eszköze nincs regisztrálva az Intune-ban, a Munkahelyi portál alkalmazás helyett a Munkahelyi portál webhelyen telepíthetik az alkalmazást.

### <a name="december-2016"></a>2016. december

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>A távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójába<!--747605-->
Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com) közreműködésével kezdjük el. A funkció próbaverziós bérlőben való engedélyezéséhez [forduljon a Microsoft támogatási szolgálatához](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).



<!--HONumber=Dec16_HO4-->


