---
title: Rövid útmutató – Jelszó-megfelelőségi szabályzat létrehozása Android rendszerű eszközökhöz
titlesuffix: Microsoft Intune
description: Ebben a rövid útmutatóban a Microsoft Intune-t fogja használni az Android-eszközöknél megkövetelt jelszóhosszúság beállításához.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cccb79ae7337c3b037141cbb7759a856d651f83f
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851015"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Gyors útmutató: Az Android-eszközök jelszó megfelelőségi szabályzat létrehozása

Ebben a rövid útmutatóban a Microsoft Intune-t használjuk annak beállítására, hogy a rendszer az Android-eszközöket használó munkatársaktól adott hosszúságú jelszót kérjen el, mielőtt engedélyezné az eszközökön található információkhoz való hozzáférést. 

Az Intune-eszközmegfelelőségi szabályzatokkal megszabhatja az eszközök megfelelőségéhez kötelezően szükséges szabályokat és beállításokat. Ezeket a megfelelőségi szabályzatokat feltételes hozzáféréssel használva megakadályozható vagy engedélyezhető a vállalati erőforrásokhoz való hozzáférés. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén.

> [!IMPORTANT]
> Az alkalmazottak tartalmainak védelme érdekében a jelszóbeállítások mellett egyéb rendszerbiztonsági beállításokat használatát is érdemes fontolóra venni. További információkért tekintse meg a [rendszerbiztonsági beállításokat](compliance-policy-create-android-for-work.md#system-security-settings) ismertető cikket.

Ha nem rendelkezik Intune-előfizetéssel, [regisztráljon egy ingyenes próbafiókkal](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Bejelentkezés az Intune-ba

Jelentkezzen be az [Intune-ba](https://aka.ms/intuneportal) globális rendszergazdaként vagy Intune-szolgáltatásadminisztrátorként. 

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása

Ebben a rövid útmutatóban a Intune-t használja majd annak beállítására, hogy a rendszer az Android-eszközöket használó munkatársaktól adott hosszúságú jelszót kérjen el, mielőtt engedélyezné az eszközökön található információkhoz való hozzáférést.

1. Az Intune-ban válassza az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** lehetőséget.
2. A **Név** mezőben adja meg az **Android compliance** (Android-megfelelőség) nevet. Egy **leírást** is adjon meg.
3. A **Platform** beállításban válassza az **Android** lehetőséget. 
4. Kattintson a **Beállítások** > **Rendszerbiztonság** elemre az Android **Rendszerbiztonság** paneljének megjelenítéséhez.
5. Kattintson a **Kötelező** elemre a **Jelszó szükséges a mobileszközök feloldásához** mellett.
6. Adja meg a **6** értéket a **Jelszó minimális hossza** mellett. 

    ![Képernyőkép egy csoport létrehozásáról a Microsoft Intune-ban](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. Ha elkészült, a szabályzat létrehozásához kattintson az **OK** > **OK** > **Létrehozás** gombra.

Ha sikeresen létrehozta a szabályzatot, az megjelenik az eszközmegfelelőségi szabályzatok listájában. 

## <a name="clean-up-resources"></a>Az erőforrások eltávolítása

Ha többé nincs szükség a szabályzatra, törölje. Ehhez jelölje ki a megfelelőségi szabályzatot, és kattintson a **Törlés** gombra.

## <a name="next-steps"></a>További lépések

Ebben a rövid útmutatóban az Intune használatával létrehozott egy megfelelőségi szabályzatot az alkalmazottak Android-eszközeihez, hogy legalább hat karakter hosszúságú jelszót kelljen hozzájuk megadni. További információk a megfelelőségi szabályzatok létrehozásáról: [Az Intune eszközmegfelelőségi szabályzatai – első lépések](device-compliance-get-started.md).

Kövesse az Intune rövid útmutatóinak sorozatát a következő rövid útmutatóval.

> [!div class="nextstepaction"]
> [Gyors útmutató: Értesítések küldése nem megfelelő eszközök](quickstart-send-notification.md)
