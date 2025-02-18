---
title: Alkalmazások előkészítése mobilalkalmazás-kezeléshez a Microsoft Intune-nal
description: Az ebben a témakörben leírtak segítenek eldönteni, mikor használja az Alkalmazásburkoló eszközt és az App SDK-t arra, hogy engedélyezze az egyéni, üzletági alkalmazások számára a mobilalkalmazás-kezelési szabályzatok használatát.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3addd79b20c685c5643a2b99fb7120e958cdecb
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394881"
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a>Üzletági alkalmazások felkészítése az alkalmazásvédelmi szabályzatok használatára

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Az Intune alkalmazásburkoló eszközével vagy az Intune App SDK-val engedélyezheti, hogy az alkalmazások alkalmazásvédelmi szabályzatokat használjanak. Az alábbi információkkal többet megtudhat erről a két módszerről és arról, mikor érdemes használni azokat.

## <a name="intune-app-wrapping-tool"></a>Intune alkalmazásburkoló eszköz
Az alkalmazásburkoló eszköz főleg **belső** üzletági (LOB) alkalmazásokhoz készült. Az eszköz egy parancssori alkalmazás, amely egy burkolót hoz létre az alkalmazás körül, amely lehetővé teszi az alkalmazás Intune alkalmazásvédelmi szabályzatokkal való kezelését. Egy független szoftverszállító (ISV) által biztosított alkalmazás védelme esetén fontos tisztázni, hogy az ISV támogatja-e a becsomagolt alkalmazást.

Nincs szüksége a forráskódra az eszköz használatához, de aláíró hitelesítő adatokra igen. További információ az aláíró hitelesítő adatokról: [Intune blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Az alkalmazásburkoló eszköz dokumentációja az [Android alkalmazásburkoló eszköz](app-wrapper-prepare-android.md) és az [iOS alkalmazásburkoló eszköz](app-wrapper-prepare-ios.md) című cikkekben található.

Az Alkalmazásburkoló eszköz **nem támogatja** az Apple App Store vagy a Google Play áruházban elérhető alkalmazásokat. Nem támogatja továbbá a szolgáltatásokat, amelyek fejlesztői integrációt igényelnek (lásd a következő szolgáltatás-összehasonlító táblázatot).

Az alkalmazásvédelmi szabályzatok támogatásához készült alkalmazásburkoló eszköznek az Intune-ban nem regisztrált eszközökön való használatáról [Az üzleti alkalmazások és az adatok védelme a Microsoft Intune-ban nem regisztrált eszközökön](apps-add.md) című témakor nyújt tájékoztatást.

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Mikor érdemes használni az Alkalmazásburkoló eszközt?
* Az alkalmazásban nincsenek beépített adatvédelmi funkciók
* Egyszerű az alkalmazás
* Az alkalmazás belső telepítésű
* Nincs hozzáférése az alkalmazás forráskódjához
* Másvalaki fejlesztette az alkalmazást
* Az alkalmazás csak minimális felhasználói hitelesítési felülettel rendelkezik

### <a name="supported-app-development-platforms"></a>Támogatott alkalmazásfejlesztési platformok

|**Alkalmazásburkoló eszköz** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Igen|Igen|
|**Android**|Nem – használja az [Intune App SDK Xamarin-kötéseket](app-sdk-xamarin.md).|Igen|

## <a name="intune-app-sdk"></a>Intune App SDK
Az App SDK főleg olyan ügyfeleknek készült, akiknek vannak az Apple App Store vagy a Google Play Store áruházban alkalmazásai, és az Intune-nal szeretnék kezelni az alkalmazásokat. De bármilyen alkalmazás kihasználhatja az SDK integrálásának előnyeit, még üzletági alkalmazások esetében is.

További információk az SDK-ról: [Áttekintés](app-sdk.md). Az SDK használatának megkezdéséhez olvassa el a [Bevezetés a Microsoft Intune App SDK használatába](app-sdk-get-started.md) című szakaszt.

### <a name="reasons-to-use-the-sdk"></a>Az SDK használatának előnyei
* Az alkalmazásban nincsenek beépített adatvédelmi funkciók
* Az alkalmazás összetett és számos felületet tartalmaz
* Az alkalmazás nyilvános alkalmazás-áruházból, például a Google Play vagy az Apple App Store áruházból telepíthető
* Ön alkalmazásfejlesztő, és rendelkezik az SDK használatához szükséges technikai tudással
* Az alkalmazás más SDK-integrációkkal rendelkezik
* Az alkalmazás gyakran frissül

### <a name="supported-app-development-platforms"></a>Támogatott alkalmazásfejlesztési platformok

|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Igen – használja az [Intune App SDK Xamarin-kötéseket](app-sdk-xamarin.md).|Nem|
|**Android**| Igen – használja az [Intune App SDK Xamarin-kötéseket](app-sdk-xamarin.md).|Nem|

## <a name="feature-comparison"></a>Szolgáltatások összehasonlítása
Ez a táblázat az App SDK-hoz és az alkalmazásburkoló eszközhöz használható beállításokat sorolja fel.

> [!NOTE]
> Az alkalmazásburkoló használható a különálló Intune-nal és a Configuration Managerrel kombinált Intune-nal is.

|Funkció|App SDK|Alkalmazásburkoló eszköz|
|-----------|---------------------|-----------|
|A vállalat által kezelt böngészőben megjelenő webtartalom korlátozása|X|X|
|Android-, iTunes- vagy iCloud-biztonságimentések megakadályozása|X|X|
|Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak|X|X|
|Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak|X|X|
|Más alkalmazásokkal végzett kivágás, másolás és beillesztés korlátozása|X|X|
|Adja meg, amely kivágott vagy másolt a kezelt alkalmazások karakterek száma|X|X|
|Egyszerű PIN-kód szükséges a hozzáféréshez|X|X|
|A PIN-kód alaphelyzetbe állítása előtti kísérletek számának megadása|X|X|
|Ujjlenyomat használatának engedélyezése PIN-kód helyett|X|X|
|Arcfelismerés használatának engedélyezése PIN-kód helyett (csak iOS)|X|X|
|Vállalati hitelesítő adatok szükségesek a hozzáféréshez|X|X|
|A felügyelt alkalmazások futtatásának tiltása jailbreakelt vagy rootolt eszközökön|X|X|
|Alkalmazásadatok titkosítása|X|X|
|A hozzáférési követelmények ismételt ellenőrzése a megadott számú percek után|X|X|
|Az offline türelmi időszak megadása|X|X|
|Képernyőrögzítés letiltása (csak Android esetén)|X|X|
|Eszközregisztráció nélküli MAM támogatása|X|X|
|Az alkalmazás adatainak teljes törlése|X|X|
|Többidentitásos környezetben a munkahelyi és iskolai adatok szelektív törlése <br><br>**Megjegyzés:** IOS-a felügyeleti profil törlésekor az alkalmazás is eltávolítja.|X||
|A „Mentés másként” művelet letiltása|X||
|Célzott alkalmazáskonfiguráció|X||
|Többszörös identitás támogatása|X||
|Testreszabható stílus |X|||
|Igény szerinti VPN-alkalmazáskapcsolatok Citrix mVPN segítségével|X|X| 
|Névjegy-szinkronizálás letiltása|X|X|
|Nyomtatás letiltása|X|X|
|Az alkalmazás minimális verziójának megkövetelése|X|X|
|Operációs rendszer minimális verziójának megkövetelése (iOS és Android)|X|X|
|Minimális Android biztonsági javítási szint megkövetelése (csak Android)|X|X|
|Minimális iOS Intune SDK-verzió megkövetelése (csak iOS)|X|X|

## <a name="next-steps"></a>További lépések

A következő témakörökből tudhat meg többet az alkalmazásvédelmi szabályzatokról és az Intune-ról:

  - [Android alkalmazásburkoló eszköz](app-wrapper-prepare-android.md)<br>
  - [iOS alkalmazásburkoló eszköz](app-wrapper-prepare-ios.md)<br>
  - [Alkalmazások előkészítése a mobilalkalmazás-felügyeletre az SDK segítségével](app-sdk.md)
