---
title: "A Dynamics CRM Online védelme"
description: "Feltételes hozzáféréssel védheti és vezérelheti a Dynamics CRM Online-hoz való hozzáférést."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: da92d75cfafa2a605ed8606ba7c8f3ec18dc6063
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="protect-access-to-dynamics-crm-online-with-intune"></a>A Dynamics CRM Online-hoz való hozzáférés védelme az Intune használatával

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Dynamics CRM Online-hoz való hozzáférést iOS- és Android-eszközökről a Microsoft Intune feltételes hozzáférési funkciójával szabályozhatja.  Az Intune feltételes hozzáférése két összetevőből áll:
* Egy [eszközmegfelelőségi szabályzatból](introduction-to-device-compliance-policies-in-microsoft-intune.md), amelynek az eszköznek meg kell felelnie, hogy a rendszer megfelelőnek találja.
* Egy [feltételes hozzáférési szabályzatból](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), amelyben meghatározhatja azokat a feltételeket, amelyeknek az eszköznek meg kell felelnie ahhoz, hogy hozzáférhessen a szolgáltatáshoz.

Ha szeretné jobban megismerni a feltételes hozzáférés működését, olvassa el [Az e-mailek, az Office 365- és egyéb szolgáltatások elérésének védelme](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) című cikket.

> [!IMPORTANT]
> A feltételes hozzáférés üzembe helyezéséhez az Intune és az Azure Active Directory Premium előfizetése is szükséges, a felhasználóknak pedig mindkét termékhez licenccel kell rendelkezniük. Az **Enterprise Mobility + Security (EMS) előfizetés** az Intune és az Azure Active Directory Premium előfizetését is tartalmazza. További részleteket az [Enterprise Mobility díjszabását ismertető lapon](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) talál. Ha nem rendelkezik EMS-előfizetéssel, előfizethet a Premium szintű Azure Active Directoryra. Lásd az [Azure Active Directory díjszabását ismertető lapot](https://azure.microsoft.com/pricing/details/active-directory/).

Amikor egy célzott felhasználó a Dynamics CRM alkalmazást szeretné használni az eszközén, a következő ellenőrzés megy végbe:

![Azokat a döntési pontokat megjelenítő diagram, amelyek segítségével a rendszer meghatározza, hogy hozzáférést kaphat-e az adott eszköz az adott szolgáltatáshoz](../media/mdm-ca-dynamics-crm-flow-diagram.png)

A Dynamics CRM Online alkalmazáshoz hozzáférést igénylő eszköznek a következő feltételeknek kell megfelelnie:
* Az eszköz legyen **Android** vagy **iOS** rendszerű.
* Az Intune-ban **regisztrálva** kell lennie.
* **Meg kell felelnie** az Intune összes telepített megfelelőségi szabályzatának.

Az eszköz állapotát a rendszer az Azure Active Directoryban tárolja, amely a megadott feltételek alapján engedélyezi vagy letiltja a hozzáférést.

Ha egy feltétel nem teljesül, a felhasználó számára az alábbi üzenetek egyike jelenik meg a bejelentkezéskor:
* Ha az eszköz nincs regisztrálva az Intune-ban vagy az Azure Active Directoryban, megjelenik egy üzenet, amely leírja, hogyan kell telepítenie a Vállalati portál alkalmazást és regisztrálnia az eszközt.
* Ha az eszköz nem megfelelő, egy üzenet jelenik meg, amely a felhasználót a Microsoft Intune Vállalati portál webhelyére vagy a Vállalati portál alkalmazásba irányítja, ahol további információt talál a problémáról és annak megoldásáról.

## <a name="configure-conditional-access-for-dynamics-crm-online"></a>A Dynamics CRM Online feltételes hozzáférésének beállítása  
### <a name="step-1-configure-active-directory-security-groups"></a>1. lépés: Az Active Directory-alapú biztonsági csoportok beállítása

Kezdés előtt állítsa be az Azure Active Directory-alapú biztonsági csoportokat a feltételes hozzáférési szabályzathoz. Ezeket a csoportokat az **Office 365 Felügyeleti központban** konfigurálhatja. Ezen csoportok alapján lehet megcélozni, illetve kivételként kezelni a felhasználókat. Amikor egy felhasználóra házirend vonatkozik, az erőforrások eléréséhez az általa használt összes eszköznek meg kell felelnie a házirendnek.

A Dynamics CRM Online-ra vonatkozó szabályzatban két csoporttípust határozhat meg:
* **Megcélzott csoportok**. Azokat a felhasználói csoportokat tartalmazza, amelyekre a szabályzat vonatkozik.
* **Kivétel alá eső csoportok**. A szabályzat alól mentesülő felhasználók csoportjait tartalmazza.

Ha egy felhasználó mindkét csoportban szerepel, mentesül a szabályzat alól.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>2. lépés: Megfelelőségi szabályzat konfigurálása és telepítése
[Hozzon létre](create-a-device-compliance-policy-in-microsoft-intune.md) és [telepítsen](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) megfelelőségi szabályzatot a szabályzat hatálya alá eső összes eszközre. Ez minden olyan eszközre értendő, amelyet a Megcélzott csoportokba tartozó felhasználók használnak.

> [!NOTE]
> A megfelelőségi szabályzatok a Microsoft Intune csoportjaira vonatkoznak, a feltételes hozzáférési szabályzatok viszont az Azure Active Directory biztonsági csoportjait célozzák meg.

> [!IMPORTANT]
> Amennyiben nem telepített megfelelőségi szabályzatot, a rendszer megfelelőként fogja értékelni az eszközöket.

Ha készen áll, folytassa a 3. lépéssel.
### <a name="step-3-configure-the-dynamics-crm-policy"></a>3. lépés: A Dynamics CRM házirendjének konfigurálása
Ezután állítsa be úgy a házirendet, hogy csak a felügyelt és a feltételeknek megfelelő eszközök érhessék el a Dynamics CRM-et. A szabályzat ezek után az Azure Active Directoryban tárolódik.

1.  Az Intune felügyeleti konzolján kattintson a **Házirend > Feltételes hozzáférés > Dynamics CRM Online-szabályzat** elemre.

  ![Képernyőfelvétel a Dynamics CRM Online feltétes hozzáférési szabályzatának oldaláról](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  Válassza a **Feltételes hozzáférési szabályzat engedélyezése** lehetőséget.
3.  Az **Alkalmazás hozzáférése**szakaszban kiválaszthatja, hogy mire szeretné alkalmazni a feltételes hozzáférési szabályzatot:
  * **iOS**
  * **Android--**
4.  A **Megcélzott csoportok** területen kattintson a **Módosítás** lehetőségre azon Active Directorybeli biztonsági csoportok kiválasztásához, amelyekre érvényes a szabályzat. Kiválaszthatja, hogy a szabályzat minden felhasználóra, vagy csak felhasználók bizonyos csoportjaira vonatkozzon.
5.  A **Kivétel alá eső csoportok**területen kattintson a **Módosítás** lehetőségre azon Active Directory-alapú biztonsági csoportok kiválasztásához, amelyekre nem érvényes a szabályzat.
6.  Ha elkészült, válassza a **Mentés** elemet.

Ezzel elvégezte a Dynamics CRM feltételes elérésének beállítását. A feltételes hozzáférési szabályzatot nem kell telepítenie, az azonnal érvénybe lép.
##  <a name="monitor-the-compliance-and-conditional-access-policies"></a>A megfelelőség és a feltételes hozzáférési házirendek megfigyelése

A **Csoportok** munkaterületen megtekintheti eszközei feltételes hozzáférési állapotát.

Válassza ki bármelyik mobileszköz-csoportot, majd az **Eszközök** lapon válasszon az alábbi **Szűrők**közül:
* **Az AAD-ben nem regisztrált eszközök**. Ezen eszközök a Dynamics CRM-hez való hozzáférése le van tiltva.
* **Nem megfelelő eszközök**. Ezen eszközök a Dynamics CRM-hez való hozzáférése le van tiltva.
* **Az AAD-ben regisztrált és megfelelő eszközök**. Ezek az eszközök hozzáférhetnek a Dynamics CRM-hez.

##  <a name="next-steps"></a>További lépések
* [A Exchange Online-hoz való hozzáférés védelme](restrict-access-to-exchange-online-with-microsoft-intune.md)

* [A helyszíni Exchange-hez való hozzáférés védelme](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
* [A SharePoint Online-hoz való hozzáférés védelme](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

* [A Skype Vállalati online verzióhoz való hozzáférés védelme](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
