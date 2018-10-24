---
title: A Mobile Threat Defense-összekötő engedélyezése a Microsoft Intune-ban
titleSuffix: ''
description: A Mobile Threat Defense (MTD) partner és a Microsoft Intune közötti összekötő engedélyezése.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e2172c1cd066e99f3634dd856538671207cf1ed0
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48232239"
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

- **Android 4.1+ rendszerű eszközök csatlakoztatása az [MTD-partner neve] for Work MTD-hez**: ezen beállítás engedélyezésével utasíthatja az Android 4.1+ rendszerű eszközöket a biztonsági kockázatok jelentésére az Intune-nak.
    - **Nem megfelelőnek minősítés, ha nem érkezik adat**: ha az Intune nem kap adatokat egy ilyen platformos eszközről az MTD-partnertől, az eszközt nem megfelelőnek minősíti.
<br></br>
- **iOS 8.0+ rendszerű eszközök csatlakoztatása az [MTD partner neve] for Work MTD-hez**: ezen beállítás engedélyezésével utasíthatja az iOS 8.0+ rendszerű eszközöket a biztonsági kockázatok jelentésére az Intune-nak.
    - **Nem megfelelőnek minősítés, ha nem érkezik adat**: ha az Intune nem kap adatokat egy ilyen platformos eszközről az MTD-partnertől, az eszközt nem megfelelőnek minősíti.
<br></br>
- **Alkalmazásszinkronizálás engedélyezése iOS-eszközök számára**: Engedélyezi a Mobile Threat Defense-partner számára, hogy iOS-alkalmazások metaadatait kérje le az Intune-ból fenyegetéselemzés céljából.

- **Nem támogatott operációsrendszer-verziók blokkolása**: a legalacsonyabb támogatott verziónál régebbi rendszerű eszközök blokkolva lesznek.

- **Partner ennyi nap után nem válaszol**: az Intune ennyi napnyi tétlenség után feltételezi, hogy a partner a kapcsolat megszakadása miatt nem válaszol. Az Intune nem veszi figyelembe a nem válaszoló MTD-partnerek megfelelőségi állapotát.

> [!IMPORTANT] 
> Az MTD-alkalmazásokat még az eszközmegfelelési és a feltételes hozzáférési szabályzatok létrehozása előtt fel kell vennie és hozzá kell rendelnie. Ez biztosítja, hogy az MTD-alkalmazás még az e-mailekhez és az egyéb céges erőforrásokhoz való hozzáférés előtt telepítésre kész és elérhető legyen a végfelhasználók számára.

> [!TIP]
> A Mobile Threat Defense panelen látható a **Kapcsolat állapota** és a **Legutóbb szinkronizálva**, mely utóbbi az Intune és az MTD-partner közötti szinkronizálásra vonatkozik.
