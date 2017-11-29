---
title: "Megfelelőségi szabályzatok alkalmazása Jamf által felügyelt eszközökön"
titlesuffix: Azure portal
description: "A megfelelőség alkalmazásával biztonságosabbá teheti a Jamf által felügyelt eszközöket."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6184552ce901ffc062f0453f169ec992049ae69b
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Jamf Pro által felügyelt Mac számítógépek megfelelőségének kikényszerítése

|A következőkre vonatkozik: Intune az Azure Portalon |
|--|
|A klasszikus portálbeli Intune-ról keres dokumentációt? [Lépjen tovább ide](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Jelenleg Private Preview verzióban|
|--|
|A jelen témakörben leírt funkciók jelenleg csak Private Preview verzióban érhetők el az ügyfelek számára. Miután a verzió minden felhasználó számára elérhetővé vált, eltávolítjuk ezt a megjegyzést.|
| |

Az Azure Active Directory és a Microsoft Intune feltételes hozzáférési szabályzatai biztosítják, hogy a végfelhasználók megfeleljenek a szervezeti követelményeknek. Ezeket a szabályzatokat a [Jamf Pro által felügyelt](conditional-access-integrate-jamf.md) Mac számítógépekre is alkalmazhatja. Ennek megvalósításához az Intune és a Jamf Pro konzolhoz egyaránt hozzáférésre van szüksége.

## <a name="set-up-device-compliance-policies-in-intune"></a>Eszközmegfelelőségi szabályzatok beállítása az Intune-ban

1. Nyissa meg a Microsoft Azure-t, majd az **Intune** > **Eszközmegfelelőség** > **Szabályzatok** oldalt. Szabályzatokat hozhat létre macOS eszközökre, beleértve számos, nem megfelelő felhasználókra és csoportokra vonatkozó műveletet (pl. figyelmeztető e-mailek küldése).
2. Keresse meg a kívánt csoportokat, és alkalmazza rájuk a szabályzatokat.

## <a name="require-the-company-portal-app-for-macos"></a>MacOS-eszközhöz készült Céges portál alkalmazás igénylése

1. A macOS-eszközön nyissa meg a https://aka.ms/macoscompanyportal oldalt a macOS-hoz készült Céges portál alkalmazás letöltéséhez.
2. Nyissa meg a Jamf Pro szolgáltatást, majd a **Számítógép-kezelés** > **Csomagok** oldalt.
3. Hozzon létre egy új csomagot a macOS-hez készült Céges portál alkalmazással, majd kattintson a **Mentés** elemre.
4. Nyissa meg a **Számítógépek** > **Szabályzatok** oldalt, majd kattintson az **Új** elemre.
5. Az **Általános** tartalom használatával konfigurálja a szabályzat beállításait, köztük az eseményindítót és a végrehajtás gyakoriságát.
6. Válassza ki a **Csomagok** tartalmat, és kattintson a **Konfigurálás** elemre.
7. A **Hozzáadás** elemre kattintva válassza ki a csomagot a Céges portál alkalmazással.
8. A felugró **Művelet** menüből válassza ki a **Telepítés** lehetőséget.
9. Konfigurálja a csomag beállításait.
10. Kattintson a **Hatókör** lapra annak meghatározásához, hogy mely számítógépeken kell telepíteni a Céges portál alkalmazást. Kattintson a **Mentés**gombra. Legközelebb, amikor a megadott eseményindító kiváltódik a számítógépen, és megfelel az **Általános** tartalomban szereplő feltételeknek, a szabályzat lefut a hatókörbe bevont eszközökön.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>Felhasználók átirányítása a Jamf Pro által kezelt eszközök Azure Active Directoryban történő regisztrációjához

> [!NOTE]
> A következő lépések előtt [üzembe kell helyeznie a macOS-eszközökhöz készült Céges portált](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos).  

Ahhoz, hogy az eszközt Jamf Pro által kezelt eszközként regisztrálhassák az Azure AD szolgáltatásban, a végfelhasználóknak a Jamf Self Service oldalról kell megnyitniuk a Céges portál alkalmazást.

1. A Jamf Pro oldalán nyissa meg a **Számítógépek** > **Szabályzatok** oldalt, és hozzon létre egy új eszközregisztrációs szabályzatot.
2. Konfigurálja a **Feltételes hozzáférés** tartalmat, beleértve az eseményindítót és a végrehajtás gyakoriságát is. Állítsa a prioritást az **Utána** lehetőségre.
3. A **Hatókör** lapra kattintva terjessze ki a szabályzat hatókörét az összes megcélzott eszközre.
4. A **Self Service** lapra kattintva tegye elérhetővé a szabályzatot a Jamf Self Service szolgáltatásban. Adja hozzá a szabályzatot az **Eszközmegfelelőség** kategóriához. Kattintson a **Mentés**gombra.
