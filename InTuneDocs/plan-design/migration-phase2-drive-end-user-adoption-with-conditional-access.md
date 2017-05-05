---
title: "A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel | Microsoft Docs"
description: "Ez a cikk azt ismerteti, hogyan lehet a feltételes hozzáféréssel ösztönözni az Intune-regisztrációt."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 12584743534a76d0b2ce92e5de6cb5f916453938
ms.lasthandoff: 04/25/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>2. fázis: A végfelhasználói bevezetés ösztönzése feltételes hozzáféréssel

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

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

-   További információk a [feltételes hozzáférésről](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access).

## <a name="task-list-for-conditional-access"></a>Feladatlista a feltételes hozzáféréshez

### <a name="task-1-get-ready-for-intune-conditional-access"></a>1. feladat: Felkészülés az Intune feltételes hozzáférési funkciójára

-   Ismerje meg, [hogyan konfigurálhatja a feltételes hozzáférést](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-set-up-intune-conditional-access"></a>2. feladat: Az Intune feltételes hozzáférési funkciójának beállítása

A feltételes hozzáférési szabályzatok alábbi típusaira kattintva további információt kaphat:

-   [Az Exchange Online és az új dedikált Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [A helyszíni Exchange és a régi dedikált Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype Vállalati online verzió](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [E-mail-hozzáférési példaszituációk](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>További lépések

[2. fázis: A szokásos migrációs ciklus](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)

