---
title: "Alkalmazásalapú feltételes hozzáférés az Intune-nal"
description: "Az Intune alkalmazásalapú feltételes hozzáférésének ismertetése."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f3a3104c4381028cca69ba3e129f4a30287a8e32
ms.sourcegitcommit: 42a0e4c83e33c1a25506ca75d673e861e9206945
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2017
---
# <a name="app-based-conditional-access-with-intune"></a>Alkalmazásalapú feltételes hozzáférés az Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az [Intune alkalmazásvédelmi szabályzataival](app-protection-policy.md) védheti vállalati adatait az Intune-ban regisztrált eszközökön. Az alkalmazásvédelmi szabályzatokat emellett a munkatársak tulajdonában álló, az Intune-ban felügyeletre nem regisztrált eszközökön is alkalmazhatja. Bár ebben az esetben nem a cég felügyeli az eszközt, mégis fontos, hogy a vállalati adatok és erőforrások védve legyenek.

Az alkalmazásalapú feltételes hozzáférés és a mobileszköz-felügyelet egy biztonsági réteget ad hozzá annak biztosításával, hogy csak az Intune alkalmazásvédelmi szabályzatait támogató mobilalkalmazások férhessenek hozzá az Exchange Online-hoz és más Office 365-szolgáltatásokhoz.

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

Az alkalmazásalapú feltételes hozzáférés [üzletági (LOB-) alkalmazásokkal is használható](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), de ezeknek az [Office 365 modern hitelesítését](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) kell használniuk.

## <a name="how-app-based-conditional-access-works"></a>Az alkalmazásalapú feltételes hozzáférés működése

Ebben a példában a rendszergazda alkalmazásvédelmi szabályzatokkal látta el az Outlook alkalmazást, majd egy feltételes hozzáférési szabállyal felvette az Outlookot a céges levelezés elérésére használható jóváhagyott alkalmazások listájára.

> [!NOTE]
> Az alábbi folyamatábra-struktúra más felügyelt alkalmazásokhoz is használható.

![Folyamatábra: alkalmazásalapú feltételes hozzáférés az Intune-nal](./media/ca-intune-common-ways-3.png)

1.  A felhasználó az Outlook alkalmazásból hitelesítést próbál végezni az Azure AD-val.

2.  A felhasználó az első hitelesítési kísérletkor átirányítódik az alkalmazás-áruházba, ahonnan közvetítő alkalmazást kell telepítenie. Ez lehet az iOS-es Microsoft Authenticator vagy az androidos eszközökre készült Microsoft Intune vállalati portál.

 Ha egy felhasználó natív levelezőalkalmazást próbál használni, a rendszer az alkalmazásáruházba irányítja át, hogy telepíthesse az Outlookot.

3.  A közvetítő alkalmazás települ az eszközre.

4.  A közvetítő alkalmazás megkezdi az Azure AD regisztrációs folyamatát, amely eszközrekordot hoz létre az Azure AD-ben. Ez nem azonos a mobileszköz-felügyelet (MDM) beléptetési folyamatával, de erre a rekordra is szükség van, hogy a feltételes hozzáférési szabályzatokat be lehessen tartatni az eszközön.

5.  A közvetítő alkalmazás ellenőrzi az alkalmazás identitását. A közvetítő alkalmazás a biztonsági rétegnek köszönhetően képes ellenőrizni, hogy az alkalmazás engedélyezett-e a felhasználó számára.

6.  A közvetítő alkalmazás a felhasználó-hitelesítési folyamat keretében elküldi az alkalmazás ügyfél-azonosítóját az Azure AD-nek, amely ellenőrzi, hogy szerepel-e a szabályzat engedélyezési listáján.

7.  Az Azure AD a szabályzat engedélyezési listája alapján engedélyezi a felhasználónak a hitelesítést és az alkalmazás használatát. Ha az alkalmazás nem szerepel a listán, az Azure AD nem engedélyezi az elérését.

8.  Az Outlook alkalmazás az Outlook felhőszolgáltatással kapcsolatba lépve kezdeményezi az Exchange Online-nal való kommunikációt.

9.  Az Outlook felhőszolgáltatás az Azure AD-vel kommunikálva lekér egy Exchange Online-szolgáltatás-hozzáférési jogkivonatot a felhasználó részére.

10.  Az Outlook alkalmazás az Exchange Online-nal kommunikálva lekéri a felhasználó céges e-mailjeit.

11.  A céges e-mailek kézbesítődnek a felhasználó postafiókjába.

## <a name="next-steps"></a>További lépések
[Alkalmazásalapú feltételes hozzáférési szabályzat létrehozása](app-based-conditional-access-intune-create.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](app-modern-authentication-block.md)
