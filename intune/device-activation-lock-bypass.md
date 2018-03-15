---
title: "iOS aktiválási zárának megkerülése az Intune-nal"
titlesuffix: Microsoft Intune
description: "Az Intune használata az iOS aktiválási zárjának megkerülésére a zárolt eszközök eléréséhez."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ec8c1a25acfa7c84c62d3686c5f00e7398d573d
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Aktiválási zár megkerülése felügyelt iOS-eszközökön az Intune-nal


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune szolgáltatással kezelhető az iOS aktiválási zára, amely az iOS 8.0 és újabb rendszerű eszközök Find My iPhone alkalmazásának egyik funkciója. Ha a felhasználó megnyitja a Find My iPhone alkalmazást egy eszközön, az aktiválási zár automatikusan engedélyezve lesz. Az engedélyezése után meg kell adni a felhasználó Apple ID azonosítóját és jelszavát ahhoz, hogy el lehessen végezni a következők bármelyikét:

- A Find My iPhone alkalmazás kikapcsolása
- Az eszköz alaphelyzetbe állítása
- Az eszköz újraaktiválása

## <a name="how-activation-lock-affects-you"></a>Az aktiválási zár hatásai

Az aktiválási zár segít az iOS-eszközök védelmének biztosításában, és növeli a megtalálásuk esélyét azok elvesztésekor vagy ellopásakor, ugyanakkor ez a funkció számos kihívást is jelenthet Ön, mint rendszergazda számára. Például:

- Egy felhasználó beállítja az aktiválási zárat egy eszközön. A felhasználó később elhagyja a céget és visszaszolgáltatja az eszközt. A felhasználó Apple ID azonosítója és jelszava nélkül semmilyen módon nem lehet újraaktiválni az eszközt.
- Szüksége van egy jelentésre az összes eszközről, amelyen engedélyezve van az aktiválási zár.
- Néhány eszközt másik részleghez szeretne rendelni a szervezetben egy eszközfrissítés során. Csak azokat az eszközöket lehet újból hozzárendelni, amelyeken nincs engedélyezve az aktiválási zár.

Az Apple az ilyen problémák megoldására vezette be az aktiválási zár megkerülését az iOS 7.1-ben. Az aktiválási zár megkerülése a felhasználó Apple-azonosítója és jelszava nélkül teszi lehetővé az aktiválási zár eltávolítását a felügyelt eszközökről. A felügyelt eszközök létre tudnak hozni egy eszközspecifikus aktiválásizár-áthidaló kódot, mely az Apple aktiválási kiszolgálóján van tárolva.

>[!TIP]
>Az iOS-eszközök felügyelt módja lehetővé teszi az eszközök az Apple Configurator eszközzel való zárolását, így meghatározott üzleti célokra korlátozva annak funkcióit. A felügyelt mód csak vállalati tulajdonú eszközökhöz használható.

Az aktiválási zárról további információt az [Apple webhelyén](https://support.apple.com/HT201365) olvashat.

## <a name="how-intune-helps-you-manage-activation-lock"></a>Az aktiválási zár kezelése az Intune-nal
Az Intune a felügyelt iOS 8.0 vagy újabb rendszerű eszközök aktiválási zárának állapotát is le tudja kérdezni. Kizárólag a felügyelt eszközök esetében az Intune képes lekérdezni az aktiválásizár-áthidaló kódot, és közvetlenül kiadni azt az eszköznek. Ha törölték az eszköz adatait, üres felhasználónévvel és a kódot jelszóként használva közvetlenül hozzáférhet az eszközhöz.

**Az aktiválási zárnak az Intune-nal történő felügyelete a következő üzleti előnyökkel jár:**

- A felhasználó élvezheti a Find My iPhone alkalmazás biztonsági előnyeit.
- Lehetővé teheti, hogy a felhasználó annak tudatában végezhesse a munkáját, hogy az eszközt ki lehet vonni vagy fel lehet oldani a zárolását, ha a használatának módosítására van szükség.

## <a name="before-you-start"></a>Előkészületek
Az eszközök aktiválási zárának megkerüléséhez azt előbb az alábbi lépéseket követve engedélyeznie kell:

1. Eszközkorlátozási profil konfigurálása iOS-hez az Intune-ban az [Eszközkorlátozási profilok konfigurálása](/intune-azure/configure-devices/how-to-configure-device-restrictions) szakasz információi alapján.
2. Az **Általános** beállítások szakaszában található [iOS-re vonatkozó eszközkorlátozási beállítások](device-restrictions-ios.md) között engedélyezze az **Aktiválási zár** lehetőséget.
3. Mentse a profilt, majd [rendelje](device-profile-assign.md) hozzá azokhoz az eszközökhöz, amelyeken kezelni kívánja az aktiválási zár megkerülését.


## <a name="how-to-use-activation-lock-bypass"></a>Az aktiválási zár megkerülésének használata

>[!IMPORTANT]
>Az eszköz aktiválási zárának megkerülése után a Find My iPhone alkalmazás megnyitásakor automatikusan életbe lép egy újabb aktiválási zár. Ezért **csak akkor kövesse ezt az eljárást, ha az eszköz a birtokában van**.

Az Intune-ban az **Aktiválási zár megkerülése** távoli eszközművelet a felhasználó Apple-azonosítója és jelszava nélkül távolítja el az aktiválási zárat az iOS-eszközről. Az aktiválási zár megkerülése után az eszköz ismét bekapcsolja az aktiválási zárat a Find My iPhone alkalmazás elindulásakor. Csak akkor kerülje meg az aktiválási zárat, ha fizikailag is hozzáfér az eszközhöz.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Minden eszköz** lehetőséget.
5. A kezelt eszközök listáján válasszon egy felügyelt iOS-eszközt, és válassza a **...Továbbiak** lehetőséget, majd az **Aktiválási zár megkerülése** távoli eszközműveletet.

## <a name="next-steps"></a>További lépések

A zárolásfeloldási kérés állapotát az **Eszközök kezelése** munkaterhelésben az eszköz részleteit megjelenítő oldalon ellenőrizheti.
