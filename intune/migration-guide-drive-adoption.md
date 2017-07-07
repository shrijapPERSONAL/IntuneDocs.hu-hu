---
title: "A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel"
description: "Ez a cikk azt ismerteti, hogyan lehet a feltételes hozzáféréssel ösztönözni az Intune-regisztrációt."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Az Intune feltételes hozzáférési funkcióival – például a levelezés letiltásával a nem regisztrált eszközökön – ösztönözhető a regisztráció és a megfelelőség biztosítása, de ez nem feltétele a sikeres migrációnak: ezt inkább az áttérési célértékek és a biztonsági követelmények alapján lehet megítélni.

## <a name="migration-campaign-with-conditional-access"></a>Migrációs kampány feltételes hozzáféréssel

Egy jellemző példán keresztül mutatjuk be, hogyan segítheti elő a feltételes hozzáférés a migrációs kampányt:

1.  Állítson be feltételes hozzáférési szabályokat minden felhasználóra, de konkrétan zárja ki azokat a felhasználókat, akiknek át kell állniuk a régi MDM-szolgáltatóról. Létrehozhat egy Azure AD-beli felhasználói csoportot is a feltételes hozzáférésből kizárt felhasználóknak,

2.  amelyből majd eltávolítja a migrációt végrehajtókat.

3.  A migráció befejeztével az összes feltételes hozzáférési szabályzatot úgy konfigurálja, hogy alapértelmezés szerint tiltsák a hozzáférést, kivéve ha az Intune engedélyezi azt.

### <a name="advantages"></a>Előnyök

-   Hozzáférés-vezérlést biztosít az új, illetve a korábbi megoldással nem felügyelt felhasználói fiókoknak is.

-   Türelmi időszakot kínál az előző megoldás felhasználóinak a migrációra.

-   Minimálisra szorítja a produktivitás csökkenését.

### <a name="disadvantages"></a>Hátrányok

-   Előfordulhat, hogy a korábbi megoldás felhasználói nem felügyelt eszközökről hozzáférnek az erőforrásokhoz, amíg számukra nincs engedélyezve a feltételes hozzáférés.

> [!TIP]
> Ez csak egy megközelítés a sok közül: választhat egyszerűbb megoldást is, amely minden feltételes hozzáférést letilt, amíg az összes felhasználó végre nem hajtotta a regisztrációt, vagy szigorúbbat, amely az első pillanattól kezdve teljes megfelelőséget követel meg a hozzáféréshez.

-   További információk a [feltételes hozzáférésről](/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Feladatlista a feltételes hozzáféréshez

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>1. feladat: A feltételes hozzáférés implementálási módjának meghatározása

[A feltételes hozzáférés szokásos használati módjai](/intune/conditional-access-intune-common-ways-use).

### <a name="task-2-set-up-intune-conditional-access"></a>2. feladat: Az Intune feltételes hozzáférési funkciójának beállítása

Válasszon egyet az alábbi lehetőségek közül:

-   [Feltételes hozzáférés konfigurálása az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [A helyszíni Exchange-összekötő telepítése az Intune-nal](/intune/exchange-connector-install)

-   [Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása az Exchange Online-hoz](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása a SharePoint Online-hoz](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Modern hitelesítés nélküli alkalmazások blokkolása (ADAL)](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>További lépések

[A szokásos áttelepítési ciklus](migration-guide-cycle.md)
