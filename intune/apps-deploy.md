---
title: Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-ban
titleSuffix: ''
description: Útmutató az Intune alkalmazás hozzárendelése csoportokhoz a felhasználók vagy eszközök Microsoft Intune-nal.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/24/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1db613f93e50caa377297e3873f6817a39714fe7
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799565"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Miután [hozzáadott egy alkalmazást](apps-add.md) a Microsoft Intune-hoz, azt felhasználókhoz és eszközökhöz rendelheti hozzá. Vegye figyelembe, hogy az alkalmazást attól függetlenül hozzárendelheti az eszközhöz, hogy az eszközt az Intune felügyeli-e.

> [!NOTE]
> Az elérhető üzembe helyezési szándék a nem támogatott eszközcsoportok, csak a felhasználói csoportok támogatottak.

Az alábbi táblázat az alkalmazások felhasználókhoz és eszközökhöz való hozzárendelésével kapcsolatos különböző lehetőségeket sorolja fel:

|   | Az Intune-ban regisztrált eszközök | Az Intune-ban nem regisztrált eszközök |
|-------------------------------------------------------------------------------------------|------------------------------|----------------------------------|
| Hozzárendelés felhasználókhoz | Igen | Igen |
| Hozzárendelés eszközökhöz | Igen | Nem |
| Burkolt alkalmazások, vagy azt Intune SDK-t magukba foglaló alkalmazások hozzárendelése (alkalmazásvédelmi szabályzatok esetén) | Igen | Igen |
| Alkalmazások hozzárendelése elérhetőként | Igen | Igen |
| Alkalmazások hozzárendelése szükségesként | Igen | Nem |
| Alkalmazások eltávolítása | Igen | Nem |
| Alkalmazásfrissítések fogadása az Intune-ból | Igen | Nem |
| A végfelhasználók a Céges portál alkalmazásban telepítik az elérhető alkalmazásokat | Igen | Nem |
| A végfelhasználók a webalapú Intune Céges portálon telepítik az elérhető alkalmazásokat | Igen | Igen |

> [!NOTE]
> Jelenleg (mind üzletági, mind pedig áruházbeli) iOS- és Android-alkalmazásokat rendelhet hozzá azokhoz az eszközökhöz, melyek nincsenek regisztrálva az Intune-ban.
>
> Az alkalmazásfrissítések fogadásához az Intune-ban nem regisztrált eszközök felhasználóinak fel kell keresniük saját céges portáljukat, hogy manuálisan telepítsék az alkalmazásfrissítéseket.

## <a name="assign-an-app"></a>Egy alkalmazás a hozzárendelése

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** menüben válassza az **Ügyfélalkalmazások** lehetőséget.
4. A menü **Kezelés** szakaszában válassza az **Alkalmazások**. elemet.
5. Az **Alkalmazások** ablaktáblán jelölje ki a hozzárendelni kívánt alkalmazást.
6. A menü **Kezelés** szakaszában válassza a **Hozzárendelések** elemet.
7. Válassza a **Csoport hozzáadása** lehetőséget az alkalmazáshoz kapcsolódó **Csoport hozzáadása** ablaktábla megnyitásához.
8. Az adott alkalmazáshoz válasszon egy **hozzárendelés-típust**:
   - **Regisztrált eszközök esetében elérhető**: Az alkalmazás hozzárendelése csoportokhoz a felhasználók számára is telepítheti az alkalmazást a céges portál alkalmazásból vagy webhelyről.
   - **Elérhető regisztrációval és anélkül**: Ez az alkalmazás hozzárendelése csoportokhoz a felhasználók, akiknek az eszközei nincsenek regisztrálva az Intune-ban. Felhasználóknak hozzá kell rendelni egy Intune-licencet, lásd: [Intune-licencek](licenses.md).
   - **Szükséges**: Az alkalmazás telepítve van a kiválasztott csoportok eszközeire. Előfordulhat, hogy az egyes platformok esetében a felhasználó elfogadja az alkalmazások telepítésének megkezdése előtt a további utasításokat.
   - **Távolítsa el**: Az alkalmazás el lesz távolítva a kijelölt csoportokba eszközök Intune-ban korábban már telepítve van az alkalmazást az eszközön keresztül egy "regisztrált eszközökhöz elérhető" vagy "Kötelező" hozzárendelés a azonos üzemelő példány használatával. A webes hivatkozások telepítése után nem lehet eltávolítani.

     > [!NOTE]
     > **Csak az iOS-alkalmazások**: Ha IOS rendszerű alkalmazásonkénti VPN-beállításokat tartalmazó VPN-profilt hozott létre, válassza a VPN-profil alatt **VPN**. Az alkalmazás futtatásakor megnyílik a VPN-kapcsolat. További tudnivalókért lásd: [VPN-beállítások iOS-eszközökön](vpn-settings-ios.md).
     >
     > **Android-alkalmazások csak**: Ha telepít egy Android-alkalmazás, **elérhető regisztrációval és anélkül**, reporting állapota csak a regisztrált eszközökön elérhető lesz.

9. Az alkalmazás-hozzárendelés által érintett felhasználócsoportok kiválasztásához válassza a **Belefoglalt csoportok** lehetőséget.
10. Miután kiválasztott egy vagy több csoportot a belefoglaláshoz, válassza a **Kiválasztás** lehetőséget.
11. Kattintson a **Hozzárendelés** ablaktáblán az **OK** gombra a belefoglalt csoportok kiválasztásának befejezéséhez.
12. Ha ki szeretne zárni felhasználói csoportokat az alkalmazás-hozzárendelésből, válassza a **Csoportok kizárása** lehetőséget.
13. Ha valamilyen csoport kizárása mellett döntött, válassza a **Csoportok kiválasztása** ablaktáblán a **Kiválasztás** lehetőséget.
14. A **Csoport hozzáadása** panelen kattintson az **OK** gombra.
15. Az alkalmazás **Hozzárendelések** ablaktábláján kattintson a **Mentés** gombra.

Ezzel az alkalmazást hozzárendelte a kiválasztott csoportokhoz. További információt az alkalmazás-hozzárendelések belefoglalásához és kizárásához az [Alkalmazás-hozzárendelések belefoglalása és kizárása](apps-inc-exl-assignments.md) részben talál.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Alkalmazások hozzárendelési ütközéseinek feloldása

Néha előfordul, hogy ugyanazt az alkalmazást eltérő szándékkal rendelik hozzá különböző csoportokhoz. A következő táblázatban található információk segítségével megértheti, hogy amikor ez előfordul, milyen szándékot eredményez:

| 1. csoport hozzárendelési szándéka | 2. csoport hozzárendelési szándéka | Eredmény |
|-----------------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|A felhasználó kötelező|A felhasználó elérhető|Kötelező és elérhető|
|A felhasználó kötelező|A felhasználható nem érhető el|Szükséges|
|A felhasználó kötelező|Felhasználó eltávolítása|Szükséges|
|A felhasználó elérhető|A felhasználható nem érhető el|Nem érhető el|
|A felhasználó elérhető|Felhasználó eltávolítása|Eltávolítás|
|A felhasználható nem érhető el|Felhasználó eltávolítása|Eltávolítás
|A felhasználó kötelező|Az eszköz kötelező|Mind a két szándék létezik, az Intune Kötelező szándékként kezeli
|A felhasználó kötelező|Eszköz eltávolítása|Mind a két szándék létezik, az Intune a Kötelezőt oldja fel
|A felhasználó elérhető|Az eszköz kötelező|Mind a két szándék létezik, az Intune a Kötelezőt oldja fel (kötelező és elérhető)
|A felhasználó elérhető|Eszköz eltávolítása|Mind a két szándék létezik, az Intune az Elérhetőt oldja fel.<br><br>Az alkalmazás megjelenik az Intune Céges portálon.<br><br>Ha az alkalmazás már telepítve van (korábbi szándékkal kötelezőként) a rendszer eltávolítja az alkalmazást.<br><br>Ha a felhasználó a **Telepítés a céges portálról** lehetőséget választja, az alkalmazás telepítve lesz, és a rendszer az eltávolítás szándékát veti el.|
|A felhasználható nem érhető el|Az eszköz kötelező|Kötelező|
|A felhasználható nem érhető el|Eszköz eltávolítása|Eltávolítás|
|Felhasználó eltávolítása|Az eszköz kötelező|Mind a két szándék létezik, az Intune a Kötelezőt oldja fel|
|Felhasználó eltávolítása|Eszköz eltávolítása|Mind a két szándék létezik, az Intune az Eltávolítást oldja fel|
|Az eszköz kötelező|Eszköz eltávolítása|Szükséges|
|A felhasználó kötelező és elérhető|A felhasználó elérhető|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Felhasználó eltávolítása|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|A felhasználható nem érhető el|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Az eszköz kötelező|Mind a két szándék, a Kötelező és az Elérhető egyaránt létezik
|A felhasználó kötelező és elérhető|Az eszköz nem érhető el|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Eszköz eltávolítása|Mind a két szándék létezik, az Intune a Kötelezőt oldja fel (kötelező és elérhető)
|A felhasználható nem érhető el|Az eszköz nem érhető el|Nem érhető el|
|A felhasználó elérhető|Az eszköz nem érhető el|Elérhető|
|A felhasználó kötelező|Az eszköz nem érhető el|Szükséges|
|A felhasználó regisztráció nélkül elérhető|A felhasználó kötelező és elérhető|Kötelező és elérhető
|A felhasználó regisztráció nélkül elérhető|A felhasználó kötelező|Szükséges
|A felhasználó regisztráció nélkül elérhető|A felhasználható nem érhető el|Nem érhető el
|A felhasználó regisztráció nélkül elérhető|A felhasználó elérhető|Elérhető|
|A felhasználó regisztráció nélkül elérhető|Az eszköz kötelező|Kötelező és Regisztráció nélkül elérhető|
|A felhasználó regisztráció nélkül elérhető|Az eszköz nem érhető el|Regisztráció nélkül elérhető|
|A felhasználó regisztráció nélkül elérhető|Eszköz eltávolítása|Eltávolítás és Regisztráció nélkül elérhető.<br><br>Ha a felhasználó nem az Intune Céges portálról telepítette az alkalmazást, akkor a rendszer az eltávolítást veszi figyelembe.<br><br>Ha a felhasználó az Intune Céges portálról telepíti az alkalmazást, akkor a rendszer a telepítést részesíti előnyben az eltávolítással szemben.|

> [!NOTE]
> Csak áruházból származó felügyelt iOS-alkalmazások esetén, ha ezeket az alkalmazásokat a Microsoft Intune-ban **kötelezőként** rendeli hozzá, akkor a **Kötelező** és az **Elérhető** szándék automatikusan egyaránt fog vonatkozni rájuk.<br><br>
> A kötelező hozzárendelési szándékkal célzott (nem iOS VPP) iOS Store-alkalmazások az eszköz bejelentkezésekor kikényszerítetten hozzá lesznek rendelve az eszközhöz, és megjelennek a Céges portál alkalmazásban is.

## <a name="managed-google-play-app-deployment-to-unmanaged-devices"></a>Felügyelt Google Play alkalmazás üzembe helyezése nem felügyelt eszközökre
Android-eszközökhöz a egy nem regisztrált alkalmazás alkalmazásvédelmi szabályzat regisztráció nélkül (alkalmazás-TUDJUK) a telepítési forgatókönyvben segítségével felügyelt Google Play áruházbeli alkalmazások és az üzletági (LOB) alkalmazások telepítése a felhasználók számára. Felügyelt Google Play-alkalmazások **elérhető regisztrációval és anélkül** fog megjelenni a felhasználó eszközén a Play Store alkalmazást, és nem a céges portál alkalmazásban. Végfelhasználói fog alkalmazások tallózásához és telepítéséhez telepítve ezen a módon kikapcsolja a Play alkalmazásból. Mivel az alkalmazásokat telepít a felügyelt Google Play áruházból, a végfelhasználónak nem kell alter ismeretlen forrásokból, ami azt jelenti, az eszközök biztonságosabb lesz alkalmazások telepítésének engedélyezése az eszköz beállításai. Az alkalmazás fejlesztőjének egy alkalmazás egy új verziója, amely a felhasználó eszközén települt Play tesz közzé, ha az alkalmazást automatikusan frissíti Play. 

A felügyelt Google Play alkalmazás hozzárendelése nem felügyelt eszközök lépéseket:

1. Az Intune-bérlő csatlakozhat a felügyelt Google Play áruházból. Ha már ezt annak érdekében, hogy az Android Enterprise munkahelyi profilt, dedikált, és teljes körűen felügyelt eszközöket, nem kell ismét megtennie.
2. Alkalmazások hozzáadása a felügyelt Google Play áruházból az Intune-konzolon.
3. Felügyelt Google Play-alkalmazások, cél **elérhető regisztrációval és anélkül** a kívánt felhasználói csoporthoz. **Szükséges** és **Eltávolítás** célcsoport-kezelési alkalmazás nem támogatottak a nem regisztrált eszközökön.
4. Alkalmazásvédelmi szabályzat hozzárendelése a felhasználói csoportot.
5. Amikor a felhasználó megnyitja a vállalati portál alkalmazást, akkor fogja látni egy üzenet arról, hogy nincsenek alkalmazások a Play Store alkalmazás ezekhez rendelkezésre.  A felhasználó koppintson erre az értesítésre, le kell tölteni a Play alkalmazás közvetlenül a vállalati alkalmazások jelennek meg, vagy azok is keresse meg a Play Store alkalmazás külön-külön.
6. A végfelhasználó kibontásával, a helyi menüben a Play Store-alkalmazás és a Váltás (ahol megjelenik a személyes alkalmazásokat) személyes Google-fiókjával, és a munkahelyi fiókjával (ahol látják áruházbeli és ÜZLETÁGI alkalmazások azokból) között. A végfelhasználók az alkalmazások telepítése a Play Store alkalmazás koppintva telepítse.

Kiadásakor az alkalmazások szelektív törlése az Intune-konzolon, a munkahelyi fiók automatikusan eltávolítjuk a Play Store-alkalmazás és a felhasználó lesz a pontot többé nem látja munkahelyi alkalmazások a Play Store alkalmazás katalógusban. A munkahelyi fiókot eltávolítják az eszközről, ha a Play Store telepített alkalmazások marad az eszközön telepített, és nem lehet eltávolítani. 

## <a name="next-steps"></a>További lépések

Alkalmazás-hozzárendelések figyelésével kapcsolatos további tudnivalókért lásd: [Alkalmazások figyelése](apps-monitor.md).
