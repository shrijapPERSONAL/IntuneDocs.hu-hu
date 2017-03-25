---
title: "Meg nem felelés esetén végrehajtandó műveletek"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Útmutató meg nem felelés esetén végrehajtandó műveletek létrehozásához"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Meg nem felelés esetén végrehajtandó műveletek létrehozása

A **Meg nem felelés esetén alkalmazandó műveletek** használatával időrendbe állított műveleteket alkalmazhat a nem megfelelőnek minősülő eszközökre. Például e-mailben értesítheti a nem megfelelő eszközök felhasználóit, vagy feltételes hozzáférés funkcióval letilthatja az eszközök hozzáférését a vállalati erőforrásokhoz.

## <a name="use-case-scenario"></a>Használatieset-forgatókönyvek

Alapértelmezés szerint ha egy Intune eszközmegfelelőségi szabályzat nem megfelelőként észlel egy eszközt, a feltételes hozzáférés azonnal letiltja az eszközt, a felhasználó pedig e-mailben kapja meg az utasításokat, amelyekkel az eszközt újra megfelelővé teheti. A **Meg nem felelés esetén alkalmazandó műveletekkel** rugalmasabban dönthet arról, hogy mi történjen, ha egy eszköz nem megfelelő. Például úgy is dönthet, hogy nem tiltja le azonnal az eszközt, hanem egy türelmi időszakot határoz meg az eszköz megfelelőségének visszaállítására.

Kétféle művelet használható:

-   A felhasználó értesítése e-mailben

-   A vállalati erőforrásokhoz való hozzáférés letiltása feltételes hozzáféréssel

## <a name="notify-the-user-via-email"></a>A felhasználó értesítése e-mailben

Előre elkészített alapértelmezett e-mail-sablonok közül is választhat, vagy létrehozhat teljesen egyéni e-mail-értesítőt is. Testre szabhatja az e-mail tárgyát, az üzenet szövegét, a vállalati logót, a kapcsolattartási adatokat, és további címzetteket adhat meg.

## <a name="block-corporate-resource-access-through-conditional-access"></a>A vállalati erőforrásokhoz való hozzáférés letiltása feltételes hozzáféréssel

Megadhatja, hogy hány napon belül legyen letiltva az eszköz számára a vállalati erőforrásokhoz való hozzáférés. A letiltást azonnali kezdettel is megadhatja, de meghatározhat egy türelmi időszakot is, amelyen belül az eszköz megfelelőségét vissza kell állítani.

## <a name="before-you-begin"></a>Előkészületek

Meg nem felelés esetén alkalmazandó műveletek beállításához rendelkeznie kell legalább egy eszközmegfelelőségi szabályzattal.

-   További információ eszközmegfelelőségi szabályzat létrehozásáról az alábbi rendszerekhez:

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

A vállalati erőforrásokhoz való hozzáférés letiltásához használandó eszközmegfelelőségi szabályzatok felállításához már üzembe helyezett EMS feltételes hozzáféréssel kell rendelkeznie.

- További információ az [EMS feltételes hozzáférés beállításáról](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Ezen kívül létre kell hoznia az értesítési üzenethez használandó üzenetsablont is. Az értesítési üzenet sablonjára a meg nem felelés esetén alkalmazandó műveletek létrehozásánál lesz szüksége, melynek része lehet a felhasználónak küldött e-mail.

### <a name="to-add-a-notification-message-template"></a>Értesítési üzenet sablonjának hozzáadásához:

Az **Eszközmegfelelőségi szabályzatok** panelen:

1.  A **Felügyelet** területen válassza az **Értesítések** elemet az Értesítési üzenetek sablonjai panel megnyitásához.

    ![Értesítési sablon hozzáadása](../media/afnc-1.png)

2.  Válassza a **Hozzáadás** lehetőséget. Ezt követően meg kell adnia az alábbi adatokat:

    a.  Leírás

    b.  Forrás

    c.  Tárgy

    d.  Üzenet

    e.  E-mail fejléce – a cég emblémájának megjelenítése

    f.  E-mail lábléce – a cég emblémájának megjelenítése

    g.  E-mail lábléce – kapcsolatfelvételi adatok megjelenítése

     ![Az értesítési üzenet sablonja](../media/afnc-2.png)

Ha megadta a szükséges információkat, kattintson a **Létrehozás** lehetőségre. Az értesítési üzenet sablonja használatra kész.

> [!NOTE] 
> A korábban létrehozott értesítési sablonokat szerkesztheti is.

## <a name="to-create-actions-for-non-compliance"></a>Meg nem felelés esetén végrehajtandó műveletek létrehozása

Művelet hozzáadását elvégezheti az új eszközmegfelelőségi szabályzat létrehozása előtt, vagy a már létező eszközmegfelelőségi szabályzat szerkesztésével is.

1.  Az **Eszközmegfelelőségi szabályzatok** panel **Kezelés** területén válassza a **Szabályzatok** elemet.

2.  Kattintson a kiválasztani kívánt eszközmegfelelőségi szabályzatra.

    ![Megfelelőségi szabályzatok](../media/afnc-3.png)

3.  A megnyíló **eszközmegfelelőségi szabályzat tulajdonságai** panelen válassza a **Meg nem felelési műveletek** lehetőséget.

4.  A műveletek paramétereinek megadásához a Meg nem felelési műveletek panelen válassza a **Hozzáadás** elemet.

    ![Meg nem felelési műveletek panel](../media/afnc-4.png)

A Meg nem felelési műveletek a következők:

-   **Feltételes hozzáférési szabályzat kényszerítése**

-   **E-mail küldése a végfelhasználónak**

### <a name="enforce-conditional-access-policy"></a>Feltételes hozzáférési szabályzat kényszerítése

A művelet hozzáadása meg nem feleléshez:

1.  A **Meg nem felelési műveletek** panelen válassza a **Hozzáadás** lehetőséget.

2.  A **Művelet paraméterei** panelen a legördülő listából válassza a **Feltételes hozzáférési szabályzat kényszerítése** elemet.

3.  Az **Ütemezés** területen adja meg, hogy a feltételes hozzáférési szabályzat kényszerítése hány nap múlva lépjen érvénybe (0-255). Ha a napok számánál **0** értéket ad meg, akkor a feltételes hozzáférés **azonnal** letiltja a hozzáférést a vállalati erőforrásokhoz, amennyiben az eszköz nem felel meg az eszközmegfelelőségi szabályzatnak.

    ![Meg nem felelési műveletek ütemezése](../media/afnc-5.png)

4.  A **Műveletek** panelen válassza a **Hozzáadás**, majd az **OK** lehetőséget.

5.  Az **Eszközmegfelelőségi szabályzat tulajdonságai** panelen válassza a **Mentés** elemet.

### <a name="send-e-mail-to-end-user"></a>E-mail küldése a végfelhasználónak

E-mail-sablon használatával is küldhet e-mailt a nem megfelelő eszközt használó felhasználónak. Az e-mail hozzájárulhat a megfelelőség kialakításához a szervezeten belül.

A művelet hozzáadása meg nem feleléshez:

1.  A **Meg nem felelési műveletek** panelen válassza a **Hozzáadás** lehetőséget.

2.  A **Művelet paraméterei panelen** a Műveletek legördülő listából válassza az **E-mail küldése a végfelhasználónak** elemet.

3.  Az **Üzenetsablon** elemre kattintva kiválaszthat egy korábban létrehozott üzenetsablont. Az üzenetsablon tartalmának ellenőrzése után válassza a **Kiválaszt** elemet.

    ![Üzenetsablon](../media/afnc-6.png)

> [!NOTE] 
> Az üzenetsablon megtekinthető, de nem szerkeszthető. Ha szerkeszteni szeretné az üzenetsablont, lépjen vissza az **Értesítések** panelre.

1.  Az **Ütemezés** területen írja be, hogy hány nap meg nem felelési időszak után küldjön a rendszer e-mailt a felhasználónak. Ha **0** értéket ad meg, akkor az e-mailt **azonnal** elküldi a rendszer.

2.  A **Műveletek** panelen válassza a **Hozzáadás**, majd az **OK** lehetőséget.

3.  Az **Eszközmegfelelőségi szabályzat tulajdonságai** panelen válassza a **Mentés** elemet.

