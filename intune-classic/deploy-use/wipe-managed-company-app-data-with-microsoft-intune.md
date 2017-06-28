---
title: "Felügyelt vállalati alkalmazás adatainak törlése"
description: "Ismerje meg a csak vállalati adatok eszközökről történő távoli eltávolításának módját."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 7025bdd5d89e52f1c99f9cd834232daf324f3285
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---

# <a name="wipe-company-app-data-with-intune-mam"></a>Az Intune MAM-mal felügyelt vállalati alkalmazások adatainak törlése

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ha egy eszközt elveszítenek vagy ellopnak, vagy ha a dolgozó elhagyja a vállalatot, fontos eltávolítani a vállalati alkalmazásadatokat az eszközről. Előfordul, hogy a személyes adatokat meg kell őrizni, különösen, ha az eszköz a dolgozó saját tulajdona.

A vállalati alkalmazásadatok szelektív törléséhez hozzon létre törlési kérést az ebben a témakörben leírt lépésekkel. A kérelem teljesítése után az alkalmazás a következő futtatásakor az eszközön a vállalati adatok törlődnek az alkalmazásból.

>[!IMPORTANT]
> Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes.

## <a name="create-a-wipe-request"></a>Törlési kérés

1.  Jelentkezzen be az [Azure portálra](https://portal.azure.com).

2.  Válassza a **További szolgáltatások** lehetőséget, a szűrési szövegmezőbe írja be az **Intune** szót, majd válassza ki az **Intune-alkalmazásvédelem** elemet. Megnyílik az Intune mobilalkalmazás-felügyelet panel.

    ![Képernyőfelvétel: Az Új törlési kérés panel](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  A **Beállítások** panelen válassza a **Törlési kérések** elemet.

3.  Kattintson az **Új törlési kérés** lehetőségre. Ennek hatására megnyílik az **Új törlési kérés** panel.

    ![Képernyőfelvétel: Az Új törlési kérés panel](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Válassza a **Felhasználó** elemet a **Felhasználó** panel megnyitásához, és válassza ki azt a felhasználót, akinek az alkalmazásadatait törölni kívánja.

5.  Válassza az **Eszköz** lehetőséget. Ekkor megnyílik az **Eszköz** panel, amelyen látható a kijelölt felhasználóhoz társított összes eszköz listája, valamint két oszlop is: az eszköznév, amely az eszköz felhasználó által definiált rövid neve, és az eszköztípus, amely az eszközplatformot mutatja. Válassza ki a törölni kívánt eszközt.

6.  Ekkor ismét az **Új törlési kérés** panel jelenik meg. A törlési kérés elindításához kattintson az **OK** gombra. 

A szolgáltatás külön törlési kéréseket hoz létre az egyes védett alkalmazásokhoz az eszközön és a törlési kéréshez társított felhasználóhoz, és nyomon követi azokat.

>[!NOTE]
> **Törlési kérést** úgy is létrehozhat, ha az Intune mobilalkalmazás-felügyeleti panelen a **Törlési kérések csempére** kattint.

## <a name="monitor-your-wipe-requests"></a>A törlési kérelmek figyelése

Elérhető egy összesítő jelentés is, amely a törlési kérelem összesített állapotát jeleníti meg, és tartalmazza a függőben lévő kérések és a hibák számát. Ha további részleteket szeretne megismerni, kövesse az alábbi lépéseket:

1.  Az Intune mobilalkalmazás-felügyelet panelen kattintson a **Törlési kérések** csempére.

2.  A **Törlési kérés** panelen kattintson a **Törlési kérések** csempére a **Törlési kérés** panel megnyitásához.

3.  A **Törlési kérés** panelen a kérelmek felhasználók szerint csoportosított listája látható. A rendszer minden, az eszközön futó védett alkalmazáshoz külön törlési kérést hoz létre, ezért több kérés jelenhet meg ugyanannál a felhasználónál. Az állapot mutatja, hogy a törlési kérés **függőben van**, **sikertelen**, vagy **sikeres**.

    ![Képernyőfelvétel: Az Új törlési kérés panel](../media/AppManagement/wipe-request-status-1.png)

Ezen kívül látható az eszköz neve és típusa is, ami megkönnyíti a jelentések olvasását.

>[!IMPORTANT]
> A törléshez a felhasználónak meg kell nyitnia az alkalmazást, ami a kéréstől számítva akár 30 percig is eltarthat.

## <a name="delete-a-wipe-request"></a>Törlési kérés törlése

A felfüggesztett állapotú törlés addig lesz megjelenítve, míg manuálisan nem törli.  Törlési kérés manuális törléséhez

1.  Az Intune mobilalkalmazás-felügyelet panelen kattintson a **Törlési kérések** csempére.

2.  A **Törlési kérés** panelen kattintson a **Törlési kérések** csempére a **Törlési kérés** panel megnyitásához.

3.  Kattintson a jobb egérgombbal a törölni kívánt törlési kérésre, majd válassza a **Törlési kérés törlése** lehetőséget.

    ![Képernyőfelvétel: Az Új törlési kérés panel](../media/AppManagement/delete-wipe-request.png)

4.  Ha a rendszer törlési megerősítést kér, válassza az **Igen** vagy a **Nem** lehetőséget, majd kattintson az **OK** gombra.


### <a name="see-also"></a>További információ
[Alkalmazásadatok védelme mobilalkalmazás-felügyeleti házirendekkel](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Az Azure-portál használata](azure-portal-for-microsoft-intune-mam-policies.md)

