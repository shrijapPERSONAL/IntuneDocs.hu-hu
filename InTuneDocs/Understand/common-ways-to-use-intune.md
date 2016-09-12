---
title: "Az Intune használatának gyakori módjai | Microsoft Intune"
description: "A hat leggyakoribb feladat, amelyek elvégzésében az Intune segít"
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2ebb8fcf348cfdc7600c37b40824f5bba37a7f36
ms.openlocfilehash: 4614c13d98c4b05882bbeabfbbd7de83d9bea2da


---

# Az Intune használatának gyakori módjai

Mielőtt belevágna a megvalósítási feladatok végrehajtásába, fontos, hogy egyeztesse az üzleti célokat azokkal, akiket a szervezetnél érint a nagyvállalati mobilitás.  Ez akkor is fontos, ha újonnan vezeti be a nagyvállalati mobilitást, és akkor is, ha egy másik termékről tér át.  A nagyvállalati mobilitáshoz kapcsolódó igények dinamikusan fejlődnek, és a Microsoft néha a piacon elérhető más megoldásoktól különböző módon ad megoldást ezekre a igényekre.  Az üzleti céloknak megfelelő tervezés legjobb módja az, hogy meghatározza, mit szeretne elérni, és ezt úgy teszi, hogy kidolgozza azokat a forgatókönyveket, amelyeket meg szeretne valósítani a dolgozók és a partnerek számára, valamint az informatikai környezetben.  Az alábbiakban röviden bemutatjuk az Intune-ra épülő 6 leggyakoribb forgatókönyvet, és feltüntetjük az egyes forgatókönyvek tervezésével és megvalósításával kapcsolatos további tudnivalókra mutató hivatkozásokat.

>[!NOTE]
>Tudni szeretné, hogy a Microsoft informatikai részlege hogyan használja az Intune-t annak biztosításához,hogy a Microsoft dolgozói hozzáférjenek a vállalati erőforrásokhoz a mobileszközeikről, és eközben hogyan biztosítja a vállalati adatok védelmét? [Olvassa el ezt az angol nyelvű technikai esettanulmányt](https://www.microsoft.com/itshowcase/Article/Content/588), amely részletesen leírja, hogyan használja a Microsoft informatikai részlege az Intune-t és az egyéb szolgáltatásokat az identitás, az eszközök, az alkalmazások és az adatok kezeléséhez.  

>[!IMPORTANT]
>A mobileszközök naprakészségének biztosítása<br>
>A nemrégiben a „Trident” kártevő által az iOS eszközök ellen indított támadások nyomán közzétettünk egy új blogbejegyzést ‒ [Hogyan biztosíthatja a mobileszközök naprakészségét a Microsoft Intune segítségével?](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) ‒, amely megismerteti az Intune által kínált különböző lehetőségeket a mobileszközök biztonságának és naprakészségének fenntartására.

## A helyszíni e-mailek és adatok védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez
A legtöbb nagyvállalati mobilitási stratégia annak megtervezésével kezdődik, hogy a dolgozók hogyan tudják biztonságosan elérni az e-maileket a mobileszközeikkel az interneten. Számos szervezet továbbra is a vállalati hálózatában tárolja és üzemelteti a helyszíni adatokat és az alkalmazáskiszolgálókat, például a Microsoft Exchange-et. Az Intune és a nagyvállalati mobilitási csomag (EMS) olyan egyedi, integrált [feltételes hozzáférési megoldást](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) kínál az Exchange Serverhez, amely garantálja, hogy egyetlen mobilalkalmazásnak sem lesz hozzáférése az e-mailekhez, amíg az eszköz nincs regisztrálva az Intune-ban, és mindezt úgy, hogy nem kell egy további átjárót üzembe helyezni a vállalati hálózat peremén.

Az e-mailek mellett az Intune támogatja az olyan mobilalkalmazások hozzáférésének biztosítását is, amelyek biztonságos hozzáférést igényelnek a helyszíni adatokhoz, mint például az üzleti alkalmazások kiszolgálói.  Ez általában az [Intune által kezelt, hozzáférés-vezérlésre használt tanúsítványokkal](/intune/deploy-use/secure-resource-access-with-certificate-profiles), valamint a szegélyhálózatban található szabványos VPN-átjáróval vagy proxyval, például a Microsoft Azure AD-alkalmazásproxyval oldható meg.  Ezekben az esetekben a vállalati adatok kizárólag az eszköznek a felügyelet hatálya alá való regisztrálásával érhetők el.  A regisztrálás után a felügyeleti rendszer gondoskodik arról, hogy a vállalati adatokhoz hozzáférő eszközök megfeleljenek a szabályzatoknak.  Ezenkívül az Intune [alkalmazásburkoló eszközével és az App SDK-val](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) megoldható, hogy az elért adatok az üzleti alkalmazáson belül maradjanak, így az alkalmazás nem tudja átadni a vállalati adatokat a fogyasztói alkalmazásoknak vagy a szolgáltatásoknak.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## Az Office 365 e-mailjeinek és adatainak védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez
Az Office 365-ben a vállalati adatok (e-mail, dokumentumok, azonnali üzenetek, névjegyek) védelme nem is lehetne egyszerűbb az Ön számára és zökkenőmentesebb a felhasználók számára. Az Intune és a nagyvállalati mobilitási csomag egyedi, integrált feltételes hozzáférési megoldást kínál, amely gondoskodik arról, hogy a felhasználók, az alkalmazások és az eszközök csak akkor érhessék el az Office 365-adatokat, ha teljesítik a vállalat megfelelőségi követelményeit ([többtényezős hitelesítés](/intune/deploy-use/protect-windows-devices-with-multi-factor-authentication) elvégzése, regisztrálás az Intune-ba, felügyelt alkalmazás használata, operációs rendszer támogatott verziója, eszköz PIN-kódja, alacsony kockázatú profil stb.). A megfelelő alkalmazás-áruházakban elérhető Office-mobilalkalmazások fel vannak készítve az Intune-nal konfigurálható adattárolási szabályzatokra, ami lehetővé teszi, hogy megakadályozza az adatok megosztását azokkal az alkalmazásokkal (például a natív e-mail alkalmazással) és tárolóhelyekkel (például a Dropboxszal), amelyeket az informatikai részleg nem felügyel.  Az Office 365 és az EMS beépítve tartalmazza mindezeket a szolgáltatásokat.  A használatukhoz nem kell telepítenie további elemeket az infrastruktúrába.

Az Office 365 gyakran alkalmazott telepítési módszere az, hogy elő kell írni az eszközöknek a felügyelet hatálya alá történő regisztrálását, ha teljesen ki kell építeni őket a vállalati alkalmazások és tanúsítványok, a Wi-Fi és a VPN konfigurációival, ami általában a vállalati tulajdonú eszközök esetében fordul elő.  Ha azonban a felhasználónak egyszerűen csak hozzáférésre van szüksége a vállalati e-mailekhez és dokumentumokhoz, ami általában a személyes tulajdonú eszközök esetében fordul elő, akkor a felhasználónak az Office-mobilalkalmazásokat kell használnia (amelyekre [érvényesítette az adattárolási szabályzatokat](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune)), és kihagyhatja az eszköz regisztrálását.  Mindkét esetben a definiált szabályzatok biztosítják az Office 365-adatok megfelelő védelmét.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## A „saját eszközök használata” (BYOD) program ajánlása a dolgozóknak
A saját eszközök használata egyre népszerűbb a szervezetekben, mivel ezzel a módszerrel csökkenthetők a hardvereszközökre fordított kiadások, és bővíthetők a mobil munkavégzés választási lehetőségei a dolgozók számára. Napjainkban szinte mindenkinek van saját telefonja, miért kellene hát még egyet a dolgozók zsebébe tenni? A legfőbb kihívás mindig az, hogy meg kell győzni a dolgozókat arról, hogy regisztrálják a személyes eszközüket a felügyelet hatálya alá, mivel tartanak attól, hogy az informatikai részleg mit láthat az eszközükön, és mit tud tenni az eszközükkel.  

Ha az eszközök regisztrálása nem kivitelezhető lehetőség, arra az esetre az Intune kínál egy másik BYOD-módszert is, amely egyszerűen csak [felügyeli a vállalati adatokat tartalmazó alkalmazásokat](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune).  Az Intune védelmet nyújt a vállalati adatok számára akkor is, ha a szóban forgó alkalmazás vállalati és személyes adatokhoz is hozzáfér, mint az Office-mobilalkalmazások esetében.  Rendszergazdaként előírhatja a felhasználóknak, hogy az Office-mobilalkalmazásokkal érjék el az Office 365-öt, és az alkalmazásokat olyan szabályzatokkal konfigurálhatja, amelyek fenntartják az adatok védelmét (titkosítás, PIN-kódos védelem stb.).  Ezek a szabályzatok megakadályozzák az adatvesztést a nem felügyelt alkalmazások és tárolóhelyek esetében, az ilyen alkalmazásokon belül és kívül is.  Például a szabályzatok megakadályozzák, hogy a felhasználó szöveget másoljon a vállalati e-mail profilból egy fogyasztói e-mail profilba még akkor is, ha mindkét profil az Outlook Mobile-ban van konfigurálva.  Hasonló konfigurációkat adhat meg a BYOD-felhasználók által használt más szolgáltatásokhoz és alkalmazásokhoz is.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## Vállalati tulajdonú telefonok kiadása az informatikai dolgozóknak
Napjainkban a legtöbb infomunkás mobileszközökkel dolgozik a versenyképesség fenntartása érdekében.  Ezeknek a dolgozóknak zavartalan hozzáférésre van szükségük az összes vállalati alkalmazáshoz és adathoz, tetszőleges időpontban, függetlenül a tartózkodási helyüktől.  Gondoskodnia kell arról, hogy a vállalati adatok védettek, a felügyeleti költségek pedig alacsonyak legyenek.  

Az Intune [tömeges kiépítési és felügyeleti megoldásokat](/intune/deploy-use/manage-corporate-owned-devices) kínál, amelyek integrálhatók a piacon jelen lévő fő vállalati eszközfelügyeleti platformokkal, beleértve az Apple készülékregisztrációs programját és a Samsung KNOX mobilbiztonsági platformot.  Az eszközkonfigurációknak az Intune-nal történő központi létrehozása lehetőséget nyújt a vállalati eszközök kiépítésének magas szintű automatizálására.  

Képzelje el a következő helyzetet: az imént adott át egy iPhone-t bontatlan dobozban az egyik dolgozónak. A dolgozó bekapcsolja a telefont, és a telefonon lefut a vállalati beállítási folyamat, amelynek során az eszköznek hitelesítenie kell magát. Zökkenőmentesen végbemegy az iPhone konfigurálása a [biztonsági szabályzatokkal](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) (merevlemez titkosítása, eszköz PIN-kódjának beállítása stb.), [az e-mail/Wi-Fi-/VPN-/tanúsítványprofilokkal](/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune), valamint az [alkalmazások](/intune/deploy-use/add-apps) alapkészletével. Ezt követően a dolgozó elindítja az Intune Vállalati portál alkalmazást, hogy hozzáférjen a számára elérhető vállalati alkalmazásokhoz.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## Korlátozott használatú megosztott táblagépek kiadása adott feladattal foglalkozó dolgozóknak
Az adott feladattal foglalkozó dolgozók körében egyre jobban terjed a mobil technológiák használata.  Például a megosztott táblagépek már hétköznapi eszköznek tekinthetők a kiskereskedelmi üzletek dolgozói esetében.  Akár egy eladást kell feldolgozni, akár a készletet kell azonnal ellenőrizni, a táblagépek nagyban megkönnyítik a kommunikációt az ügyfelekkel.  Ebben az esetben a felhasználói élmény nagyon fontos jellemzője az egyszerűség.  Emiatt a dolgozók táblagépei általában korlátozott használatú módban működnek, például úgy, hogy a dolgozó csak egyetlen üzleti alkalmazást tud használni a táblagépen.  Az Intune lehetővé teszi az ilyen korlátozott használatú módban működő, megosztott [iOS](/intune/deploy-use/ios-policy-settings-in-microsoft-intune#general-configuration-policy-settings) és [Android](/intune/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy) rendszerű táblagépek tömeges kiépítését, védelmét és központi felügyeletét.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## Az Office 365 nem felügyelt nyilvános kioszkból történő biztonságos elérésének engedélyezése a dolgozók számára
A dolgozóknak néha olyan eszközöket, alkalmazásokat vagy böngészőket kell használniuk, amelyeket a vállalat nem tud felügyelni, mint például a kereskedelmi vásárokon vagy a szállodák előterében található nyilvános számítógépeket. Engedélyezheti a dolgozóknak a vállalati e-mailek elérését ilyen számítógépről? Az Intune és a nagyvállalati mobilitási csomag esetén <!--you have choices. The--> a válasz lehet egyszerűen „nem”, ha a [szervezet által felügyelt eszközökre korlátozza az e-mailek elérését](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  Ezzel biztosíthatja, hogy az erős hitelesítésen átesett dolgozók nem hagynak véletlenül vállalati adatokat a nem megbízható számítógépen.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Sep16_HO1-->


