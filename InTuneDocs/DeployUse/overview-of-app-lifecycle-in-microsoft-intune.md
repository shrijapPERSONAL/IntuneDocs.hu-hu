---
title: "Az alkalmazás-életciklus áttekintése | Microsoft Intune"
description: "Ismerje meg az Intune által felügyelt alkalmazások életciklusát, kezdve a hozzáadásuktól a végső eltávolításukig."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 86d9de9992003ffd163291035174c8d1e822929a


---

# Az alkalmazás-életciklus áttekintése

Az Intune alkalmazás-életciklusa akkor kezdődik, amikor felvesznek az Intune-ba egy alkalmazást. Ez különböző fázisokon halad át az életciklusa folyamán, amíg el nem távolítják.

![Az alkalmazások életciklusa](./media/app-lifecycle.png "the Intune app lifecycle")

## Hozzáadás

Az alkalmazások telepítésének első lépéseként fel kell vennie az Intune-ban felügyelni és telepíteni kívánt alkalmazást. Habár számos különböző típusú alkalmazás létezik, az alapvető eljárás mindegyik esetében megegyezik. Az Intune-ban [regisztrált eszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md), valamint [az Intune ügyfélszoftverével felügyelt Windows-számítógépekhez](add-apps-for-windows-pcs-in-microsoft-intune.md) egyaránt vehet fel alkalmazásokat.

## Telepítés

Az Intune-ba való felvételét követően [telepítheti az alkalmazást a felügyelni kívánt eszközökre](deploy-apps.md). Az Intune jelentősen leegyszerűsíti ezt a folyamatot, ráadásul az alkalmazás telepítését követően az Intune felügyeleti konzoljából [ellenőrizheti a telepítés sikerességét](monitor-apps-in-microsoft-intune.md). Ezenfelül egyes alkalmazás-áruházak, például az [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) és a [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) alkalmazás-áruházai lehetővé teszik azt is, hogy több licencet vásároljon egyszerre vállalata számára. Az Intune képes szinkronizálni az adatokat ezekkel az áruházakkal, így a felhasználó közvetlenül az Intune felügyeleti konzoljából elvégezheti a telepítést, és nyomon követheti a licenchasználatot.

## Konfigurálás

Az alkalmazások életciklusa során általában az alkalmazás több új verziója is megjelenik. Az Intune számos eszközt kínál a telepített [alkalmazások új verzióra történő frissítésére](update-apps-using-microsoft-intune.md). Ezenfelül bizonyos alkalmazásokban további funkciók konfigurálására is lehetőség van, például:
- Az [iOS-eszközökhöz használható alkalmazáskonfigurálási házirend](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) segítségével meghatározhatja, hogy a kompatibilis iOS-alkalmazások futása esetén mely beállítások lépjenek érvénybe. Az alkalmazásokhoz megadhat például márkajelzési beállításokat, illetve meghatározhatja a kiszolgáló nevét, amelyhez szeretné, hogy az alkalmazás csatlakozzon.
- A [felügyeltböngésző-szabályzatok](manage-internet-access-using-managed-browser-policies.md) segítségével beállításokat adhat meg az Intune által felügyelt, az eszköz alapértelmezett böngészőjét felváltó böngésző számára, illetve korlátozhatja, hogy a felhasználók milyen weboldalakat nyithassanak meg.

## Védelem

Az Intune számos módszert kínál az alkalmazásokban tárolt adatok védelmére. A legfontosabb megoldások a következők:
- A [Feltételes hozzáférés](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) funkció segítségével az Ön által megadott feltételek (például az eszköz típusa, illetve a telepített [eszközmegfelelőségi szabályzat](introduction-to-device-compliance-policies-in-microsoft-intune.md)) alapján szabályozhatja a hozzáférést az e-mailekhez és más szolgáltatásokhoz.
- A [Mobilalkalmazás-kezelés (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) funkció az egyes alkalmazásokkal együttműködve nyújt védelmet az általuk használt vállalati adatok számára. Letilthatja például az adatok nem felügyelet alkalmazások és az Ön által felügyelt alkalmazások közötti másolását, illetve megakadályozhatja, hogy az alkalmazások elinduljanak függetlenített vagy feltört eszközökön.

## Kivonás

Az idő múlásával a telepített alkalmazások elavulttá válnak, így el kell őket távolítani. Az Intune segítségével egyszerűen [kivonhatja a kívánt alkalmazásokat a szolgáltatásból](retire-apps-using-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


