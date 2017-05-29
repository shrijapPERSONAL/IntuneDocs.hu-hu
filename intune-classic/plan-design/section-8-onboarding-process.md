---
title: "Az Intune bevezetési folyamata | Microsoft Docs"
description: "Ez a cikk részletesen ismerteti azokat a szempontokat, amelyeket figyelembe kell venni az Intune kizárólag felhőalapú megoldásának bevezetési folyamatánál saját környezetben."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 562e24af8058df56f1b952c82fefe62d38388ec3
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="intune-implementation"></a>Az Intune implementációja

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A bevezetési fázis során az Intune éles környezetbe való implementálása történik. Az implementálási folyamat során az Intune és (ha szükséges) a külső függőségek telepítése és konfigurálása zajlik az ebben az útmutatóban már korábban áttekintett [használatieset-követelmények](section-3-determine-use-case-requirements.md) alapján.

A következő szakasz áttekintést nyújt az Intune implementálási folyamatáról, többek között a követelményekről és az átfogó szintű feladatokról.

>[!TIP]
> A [További forrásokban](additional-resources.md) még több információt talál az Intune implementálási folyamatáról.

## <a name="intune-requirements"></a>Az Intune-ra vonatkozó követelmények

Az önálló Intune-ra vonatkozó követelmények az alábbiak:

-   EMS/Intune-előfizetés

-   Office 365-előfizetés (Office-alkalmazásokhoz és MAM-szabályzat által kezelt alkalmazásokhoz)

-   Apple APNs-tanúsítvány (iOS eszközplatform kezeléséhez)

-   Azure AD Connect (címtár-szinkronizáláshoz)

-   Exchange-hez készült Intune On-Premises Connector (hitelesítésszolgáltatóhoz helyszíni Exchange-hez, ha szükséges)

-   Intune Certificate Connector (SCEP-tanúsítvány telepítéséhez, ha szükséges)

>[!TIP]
> Az önálló Intune követelményeiről [itt](/intune-classic/get-started/what-to-know-before-you-start-microsoft-intune) talál további információt.

## <a name="intune-implementation-process"></a>Az Intune implementációjának folyamata

### <a name="overview-of-implementation-tasks"></a>Az implementációs feladatok áttekintése

Az alábbiakban áttekintjük az Intune implementálásának egyes feladatait.

#### <a name="task-1-add-intune-subscription"></a>1. feladat: Intune-előfizetés hozzáadása

Ahogy azt az előző szakaszban említettük, szükség van EMS- vagy Intune-előfizetésre. Ha a szervezet még nem rendelkezik EMS- vagy Intune-előfizetéssel, vegye fel a kapcsolatot a Microsofttal vagy a Microsoft-fiók ügyfélszolgálatával az Enterprise Mobility + Security (EMS) vagy az Intune megvásárlásával kapcsolatban.

-   További információk a [Microsoft Intune megvásárlásával](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing) kapcsolatban.

#### <a name="task-2-add-office-365-subscription"></a>2. feladat: Office 365-előfizetés hozzáadása

Ez a lépés nem kötelező. Ahogy a követelményeket ismertető előző fejezetben szerepelt, Office 365-előfizetésre van szükség, ha az Exchange Online-t kívánja használni, és ha MAM-szabályzatokkal kívánja felügyelni Office mobilalkalmazásait. Ha a szervezet még nem rendelkezik Office 365-előfizetéssel, vegye fel a kapcsolatot a Microsofttal vagy a Microsoft-fiók ügyfélszolgálatával az Office 365 megvásárlásával kapcsolatban.

-   További információk az [Office 365 megvásárlásával](https://products.office.com/business/compare-office-365-for-business-plans) kapcsolatban.

#### <a name="task-3-add-users-groups-in-azure-ad"></a>3. feladat: felhasználói csoportok hozzáadása az Azure AD-ben

Az Intune üzembe helyezésének használatieset-forgatókönyvei és a követelmények függvényében szükség lehet felhasználók vagy biztonsági csoportok hozzáadására az AD-ben vagy az AAD-ben. Javasoljuk, hogy tekintse át az Active Directory vagy az Azure Active Directory jelenlegi felhasználóit és biztonsági csoportjait, és ellenőrizze, hogy mindenben megfelelnek-e a szükségleteknek. Az új felhasználókat és biztonsági csoportokat általában az Active Directoryban kell felvenni, majd az Azure AD Directory Connect segítségével az Azure Active Directoryban szinkronizálni.

-   További információk: [felhasználók és csoportok hozzáadása az Intune-ban](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>4. feladat: Intune és Office 365 felhasználói licencek hozzárendelése

Az EMS/Intune és az Office 365 bevezetésével érintett minden felhasználónak rendelkeznie kell egy hozzá rendelt licencel. Az EMS/Intune- és Office 365-licencek hozzárendelését az Office 365 Felügyeleti központ portálján lehet elvégezni.

-   További információ: [Intune-licencek hozzárendelése](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>5. feladat: az Intune beállítása mobileszköz-kezelő szolgáltatóként

Mielőtt elkezdené az eszközök beállítását, konfigurálását, felügyeletét és regisztrálását az Intune-ban, először be kell állítania az Intune-t mobileszköz-kezelő szolgáltatóként. A mobileszköz-kezelő szolgáltató beállítását az Intune felügyeleti portálon, a Rendszergazda munkaterületen lehet elvégezni.

-   További információ: [a mobileszköz-kezelő szolgáltató beállítása](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>6. feladat: eszközplatformok engedélyezése

Alapértelmezés szerint az Intune felügyeleti konzolján a legtöbb eszközplatform engedélyezve van, kivéve az Apple-eszközöket (iOS és Mac). Az iOS-eszközök Intune-beli regisztrálása és felügyelete előtt az eszközplatformot engedélyezni kell. Az iOS-eszközplatform engedélyezése három lépésben végezhető el: az APNs-tanúsítvány létrehozása, letöltése, majd az APNs-tanúsítvány feltöltése az Intune-ba.

-   További tudnivalók [az iOS és Mac eszközkezelés beállításáról.]/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>7. feladat: használati feltételekre vonatkozó szabályzatok hozzáadása és telepítése

A Microsoft Intune támogatja a használati feltételekre vonatkozó szabályzatok hozzáadását és telepítését. A használati feltételekre vonatkozó szabályzatok hozzáadása és telepítése az Intune felügyeleti portálon, a Házirend munkaterületen végezhető el. A használati feltételekre vonatkozó szabályzatokat szükség szerint adja hozzá, és az Intune üzembe helyezésének használatieset-forgatókönyveit és a követelményeket figyelembe véve telepítse őket a célcsoportoknál.

-   További információk: [A használati feltételekre vonatkozó szabályzatok hozzáadása és telepítése](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>8. feladat: konfigurációs szabályzatok hozzáadása és telepítése

A Microsoft Intune kétféle konfigurációs szabályzat hozzáadását támogatja: általános és egyéni. A konfigurációs szabályzatok hozzáadása és telepítése az Intune felügyeleti portálon, a Házirend munkaterületen végezhető el. A konfigurációs szabályzatokat szükség szerint adja hozzá, és az Intune üzembe helyezésének használatieset-forgatókönyveit és a követelményeket figyelembe véve telepítse őket a célcsoportoknál.

-   További információk: [konfigurációs szabályzatok hozzáadása és telepítése](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>9. feladat: erőforrásprofilok hozzáadása és telepítése

A Microsoft Intune E-mail-, Wi-Fi- és VPN-profilokat támogat. A profilok hozzáadása és telepítése az Intune felügyeleti portálon, a Házirend munkaterületen végezhető el. A konfigurációs szabályzatokat szükség szerint adja hozzá, és az Intune üzembe helyezésének használatieset-forgatókönyveit és a követelményeket figyelembe véve telepítse őket a célcsoportoknál.

-   További információ: [a vállalati erőforrások hozzáférésének engedélyezése az Intune-nal](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>10. feladat: alkalmazások hozzáadása és telepítése

A Microsoft Intune a webes, üzletági és a nyilvános áruházból származó alkalmazások telepítését támogatja. Ezen kívül támogatott az olyan alkalmazások felügyelete is, amelyekkel MAM-szabályzatok alkalmazásával integrálva van az Intune SDK. Alkalmazások hozzáadása és telepítése az Intune felügyeleti portálon, az Alkalmazások munkaterületen végezhető el. MAM-szabályzatok hozzáadása és telepítése az Intune felügyeleti portálon, a Házirend munkaterületen végezhető el. Az alkalmazásokat szükség szerint adja hozzá, és az Intune üzembe helyezésének használatieset-forgatókönyveit és a követelményeket figyelembe véve telepítse őket a célcsoportoknál.

-   További információk: [alkalmazások hozzáadása és telepítése](/intune-classic/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>11. feladat: megfelelőségi szabályzatok hozzáadása és telepítése

A Microsoft Intune támogatja a megfelelőségi szabályzatok használatát. A megfelelőségi szabályzatok hozzáadása és telepítése az Intune felügyeleti portálon, a Házirend munkaterületen végezhető el. A megfelelőségi szabályzatokat szükség szerint adja hozzá, és az Intune üzembe helyezésének használatieset-forgatókönyveit és a követelményeket figyelembe véve telepítse őket a célcsoportoknál.

-   További információ: [megfelelőségi szabályzatok](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>12. feladat: feltételes hozzáférési szabályzat engedélyezése

A Microsoft Intune támogatja a feltételes hozzáférési folyamatot online / helyszíni Exchange esetén, a SharePoint Online-t, a Skype Vállalati online verziót és a Dynamics CRM Online-t. A feltételes hozzáférési szabályzatokat az Intune felügyeleti portálon, a Házirend munkaterületen engedélyezheti. A feltételes hozzáférési szabályzatokat szükség szerint engedélyezze, figyelembe véve [az Intune üzembe helyezésének használatieset-forgatókönyveit és a követelményeket](section-3-determine-use-case-requirements.md).

-   További információk: [feltételes hozzáférés](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>13. feladat: eszközök regisztrálása

Az Intune az iOS, Mac OS, Android, Windows asztali és Windows Mobile eszközplatformokat támogatja. A mobileszköz-platformokat szükség szerint regisztrálja, figyelembe véve az Intune üzembe helyezésének használatieset-forgatókönyveit és a követelményeket.

-   További információk: [eszközök regisztrálása](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Az Intune bevezetési folyamatáról további információkat talál a [Microsoft Virtual Academy Intune-ról szóló részében](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676).

## <a name="next-section"></a>Következő szakasz

A következő szakaszban útmutatót talál az [Intune üzembe helyezésének teszteléséről és ellenőrzéséről](section-9-test-and-validation.md).

