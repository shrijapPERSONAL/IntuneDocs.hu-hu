---
title: "Mobile Threat Defense-összekötő engedélyezése az Intune-nal"
titleSuffix: Intune on Azure
description: "Engedélyezheti a Mobile Threat Defense-összekötőt az Intune-ban."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 38fb9977ed8af05380a265ee254259acef7b43f0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="enable-mobile-threat-defense-in-intune"></a>Mobile Threat Defense engedélyezése az Intune-ban

A Mobile Threat Defense (MTD) Intune-beli engedélyezéséhez az Intune-összekötő előzetes konfigurálására van szükség az MTD-megoldáskonzolon.

## <a name="to-enable-the-mtd-connector"></a>Az MTD-összekötő engedélyezése

1. Az [Azure Portalon](https://portal.azure.com) jelentkezzen be az Intune-os hitelesítő adataival. Miután sikeresen bejelentkezett, megjelenik az **Azure irányítópultja**.

2. Az **Azure-irányítópulton** válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Ha az **Intune** elemre kattint, megnyílik az **Intune irányítópultja**.

4. Az **Intune-irányítópulton** válassza az **Eszközmegfelelőség**, majd a **Beállítás** szakaszban a **Mobile Threat Defense** elemet.

5. A **Mobile Threat Defense** panelen válassza a **Hozzáadás** elemet.

6. A legördülő listában jelölje ki a saját MTD-megoldását mint **Beállítani kívánt Mobile Threat Defense-összekötőt**.

    ![Az MTD beállítása az Azure-beli Intune-portálon](./media/enable-mtd-connector-1.png)

7. A szervezet igényeinek megfelelően adja meg a kapcsolós beállításokat.

## <a name="mtd-toggle-options"></a>Az MTD kapcsolós megoldásai

A cég igényei alapján eldöntheti, hogy az MTD mely kapcsolós beállításait kell engedélyeznie. További részletek:

- **Android 4.1+ rendszerű eszközök csatlakoztatása az [MTD-partner neve] for Work MTD-hez**: ezen beállítás engedélyezésével utasíthatja az Android 4.1+ rendszerű eszközöket a biztonsági kockázatok jelentésére az Intune-nak.
    - **Nem megfelelőnek minősítés, ha nem érkezik adat**: ha az Intune nem kap adatokat egy ilyen platformos eszközről az MTD-partnertől, az eszközt nem megfelelőnek minősíti.
<br></br>
- **iOS 8.0+ rendszerű eszközök csatlakoztatása az [MTD partner name] for Work MTD-hez**: ezen beállítás engedélyezésével utasíthatja az iOS 8.0+ rendszerű eszközöket a biztonsági kockázatok jelentésére az Intune-nak.
    - **Nem megfelelőnek minősítés, ha nem érkezik adat**: ha az Intune nem kap adatokat egy ilyen platformos eszközről az MTD-partnertől, az eszközt nem megfelelőnek minősíti.
<br></br>
- **Nem támogatott operációsrendszer-verziók blokkolása**: a legalacsonyabb támogatott verziónál régebbi rendszerű eszközök blokkolva lesznek.

- **Partner ennyi nap után nem válaszol**: az Intune ennyi napnyi tétlenség után feltételezi, hogy a partner a kapcsolat megszakadása miatt nem válaszol. Az Intune nem veszi figyelembe a nem válaszoló MTD-partnerek megfelelőségi állapotát.

> [!IMPORTANT] 
> Az MTD-alkalmazásokat még az eszközmegfelelési és a feltételes hozzáférési szabályzatok létrehozása előtt fel kell vennie és hozzá kell rendelnie. Ez biztosítja, hogy az MTD-alkalmazás még az e-mailekhez és az egyéb céges erőforrásokhoz való hozzáférés előtt telepítésre kész és elérhető legyen a végfelhasználók számára.

> [!TIP]
> A Mobile Threat Defense panelen látható a **Kapcsolat állapota** és a **Legutóbb szinkronizálva**, mely utóbbi az Intune és az MTD-partner közötti szinkronizálásra vonatkozik.

## <a name="next-steps"></a>További lépések

[A Mobile Threat Defense eszközmegfelelési szabályzatának létrehozása az Intune-ban](mtd-device-compliance-policy-create.md)
