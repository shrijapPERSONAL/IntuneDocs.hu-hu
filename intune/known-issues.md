---
title: "Az Azure-beli Microsoft Intune ismert problémái"
titleSuffix: Intune on Azure
description: "Tájékozódhat az Intune ismert problémáiról.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fda224613d8b69be82ef7f9681ba9165be33e52
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="known-issues-in-microsoft-intune"></a>A Microsoft Intune ismert problémái


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Ebből a témakörből megismerheti a Microsoft Intune esetleges ismert problémáit.

Ha olyan hibát szeretne jelenteni, amely nem szerepel itt, [nyisson meg egy támogatási kérelmet](get-support.md).

Ha új szolgáltatást szeretne igényelni az Intune-hoz, jelentést küldhet el [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) webhelyünkön.

## <a name="migration"></a>Áttelepítés

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Az Intune által migrálás közben létrehozott csoportok hatással lehetnek más Microsoft-termékek működésére

Ha a klasszikus Intune-portálról az Azure Portalra migrált, megjelenhet egy **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** nevű új csoport. Ez a csoport az Azure Active Directory minden felhasználóját tartalmazza, nem csak az Intune-nal felügyelt felhasználókat. Ez a használat akkor okozhat problémát más Microsoft-termékeknél, ha azt szeretné, hogy valamely meglévő vagy új felhasználók egyetlen csoportnak se legyenek tagjai.

### <a name="secondary-migration-required-for-select-capabilities"></a>Egyes képességekhez szükséges másodlagos migrálás

A 2017 januárja előtt létrehozott Intune-fiókokat migrálni kell, hogy az alábbi lehetőségek használhatók legyenek az Azure Portalon:

- Vállalati eszközregisztrációs profilok
- Apple Készülékregisztrációs program
- Előre regisztrált vállalati eszközök iOS-es sorozatszám-csoportok alapján
- Eszközregisztráció-kezelők
- Apple Volume Purchase Program

Mivel ezek a lehetőségek nem kezelhetők egyszerre a klasszikus Silverlight- és az Azure-konzolon is, a migrálás az alábbi hatást váltja ki:
- letiltja őket a klasszikus konzolon
- engedélyezi őket az Azure-konzolon.  

Ha a továbbiakban ezeket az Intune-lehetőségeket az Azure Portalon kezeli, vegye figyelembe az alábbi pontokat:

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Eltávolítja a céges eszközregisztrációs profilokat az Apple DEP-ben
Az Azure Portal nem támogat alapértelmezés szerinti céges eszközregisztrációs profilt az Apple Készülékregisztrációs program (DEP) eszközeihez. A klasszikus Silverlight Intune-konzol ezen funkcióját a profilok szándékolatlan hozzárendelésének megelőzése érdekében megszüntetjük. Az Azure Portalon az Apple DEP-fiókokból szinkronizált sorozatszámokhoz a rendszer nem rendel céges eszközregisztrációs profilt. Az eszköz használata előtt regisztrációs profilt kell hozzárendelni.

#### <a name="apple-dep-token-restored-with-migration"></a>Az Apple DEP-token migráláskor visszaáll

Ha a klasszikus Intune-portálon (Silverlight) törli az Apple Device Enrollment Program tokenjét, és nem tölt fel új tokent az Azure Portalra, akkor migráláskor az eredeti token áll vissza az Azure Portalon. A token eltávolításához és a DEP-regisztráció megakadályozásához törölje a tokent az Azure Portalról.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>A migrált szabályzatok állapotpaneljei nem működnek

A klasszikus portálról az Azure Portalra migrált szabályzatok állapotinformációi nem jelennek meg. A klasszikus portálon azonban megnézhetők ezeknek a szabályzatoknak az állapotinformációi.
A migrált konfigurációs szabályzatok állapotinformációit akkor jelenítheti meg, ha újra létrehozza őket az Azure Portalon.

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
 
A Cisco AnyConnect VPN-ügyfél legújabb kiadása (4.0.07072) jelenleg nem kompatibilis az Intune-nal. Egy jövőbeli Intune-frissítés tartalmazni fogja a kompatibilitást ezzel a verzióval. Addig is azt javasoljuk, hogy használja tovább a jelenlegi verziót, és ne frissítse a Cisco AnyConnect VPN-ügyfelet.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Numerikus jelszó használata macOS Sierra rendszerű eszközökkel

Jelenleg ha a **Numerikust** választja ki a **Kötelező jelszó típusa** értékeként a macOS Sierra-eszközök eszközkorlátozási profiljában, akkor az **Alfanumerikusként** lesz megkövetelve. Ha ezeknél az eszközöknél numerikus jelszót szeretne használni, ne konfigurálja ezt a beállítást.
Ezt a problémát várhatóan az macOS jövőbeli kiadása javítja.

További tudnivalók a fenti beállításokhoz: [A macOS eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban](device-restrictions-macos.md).

## <a name="compliance"></a>Megfelelőség

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Az Intune-beli megfelelőségi szabályzatok nem jelennek meg az új konzolon

A klasszikus Intune-portálon létrehozott megfelelőségi szabályzatok migrálva lesznek, de az Azure Portal szerkezeti módosításai miatt nem jelennek meg az Azure Portalon. A klasszikus Intune-portálon létrehozott megfelelőségi szabályzatok továbbra is érvényben vannak, de megnézni és szerkeszteni csak a klasszikus Intune-portálon lehet őket.
Ügyeljen továbbá arra is, hogy az Azure Portalon létrehozott új szabályzatok a klasszikus Intune-portálon már nem jelennek meg.

További információt a [Mi az eszközmegfelelőség](device-compliance.md) című témakörben talál.

<!-- ## Enrollment -->


<!-- ## Data protection -->


## <a name="administration-and-accounts"></a>Felügyelet és fiókok

A globális rendszergazdák (más néven a bérlői rendszergazdák) folytathatják a mindennapos adminisztrációs feladataikat különálló Intune- vagy Nagyvállalati mobilitási csomag- (EMS-) licenc nélkül. Ha azonban a szolgáltatást szeretnék használni például a saját eszközük vagy vállalati eszköz regisztrálásához vagy a munkahelyi Intune portál használatához, Intune- vagy EMS-licencre van szükségük.

<!-- ## Additional items -->












 