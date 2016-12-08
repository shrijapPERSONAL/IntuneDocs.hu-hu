---
title: "Előzetes kiadás | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6dd584397451d38be86fa0780efff435ffb9b2af
ms.openlocfilehash: d70ebf87bc930f853741ddc0d572d2174c636dac


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>A Microsoft Intune előzetes kiadása – November

Ez az **Előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az új dokumentációba.

Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>A távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójába<!--747605-->
Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com) közreműködésével kezdjük el.

## <a name="new-capabilities"></a>Új képességek

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Többtényezős hitelesítés minden platformon <!--747590-->
Mostantól többtényezős hitelesítést (MFA) írhat elő a felhasználók egy kiválasztott csoportja számára, ha iOS, Android, Windows 8.1+ vagy Windows Phone 8.1+ rendszerű eszközt regisztrálnak az Azure felügyeleti portálon. Ehhez konfigurálnia kell a többtényezőst hitelesítést a Microsoft Intune regisztrációs alkalmazására vonatkozóan az Azure Active Directoryban.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>Feltételes hozzáférés a SharePort Online-hoz a mobilalkalmazás-felügyelet (MAM) segítségével <!--VSO 679339-->
Megakadályozhatja, hogy olyan alkalmazások érjék el a SharePoint Online-t, amelyeket nem támogatnak az Intune mobilalkalmazás-felügyeleti (MAM) szabályzatai.  Az Intune mobilalkalmazás-felügyelettel az Azure Portalon ismerkedhet meg. Ehhez keresse a __Beállítások__ panelen a __Feltételes hozzáférés__ területet. Ezen megtalálja a SharePoint Online-ra vonatkozó beállítást is. Ezt a funkciót a szolgáltatás mostani kiadásától külön fogjuk biztosítani.

### <a name="ability-to-restrict-intune-mobile-device-enrollment"></a>Az Intune-beli mobileszköz-regisztrálás korlátozásának képessége
Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile. 
* A macOS, illetve a Windows 8.1-es és újabb verziói esetében mobileszközplatformonként korlátozható a regisztráció. 
* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépügynökök regisztrációjára. 
* Az iOS esetében fennáll egy további lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására. Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.


## <a name="notices"></a>Értesítések

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>A regisztrációra vonatkozó többtényezős hitelesítés átkerül az Azure Portalra <!--VSO 750545-->
Korábban a rendszergazdák vagy az Intune konzolban, vagy a Configuration Managerben (az 1610-esnél korábbi kiadásokban) állították be a többtényezős hitelesítést az Intune-beli regisztrációra vonatkozóan. A funkció átdolgozásának köszönhetően mostantól a [Microsoft Azure Portalra](https://manage.windowsazure.com) kell bejelentkezni az Intune-beli hitelesítő adatokkal, és az Azure AD-ben lehet konfigurálni a többtényezős hitelesítést. Erről [itt](https://aka.ms/mfa_ad) olvashat részletesebb tájékoztatást.

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>A Munkahelyi portál androidos verziója mostantól Kínában is elérhető <!--VSO 658093-->
Kínában való letöltésre is közzétesszük a Munkahelyi portál alkalmazás androidos verzióját. Kínában nem érhető el a Google Play áruház, ezért az androidos eszközöknek kínai alkalmazásáruházakból kell beszerezniük az alkalmazásokat. Az androidos Munkahelyi portál alkalmazás a 360, a Tencent, a Xiaomi, a Wandoujia és Huawei alkalmazásáruházából lesz letölthető. 

A Munkahelyi portál alkalmazás androidos verziója a Google Play szolgáltatások segítségével kommunikál a Microsoft Intune szolgáltatással. A Google Play szolgáltatások egyelőre nem érhetők el Kínában, ezért a következő műveletek bármelyike akár 8 órát is igénybe vehet. 

|Intune felügyeleti konzol| Intune Munkahelyi portál alkalmazás Androidhoz |Intune Munkahelyi portál webhely|   
|---|---|---|
|Teljes törlés| Távoli eszköz eltávolítása| Eszköz eltávolítása (helyi és távoli)|
|Szelektív törlés| Eszköz alaphelyzetbe állítása| Eszköz alaphelyzetbe állítása|
|Új vagy frissített alkalmazás telepítése| Rendelkezésre álló üzleti alkalmazások telepítése| Eszköz PIN-kódjának alaphelyzetbe állítása|
|Távoli zárolás|||
|PIN-kód alaphelyzetbe állítása|||

## <a name="deprecations"></a>Elavulások

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Az Exchange Online mobilpostaláda-szabályzatainak eltávolítása <!--770687-->
Decembertől kezdve a rendszergazdák sem megtekinteni, sem konfigurálni nem tudják az Exchange Online (EAS) mobilpostaláda-szabályzatait az Intune konzolban. Ez a változás december és január során folyamatosan terjed ki minden Intune-bérlőre. Minden meglévő szabályzat konfigurálva marad. Új szabályzatokat az Exchange Management Shell-lel lehet konfigurálni. További tájékoztatás [itt](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx) olvasható.

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Megszűnik az Intune AV Player, Image Viewer és PDF Viewer alkalmazás támogatása Androidon <!--747553-->
2016 decemberének közepétől kezdve a felhasználók nem fogják tudni használni az Intune AV Player, Image Viewer és PDF Viewer alkalmazást. Ezeket az alkalmazásokat felváltotta az Azure Information Protection alkalmazás. Az Azure Information Protection alkalmazásról [itt](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) olvashat további tájékoztatást.

### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).



<!--HONumber=Nov16_HO5-->


