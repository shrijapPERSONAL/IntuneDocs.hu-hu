---
title: "A Microsoft Intune előzetesének ismert problémái"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: További információ az előzetes ismert problémáiról"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>A Microsoft Intune előzetesének ismert problémái


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Ezen témakörből részletesebben megismerheti az Intune előzetesének esetleges ismert problémát.

Ha olyan hibát szeretne jelenteni, amely nem szerepel itt, [nyisson meg egy támogatási kérelmet](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Ha új szolgáltatás hozzáadását szeretné igényelni az Intune-hoz, vegye fontolóra egy jelentés benyújtását saját [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) webhelyünkön.

## <a name="administration-and-accounts"></a>Felügyelet és fiókok

- A globális rendszergazdák (másnéven a bérlő rendszergazdák) folytathatják a mindennapos adminisztrációs feladataikat különálló Intune- vagy Nagyvállalati mobilitási csomag- (EMS-) licenc nélkül. Ha azonban a globális rendszergazdák a szolgáltatást szeretnék használni, például a saját eszközük vagy vállalati eszköz regisztrálásához vagy a munkahelyi Intune portál használatához, Intune- vagy EMS-licencre van szükségük, mint minden más felhasználónak.

## <a name="apple-enrollment-profile-migration"></a>Az Apple-belépetési profil áttelepítése
- A következő néhány hónap során az Intune lehetővé teszi, hogy az új Azure Portalon felügyelje az Apple Device Enrollment Programmal és az Apple Configurator eszközzel végzett regisztrálást. Ha törli az Apple Device Enrollment Program tokenjét, és nem tölt fel frissített tokent, akkor az Intune-fiók áttelepítésének részeként az eredeti token vissza lesz állítva az új Azure Portalon. Ha el szeretné távolítani a tokent, és szeretné megakadályozni a DEP-regisztrációt, törölje a tokent az Azure Portalon. 

