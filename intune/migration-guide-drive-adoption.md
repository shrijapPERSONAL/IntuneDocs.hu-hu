---
title: A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel
titleSuffix: Microsoft Intune
description: Megtudhatja, hogyan ösztönözheti a Microsoft Intune-regisztrációt a feltételes hozzáféréssel.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: a37d6dac24049a10b5abaed41a44c0c391b095e6
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050475"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel a Microsoft Intune-ban

Az Intune feltételes hozzáférési funkcióival – például a levelezés letiltásával a nem regisztrált eszközökön – ösztönözhető a regisztráció és a megfelelőség biztosítása, de ez nem feltétele a sikeres migrációnak. ezt inkább az áttérési célértékek és a biztonsági követelmények alapján lehet megítélni.

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


Ez csak egy megközelítés a sok közül: választhat egyszerűbb megoldást is, amely minden feltételes hozzáférést letilt, amíg az összes felhasználó végre nem hajtotta a regisztrációt, vagy szigorúbbat, amely az első pillanattól kezdve teljes megfelelőséget követel meg a hozzáféréshez.

-   További információk a [feltételes hozzáférésről](conditional-access.md).

## <a name="task-list-for-conditional-access"></a>Feladatlista a feltételes hozzáféréshez

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>1. feladat: Annak eldöntése, hogyan kívánja a feltételes hozzáférés alkalmazása

[A feltételes hozzáférés szokásos használati módjai](conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>2. feladat: Az Intune feltételes hozzáférés beállítása

Válasszon egyet az alábbi lehetőségek közül:

-   [Feltételes hozzáférés konfigurálása az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [A helyszíni Exchange-összekötő telepítése az Intune-nal](exchange-connector-install.md)

-   [Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása az Exchange Online-hoz](app-based-conditional-access-intune-create.md)

-   [Alkalmazásalapú feltételes hozzáférési szabályzatok beállítása a SharePoint Online-hoz](app-based-conditional-access-intune-create.md)

-   [Modern hitelesítés nélküli alkalmazások blokkolása (ADAL)](app-modern-authentication-block.md)

## <a name="next-steps"></a>További lépések

További tudnivalókat a [szokásos migrálási ciklus](migration-guide-cycle.md) ismertetőjében talál.
