---
title: Alkalmazások telepítésével kapcsolatos problémák elhárítása
titlesuffix: Microsoft Intune
description: A Microsoft Intune hibaelhárítási paneljével elháríthatja az alkalmazások telepítésével kapcsolatos problémákat.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: c1c2a37103f8fedc09a70b4387aae3f472dfb636
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138679"
---
# <a name="troubleshoot-app-installation-issues"></a>Alkalmazások telepítésével kapcsolatos problémák elhárítása

A Microsoft Intune MDM által felügyelt eszközökön néha sikertelenek lehetnek az alkalmazástelepítések. Ilyen esetekben nem könnyű megérteni a hiba okát, illetve elhárítani azt. A Microsoft Intune olyan adatokat szolgáltat az alkalmazástelepítésbeli hibákról, amelyekkel az ügyfélszolgálati operátorok és az Intune-rendszergazdák megtekinthetik az alkalmazásadatokat, és reagálhatnak az ügyfelek kérelmeire. Az Intune hibaelhárítási panelje megjeleníti a hibák adatait, így a felhasználói eszközökön kezelt alkalmazások információit is. Az alkalmazások végpontok közötti életciklusához tartozó adatok a **Felügyelt alkalmazások** panelen, az egyes eszközök alatt tekinthetők meg. Itt megtekintheti a telepítési problémákat, például az alkalmazás létrehozási, módosítási és célzási dátumát, valamint az eszközökre való továbbításának dátumát. 

## <a name="to-review-app-troubleshooting-details"></a>Az alkalmazás hibaelhárítási adatainak ellenőrzése

Az Intune az adott felhasználók eszközein telepített alkalmazások alapján szolgáltat hibaelhárítási információkat.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Hibaelhárítás** lehetőséget.
4. A felhasználó kiválasztásához kattintson a **Felhasználó kijelölése** lehetőségre. Ekkor megjelenik a **Felhasználók kijelölése** panel.
5. Jelöljön ki egy felhasználót a megfelelő név vagy e-mail cím beírásával. Kattintson a **Kijelölés** gombra a lap alján. A felhasználóval kapcsolatos hibaelhárítási információ a **Hibaelhárítás** panelen jelenik meg. 
6. Az **Eszközök** listában jelölje ki azt az eszközt, amelyen hibaelhárítást szeretne végezni.
    ![Az Intune Hibaelhárítás panelje.](media/troubleshoot-app-install-01.png)
7. A kijelölt eszköz paneljén válassza a **Felügyelt alkalmazások** lehetőséget. Megjelenik a felügyelt alkalmazások listája.
    ![Az Intune által kezelt eszköz adatai.](media/troubleshoot-app-install-02.png)
8. Válassza ki azt az alkalmazást, amelynél hibát jelez a **Telepítés állapota**.
    ![A kiválasztott alkalmazás, amelynél megjelennek a telepítési hiba adatai.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Ugyanazt az alkalmazást eltérő alkalmazásműveleti szándékkal rendelhetik hozzá különböző csoportokhoz. Egy alkalmazás feloldott szándéka például **Kizárva** értéket jelez, ha az alkalmazás ki van zárva egy felhasználó számára az alkalmazás-hozzárendelés során. További információ: [Alkalmazások hozzárendelési ütközéseinek feloldása](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Az Intune jelenleg nem szűri operációsrendszer-platform alapján az alkalmazásokat.

Az alkalmazástelepítési hiba információi ismertetik a problémát. Ezen adatok segítségével meghatározhatja a probléma feloldásához szükséges műveletet. További információ az alkalmazástelepítési problémák elhárításáról: [Alkalmazástelepítési problémák hibakódjai](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> A **Hibaelhárítás** panel a böngészőben a [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) címen is elérhető.

## <a name="next-steps"></a>További lépések

- További információt az Intune hibaelhárításáról a [Segítségnyújtás a céges felhasználóknak a hibaelhárítási portál használatával](help-desk-operators.md) című témakörben talál. 
- Ismertető a Microsoft Intune esetleges ismert problémáiról. További információt [Az Intune ismert problémái](known-issues.md) című témakörben talál.
- További segítségre van szüksége? Ismerje meg, [hogyan kérhet támogatást az Intune-hoz](get-support.md).
