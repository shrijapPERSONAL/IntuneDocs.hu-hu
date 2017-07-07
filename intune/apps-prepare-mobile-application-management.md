---
title: "Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal"
description: "Az ebben a témakörben leírtak segítenek eldönteni, mikor használja az Alkalmazásburkoló eszközt és az App SDK-t arra, hogy engedélyezze az egyéni, üzletági alkalmazások számára a mobilalkalmazás-kezelési szabályzatok használatát."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8b218ce38a7e76135a62b1155dbf9060ba511cc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="prepare-line-of-business-apps-for-mam"></a>Üzletági alkalmazások előkészítése mobilalkalmazás-felügyelethez

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Az Intune alkalmazásburkoló eszközével vagy az Intune App SDK-val engedélyezheti, hogy az alkalmazások mobilalkalmazás-felügyeleti (MAM) szabályzatokat használjanak. Az alábbi információkkal többet megtudhat erről a két módszerről és arról, mikor érdemes használni azokat.

## <a name="intune-app-wrapping-tool"></a>Intune alkalmazásburkoló eszköz
Az alkalmazásburkoló eszköz főleg belső üzletági (LOB) alkalmazásokhoz készült. Az eszköz egy parancssori alkalmazás, amely egy burkolót hoz létre az alkalmazás körül, az pedig azután lehetővé teszi az alkalmazásnak az Intune mobilalkalmazás-kezelési szabályzatokkal való kezelését.

Nincs szüksége a forráskódra az eszköz használatához, de aláíró hitelesítő adatokra igen.  További információ az aláíró hitelesítő adatokról: [Intune blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Az alkalmazásburkoló eszköz dokumentációja az [Android alkalmazásburkoló eszköz](app-wrapper-prepare-android.md) és az [iOS alkalmazásburkoló eszköz](app-wrapper-prepare-ios.md) című cikkekben található.

Az Alkalmazásburkoló eszköz **nem támogatja** az Apple App Store vagy a Google Play áruházban elérhető alkalmazásokat. Nem támogatja továbbá a szolgáltatásokat, amelyek fejlesztői integrációt igényelnek (lásd a következő szolgáltatás-összehasonlító táblázatot).


A MAM alkalmazásburkoló eszköznek az Intune-ban nem regisztrált eszközökön való használatáról [Az üzleti alkalmazások és az adatok védelme a nem regisztrált eszközökön a Microsoft Intune-ban című](/intune-classic/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune) cikk nyújt tájékoztatást.

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Miért futtassa az alkalmazásburkoló eszközt?
* Az alkalmazásban nincsenek beépített adatvédelmi funkciók.
* Egyszerű az alkalmazása.
* Belső telepítésű az alkalmazása.
* Nincs hozzáférése az alkalmazás forráskódjához
* Nem ön fejlesztette az alkalmazást.
* Alkalmazása minimális felhasználói hitelesítési tapasztalattal rendelkezik.


### <a name="supported-app-development-platforms"></a>Támogatott alkalmazásfejlesztési platformok

|**Alkalmazásburkoló eszköz** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Igen|Igen|
|**Android--**| Nem |Igen|

## <a name="intune-app-sdk"></a>Intune App SDK
Az App SDK főleg olyan ügyfeleknek készült, akiknek vannak az Apple App Store vagy a Google Play Store áruházban alkalmazásai, és az Intune-nal szeretnék kezelni az alkalmazásokat. De bármilyen alkalmazás kihasználhatja az SDK integrálásának előnyeit, még üzletági alkalmazások esetében is.

További információk az SDK-ról: [Áttekintés](app-sdk.md). Az SDK használatának megkezdéséhez olvassa el a [Bevezetés a Microsoft Intune App SDK használatába](app-sdk-get-started.md) című szakaszt.

### <a name="reasons-to-use-the-sdk"></a>Az SDK használatának előnyei
* Az alkalmazásban nincsenek beépített adatvédelmi funkciók.
* Alkalmazása összetett és számos felületet tartalmaz.
* Alkalmazása nyilvános alkalmazás-áruházban telepített, például a Google Play-ben vagy az Apple App Store-ban.
* Ön alkalmazás-fejlesztő és rendelkezik az SDK felhasználásához szükséges technikai tudással.
* Alkalmazása más SDK-integrációkkal rendelkezik.
* Alkalmazása gyakran kerül frissítésre.

### <a name="supported-app-development-platforms"></a>Támogatott alkalmazásfejlesztési platformok

|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Igen – használja az [Intune App SDK Xamarin összetevőt](app-sdk-xamarin.md).|Igen – használja az [Intune App SDK Cordova beépülő modult](app-sdk-cordova.md).|
|**Android--**| Igen – használja az [Intune App SDK Xamarin összetevőt](app-sdk-xamarin.md).|Igen – használja az [Intune App SDK Cordova beépülő modult](app-sdk-cordova.md).|

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
|Kivágási, másolási és beillesztési műveletek korlátozása más alkalmazásokkal|X|X|
|Egyszerű PIN-kód szükséges a hozzáféréshez|X|X|
|Az alkalmazások beépített PIN-kódjának lecserélése Intune PIN-kóddal|X||
|A PIN-kód alaphelyzetbe állítása előtti kísérletek számának megadása|X|X|
|Ujjlenyomat használatának engedélyezése PIN-kód helyett |X|X|
|Vállalati hitelesítő adatok szükségesek a hozzáféréshez|X|X|
|A felügyelt alkalmazások futtatásának tiltása jailbreakelt vagy rootolt eszközökön|X|X|
|Alkalmazásadatok titkosítása|X|X|
|A hozzáférési követelmények ismételt ellenőrzése a megadott számú percek után|X|X|
|Az offline türelmi időszak megadása|X|X|
|Képernyőrögzítés letiltása (csak Android esetén)|X|X|
|Eszközregisztráció nélküli MAM támogatása|X|X|
|Teljes törlés|X|X|
|Szelektív törlés <br></br>**Megjegyzés:** iOS esetén a felügyeleti profil törlésekor az alkalmazást is törli.|X||
|A „Mentés másként” művelet letiltása |X||
|Célzott alkalmazáskonfiguráció |X||
|Többszörös identitás támogatása|X||
|Testreszabható stílus |X|||
### <a name="see-also"></a>További információ

[Android alkalmazásburkoló eszköz](app-wrapper-prepare-android.md)</br>
[iOS alkalmazásburkoló eszköz](app-wrapper-prepare-ios.md)</br>
[Alkalmazások előkészítése a mobilalkalmazás-felügyeletre az SDK segítségével](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
