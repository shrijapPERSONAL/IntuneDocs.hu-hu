---
title: "A Skype Vállalati online verzió védelme"
description: "A feltételes hozzáférés funkció segítségével védheti és felügyelheti a Skype Vállalati online verzióhoz való hozzáférést."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 30d1abb3e7411cae73a98be51489cffdfc738e7f
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="protect-access-to-skype-for-business-online-with-microsoft-intune"></a>A Skype Vállalati online verzió elérésének védelme a Microsoft Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Skype Vállalati online verzióhoz való hozzáférés korlátozásához állítson be a **Skype Vállalati online verzióra** vonatkozó feltételes hozzáférési szabályzatot.
A feltételes hozzáférés két összetevőből áll:
- Egy eszközmegfelelőségi szabályzatból, amelynek az eszköznek meg kell felelnie, hogy a rendszer megfelelőnek találja.
- Egy feltételes hozzáférési szabályzatból, amelyben meghatározhatja azokat a feltételeket, amelyeknek az eszköznek meg kell felelnie ahhoz, hogy hozzáférhessen a szolgáltatáshoz.
Ha szeretné jobban megismerni a feltételes hozzáférés működését, olvassa el [Az e-mailek és az O365-szolgáltatások elérésének védelme](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) című cikket.

Amikor egy célzott felhasználó a Skype Vállalati online verziót szeretné használni eszközén, a következő ellenőrzés megy végbe:

![Azokat a döntési pontokat bemutató diagram, amelyek segítségével a rendszer meghatározza, hogy az eszköz hozzáférhessen-e a Skype Vállalati online verzióhoz](../media/ConditionalAccess_SkypeforBusiness.png)

**Mielőtt** beállítaná a Skype Vállalati online verzióra vonatkozó feltételes hozzáférési szabályzatot, a következőknek kell teljesülniük:
- Rendelkeznie kell **Skype Vállalati online verzió-előfizetéssel**, valamint ki kell osztania a Skype Vállalati online verzió licenceit a felhasználóknak.
- Rendelkeznie kell **Enterprise Mobility + Security (EMS) előfizetéssel** vagy **Azure Active Directory (Azure AD) Premium előfizetéssel**, és a felhasználóknak is licenccel kell rendelkezniük az EMS-hez vagy az Azure AD-hoz. Részletesebb tájékoztatást az [Enterprise Mobility díjszabását](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását ismertető lapon](https://azure.microsoft.com/pricing/details/active-directory/) talál.

-   [Engedélyeznie kell a modern hitelesítést](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) a Skype Vállalati online verzióhoz.
-  Minden végfelhasználónak a **Skype Vállalati online verziót** kell használnia. Amennyiben a telepítésben Skype Vállalati online verzió és helyi Skype Vállalati verzió is szerepel, a rendszer nem alkalmazza a feltételes hozzáférési szabályzatot a felhasználókra.

A Skype Vállalati online verzióhoz hozzáférést igénylő eszközre vonatkozóan a következőknek kell teljesülniük:

-   Az eszköz legyen **Android** vagy **iOS** rendszerű.

-   Az Intune-nal **regisztrálva** kell lennie.

-   Meg kell felelnie az Intune összes telepített **megfelelőségi** szabályzatának.


Az eszköz állapotát a rendszer az Azure Active Directoryban tárolja, amely a megadott feltételek alapján engedélyezi vagy letiltja a hozzáférést.

Ha egy feltétel nem teljesül, a felhasználó számára az alábbi üzenetek egyike jelenik meg a bejelentkezéskor:

-   Ha az eszköz nincs regisztrálva az Intune-ban vagy az Azure Active Directoryban, megjelenik egy üzenet, amely leírja, hogyan kell telepítenie a Vállalati portál alkalmazást és regisztrálnia az eszközt.

-   Ha az eszköz nem megfelelő, egy üzenet jelenik meg, amely az Intune vállalati portálra vagy a Céges portál alkalmazásba irányítja a felhasználót, ahol további információt talál a problémáról, és annak megoldásáról.

## <a name="configure-conditional-access-for-skype-for-business-online"></a>A Skype Vállalati online verzió feltételes elérésének beállítása

### <a name="step-1-configure-azure-active-directory-security-groups"></a>1. lépés: Az Azure Active Directory-alapú biztonsági csoportok beállítása
Kezdés előtt állítsa be az Azure Active Directory-alapú biztonsági csoportokat a feltételes hozzáférési szabályzathoz. Ezeket a csoportokat az **Office 365 Felügyeleti központban** konfigurálhatja. A rendszer e csoportok alapján célozza meg a felhasználókat, illetve helyezi őket kivétel alá. Amikor egy felhasználóra szabályzat vonatkozik, az erőforrások eléréséhez az általa használt összes eszköznek meg kell felelnie a szabályzatnak.

A Skype Vállalati verziójára vonatkozó szabályzatban két csoporttípust határozhat meg:

-   **Megcélzott csoportok**: Azokat a felhasználói csoportokat tartalmazza, amelyekre a szabályzat vonatkozik.

-   **Kivétel alá eső csoportok**: A szabályzat alól mentesülő felhasználók csoportjait tartalmazza.

Ha egy felhasználó mindkét csoportban szerepel, mentesül a házirend alól.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>2. lépés: Megfelelőségi szabályzat konfigurálása és telepítése
[Hozzon létre](create-a-device-compliance-policy-in-microsoft-intune.md) és [telepítsen](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) megfelelőségi szabályzatot a szabályzat hatálya alá eső összes eszközre. Ez minden olyan eszközre értendő, amelyet a **Megcélzott csoportok** csoporthoz tartozó felhasználók használnak.

> [!NOTE]
> A megfelelőségi szabályzatok a Microsoft Intune csoportjaira vonatkoznak, a feltételes hozzáférési szabályzatok viszont az Azure Active Directory biztonsági csoportjait célozzák meg.


> [!IMPORTANT]
> Amennyiben nem telepített megfelelőségi szabályzatot, a rendszer megfelelőként fogja értékelni az eszközöket.

Ha készen áll, folytassa a **3. lépéssel**.

### <a name="step-3-configure-the-skype-for-business-online-policy"></a>3. lépés: A Skype Vállalati online verzióra vonatkozó szabályzat beállítása
Ezután állítsa be úgy a szabályzatot, hogy csak a felügyelt és a feltételeknek megfelelő eszközök érhessék el a Skype Vállalati online verziót. A szabályzat ezek után az Azure Active Directoryban tárolódik.

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Házirend** > **Feltételes hozzáférés** > **A Skype Vállalati online verzió szabályzata** lehetőségre.

  ![A Skype Vállalati online verzió feltétes hozzáférési szabályzatának oldaláról készült képernyőkép](./media/conditional_access_SFBPolicy.png)

2.  Válassza a **Feltételes hozzáférési szabályzat engedélyezése** lehetőséget.

3.  Az **Alkalmazás hozzáférése**szakaszban kiválaszthatja, hogy mire szeretné alkalmazni a feltételes hozzáférési szabályzatot:

    -   **iOS**

    -   **Android--**

4.  A **Megcélzott csoportok** területen kattintson a **Módosítás** lehetőségre azon Active Directorybeli biztonsági csoportok kiválasztásához, amelyekre érvényes a szabályzat. Kiválaszthatja, hogy a szabályzat minden felhasználóra, vagy csak felhasználók bizonyos csoportjaira vonatkozzon.

5.  A **Kivétel alá eső csoportok**területen kattintson a **Módosítás** lehetőségre azon Active Directory-alapú biztonsági csoportok kiválasztásához, amelyekre nem érvényes a szabályzat.

6.  Ha elkészült, válassza a **Mentés** elemet.

Ezzel elvégezte a Skype Vállalati online verzió feltételes elérésének beállítását. Nem kell telepítenie a feltételes hozzáférési szabályzatot, az azonnal érvénybe lép.


## <a name="monitor-the-compliance-and-conditional-access-policies"></a>A megfelelőség és a feltételes hozzáférési házirendek megfigyelése
A **Csoportok** munkaterületen megtekintheti eszközei feltételes hozzáférési állapotát.

Válassza ki a kívánt mobileszközök csoportját. Majd az **Eszközök** lapon válasszon az alábbi **Szűrők** közül:

* **Az AAD-ben nem regisztrált eszközök** – Ezeknek az eszközöknek nincs hozzáférésük a Skype Vállalati online verzióhoz.

* **Nem megfelelő eszközök** – Ezeknek az eszközöknek nincs hozzáférésük a Skype Vállalati online verzióhoz.

* **Az AAD-ben regisztrált és megfelelő eszközök** – Ezek az eszközök hozzáférhetnek a Skype Vállalati online verzióhoz.
