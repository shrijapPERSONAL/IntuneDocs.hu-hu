---
title: "Csak a céges adatok törlése az alkalmazásokból"
titleSuffix: Azure portal
description: "A cikk tájékoztatást nyújt az alkalmazások Microsoft Intune-nal való szelektív törléséről."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a1c6085ddf07c70eaaf81b6e043b6da35544388
ms.sourcegitcommit: 9fabf1a8db53842f7b00762374de5b137158ee25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Csak vállalati adatok törlése az Intune által felügyelt alkalmazásokból

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ha egy eszközt elveszítenek vagy ellopnak, vagy ha a dolgozó elhagyja a vállalatot, fontos eltávolítani a vállalati alkalmazásadatokat az eszközről. Előfordul, hogy a személyes adatokat meg kell őrizni, különösen, ha az eszköz a dolgozó saját tulajdona.

>[!NOTE]
> A vállalati adatok Intune által felügyelt alkalmazásokból való törlése jelenleg csak iOS és Android platformon támogatott.

A vállalati alkalmazásadatok szelektív törléséhez hozzon létre törlési kérést az ebben a témakörben leírt lépésekkel. A kérelem teljesítése után az alkalmazás a következő futtatásakor az eszközön a vállalati adatok törlődnek az alkalmazásból.

>[!IMPORTANT]
> Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes.

## <a name="create-a-wipe-request"></a>Törlési kérés

1.  Jelentkezzen be az [Azure portálra](https://portal.azure.com).

2.  Válassza a **További szolgáltatások** lehetőséget, a szűrési szövegmezőbe írja be az **Intune** szót, majd válassza ki az **Intune** elemet. Amikor megjelenik az Intune panel, válassza a **Mobilalkalmazások** panelt.

    ![A Microsoft Intune panel képernyőképe](./media/apps-selective-wipe01.png)

3.  A **Mobilalkalmazások panelen** válassza az **Alkalmazások szelektív törlése** lehetőséget.

4.  Kattintson az **Új törlési kérés** lehetőségre. Ennek hatására megnyílik az **Új törlési kérés** panel.

    ![Képernyőfelvétel: Az Új törlési kérés panel](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Válassza a **Felhasználó** elemet a **Felhasználó** panel megnyitásához, és válassza ki azt a felhasználót, akinek az alkalmazásadatait törölni kívánja.

6.  Ezután válassza az **Eszköz** lehetőséget az **Új törlési kérés** panelen. Ekkor megnyílik az **Eszköz kiválasztása** panel, amelyen látható a választott felhasználóhoz társított összes eszköz listája, valamint két oszlop is: az eszköznév, amely az eszköz felhasználó által definiált rövid neve, és az eszköztípus, amely az eszközplatformot mutatja. Válassza ki a törölni kívánt eszközt.

7.  Ekkor ismét az **Új törlési kérés** panel jelenik meg. A törlési kérés elindításához kattintson az **OK** gombra.

A szolgáltatás külön törlési kéréseket hoz létre az egyes védett alkalmazásokhoz az eszközön és a törlési kéréshez társított felhasználóhoz, és nyomon követi azokat.

## <a name="monitor-your-wipe-requests"></a>A törlési kérelmek figyelése

Elérhető egy összesítő jelentés is, amely a törlési kérelem összesített állapotát jeleníti meg, és tartalmazza a függőben lévő kérések és a hibák számát. Ha további részleteket szeretne megismerni, kövesse az alábbi lépéseket:

1.  A **Mobilalkalmazások – Alkalmazások szelektív törlése** panel a kérések listáját felhasználói csoportosításban jeleníti meg. A rendszer minden, az eszközön futó védett alkalmazáshoz külön törlési kérést hoz létre, ezért több kérés jelenhet meg ugyanannál a felhasználónál. Az állapot mutatja, hogy a törlési kérés **függőben van**, **sikertelen**, vagy **sikeres**.

    ![Képernyőkép a törlési kérés állapotáról az Alkalmazások szelektív törlése panelen](./media/wipe-request-status-1.png)

Ezen kívül látható az eszköz neve és típusa is, ami megkönnyíti a jelentések olvasását.

>[!IMPORTANT]
> A törléshez a felhasználónak meg kell nyitnia az alkalmazást, ami a kéréstől számítva akár 30 percig is eltarthat.

## <a name="delete-a-wipe-request"></a>Törlési kérés törlése

A felfüggesztett állapotú törlés addig lesz megjelenítve, míg manuálisan nem törli.  Törlési kérés manuális törléséhez:

1.  Nyissa meg a **Mobilalkalmazások – Alkalmazások szelektív törlése** panelt.

2.  Kattintson a listában a jobb gombbal a törölni kívánt törlési kérésre, és válassza a **Törlési kérés törlése** lehetőséget.

    ![Képernyőkép a törlési kérések listájáról az Alkalmazások szelektív törlése panelen](./media/delete-wipe-request.png)

3.  Ha a rendszer törlési megerősítést kér, válassza az **Igen** vagy a **Nem** lehetőséget, majd kattintson az **OK** gombra.

### <a name="see-also"></a>Lásd még:
[Mi az alkalmazásvédelmi szabályzat?](app-protection-policy.md)

[Mi az alkalmazáskezelés?](app-management.md)
