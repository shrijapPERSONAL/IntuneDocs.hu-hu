---
title: "Az Intune alkalmazás-életciklusának áttekintése"
description: "Ismerje meg az Intune által felügyelt alkalmazások életciklusát, kezdve a hozzáadásuktól a végső eltávolításukig."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 87bd0ceed846052444e4dac4366e3a0304b1452c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="overview-of-the-app-lifecycle"></a>Az alkalmazás-életciklus áttekintése

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Az Intune-ban az alkalmazások életciklusa az alkalmazás felvételével kezdődik. Ezt követően az alkalmazás különböző fázisokon halad át egészen addig, amíg el nem távolítják.

![Az alkalmazások életciklusa](./media/app-lifecycle.png "Az alkalmazások életciklusa az Intune-ban")

## <a name="add"></a>Hozzáadás

Az alkalmazások központi telepítésének első lépéseként fel kell vennie az Intune-ba a felügyelni és hozzárendelni kívánt alkalmazásokat. Jóllehet számos különböző típusú alkalmazással dolgozhat, az alapvető eljárás mindegyiknél ugyanaz. Az Intune-ban [regisztrált eszközökhöz](apps-add.md) ([a klasszikus portálon](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)), valamint [az Intune ügyfélszoftverével felügyelt Windows-számítógépekhez](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune) egyaránt vehet fel alkalmazásokat.

## <a name="deploy"></a>telepítése Telepítse a

Az Intune-ba való felvételét követően [hozzárendelheti az alkalmazást a felügyelni kívánt eszközökre](apps-deploy.md) ([a klasszikus portálon](/intune-classic/deploy-use/deploy-apps)). Az Intune jelentős mértékben leegyszerűsíti ezt a folyamatot, ráadásul az alkalmazás telepítését követően az Intune felügyeleti konzoljából [ellenőrizheti a telepítés sikerességét](apps-monitor.md) ([a klasszikus portálon](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)). Emellett egyes alkalmazás-áruházakban, például az [Apple](vpp-apps-ios.md) ([klasszikus portál](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) és a [Windows](windows-store-for-business.md) ([klasszikus portál](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)) alkalmazás-áruházaiban nagyban is vásárolhat alkalmazáslicenceket vállalata számára. Az Intune képes szinkronizálni az adatokat ezekkel az áruházakkal, így Ön közvetlenül az Intune felügyeleti konzoljából hajthatja végre a központi telepítést és követheti nyomon a licenchasználatot.

## <a name="configure"></a>Konfigurálás

Az alkalmazások életciklusa során általában az alkalmazás több új verziója is megjelenik. Az Intune számos eszközt kínál a központilag telepített alkalmazások [verziófrissítésére](apps-add.md) ([a klasszikus portálon](/intune-classic/deploy-use/update-apps-using-microsoft-intune)). Ezen túlmenően bizonyos alkalmazásokhoz további funkciók is konfigurálhatók, például:
- Az [iOS-alkalmazáskonfigurációs szabályzatok](app-configuration-policies-use-ios.md) segítségével ([a klasszikus portálon](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)) meghatározhatja, hogy a kompatibilis iOS-alkalmazások futása esetén mely beállítások lépjenek érvénybe. Az alkalmazásokhoz megadhat például márkajelzési beállításokat, illetve meghatározhatja a kiszolgáló nevét, amelyhez szeretné, hogy az alkalmazás csatlakozzon.
- A [felügyeltböngésző-szabályzatok](app-configuration-managed-browser.md) segítségével ([a klasszikus portálon](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)) konfigurálhatja az Intune által felügyelt, az eszközök alapértelmezett böngészőjét felváltó böngésző beállításait, illetve korlátozhatja, hogy a felhasználók milyen weboldalakat nyithatnak meg.

## <a name="protect"></a>Védelem

Az Intune számos módszert kínál az alkalmazásokban tárolt adatok védelmére. A legfontosabb megoldások a következők:
- A [feltételes hozzáférés](conditional-access.md) ([a klasszikus portálon](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) az Ön által megadott feltételek alapján szabályozza az email és egyéb szolgáltatások elérését. Ilyen feltétel lehet az eszköz típusa, vagy az, hogy megfelel-e a központilag telepített [eszközmegfelelőségi szabályzatnak](device-compliance.md) ([a klasszikus portálon](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)).
- Az [alkalmazásvédelmi szabályzatok](app-protection-policy.md) ([a klasszikus portálon](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) az egyes alkalmazásokkal együttműködve nyújtanak védelmet az általuk használt vállalati adatok számára. Letilthatja például az adatok másolását a nem felügyelt és a felügyelt alkalmazások között, illetve megakadályozhatja az alkalmazások futtatását függetlenített vagy feltört eszközökön.

## <a name="retire"></a>Kivonás

Az idő múlásával a telepített alkalmazások elavulttá válnak, így el kell őket távolítani. Az Intune segítségével egyszerűen [kivonhatja a kívánt alkalmazásokat a szolgáltatásból](device-management.md) ([a klasszikus portálon](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
