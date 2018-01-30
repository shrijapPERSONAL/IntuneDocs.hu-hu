---
title: "Ismert problémák a Microsoft Intune-ban az Azure Portalon"
titlesuffix: Azure portal
description: "Tájékozódhat az Intune ismert problémáiról.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 255bd839bda8e8d85794a88fc76899bbd5870bc0
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="known-issues-in-microsoft-intune"></a>A Microsoft Intune ismert problémái


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Ebből a témakörből megismerheti a Microsoft Intune esetleges ismert problémáit.

Ha olyan hibát szeretne jelenteni, amely nem szerepel itt, [nyisson meg egy támogatási kérelmet](get-support.md).

Ha új szolgáltatást szeretne igényelni az Intune-hoz, jelentést küldhet el [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) webhelyünkön.

## <a name="migration"></a>Áttelepítés

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Az Intune régebbi számítógépügyfelének funkciói csak a Silverlight-konzolon érhetők el

A Windows 10 rendszert Windows MDM-regisztráción keresztül tudja felügyelni az Azure-beli Intune-portálon. További információt [Az Azure-beli Intune-konzol és az örökölt Intune-számítógépügyfél](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure) című témakörben találhat.

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Az Intune által migrálás közben létrehozott csoportok hatással lehetnek más Microsoft-termékek működésére

Ha az Intune-portálról az Azure Portalra migrált, megjelenhet egy **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** nevű új csoport. Ez a csoport az Azure Active Directory minden felhasználóját tartalmazza, nem csak az Intune-nal felügyelt felhasználókat. Ez a használat akkor okozhat problémát más Microsoft-termékeknél, ha azt szeretné, hogy valamely meglévő vagy új felhasználók egyetlen csoportnak se legyenek tagjai.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>A migrált szabályzatok állapotpaneljei nem működnek

A klasszikus portálról az Azure Portalra migrált szabályzatok állapotinformációi nem jelennek meg. A klasszikus portálon azonban megnézhetők ezeknek a szabályzatoknak az állapotinformációi. A migrált konfigurációs szabályzatok állapotinformációit akkor jelenítheti meg, ha újra létrehozza őket az Azure Portalon.

## <a name="apps"></a>Alkalmazások

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Az iOS mennyiségi programban vásárolt alkalmazások csak az Intune-bérlő alapértelmezés szerinti nyelvén érhetők el
Az iOS mennyiségi programban vásárolt alkalmazások csak az Intune-fiókéval megegyező országkódnak megfelelő nyelven jelennek meg, és ahhoz rendelhetők. Az Intune csak az Intune-bérlő országkódjával megegyező iTunes területi beállításról származó alkalmazásokat szinkronizálja. Például ha német Intune-fiókkal rendelkezik, és olyan alkalmazást vásárol, amely csak az Egyesült Államok-beli áruházban érhető el, akkor az Intune nem jeleníti meg az alkalmazást.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Ugyanazon iOS mennyiségi vásárlási programból több példány is feltöltődik
Ugyanazon VPP-token feltöltéséhez ne kattintson egynél többször a **Feltöltés** gombra. A többszöri kattintás azt eredményezi, hogy másodpéldányok töltődnek fel a VPP-tokenből, és az alkalmazások többször szinkronizálnak ugyanazzal a tokennel.


<!-- ## Groups -->

## <a name="device-configuration"></a>Eszközök konfigurálása

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Egyes eszközöknél nem menthető a Windows Information Protection-szabályzat

Az Intune-ban nem regisztrált eszközök esetén csak elsődleges tartományt adhat meg a Windows Information Protection-szabályzat beállításainak **Vállalati identitás** mezőjében.
Ha a **Speciális beállítások** > **Peremhálózat** > **Védett tartomány hozzáadása** beállítás használatával további tartományokat ad meg, a szabályzat nem menthető. A megjelenő hibaüzenetet hamarosan pontosítani fogjuk.

### <a name="cisco-anyconnect-vpn-client-support"></a>Cisco AnyConnect VPN-ügyfelek támogatása

A Cisco AnyConnect VPN-ügyfél legújabb kiadása (4.0.07072) jelenleg nem kompatibilis az Intune-nal.
Egy jövőbeli Intune-frissítés tartalmazni fogja a kompatibilitást ezzel a verzióval. Addig is azt javasoljuk, hogy használja tovább a jelenlegi verziót, és ne frissítse a Cisco AnyConnect VPN-ügyfelet.

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


## <a name="data-protection"></a>Adatvédelem

### <a name="ios-app-protection-policies"></a>iOS-es alkalmazásvédelmi szabályzatok

Megadhat olyan [iOS-hez készült alkalmazásvédelmi szabályzatokat](app-protection-policy-settings-ios.md), melyek a mobilakalmazás-kezeléssel (MAM), regisztráció nélkül kezelt eszközök felhasználói számára érhetőek el. Egy átmeneti hiba miatt ezeket a szabályzatok csak olyan iOS-verziókhoz adhatók meg, melyekben egyetlen, és nem pedig több tizedespont szerepel. Ahelyett, hogy az iOS 10.3.1-et adná meg minimális verzióként, az iOS 10.3-at kell beállítania. Ezt a problémát az iOS SDK hamarosan megjelenő frissítése meg fogja oldani.


## <a name="administration-and-accounts"></a>Felügyelet és fiókok

A globális rendszergazdák (más néven a bérlői rendszergazdák) folytathatják a mindennapos adminisztrációs feladataikat különálló Intune- vagy Nagyvállalati mobilitási csomag- (EMS-) licenc nélkül. Ha azonban a szolgáltatást szeretnék használni például a saját eszközük vagy vállalati eszköz regisztrálásához vagy a munkahelyi Intune portál használatához, Intune- vagy EMS-licencre van szükségük.

<!-- ## Additional items -->
