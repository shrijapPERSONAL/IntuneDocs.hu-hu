---
title: "Eszközök regisztrálása – készülékregisztráció-kezelő"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk ismerteti, hogyan lehet regisztrálni az eszközöket az Intune-ban a készülékregisztráció-kezelővel. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: aded0826c2628e4dc72859387fbe4a76d683db9e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Eszközök regisztrálása a készülékregisztráció-kezelővel

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A szervezetek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói fiókkal. Az *eszközregisztráció-kezelői* (DEM-) fiók egy speciális felhasználói fiók, mely akár ezer eszköz regisztrálására képes. A meglévő felhasználók a DEM-fiókba való felvételével különleges DEM-képességeket biztosíthat számukra. Minden regisztrált eszköz felhasznál egyetlen licencet. Az ezzel a fiókkal regisztrált eszközöket célszerű nem személyes („BYOD”), hanem megosztott eszközökként használni.  

A felhasználóknak szerepelniük kell az Azure Portal webhelyen ahhoz, hogy fel lehessen venni őket eszközregisztráció-kezelőként. Az optimális biztonság biztosítása érdekében a DEM-felhasználó nem lehet egyben Intune-rendszergazda is.

>[!NOTE]
>A készülékregisztráció-kezelős módszer nem használható a következő egyéb regisztrációs módszerekkel: [Apple Configurator beállítási asszisztenssel](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator közvetlen beléptetéssel](apple-configurator-direct-enroll-ios.md), illetve [készülékregisztrációs program](device-enrollment-program-enroll-ios.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Eszközregisztráció-kezelői példaforgatókönyv

Egy étterem 50 pénztári táblagépet szeretne biztosítani a felszolgálóknak és rendelési monitorokat a konyhai személyzetnek. Az alkalmazottaknak nem szükséges hozzáférni a céges adatokhoz, vagy felhasználóként bejelentkezni. Az Intune-rendszergazda létrehoz egy eszközregisztráció-kezelői fiókot, és felveszi az étterem egyik vezetőjét a DEM-fiókba, ezzel gyakorlatilag DEM-képességeket biztosítva az adott vezető számára. A vezető ekkor már regisztrálhatja az 50 táblagépet a DEM-hitelesítőadatok használatával.

Csak az Intune-konzolon szereplő felhasználók lehetnek eszközregisztráció-kezelők. Az eszközregisztráció-kezelő felhasználó nem lehet Intune-rendszergazda.

A DEM-felhasználó a következőket teheti:

-   Legfeljebb 1000 eszköz regisztrálása az Intune-ban.
-   Bejelentkezés a Vállalati portálra vállalati alkalmazások beszerzéséhez.
-   A vállalati adatok elérésének konfigurálása szerepkör-specifikus alkalmazások a táblagépekre való telepítésével.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>A DEM-fiókkal regisztrált eszközökre vonatkozó korlátozások

Az eszközregisztráció-kezelői fiókokkal regisztrált eszközökre a következő korlátozások vonatkoznak:

  - Az eszköznek nincs konkrét „felhasználója”. Így nincs e-mail-fiókhoz vagy a céges adatokhoz való hozzáférés. Az adatok például VPN-nel azonban továbbra is hozzáférhetővé tehetők az eszközökön.

  - Nincs feltételes hozzáférés, mivel az a felhasználókon alapul.

  - A DEM-felhasználó magán az eszközön nem törölheti az eszközregisztráció-kezelésre regisztrált eszközök regisztrációját a Vállalati portálon. Az Intune-rendszergazda rendelkezik ezzel a képességgel, a DEM-felhasználó viszont nem.

  - A Vállalati portál alkalmazásban vagy a webhelyén csak a helyi eszköz jelenik meg.
 
  - A felhasználók nem futtathatnak az Apple Volume Purchase Program (VPP) keretében vásárolt alkalmazásokat az eszközökön, mivel az alkalmazások kezeléséhez felhasználói Apple ID azonosítóra van szükség.
 
  - (Csak iOS esetén) Ha eszközregisztráció-kezelővel regisztrálja az iOS-eszközöket, nem használhatja az Apple Configuratort vagy az Apple Device Enrollment Programot (DEP) az eszközök regisztrálásához.


> [!NOTE]
> A vállalati alkalmazások eszközregisztráció-kezelővel felügyelt eszközökre történő telepítéséhez telepítse a Vállalati portál alkalmazást **Szükséges telepítésként** az eszközregisztráció-kezelő felhasználói fiókjára.
> A teljesítmény javítása érdekében a DEM-eszközökön a Vállalati portál alkalmazás kizárólag a helyi eszközt jeleníti meg. A többi DEM-eszköz távoli felügyelete kizárólag az Intune felügyeleti konzolból valósítható meg.


## <a name="add-a-device-enrollment-manager"></a>Eszközregisztráció-kezelő hozzáadása

1.  Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2.  Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Készülékregisztráció-kezelők** elemet.

3.  Válassza a **Hozzáadás** elemet.

4.  Adja meg a készülékregisztráció-kezelő felhasználó egyszerű felhasználónevét a **Felhasználó hozzáadása** panelen, majd válassza a **Hozzáadás** elemet. A készülékregisztráció-kezelő felhasználó bekerül a készülékregisztráció-kezelő felhasználók listájába.

## <a name="remove-a-device-enrollment-manager"></a>Készülékregisztráció-kezelő eltávolítása

A készülékregisztráció-kezelő eltávolítása nincs hatással a regisztrált eszközökre. A készülékregisztráció-kezelő eltávolításakor:

-   Ha töröl egy felhasználót a készülékregisztráció-kezelő felhasználók listájáról, az nincs hatással a regisztrált eszközökre, ezek továbbra is teljes felügyelet alatt állnak.

-   Az eltávolított készülékregisztráció-kezelői fiók hitelesítő adatai érvényesek maradnak.

-   Az eltávolított készülékregisztráció-kezelő azonban nem törölheti az eszközök tartalmát, és nem vonhatja vissza őket.

-   Az eltávolított készülékregisztráció-kezelő nem regisztrálhat további eszközöket, kivéve, ha még nem érte el – az Intune-rendszergazda által konfigurált – eszközönkénti felső határt.

**Készülékregisztráció-kezelő eltávolítása**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Készülékregisztráció-kezelők** elemet.

3. A **Készülékregisztráció-kezelő** panelen kattintson a jobb gombbal a készülékregisztráció-kezelő felhasználóra, és válassza az **Eltávolítás** parancsot.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>A készülékregisztráció-kezelő tulajdonságainak megtekintése

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Készülékregisztráció-kezelők** elemet.

3. Kattintson a jobb gombbal a készülékregisztráció-kezelő felhasználóra az **Készülékregisztráció-kezelők** panelen, és válassza a **Tulajdonságok** parancsot.

