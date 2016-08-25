---
title: "Az eszköz titkosítása | Microsoft Intune"
description: "Egy Android-eszköz titkosítását ismerteti"
keywords: 
author: staciebarker
manager: angrobe
ms.date: 06/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6c6a6fed876e49888d8fda1fd93b39313387ba38
ms.openlocfilehash: 6cb6c0b8a8f4c1b88565ce4b7a5690406b4ddf40


---


# Az eszköz titkosítása

Ha a vállalata vagy szervezete megköveteli Android-eszközének titkosítását a vállalati fájlokhoz, levelekhez vagy adatokhoz való hozzáféréshez, az eszközt az alábbi lépésekkel titkosíthatja. Ha a rendszergazda ezt kéri, előfordulhat, hogy egy PIN-kódot vagy jelszót kell beállítania a titkosítás megkezdése előtt.

Ha megszünteti a telefonja regisztrációját, a titkosítás megmarad.

1.  Győződjön meg arról, hogy a képernyő-zárolási PIN-kód vagy jelszó be van állítva az eszközön.

2.  A **Beállítások** alatt kattintson a **Biztonság** &gt; **Telefon titkosítása** lehetőségre.
    (Egyes telefonokon a **Tárolás** &gt; **Tárolás titkosítása** vagy a **Tárolás** &gt; **Zárolási képernyő és biztonság** &gt; **További biztonsági beállítások** alatt található a „Titkosítás” opció).

3.  Kövesse a képernyőn megjelenő utasításokat. Előfordulhat, hogy a titkosítás során az eszköz többször újraindul.

### Mi a teendő ha problémába ütközik?
**Probléma:** Már titkosította az eszközt, és a következők egyikét látja:

- A titkosítási gomb le van tiltva.
- Egy üzenet azt jelzi, hogy titkosítania kell az eszközt.
- Hibaüzenet jelenik meg a Vállalati portál alkalmazás használatakor.

**Az alábbiakkal próbálkozhat:** 

1. Ellenőrizze, hogy az eszköz fel van-e töltve és csatlakoztatva van-e.

2. Ellenőrizze, hogy beállított-e PIN-kódot vagy jelszót az eszközön.

3. Ha már beállította a PIN-kódot vagy jelszót, próbálkozzon az alábbi lépésekkel, amelyeket a rendszergazda megkövetelhet az eszköz biztonságosabbá tételéhez. A lépésekben szereplő menünevek kissé eltérhetnek az eszközön láthatóktól, attól függően, hogy milyen Android-eszközt használ.

    a. Válassza a **Settings** (Beállítások) > **Security** (Biztonság) > **Screen lock** (Képernyőzár) lehetőséget. Erősítse meg jelenlegi PIN-kódját vagy jelszavát.

    b. A **Choose screen lock** (Képernyőzár kiválasztása) képernyőn válassza ki a használni kívánt képernyőzárat.

    c. A **Secure start-up** (Biztonságos indítás) képernyőn koppintson a **Require PIN to start device** (PIN-kód kérése az eszköz indításához), majd a **Continue** (Folytatás) elemre.

    d. Adjon meg egy PIN-kódot (a korábban megadott PIN-kódot is beírhatja), és koppintson a **Confirm your PIN** (PIN-kód megerősítése) elemre.

    e. Nyissa meg a Vállalati portál alkalmazást, jelölje ki az eszközét, és koppintson a **Megfelelőség ellenőrzése** elemre.

További segítségre van szüksége? Forduljon a rendszergazdához (a kapcsolattartási adatokat a [Vállalati portál webhelyén](http://portal.manage.microsoft.com) találja), vagy írjon a Microsoft Android-csapatának a wintunedroidfbk@microsoft.com címre.

### További információ
[Android-eszköz használata az Intune-nal](using-your-android-device-with-intune.md)



<!--HONumber=Aug16_HO2-->


