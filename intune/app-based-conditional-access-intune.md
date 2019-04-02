---
title: Alkalmazásalapú feltételes hozzáférés az Intune-nal
titleSuffix: Microsoft Intune
description: Megtudhatja, hogyan működik az Intune alkalmazásalapú feltételes hozzáférése.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/11/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b4c39a1d95a10c96b8f34703f99c4d8414efbbf0
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798279"
---
# <a name="app-based-conditional-access-with-intune"></a>Alkalmazásalapú feltételes hozzáférés az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az [Intune alkalmazásvédelmi szabályzataival](app-protection-policy.md) védheti vállalati adatait az Intune-ban regisztrált eszközökön. Az alkalmazásvédelmi szabályzatokat emellett a munkatársak tulajdonában álló, az Intune-ban felügyeletre nem regisztrált eszközökön is alkalmazhatja. Bár ebben az esetben nem a cég felügyeli az eszközt, mégis fontos, hogy a vállalati adatok és erőforrások védve legyenek.

Az alkalmazásalapú feltételes hozzáférés és az ügyfélalkalmazás-felügyelet egy további biztonsági réteget jelent, mivel gondoskodik róla, hogy csak az Intune alkalmazásvédelmi szabályzatait támogató mobilalkalmazások férhessenek hozzá az Exchange Online-hoz és más Office 365-szolgáltatásokhoz.

> [!NOTE]
> A felügyelt alkalmazásra alkalmazásvédelmi szabályzatok vonatkoznak, és az Intune-nal felügyelhető.

Azzal, hogy csak a Microsoft Outlook alkalmazásnak engedélyezi az Exchange Online elérését, blokkolhatja az iOS és az Android beépített levelezőalkalmazásait. Ezenfelül blokkolhatja az Intune alkalmazásvédelmi szabályzattal el nem látott alkalmazások SharePoint Online-elérését is.

## <a name="prerequisites"></a>Előfeltételek
Alkalmazásalapú feltételes hozzáférési szabályzat létrehozásához az alábbiak szükségesek:

- **Enterprise Mobility + Security (EMS)** vagy **Prémium szintű Azure Active Directory- (AD-) előfizetés**
- EMS- vagy Azure AD-licenc a felhasználók számára

További információt az [Enterprise Mobility díjszabását](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását](https://azure.microsoft.com/pricing/details/active-directory/) ismertető lapon talál.

## <a name="supported-apps"></a>Támogatott alkalmazások

Az alkalmazásalapú feltételes hozzáférést támogató alkalmazások listája az [Azure Active Directory feltételes hozzáférésének technikai dokumentációjában](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference) érhető el.

Az alkalmazásalapú feltételes hozzáférés [üzletági (LOB-) alkalmazásokkal is használható](app-modern-authentication-block.md), de ezeknek az [Office 365 modern hitelesítését](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) kell használniuk. 

## <a name="how-app-based-conditional-access-works"></a>Az alkalmazásalapú feltételes hozzáférés működése

Ebben a példában a rendszergazda alkalmazásvédelmi szabályzatokkal látta el az Outlook alkalmazást, majd egy feltételes hozzáférési szabállyal felvette az Outlookot a céges levelezés elérésére használható jóváhagyott alkalmazások listájára.

> [!NOTE]
> Az alábbi folyamatábra-struktúra más felügyelt alkalmazásokhoz is használható.

![Az alkalmazásalapú feltételes hozzáférés folyamata egy folyamatábrán bemutatva](./media/ca-intune-common-ways-3.png)

1. A felhasználó az Outlook alkalmazásból hitelesítést próbál végezni az Azure AD-val.

2. A felhasználó az első hitelesítési kísérletkor átirányítódik az alkalmazás-áruházba, ahonnan közvetítő alkalmazást kell telepítenie. Ez lehet az iOS-es Microsoft Authenticator vagy az androidos eszközökre készült Microsoft Intune vállalati portál.

   Ha egy felhasználó natív levelezőalkalmazást próbál használni, a rendszer az alkalmazásáruházba irányítja át, hogy telepíthesse az Outlookot.

3. A közvetítő alkalmazás települ az eszközre.

4. A közvetítő alkalmazás megkezdi az Azure AD regisztrációs folyamatát, amely eszközrekordot hoz létre az Azure ad-ben. Ez nem ugyanaz, mint a mobileszköz-felügyelet (MDM) beléptetési folyamatot, de ez a rekord szükség, hogy a feltételes hozzáférési szabályzatokat be lehessen tartatni az eszközön.

5. A közvetítő alkalmazás ellenőrzi az alkalmazás identitását. Egy biztonsági réteget van, a közvetítő alkalmazás érvényesíthessük, ha az alkalmazás a felhasználó által engedélyezett való használatra.

6. A közvetítő alkalmazás a felhasználó-hitelesítési folyamat keretében elküldi az alkalmazás ügyfél-azonosítóját az Azure AD-nek, amely ellenőrzi, hogy szerepel-e a szabályzat engedélyezési listáján.

7. Az Azure AD a szabályzat engedélyezési listája alapján engedélyezi a felhasználónak a hitelesítést és az alkalmazás használatát. Ha az alkalmazás nem szerepel a listában, az Azure AD megtagadja a hozzáférést az alkalmazáshoz.

8. Az Outlook alkalmazás az Outlook felhőszolgáltatással kapcsolatba lépve kezdeményezi az Exchange Online-nal való kommunikációt.

9. Az Outlook felhőszolgáltatás az Azure AD-vel kommunikálva lekér egy Exchange Online-szolgáltatás-hozzáférési jogkivonatot a felhasználó részére.

10. Az Outlook alkalmazás az Exchange Online-nal kommunikálva lekéri a felhasználó céges e-mailjeit.

11. A céges e-mailek kézbesítődnek a felhasználó postafiókjába.

## <a name="next-steps"></a>További lépések
[Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása](app-based-conditional-access-intune-create.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](app-modern-authentication-block.md)
