---
title: A Microsoft Intune használatának gyakori módjai
description: A Microsoft Intune-nal elvégezhető hat leggyakoribb feladattípus ismertetése.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/29/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32be10340e1e77d2f994c5f038e6328ea42a6303
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394773"
---
# <a name="common-ways-to-use-microsoft-intune"></a>A Microsoft Intune használatának gyakori módjai

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Mielőtt belevágna a megvalósítási feladatok be, fontos a vállalati vállalati mobilitási résztvevőket az üzleti célokat, az Intune-nal körül igazítása. Résztvevő igazítás fontos, akár most ismerkedik az enterprise mobility vagy egy másik termékről áttelepítése.  

A nagyvállalati mobilitáshoz kapcsolódó igények dinamikusan fejlődnek, és a Microsoft néha a piacon elérhető más megoldásoktól különböző módon ad megoldást ezekre a igényekre. Az üzleti céloknak megfelelő tervezés legjobb módja az, hogy meghatározza a célokat azon forgatókönyvek kidolgozásával, amelyeket meg szeretne valósítani a dolgozók és a partnerek számára, valamint az informatikai részlegben.  

Az alábbiakban röviden bemutatjuk az Intune-ra épülő hat leggyakoribb forgatókönyvet, és feltüntetjük az egyes forgatókönyvek tervezésével és megvalósításával kapcsolatos további tudnivalókra mutató hivatkozásokat.

>[!NOTE]
>Tudni szeretné, hogy a Microsoft informatikai részlege hogyan használja az Intune-t annak biztosítására, hogy a Microsoft dolgozói hozzáférjenek a vállalati erőforrásokhoz a mobileszközeikről, és eközben hogyan gondoskodik a vállalati adatok védelméről? [Olvassa el ezt az angol nyelvű technikai esettanulmányt](https://www.microsoft.com/itshowcase/Article/Content/588), amely részletesen leírja, hogyan használja a Microsoft informatikai részlege az Intune-t és az egyéb szolgáltatásokat az identitás, az eszközök, az alkalmazások és az adatok kezeléséhez.  

>[!IMPORTANT]
>A nemrégiben a „Trident” kártevő által az iOS-eszközök ellen indított támadások miatt biztosítani szeretnénk a mobileszközök naprakészségét. Ezért tettük közzé a [mobileszközök folyamatos frissítésének a Microsoft Intune segítségével történő biztosítását](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) ismertető blogbejegyzést. Ez bemutatja az Intune által kínált különböző lehetőségeket a mobileszközök biztonságának és naprakészségének fenntartására.

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>A helyszíni e-mailek és adatok védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez
A legtöbb nagyvállalati mobilitási stratégia annak megtervezésével kezdődik, hogy a dolgozók hogyan tudják biztonságosan elérni az e-maileket az internethez kapcsolódó mobileszközeikkel. Számos szervezet továbbra is a vállalati hálózatában tárolja és üzemelteti a helyszíni adatokat és az alkalmazáskiszolgálókat, például a Microsoft Exchange-et.


Az Intune és a Microsoft Enterprise Mobility + Security (EMS) olyan egyedi, integrált [feltételes hozzáférési megoldást](conditional-access.md) kínál az Exchange Serverhez, amely gondoskodik arról, hogy egyetlen mobileszköznek se legyen hozzáférése az e-mailekhez, amíg az eszköz nincs regisztrálva az Intune-ban. Az ilyen típusú e-mailek elérését anélkül, hogy további átjárót üzembe helyeznie a vállalati hálózat széle valósítható meg.

Az Intune támogatja az olyan mobilalkalmazások hozzáférésének biztosítását is, amelyek biztonságos hozzáférést igényelnek a helyszíni adatokhoz, mint például az üzleti alkalmazások kiszolgálói. Ez a hozzáféréstípus általában az [Intune által kezelt, hozzáférés-vezérlésre használt tanúsítványokkal](certificates-configure.md), valamint a szegélyhálózatban található szabványos VPN-átjáróval vagy proxyval, például a Microsoft Azure Active Directory-alkalmazásproxyval oldható meg. 

Ezekben az esetekben a céges adatok kizárólag az eszköz felügyeletre való regisztrálásával érhetők el. Az eszközök regisztrálása után a felügyeleti rendszer gondoskodik arról, hogy az eszközök megfeleljenek a szabályzatoknak, mielőtt hozzáférhetnek a vállalati adatokhoz. Ezenkívül az Intune [alkalmazásburkoló eszközével és az App SDK-val](apps-prepare-mobile-application-management.md) az elért adatok az üzleti alkalmazáson belül tarthatók, hogy az alkalmazás ne tudja átadni a vállalati adatokat a fogyasztói alkalmazásoknak vagy szolgáltatásoknak.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->


## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Az Office 365 e-mailjeinek és adatainak védelme a mobileszközökről történő biztonságos hozzáférés lehetővé tételéhez
Az Office 365-ben a vállalati adatok (e-mail, dokumentumok, azonnali üzenetek, névjegyek) védelme nem is lehetne egyszerűbb az Ön számára és zökkenőmentesebb a felhasználók számára.

Az Intune és a Microsoft Enterprise Mobility + Security csomag egyedi, integrált feltételes hozzáférési megoldást kínál, amely gondoskodik arról, hogy a felhasználók, az alkalmazások és az eszközök csak akkor érhessék el az Office 365-adatokat, ha teljesítik a vállalat megfelelőségi követelményeit ([többtényezős hitelesítés](multi-factor-authentication.md) elvégzése, regisztrálás az Intune-ba, felügyelt alkalmazás használata, operációs rendszer támogatott verziója, eszköz PIN-kódja, alacsony kockázatú profil stb.).


A megfelelő alkalmazás-áruházakban elérhető Office-mobilalkalmazások fel vannak készítve az Intune-nal konfigurálható adattárolási szabályzatokra. Ez lehetővé teszi, hogy megakadályozza az adatok megosztását azokkal az alkalmazásokkal (például a natív e-mail alkalmazással) és tárolóhelyekkel (például a Dropboxszal), amelyeket az informatikai részleg nem felügyel. Az Office 365 és az EMS beépítve tartalmazza mindezeket a szolgáltatásokat. A használatukhoz nem kell telepítenie további elemeket az infrastruktúrába.

Az Office 365 gyakran alkalmazott telepítési módszere, hogy ha mindent, a vállalati alkalmazásokat és tanúsítványokat, valamint a Wi-Fi és a VPN konfigurációját is telepíteni kell az eszközökre, akkor kötelező regisztrálni őket felügyeletre. Ez gyakorta előfordul a vállalati tulajdonú eszközök esetében.  


Azonban, ha a felhasználónak egyszerűen csak hozzáférésre van szüksége vállalati e-mailekhez és dokumentumokhoz, ami általában a személyes tulajdonú eszközök esetében fordul, majd megkövetelheti a felhasználó az Office-mobilalkalmazásokat használja (amelyekre a [alkalmazásvédelmi szabályzatok](app-protection-policies.md)és kihagyhatja az eszköz regisztrálását.  



Mindkét esetben a definiált szabályzatok biztosítják az Office 365-adatok megfelelő védelmét.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->


## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>A „saját eszközök használata” program ajánlása a dolgozóknak
A saját eszközök használata (BYOD) egyre népszerűbb a szervezetekben, mivel ezzel a módszerrel csökkenthetők a hardvereszközökre fordított kiadások, és bővíthetők a mobil munkavégzés választási lehetőségei a dolgozók számára. Napjainkban szinte mindenkinek van saját telefonja, miért kellene hát még egyet a dolgozók zsebébe tenni? A legfőbb kihívás mindig az, hogy meg kell győzni a dolgozókat arról, hogy regisztrálják a személyes eszközüket a felügyelet hatálya alá, mivel tartanak attól, hogy az informatikai részleg mit láthat az eszközükön, és mit tud tenni az eszközükkel.  

Ha az eszközök regisztrálása nem kivitelezhető lehetőség, arra az esetre az Intune kínál egy másik BYOD-módszert is, amely egyszerűen csak [felügyeli a vállalati adatokat tartalmazó alkalmazásokat](app-protection-policies.md). Az Intune védelmet nyújt a vállalati adatok számára akkor is, ha a szóban forgó alkalmazás vállalati és személyes adatokhoz is hozzáfér, mint az Office-mobilalkalmazások esetében.  

Rendszergazdaként előírhatja a felhasználóknak, hogy az Office-mobilalkalmazásokkal érjék el az Office 365-öt, és az alkalmazásokat olyan szabályzatokkal konfigurálhatja, amelyek fenntartják az adatok védelmét (például titkosítással, PIN-kódos védelemmel stb.). Ezek az alkalmazásvédelmi szabályzatok megakadályozzák az adatvesztést a nem felügyelt alkalmazásoknál és tárolóhelyeknél, az ilyen alkalmazásokon belül és kívül is. Például a szabályzatok megakadályozzák, hogy a felhasználó szöveget másoljon a vállalati e-mail-profilból egy fogyasztói e-mail-profilba még akkor is, ha mindkét profil az Outlook Mobile-ban van konfigurálva. Hasonló konfigurációkat adhat meg a BYOD-felhasználók által használt más szolgáltatásokhoz és alkalmazásokhoz is.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-employees"></a>Vállalati tulajdonú telefonok kiadása a dolgozóknak
Napjainkban sok dolgozó mobileszközökkel dolgozik, így a versenyképesség fenntartása érdekében elengedhetetlen a termelékenység megteremtése mobileszközökön is. Ezeknek a dolgozóknak zavartalan hozzáférésre van szükségük az összes vállalati alkalmazáshoz és adathoz, tetszőleges időpontban, függetlenül a tartózkodási helyüktől. Gondoskodnia kell arról, hogy a vállalati adatok védettek, a felügyeleti költségek pedig alacsonyak legyenek.  

Az Intune kínál [tömeges kiépítési és felügyeleti megoldásokat](device-enrollment.md) , amelyek integrálhatók a a piacon jelen lévő fő vállalati eszközfelügyeleti platformokkal, beleértve az Apple Készülékregisztrációs programját és a Samsung Knox mobil biztonsági platform. Az eszközkonfigurációknak az Intune-nal történő központi létrehozása elősegíti a vállalati eszközök kiépítésének magas szintű automatizálását.  

Képzelje el a következő helyzetet: az imént adott át egy iPhone-t bontatlan dobozban az egyik dolgozónak. A dolgozó bekapcsolja a telefont, és a telefonon lefut a vállalati beállítási folyamat, amelynek során az eszköznek hitelesítenie kell magát. Az iPhone-t a [biztonsági szabályzatok](device-profiles.md) zökkenőmentesen konfigurálják.

Ezt követően a dolgozó elindítja az Intune Munkahelyi portál alkalmazást, hogy hozzáférjen a számára elérhető vállalati alkalmazásokhoz.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-employees"></a>Korlátozott használatú közösen használható táblagépek kiadása a dolgozóknak
A dolgozók körében egyre jobban terjed a mobil technológiák használata. Például a közösen használt táblagépek már hétköznapi eszköznek tekinthetők a kiskereskedelmi üzletek dolgozói esetében.  Akár egy eladást kell feldolgozni, akár a készletet kell azonnal ellenőrizni, a táblagépek nagyban megkönnyítik a kommunikációt az ügyfelekkel.

Ebben az esetben a felhasználói élmény nagyon fontos jellemzője az egyszerűség. Ebből kifolyólag táblagépek általában által alkalmazott korlátozott használatú módban működnek, például úgy, hogy egyetlen sor üzleti alkalmazás, hogy a dolgozó. Az Intune lehetővé teszi, hogy tömeges kiépítését, védelmét és központi felügyeletét megosztott [iOS és Android](device-profiles.md) eszközöket, amelyek beállíthatók úgy, hogy az ilyen korlátozott használatú módban.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Az Office 365 nem felügyelt nyilvános kioszkból történő biztonságos elérésének engedélyezése a dolgozók számára
A dolgozóknak néha olyan eszközöket, alkalmazásokat vagy böngészőket kell használniuk, amelyeket a vállalat nem tud felügyelni, mint például a kereskedelmi vásárokon vagy a szállodák előterében található nyilvános számítógépeket.

Engedélyezheti a dolgozóknak a vállalati e-mailek elérését ilyen számítógépről? Az Intune és a Microsoft Enterprise Mobility + Security, a válasz egyszerűen lehet "nem", [korlátozza az e-mailek elérését a szervezet által felügyelt eszközök](conditional-access.md). Ez gondoskodik arról, hogy az erős hitelesítésen átesett dolgozók ne hagyjanak véletlenül vállalati adatokat a nem megbízható számítógépen.
