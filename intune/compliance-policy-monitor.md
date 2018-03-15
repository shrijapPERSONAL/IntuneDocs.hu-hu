---
title: "Intune-eszközmegfelelőségi szabályzatok figyelése"
titlesuffix: Azure portal
description: "Útmutató az eszközmegfelelőségi szabályzatok figyeléséhez"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 2/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f80d46e3e7c25c2b2e7a7c1af9604de1257a21e
ms.sourcegitcommit: a55c009a2ab223f79dc7439539937b284aee0626
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2018
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune-eszközmegfelelőségi szabályzatok figyelése

A megfelelőségi jelentésekkel a rendszergazdák elemezhetik a cég eszközeinek megfelelőségi állapotát, és így gyorsan elháríthatják a szervezet felhasználói által tapasztalt megfelelőségi problémákat. A jelentésekkel információ szerezhető egy eszköz általános megfelelőségi állapotáról, az egyes beállítások vagy egyes szabályzatok megfelelőségi állapotáról, és egy-egy eszköz részletesebben is megvizsgálható, és ellenőrizhető, hogy mely beállítások és szabályzatok vonatkoznak rá.

## <a name="before-you-begin"></a>Előkészületek

Az **Intune eszközmegfelelőségi irányítópultját** a következő lépéseket követve találhatja meg az Azure Portalon:

1.  Az [Azure Portalon](https://portal.azure.com) jelentkezzen be az Intune-os hitelesítő adataival.

2.  Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3.  Az **Eszközmegfelelőségi irányítópult** megnyitásához válassza az **Intune** &gt; **Eszközmegfelelőség** &gt; **Áttekintés** elemet.

> [!IMPORTANT] 
> Az eszközmegfelelőségi szabályzatok csak akkor alkalmazhatók az eszközökre, ha azok regisztrálva vannak az Intune-ban.

## <a name="device-compliance-dashboard"></a>Eszközmegfelelőségi irányítópult

Az **Eszközmegfelelőségi irányítópulton** ellenőrizheti az eszközmegfelelőségi szabályzatok állapotát. A különböző csempéken több jelentés érhető el, amelyek a szervezet eszközeinek megfelelőségi állapotáról adnak információt. A következő jelentések érhetőek el:

-   Általános összesített eszközmegfelelőség

-   Szabályzatok szerinti eszközmegfelelőség

-   Beállítások szerinti eszközmegfelelőség

![Eszközmegfelelőségi irányítópult](./media/idc-1.png)

Az egyes eszközökre vonatkozó megfelelőségi szabályzatokat és beállításokat ugyancsak megtekintheti, és ellenőrizheti az adott eszközre vonatkozó egyes beállítások összesített megfelelőségi állapotát is.

### <a name="overall-device-compliance-aggregate-report"></a>Általános összesített eszközmegfelelőségi jelentés

Az Intune-ban regisztrált összes eszköz összesített megfelelőségi állapota egy fánkdiagramon látható. Az eszközmegfelelőségi állapot adatait két külön adatbázis tárolja: az Intune és az Azure Active Directory. További információ az eszközmegfelelőségi szabályzatok állapotáról:

-   **Megfelelő**: az eszköz megfelel a rendszergazda által meghatározott egy vagy több eszközmegfelelőségi szabályzatnak.

-   **Nem megfelelő:** az eszköz nem felel meg a rendszergazda által meghatározott egy vagy több eszközmegfelelőségi szabályzatnak, vagy a felhasználó nem a rendszergazda által meghatározott szabályzatoknak megfelelően járt el.

-   **Türelmi időszak:** az eszközre a rendszergazda által létrehozott egy vagy több eszközmegfelelőségi szabályzat vonatkozik, de a felhasználó még nem alkalmazta a szabályzatokat, az eszköz tehát még nem megfelelő állapotú, de a rendszergazda által meghatározott türelmi időszak érvényes rá.

    -   További információ a nem megfelelő eszközökre alkalmazható műveletekről.

-   **Az eszköz nincs szinkronizálva:** az eszköz nem jelentette az eszközmegfelelőségi szabályzat állapotát a következő okok egyike miatt:

    -   **Ismeretlen**: az eszköz offline állapotban van, vagy valamilyen más okból nem sikerült kapcsolatba lépnie az Intune-nal vagy az Azure AD-vel.

    -   **Hiba**: az eszköznek nem sikerült kapcsolatba lépnie az Intune-nal vagy az Azure AD-vel, és üzenetben megkapta a hiba okát.

> [!IMPORTANT] 
> A jelentésben a **Megfelelő** gyűjtőben szerepelnek azok az eszközök, amelyek regisztrálva vannak az Intune-ban, de nem vonatkozik rájuk eszközmegfelelőségi szabályzat.

#### <a name="drill-down-option"></a>Részletes információ

Az **Eszközmegfelelőségi irányítópulton** az eszközmegfelelőségi csempére kattintva részletes információt kaphat a **megfelelőségi állapotról**, a **felhasználói e-mail-aliasokról**, az **eszköz modelljéről** és a **tartózkodási helyről** az eszközmegfelelőségi szabályzat által érintett egyes eszközök esetében.

![Eszközmegfelelőségi irányítópult – részletes információk](./media/idc-2.png)

Ha további információt szeretne az egyes felhasználókról, a felhasználó e-mail-aliasának beírásával szűrést végezhet az eszközmegfelelőségi jelentés diagramján.

![Eszközmegfelelőségi irányítópult – egyes felhasználók](./media/idc-3.png)

Az eszközmegfelelőségi diagram egyes megfelelőségi állapotaira kattintva további részleteket tekinthet meg a felhasználó eszközeinek megfelelőségi állapotáról.

![Eszközmegfelelőségi irányítópult – egyes állapotok](./media/idc-4.png)

#### <a name="filter"></a>Szűrő

Ha a **Szűrő** gombra kattint, egy beúszó lapka jelenik meg az alábbi lehetőségekkel:

-   Modell

    -   Szövegmező tetszőleges keresési szöveg beírásához
<br></br>
-   Platform

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   Állapot

    -   Compliant (Megfelelő)

    -   Nem megfelelő

    -   Türelmi időszakban

    -   Ismeretlen

    -   Hiba

Ha a **Frissítés gombra** kattint, a beúszó lapka bezárul, a megjelenített eredmények pedig a bejelölt szűrési feltételeknek megfelelően frissülnek.

##### <a name="device-details"></a>Eszközadatok

Az egyes eszközökre kattintással megnyitható a kiválasztott eszközhöz tartozó **Eszköz panel**. Itt további információt talál az adott eszközre alkalmazott eszközmegfelelőségi szabályzat beállításairól.

![Eszközmegfelelőségi irányítópult](./media/idc-6.png)

Ha az egyes eszközmegfelelőségi szabályzatbeállításokra kattint, megjelenik annak a rendszergazda által meghatározott eszközmegfelelőségi szabályzatnak a neve, amelyen ez a beállítás alapul.

![Eszközmegfelelőségi beállítás neve](./media/idc-7.png)

## <a name="policy-compliance-report"></a>Szabályzatoknak való megfelelőségi jelentés

Ez a jelentés megfelelőség szerinti bontásban tartalmaz információt a szabályzatokról és az egyes megfelelőségi állapotokhoz tartozó eszközök összesített számáról. A **Szabályzatmegfelelőség** csempe az **Eszközmegfelelőségi irányítópulton** érhető el, és megtekinthető rajta a rendszergazda által eddig létrehozott összes szabályzat, a szabályzat által megcélzott platformok, valamint a megfelelő és a nem megfelelő eszközök száma.

![Szabályzatok szerinti eszközmegfelelőségi jelentés](./media/idc-8.png)

A Szabályzatoknak való megfelelőség csempéjére, majd az egyes eszközmegfelelőségi szabályzatokra kattintva megtekinthető a **megfelelőségi állapot**, a **felhasználói e-mail-alias**, **az eszköz modellje** és a **tartózkodási hely** az eszközmegfelelőségi szabályzat által érintett egyes eszközök esetében.

![Szabályzatmegfelelőségi csempe](./media/idc-9.png)

## <a name="setting-compliance-report"></a>Beállításoknak való megfelelőségi jelentés

Ez a jelentés szabályzatbeállítások szerinti bontásban tartalmaz információt az egyes megfelelőségi állapotokhoz tartozó eszközök összesített számáról. A **Beállításmegfelelőségi** csempe az **Eszközmegfelelőségi irányítópulton** érhető el, és megtekinthető rajta a rendszergazda által létrehozott összes eszközmegfelelőségi szabályzat minden megfelelőségi szabályzatbeállítása, a szabályzatbeállítások által megcélzott platformok, valamint a nem megfelelő eszközök száma.

![Beállítások szerinti eszközmegfelelőségi jelentés](./media/idc-10.png)

A Beállításmegfelelőségi csempére, majd az egyes eszközmegfelelőségi szabályzatbeállításokra kattintva megtekinthető a **megfelelőségi állapot**, a **felhasználói e-mail-alias**, **az eszköz modellje** és a **tartózkodási hely** az adott eszközmegfelelőségi szabályzatbeállítás által érintett egyes eszközök esetében.

![Beállításmegfelelőségi csempe](./media/idc-11.png)

## <a name="threat-agent-status-report"></a>A fenyegetésfigyelő ügynök állapotjelentése

Ez a jelentés lehetővé teszi, hogy megtekintse a Windows Defender-ügynök állapotát. Ha az **Eszközmegfelelőséghez** egy összesített állapotjelentést használ, megtekintheti azokat az eszközöket, melyeken el kell végezni a következő műveletek egyikét:
- Aláírás frissítése
- Újraindítás
- Manuális beavatkozás
- Teljes vizsgálat
- Egyéb, beavatkozást igénylő ügynökállapotok

Az egyes állapotkategóriákhoz tartozó részletes jelentésekben megtalálhatók a figyelmet igénylő, illetve a **tisztaként** jelentő számítógépek.
