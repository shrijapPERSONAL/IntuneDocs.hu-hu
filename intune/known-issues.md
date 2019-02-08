---
title: Ismert problémák a Microsoft Intune-ban – Azure | Microsoft Docs
description: A Microsoft Intune ismert problémái.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 985c3b2cf3de712e5441f72c3a9f52da6e482fcd
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842422"
---
# <a name="known-issues-in-microsoft-intune"></a>A Microsoft Intune ismert problémái


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ebből a cikkből megismerheti a Microsoft Intune esetleges ismert problémáit.

Ha azt szeretné, hogy jelentése, amely nem szerepel a listán, [nyisson egy támogatási kérést](get-support.md).

Ha szeretné az Intune új funkciót javasolna, fontolja meg a bejelentés egy [a Microsoft Intune-Feedback](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) jelentést.

## <a name="migration"></a>Áttelepítés

### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal"></a>Megfelelőségi szabályzatok exportálása a klasszikus Azure-portálról, és azok újbóli létrehozása az Azure-beli Intune-portálon

A klasszikus Azure-portálon létrehozott megfelelőségi szabályzatok hamarosan elavulnak. Áttekintheti és törölheti a meglévő megfelelőségi szabályzatokat, de már nem frissítheti őket. Ha megfelelőségi szabályzatokat kell az Azure-beli Intune-portálra migrálnia, akkor veszővel tagolt (.csv) fájlként exportálhatja azokat. Ezt követően a fájlban lévő adatok felhasználásával újra létrehozhatja a szabályzatokat az Azure-beli Intune-portálon.

> [!IMPORTANT]
> A klasszikus Azure-portál kivonása után többé nem fér majd hozzá megfelelőségi szabályzataihoz, és meg sem tekintheti azokat. Ezért ne feledje exportálni és az Azure Portalon újra létrehozni szabályzatait még a klasszikus Azure-portál elavulása előtt.

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Az Intune régebbi számítógépügyfelének funkciói csak a Silverlight-konzolon érhetők el

A Windows 10 rendszert Windows MDM-regisztráción keresztül tudja felügyelni az Azure-beli Intune-portálon. További információt [Az Azure-beli Intune-konzol és az örökölt Intune-számítógépügyfél](intune-legacy-pc-client.md) című témakörben találhat.

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Az Intune által migrálás közben létrehozott csoportok hatással lehetnek más Microsoft-termékek működésére

Ha az Intune-portálról az Azure Portalra migrált, megjelenhet egy **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** nevű új csoport. Ez a csoport az Azure Active Directory minden felhasználóját tartalmazza, nem csak az Intune-nal felügyelt felhasználókat. Ez a használat akkor okozhat problémát más Microsoft-termékeknél, ha azt szeretné, hogy valamely meglévő vagy új felhasználók egyetlen csoportnak se legyenek tagjai.

### <a name="status-blades-for-migrated-policies-dont-work"></a>A migrált szabályzatok állapotpaneljei nem működnek.

A klasszikus Azure Portalról az Azure Portalra migrált szabályzatok állapotinformációi nem jelennek meg. A klasszikus portálon azonban megnézhetők ezeknek a szabályzatoknak az állapotinformációi. A migrált konfigurációs szabályzatok állapotinformációit akkor jelenítheti meg, ha újra létrehozza őket az Azure Portalon.

## <a name="apps"></a>Alkalmazások


### <a name="multiple-app-install-prompts-for-certain-vpp-apps"></a>Több alkalmazástelepítési kérelem egyes VPP-alkalmazások esetében
Több alkalmazás telepítése kéri bizonyos VPP-alkalmazásokat, amelyre már telepítve vannak a végfelhasználói eszközökön jelenhet meg. A problémát az okozza, hogy az **Automatikus alkalmazásfrissítések** beállítás **Be** van kapcsolva a VPP-tokenben, amelyet az Intune Azure Portalra feltöltött.    

A probléma elkerüléséhez letilthatja a **automatikus alkalmazásfrissítések** VPP-token lehetőséget. Ehhez nyissa meg a Microsoft Intune-t az Azure Portalon. Az Intune-ban válassza az **Ügyfélalkalmazások** > **iOS VPP-tokenek** lehetőséget. Ezután válassza ki azt a VPP-tokent, amely az érintett alkalmazást telepítette, majd válassza ki a **Szerkesztés** > **Automatikus alkalmazásfrissítések** > **Ki** > **Mentés** lehetőségeket. A másik lehetőség, hogy letiltja az érintett alkalmazás VPP-alkalmazásként történő telepítését, így a továbbiakban nem jelennek meg a telepítési kérelmek sem.    

Ez az egy ismert probléma a jelenlegi kiadásban. Megoldja a problémát egy közelgő javítást kell, hogy. Ha a javítás telepítve lesz, a felhasználók nem fogják többé ezeket az alkalmazástelepítési kérelmeket megkapni.

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Az iOS mennyiségi programban vásárolt alkalmazások csak az Intune-bérlő alapértelmezés szerinti nyelvén érhetők el
Az iOS mennyiségi programban vásárolt alkalmazások csak az Intune-fiókéval megegyező országkódnak megfelelő nyelven jelennek meg, és ahhoz rendelhetők. Az Intune csak az Intune-bérlő országkódjával megegyező iTunes területi beállításról származó alkalmazásokat szinkronizálja. Például ha német Intune-fiókkal rendelkezik, és olyan alkalmazást vásárol, amely csak az Egyesült Államok-beli áruházban érhető el, akkor az Intune nem jeleníti meg az alkalmazást.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Ugyanazon iOS mennyiségi vásárlási programból több példány is feltöltődik
Ugyanazon VPP-token feltöltéséhez ne kattintson egynél többször a **Feltöltés** gombra. A többszöri kattintás azt eredményezi, hogy másodpéldányok töltődnek fel a VPP-tokenből, és az alkalmazások többször szinkronizálnak ugyanazzal a tokennel.

### <a name="some-managed-browser-traffic-not-routed-through-azure-app-proxy----2463492---"></a>Bizonyos Managed Browser-forgalmak nem lettek továbbítva az Azure App Proxyn <!-- 2463492 -->
A Managed Browser és az App Proxy integrációjában egy ismert hiba megakadályozza bizonyos harmadlagos forgalmak (például a javascript vagy az AJAX-hívások) továbbítását az Azure App Proxyn. Ez az egy ismert probléma a jelenlegi kiadásban.  

<!-- ## Groups -->

## <a name="device-configuration"></a>Eszközök konfigurálása

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Egyes eszközöknél nem menthető a Windows Information Protection-szabályzat

Az Intune-ban nem regisztrált eszközök esetén csak elsődleges tartományt adhat meg a Windows Information Protection-szabályzat beállításainak **Vállalati identitás** mezőjében.
Ha a **Speciális beállítások** > **Peremhálózat** > **Védett tartomány hozzáadása** beállítás használatával további tartományokat ad meg, a szabályzat nem menthető. A megjelenő hibaüzenetet hamarosan pontosítani fogjuk.

### <a name="cisco-anyconnect-and-cisco-legacy-anyconnect-vpn-client-support---ios"></a>Cisco AnyConnect és Cisco Legacy AnyConnect VPN ügyfelek támogatása – iOS

IOS-eszközökön a hálózati hozzáférés-vezérlés (NAC) integrációja az új Cisco AnyConnect-ügyféllel nem működik. Jelenleg is dolgozunk a Cisco közreműködésével a NAC-integráció elérhetővé tételén.

A [VPN-profilok létrehozása az Intune-ban](vpn-settings-ios.md) című cikk bővebb tájékoztatást nyújt a Cisco AnyConnect és Cisco Legacy AnyConnect ügyfelekről.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Numerikus jelszó használata macOS Sierra rendszerű eszközökkel

Jelenleg ha a **Numerikust** választja ki a **Kötelező jelszó típusa** értékeként a macOS Sierra-eszközök eszközkorlátozási profiljában, akkor az **Alfanumerikusként** lesz megkövetelve. Ha ezeknél az eszközöknél numerikus jelszót szeretne használni, ne konfigurálja ezt a beállítást.
Ezt a problémát várhatóan az macOS jövőbeli kiadása javítja.

További tudnivalók a fenti beállításokhoz: [A macOS eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban](device-restrictions-macos.md).

## <a name="compliance"></a>Megfelelőség

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Az Intune-beli megfelelőségi szabályzatok nem jelennek meg az új konzolon

A klasszikus Intune-portálon létrehozott megfelelőségi szabályzatok migrálva lesznek, de az Azure Portal szerkezeti módosításai miatt nem jelennek meg az Azure Portalon. A klasszikus Intune-portálon létrehozott megfelelőségi szabályzatok továbbra is érvényben vannak, de megnézni és szerkeszteni csak a klasszikus portálon lehet őket.

Ügyeljen továbbá arra is, hogy az Azure Portalon létrehozott új szabályzatok a klasszikus portálon már nem jelennek meg.

További információt a [Mi az eszközmegfelelőség](device-compliance.md) című témakörben talál.

<!-- ## Enrollment -->

## <a name="conditional-access"></a>Feltételes hozzáférés

### <a name="conditional-access-settings-from-intune-do-not-show-up-in-new-console"></a>Az Intune-beli feltételes hozzáférési beállítások nem jelennek meg az új konzolon

A bérlő az Azure Portalra történő áttelepítését követően továbbra is érvényesek maradnak a feltételes hozzáféréssel kapcsolatos beállításai, azonban nem fognak megjelenni az Azure Intune protálon. 

Ha szeretné megtekinteni és kezelni ezeket a beállításokat az Azure Portalon, akkor el kell távolítania a régi beállításokat a klasszikus portálról, és újra létre kell hoznia őket az Azure Portalon. 

További információért tekintse meg a [Feltételes hozzáféréssel kapcsolatos ajánlott eljárások az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices) című részt.

## <a name="data-protection"></a>Adatvédelem

### <a name="ios-app-protection-policies"></a>iOS-es alkalmazásvédelmi szabályzatok

Megadhat olyan [iOS-hez készült alkalmazásvédelmi szabályzatokat](app-protection-policy-settings-ios.md), melyek a mobilakalmazás-kezeléssel (MAM), regisztráció nélkül kezelt eszközök felhasználói számára érhetőek el. Egy átmeneti hiba miatt ezeket a szabályzatok csak olyan iOS-verziókhoz adhatók meg, melyekben egyetlen, és nem pedig több tizedespont szerepel. Ahelyett, hogy az iOS 10.3.1-et adná meg minimális verzióként, az iOS 10.3-at kell beállítania. Ezt a problémát az iOS SDK hamarosan megjelenő frissítése meg fogja oldani.


## <a name="administration-and-accounts"></a>Felügyelet és fiókok

A globális rendszergazdák (más néven a bérlői rendszergazdák) folytathatják a mindennapos adminisztrációs feladataikat különálló Intune- vagy Nagyvállalati mobilitási csomag- (EMS-) licenc nélkül. Ha azonban a szolgáltatást szeretnék használni például a saját eszközük vagy vállalati eszköz regisztrálásához vagy a munkahelyi Intune portál használatához, Intune- vagy EMS-licencre van szükségük.

<!-- ## Additional items -->
