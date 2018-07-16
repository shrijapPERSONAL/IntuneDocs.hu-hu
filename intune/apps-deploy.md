---
title: Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-ban
titlesuffix: ''
description: Útmutató Intune-alkalmazás felhasználói csoportokhoz vagy eszközökhöz való hozzárendeléséhez.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 581d3c9762145a4681b421ededaaf9099e8ceb80
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905886"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Miután [hozzáadott egy alkalmazást](apps-add.md) a Microsoft Intune-hoz, azt felhasználókhoz és eszközökhöz rendelheti hozzá. Vegye figyelembe, hogy az alkalmazást attól függetlenül hozzárendelheti az eszközhöz, hogy az eszközt az Intune felügyeli-e. 

Az alábbi táblázat az alkalmazások felhasználókhoz és eszközökhöz való hozzárendelésével kapcsolatos különböző lehetőségeket sorolja fel:

||||
|-|-|-|-|
|&nbsp;|**Az Intune-ban regisztrált eszközök**|**Az Intune-ban nem regisztrált eszközök**|
|Hozzárendelés felhasználókhoz|Igen|Igen|
|Hozzárendelés eszközökhöz|Igen|Nem|
|Burkolt alkalmazások, vagy azt Intune SDK-t magukba foglaló alkalmazások hozzárendelése (alkalmazásvédelmi szabályzatok esetén)|Igen|Igen|
|Alkalmazások hozzárendelése elérhetőként|Igen|Igen|
|Alkalmazások hozzárendelése szükségesként|Igen|Nem|
|Alkalmazások eltávolítása|Igen|Nem|
|Alkalmazásfrissítések fogadása az Intune-ból|Igen|Nem|
|A végfelhasználók a Céges portál alkalmazásban telepítik az elérhető alkalmazásokat|Igen|Nem|
|A végfelhasználók a webalapú Intune Céges portálon telepítik az elérhető alkalmazásokat|Igen|Igen|

> [!NOTE]
> Jelenleg (mind üzletági, mind pedig áruházbeli) iOS- és Android-alkalmazásokat rendelhet hozzá azokhoz az eszközökhöz, melyek nincsenek regisztrálva az Intune-ban.
>
> Az alkalmazásfrissítések fogadásához az Intune-ban nem regisztrált eszközök felhasználóinak fel kell keresniük saját céges portáljukat, hogy manuálisan telepítsék az alkalmazásfrissítéseket.

## <a name="to-assign-an-app"></a>Alkalmazás hozzárendelése

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** menüben válassza a **Mobilalkalmazások** lehetőséget.
4. A menü **Kezelés** szakaszában válassza az **Alkalmazások**. elemet.
5. Az **Alkalmazások** ablaktáblán jelölje ki a hozzárendelni kívánt alkalmazást.
6. A menü **Kezelés** szakaszában válassza a **Hozzárendelések** elemet.
7. Válassza a **Csoport hozzáadása** lehetőséget az alkalmazáshoz kapcsolódó **Csoport hozzáadása** ablaktábla megnyitásához.
8. Az adott alkalmazáshoz válasszon egy **hozzárendelés-típust**:
   - **Regisztrált eszközökhöz elérhető**: A felhasználók a Céges portál alkalmazásban vagy webhelyen telepítik az alkalmazást.
   - **Regisztrációval vagy anélkül is elérhető**: Az alkalmazás hozzárendelése olyan felhasználók csoportjaihoz, akik eszközei nincsenek regisztrálva az Intune-ban. A felügyelt Google Play áruházból származó és a macOS üzletági alkalmazások nem támogatják ezt a lehetőséget. 
   - **Szükséges**: A rendszer telepíti az alkalmazást a kiválasztott csoportok eszközeire.
   - **Eltávolítás**: A rendszer eltávolítja az alkalmazást a kiválasztott csoportok eszközeiről.

     > [!NOTE]
     > **Csak iOS-alkalmazásokhoz**: Ha alkalmazásonkénti VPN-beállításokat tartalmazó iOS VPN-profilt hozott létre, a VPN-profilt a **VPN** alatt jelölheti ki. Az alkalmazás futtatásakor megnyílik a VPN-kapcsolat. További tudnivalókért lásd: [VPN-beállítások iOS-eszközökön](vpn-settings-ios.md).

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

||||
|-|-|-|
|**1. csoport hozzárendelési szándéka**|**2. csoport hozzárendelési szándéka**|**Eredmény**|
|A felhasználó kötelező|A felhasználó elérhető|Kötelező és elérhető|
|A felhasználó kötelező|A felhasználható nem érhető el|Kötelező|
|A felhasználó kötelező|Felhasználó eltávolítása|Kötelező|
|A felhasználó elérhető|A felhasználható nem érhető el|Nem érhető el|
|A felhasználó elérhető|Felhasználó eltávolítása|Eltávolítás|
|A felhasználható nem érhető el|Felhasználó eltávolítása|Eltávolítás
|A felhasználó kötelező|Az eszköz kötelező|Mind a két szándék létezik, az átjáró Kötelező szándékként kezeli
|A felhasználó kötelező|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró a Kötelezőt oldja fel
|A felhasználó elérhető|Az eszköz kötelező|Mind a két szándék létezik, az átjáró a Kötelezőt oldja fel (kötelező és elérhető)
|A felhasználó elérhető|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró az Elérhető szándékot oldja fel.<br><br>Az alkalmazás megjelenik az Intune Céges portálon.<br><br>Ha az alkalmazás már telepítve van (korábbi szándékkal kötelezőként) a rendszer eltávolítja az alkalmazást.<br><br>Ha a felhasználó a **Telepítés a céges portálról** lehetőséget választja, az alkalmazás telepítve lesz, és a rendszer az eltávolítás szándékát veti el.|
|A felhasználható nem érhető el|Az eszköz kötelező|Kötelező|
|A felhasználható nem érhető el|Eszköz eltávolítása|Eltávolítás|
|Felhasználó eltávolítása|Az eszköz kötelező|Mind a két szándék létezik, az átjáró a Kötelezőt oldja fel|
|Felhasználó eltávolítása|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró az Eltávolítást oldja fel|
|Az eszköz kötelező|Eszköz eltávolítása|Kötelező|
|A felhasználó kötelező és elérhető|A felhasználó elérhető|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Felhasználó eltávolítása|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|A felhasználható nem érhető el|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Az eszköz kötelező|Mind a két szándék, a Kötelező és az Elérhető egyaránt létezik
|A felhasználó kötelező és elérhető|Az eszköz nem érhető el|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró a Kötelezőt oldja fel (kötelező és elérhető)
|A felhasználható nem érhető el|Az eszköz nem érhető el|Nem érhető el|
|A felhasználó elérhető|Az eszköz nem érhető el|Elérhető|
|A felhasználó kötelező|Az eszköz nem érhető el|Kötelező|
|A felhasználó regisztráció nélkül elérhető|A felhasználó kötelező és elérhető|Kötelező és elérhető
|A felhasználó regisztráció nélkül elérhető|A felhasználó kötelező|Kötelező
|A felhasználó regisztráció nélkül elérhető|A felhasználható nem érhető el|Nem érhető el
|A felhasználó regisztráció nélkül elérhető|A felhasználó elérhető|Elérhető|
|A felhasználó regisztráció nélkül elérhető|Az eszköz kötelező|Kötelező és Regisztráció nélkül elérhető|
|A felhasználó regisztráció nélkül elérhető|Az eszköz nem érhető el|Regisztráció nélkül elérhető|
|A felhasználó regisztráció nélkül elérhető|Eszköz eltávolítása|Eltávolítás és Regisztráció nélkül elérhető.<br><br>Ha a felhasználó nem az Intune Céges portálról telepítette az alkalmazást, akkor a rendszer az eltávolítást veszi figyelembe.<br><br>Ha a felhasználó az Intune Céges portálról telepíti az alkalmazást, akkor a rendszer a telepítést részesíti előnyben az eltávolítással szemben.|

> [!NOTE]
> Csak áruházból származó felügyelt iOS-alkalmazások esetén, ha ezeket az alkalmazásokat a Microsoft Intune-ban **kötelezőként** rendeli hozzá, akkor a **Kötelező** és az **Elérhető** szándék automatikusan egyaránt fog vonatkozni rájuk.<br><br>
> A kötelező hozzárendelési szándékkal célzott (nem iOS VPP) iOS Store-alkalmazások az eszköz bejelentkezésekor kikényszerítetten hozzá lesznek rendelve az eszközhöz, és megjelennek a Céges portál alkalmazásban is.

## <a name="next-steps"></a>További lépések

Alkalmazás-hozzárendelések figyelésével kapcsolatos további tudnivalókért lásd: [Alkalmazások figyelése](apps-monitor.md).
