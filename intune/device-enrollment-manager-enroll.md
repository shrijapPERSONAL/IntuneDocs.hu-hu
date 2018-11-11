---
title: Eszközök regisztrálása készülékregisztráció-kezelői fiók használatával
titlesuffix: Microsoft Intune
description: Az eszközök Intune-ban való regisztrálásához használja a készülékregisztráció-kezelői fiókot. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d510596f021725292c7221e3056986c2c3fc93c
ms.sourcegitcommit: 9d08545727543b434dd270371fa50233470f2bce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50410786"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Eszközök regisztrálása készülékregisztráció-kezelői fiók használatával

Készülékregisztráció-kezelői (DEM) fiók használatával akár 1000 mobileszközt is regisztrálhat egyetlen Azure Active Directory-fiókkal. A DEM egy Intune-engedély, amelyet AAD felhasználói fiókokra lehet alkalmazni, és lehetővé teszi, hogy a felhasználó akár 1000 eszközt is regisztráljon. A DEM-fiók olyan forgatókönyvek esetén hasznos, ahol az eszközöket regisztrálják és előkészítik, mielőtt kiadnák azokat a felhasználóknak.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>A DEM-fiókkal regisztrált eszközökre vonatkozó korlátozások

A DEM-fiókokra és a DEM-fiókokkal regisztrált eszközökre a következő korlátozások vonatkoznak:

  - Nem végezhető el az összes adat törlése a Céges portálról. A DEM felhasználói fiókkal regisztrált eszközök összes adatának törlése a Azure Portalon az Intune-ból végezhető el.
  - A Vállalati portál alkalmazásban vagy a webhelyén csak a helyi eszköz jelenik meg.
  - A DEM felhasználói fiókok nem használhatnak az Apple Volume Purchase Program (VPP) keretében vásárolt alkalmazásokat az Apple VPP felhasználói licencekkel, mivel az alkalmazások kezeléséhez felhasználói Apple ID azonosítóra van szükség.
  - Az eszközök akkor telepíthetnek VPP-alkalmazásokat, ha rendelkeznek Apple VPP-eszközlicenccel.
  


## <a name="add-a-device-enrollment-manager"></a>Eszközregisztráció-kezelő hozzáadása

1.  Az [Azure-beli Intune-portálon](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Eszközregisztráció-kezelők** elemet.

2.  Válassza a **Hozzáadás** elemet.

3.  Adja meg a készülékregisztráció-kezelő felhasználó egyszerű felhasználónevét a **Felhasználó hozzáadása** panelen, majd válassza a **Hozzáadás** elemet. A készülékregisztráció-kezelő felhasználó bekerül a készülékregisztráció-kezelő felhasználók listájába.

## <a name="permissions-for-dem"></a>DEM-engedélyek

Globális vagy Intune-szolgáltatási rendszergazdai Azure AD-szerepkörök szükségesek az alábbiakhoz:
- DEM-engedély hozzárendelése Azure AD felhasználói fiókhoz,
- az összes DEM-felhasználó megtekintéséhez.

Ha egy felhasználó nem rendelkezik hozzárendelt globális rendszergazdai vagy Intune-szolgáltatásrendszergazdai szerepkörrel, de van olvasási jogosultsága a hozzá rendelt készülékregisztráció-kezelői szerepkörhöz, akkor csak az általa létrehozott DEM-felhasználókat láthatja.


## <a name="remove-device-enrollment-manager-permissions"></a>Készülékregisztráció-kezelői engedélyek eltávolítása

A készülékregisztráció-kezelő eltávolítása nincs hatással a regisztrált eszközökre.

**Készülékregisztráció-kezelő eltávolítása**

1. Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása**, majd a **Készülékregisztráció-kezelők** lehetőséget.
2. A **Készülékregisztráció-kezelő** panelen válassza ki a készülékregisztráció-kezelő felhasználót, majd válassza az **Eltávolítás** lehetőséget.

