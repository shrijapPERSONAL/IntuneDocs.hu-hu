---
title: Alkalmazásadatok és -hozzárendelések figyelése
titlesuffix: Microsoft Intune
description: Miután társított egy alkalmazást a felhasználókhoz vagy eszközökhöz, ezekkel az információkkal monitorozhatja az alkalmazás állapotát.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09e4cfc314ea21294cd3de62611a089ec724a683
ms.sourcegitcommit: f69f2663ebdd9c1def68423e8eadf30f86575f7e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2018
ms.locfileid: "49075627"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>Alkalmazásadatok és -hozzárendelések figyelése a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune több módot is kínál a felügyelt alkalmazások jellemzőinek figyelésére és az alkalmazások hozzárendelési állapotának kezelésére.

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** menüben válassza az **Ügyfélalkalmazások** lehetőséget.
4. A menü **Kezelés** szakaszában válassza az **Alkalmazások**. elemet.
5. Az alkalmazáslistában válasszon egy figyelni kívánt alkalmazást. Ekkor megjelenik az alkalmazás panelje, melyen áttekintheti az eszköz és a felhasználó állapotát.

> [!NOTE]
> Az **Elérhető** beállítással telepített Androidos áruházbeli alkalmazások nem jelentik a telepítési állapotukat.

## <a name="app-overview-pane"></a>Alkalmazás áttekintése panel

Az alkalmazáshoz tartozó panelen áttekintheti a környezetében lévő alkalmazás részletes állapotadatait.

### <a name="essentials"></a>Alapok
Az **Alapadatok** szakasz az alábbi információkat nyújtja az alkalmazásról:

 | **Alkalmazás részletei**            | **Leírás**                                                      |
|------------------------|------------------------------------------------------------------|
| **Kiadó**          | Az alkalmazás kiadója.                                            |
| **Operációs rendszer**   | Az alkalmazás operációs rendszere (Windows, iOS, Android és hasonlók). |
| **Létrehozás dátuma**             | A jelen változat létrehozásának dátuma és ideje.                         |
| **Kiosztott**           | **Igen** vagy **Nem** attól függően, hogy az alkalmazás ki lett-e osztva.                  |

### <a name="device-and-user-status-graphs"></a>Eszközök és felhasználók állapotábrái
Az ábrán az alábbi állapothoz tartozó alkalmazások száma jelenik meg:

| **Eszközállapot**       | **Leírás**                                       |
|-----------------------|-------------------------------------------------------|
| **Telepítve**         | A telepített alkalmazások száma.                         |
| **Nincs telepítve**     | A nem telepített alkalmazások száma.                     |
| **Sikertelen**            | A sikertelen telepítések száma.                   |
| **Telepítés függőben**   | Azon alkalmazások száma, amelyek telepítése jelenleg zajlik. |
| **Nem alkalmazható**           | A nem alkalmazható állapotértékkel rendelkező alkalmazások száma.            |

> [!NOTE]
> A felderített alkalmazások száma nem feltétlenül egyezik a telepített állapotú alkalmazások számával. A lehetséges eltérések a következők:
>    - Egy telepített felügyelt alkalmazás céljának módosítása miatt csökkenhet a telepítések száma az állapotpanelen, de az alkalmazás továbbra is szerepel az észlelt alkalmazások paneljén.
>    - Egy bérlőn belül egyazon alkalmazás több példányának megjelölése esetén a felhasználók és eszközök esetleges átfedései miatt eltérés léphet fel a számok között. Az alkalmazás minden példánya számolja az átfedésben lévő felhasználókat, a felderített alkalmazások esetében azonban a felhasználók többszörösen lesznek számolva.
>    - A felderített alkalmazásokat és az alkalmazások állapotát a rendszer különböző időközönként gyűjti be, így emiatt is eltérések alakulhatnak ki az alkalmazások számát illetően.
 
### <a name="device-install-status"></a>Eszköztelepítés állapota

Az eszközállapot-lista akkor jelenik meg, ha a menü **Figyelés** szakasz **Eszköztelepítés állapota** lehetőségét választja. A részleteket tartalmazó táblázatban az alábbi oszlopok szerepelnek:

| **Eszközoszlop**      | **Leírás**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Eszköz neve**      | Az eszköz neve az eszközök elnevezését megengedő platformokon. Más platformokon az Intune hoz létre nevet más tulajdonságok alapján. Ez az attribútum nem érhető el semmilyen más eszközön.                                                                       |
| **Felhasználónév**        | A felhasználó neve.                                                                                                                                                                                                                                      |
| **Platform**         | Az eszköz operációs rendszere (Windows, iOS, Android és hasonlók.).                                                                                                                                                                                           |
| **Verzió**          | Az alkalmazás verziószáma. Az üzletági alkalmazások esetében az alkalmazás teljes verziószáma jelenik meg. A teljes verziószám az alkalmazás egy adott verzióját azonosítja. A szám az alábbi formátumban jelenik meg: _Verzió_(_Build_). Például 2.2(2.2.17560800). |
| **Állapot**           | Az alkalmazás állapota.                                                                                                                                                                                                                                     |
| **Állapot részletei**   | Az állapot részletei.                                                                                                                                                                                                                                     |
| **Legutóbbi bejelentkezés**    | Az eszköz Intune-nal való utolsó szinkronizálásának dátuma.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Felhasználótelepítés állapota

A felhasználóállapot-lista akkor jelenik meg, ha a menü **Figyelés** szakasz **Felhasználótelepítés állapota** lehetőségét választja. A részleteket tartalmazó táblázatban az alábbi oszlopok szerepelnek:

| **Felhasználóoszlop**     | **Leírás**                           |
|---------------------|-------------------------------------------|
| **Név**            | A felhasználó Azure Active Directoryban használt neve.         |
| **Felhasználónév**       | A felhasználó egyedi neve.              |
| **Telepítések**   | A felhasználó által nem telepített alkalmazások száma. |
| **Hibák**        | A felhasználó sikertelen alkalmazástelepítéseinek száma.     |
| **Nincs telepítve**   | A felhasználó által nem telepített alkalmazások száma. |


## <a name="next-steps"></a>További lépések

- Az Intune-adatok használatáról bővebben [Az Intune-adattárház használata](reports-nav-create-intune-reports.md) című témakörben tájékozódhat.
- További információ az alkalmazáskonfigurációs szabályzatokról: [Az Intune alkalmazáskonfigurációs szabályzatai](app-configuration-policies-overview.md).
