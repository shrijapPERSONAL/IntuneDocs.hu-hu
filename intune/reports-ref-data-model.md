---
title: "Az adattárház adatmodellje | Microsoft Docs"
description: "Az Intune-adattárház napi adatgyűjtéssel dokumentálja a folyamatosan változó mobilkörnyezet előzményeit."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9257af29c65dbe27667738abc8ee06203177124f
ms.sourcegitcommit: b8ef9d8387b4d9b2ea4e6ce937635304771e6532
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/11/2017
---
# <a name="data-warehouse-data-model"></a>Az adattárház adatmodellje

Az Intune-adattárház napi adatgyűjtéssel dokumentálja a folyamatosan változó mobilkörnyezet előzményeit.

A bérlőről lekért adatokat a rendszer egy adattárházba továbbítja. Az adattárház olyan entitások és kapcsolatok összessége, amelyek fontosak lehetnek a feltenni kívánt kérdések szempontjából. Ahhoz például, hogy megítélje, növekvő tendenciát mutatnak-e egy belső fejlesztésű androidos alkalmazás telepítései, áttekintheti a múlt heti telepítések számát napi bontásban. Az adattárház szerkezete lehetővé teszi a mobil környezet alapos megismerését. Az olyan elemzési eszközök pedig, mint a Microsoft Power BI, képi megjelenítéseket és dinamikus irányítópultokat hozhatnak létre az adattárház adatmodellje alapján.

Az Intune-adattárház szerkezete a csillagséma-modellt használja. A csillagséma az idő dimenziójában rendszerezi a tényadatokat. Ebben a modellben a *tényadat* mennyiségi mérőszám, mint például az eszközök száma, az alkalmazások száma, vagy a regisztráció ideje. Szintén ebben a modellben a *dimenzió* bizonyos kategóriák összességét és a köztük lévő hierarchikus kapcsolatot jelenti. Például a napok hónapokba, a hónapok évekbe rendeződnek. A rugalmasságra és adatelemzésre optimalizált csillagséma-modell segít összeállítani a folyamatosan változó mobilkörnyezet megértéséhez szükséges jelentéseket.

Az adattárház az adatokat a következő magas szintű kategóriákban tünteti fel:
  -  Alkalmazásvédelem által engedélyezett alkalmazások és használat
  -  Regisztrált eszközök, tulajdontárgyak és készlet
  -  Alkalmazások és szoftverleltár
  -  Eszközkonfigurációs és megfelelőségi szabályzatok

**Az adatmodell entitáskészletei**

Az entitáskészletek az adatmodell nevesített entitásgyűjteményei. Ezen készletek tartalmazzák a modellben összegyűjtött adatok meghatározására szolgáló entitásokat. Minden entitáskészlet egy hozzáférési pontot biztosít az adattárház adatmodelljéhez. A következő entitáskategóriákról részletes leírást talál:

  -  [Dátum](reports-ref-date.md)
  -  [Felhasználó](reports-ref-user.md)
  -  [Mobilalkalmazás-felügyelet (MAM)](reports-ref-mobile-app-management.md)
  -  [Eszközök](reports-ref-devices.md)
  -  [Alkalmazás](reports-ref-application.md)
  -  [Szabályzat](reports-ref-policy.md)

<!-- ## Data Model relationships

For more information on the relationships in the data model, see [Relationships of Entities](reports-api-entity-relationships.md). -->