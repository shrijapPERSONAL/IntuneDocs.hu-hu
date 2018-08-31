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
ms.openlocfilehash: ce785ad7898f9e792feeadcd1623bd0989f0d6d0
ms.sourcegitcommit: 40b1d82df99f09a75a17065cdd0e84d8038f460a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2018
ms.locfileid: "40255566"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Eszközök regisztrálása készülékregisztráció-kezelői fiók használatával

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cégek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói fiókkal. Az *eszközregisztráció-kezelői* (DEM-) fiók egy speciális felhasználói fiók, mely akár ezer eszköz regisztrálására képes. Ha felveszi a meglévő felhasználókat egy DEM-fiókba, különleges DEM-képességeket biztosíthat nekik. Minden regisztrált eszköz felhasznál egyetlen licencet. Az ezzel a fiókkal regisztrált eszközöket célszerű nem személyes („BYOD”), hanem megosztott eszközökként használni.  

A felhasználóknak szerepelniük kell az [Azure Portalon](https://portal.azure.com) ahhoz, hogy fel lehessen venni őket eszközregisztráció-kezelőként. Az optimális biztonság érdekében a DEM-felhasználók nem lehetnek egyben Intune-rendszergazdák is.

>[!NOTE]
>A készülékregisztráció-kezelős módszer nem használható a következő egyéb regisztrációs módszerekkel: [Apple Configurator beállítási asszisztenssel](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator közvetlen beléptetéssel](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) vagy [Készülékregisztrációs program (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Eszközregisztráció-kezelői példaforgatókönyv

Egy étterem 50 pénztári táblagépet szeretne biztosítani a felszolgálóknak és rendelési monitorokat a konyhai személyzetnek. Az alkalmazottaknak nem szükséges hozzáférni a céges adatokhoz, vagy felhasználóként bejelentkezni. Az Intune-rendszergazda létrehoz egy eszközregisztráció-kezelői fiókot az étterem vezetője számára.  Ez a fiók nem azonos a vezető elsődleges fiókjával, és csak a megosztott eszközök Intune-ban való regisztrálására lehet használni. A vezető ekkor már regisztrálhatja az 50 táblagépet a DEM-hitelesítőadatok használatával.

Csak az [Azure Portalon](https://portal.azure.com) szereplő felhasználók lehetnek eszközregisztráció-kezelők. Az eszközregisztráció-kezelő felhasználó nem lehet Intune-rendszergazda.

A DEM-felhasználó a következőket teheti:

-   Legfeljebb 1000 eszköz regisztrálása az Intune-ban
-   Bejelentkezés a Céges portálra céges alkalmazások beszerzéséhez
-   Szerepkör-specifikus alkalmazások telepítése a táblagépekre a céges adatok elérésének konfigurálásához

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>A DEM-fiókkal regisztrált eszközökre vonatkozó korlátozások

Az eszközregisztráció-kezelői fiókokkal regisztrált eszközökre a következő korlátozások vonatkoznak:

  - Nincs felhasználónkénti hozzáférés. Mivel az eszközök nem rendelkeznek hozzárendelt felhasználóval, az eszközök nem férhetnek hozzá az e-mailekhez és a céges adatokhoz. A VPN-konfigurációk például továbbra is használhatók, hogy az eszközök alkalmazásai elérhessék az adatokat.
  - A DEM-felhasználó magán az eszközön nem törölheti az eszközregisztráció-kezelésre regisztrált eszközök regisztrációját a Vállalati portálon. Az Intune-rendszergazda törölheti a regisztrációt.
  - A Vállalati portál alkalmazásban vagy a webhelyén csak a helyi eszköz jelenik meg.
  - A felhasználók nem használhatnak az Apple Volume Purchase Program (VPP) keretében vásárolt alkalmazásokat a felhasználói licencekkel, mivel az alkalmazások kezeléséhez felhasználói Apple ID azonosítóra van szükség.
  - (Csak iOS esetén) Ha eszközregisztráció-kezelővel regisztrálja az iOS-eszközöket, akkor nem használhatja az Apple Configuratort, a Készülékregisztrációs programot (DEP) és az Apple School Manager (ASM) programot az eszközök regisztrálására.
  - (Csak Android esetén) Az egy DEM-fiókkal regisztrálható, androidos munkahelyi profilos eszközök száma korlátozott. DEM-fiókonként legfeljebb 10 androidos munkahelyi profillal rendelkező eszközt lehet regisztrálni. Ez a korlátozás a hagyományos Android-eszközök regisztrációjára nem vonatkozik.
  - Az eszközök telepíthetnek VPP-alkalmazásokat, ha rendelkeznek eszközlicenccel.
  - A DEM használatához nem szükséges Intune-eszközlicenc. További információ a [felhasználói és eszközlicencekről](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> A céges alkalmazásokat olyan eszközökön vezetheti be, amelyeket az eszközregisztráció-kezelő kezel. A Céges portál alkalmazást helyezze a **kötelező telepítésként** üzembe az eszközregisztráció-kezelő felhasználói fiókjában.
> A teljesítmény javítása érdekében a DEM-eszközökön a Vállalati portál alkalmazás kizárólag a helyi eszközt jeleníti meg. A többi DEM-eszköz távoli felügyelete kizárólag az Intune felügyeleti konzolból valósítható meg.


## <a name="add-a-device-enrollment-manager"></a>Eszközregisztráció-kezelő hozzáadása

1.  Az [Azure-beli Intune-portálon](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása** > **Eszközregisztráció-kezelők** elemet.

2.  Válassza a **Hozzáadás** elemet.

3.  Adja meg a készülékregisztráció-kezelő felhasználó egyszerű felhasználónevét a **Felhasználó hozzáadása** panelen, majd válassza a **Hozzáadás** elemet. A készülékregisztráció-kezelő felhasználó bekerül a készülékregisztráció-kezelő felhasználók listájába.

## <a name="permissions-for-dem"></a>DEM-engedélyek

Globális vagy Intune-szolgáltatási rendszergazdai Azure AD-szerepkörök szükségesek
- a DEM-regisztrációs feladatok végrehajtásához az adminisztrátori portálon;
- az összes DEM-felhasználó megtekintéséhez, függetlenül az egyéni felhasználói szerepkör alatt felsorolt és elérhető RBAC-jogosultságoktól.

Azok a hozzárendelt globális rendszergazdai vagy Intune-szolgáltatásrendszergazdai szerepkörrel nem rendelkező felhasználók, akiknek van olvasási jogosultságuk a készülékregisztráció-kezelői szerepkörhöz, csak az általuk létrehozott DEM-felhasználókat láthatják. Az RBAC-szerepkörök támogatása ezekhez a funkciókhoz később lesz bejelentve.


## <a name="remove-a-device-enrollment-manager"></a>Készülékregisztráció-kezelő eltávolítása

A készülékregisztráció-kezelő eltávolításakor:

-   A regisztrált eszközöket ez nem érinti, és továbbra is teljes felügyelet alatt állnak.
-   Az eltávolított DEM-fiók hitelesítő adatai továbbra is érvényesek maradnak.
-   Az eltávolított DEM továbbra sem törölheti eszközök tartalmát, és nem vonhatja ki őket a használatból.
-   Az eltávolított DEM csak annyi eszközt regisztrálhat, amennyit az Intune-rendszergazda felhasználónként engedélyezett.

**Készülékregisztráció-kezelő eltávolítása**

1. Az [Azure Portalbeli Intune-on](https://aka.ms/intuneportal) válassza az **Eszközök regisztrálása**, majd a **Készülékregisztráció-kezelők** lehetőséget.
2. A **Készülékregisztráció-kezelő** panelen válassza ki a készülékregisztráció-kezelő felhasználót, majd válassza az **Eltávolítás** lehetőséget.

