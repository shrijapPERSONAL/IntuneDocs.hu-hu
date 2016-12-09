---
title: "Felügyelt vállalati alkalmazás adatainak törlése | Microsoft Intune"
description: "Ismerje meg a csak vállalati adatok eszközökről történő távoli eltávolításának módját."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d32a66ee283906586e25173e736c02ee8bf23042


---

# <a name="wipe-managed-company-app-data-with-microsoft-intune"></a>A Microsoft Intune-nal felügyelt vállalati alkalmazások adatainak törlése
Ha egy eszközt elveszítenek vagy ellopnak, vagy ha a dolgozó elhagyja a vállalatot, fontos eltávolítani a vállalati alkalmazásadatokat az eszközről. Előfordul, hogy a személyes adatokat meg kell őrizni, különösen, ha az eszköz a dolgozó saját tulajdona.

A vállalati alkalmazásadatok szelektív törléséhez hozzon létre törlési kérést az ebben a témakörben leírt lépésekkel. A kérelem teljesítése után az alkalmazás a következő futtatásakor az eszközön a vállalati adatok törlődnek az alkalmazásból.
>[!NOTE]
> Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes.



## <a name="create-a-wipe-request"></a>Törlési kérés

1.  Az **Intune mobilalkalmazás-kezelés** panelen kattintson a **Törlési kérések** csempére.

    ![Képernyőfelvétel: Intune mobilalkalmazás-kezelés panel, Összefoglalás csempék](../media/AppManagement/AzurePortal_MAM_WipeRequests.png)

2.  Kattintson az **Új törlési kérés** lehetőségre. Ennek hatására megnyílik az **Új törlési kérés** panel.

    ![Képernyőfelvétel: Az Új törlési kérés panel](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

3.  Válassza a **Felhasználó** elemet a **Felhasználó** panel megnyitásához, és válassza ki azt a felhasználót, akinek az alkalmazásadatait törölni kívánja.

4.  Válassza az **Eszköz** lehetőséget.  Ekkor megnyílik a **Eszköz** panel, amelyen látható a kijelölt felhasználóhoz társított összes eszköz listája.  Válassza ki a törölni kívánt eszközt.

5.  Ekkor ismét az **Új törlési kérés** panel jelenik meg. A törlési kérés elindításához kattintson az **OK** gombra. A szolgáltatás külön törlési kéréseket hoz létre az egyes védett alkalmazásokhoz az eszközön, és nyomon követi azokat.


![Képernyőfelvétel: A Törlési kérések csempe ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## <a name="monitor-your-wipe-requests"></a>A törlési kérelmek figyelése
Az **Intune mobilalkalmazás-felügyelet** panel összefoglaló jelentést jelenít meg a **Törlési kérés** csempén.  Ez megjeleníti a törlés összesített állapotát és a függőben lévő kérések és hibák számát. A következő lépésekkel további részleteket is megjeleníthet:

1.  Az **Intune mobilalkalmazás-kezelés** panelen kattintson a **Törlési kérések** csempére a **Törlési kérés** panel megnyitásához.

2.  A **Törlési kérés** panelen a kérelmek felhasználók szerint csoportosított listája látható. A rendszer minden, az eszközön futó védett alkalmazáshoz külön törlési kérést hoz létre, ezért több kérés jelenhet meg ugyanannál a felhasználónál. Az állapot mutatja, hogy a törlési kérés **függőben van**, **sikertelen**, vagy **sikeres**.

A törléshez a felhasználónak meg kell nyitnia az alkalmazást, ami a kéréstől számítva akár 30 percig is eltarthat.

A felfüggesztett állapotú törlés addig lesz megjelenítve, míg manuálisan nem törli.  A törlési kérés manuális törléséhez kattintson a jobb egérgombbal, és válassza a törlés lehetőséget.

### <a name="see-also"></a>További információ
[Alkalmazásadatok védelme mobilalkalmazás-felügyeleti házirendekkel](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Az Azure-portál használata](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Dec16_HO2-->


