---
title: A használati feltételek beállítása a Microsoft Intune-ban
titlesuffix: ''
description: A felhasználók által az Intune Céges portálon látható használati feltételek beállítása.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b0571ad6196277ee2bc257d72cc4db24fcc3424
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237945"
---
# <a name="terms-and-conditions-for-user-access"></a>Felhasználói hozzáférési használati feltételek

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune rendszergazdájaként megkövetelheti a felhasználóktól a cég feltételeinek elfogadását, mielőtt a Céges portált az alábbiakra használnák:
- eszközök regisztrálása,
- erőforrások, például a vállalati alkalmazások és az e-mailek elérése.    
A használati feltételek konfigurálása nem kötelező.

Több használati feltételt hozhat létre, és azokat különböző csoportokhoz rendelheti hozzá, így például eltérő nyelveket támogathat.

A céges használati feltételeket kétféleképpen hozhatja létre:
- Az Intune-nal az ebben a cikkben leírtak szerint.
- Az [Azure Active Directory használati feltételek funkciójával](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou). Hogy megtudja, melyik módszer a legjobb az Ön számára, tekintse át [a cége számára megfelelő használati feltételi megoldás kiválasztásáról szóló blogbejegyzést](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409). 

## <a name="create-terms-and-conditions"></a>Használati feltételek létrehozása
Az alábbi lépések végrehajtásával hozhat létre használati feltételeket. A megjelenítendő név és leírás adminisztrációs célt szolgál, míg a feltételek tulajdonságait a felhasználók láthatják a Céges portálon.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Intune** panelen az **Eszközregisztráció** > **Feltételek és kikötések** lehetőséget.
2. Válassza a **Létrehozás** lehetőséget.
![Képernyőkép az Azure Portalról, melyen a használati feltételekhez tartozó Létrehozás gomb látható](media/terms-create-terms.png)
3. A kibontott panelen adja meg az alábbi adatokat:

   - **Megjelenített név**: Az Azure Portalon a feltételek neve. A felhasználók nem látják ezt a nevet.

   - **Description** (Leírás): További részletek, amelyek segítenek azonosítani az adott feltételkészlet az Azure Portalon.

4. Nyissa meg a Feltételek és kikötések panelt a **Használati feltételek megadása** melletti nyílra kattintva, majd adja meg a következő adatokat:

   ![Képernyőkép a végfelhasználói használati feltételek elfogadó képernyőjéről a feltételek összegzésével](./media/terms-summary-create.png)

   - **Cím**: A felhasználók számára a vállalati portálon, a fenti feltételek neve az **összefoglalás**.
   - **Feltételek összefoglalása**: Az szöveg, amely azt ismerteti, hogy mit jelent van, amikor a felhasználók elfogadják a feltételeket. Például: „Az eszköz regisztrálásával Ön elfogadja a Contoso által meghatározott használati feltételeket. Folytatás előtt figyelmesen olvassa el a feltételeket.”
   - **Feltételek és kikötések**: A használati feltételeket, amelyek a felhasználók megtekintéséhez és kell elfogadhatja vagy elutasíthatja.

5. Válassza az **OK** > **Létrehozás** lehetőséget.

## <a name="see-how-terms-are-displayed-to-your-users"></a>A felhasználóknak megjelenő feltételek megtekintése
Az alábbi példában látható, hogyan jelenik meg a **Cím** és a **Feltételek összefoglalása** a felügyeleti konzolon és a Céges portálon.

![Képernyőkép: a Cím és a Feltételek összefoglalása a felügyeleti konzolon és a Céges portálon.](./media/terms-summary-terms.png)

Az alábbi példában látható, hogyan jelennek meg a használati feltételek a felügyeleti konzolon és a Céges portálon.

![Képernyőkép: a használati feltételek a felügyeleti konzolon és a Céges portálon.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Használati feltételek hozzárendelése

Hozzárendelhet használati feltételeket olyan felhasználói csoportokhoz, amelyeknek el kell fogadniuk a feltételeket a Céges portál használata előtt.

1. Válassza az Azure Portalon az **Eszközök regisztrálása**, majd a **Használati feltételek** lehetőséget.
2. A használati feltételek listájában válassza ki a hozzárendelni kívánt feltételeket, majd válassza a **Kezelés** > **Hozzárendelések** elemet.
![Képernyőkép az Azure Portal Csoport hozzárendelése paneljéről, amelyen látható a használati feltételek hozzárendeléséhez tartozó Csoport kijelölése és Kijelölés gomb](media/terms-assign-groups.png)
3. Válassza a **Bevonandó csoportok kijelölése** lehetőséget, válassza ki a feltételekhez hozzárendelni kívánt csoportokat, majd a **Kijelölés** lehetőséget. A dinamikus csoportokhoz nem lehet használati feltételeket rendelni.
4. A **Hozzárendelt csoportok** panelen válassza a **Mentés** gombot.  Ezzel megtörtént a használati feltételek hozzárendelése a kijelölt csoportok felhasználóihoz. A következő alkalommal a rendszer fel fogja szólítani a felhasználókat a feltételek elfogadására a Céges portálhoz való hozzáférés előtt. A használati feltételeket csak egyszer kell elfogadni, a több eszközzel bíró felhasználóknak tehát nem kell ezt megtenniük minden eszközön.


## <a name="monitor-terms-and-conditions"></a>A használati feltételek figyelése

1. Az Azure Portalon válassza a **Minden szolgáltatás** > **Figyelés + felügyelet** > **Intune** lehetőséget. 
1. Válassza az Intune panelen az **Eszközregisztráció** > **Feltételek és kikötések** lehetőséget.
2. A használati feltételek listájában válassza ki azokat a feltételeket, amelyeknél meg szeretné tekinteni az elfogadást, majd válassza az **Elfogadási jelentés** lehetőséget.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>A használati feltételek több változatának használata
Szerkesztheti a használati feltételeket, és felügyelheti verzióikat. Minden alkalommal, amikor lényeges módosításokat végez a használati feltételekben, el kell végeznie az alábbiakat:
- az alkalmazás verziószámának növelése
- meg kell követelnie a felhasználóktól az új feltételek és kikötések elfogadását. Ha például helyesírási hibákat javít, vagy módosítja a formázást, őrizze meg az aktuális verziószámot.

1. Az Azure Portalon válassza a **Minden szolgáltatás** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen válassza az **Eszközök beléptetése** > **Feltételek és kikötések** lehetőséget, válassza ki a módosítani kívánt használati feltételeket, majd válassza a **Tulajdonságok** lehetőséget.

4. A **Tulajdonságok** panelen válassza a **Feltételek és kikötések** lehetőséget, majd szükség szerint módosítsa a **Cím**, a **Feltételek összefoglalása** és a **Feltételek és kikötések** szövegét. Ha a módosítások miatt a felhasználóknak újra el kell fogadniuk a feltételeket, válassza a **Kérje a felhasználóktól az újbóli elfogadást, és növelje a verziószámot a következőre** lehetőséget.

4.  Válassza az **OK** > **Mentés** gombokat.

A használati feltételeket csak egyszer kell elfogadni, a több eszközzel bíró felhasználóknak tehát nem kell ezt megtenniük minden eszközön.
