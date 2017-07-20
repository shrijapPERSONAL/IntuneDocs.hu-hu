---
title: "BYOD engedélyezése a Microsoft Intune-nal"
description: 
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 880b83a63eefe13a96ab8838c7092c185aa32cd0
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2017
---
# <a name="enable-byod-with-intune"></a>BYOD engedélyezése az Intune-nal

Ez a témakör az Intune a szervezeti BYOD-megoldások engedélyezéséhez való beállításának fő lépéseit mutatja be. A feladatot három folyamatra, és további útmutatókra mutató hivatkozásra bontottuk.

A munkafolyamat az alábbi három folyamatból áll. Az egyes folyamatok jellemzőit a cége szükségletei szerint testre szabhatja.

-   Az **[Eszközök regisztrálása és a megfelelőség ellenőrzése](#enroll-devices-and-check-for-compliance)** című szakasz a felhasználók személyes eszközei felügyeleti Intune-regisztrációjának engedélyezését ismerteti. Az Intune az iOS-, macOS-, Android- és Windows-eszközöket felügyeli. Ez a szakasz emellett a szabályzatok az eszközökön való bevezetését, valamint a szabályzatokhoz tartozó alapvető biztonsági követelmények betartásának módját is ismerteti.

- A **[Hozzáférés biztosítása a vállalati erőforrásokhoz](#provide-access-to-company-resources)** című szakasz azt ismerteti, hogy az üzemeltető hogyan engedélyezheti a felhasználóknak a céges erőforrásokhoz való könnyű és biztonságos hozzáférést. Ezt hozzáférésprofilok a felügyelt eszközökön való üzembe helyezésével érheti el. Ez a szakasz emellett a mennyiségi licencszerződés keretében vásárolt alkalmazások az Intune-nal való üzembe helyezését is ismerteti.

-   A **[Vállalati adatok védelme](#protect-company-data)**című szakasz bemutatja, hogyan lehet feltételes hozzáférést nyújtani a céges erőforrásokhoz, megelőzni az adatvesztést, és eltávolítani a vállalati alkalmazásokat és adatokat azokról az eszközökről, amelyek szükségtelenné váltak a munkához, illetve amelyeket elloptak vagy elveszítettek.

[![A BYOD a Microsoft Intune-nal való engedélyezési munkafolyamat-ábrájának fő lépései](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Előkészületek
Mielőtt a felhasználók regisztrálhatnák az eszközeiket, Önnek elő kell készítenie az Intune-szolgáltatást. Ehhez [rendeljen licenceket a felhasználókhoz](licenses-assign.md) és [adja meg a mobileszköz-felügyeleti szolgáltatót](mdm-authority-set.md).

Ebben a lépésben célszerű [testre szabni a céges portált](company-portal-customize.md). Adjon hozzá vállalati védjegyzést, és nyújtson támogatási információkat a felhasználóknak. Ezzel egy megbízható regisztrációs és támogatási élményt nyújthat a felhasználóinak.

## <a name="enroll-devices-and-check-for-compliance"></a>Eszközök regisztrálása és a megfelelőség ellenőrzése

Az Intune előkészítése után meg kell győződnie arról, hogy a felügyelni kívánt eszköztípusok megfelelnek a különböző regisztrációs követelményeknek. Az eszközregisztráció folyamata cseppet sem bonyolult, ám eszköztípusonként némileg eltérő.

-   **iOS- és Mac-eszköz** iPadek, iPhone-ok és Mac OS-es eszközök regisztrálásához [be kell szereznie egy Apple Push Notification- (APNs) tanúsítványt](apple-mdm-push-certificate-get.md). Ha feltöltötte az APNs-tanúsítványt az Intune-ba, megkezdheti az [iOS-es eszközök regisztrálását](/intune-user-help/enroll-your-device-in-intune-ios) a Céges portál alkalmazással, illetve a [Mac OS-es eszközök regisztrálását](/intune-user-help/enroll-your-device-in-intune-macos) a Céges portál webhelyen.

-   **Android-eszközök** Android-eszközein nincs teendője, ezek alapértelmezés szerint készen állnak az Intune szolgáltatásba való regisztrációra. A felhasználók rendkívül egyszerűen, a Google Play Áruházban elérhető Munkahelyi portál alkalmazással [regisztrálhatják Android-eszközeiket](/intune-user-help/enroll-your-device-in-intune-android.md).

-   **Windows Phone-telefonok és Windows rendszerű PC-k** A Windows-eszközök regisztrálását megkönnyíti, ha [beállítja a regisztrációs kiszolgáló DNS-aliasnevét](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium). Ha ezt nem szeretné, a felhasználók munkahelyi vagy iskolai fiók hozzáadásával is [regisztrálhatják a Windows-eszközöket](/intune-user-help/enroll-your-w10-phone-or-w10-pc-windows).

  - Ha rendelkezik az Azure AD Premium szolgáltatással, az [automatikus regisztrálási](windows-enroll.md) funkció aktiválásával még könnyebbé teheti a felhasználói Windows-eszközök regisztrálását. Ez a funkció automatikusan regisztrálja az Intune-ba az eszközöket, amikor egy felhasználó egy munkahelyi vagy iskolai fiókkal regisztrál egy személyes eszközt. Emellett a vállalati tulajdonban lévő, a cég Azure AD-szolgáltatásához csatlakozó eszközökkel is működik.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>A felügyelt eszközök alapvető biztonsági követelményeknek való megfelelésének ellenőrzése

Miután a felhasználók regisztrálják eszközeiket a felügyelet alá, az IT-részlegnek biztosítania kell, hogy a vállalati alkalmazások és adatok elérésére használt eszközök megfeleljenek az alapvető biztonsági követelményeknek. Ilyen szabály lehet például, hogy PIN-kódot kell használni az eszközök eléréséhez, és titkosítani kell az eszközökön tárolt adatokat. Az ilyen szabályok összességét [megfelelőségi szabályzatnak](device-compliance.md) nevezzük.

Amikor [megfelelőségi szabályzatot telepít](device-compliance-get-started.md) egy felhasználónak, akkor az Intune az illető összes Intune által felügyelt eszközénél ellenőrzi, hogy megfelelnek-e a BYOD-szabályzat részeként definiált alapvető biztonsági követelményeknek. Az eszközök a megfelelőségi ellenőrzés után lejelentik állapotukat az Intune-nak. Bizonyos esetekben előfordulhat, hogy a rendszer a felhasználóktól egyes beállítások módosítását kéri, például a PIN-kód vagy az eszköztitkosítás megváltoztatását. Egyéb esetekben a céges portál alkalmazás egyszerű értesítést küld a felhasználónak a szabályzat feltételeinek nem megfelelő beállításokról.

## <a name="provide-access-to-company-resources"></a>Hozzáférés biztosítása a vállalati erőforrásokhoz

Általános jelenség, hogy dolgozói szeretnék mobileszközeiken is elérni a vállalati levelezést és dokumentumokat. Az is fontos szempont számukra, hogy ennek beállításához ne kelljen bonyolult lépéseket elvégezni, illetve a segélyszolgálatnak telefonálgatni. Az Intune segítségével könnyebben [hozhat létre és telepíthet e-mail-beállításokat](conditional-access-intune-common-ways-use.md) a mobileszközökre előre telepített natív levelezőalkalmazásokhoz.
<!--- this was old link: (https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune). check with Andre--->

> [!NOTE]
> Az Intune támogatja az Android for Work e-mail profiljainak konfigurálását a Google Play Áruházban is megtalálható Gmail és Nine Work levelezőalkalmazásokra vonatkozóan.

Az Intune-nal emellett felügyelheti és megvédheti a helyszíni céges adatok hozzáférését, amikor a felhasználók külső helyszínen dolgoznak. Az Intune-alapú [Wi-Fi-](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN-](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) és e-mail-profilokkal hozzáférést biztosíthat a felhasználóknak a munkájuk elvégzéséhez szükséges fájlokhoz és erőforrásokhoz, bárhol legyenek is. Az Azure Active Directory alkalmazásproxy és a feltételes hozzáférési funkciók segítségével a vállalat helyileg üzemeltetett webes alkalmazásai és szolgáltatásai is biztonságosan elérhetők és megvédhetők.

### <a name="manage-volume-purchased-apps"></a>Mennyiségi programban vásárolt alkalmazások felügyelete
Az Intune-nal könnyen elvégezheti az alábbi műveleteket:
* A mennyiségi licencelési információk importálása bármelyik alkalmazásáruházból
* A használt licencek nyomon követése
* Annak megakadályozása, hogy a felhasználók több példányt telepítsenek az alkalmazásból, mint amennyit vásárolt
* [Áruházbeli alkalmazások telepítése a felügyelt eszközökre](apps-deploy.md)
* A céges portál webhelyen még nem felügyelt eszközök megcélzása az alkalmazásokkal

Az Intune az iOS App Store áruházból és a Vállalati Windows Áruházból mennyiségi programban megvásárolt alkalmazások felügyeletét és üzembe helyezését is lehetővé teszi. Ezzel a megoldással csökkenthetők a mennyiségi konstrukcióban vásárolt alkalmazások nyilvántartásával járó adminisztratív terhek.

> [!TIP]
> Konfigurálhatja az [egyszeri bejelentkezést (SSO) az Azure AD Connecttel](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). Az egyszeri bejelentkezés lehetővé teszi a felhasználók számára, hogy a helyszínen használt tartományi felhasználónévvel és jelszóval bejelentkezzenek az alkalmazásokba. Az Azure Active Directory alkalmazásproxyval pedig [internetes hozzáférést biztosíthat a helyszíni üzemeltetésű webalkalmazásokhoz](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

-   [Mennyiségi konstrukcióban vásárolt alkalmazások felügyelete iOS-eszközökön](vpp-apps-ios.md): Az [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) programon keresztül egyszerre több licencet vásárolhat az iOS-alkalmazásokhoz. Ehhez Apple VPP-fiókot kell beállítania az Apple webhelyén, és az Apple VPP-tokent fel kell tölteni az Intune-ba. Ezután szinkronizálhatja a mennyiségi vásárlás adatait az Intune-nal, és nyomon követheti a mennyiségi programban vásárolt alkalmazás használatát.

-   [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése](windows-store-for-business.md). A [Vállalati Windows Áruházban](https://www.microsoft.com/business-store) alkalmazásokat vásárolhat a szervezete számára egyenként vagy nagyobb mennyiségben. Az áruházat az Intune-nal összekapcsolva a mennyiségi licencszerződés keretében vásárolt alkalmazásokat az Intune-portálról kezelheti.

## <a name="protect-company-data"></a>Vállalati adatok védelme

Az Intune a vállalati adatokat számos technológiai réteg segítségével védi. Az identitáskezelő rétegben a feltételes hozzáférés gondoskodik a védelemről. A feltételes hozzáféréssel a szolgáltatásokhoz csak felügyelt, illetve a szabályoknak megfelelő eszközökkel lehet hozzáférni. Az ügyfél-alkalmazási rétegben a mobilalkalmazás-kezelés (MAM) gondoskodik az adatvesztés elleni védelemről.  Ennek részeként megakadályozza az adatok nem védett alkalmazásokba vagy tárhelyekre történő áthelyezését, valamint az eszköz elvesztése vagy ellopása esetén törlik az adatokat.

### <a name="enforce-conditional-access-to-company-resources"></a>A vállalati erőforrásokhoz való feltételes hozzáférés betartatása

A [feltételes hozzáférési szabályzatok](device-compliance.md) és a megfelelőségi szabályzatok együttes használata révén ellenőrizheti, hogy az eszközök megfelelnek-e a BYOD-szabályzat által támasztott alapvető biztonsági követelményeknek. Ha egy eszköz nem felel meg a szabályzatnak, a szabályok életbe lépnek, és az eszköz nem kap hozzáférést, amíg nem konfigurálják a követelményekkel összhangban. Így biztosítható, hogy csak a felügyelt és a szabályzatoknak megfelelő eszközök férhessenek hozzá a különféle szolgáltatásokban , például az Exchange-ben ([helyszíni Exchange](exchange-connector-install.md) vagy [Exchange Online](conditional-access-exchange-create.md)), a SharePoint Online-on vagy a Skype Vállalati online verzióban tárolt céges adatokhoz.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> A feltételes hozzáférési szabályzatok csak akkor működnek, ha korábban már létrehozott egy megfelelőségi szabályzatot, amelynek alapján a rendszer értékelni tudja a megfelelést.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Vállalati adatvesztés megelőzése alkalmazásvédelmi szabályzatokkal

Az Intune alkalmazásvédelmi szabályzataival Ön döntheti el, hogyan történjen az adatok elérése eszközregisztrációval, illetve anélkül. Ez a sokoldalúság teszi lehetővé a céges adatok védelmét, így a felhasználók akkor is biztonságosan elérhetik azokat, ha nem regisztrálták az eszközüket az Intune-nal.

Az [Intune alkalmazásvédelmi szabályzataival](app-protection-policies.md) védheti a felhasználók iOS-es és androidos eszközeivel elért vállalati adatokat. Ezeknek az alkalmazásszintű szabályzatoknak a használatával megszabhatja, hogy dolgozói hogyan használhatják fel és oszthatják meg az adatokat még akkor is, ha valamelyik eszközt nem felügyeli az Intune.

A [Windows Információvédelem (WIP) szabályzataival](app-protection-policies-configure-windows-10.md) ugyanezt teheti meg a felügyelt Windows 10-es eszközökön. Ezek a szabályzatok nem befolyásolják a dolgozók felhasználói élményét, és nem igénylik a hálózati környezet és más alkalmazások módosítását sem.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Céges adatok törlése a személyes adatok érintetlenül hagyásával

Fontos, hogy el lehessen távolítani a vállalati alkalmazásokat és adatokat azokról az eszközökről, ha azokat a továbbiakban már nem fogják munkahelyi célokra használni, más célra hasznosítják, esetleg elhagyják őket. Ehhez az Intune szelektív és teljes törlési funkcióit használhatja. A felhasználók az Intune céges portálról távolról is törölhetik saját eszközeiket, ha azokat korábban regisztrálták az Intune-ban.

A [teljes törlés](devices-wipe.md) visszaállítja az eszközt a gyári beállításokra, és eltávolít minden felhasználói adatot és beállítást. A [szelektív törlés](devices-wipe.md#selective-wipe) csak a vállalati adatokat távolítja el az eszközről, a személyes felhasználói adatokat nem érinti.

A parancs kiadását követően a rendszer azonnal elkezdi a szelektív törlési folyamatot, és kivonja az eszközt a felügyelet alól. Az eljárás hatására az eszközről eltűnik az összes vállalati adat, az eszköz neve pedig kikerül az Intune felügyeleti konzoljából. Ezzel végéhez ér az eszközfelügyeleti életciklus.