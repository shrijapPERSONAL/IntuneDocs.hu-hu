---
title: "A használati feltételek beállítása a Microsoft Intune-ban"
titleSuffix: Intune Azure preview
description: "A felhasználók által az Intune Céges portálon látható használati feltételek beállítása. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d53e91e24988d1bc71ff8df425f0d82e0fc43b58
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017

---

# <a name="ensure-users-accept-company-terms-for-access"></a>Gondoskodhat arról, hogy a felhasználók elfogadják a hozzáférésre vonatkozó céges feltételeket

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Az Intune rendszergazdájaként Ön döntheti el, hogy megköveteli-e a felhasználóktól a cég használati feltételeinek elfogadását a Céges portál használata előtt a saját eszközök beléptetése, valamint a céges erőforrások elérése céljából (például alkalmazások és e-mailek). A használati feltételek konfigurálása nem kötelező.

Több használati feltételt hozhat létre, és azokat különböző csoportokhoz rendelheti hozzá, így például eltérő nyelveket támogathat.

## <a name="create-terms-and-conditions"></a>Használati feltételek létrehozása
Az alábbi lépések végrehajtásával hozhat létre használati feltételeket. A megjelenítendő név és leírás adminisztrációs célt szolgál, míg a feltételek tulajdonságait a felhasználók láthatják a Céges portálon.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panelen az **Eszközök beléptetése**, majd a **Használati feltételek** elemet.

3. Válassza a **Létrehozás** lehetőséget.
![Képernyőkép az Intune-portálról, ahol a használati feltételekhez tartozó Létrehozás gomb látható](media/terms-create-terms.png)

4. A kibontott panelen adja meg az alábbi adatokat:

   - **Megjelenítendő név**: A feltételek neve az Intune-portálon. A felhasználók nem látják ezt a nevet.

   - **Leírás**: További részletek, amelyek alapján könnyebben felismerhetők a feltételek az Intune-portálon.

5. Nyissa meg a Feltételek és kikötések panelt a Használati feltételek megadása elem melletti nyílra kattintva, majd adja meg a következő adatokat:

   ![Képernyőkép a végfelhasználói használati feltételek elfogadó képernyőjéről a feltételek összegzésével](./media/terms-summary-create.png)

   - **Cím**: Ezt a címet látják a felhasználók a Céges portálon.

   - **Feltételek összefoglalása**: Ez a szöveg elmagyarázza, hogy mi történik, ha a felhasználók elfogadják a feltételeket. Például: „Az eszköz regisztrációjával Ön elfogadja a Contoso által meghatározott használati feltételeket. Folytatás előtt figyelmesen olvassa el a feltételeket.”

   - **Használati feltételek**: Azok a használati feltételek, amelyeket a felhasználók látnak, és amelyek elfogadása vagy elutasítása kötelező.

6. Válassza az **Ok**, majd a **Létrehozás** elemet.

## <a name="assign-terms-and-conditions"></a>Használati feltételek hozzárendelése

Hozzárendelhet használati feltételeket olyan felhasználói csoportokhoz, amelyeknek el kell fogadniuk a feltételeket a Céges portál használata előtt.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panelen az **Eszközök beléptetése**, majd a **Használati feltételek** elemet.

3. A használati feltételek listájában válassza ki a hozzárendelendő feltételeket, majd válassza a **Hozzárendelt csoportok** elemet.
![Képernyőkép az Intune-portál Csoport hozzárendelése paneljéről, amelyen a használati feltételek hozzárendelésekor látható a Csoport kijelölése és a Kijelölés gomb](media/terms-assign-groups.png)

4. Kattintson a **Csoport kijelölése** gombra, a **Csoportok kijelölése** panelen válassza ki a feltételekhez hozzárendelendő csoportokat, majd kattintson a **Kijelölés** elemre.

5. A **Hozzárendelt csoportok** panelen kattintson a **Mentés** elemre.  Ezzel megtörtént a használati feltételek hozzárendelése a kijelölt csoportok felhasználóihoz. A következő alkalommal a rendszer fel fogja szólítani a felhasználókat a feltételek elfogadására a Céges portálhoz való hozzáférés előtt.

   ![Képernyőkép a végfelhasználói használati feltételek elfogadó képernyőjéről a feltételek összegzésével](./media/terms-summary-accept.png)

## <a name="monitor-a-terms-and-conditions"></a>A használati feltételek figyelése

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Válassza az Intune panelen az **Eszközök beléptetése**, majd a **Használati feltételek** elemet.
2. A használati feltételek listájában válassza ki azokat a feltételeket, amelyeknél meg szeretné tekinteni az elfogadást, majd válassza az **Elfogadási állapotok** elemet.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>A használati feltételek több változatának használata
Szerkesztheti a használati feltételeket, és felügyelheti verzióikat. Javasoljuk, hogy amikor jelentős módosításokat végez a használati feltételeken, mindig növelje meg a verziószámot, és követelje meg az új feltételek elfogadását. Akkor tartsa meg az aktuális verziószámot, ha például gépelési hibákat javít, vagy a formázást módosítja.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az Intune panelen válassza az **Eszközök beléptetése** elemet, válassza a **Használati feltételek** elemet, válassza ki a módosítandó használati feltételeket, majd válassza a **Tulajdonságok** elemet.

4. A **Tulajdonságok** panelen válassza a **Használati feltételek** elemet, majd szükség szerint módosítsa a **Cím**, a **Feltételek összefoglalása** és a **Használati feltételek** elemeket. Ha a végzett módosítások miatt a felhasználóknak újra el kell fogadniuk a feltételeket, kattintson a következő elemre: **Kérje a felhasználóktól az újbóli elfogadást, és növelje a verziószámot a következőre**

4.  Válassza az **Ok**, majd a **Mentés** elemet.

