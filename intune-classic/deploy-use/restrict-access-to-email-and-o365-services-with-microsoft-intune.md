---
title: "E-mailek és az Office 365 védelme"
description: "Ez a témakör azt ismerteti, hogyan használható a feltételes hozzáférés arra, hogy csak a megfelelő eszközök férhessenek hozzá a vállalati e-mailekhez, valamint a SharePoint Online-on és más szolgáltatásokban tárolt vállalati adatokhoz."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3405671130a58aa944d6c689264379a254face1d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>Az e-mailek, az Office 365- és egyéb szolgáltatások elérésének védelme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Enterprise Mobility + Security (EMS) feltételes hozzáférés használatával védheti a vállalati e-mailek és az Office 365-szolgáltatások, például a **Helyszíni Exchange**, az **Exchange Online**, a **Dedikált Exchange Online**, a **SharePoint Online**, a **Skype Vállalati online verzió** és más szolgáltatások elérését. Ez a funkció lehetővé teszi, hogy a vállalati e-mail- és Office 365-szolgáltatásokhoz csak olyan eszközök férhessenek hozzá, amelyek megfelelnek az Ön által az Intune rendszergazdai konzolján vagy a klasszikus Azure-portálon beállított szabályoknak.
## <a name="how-does-conditional-access-work"></a>Hogyan működik a feltételes hozzáférés?
A rendszer a megfelelőségi szabályok beállításai alapján ellenőrizheti az eszköz megfelelőségét. A feltételes hozzáférési szabályzat ennek az ellenőrzésnek az eredménye alapján engedélyezi vagy korlátozza a hozzáférést az adott szolgáltatásokhoz. A feltételes hozzáférési szabályzat és az eszközmegfelelőségi szabályzat együttes alkalmazásával elérheti, hogy a szolgáltatáshoz csak megfelelő eszközök férhessenek hozzá. A megfelelőségi szabályzat és a feltételes hozzáférési szabályzat telepítve van a felhasználónál. A rendszer minden olyan eszköz megfelelőségét ellenőrzi, amelyről a felhasználó használja a szolgáltatásokat.

> [!IMPORTANT]
> Ne feledje, hogy ahhoz, hogy a rendszer képes legyen az eszköz megfelelőségének ellenőrzésére, az eszközt használó felhasználóra vonatkozóan megfelelőségi szabályzatot kell alkalmazni.
> Amennyiben a felhasználóra nem vonatkozik megfelelőségi szabályzat, a rendszer megfelelőként kezeli az eszközt, és egyáltalán nem korlátozza a hozzáférést.

Ha az eszközök nem felelnek meg a szabályzatokban megadott feltételeknek, a rendszer végigvezeti a végfelhasználót az eszköz regisztrálásának és az eszköz kompatibilitását megakadályozó problémák megoldásának a folyamatán.

A feltételes hozzáférés jellemzően a következő folyamatot követi:

![Azokat a döntési pontokat megjelenítő diagram, amelyek segítségével a rendszer meghatározza, hogy hozzáférést kaphat-e az adott eszköz az adott szolgáltatáshoz](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a>Beállítási szempontok

### <a name="licensing"></a>Licencek

A Microsoft Intune és az Azure Active Directory (Azure AD) Premium tökéletes együttműködése több ellenőrzési réteget biztosít az EMS feltételes hozzáférés használatával. Ha az Intune-nal szeretne feltételes hozzáférési szabályzatokat érvénybe léptetni, akkor mindkét termékhez rendelkeznie kell licenccel.

Az **Azure AD Premium-licencek** megvásárolhatók önálló szolgáltatásként vagy (együtt az Intune-nal) az Enterprise-szerződés részeként. Ha az Intune-nal feltételes hozzáférési házirendeket léptetett érvénybe, akkor győződjön meg róla, hogy beszerezte a megfelelő Azure AD Premium- vagy **EMS-licenceket**.

- Részletesebb tájékoztatást az [Enterprise Mobility díjszabását](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását ismertető lapon](https://azure.microsoft.com/pricing/details/active-directory/) talál.

Továbbá győződjön meg arról, hogy azok a felhasználók, akikhez feltételes hozzáférési szabályzatokat szeretne hozzárendelni, [rendelkeznek Azure AD Premium- vagy EMS-licenccel](/intune/licenses-assign).

### <a name="device-compliance-settings"></a>Eszközmegfelelőségi beállítások

A feltételes hozzáférés beállításához állítson be eszközmegfelelőségi szabályzatot és feltételes hozzáférési szabályzatot. A megfelelőségi szabályzathoz többek között a következő beállítások tartoznak: PIN-kód, titkosítás, feltörték-e az eszközt. Ahhoz, hogy az eszközt a rendszer megfelelőnek értékelje, meg kell felelnie a szabályoknak.

- További tudnivalók az[eszközmegfelelőségi szabályzatokról és működésükről](introduction-to-device-compliance-policies-in-microsoft-intune.md).

### <a name="conditional-access-policy"></a>Feltételes hozzáférési szabályzat

A feltételes hozzáférési szabályzat segítségével a következők alapján védheti a hozzáférést:
- Az eszköz megfelelőségi állapota.
- A platform, amelyen az eszköz fut.
- A szolgáltatásokhoz való hozzáféréshez használt alkalmazások típusa.

Az Intune más szabályzataitól eltérően a feltételes hozzáférési szabályzatokat nem kell telepítenie. Elég konfigurálni a szabályzatot, kiválasztani, hogy mely felhasználókra vonatkozzon, és a rendszer már alkalmazza is a szabályzatot a megcélzott felhasználókra. Amikor egy felhasználóra házirend vonatkozik, az erőforrások eléréséhez az általa használt összes eszköznek meg kell felelnie a házirendnek.


## <a name="next-steps"></a>További lépések


2. [Eszközmegfelelőségi szabályzat létrehozása](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Feltételes hozzáférési szabályzat létrehozása a következők Microsoft-felhőszolgáltatás/-termék valamelyikéhez:

  - [Feltételes hozzáférési szabályzat létrehozása az Exchange Online-hoz](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a helyszíni Exchange-hez](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása az új Dedikált Exchange Online-hoz](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a régi Dedikált Exchange Online-hoz](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a SharePoint Online-hoz](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a Skype Vállalati online verziójához](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Feltételes hozzáférési szabályzat létrehozása a Dynamics CRM Online-hoz](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
