---
title: "Alkalmazások hozzárendelése csoportokhoz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Miután hozzáadott egy alkalmazást az Intune-hoz, érdemes hozzárendelni felhasználók vagy eszközök csoportjaihoz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 145f27e44d57e0f5ff7bbed76e14db713dd75286

---

# <a name="how-to-assign-apps-to-groups"></a>Alkalmazások hozzárendelése csoportokhoz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Miután hozzáadott egy alkalmazást az Intune-hoz, érdemes eljuttatni felhasználókhoz és eszközökre. Ezt hozzárendeléssel teheti meg.

Az alkalmazásokat hozzárendelheti eszközökhöz, függetlenül attól, hogy azokat az Intune kezeli-e vagy sem. Az alábbi táblázat segítségével megismerheti az alkalmazások felhasználókhoz és eszközökhöz való hozzárendelésének különböző lehetőségeit:

||||
|-|-|-|-|
|&nbsp;|Az Intune-ban regisztrált eszközök|Az Intune-ban nem regisztrált eszközök|
|Hozzárendelés felhasználókhoz|Igen|Igen|
|Hozzárendelés eszközökhöz|Igen|Nem|
|Burkolt alkalmazások, vagy azt Intune SDK-t magukba foglaló alkalmazások hozzárendelése (alkalmazásvédelmi szabályzatok esetén)|Igen|Igen|
|Alkalmazások hozzárendelése elérhetőként|Igen|Igen|
|Alkalmazások hozzárendelése szükségesként|Igen|Nem|
|Alkalmazások eltávolítása|Igen|Igen|
|A végfelhasználók a Céges portál alkalmazásban telepítik az elérhető alkalmazásokat|Igen|Nem|
|A végfelhasználók a webalapú Céges portálon telepítik az elérhető alkalmazásokat|Igen|Igen|

> [!NOTE]
> Jelenleg (mind üzletági, mind pedig áruházbeli) iOS- és Android-alkalmazásokat rendelhet hozzá azokhoz az eszközökhöz, melyek nincsenek regisztrálva az Intune-ban.

## <a name="how-to-assign-an-app"></a>Alkalmazás hozzárendelése

1. Jelentkezzen be az Azure Portal webhelyre.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
1. Az **Alkalmazások kezelése** területen válassza a **Felügyelet** > **Alkalmazások** elemet.
2. Az alkalmazáslista paneljén kattintson arra az alkalmazásra, amelyet szeretne hozzárendelni.
3. Az <*alkalmazásnév*> – **Áttekintés** panelen válassza a **Kezelés** > **Hozzárendelések** lehetőséget.
4. Válassza a **Csoportok kiválasztása** lehetőséget, majd a **Csoportok kiválasztása** panelen jelölje ki azon Azure AD-csoportokat, amelyekhez hozzá szeretné rendelni az alkalmazást.
5. Minden kiválasztott alkalmazáshoz válasszon egy **hozzárendelési típust** az alábbi lehetőségek közül:
    - **Elérhető** – A felhasználók a Céges portál alkalmazásban vagy webhelyen telepítik az alkalmazást.
    - **Nem alkalmazható** – Az alkalmazás nincs telepítve, vagy nem jelenik meg a Céges portálon.
    - **Szükséges** – A rendszer telepíti az alkalmazást a kiválasztott csoportok eszközeire.
    - **Eltávolítás** – A rendszer eltávolítja az alkalmazást a kiválasztott csoportok eszközeiről.
    - **Regisztrációval vagy anélkül is elérhető** – Az alkalmazás hozzárendelése olyan felhasználók csoportjaihoz, akik eszközei nincsenek regisztrálva az Intune-ban. A fenti táblázatban találhat segítséget.
6. Ha elkészült, válassza a **Mentés** elemet.

Az alkalmazás hozzá lett rendelve a kiválasztott csoporthoz.

Az alkalmazás-hozzárendelések figyeléséhez a [How to monitor apps](monitor-apps.md) (Alkalmazások figyelése) című témakörben találhat segítséget.



<!--HONumber=Feb17_HO1-->


