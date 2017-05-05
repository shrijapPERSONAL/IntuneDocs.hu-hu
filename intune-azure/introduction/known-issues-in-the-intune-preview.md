---
title: "A Microsoft Intune előzetesének ismert problémái"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: További információ az előzetes ismert problémáiról"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 08e2f65bcd600489f6599d37e5ef56c205176cd7
ms.lasthandoff: 04/25/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>A Microsoft Intune előzetesének ismert problémái


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Ezen témakörből részletesebben megismerheti az Intune előzetesének esetleges ismert problémát.

Ha olyan hibát szeretne jelenteni, amely nem szerepel itt, [nyisson meg egy támogatási kérelmet](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Ha új szolgáltatás hozzáadását szeretné igényelni az Intune-hoz, vegye fontolóra egy jelentés benyújtását saját [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) webhelyünkön.

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Az Intune által migrálás közben létrehozott csoportok hatással lehetnek más Microsoft-termékek működésére

Ha a klasszikus Intune-portálról az Azure Portalra migrált, megjelenhet egy **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** nevű új csoport. Vegye figyelembe, hogy ez a csoport az Azure Active Directory minden felhasználóját tartalmazza, nem csak az Intune-nal felügyelt felhasználókat. Ez akkor okozhat problémát más Microsoft-termékeknél, ha azt szeretné, hogy valamely meglévő vagy új felhasználók egyetlen csoportnak se legyenek tagjai.

### <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>Az Intune által migráláskor létrehozott csoportok lelassítják a migrálást

A migrálásra való felkészüléskor a csoportok az Intune-ból az Azure AD-be lesznek másolva. A klasszikus Intune-portálon elvégzett minden változtatás az Azure AD-csoportban is megjelenik. Az Azure AD-ben végrehajtott változtatások azonban nem lesznek szinkronizálva a klasszikus Intune-konzolra. Ez azt eredményezheti, hogy az Azure Portalra való migrálás sikertelen lesz, és késések jelentkezhetnek a migrálásban.

### <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Az Intune-beli megfelelőségi szabályzatok nem jelennek meg az új konzolon 

A klasszikus Intune-portálon létrehozott összes megfelelőségi szabályzat migrálva lesz, de nem jelennek meg az Azure Portalon. Ez az Azure Portal felületének tervezési változásai miatt van így. A klasszikus Intune-portálon létrehozott megfelelőségi szabályzatok továbbra is érvényben vannak, de megnézni és szerkeszteni csak a klasszikus portálon lehet őket.
Ügyeljen továbbá arra is, hogy az Azure Portalon létrehozott új szabályzatok a klasszikus portálon már nem jelennek meg.
További információt a [Mi az eszközmegfelelőség](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance) című témakörben talál.




### <a name="administration-and-accounts"></a>Felügyelet és fiókok

A globális rendszergazdák (másnéven a bérlő rendszergazdák) folytathatják a mindennapos adminisztrációs feladataikat különálló Intune- vagy Nagyvállalati mobilitási csomag- (EMS-) licenc nélkül. Ha azonban a globális rendszergazdák a szolgáltatást szeretnék használni, például a saját eszközük vagy vállalati eszköz regisztrálásához vagy a munkahelyi Intune portál használatához, Intune- vagy EMS-licencre van szükségük, mint minden más felhasználónak.

### <a name="apple-enrollment-profile-migration"></a>Az Apple-belépetési profil áttelepítése
A következő néhány hónap során az Intune lehetővé teszi, hogy az új Azure Portalon felügyelje az Apple Device Enrollment Programmal és az Apple Configurator eszközzel végzett regisztrálást. Ha törli az Apple Device Enrollment Program tokenjét, és nem tölt fel frissített tokent, akkor az Intune-fiók áttelepítésének részeként az eredeti token vissza lesz állítva az új Azure Portalon. Ha el szeretné távolítani a tokent, és szeretné megakadályozni a DEP-regisztrációt, törölje a tokent az Azure Portalon. 

