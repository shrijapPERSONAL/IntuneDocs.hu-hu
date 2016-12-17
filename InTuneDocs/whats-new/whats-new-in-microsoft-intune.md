---
title: "Újdonságok | Microsoft Intune"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9fd309a10d9eb020795c5ce46df124b13dc1a006
ms.openlocfilehash: d117c929fbde4dd0a39503b8da695aa9c9ea91ad


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Újdonságok a Microsoft Intune-ban – 2016. december
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

> [!Note]
> Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója<!--736542-->
A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon. Mielőtt az összes Intune-bérlő számára elérhetővé tesszük a portált, a hónap második felében bizonyos kiválasztott bérlők számára előzetes hozzáférést biztosítunk az új felügyeleti megoldáshoz.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Addig is olvassa el az [új dokumentációt](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), amelyből megtudhatja, hogy miket tervezünk az Azure Portalon a Microsoft Intune szolgáltatásra vonatkozóan.

Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>A távközlési költségek kezelésének integrációja az Azure Portal nyilvános előzetes verziójába<!--747605-->
Elkezdtünk külső távközlési szolgáltatók költségeinek kezelésére (telecom expense management, TEM) való szolgáltatásokat integrálni előzetes verzióban az Azure Portalba. Az Intune segítségével korlátozásokat lehet foganatosítani az adatforgalomra a belföldi használat és roaming idejére. Az integrációt a [Saaswedo](http://www.saaswedo.com) közreműködésével kezdjük el.

## <a name="new-capabilities"></a>Új képességek

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Többtényezős hitelesítés minden platformon <!--747590-->
Mostantól többtényezős hitelesítést (MFA) írhat elő a felhasználók egy kiválasztott csoportja számára, ha iOS, Android, Windows 8.1+ vagy Windows Phone 8.1+ rendszerű eszközt regisztrálnak az Azure felügyeleti portálon. Ehhez konfigurálnia kell a többtényezőst hitelesítést a Microsoft Intune regisztrációs alkalmazására vonatkozóan az Azure Active Directoryban.

<!--VSO 679339, awaiting chrisgre for go-live--><!--### Conditional access for MAM with SharePoint Online
Megakadályozhatja, hogy olyan alkalmazások érjék el a SharePoint Online-t, amelyeket nem támogatnak az Intune mobilalkalmazás-felügyeleti (MAM) szabályzatai.  Az Intune mobilalkalmazás-felügyelettel az Azure Portalon ismerkedhet meg. Ehhez keresse a __Beállítások__ panelen a __Feltételes hozzáférés__ területet. Ezen megtalálja a SharePoint Online-ra vonatkozó beállítást is. Ezt a funkciót a szolgáltatás mostani kiadásától külön fogjuk biztosítani. További információk az új szolgáltatásról [itt](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>A mobileszköz-regisztrálás korlátozásának képessége<!--747596-->
Az Intune új regisztrációs korlátozásokat léptet életbe, amelyek azt szabályozzák, hogy mely mobileszközplatformok számára engedélyezett a regisztráció. Az Intune az alábbi mobileszközplatformokat különbözteti meg: iOS, macOS, Android, Windows és Windows Mobile.
* A mobileszköz-regisztráció korlátozása nem terjed ki a számítógépes ügyfelek regisztrációjára.
* Az iOS esetében fennáll egy további lehetőség a személyes tulajdonban lévő eszközök regisztrációjának letiltására.

Az Intune mindaddig személyes tulajdonúként jelöli meg az összes új eszközt, amíg az [alábbi cikkben](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) ismertetett módon a rendszergazda meg nem jelöli azokat céges eszközökként.


## <a name="notices"></a>Értesítések

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>A regisztrációra vonatkozó többtényezős hitelesítés átkerül az Azure Portalra <!--VSO 750545-->
Korábban a rendszergazdák vagy az Intune-konzolban, vagy a Configuration Managerben (az 2016. októberinél korábbi kiadásokban) állították be a többtényezős hitelesítést az Intune-beli regisztrációra vonatkozóan. A funkció átdolgozásának köszönhetően mostantól a [Microsoft Azure Portalra](https://manage.windowsazure.com) kell bejelentkezni az Intune-beli hitelesítő adatokkal, és az Azure AD-ben lehet konfigurálni a többtényezős hitelesítést. Erről [itt](https://aka.ms/mfa_ad) olvashat részletesebb tájékoztatást.

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>A Munkahelyi portál androidos verziója mostantól Kínában is elérhető <!--VSO 658093-->
Kínában való letöltésre is közzétesszük a Munkahelyi portál alkalmazás androidos verzióját. Kínában nem érhető el a Google Play áruház, ezért az androidos eszközöknek kínai alkalmazásáruházakból kell beszerezniük az alkalmazásokat. Az androidos Munkahelyi portál alkalmazás a következő áruházakból is letölthető lesz:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

A Munkahelyi portál alkalmazás androidos verziója a Google Play szolgáltatások segítségével kommunikál a Microsoft Intune szolgáltatással. A Google Play szolgáltatások egyelőre nem érhetők el Kínában, ezért a következő műveletek bármelyike akár 8 órát is igénybe vehet. 

|Intune felügyeleti konzol| Intune Munkahelyi portál alkalmazás Androidhoz |Intune Munkahelyi portál webhely|   
|---|---|---|
|Teljes törlés| Távoli eszköz eltávolítása| Eszköz eltávolítása (helyi és távoli)|
|Szelektív törlés| Eszköz alaphelyzetbe állítása| Eszköz alaphelyzetbe állítása|
|Új vagy frissített alkalmazás telepítése| Rendelkezésre álló üzleti alkalmazások telepítése| Eszköz PIN-kódjának alaphelyzetbe állítása|
|Távoli zárolás|||
|PIN-kód alaphelyzetbe állítása|||

## <a name="deprecations"></a>Elavulások

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>A Firefox megszünteti a Silverlight támogatását<!--VSO TBA-->
A Mozilla a [Firefox böngésző](https://www.mozilla.org/firefox) 2017 márciusában megjelenő 52-es verziójával kezdve megszünteti a Silverlight támogatását. Ez azt jelenti, hogy a Firefox 51-esnél újabb verzióiban nem fog tudni bejelentkezni a meglévő Intune-konzolba. Azt javasoljuk, hogy használja az Internet Explorer 10-es vagy 11-es verzióját, illetve a [Firefox 52-es előtti valamelyik verzióját](https://ftp.mozilla.org/pub/firefox/releases/) a felügyeleti konzol eléréséhez. Amikor az Intune átáll az Azure Portal használatára, számos [modern böngésző](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) használata fog elérhetővé válni, mivel többé nem lesz szükség a Silverlightra.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Az Exchange Online mobilpostaláda-szabályzatainak eltávolítása <!--770687-->
Decembertől kezdve a rendszergazdák sem megtekinteni, sem konfigurálni nem tudják az Exchange Online (EAS) mobilpostaláda-szabályzatait az Intune konzolban. Ez a változás december és január során folyamatosan terjed ki minden Intune-bérlőre. Minden meglévő szabályzat konfigurálva marad. Új szabályzatokat az Exchange Management Shell-lel lehet konfigurálni. További tájékoztatás [itt](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx) olvasható.

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Megszűnik az Intune AV Player, Image Viewer és PDF Viewer alkalmazás támogatása Androidon <!--747553-->
2016 decemberének közepétől kezdve a felhasználók nem fogják tudni használni az Intune AV Player, Image Viewer és PDF Viewer alkalmazást. Ezeket az alkalmazásokat felváltotta az Azure Information Protection alkalmazás. Az Azure Information Protection alkalmazásról [itt](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) olvashat további tájékoztatást.

### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Az Intune korábbi kiadásai](whats-new-archive.md)



<!--HONumber=Dec16_HO2-->


