---
title: "Ismert problémák a Microsoft Intune-ban az Azure Portalon"
titlesuffix: Azure portal
description: "Tájékozódhat az Intune ismert problémáiról.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 059242b76ef1f14a5237c34e57ed626fc53f17be
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2017
---
# <a name="known-issues-in-microsoft-intune"></a>A Microsoft Intune ismert problémái


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Ebből a témakörből megismerheti a Microsoft Intune esetleges ismert problémáit.

Ha olyan hibát szeretne jelenteni, amely nem szerepel itt, [nyisson meg egy támogatási kérelmet](get-support.md).

Ha új szolgáltatást szeretne igényelni az Intune-hoz, jelentést küldhet el [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) webhelyünkön.

## <a name="migration"></a>Áttelepítés

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Az Intune által migrálás közben létrehozott csoportok hatással lehetnek más Microsoft-termékek működésére

Ha az Intune-portálról az Azure Portalra migrált, megjelenhet egy **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** nevű új csoport. Ez a csoport az Azure Active Directory minden felhasználóját tartalmazza, nem csak az Intune-nal felügyelt felhasználókat. Ez a használat akkor okozhat problémát más Microsoft-termékeknél, ha azt szeretné, hogy valamely meglévő vagy új felhasználók egyetlen csoportnak se legyenek tagjai.

### <a name="secondary-migration-required-for-select-capabilities"></a>Egyes képességekhez szükséges másodlagos migrálás

A 2017 januárja előtt létrehozott Intune-fiókokat migrálni kell, hogy az alábbi lehetőségek használhatók legyenek az Azure Portalon:

- Vállalati eszközregisztrációs profilok
- Apple Készülékregisztrációs program
- Céges eszközök előzetes bejelentése iOS-es sorozatszám alapján
- Készülékregisztráció-kezelői fiókok
- Apple Volume Purchase Program

Mivel ezek a lehetőségek nem kezelhetők egyszerre az Intune- (Silverlight-) konzolon és az Azure Portalon is, a migrálás az alábbi hatással lesz rájuk:
- letiltja őket a klasszikus portálon
- engedélyezi őket az Azure Portalon  

2017. szeptember 22-től ezeknek a funkcióknak a migrálása az Azure-ba történő elsődleges migrálás részeként történik. Ha a fiókját már migrálták az Azure Portalra, erre a másodlagos migrálásra már korábban sor kerülhetett. Ha nem ez a helyzet, akkor ezeknek a lehetőségeknek az Azure-ba való migrálása novemberig megtörténik. A fiókmigrálás még azon a napon befejeződik, amelyen elkezdődött. A migrálás a funkciók klasszikus Intune-portálon való letiltásától számítva akár hat óráig is eltarthat.

Ha a továbbiakban ezeket az Intune-lehetőségeket az Azure Portalon kezeli, vegye figyelembe az alábbi pontokat:

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Eltávolítja a céges eszközregisztrációs profilokat az Apple DEP-ben
Az Azure Portal nem támogat alapértelmezett céges eszközregisztrációs profilt az Apple Készülékregisztrációs program (DEP) eszközeihez. Ezt az Intune- (Silverlight-) konzolon elérhető funkciót a profilok szándékolatlan hozzárendelésének megelőzése érdekében megszüntetjük. Az Azure Portalon az Apple DEP-fiókokból szinkronizált sorozatszámokhoz a rendszer nem rendel alapértelmezett céges eszközregisztrációs profilt. Az eszköz használata előtt regisztrációs profilt kell hozzárendelni.

#### <a name="apple-dep-token-restored-with-migration"></a>Az Apple DEP-token migráláskor visszaáll

Ha az Intune- (Silverlight-) portálon törli az Apple Készülékregisztrációs program tokenjét, és nem tölt fel új tokent az Azure Portalra, akkor migráláskor az eredeti token áll vissza az Azure Portalon. A token eltávolításához és a DEP-regisztráció megakadályozásához törölje a tokent az Azure Portalról.

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
