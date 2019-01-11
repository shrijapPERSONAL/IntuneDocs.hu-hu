---
title: Az iOS-beli Microsoft Intune - eszközök zárolási képernyő testreszabása |} A Microsoft Docs
titlesuffix: ''
description: A használatával a megosztott eszköz konfigurációs beállításai iOS-hez készült iOS-eszköz zárolási képernyőjén információ megjelenítéséhez használható Microsoft Intune azon beállításainak ismertetése.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9f4d75d795421c761398f349c324b498fd21ca01
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203076"
---
# <a name="add-custom-messages-to-lock-screen-and-login-window-on-ios-devices-using-microsoft-intune"></a>Adja hozzá az egyéni üzenet a zárolási képernyő és a bejelentkezési ablakban az iOS-eszközökön a Microsoft Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk bemutatja a Microsoft Intune-beállítások segítségével adatainak megjelenítése az IOS-es eszköz zárolási képernyő és a bejelentkezési ablakban. 

Ezek a beállítások használatával egy egyéni üzenetet vagy szöveg megjelenítése a bejelentkezési ablakban és a zárolási képernyőn. Például megadhat egy "Ha megtalálja, térjen vissza..." üzenetet és eszközcímkeadatokat.

Ezek a beállítások az iOS 9.3-at vagy újabb verziót futtató felügyelt eszközökön vannak támogatva.

## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure Portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adjon meg egy **nevet** és egy **leírást** a profil számára.
4. A **Platform**válassza **iOS**. A **profiltípus**válassza **eszközfunkciók**.
5. A **beállítások**válassza **(csak felügyelt) üzenet a zárolási képernyőn**. Adja meg a következő beállításokat:

    - **Eszközcímke-információ**: Adja meg az eszköz az eszközcímke adatait. Például írja be a következőt: `123xyz`.

        A beírt szöveg jelenik meg a bejelentkezési ablakban és a zárolási képernyőn az eszközön.

    - **Lábjegyzet a zárolási képernyőn**: Ha az eszköz elveszett vagy ellopták, adjon meg egy, melyek segíthetnek az eszközt. Megadhatja, hogy a mező kívánt szöveget. Például: `If found, call Contoso at ...`.

    Eszközök tokenjeit is használható eszközre vonatkozó információk hozzáadása a mezőkhöz. Írja be például a sorozatszám megjeleníthető `Serial Number: {{serialnumber}}`. A zárolási képernyőn a szöveg látható hasonló `Serial Number 123456789ABC`. Változók megadásakor ügyeljen arra, hogy kapcsos zárójeleket `{{ }}`. [Alkalmazás-konfigurációs jogkivonatokról](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) használható változók listáját tartalmazza. Is `deviceName` vagy bármely más eszközspecifikus érték.

6. Amikor végzett, válassza ki a **OK** > **OK** > **létrehozás**. A profil látható a listában.

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).
