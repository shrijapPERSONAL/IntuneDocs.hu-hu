---
title: "Az eszköz titkosítása | Microsoft Intune"
description: "Egy Android-eszköz titkosítását ismerteti"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 81c0c29e1b874a7f5c7faa1c1216dbaa99ec4543
ms.openlocfilehash: b8214506ae4609cb5316c66b854fbd572fbac94f


---


# <a name="encrypt-your-device"></a>Az eszköz titkosítása

Ha a vállalata vagy szervezete előírja Android-eszközének titkosítását a vállalati fájlokhoz, levelekhez vagy adatokhoz való hozzáféréshez, az eszközt az alábbi lépésekkel titkosíthatja. Ha a rendszergazda ezt kéri, előfordulhat, hogy egy PIN-kódot vagy jelszót kell beállítania a titkosítás megkezdése előtt.

Ha megszünteti a telefonja regisztrációját, a titkosítás megmarad.

1.  Győződjön meg arról, hogy a képernyő-zárolási PIN-kód vagy jelszó be van állítva az eszközön.

2.  A **Beállítások** menüben válassza ki a **Biztonság** &gt; **Telefon titkosítása** lehetőséget.
    (Egyes telefonokon a **Tárolás** &gt; **Tárolás titkosítása** vagy a **Tárolás** &gt; **Zárolási képernyő és biztonság** &gt; **További biztonsági beállítások** menüben található a „Titkosítás” opció).

3.  Kövesse a képernyőn megjelenő utasításokat. Előfordulhat, hogy a titkosítás során az eszköz többször újraindul.

### <a name="what-to-do-if-you-have-issues"></a>Mi a teendő ha problémába ütközik?
**Probléma:** Már titkosította az eszközt, és a következők egyikét látja:

- A titkosítási gomb le van tiltva.
- Egy üzenet azt jelzi, hogy titkosítania kell az eszközt.
- Hibaüzenet jelenik meg a Vállalati portál alkalmazás használatakor.

**Az alábbiakkal próbálkozhat**

- Ellenőrizze, hogy az eszköz fel van-e töltve és csatlakoztatva van-e.
- Ellenőrizze, hogy beállított-e PIN-kódot vagy jelszót az eszközön.
- Ha már beállította a PIN-kódot vagy jelszót, próbálkozzon az alábbi lépésekkel, amelyeket a rendszergazda megkövetelhet az eszköz biztonságosabbá tételéhez. A lépésekben szereplő menünevek kissé eltérhetnek az eszközön láthatóaktól, attól függően, hogy milyen Android-eszközt használ.

    1. Válassza a **Settings** (Beállítások) > **Security** (Biztonság) > **Screen lock** (Képernyőzár) lehetőséget. Erősítse meg jelenlegi PIN-kódját vagy jelszavát.

    2. A **Choose screen lock** (Képernyőzár kiválasztása) képernyőn válassza ki a használni kívánt képernyőzárat.

    3. A **Secure start-up** (Biztonságos indítás) képernyőn koppintson a **Require PIN to start device** (PIN-kód kérése az eszköz indításához), majd a **Continue** (Folytatás) elemre.

    4. Adjon meg egy PIN-kódot (a korábban megadott PIN-kódot is beírhatja), és koppintson a **Confirm your PIN** (PIN-kód megerősítése) elemre.

    5. Nyissa meg a Vállalati portál alkalmazást, jelölje ki az eszközét, és koppintson a **Megfelelőség ellenőrzése** elemre.

További segítségre van szüksége? Forduljon a rendszergazdához (a kapcsolattartási adatokat a [Munkahelyi portál webhelyén](http://portal.manage.microsoft.com) találja), vagy írjon a [Microsoft Android-csapatának](mailto:wintunedroidfbk@microsoft.com).



<!--HONumber=Nov16_HO2-->


