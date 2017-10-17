---
title: "Zárolás és jelszó alaphelyzetbe állítása távolról"
description: "Az Intune egyaránt nyújt távoli zárolásra és a jelszavak alaphelyzetbe állítására szolgáló funkciókat."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.custom: intune-classic
ms.openlocfilehash: 0fb7014392655eef44f94cf095717616732ebfd0
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Az adatok védelme távoli zárolással és jelszó alaphelyzetbe állításával

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune egyaránt biztosít távoli zárolásra és a jelszavak alaphelyzetbe állítására szolgáló képességeket.

## <a name="lock-a-device-remotely"></a>Eszköz távoli zárolása
Ha egy felhasználó elveszíti az eszközét, távolról zárolhatja az eszközt. A távoli zárolás használata előtt már rendelkeznie kell az eszközön egy beállított PIN-kóddal vagy hitelesítő kóddal.

Az alábbi táblázatban áttekintheti, hogy hogyan működik a távoli zárolás az egyes mobilplatformokon.

|Platform|Távoli zárolás|
|------------|---------------|
|macOS|Nem támogatott|
|iOS|Támogatott|
|Android|Támogatott|
|Android for Work|Támogatott|
|Windows 10 (mobilverzió)|Támogatott|
|Windows 10 (asztali verzió)|Nem támogatott|
|Windows Phone 8 és Windows Phone 8.1|Támogatott|
|Windows RT 8.1 és Windows RT|Támogatott, ha az eszköz aktuális felhasználója megegyezik az eszközt beléptető felhasználóval.|
|Windows 8.1|Támogatott, ha az eszköz aktuális felhasználója megegyezik az eszközt beléptető felhasználóval.|

Az Intune szoftverügyfélben regisztrált Windows számítógépek nem támogatják a távoli zárolást.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Mobileszköz zárolása távolról az Intune-konzollal

1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) kattintson a **Csoportok** &gt; **Minden eszköz** &gt; **Minden mobileszköz** elemre.

2.  Kattintson a **Minden közvetlenül felügyelt eszköz** elemre az Intune-ban regisztrált eszközök megjelenítéséhez, vagy kattintson a **Minden Exchange ActiveSync által kezelt eszköz** elemre.

    > [!TIP]
    > Az eszközt akár a felhasználó alapján is megtalálhatja. Válassza a **Minden felhasználó** lehetőséget. A felhasználó Tulajdonságok lapján kattintson az **Eszközök** elemre, majd a zárolni kívánt mobileszköz nevére.

3.  A listában kattintson a zárolni kívánt eszközre vagy eszközökre. A tálcán kattintson a **Távoli feladatok** elemre, és válassza a **Távoli zárolás** lehetőséget.

## <a name="reset-the-passcode-on-a-device"></a>Eszköz PIN-kódjának alaphelyzetbe állítása
Ha egy felhasználó elfelejti a PIN-kódját, segítségként eltávolíthatja a PIN-kódot az eszközről, vagy új ideiglenes PIN-kódot kényszeríthet az eszközre. A következő táblázatban áttekintheti, hogy hogyan működik a PIN-kód cseréje az egyes mobilplatformokon.

|Platform|PIN-kód alaphelyzetbe állítása|
|------------|------------------|
|macOS|Nem támogatott|
|iOS|Csak a PIN-kód eszközről való törlése támogatott. Nem lehet új ideiglenes PIN-kódot létrehozni.|
|Android|Az Android 7.0-nál régebbi verziói támogatottak. Létrehoz egy ideiglenes jelszót.|
|Android for Work|Nem támogatott|
|Windows 10 mobil verzió|Az Azure AD-hez csatlakoztatott, Windows 10 alkotói frissítést és későbbi verziókat futtató mobileszközök esetén támogatott.|
|Windows Phone 8 és Windows Phone 8.1|Támogatott|
|Windows RT 8.1|Nem támogatott|
|Windows 8.1|Nem támogatott|
|Windows 10 asztali verzió|Nem támogatott|

Az Intune szoftverügyfélben regisztrált Windows számítógépek nem támogatják a jelszó alaphelyzetbe állítását.

### <a name="reset-a-passcode"></a>Új PIN-kód kérése

1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) kattintson a **Csoportok** &gt; **Minden eszköz** &gt; **Minden mobileszköz** elemre.

2.  Kattintson a **Minden közvetlenül felügyelt eszköz** elemre az Intune-ban regisztrált eszközök megjelenítéséhez, vagy kattintson a **Minden Exchange ActiveSync által kezelt eszköz** elemre.

    > [!TIP]
    > Az eszközt akár a felhasználó alapján is megtalálhatja. Kattintson a **Minden felhasználó** elemre. A felhasználó Tulajdonságok lapján kattintson az **Eszközök** elemre, majd a törölni kívánt mobileszköz nevére.

3.  A listában kattintson a zárolni kívánt eszközre vagy eszközökre. A tálcán kattintson a **Távoli feladatok** elemre, és válassza a **Jelszó alaphelyzetbe állítása** lehetőséget.


### <a name="see-also"></a>További információ
[Eszköz kivonása](retire-devices-from-microsoft-intune-management.md), illetve [a Windowsban elérhető, az eszközadatok felügyeletére szolgáló szelektív törlési funkció ismertetése](http://technet.microsoft.com/library/dn486874.aspx)
