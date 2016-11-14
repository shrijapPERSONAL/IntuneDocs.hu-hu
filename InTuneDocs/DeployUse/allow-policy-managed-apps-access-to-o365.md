---
title: "Alkalmazás alapú feltételes hozzáférés az 0365-höz | Microsoft Intune"
description: "Ismerje meg, a MAM feltételes hozzáférés miként tud segíteni abban, hogy mely alkalmazások férhessenek hozzá az O365 szolgátasaihoz."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Hozzon létre egy olyan házirendet, amely csak azokat a mobilalkalmazásokat engedi hozzáférni az O365 szolgátasaihoz, amelyek támogatják az Intune MAM-szabályzatokat
Az [Intune mobilalkalmazás-felügyeleti (MAM) szabályzatok](protect-apps-and-data-with-microsoft-intune.md) segítségével védheti vállalati adatait az Intune-ban regisztrált és felügyelt eszközökön. A MAM-szabályzatokat emellett olyan eszközökön is alkalmazhatja, amelyek **a munkatársak tulajdonában állnak, és amelyek nincsenek az Intune-ban felügyeletre regisztrálva**.  Jóllehet ebben az esetben nem felügyeli az eszközt, mégis fontos, hogy a vállalati adatok és erőforrások védettek legyenek. A MAM feltételes hozzáférés (MAM CA) segítségével létrehozhat egy olyan szabályzatot, amely csak az Intune MAM-szabályzatokat támogató mobilalkalmazásokat engedi hozzáférni az O365 szolgáltatásokhoz, például az Exchange Online-hoz.

Például ha csak a **Microsoft Outlook alkalmazást** engedélyezi hozzáférni az Exchange Online-hoz, **blokkolhatja azokat a beépített levelezőalkalmazásokat iOS-en és Androidon**, amelyek nem rendelkeznek az Intune MAM-szabályzatok adatvédelmével, hogy levelezést az **Exchange Online-on** folytathassa.

## Előfeltételek
**Mielőtt** konfigurálhatna egy MAM feltételes hozzáférés szabályzatot, rendelkeznie kell **Enterprise Mobility + Security vagy Azure Active Directory Premium szintű előfizetéssel**, és a felhasználóknak licenccel kell rendelkezniük az EMS-hez vagy az Azure AD-hoz. Részletesebb tájékoztatást az [Enterprise Mobility díjszabását](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) vagy az [Azure Active Directory díjszabását ismertető lapon](https://azure.microsoft.com/en-us/pricing/details/active-directory/) talál.


## Támogatott alkalmazások
**Exchange Online**
* Microsoft Outlook Androidhoz és iOS-hez

## Átfedések más feltételes hozzáférési és hitelesítési módszerekkel
### A MAM feltételes hozzáférés az Azure Active Directory tanúsítványalapú hitelesítéssel

A MAM feltételes hozzáférést tilos az Azure Active Directory (Azure AD) tanúsítványalapú hitelesítéssel használni. A fentiek közül csak az egyik lehet egyszerre konfigurálva.
### A MAM feltételes hozzáférés és az eszköz megfelelőségén alapuló feltételes hozzáférés  

Az [eszköz megfelelőségén alapuló feltételes hozzáférést](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Eszköz CA**) az [Intune felügyeleti konzolon](https://manage.microsoft.com) vagy az [Azure AD Premium felügyeleti konzolon (https://manage.windowsazure.com) konfigurálhatja. Az eszköz megfelelőségén alapuló feltételes hozzáférés előírja, hogy a felhasználók csak az Intune által felügyelt, az Intune eszközmegfelelőségi szabályzatának megfelelő eszközökkel vagy tartományhoz csatlakozó számítógéppel csatlakozzanak az Exchange Online-hoz.  Ha egy felhasználó egy vagy több biztonsági csoport tagja, amelyekre vonatkozik a MAM feltételes hozzáférés vagy eszköz megfelelőségén alapuló feltételes hozzáférés szabályzat, akkor az alábbi két előírás egyikének teljesülnie kell:
* A szolgáltatáshoz való hozzáférésre használt alkalmazás a MAM feltételes hozzáférés által támogatott mobilalkalmazás, és az eszközre, amelyen ez az alkalmazás fut, telepítve van az **iOS Authenticator (iOS-eszköz esetén)** vagy a **Vállalati portál alkalmazás (Android-eszköz esetén)**.
* A szolgáltatáshoz való hozzáférésre használt eszköz az **Intune által van felügyelve, és megfelel** az Intune eszközmegfelelőségi szabályzatának, vagy az eszköz egy **tartományhoz csatlakozó számítógép**.  Álljon itt néhány példa ennek illusztrálására:
  * Amennyiben a felhasználó **natív iOS levelezőalkalmazásról** szeretne kapcsolódni, **felügyelt és megfelelő eszközzel** kell tennie azt, ugyanis a natív levelezőalkalmazást nem támogatja a MAM feltételes hozzáférés.
  * Ha a felhasználó **Windowst futtató otthoni számítógépről** csatlakozik, az **eszköz megfelelőségén alapuló feltételes hozzáférés** alkalmazandó, amely előírja, a felhasználónak, hogy tartományhoz csatlakozó számítógépet kell használnia.


## Mire számítson, ha egy alkalmazást a MAM feltételes hozzáféréssel használ?
A MAM feltételes hozzáférés közvetítésalkalmazással – amelynek az eszközön kell lennie – ellenőrzi az engedélyezett alkalmazás identitását:
*  **iOS** esetén a közvetítőalkalmazás az **Azure Authenticator alkalmazás**.
* **Android** esetén a közvetítőalkalmazás az **Intune Vállalati portál alkalmazás**. 

A MAM feltételes hozzáférés által támogatott alkalmazásba, például a OneDrive-ba vagy az Outlookba először bejelentkező végfelhasználónak le kell töltenie a közvetítőalkalmazást és regisztrálnia kell az eszközt Azure AD-ben. Az Azure AD-ba történő eszközregisztráció (korábban Munkahelyi csatlakoztatás) eszközrekordot és tanúsítványt hoz létre, amelyek ellenében jogkivonatokat állítanak ki.  Ez **nem** ugyanaz, mint az **MDM-regisztráció**. Nincsenek alkalmazott felügyelt profilok vagy szabályzatok, és nincs az eszközön található alkalmazásokról sem leltár.  A közvetítőalkalmazás telepítése és az eszköz regisztrálása csak a felügyelt alkalmazás első használatakor történik meg.


## További lépések
[Exchange Online-szabályzat létrehozása MAM-alkalmazásokhoz](mam-ca-for-exchange-online.md)

[Modern hitelesítés nélküli alkalmazások blokkolása](block-apps-with-no-modern-authentication.md)

### További információ

[Alkalmazásadatok védelme MAM-szabályzatok használatával](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


