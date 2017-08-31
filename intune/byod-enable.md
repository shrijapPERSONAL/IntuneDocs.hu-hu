---
title: "BYOD engedélyezése a Microsoft Intune-nal"
description: "Az Intune a szervezeti BYOD-megoldások engedélyezéséhez való beállításának fő lépései."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: fa70e21b9e9f7adfc508e24bd442a48c834ed7db
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2017
---
# <a name="enable-byod-with-intune"></a>BYOD engedélyezése az Intune-nal

Ez a témakör az Intune a szervezeti BYOD-megoldások engedélyezéséhez való beállításának fő lépéseit mutatja be. A feladatot három folyamatra, és további útmutatókra mutató hivatkozásra bontottuk.

A munkafolyamat az alábbi három folyamatból áll. Az egyes folyamatok jellemzőit a cége szükségletei szerint testre szabhatja.

-   Az **[Eszközök regisztrálása és a megfelelőség ellenőrzése](#enroll-devices-and-check-for-compliance)** című szakasz a felhasználók személyes eszközei felügyeleti Intune-regisztrációjának engedélyezését ismerteti. Az Intune az iOS-, macOS-, Android- és Windows-eszközöket felügyeli. Ez a szakasz emellett a szabályzatok az eszközökön való bevezetését, valamint a szabályzatokhoz tartozó alapvető biztonsági követelmények betartásának módját is ismerteti.

- A **[Hozzáférés biztosítása a vállalati erőforrásokhoz](#provide-access-to-company-resources)** című szakasz azt ismerteti, hogyan engedélyezheti a felhasználóknak a céges erőforrásokhoz való könnyű és biztonságos hozzáférést. Ezt hozzáférésprofilok a felügyelt eszközökön való üzembe helyezésével érheti el. Ez a szakasz emellett a mennyiségi licencszerződés keretében vásárolt alkalmazások az Intune-nal való üzembe helyezését is ismerteti.

-   A **[Vállalati adatok védelme](#protect-company-data)**című szakasz bemutatja, hogyan lehet feltételes hozzáférést nyújtani a céges erőforrásokhoz, megelőzni az adatvesztést, és eltávolítani a vállalati alkalmazásokat és adatokat azokról az eszközökről, amelyek szükségtelenné váltak a munkához, illetve amelyeket elloptak vagy elveszítettek.

[![A BYOD a Microsoft Intune-nal való engedélyezési munkafolyamat-ábrájának fő lépései](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Előkészületek
Mielőtt a felhasználók regisztrálhatnák az eszközeiket, Önnek elő kell készítenie az Intune-szolgáltatást. Ehhez [rendeljen licenceket a felhasználókhoz](licenses-assign.md) és [adja meg a mobileszköz-felügyeleti szolgáltatót](mdm-authority-set.md).

Ebben a lépésben célszerű [testre szabni a céges portált](company-portal-customize.md). Adjon hozzá vállalati védjegyzést, és nyújtson támogatási információkat a felhasználóknak. Ezzel egy megbízható regisztrációs és támogatási élményt nyújthat a felhasználóinak. Létrehozhat [használati feltételeket](terms-and-conditions-create.md) is, amelyeket a felhasználóknak el kell fogadniuk a regisztráció előtt, illetve olyan [eszközkorlátozásokat](enrollment-restrictions-set.md) is, amelyek a támogatott platformokat határozzák meg.

## <a name="enroll-devices-and-check-for-compliance"></a>Eszközök regisztrálása és a megfelelőség ellenőrzése

Az Intune előkészítése után meg kell győződnie arról, hogy a felügyelni kívánt eszköztípusok megfelelnek a különböző regisztrációs követelményeknek. Az eszközregisztráció folyamata cseppet sem bonyolult, ám eszköztípusonként némileg eltérő.

-   **iOS- és Mac-eszközök** iPadek, iPhone-ok és macOS rendszerű eszközök regisztrálásához [be kell szereznie egy Apple MDM Push-tanúsítványt](apple-mdm-push-certificate-get.md). Ha feltöltötte az MDM Push-tanúsítványt az Intune-ba, a felhasználók megkezdhetik az [iOS-eszközök regisztrálását](/intune-user-help/enroll-your-device-in-intune-ios) a Céges portál alkalmazásban, illetve a [macOS rendszerű eszközök regisztrálását](/intune-user-help/enroll-your-device-in-intune-macos) a Céges portál webhelyen.

-   **Android-eszközök** Android-eszközein nincs teendője, ezek alapértelmezés szerint készen állnak az Intune szolgáltatásba való regisztrációra. A felhasználók rendkívül egyszerűen, a Google Play Áruházban elérhető Munkahelyi portál alkalmazással [regisztrálhatják Android-eszközeiket](/intune-user-help/enroll-your-device-in-intune-android).

-   **Windows Phone-telefonok és PC-k** A Windows-eszközök további beállítások használatával regisztrálhatók. A felhasználói élmény egyszerűsítése érdekében engedélyezheti a Windows 10-es számítógépek és a Windows 10-es mobileszközök prémium szintű Azure Active Directory (AD) szolgáltatásban való automatikus regisztrációját. Ha nem rendelkezik Azure AD Premium szolgáltatással, vagy ha a Windows 8.1-hez van szüksége támogatásra, a regisztrálási folyamat megkönnyítése érdekében létrehozhat [a regisztrációs kiszolgálóhoz tartozó DNS-aliast](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium).


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>A felügyelt eszközök alapvető biztonsági követelményeknek való megfelelésének ellenőrzése

Miután a felhasználók regisztrálják eszközeiket a felügyelet alá, az IT-részlegnek biztosítania kell, hogy a vállalati alkalmazások és adatok elérésére használt eszközök megfeleljenek az alapvető biztonsági követelményeknek. Ilyen szabály lehet például, hogy PIN-kódot kell használni az eszközök eléréséhez, és titkosítani kell az eszközökön tárolt adatokat. Az ilyen szabályok összességét [megfelelőségi szabályzatnak](device-compliance.md) nevezzük.

Amikor [megfelelőségi szabályzatot telepít](device-compliance-get-started.md) egy felhasználó számára, az Intune az illető összes Intune által felügyelt eszközénél ellenőrzi, hogy az eszköz megfelel-e a BYOD-szabályzat részeként definiált alapvető biztonsági követelményeknek. Az eszközök a megfelelőségi ellenőrzés után lejelentik állapotukat az Intune-nak. Bizonyos esetekben előfordulhat, hogy a rendszer a felhasználóktól egyes beállítások módosítását kéri, például a PIN-kód vagy az eszköztitkosítás megváltoztatását. Egyéb esetekben a céges portál alkalmazás egyszerű értesítést küld a felhasználónak a szabályzat feltételeinek nem megfelelő beállításokról.

## <a name="provide-access-to-company-resources"></a>Hozzáférés biztosítása a vállalati erőforrásokhoz

Általános jelenség, hogy az alkalmazottak szeretnék mobileszközeiken is elérni a céges levelezést és dokumentumokat. Az is fontos szempont számukra, hogy ennek beállításához ne kelljen bonyolult lépéseket elvégezni, vagy felhívni az ügyfélszolgálatot. Az Intune segítségével könnyebben [hozhat létre és telepíthet e-mail-beállításokat](email-settings-configure.md) a mobileszközökre előre telepített natív levelezőalkalmazásokhoz.


> [!NOTE]
> Az Intune támogatja az Android for Work e-mail profiljainak konfigurálását a Google Play Áruházban is megtalálható Gmail és Nine Work levelezőalkalmazásokra vonatkozóan.

Az Intune-nal emellett felügyelheti és megvédheti a helyszíni céges adatok hozzáférését, amikor a felhasználók külső helyszínen dolgoznak. Az Intune-alapú [Wi-Fi-](wi-fi-settings-configure.md), [VPN-](vpn-settings-configure.md) és e-mail-profilokkal hozzáférést biztosíthat a felhasználóknak a munkájuk elvégzéséhez szükséges fájlokhoz és erőforrásokhoz, bárhol legyenek is. Az Azure Active Directory alkalmazásproxy és a feltételes hozzáférési funkciók segítségével a vállalat helyileg üzemeltetett webes alkalmazásai és szolgáltatásai is biztonságosan elérhetők és megvédhetők.

### <a name="manage-volume-purchased-apps"></a>Mennyiségi programban vásárolt alkalmazások felügyelete
Az Intune-nal könnyen elvégezheti az alábbi műveleteket:
* A mennyiségi licencelési információk importálása bármelyik alkalmazásáruházból
* A használt licencek nyomon követése
* Annak megakadályozása, hogy a felhasználók több példányt telepítsenek az alkalmazásból, mint amennyit vásárolt
* [Áruházbeli alkalmazások telepítése a felügyelt eszközökre](apps-deploy.md)
* A céges portál webhelyen még nem felügyelt eszközök megcélzása az alkalmazásokkal

Az Intune az iOS App Store áruházból és a Vállalati Microsoft Áruházból mennyiségi programban megvásárolt alkalmazások felügyeletét és üzembe helyezését is lehetővé teszi. Ezzel a megoldással csökkenthetők a mennyiségi konstrukcióban vásárolt alkalmazások nyilvántartásával járó adminisztratív terhek.

> [!TIP]
> Konfigurálhatja az [egyszeri bejelentkezést (SSO) az Azure AD Connecttel](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). Az egyszeri bejelentkezés lehetővé teszi a felhasználók számára, hogy a helyszínen használt tartományi felhasználónévvel és jelszóval bejelentkezzenek az alkalmazásokba. Az Azure Active Directory alkalmazásproxyval pedig [internetes hozzáférést biztosíthat a helyszíni üzemeltetésű webalkalmazásokhoz](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

-   [Mennyiségi konstrukcióban vásárolt alkalmazások felügyelete iOS-eszközökön](vpp-apps-ios.md): Az [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) programon keresztül egyszerre több licencet vásárolhat az iOS-alkalmazásokhoz. Ehhez Apple VPP-fiókot kell beállítania az Apple webhelyén, és az Apple VPP-tokent fel kell tölteni az Intune-ba. Ezután szinkronizálhatja a mennyiségi vásárlás adatait az Intune-nal, és nyomon követheti a mennyiségi programban vásárolt alkalmazás használatát.

-   [A Vállalati Microsoft Áruházban vásárolt alkalmazások kezelése](windows-store-for-business.md). A [Vállalati Microsoft Áruházban](https://www.microsoft.com/business-store) alkalmazásokat kereshet a vállalat számára és egyenként vagy nagyobb mennyiségben is vásárolhat közülük. Az áruházat az Intune-nal összekapcsolva a mennyiségi licencszerződés keretében vásárolt alkalmazásokat az Intune-portálról kezelheti.

## <a name="protect-company-data"></a>Vállalati adatok védelme

Az Intune a vállalati adatokat számos technológiai réteg segítségével védi. Az identitáskezelő rétegben a feltételes hozzáférés gondoskodik a védelemről. A feltételes hozzáféréssel a szolgáltatásokhoz csak felügyelt, illetve a szabályoknak megfelelő eszközökkel lehet hozzáférni. Az ügyfélalkalmazási réteg szintjén alkalmazásvédelmi szabályzatok nyújtanak védelmet az adatvesztés ellen. Ennek részeként megakadályozza az adatok nem védett alkalmazásokba vagy tárhelyekre történő áthelyezését, valamint az eszköz elvesztése vagy ellopása esetén törlik az adatokat.

### <a name="enforce-conditional-access-to-company-resources"></a>A vállalati erőforrásokhoz való feltételes hozzáférés betartatása

A [feltételes hozzáférési szabályzatok](device-compliance.md) és a megfelelőségi szabályzatok együttes használata révén ellenőrizheti, hogy az eszközök megfelelnek-e a BYOD-szabályzat által támasztott alapvető biztonsági követelményeknek. Ha egy eszköz nem felel meg a szabályzatnak, a szabályok életbe lépnek, és az eszköz nem kap hozzáférést, amíg nem konfigurálják a követelményekkel összhangban. Így biztosítható, hogy csak a felügyelt és a szabályzatoknak megfelelő eszközök férhessenek hozzá a különféle szolgáltatásokban , például az Exchange-ben ([helyszíni Exchange](exchange-connector-install.md) vagy [Exchange Online](conditional-access-exchange-create.md)), a SharePoint Online-on vagy a Skype Vállalati online verzióban tárolt céges adatokhoz.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> A feltételes hozzáférési szabályzatok csak akkor működnek, ha korábban már létrehozott egy megfelelőségi szabályzatot, amelynek alapján a rendszer értékelni tudja a megfelelést.

### <a name="prevent-data-loss-of-company-data-with-app-protection-policies"></a>A céges adatvesztés megelőzése alkalmazásvédelmi szabályzatokkal

Az Intune alkalmazásvédelmi szabályzataival Ön döntheti el, hogyan történjen az adatok elérése eszközregisztrációval, illetve anélkül. Ez a sokoldalúság teszi lehetővé a céges adatok védelmét, így a felhasználók akkor is biztonságosan elérhetik azokat, ha nem regisztrálták az eszközüket az Intune-nal.

Az [Intune alkalmazásvédelmi szabályzataival](app-protection-policies.md) megvédheti azokat a céges adatokat, amelyeket a felhasználók iOS- és Android-eszközeikkel érnek el. Ezeknek az alkalmazásszintű szabályzatoknak a használatával megszabhatja, hogy dolgozói hogyan használhatják fel és oszthatják meg az adatokat még akkor is, ha valamelyik eszközt nem felügyeli az Intune.

A [Windows Information Protection (WIP)](app-protection-policies-configure-windows-10.md) használatával ugyanezt megteheti felügyelt Windows 10-s eszközök esetében is. Ezek a szabályzatok nem befolyásolják a dolgozók felhasználói élményét, és nem igénylik a hálózati környezet és más alkalmazások módosítását sem.

### <a name="remove-company-data-while-leaving-personal-data-intact"></a>Céges adatok törlése a személyes adatok érintetlenül hagyásával

A céges alkalmazásokat és adatokat el lehet távolítani azokról az eszközökről, amelyeket a továbbiakban már nem használnak munkahelyi célokra, a továbbiakban más célra fognak használni, vagy elvesztek. Erre az Intune a céges adatok eltávolítása és a gyári beállítások visszaállítása funkciók használatával ad lehetőséget. A felhasználók az Intune Céges portálról távolról is visszaállíthatják saját eszközeiket, ha azokat korábban regisztrálták az Intune-ban.

A [gyári beállítások visszaállítása](devices-wipe.md) visszaállítja az eszközt a gyári alaphelyzetre, eltávolít minden felhasználói adatot és beállítást, és eltávolítja az eszközt az Intune felügyeleti szolgáltatásából. A [Céges adatok eltávolítása](devices-wipe.md#remove-company-data) csak a céges adatokat távolítja el az eszközről, a személyes felhasználói adatokat nem érinti.

Az eljárás indítása után az eszköz azonnal hozzálát a visszaállítás folyamatához. Az eljárás hatására az eszközről eltűnik az összes vállalati adat, az eszköz neve pedig el lesz távolítva az Intune-ból. Ezzel végéhez ér az eszközfelügyeleti életciklus.
