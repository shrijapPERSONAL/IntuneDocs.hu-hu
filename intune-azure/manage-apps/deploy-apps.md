---
title: "Alkalmazások hozzárendelése csoportokhoz"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Miután hozzáadott egy alkalmazást az Intune-hoz, érdemes hozzárendelni felhasználók vagy eszközök csoportjaihoz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b372d4ee505ca39a4739069e5798918ecde134ea
ms.openlocfilehash: abf45b835d13ef5fe4acb769194542611448504e
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal

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

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Változások az alkalmazások csoportokhoz való hozzárendelésében az Intune előzetesben

Az Intune az Azure-on előzetesében az alkalmazások hozzárendeléséhez már nem használatosak az Intune-csoportok. Helyettük Azure Active Directory (Azure AD) biztonsági csoportokat kell használni. Ezért érdemes megismerkednie az alkalmazás-hozzárendeléseket érintő bizonyos változásokkal, különösen ha Intune-gyermekcsoportokhoz rendelt hozzá alkalmazásokat.
A legfontosabb változás, hogy az Azure AD-ben nem alkalmazzuk a gyermekcsoport fogalmát. Ezzel együtt bizonyos csoportok rendelkezhetnek ugyanazokkal a tagokkal. Ilyen esetekben a klasszikus Intune és az Intune az Azure-on viselkedése eltér egymástól. Ez az alábbi táblázatban látható:

||||||
|-|-|-|-|-|
|**Klasszikus Intune (a bérlő áttelepítése előtt)**|-|**Intune az Azure-on (a bérlő áttelepítése után)**|-|**További információ**|
|**Üzembe helyezési szándék a szülőcsoportban**|**Üzembe helyezési szándék a gyermekcsoportban**|**Az előző szülő- és gyermekcsoport tagjai számára érvényesülő hozzárendelési szándék**|**A szülőcsoport tagjai számára érvényesülő hozzárendelési szándék**|-|    
|Elérhető|Kötelező|Kötelező és elérhető|Elérhető|A „kötelező és elérhető” azt jelenti, hogy a kötelezőként hozzárendelt alkalmazások a Vállalati portál alkalmazásban is megjelennek.
|Nem alkalmazható|Elérhető|Nem alkalmazható|Nem alkalmazható|Megkerülő megoldás: távolítsa el a „Nem alkalmazható” üzembe helyezési szándékmegjelölést az Intune szülőcsoportból.
|Kötelező|Elérhető|Kötelező és elérhető|Kötelező|-|
|Kötelező és elérhető<sup>1</sup>|Elérhető|Kötelező és elérhető|Kötelező és elérhető|-|    
|Kötelező|Nem alkalmazható|Kötelező|Kötelező|-|    
|Kötelező és elérhető|Nem alkalmazható|Kötelező és elérhető|Kötelező és elérhető|-|    
|Kötelező|Eltávolítás|Kötelező|Kötelező|-|    
|Kötelező és elérhető|Eltávolítás|Kötelező és elérhető|Kötelező és elérhető|-|
<sup>1</sup> Csak áruházból származó felügyelt iOS-alkalmazás esetén. Ha az alkalmazás kötelezőként lett hozzáadva az Intune-hoz, akkor arra automatikusan mind a Kötelező, mind az Elérhető szándék fog vonatkozni.

Az üzembe helyezési ütközések elkerülése érdekében a következőket teheti:

1.    Ha már üzembe helyezett alkalmazásokat egymáshoz kapcsolódó Intune szülő- és gyermekcsoportokba, ezeket az üzemelő példányokat még a bérlő áttelepítése előtt érdemes eltávolítani.
2.    Távolítsa el a gyermekcsoportokat a szülőcsoportokból, majd hozzon létre egy új csoportot a korábbi gyermekcsoport tagjaiból. Ezt követően ebben a csoportban létrehozhat egy új alkalmazástelepítést.
Megjegyzés: Ha a korábbi szülőcsoport „Minden felhasználó” volt, akkor olyan új dinamikus csoportot kell létrehoznia, amely nem tartalmazza a gyermekcsoport tagjait.
A felhasználókat és eszközcsoportokat érintő csoportmódosításokat az [Azure Portalon](https://portal.azure.com/) kell elvégezni. A [klasszikus Azure-portál](https://manage.windowsazure.com/) csak a felhasználói csoportok módosítását teszi lehetővé.


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

