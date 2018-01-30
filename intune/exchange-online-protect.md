---
title: "Az Office 365 Exchange Online védelmének biztosítása eszközkezelés megkövetelése nélkül"
description: "Hozzáférést biztosít az alkalmazottaknak a munkahelyi e-mail-címükhöz. Nincs szükség eszközkezelésre."
keywords: "Office 365 Exchange e-mail-hozzáférés"
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 53872921bc4c7a52224741ab3b743a1d9ac52f42
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Az Office 365 Exchange Online védelmének biztosítása eszközkezelés megkövetelése nélkül

Ha az eszközkezelési rendszer kiépítésével járó többletterhek nélkül szeretne az alkalmazottaknak hozzáférést biztosítani a munkahelyi e-mail-címükhöz, erre van lehetősége. Az Intune-on keresztül biztosíthat hozzáférést az Office 365 Exchange Online szolgáltatáshoz. A szükséges lépések elvégzéséhez erősítse meg, hogy rendelkezik Microsoft 365- , illetve (prémium szintű) Azure Active Directory- és Intune-licenccel. Az alkalmazottaknak [támogatott iOS- vagy Android-eszközökkel](supported-devices-browsers.md) kell rendelkezniük. 

Ha az eszközkezelő rendszer kiépítése mellett dönt, erre van lehetősége. Az ilyen típusú alkalmazásvédelem ugyanis eszközkezeléstől függetlenül is működik. 

## <a name="action-plan"></a>Műveletterv

1. [További információ a feltételes hozzáférésről](conditional-access.md). 
2. [További információ az alkalmazásalapú feltételes hozzáférésről](app-based-conditional-access-intune.md).
3. [Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása az Exchange Online-hoz](app-based-conditional-access-intune-create.md).
4. [Letilthatja a nem felügyelhető alkalmazásokat](app-modern-authentication-block.md), különösen azokat, amelyek nem használják az Azure Active Directory Authentication Libraryt (ADAL).
5. (Nem kötelező) [Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása a SharePoint Online-hoz](app-based-conditional-access-intune-create.md). Ezekkel a szabályzatokkal letiltható a céges adatokhoz való hozzáférés azokból az alkalmazásokból, amelyek felügyelete és védelme nem biztosítható. A szabályzatok emellett korlátozzák a SharePoint mobile alkalmazáson keresztüli hozzáférést is. 

## <a name="what-to-tell-employees-and-students"></a>Miről kell tájékoztatni az alkalmazottakat és a tanulókat?

* Kérje meg az alkalmazottakat és a tanulókat arra, hogy töltsék le és telepítsék a Microsoft Outlookot vagy a Microsoft SharePointot iOS rendszeren az Apple App Store áruházból, Androidon pedig a Google Play Áruházból. 
* Ha le van tiltva a modern hitelesítést nem használó alkalmazásokhoz való hozzáférés, hívja fel az alkalmazottak és a tanulók figyelmét erre a korlátozásra. 

## <a name="next-steps"></a>További lépések

Alkalmazásalapú feltételes hozzáférést használt a céges adatok biztonságának növeléséhez. A következő lépések részeként további információhoz juthat azokról az egyéb módszerekről, melyekkel növelhető a céges adatok védelme, beleértve a következőket: 

* [Az eszközmegfelelőségen, eszközkockázaton, helyen, valamint az Active Directoryban és az Azure Active Directoryban lévő felhasználói attribútumokon alapuló feltételes hozzáférés](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) beállítása.  
* Az alkalmazásvédelmi szabályzatok beállításával biztosíthatja a céges adatok szándékos vagy véletlen adatszivárgással szembeni védelmét. 
* Az Azure Information Protection használatával biztosíthatja a hálózaton kívüli céges adatok védelmét. 

Segítségre van szüksége ennek, illetve az egyéb EMS- vagy Office 365-forgatókönyvek lehetővé tételéhez? Ha legalább 150 Microsoft 365- , Enterprise Mobility + Security- vagy Prémium szintű Azure Active Directory-licenccel rendelkezik, használja [FastTrack-juttatásait](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 