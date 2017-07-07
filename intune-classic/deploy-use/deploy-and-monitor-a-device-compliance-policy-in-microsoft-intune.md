---
title: "Megfelelőségi házirend üzembe helyezése és figyelése"
description: "Használja az ebben a témakörben található részletes útmutatót az eszközmegfelelőségi szabályzat üzembe helyezéséhez és figyeléséhez."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d0d48724a8c09a5dac0bfa2987a1eee05f218950
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a>Eszközmegfelelőségi szabályzat üzembe helyezése és figyelése a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a>Megfelelőségi házirend telepítése
Léptesse életbe a [létrehozott](create-a-device-compliance-policy-in-microsoft-intune.md) megfelelőségi szabályzatot szervezete egy vagy több felhasználócsoportjára vonatkozóan. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer a felhasználói eszközök megfelelőségét ellenőrzi.

1.  A **Házirend** munkaterületen válassza ki a telepíteni kívánt házirendet, majd kattintson a **Központi telepítés kezelése** elemre.
![A megfelelőségi szabályzat lapjának felső részén található Központi telepítés kezelése menüt megjelenítő képernyőkép](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  A **Központi telepítés kezelése** párbeszédpanelen válasszon ki egy vagy több olyan csoportot, amelyre a szabályzatot érvényesíteni szeretné, majd válassza a **Hozzáadás** > **OK** elemet.
![A Központi telepítés kezelése párbeszédpanel képernyőképe](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Használja a már létrehozott és az Intune-nal szinkronizált Active Directory-csoportokat, vagy hozza létre ezeket a csoportokat manuálisan az Intune-konzolon. A szabályzatok beállításával kapcsolatos további tudnivalókért lásd a [konfigurációs szabályzat beállításáról](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) szóló részt.

A **Házirend** munkaterület **Áttekintés** lapján található állapotösszegzés és riasztások használatával azonosíthatók a szabályzattal kapcsolatos, figyelmet igénylő problémák. Ezen felül egy állapotösszegzés megjelenik az **Irányítópult** munkaterületen is.

> [!IMPORTANT]
> Ha nem telepített megfelelőségi szabályzatot, és engedélyez egy Exchange feltételes hozzáférési szabályzatot, az összes megcélzott eszköz számára engedélyezve lesz a hozzáférés.

## <a name="monitor-the-compliance-policy"></a>A megfelelőségi házirend megfigyelése

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a>Megfelelőségi házirendet be nem tartó eszközök megtekintése

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) válassza a **Csoportok** > **Minden eszköz** elemet.

2.  Kattintson duplán az eszköz nevére az eszközök listájában.

3.  Válassza a **Házirend** fület az eszköz házirendjei listájának megtekintéséhez.

4.  A **Szűrők** legördülő listából válassza a **Nem felel meg a megfelelőségi szabályzatnak** elemet.
![A szűrők listában szereplő beállítási lehetőségek képernyőképe](./media/intune-sa-3e-view-device-noncompliance.png)

#### <a name="to-view-the-health-attestation-reports"></a>Az állapotigazolási jelentések megtekintése

1.  A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza a **Jelentések** elemet.

2.  Az **Állapotigazolási jelentés – Új jelentés létrehozása** lapon megtekintheti az Intune által gyűjtött összes Windows 10-állapotigazolási adatot. Szűrők segítségével az adatok egy részét tartalmazó jelentést is létrehozhat. A szűrők az eszköz típusán, az operációs rendszeren vagy az adatpontok egy részén alapulhatnak.

## <a name="how-intune-resolves-policy-conflicts"></a>Hogyan oldja fel az Intune az szabályzatütközéseket?
Szabályzatütközésről akkor beszélünk, hogy egy eszközre több Intune-szabályzat vonatkozik. Ha a szabályzatbeállítások közt átfedés van, az Intune a következő szabályok alkalmazásával oldja fel az ütközéseket:

-   Ha az ütköző beállítások egy Intune konfigurációs szabályzatból és egy megfelelőségi szabályzatból kerülnek ki, akkor a megfelelőségi szabályzat beállításai érvényesülnek a konfigurációs szabályzatéival szemben. Ez még akkor is így van, ha a konfigurációs szabályzat beállításai biztonságosabbak.

-   Ha több megfelelőségi szabályzatot telepített, akkor az Intune a legbiztonságosabbat alkalmazza a szabályzatok közül.

## <a name="next-steps"></a>További lépések
Arról, hogy miképpen korlátozhatja a szervezet szolgáltatásaihoz való hozzáférést a megfelelőségi szabályzat feltételes hozzáférési szabályzattal együttes használatával, [Az e-mailek és az O365-szolgáltatások elérésének korlátozása](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) című cikk nyújt tájékoztatást.


### <a name="see-also"></a>További információ
[Az Intune eszközmegfelelőségi szabályzatainak bemutatása](introduction-to-device-compliance-policies-in-microsoft-intune.md)
