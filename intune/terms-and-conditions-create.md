---
title: "A használati feltételek beállítása a Microsoft Intune-ban"
titlesuffix: Azure portal
description: "A felhasználók által az Intune Céges portálon látható használati feltételek beállítása. "
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63434cbbc9edc668d59fb99968727551e0c4cc40
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2017
---
# <a name="ensure-users-accept-company-terms-for-access"></a>Gondoskodhat arról, hogy a felhasználók elfogadják a hozzáférésre vonatkozó céges feltételeket

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune-rendszergazdaként Ön döntheti el, hogy megköveteli-e a felhasználóktól a cég használati feltételeinek elfogadását, mielőtt a Céges portált használnák saját eszközeik beléptetéséhez, valamint az erőforrások (például céges alkalmazások és e-mailek) eléréséhez. A használati feltételek konfigurálása nem kötelező.

Több használati feltételt hozhat létre, és azokat különböző csoportokhoz rendelheti hozzá, így például eltérő nyelveket támogathat.

## <a name="create-terms-and-conditions"></a>Használati feltételek létrehozása
Az alábbi lépések végrehajtásával hozhat létre használati feltételeket. A megjelenítendő név és leírás adminisztrációs célt szolgál, míg a feltételek tulajdonságait a felhasználók láthatják a Céges portálon.

1. Válassza az Azure Portalon az **Eszközök regisztrálása**, majd a **Használati feltételek** lehetőséget.
2. Válassza a **Létrehozás** lehetőséget.
![Képernyőkép az Azure Portalról, melyen a használati feltételekhez tartozó Létrehozás gomb látható](media/terms-create-terms.png)
3. A kibontott panelen adja meg az alábbi adatokat:

   - **Megjelenített név**: A feltételek neve az Azure Portalon. A felhasználók nem látják ezt a nevet.

   - **Leírás**: További részletek, amelyek alapján könnyebben felismerhető az adott feltételkészlet az Azure Portalon.

4. Nyissa meg a Feltételek és kikötések panelt a Használati feltételek megadása elem melletti nyílra kattintva, majd adja meg a következő adatokat:

   ![Képernyőkép a végfelhasználói használati feltételek elfogadó képernyőjéről a feltételek összegzésével](./media/terms-summary-create.png)

   - **Cím**: a felhasználóknak ez jelenik meg a Céges portálon az **Összegzés** fölött.
   - **Feltételek összefoglalása**: Ez a szöveg ismerteti, hogy mi történik, ha a felhasználók elfogadják a feltételeket. Például: „Az eszköz regisztrálásával Ön elfogadja a Contoso által meghatározott használati feltételeket. Folytatás előtt figyelmesen olvassa el a feltételeket.”
   - **Használati feltételek**: Azok a használati feltételek, amelyeket a felhasználók látnak, és amelyek elfogadása vagy elutasítása kötelező.

5. Válassza az **Ok**, majd a **Létrehozás** elemet.

## <a name="see-how-terms-are-displayed-to-your-users"></a>A felhasználóknak megjelenő feltételek megtekintése
Az alábbi példában látható, hogyan jelenik meg a **Cím** és a **Feltételek összefoglalása** a felügyeleti konzolon és a Céges portálon.

![Képernyőkép: a Cím és a Feltételek összefoglalása a felügyeleti konzolon és a Céges portálon.](./media/terms-summary-terms.png)

Az alábbi példában látható, hogyan jelennek meg a használati feltételek a felügyeleti konzolon és a Céges portálon.

![Képernyőkép: a használati feltételek a felügyeleti konzolon és a Céges portálon.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Használati feltételek hozzárendelése

Hozzárendelhet használati feltételeket olyan felhasználói csoportokhoz, amelyeknek el kell fogadniuk a feltételeket a Céges portál használata előtt.

1. Válassza az Azure Portalon az **Eszközök regisztrálása**, majd a **Használati feltételek** lehetőséget.
2. A használati feltételek listájában válassza ki a hozzárendelendő feltételeket, majd válassza a **Hozzárendelt csoportok** elemet.
![Képernyőkép az Azure Portal Csoport hozzárendelése paneljéről, amelyen látható a használati feltételek hozzárendeléséhez tartozó Csoport kijelölése és Kijelölés gomb](media/terms-assign-groups.png)
3. Kattintson a **Csoport kijelölése** gombra, a **Csoportok kijelölése** panelen válassza ki a feltételekhez hozzárendelendő csoportokat, majd kattintson a **Kijelölés** elemre. A dinamikus csoportokhoz nem lehet használati feltételeket rendelni.
4. A **Hozzárendelt csoportok** panelen kattintson a **Mentés** elemre.  Ezzel megtörtént a használati feltételek hozzárendelése a kijelölt csoportok felhasználóihoz. A következő alkalommal a rendszer fel fogja szólítani a felhasználókat a feltételek elfogadására a Céges portálhoz való hozzáférés előtt. A használati feltételeket csak egyszer kell elfogadni, a több eszközzel bíró felhasználóknak tehát nem kell ezt megtenniük minden eszközön.


## <a name="monitor-terms-and-conditions"></a>A használati feltételek figyelése

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Válassza az Intune panelen az **Eszközök beléptetése**, majd a **Használati feltételek** elemet.
2. A használati feltételek listájában válassza ki azokat a feltételeket, amelyeknél meg szeretné tekinteni az elfogadást, majd válassza az **Elfogadási állapotok** elemet.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>A használati feltételek több változatának használata
Szerkesztheti a használati feltételeket, és felügyelheti verzióikat. Javasoljuk, hogy amikor jelentős módosításokat végez a használati feltételeken, mindig növelje meg a verziószámot, és követelje meg az új feltételek elfogadását. Akkor tartsa meg az aktuális verziószámot, ha például gépelési hibákat javít, vagy a formázást módosítja.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen válassza az **Eszközök beléptetése** elemet, válassza a **Használati feltételek** elemet, válassza ki a módosítandó használati feltételeket, majd válassza a **Tulajdonságok** elemet.

4. A **Tulajdonságok** panelen válassza a **Használati feltételek** elemet, majd szükség szerint módosítsa a **Cím**, a **Feltételek összefoglalása** és a **Használati feltételek** elemeket. Ha a módosítások miatt a felhasználóknak újra el kell fogadniuk a feltételeket, kattintson a **Kérje a felhasználóktól az újbóli elfogadást, és növelje a verziószámot a következőre** elemre.

4.  Válassza az **Ok**, majd a **Mentés** elemet.

A használati feltételeket csak egyszer kell elfogadni, a több eszközzel bíró felhasználóknak tehát nem kell ezt megtenniük minden eszközön.
