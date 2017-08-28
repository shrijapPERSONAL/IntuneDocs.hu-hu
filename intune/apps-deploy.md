---
title: "Alkalmazások hozzárendelése csoportokhoz"
titleSuffix: Intune on Azure
description: "Miután hozzáadott egy alkalmazást az Intune-hoz, érdemes hozzárendelni azt felhasználók vagy eszközök csoportjaihoz."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a0249fe3ecd82f6382b2625378d6a81d33129069
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Miután felvett egy alkalmazást az Intune-ba, felhasználókhoz és eszközökhöz rendelheti hozzá.

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
|A végfelhasználók a Céges portál alkalmazásban telepítik az elérhető alkalmazásokat|Igen|Nem|
|A végfelhasználók a webalapú Céges portálon telepítik az elérhető alkalmazásokat|Igen|Igen|

> [!NOTE]
> Jelenleg (mind üzletági, mind pedig áruházbeli) iOS- és Android-alkalmazásokat rendelhet hozzá azokhoz az eszközökhöz, melyek nincsenek regisztrálva az Intune-ban.

## <a name="how-to-assign-an-app"></a>Alkalmazás hozzárendelése

1. Jelentkezzen be az Azure Portal webhelyre.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
2. Az alkalmazáslista paneljén kattintson arra az alkalmazásra, amelyet szeretne hozzárendelni.
3. Az <*alkalmazásnév*> – **Áttekintés** panelen válassza a **Kezelés** > **Hozzárendelések** lehetőséget.
4. Válassza a **Csoportok kiválasztása** lehetőséget, majd a **Csoportok kiválasztása** panelen jelölje ki azon Azure AD-csoportokat, amelyekhez hozzá szeretné rendelni az alkalmazást.
5. Minden kiválasztott alkalmazáshoz válasszon egy **hozzárendelési típust** az alábbi lehetőségek közül:
    - **Elérhető** – A felhasználók a Céges portál alkalmazásban vagy webhelyen telepítik az alkalmazást.
    - **Nem alkalmazható** – Az alkalmazás nincs telepítve, vagy nem jelenik meg a Céges portálon.
    - **Szükséges** – A rendszer telepíti az alkalmazást a kiválasztott csoportok eszközeire.
    - **Eltávolítás** – A rendszer eltávolítja az alkalmazást a kiválasztott csoportok eszközeiről.
    - **Regisztrációval vagy anélkül is elérhető** – Az alkalmazás hozzárendelése olyan felhasználók csoportjaihoz, akik eszközei nincsenek regisztrálva az Intune-ban.
6. **Csak iOS-alkalmazásokhoz** – Ha alkalmazásonkénti VPN-beállításokat tartalmazó iOS VPN-profilt hozott létre, a **VPN** elem alatt jelölheti ki azt. Ha az alkalmazás fut, a VPN-kapcsolat nyitva van. További tudnivalókért lásd: [VPN-beállítások iOS-eszközökön](vpn-settings-ios.md).
6. Ha elkészült, válassza a **Mentés** elemet.

Ezzel az alkalmazást hozzárendelte a kiválasztott csoportokhoz.

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
>Csak áruházból származó felügyelt iOS-alkalmazások esetén, ha ezeket az alkalmazásokat az Intune-ban kötelezőként rendeli hozzá, akkor a Kötelező és az Elérhető szándék automatikusan egyaránt fog vonatkozni rájuk.

## <a name="next-steps"></a>További lépések

Az alkalmazás-hozzárendelések figyeléséhez a [How to monitor apps](apps-monitor.md) (Alkalmazások figyelése) című témakörben találhat segítséget.
