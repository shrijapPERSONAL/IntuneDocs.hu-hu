---
title: "Alkalmazások előkészítése mobilalkalmazás-kezeléshez | Microsoft Intune"
description: "Az ebben a témakörben leírtak segítenek eldönteni, mikor használja az Alkalmazásburkoló eszközt és az App SDK-t arra, hogy engedélyezze az egyéni, üzletági alkalmazások számára a mobilalkalmazás-kezelési szabályzatok használatát."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 977716dd821bf9c487db199b57130c432b008a12


---

# <a name="decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune"></a>Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal
Az Intune alkalmazásburkoló eszközével vagy az Intune App SDK-val engedélyezheti, hogy az alkalmazások mobilalkalmazás-felügyeleti (MAM) szabályzatokat használjanak. Az alábbi információkkal többet megtudhat erről a két módszerről és arról, mikor érdemes használni azokat.

## <a name="intune-app-wrapping-tool"></a>Intune alkalmazásburkoló eszköz
Az alkalmazásburkoló eszköz főleg belső üzletági (LOB) alkalmazásokhoz készült. Az eszköz egy parancssori alkalmazás, amely egy burkolót hoz létre az alkalmazás körül, az pedig azután lehetővé teszi az alkalmazásnak az Intune mobilalkalmazás-kezelési szabályzatokkal való kezelését.

Nincs szüksége a forráskódra az eszköz használatához, de aláíró hitelesítő adatokra igen.  További információ az aláíró hitelesítő adatokról: [Intune blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Az alkalmazásburkoló eszköz dokumentációja az [Android alkalmazásburkoló eszköz](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) és az [iOS alkalmazásburkoló eszköz](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) című cikkekben található.

Az Alkalmazásburkoló eszköz **nem támogatja** az Apple App Store vagy a Google Play áruházban elérhető alkalmazásokat. Nem támogatja továbbá a szolgáltatásokat, amelyek fejlesztői integrációt igényelnek (lásd a következő szolgáltatás-összehasonlító táblázatot).


A MAM alkalmazásburkoló eszköznek az Intune-ban nem regisztrált eszközökön való használatáról [Az üzleti alkalmazások és az adatok védelme a nem regisztrált eszközökön a Microsoft Intune-ban című](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) cikk nyújt tájékoztatást.

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

További információk az SDK-ról: [Áttekintés](/intune/develop/intune-app-sdk). Az SDK használatának megkezdéséhez olvassa el a [Bevezetés a Microsoft Intune App SDK használatába](/intune/develop/intune-app-sdk-get-started) című szakaszt.

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
|**iOS**|Igen – használja az [Intune App SDK Xamarin összetevőt](/../develop/intune-app-sdk-xamarin).|Igen – használja az [Intune App SDK Cordova beépülő modult](/../develop/intune-app-sdk-cordova).|
|**Android--**| Igen – használja az [Intune App SDK Xamarin összetevőt](/../develop/intune-app-sdk-xamarin).|Igen – használja az [Intune App SDK Cordova beépülő modult](/../develop/intune-app-sdk-cordova).|

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
|Teljes törlés|X|X|
|Szelektív törlés <br></br>**Megjegyzés:** iOS esetén a felügyeleti profil törlésekor az alkalmazást is törli.|X||
|A „Mentés másként” művelet letiltása |X||
|Többszörös identitás támogatása|X||
|Eszközregisztráció nélküli MAM támogatása|X|X|
|Testreszabható stílus |X|||
### <a name="see-also"></a>További információ

[Android alkalmazásburkoló eszköz](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS alkalmazásburkoló eszköz](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Alkalmazások előkészítése a mobilalkalmazás-felügyeletre az SDK segítségével](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO5-->


