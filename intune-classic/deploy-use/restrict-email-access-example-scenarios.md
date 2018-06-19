---
title: Példák az e-mail-védelem használatára
description: Az alábbiakban néhány példaforgatókönyvet és a feltételes hozzáféréssel történő megvalósításuk módját találhatja.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3116cfdb6b1ea153d914630a23e0db82a8c31d85
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31019415"
---
# <a name="protect-access-to-email-with-microsoft-intune-example-scenarios"></a>Az e-mailekhez való hozzáférés védelme a Microsoft Intune használatával – Példaforgatókönyvek

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a>1. forgatókönyv: Felhasználók megakadályozása az Exchange Online nem megfelelő eszközökkel való elérésében
### <a name="scenario-requirements"></a>Forgatókönyv követelményei
- A **Könyvelés** Azure Active Directory biztonsági csoportban lévő összes felhasználó számára le kell tiltani az Exchange Online elérését, ha eszközük nem felel meg egy telepített megfelelőségi szabályzatnak.
- Ha tartozik a csoportba olyan felhasználó, akinek az eszközeit az Intune nem támogatja, számára le kell tiltani az Exchange Online elérését a kérdéses eszközökön.
- A **Pénzügy** Azure Active Directory biztonsági csoportba tartozó egyik felhasználóra sem lehet érvényes a szabályzat, még akkor sem, ha az adott felhasználó a **Könyvelés** biztonsági csoportban is szerepel.

Ennek eléréséhez hozzon létre egy feltételes hozzáférési szabályzatot az Exchange Online rendszerre vonatkozóan a következő beállításokkal:

- Válassza a **Feltételes hozzáférési szabályzat engedélyezése** lehetőséget.

- Válassza ki azt a platformot, amelyhez hozzáférést szeretne biztosítani a modern hitelesítést használó alkalmazásokból.
- Az Exchange ActiveSync alkalmazások esetében jelölje be a következőket: **A nem megfelelő eszközök letiltása a Microsoft Intune által támogatott platformokon** és **Minden egyéb eszköz letiltása a Microsoft Intune által nem támogatott platformokon.**
-   A **Célcsoport** szakasz **Kiválasztott biztonsági csoportok** területén válassza a **Könyvelés** felhasználói csoportot.

-   A **Kivétel alá eső csoportok** szakasz a **Kiválasztott biztonsági csoportok** területén válassza a **Pénzügy** felhasználói csoportot.


Ebben a forgatókönyvben a következő folyamattal határozzuk meg, hogy mely eszközök érhessék el az Exchange Online-t:

![Az eszközök általi elérés folyamata](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a>2. forgatókönyv: A helyi Exchange-et elérő összes iOS-eszközt az Intune-nak kell felügyelnie
### <a name="scenario-requirements"></a>Forgatókönyv követelményei
- A helyi Exchange-hez kizárólag iOS-rendszerrel működő eszközöknek lehessen hozzáférése.
- Ahhoz, hogy az eszközöket használni lehessen az Exchange elérésére, regisztrálni kell őket az Intune-ban, illetve meg kell felelniük a megfelelőségi szabályzat előírásainak.

Ennek eléréséhez hozzon létre egy feltételes hozzáférési szabályzatot a helyi Exchange-re vonatkozóan a következő beállításokkal:

- Válassza **A helyi Exchange-hez való hozzáférés letiltása a levelezőalkalmazásoknak, ha az eszköz nem kompatibilis vagy nincs regisztrálva a Microsoft Intune-ba** lehetőséget. Ezzel a beállítással engedélyezi a feltételes hozzáférési szabályzatot, amely gondoskodik arról, hogy csak azok az eszközök férjenek hozzá az Exchange-hez, amelyeket regisztráltak a Microsoft Intune-ban, illetve, amelyek megfelelnek a megfelelőségi szabályzat előírásainak.

- Az Exchange Active Sync speciális beállításainak megadásához hozza létre a következőket:

  -   Platformkivétel, amely lehetővé teszi, hogy az iOS rendszerű eszközök hozzáférjenek az Exchange-hez.   

  -   Alapértelmezett szabály, amely meghatározza, hogy amennyiben egy adott eszközre nem vonatkoznak a platformkivétel szabályai, az eszköz ne férhessen hozzá az Exchange-hez. Ez a szabály gondoskodik arról, hogy az Exchange-hez kizárólag az iOS rendszerű eszközök férjenek hozzá.

A következő folyamattal határozható meg, hogy mely eszközök férhetnek hozzá az Exchange-hez:

![Az eszközök általi elérés folyamata](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a>3. forgatókönyv: Az Android-eszközök nem férnek hozzá a helyi Exchange-hez
### <a name="scenario-requirements"></a>Forgatókönyv követelményei
- Az Android-eszközök ne férhessenek hozzá az Exchange-hez.
- Az összes többi támogatott eszköz hozzáférhet az Exchange-hez, ha az Intune felügyeli őket.

Ennek eléréséhez hozzon létre egy feltételes hozzáférési szabályzatot a helyi Exchange rendszerre vonatkozóan a következő beállításokkal:

-   Válassza **A helyi Exchange-hez való hozzáférés letiltása a levelezőalkalmazásoknak, ha az eszköz nem kompatibilis vagy nincs regisztrálva a Microsoft Intune-ba** lehetőséget. A beállítás kiválasztásával megköveteli az eszközök regisztrálását az Intune-ban, valamint a megfelelőségi szabályzat előírásainak betartását.

- Az Exchange Active Sync speciális beállításainak megadásához hozza létre a következőket:
  -   Platformkivétel, amely blokkolja az Android rendszerű eszközök hozzáférését az Exchange-hez. Ez a szabály gondoskodik arról, hogy az Android-eszközök ne érhessék el az Exchange-et.

  -   Alapértelmezett szabály, amely meghatározza, hogy ha egy eszközre nem érvényes más szabály, akkor engedélyezni kell számára az Exchange-hez való hozzáférést. Ez az alapértelmezett szabály gondoskodik arról, hogy azok az eszközök, amelyeken nem Android, hanem a Microsoft Intune által támogatott más platform fut, hozzáférhessenek az Exchange-hez. Azonban ezeket is regisztrálni kell az Intune-ban, illetve ezeknek is meg kell felelniük a megfelelőségi szabályzat előírásainak.

A következő folyamattal határozható meg, hogy mely eszközök férhetnek hozzá az Exchange-hez:

![Az eszközök általi elérés folyamata](./media/ConditionalAccess8-4.png)
