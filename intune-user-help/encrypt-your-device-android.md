---
title: Androidos eszközök védelme titkosítással | Microsoft Docs
description: Androidos eszköz védelme
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: cea43f2bf3b13bf0463e1dedd6c20a1587336d5b
ms.sourcegitcommit: 7f46e9990797bdfa669ccba2077721f1bc70c07e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/04/2018
ms.locfileid: "30754994"
---
# <a name="how-to-protect-your-android-device-using-encryption"></a>Androidos eszközök védelme titkosítással

Egy eszköz titkosításakor a rajta lévő információt egy védelmi kódréteg veszi körül, amely megakadályozza, hogy illetéktelenek férjenek hozzá. Az információbiztonság érdekében a munkahelye az androidos eszközök titkosítását követeli meg Öntől, mielőtt hozzáférhetne a vállalati fájlokhoz, e-mailekhez és adatokhoz.

> [!Note]
> Bizonyos androidos eszközöket, mint a Vivo és az OPPO gyártású, valamint egyes Huawei gyártású eszközök, nem lehet titkosítani. További információért [kattintson ide](your-device-appears-encrypted-but-cp-says-otherwise-android.md).

Ha megszünteti a telefonja regisztrációját, a titkosítás megmarad.

1.  Győződjön meg arról, hogy a képernyő-zárolási PIN-kód vagy jelszó be van állítva az eszközön.

2.  A **Settings** (Beállítások) menüben válassza a **Security** (Biztonság)  >  **Encrypt Device** (Eszköz titkosítása) lehetőséget.
    (Egyes telefonokon a **Storage** (Tárhely)  >  **Storage encryption** (Tárhely titkosítása) vagy a **Storage** (Tárhely)  >  **Lock screen and security**  >  (Zárolási képernyő és biztonság) **Other security settings** (További biztonsági beállítások) menüben található az Encrypt (Titkosítás) beállítás).

3.  Kövesse a képernyőn megjelenő utasításokat. Előfordulhat, hogy a titkosítás során az eszköz többször újraindul.

### <a name="what-to-do-if-you-have-issues"></a>Mi a teendő ha problémába ütközik?
**Probléma:** Már titkosította az eszközt, és a következők egyikét látja:

- A titkosítási gomb le van tiltva.
- Egy üzenet azt jelzi, hogy titkosítania kell az eszközt.
- Hibaüzenet jelenik meg a Vállalati portál alkalmazás használatakor.

**Az alábbiakkal próbálkozhat**

- Ellenőrizze, hogy az eszköz fel van-e töltve és csatlakoztatva van-e.
- Ellenőrizze, hogy beállított-e PIN-kódot vagy jelszót az eszközön.
- Ha már beállította a PIN-kódot vagy jelszót, próbálkozzon az alábbi lépésekkel, amelyeket a cég informatikai támogatási szolgálata megkövetelhet az eszköz biztonságosabbá tételéhez. A lépésekben szereplő menünevek kissé eltérhetnek az eszközön láthatóaktól, attól függően, hogy milyen Android-eszközt használ.

    1. Nyissa meg a **Settings** (Beállítások) > **Lock Screen and Security** (Zárolási képernyő és biztonság) > **Screen lock** (Képernyőzárolás) lapot. Erősítse meg jelenlegi PIN-kódját vagy jelszavát.

    2. A **Choose screen lock** (Képernyőzár kiválasztása) képernyőn válassza ki a használni kívánt képernyőzárat. 

    3. Miután kiválasztotta a képernyőzárat, lépjen vissza a **Lock Screen and Security** (Zárolási képernyő és biztonság) képernyőre, és válassza a **Secure Startup** (Biztonságos indítás) lehetőséget. 
    
    4. A **Secure startup** (Biztonságos indítás) képernyőn koppintson a **Require PIN to start device** (PIN-kód kérése az eszköz indításához), majd a **Continue** (Folytatás) elemre.

    5. Adjon meg egy PIN-kódot (a korábban megadott PIN-kódot is beírhatja), és koppintson a **Confirm your PIN** (PIN-kód megerősítése) elemre.

    6. Nyissa meg a Vállalati portál alkalmazást, jelölje ki az eszközét, és koppintson a **Megfelelőség ellenőrzése** elemre.

További segítségre van szüksége? Forduljon a cég informatikai támogatási szolgálatához (a kapcsolattartási adatokat a [céges portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.
