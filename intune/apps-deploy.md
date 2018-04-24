---
title: Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-ban
titlesuffix: ''
description: Miután hozzáadott egy alkalmazást a Microsoft Intune-hoz, érdemes hozzárendelni azt felhasználók vagy eszközök csoportjaihoz.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de95f5516298e8ade9e394fab8b05fc056651b0c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Miután hozzáadott egy alkalmazást a Microsoft Intune-hoz, felhasználókhoz és eszközökhöz rendelheti hozzá.

Az alkalmazásokat hozzárendelheti eszközökhöz, függetlenül attól, hogy azokat az Intune kezeli-e vagy sem. Az alábbi táblázat segítségével megismerheti az alkalmazások felhasználókhoz és eszközökhöz való hozzárendelésének különböző lehetőségeit:

||||
|-|-|-|-|
|&nbsp;|Az Intune-ban regisztrált eszközök|Az Intune-ban nem regisztrált eszközök|
|Hozzárendelés felhasználókhoz|Igen|Igen|
|Hozzárendelés eszközökhöz|Igen|Nem|
|Burkolt alkalmazások, vagy azt Intune SDK-t magukba foglaló alkalmazások hozzárendelése (alkalmazásvédelmi szabályzatok esetén)|Igen|Igen|
|Alkalmazások hozzárendelése elérhetőként|Igen|Igen|
|Alkalmazások hozzárendelése szükségesként|Igen|Nem|
|Alkalmazások eltávolítása|Igen|Nem|
|Alkalmazásfrissítések fogadása az Intune-ból|Igen|Nem|
|A végfelhasználók a Céges portál alkalmazásban telepítik az elérhető alkalmazásokat|Igen|Nem|
|A végfelhasználók a webalapú Céges portálon telepítik az elérhető alkalmazásokat|Igen|Igen|

> [!NOTE]
> Jelenleg (mind üzletági, mind pedig áruházbeli) iOS- és Android-alkalmazásokat rendelhet hozzá azokhoz az eszközökhöz, melyek nincsenek regisztrálva az Intune-ban.<br></br><br></br>
> Az alkalmazásfrissítések fogadásához az Intune-ban nem regisztrált eszközök felhasználóinak fel kell keresniük saját céges portáljukat, hogy manuálisan telepítsék az alkalmazásfrissítéseket.

## <a name="how-to-assign-an-app"></a>Alkalmazás hozzárendelése

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** terület **Kezelés** szakaszában válassza az **Alkalmazások** lehetőséget.
5. Az alkalmazáslista paneljén kattintson arra az alkalmazásra, amelyet szeretne hozzárendelni.
6. Az alkalmazásspecifikus **Áttekintés** panel **Kezelés** szakaszában válassza a **Hozzárendelések** lehetőséget.
7. Válassza a **Csoport hozzáadása** lehetőséget az alkalmazáshoz tartozó **Csoport hozzáadása** panel megjelenítéséhez.
8. Az adott alkalmazáshoz válasszon egy **hozzárendelési típust** az alábbi lehetőségek közül:
   - **Regisztrált eszközökhöz elérhető** – A felhasználók a Céges portál alkalmazásban vagy webhelyen telepítik az alkalmazást.
   - **Regisztrációval vagy anélkül is elérhető** – Az alkalmazás hozzárendelése olyan felhasználók csoportjaihoz, akik eszközei nincsenek regisztrálva az Intune-ban. Vegye figyelembe, hogy az **Android for Work alkalmazás** típus nem támogatja ezt a beállítást. 
   - **Szükséges** – A rendszer telepíti az alkalmazást a kiválasztott csoportok eszközeire.
   - **Eltávolítás** – A rendszer eltávolítja az alkalmazást a kiválasztott csoportok eszközeiről.

     > [!NOTE]
     > **Csak iOS-alkalmazásokhoz** – Ha alkalmazásonkénti VPN-beállításokat tartalmazó iOS VPN-profilt hozott létre, a **VPN** elem alatt jelölheti ki azt. Az alkalmazás futtatásakor megnyílik a VPN-kapcsolat. További tudnivalókért lásd: [VPN-beállítások iOS-eszközökön](vpn-settings-ios.md).

9. Az alkalmazás-hozzárendelés célcsoportjának kiválasztásához válassza a **Belefoglalt csoportok** lehetőséget.
10. A csoportok kiválasztása után kattintson a **Kiválasztás** lehetőségre.
11. Kattintson a **Hozzárendelés** panel **OK** gombjára a belefoglalt csoportok szakasz befejezéséhez.
12. Ha ki szeretne zárni felhasználói csoportokat az alkalmazás-hozzárendelés alól, kattintson a **Csoportok kizárása** lehetőségre.
13. Ha kizár csoportokat, kattintson a **Csoportok kiválasztása** panel **Kiválasztás** lehetőségére.
14. A **Csoport hozzáadása** panelen kattintson az **OK** lehetőségre.
15. Az alkalmazás **Hozzárendelések** panelén kattintson a **Mentés** lehetőségre a hozzárendelések mentéséhez.

Ezzel az alkalmazást hozzárendelte a kiválasztott csoportokhoz. További információt az alkalmazás-hozzárendelések belefoglalásához és kizárásához az [Alkalmazás-hozzárendelések belefoglalása és kizárása](apps-inc-exl-assignments.md) részben talál.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Alkalmazások hozzárendelési ütközéseinek feloldása

Néha előfordul, hogy ugyanazt az alkalmazást eltérő szándékkal rendelik hozzá különböző csoportokhoz. Ilyenkor az eredményként kapott hozzárendelési szándék megértéséhez használja az alábbi táblázatot.

||||
|-|-|-|
|1. csoport hozzárendelési szándéka|2. csoport hozzárendelési szándéka|Eredmény|
|A felhasználó kötelező|A felhasználó elérhető|Kötelező és elérhető|
|A felhasználó kötelező|A felhasználható nem érhető el|Kötelező|
|A felhasználó kötelező|Felhasználó eltávolítása|Kötelező|
|A felhasználó elérhető|A felhasználható nem érhető el|Nem érhető el|
|A felhasználó elérhető|Felhasználó eltávolítása|Eltávolítás|
|A felhasználható nem érhető el|Felhasználó eltávolítása|Eltávolítás
|A felhasználó kötelező|Az eszköz kötelező|Mind a két szándék létezik, az átjáró Kötelező szándékként kezeli
|A felhasználó kötelező|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró a Kötelező szándékot oldja fel
|A felhasználó elérhető|Az eszköz kötelező|Mind a két szándék létezik, az átjáró a Kötelező szándékot oldja fel (Kötelező és Elérhető)
|A felhasználó elérhető|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró az Elérhető szándékot oldja fel.<br>Az alkalmazás megjelenik a Céges portálon.<br>Korábban (korábbi szándékkal kötelezőként) telepített alkalmazás esetén a rendszer eltávolítja az alkalmazást.<br>Ha viszont a felhasználó a Céges portálról kattint a telepítésre, az alkalmazás telepítve lesz, és a rendszer az eltávolítás szándékát veti el.|
|A felhasználható nem érhető el|Az eszköz kötelező|Kötelező|
|A felhasználható nem érhető el|Eszköz eltávolítása|Eltávolítás|
|Felhasználó eltávolítása|Az eszköz kötelező|Mind a két szándék létezik, az átjáró a Kötelező szándékot oldja fel|
|Felhasználó eltávolítása|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró az Eltávolítást oldja fel|
|Az eszköz kötelező|Eszköz eltávolítása|Kötelező|
|A felhasználó kötelező és elérhető|A felhasználó elérhető|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Felhasználó eltávolítása|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|A felhasználható nem érhető el|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Az eszköz kötelező|Mind a két szándék, a Kötelező és az Elérhető egyaránt létezik
|A felhasználó kötelező és elérhető|Az eszköz nem érhető el|Kötelező és elérhető|
|A felhasználó kötelező és elérhető|Eszköz eltávolítása|Mind a két szándék létezik, az átjáró a Kötelező szándékot oldja fel. Kötelező + Elérhető
|A felhasználható nem érhető el|Az eszköz nem érhető el|Nem érhető el|
|A felhasználó elérhető|Az eszköz nem érhető el|Elérhető|
|A felhasználó kötelező|Az eszköz nem érhető el|Kötelező|
|A felhasználó regisztráció nélkül elérhető|A felhasználó kötelező és elérhető|Kötelező és elérhető
|A felhasználó regisztráció nélkül elérhető|A felhasználó kötelező|Kötelező
|A felhasználó regisztráció nélkül elérhető|A felhasználó nem érhető el|Nem érhető el
|A felhasználó regisztráció nélkül elérhető|A felhasználó elérhető|Elérhető|
|A felhasználó regisztráció nélkül elérhető|Az eszköz kötelező|Kötelező és Regisztráció nélkül elérhető|
|A felhasználó regisztráció nélkül elérhető|Az eszköz nem érhető el|Regisztráció nélkül elérhető|
|A felhasználó regisztráció nélkül elérhető|Eszköz eltávolítása|Eltávolítás és Regisztráció nélkül elérhető.<br>Ha a felhasználó nem a Céges portálról telepítette az alkalmazást, akkor a rendszer az eltávolítást veszi figyelembe.<br>Ha a felhasználó a Céges portálról telepíti az alkalmazást, akkor a rendszer a telepítést részesíti előnyben az eltávolítással szemben.|

>[!NOTE]
>Csak áruházból származó felügyelt iOS-alkalmazások esetén, ha ezeket az alkalmazásokat a Microsoft Intune-ban **kötelezőként** rendeli hozzá, akkor a **Kötelező** és az **Elérhető** szándék automatikusan egyaránt fog vonatkozni rájuk.

## <a name="next-steps"></a>További lépések

Az alkalmazás-hozzárendelések figyeléséhez a [How to monitor apps](apps-monitor.md) (Alkalmazások figyelése) című témakörben találhat segítséget.
