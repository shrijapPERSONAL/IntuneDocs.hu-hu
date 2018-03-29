---
title: Regisztrációs korlátozások beállítása a Microsoft Intune-ban
titlesuffix: ''
description: Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 99c69d08bb11ed097e2262938d254074169492c3
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="set-enrollment-restrictions"></a>Regisztrációs korlátozások beállítása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune-rendszergazdaként létrehozhat és felügyelhet olyan regisztrációs korlátozásokat, amelyek meghatározzák az Intune-ban regisztrálható eszközök számát és típusát. Több korlátozást is létrehozhat, melyeket alkalmazhat különféle felhasználói csoportokra. Az egyes korlátozásokhoz [prioritássorrendet](#change-enrollment-restriction-priority) állíthat be.

>[!NOTE]
>A regisztrációs korlátozások nem biztonsági funkciók. A feltört eszközök más tulajdonságokat állíthatnak magukról. Ezek a korlátozások a nem rosszindulatú felhasználók esetén jelentenek észszerű erőfeszítést igénylő akadályt.

>[!NOTE]
>A cikkben említett csoporthoz rendelhető regisztrációs korlátozás és a prioritási funkció jelenleg bevezetés alatt áll az Intune ügyfélbázisa számára. A bevezetés befejezéséig elképzelhető, hogy nem lehet hozzáférni a csoportra és a prioritásra vonatkozó funkciókhoz.

Többek között az alábbi regisztrációs korlátozásokat hozhatja létre:

- Regisztrált eszközök maximális száma.
- Regisztrációra alkalmas eszközplatformok:
  - Android.
  - Android for Work.
  - iOS.
  - macOS.
  - Windows.
- Platform operációsrendszer-verziók iOS, Android, Android for Work és Windows rendszerhez. (Csak a Windows 10-es verziók használhatók. Hagyja üresen, ha a Windows 8.1 engedélyezett.)
  - Minimális verzió.
  - Maximális verzió.
- Személyes tulajdonú eszközök korlátozása (csak iOS, Android, Android for Work vagy macOS esetén).

## <a name="default-restrictions"></a>Alapértelmezett korlátozások

A rendszer tartalmaz alapértelmezett korlátozásokat mind az eszköztípusra, mind az eszközszámra vonatkozóan. Módosíthatja az alapértelmezések beállításait. Az alapértelmezett korlátozások minden felhasználós és felhasználó nélküli regisztrációra vonatkoznak. Felülbírálhatja ezeket az alapértelmezéseket új, magasabb prioritású korlátozások létrehozásával.

## <a name="create-a-restriction"></a>Korlátozás létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Válassza a **Korlátozás létrehozása** lehetőséget.
5. Adjon meg nevet és leírást a korlátozás számára.
6. Adja meg a **Korlátozás típusa** beállítás értékét, és válassza a **Létrehozás** lehetőséget.
7. Eszközszámkorlát esetén válassza az **Eszközszámkorlát** lehetőséget a felhasználó által regisztrálható eszközök maximális számának beállításához.
8. Eszköztípuskorlát esetén kattintson a **Platformok** és a **Platformkonfigurációk** lehetőségre a különféle platformok és verziók engedélyezéséhez vagy blokkolásához.
9. Válassza a **Hozzárendelések** > **+ Csoportok kiválasztása** lehetőséget.
10. A **Csoportok kiválasztása** területen válasszon egy vagy több csoportot, és válassza a **Kiválasztás** lehetőséget. A korlátozás csak azokra a csoportokra lesz érvényes, amelyekhez hozzárendelte azt. Ha egy korlátozást egyetlen csoporthoz sem rendel hozzá, akkor az adott korlátozásnak semmilyen hatása nem lesz.
11. Válassza a **Mentés** lehetőséget.
12. Az új korlátozások az alapértelmezett korlátozásnál eggyel magasabb prioritással jönnek létre. Igény esetén [módosíthatja a prioritást](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Típus szerinti korlátozás beállítása

Az eszköztípuskorlátok beállításait az alábbi lépésekkel módosíthatja:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Az **Eszköztípus-korlátozások** területen válassza ki a beállítani kívánt korlátot.
5. A korlát neve alatt (mely az alapértelmezett korlát esetében **Minden felhasználó**) válassza a **Platformok** lehetőséget. Adja meg az **Engedélyezés** vagy a **Blokkolás** beállítást az összes felsorolt platformhoz.
6. Válassza a **Mentés** lehetőséget.
7. A korlát neve alatt (mely az alapértelmezett korlát esetében **Minden felhasználó**) válassza a **Platformkonfigurációk** lehetőséget. Ezután válassza ki a felsorolt platformokhoz a minimális és maximális **Verziók** értékét. Példa a támogatott verziókra:
    - Az Android és az Android for Work a főverzió.alverzió.változat.build formátumot támogatja.
    - Az iOS a főverzió.alverzió.változat formátumot támogatja.
    - A Windows a főverzió.alverzió.változat.build formátumot támogatja, csak Windows 10 esetén.
  Az operációs rendszer verziójának korlátozásai nem vonatkoznak a Készülékregisztrációs programban, az Apple School Manager programban vagy az Apple Configurator alkalmazással regisztrált Apple-eszközökre.
8. Válassza a **személyes tulajdonú** eszközök **Engedélyezés** vagy **Blokkolás** lehetőségét az összes felsorolt platform esetében.
    ![Eszközkorlátozási munkaterület az alapértelmezett eszközplatform-konfigurációkkal, ahol a személyes tulajdonú eszközök beállításai meg vannak adva](media/device-restrictions-platform-configurations.png)
9. Válassza a **Mentés** lehetőséget.


>[!NOTE]
>- Ha letiltja a személyes tulajdonú Android-eszközök regisztrációját, a személyes tulajdonú Android for Work-eszközök továbbra is regisztrálhatók.
>- Alapértelmezés szerint az Android for Work-eszközök beállításai ugyanazok, mint az Android-eszközöké. Az Android for Work-beállítások módosítása után ez már nem lesz így.
>- Ha letiltja a személyes Android for Work-regisztrációt, csak a vállalati Android-eszközök regisztrálhatók Android for Work-eszközként.

## <a name="set-device-limit-restrictions"></a>Regisztrált eszközök maximális számának beállítása

Az eszközszámkorlátok beállításait az alábbi lépésekkel módosíthatja:

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Az **Eszközszámkorlátok** területen válassza ki a beállítani kívánt korlátot.
5. Válassza az **Eszközszámkorlát** lehetőséget, majd a legördülő listában válassza ki a felhasználó által regisztrálható eszközök maximális számát.
    ![Az Eszközszámkorlátok panel az eszközszámkorlátokkal](./media/device-restrictions-limit.png)
6. Válassza a **Mentés** lehetőséget.


A felhasználók üzenetet kapnak majd, ha elérték a regisztrálható eszközök maximális számát. iOS rendszer esetében ez az alábbi módon jelenik meg:

![Az iOS-eszközön megjelenő limitértesítés](./media/enrollment-restrictions-ios-set-limit-notification.png)

## <a name="change-enrollment-restriction-priority"></a>A regisztrációs korlátozások prioritásának módosítása

A prioritást akkor használja a rendszer, ha egy felhasználó több olyan csoportnak is a tagja, amelyhez korlátozások vannak hozzárendelve. A felhasználókra a rendszer egyedül a vonatkozó csoportok legmagasabb prioritású korlátozását alkalmazza. Tegyük fel például, hogy Attila tagja az A csoportnak, melyhez egy 5-ös prioritású korlátozás van hozzárendelve, illetve tagja a B csoportnak is, melyhez egy 2-es prioritású korlátozás van hozzárendelve. Ez esetben Attilára csak a 2-es prioritású korlátozást alkalmazza a rendszer.

Az Ön által létrehozott korlátozások az alapértelmezettnél eggyel magasabb prioritást kapnak.

Az eszközregisztráció tartalmaz alapértelmezett korlátozásokat mind az eszköztípusra, mind az eszközszámra vonatkozóan. Ez a két korlátozás az összes felhasználóra érvényes, hacsak felül nem bírálják őket magasabb prioritású korlátozások.

Az összes egyéni korlátozás prioritását módosíthatja.

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Vigye az egérmutatót a korlátozás fölé a prioritáslistában.
5. A három függőleges pontot alkotó ikon használatával húzza a prioritást a lista megfelelő helyére.
