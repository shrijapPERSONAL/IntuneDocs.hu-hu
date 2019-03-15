---
title: A Microsoft Intune Mobile Threat Defense-összekötő engedélyezése |} A Microsoft Intune-ban
description: A Mobile Threat Defense (MTD) partner és a Microsoft Intune közötti összekötő engedélyezése.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1f4e920719b26cf90292a927a129b4fae2b17b45
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394018"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>A Mobile Threat Defense-összekötő engedélyezése az Intune-ban

> [!NOTE] 
> Ez a témakör minden Mobile Threat Defense-partnerre vonatkozik.

A Mobile Threat Defense (MTD) beállítása során konfigurált egy, az MTD-partnerkonzolra vonatkozó fenyegetésosztályozási szabályzatot, és létrehozta az eszközmegfelelőségi szabályzatot az Intune-ban. Ha már konfigurálta az Intune-összekötőt az MTD-partnerkonzolon, engedélyezheti az MTD-kapcsolatot az Intune-ban.

## <a name="to-enable-the-mtd-connector"></a>Az MTD-összekötő engedélyezése

1. Az [Azure Portalon](https://portal.azure.com) jelentkezzen be az Intune-os hitelesítő adataival. Miután sikeresen bejelentkezett, megjelenik az **Azure irányítópultja**.

2. Az **Azure-irányítópulton** válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Ha az **Intune** elemre kattint, megnyílik az **Intune irányítópultja**.

4. Az **Intune-irányítópulton** válassza az **Eszközmegfelelőség**, majd a **Beállítás** szakaszban a **Mobile Threat Defense** elemet.

5. A **Mobile Threat Defense** panelen válassza a **Hozzáadás** elemet.

6. A legördülő listában jelölje ki a saját MTD-megoldását mint **Beállítani kívánt Mobile Threat Defense-összekötőt**.

    ![Az MTD beállítása az Azure-beli Intune-portálon](./media/enable-mtd-connector-1.png)

7. A szervezet igényeinek megfelelően adja meg a kapcsolós beállításokat. Az elérhető kapcsolós megoldások az MTD-partnertől függenek.

## <a name="mtd-toggle-options"></a>Az MTD kapcsolós megoldásai

A cég igényei alapján eldöntheti, hogy az MTD mely kapcsolós beállításait kell engedélyeznie. További részletek:

- **Csatlakozás Android 4.1 + eszközök az [MTD partner name] for Work MTD-hez**: Ha engedélyezi ezt a beállítást, az akkor Android 4.1 + rendszerű eszközök bejelenthetik a biztonsági kockázatokat az Intune-bA biztonsági másolatot.
    - **Nem megfelelőnek minősítés, ha nem érkezik adat**: Ha az Intune nem kap adatokat egy ilyen platformos eszközről az MTD-partnertől, fontolja meg az eszköz nem megfelelő.
<br></br>
- **Csatlakozás iOS 8.0 és újabb eszközökre az [MTD partner name] for Work MTD-hez**: Ha engedélyezi ezt a beállítást, akkor is iOS 8.0 + eszközök bejelenthetik a biztonsági kockázatokat vissza az Intune-hoz.
    - **Nem megfelelőnek minősítés, ha nem érkezik adat**: Ha az Intune nem kap adatokat egy ilyen platformos eszközről az MTD-partnertől, fontolja meg az eszköz nem megfelelő.
<br></br>
- **IOS eszközök Alkalmazásszinkronizálásának engedélyezése**: Lehetővé teszi, hogy a Mobile Threat Defense-partner threat elemzési célokra használja az Intune az iOS-alkalmazások metaadatait kérhet.

- **Nem támogatott operációsrendszer-verziók letiltása**: Annak letiltása, ha az eszköz operációs rendszer fut, kevesebb, mint a minimális támogatott verziója.

- **Ennyi nap múlva partner nem válaszol**: Ennyi nap inaktivitás után tekinti úgy a partner a kapcsolat megszakadása miatt nem válaszol az Intune. Az Intune nem veszi figyelembe a nem válaszoló MTD-partnerek megfelelőségi állapotát.

> [!IMPORTANT] 
> Az MTD-alkalmazásokat még az eszközmegfelelési és a feltételes hozzáférési szabályzatok létrehozása előtt fel kell vennie és hozzá kell rendelnie. Ez biztosítja, hogy az MTD-alkalmazás még az e-mailekhez és az egyéb céges erőforrásokhoz való hozzáférés előtt telepítésre kész és elérhető legyen a végfelhasználók számára.

> [!TIP]
> A Mobile Threat Defense panelen látható a **Kapcsolat állapota** és a **Legutóbb szinkronizálva**, mely utóbbi az Intune és az MTD-partner közötti szinkronizálásra vonatkozik.
