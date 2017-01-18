---
title: "Újdonságok | Microsoft Docs"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2fdf4086ccf4b4f256596b7d0f7192b70a4efd2a
ms.openlocfilehash: a2f3eab11f208c0260dc4dbc245801416dc36633


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Újdonságok a Microsoft Intune-ban – 2017. január
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

> [!Note]
> Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>MAM-jelentések a konzolon a nem regisztrált eszközökről <!--677961-->
Új alkalmazásvédelmi jelentések érhetők el mind a regisztrált, mind a nem regisztrált eszközökkel kapcsolatban. További információ [a mobilalkalmazás-felügyeleti szabályzatok Intune-nal történő figyeléséről](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1-támogatás <!--694397-->
Az Intune mostantól teljes mértékben támogatja és képes felügyelni az Android 7.1.1-es verzióját.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>A következő probléma elhárítása: Az iOS-eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük

Ha a felhasználói eszközök elveszítik a kapcsolatot az Intune-nal, új hibaelhárítási lépések átadásával segítheti a felhasználókat a vállalati erőforrásokhoz való hozzáférés visszaszerzésében. Lásd: [Az eszközök inaktívak, vagy a felügyeleti konzol nem tud kommunikálni velük](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Értesítések

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>A windowsos asztali eszközök felügyelete alapértelmezés szerint a Windows beállításain keresztül történik <!--663050-->
Megváltozik a Windows 10-es asztali rendszerek regisztrációjának alapértelmezett működése. Az új regisztrációk a tipikus MDM-ügynöki regisztrációs folyamatot követik, nem a PC-s ügynökön keresztül zajlanak.

A Munkahelyi portál webhely olyan instrukciókat szolgáltat az asztali Windows 10-es felhasználóknak, amelyek alapján asztali Windows 10-es számítógépeiket mobileszközként regisztrálhatják. Ez nem érinti a korábban regisztrált PC-ket, és a cég továbbra is felügyelheti a Windows 10-es asztali rendszereket a PC-s ügynökkel, [ha erre van igény](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

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

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója – újdonságok<!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Az Intune Azure-beli előzetes verziójának újdonságait [Ide kattintva](https://docs.microsoft.com/intune-azure/introduction/whats-new) tekintheti meg.

### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Az Azure előzetes verziójának újdonságai](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Újdonságok – Archívum](whats-new-archive.md)



<!--HONumber=Jan17_HO2-->


