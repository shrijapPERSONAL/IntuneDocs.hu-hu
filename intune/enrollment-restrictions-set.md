---
title: Regisztrációs korlátozások beállítása a Microsoft Intune-ban
titleSuffix: ''
description: Regisztráció korlátozása platform alapján és eszközregisztrálási korlát beállítása az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ed2a16e4cc34d68342f8cd5b21daeec46c22ff9d
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799553"
---
# <a name="set-enrollment-restrictions"></a>Regisztrációs korlátozások beállítása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune-rendszergazdaként létrehozhat és felügyelhet olyan regisztrációs korlátozásokat, amelyek meghatározzák az Intune-ban regisztrálható eszközök számát és típusát. Több korlátozást is létrehozhat, melyeket alkalmazhat különféle felhasználói csoportokra. Az egyes korlátozásokhoz [prioritássorrendet](#change-enrollment-restriction-priority) állíthat be.

>[!NOTE]
>A regisztrációs korlátozások nem biztonsági funkciók. A feltört eszközök más tulajdonságokat állíthatnak magukról. Ezek a korlátozások a nem rosszindulatú felhasználók esetén jelentenek észszerű erőfeszítést igénylő akadályt.

Többek között az alábbi regisztrációs korlátozásokat hozhatja létre:

- Regisztrált eszközök maximális száma.
- Regisztrációra alkalmas eszközplatformok:
  - Android
  - Androidos munkahelyi profil
  - iOS
  - macOS
  - Windows
- Platform operációsrendszer-verziók iOS, Android, androidos munkahelyi profilos és Windows rendszerű eszközökhöz. (Csak a Windows 10-es verziók használhatók. Hagyja üresen, ha a Windows 8.1 engedélyezett.)
  - Minimális verzió.
  - Maximális verzió.
- Személyes tulajdonú eszközök korlátozása (csak iOS, Android, androidos munkahelyi profil, macOS vagy Windows esetén).

## <a name="default-restrictions"></a>Alapértelmezett korlátozások

A rendszer tartalmaz alapértelmezett korlátozásokat mind az eszköztípusra, mind az eszközszámra vonatkozóan. Módosíthatja az alapértelmezések beállításait. Az alapértelmezett korlátozások minden felhasználós és felhasználó nélküli regisztrációra vonatkoznak. Felülbírálhatja ezeket az alapértelmezéseket új, magasabb prioritású korlátozások létrehozásával.

## <a name="create-a-restriction"></a>Korlátozás létrehozása

1. Jelentkezzen be az Azure portálra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Válassza a **Korlátozás létrehozása** lehetőséget.
5. Adjon meg nevet és leírást a korlátozás számára.
6. Adja meg a **Korlátozás típusa** beállítás értékét, és válassza a **Létrehozás** lehetőséget.
7. Eszközszámkorlát esetén válassza az **Eszközszámkorlát** lehetőséget a felhasználó által regisztrálható eszközök maximális számának beállításához.
8. Eszköztípuskorlát esetén kattintson a **Platformok** és a **Platformkonfigurációk** lehetőségre a különféle platformok és verziók engedélyezéséhez vagy blokkolásához.
9. Válassza a **Hozzárendelések** > **+ Csoportok kiválasztása** lehetőséget.
10. A **Csoportok kiválasztása** területen válasszon egy vagy több csoportot, és válassza a **Kiválasztás** lehetőséget. A korlátozás csak azokra a csoportokra lesz érvényes, amelyekhez hozzárendelte azt. Ha egy korlátozást egyetlen csoporthoz sem rendel hozzá, akkor az adott korlátozásnak semmilyen hatása nem lesz.
11. Kattintson a **Mentés** gombra.
12. Az új korlátozások az alapértelmezett korlátozásnál eggyel magasabb prioritással jönnek létre. Igény esetén [módosíthatja a prioritást](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Típus szerinti korlátozás beállítása

Az eszköztípuskorlátok beállításait az alábbi lépésekkel módosíthatja. Ezek a korlátozások a már regisztrált eszközöket nem érintik. Ez a funkció nem alkalmas az [Intune PC-ügynök](manage-windows-pcs-with-microsoft-intune.md) használatával regisztrált eszközök letiltásához.

1. Jelentkezzen be az Azure portálra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Az **Eszköztípus-korlátozások** területen válassza ki a beállítani kívánt korlátot, majd válassza a **Tulajdonságok** > **Platformok kijelölése** lehetőséget. Adja meg az **Engedélyezés** vagy a **Blokkolás** beállítást az összes felsorolt platformhoz.
    ![Képernyőkép platform tiltásához vagy blokkolásához](media/enrollment-restrictions-set/platform-allow-block.png)
5. Válassza az **OK** gombot.
6. Válassza a **Platformok konfigurálása** lehetőséget.
    ![Képernyőkép platformok konfigurálásához](media/enrollment-restrictions-set/configure-platforms.png)
7. Válassza ki a felsorolt platformokhoz a minimális és maximális **Verziók** értékét. Támogatott verzióformátumok többek között az alábbiak:
    - Az androidos munkahelyi profil támogatja a főverzió.alverzió.változat.build formátumot.
    - Az iOS a főverzió.alverzió.változat formátumot támogatja. Az operációs rendszer verziójának korlátozásai nem vonatkoznak a Készülékregisztrációs programban, az Apple School Manager programban vagy az Apple Configurator alkalmazással regisztrált Apple-eszközökre.
    - A Windows a főverzió.alverzió.változat.build formátumot támogatja, csak Windows 10 esetén.
> [!Note]
> Windows 10-es nem biztosít a buildszám-regisztráció során, ha megadta a 10.0.17134.100 és az eszköz van 10.0.17134.174 példány le lesz tiltva regisztráció során.
8. Válassza a **személyes tulajdonú** eszközök **Engedélyezés** vagy **Tiltás** lehetőségét az összes felsorolt platform esetében.
9. Válassza az **OK** gombot.

### <a name="blocking-personal-android-devices"></a>Személyes Android-eszközök letiltása
- Ha letiltja a személyes tulajdonú Android-eszközök regisztrációját, a személyes tulajdonú androidos munkahelyi profilos eszközök továbbra is regisztrálhatók.
- Alapértelmezés szerint az androidos munkahelyi profilos eszközök beállításai ugyanazok, mint az Android-eszközöké. Az androidos munkahelyi profil beállításainak módosítása után ez már nem lesz így.
- Ha letiltja a személyes androidos munkahelyi profilos regisztrációt, csak a vállalati Android-eszközök regisztrálhatók androidos munkahelyi profilos eszközként.

### <a name="blocking-personal-windows-devices"></a>Személyes Windows-eszközök letiltása
Ha letiltja a személyes tulajdonban lévő windowsos eszközök regisztrációját, az Intune ellenőrzi, hogy minden új Windows-regisztrációs kérelem vállalati regisztrációként lett-e engedélyezve. A jogosulatlan regisztrációk le lesznek tiltva.

Windows vállalati regisztrációnak minősülnek az alábbi módszerek:
 - A felhasználó [készülékregisztráció-kezelői fiókot]( device-enrollment-manager-enroll.md) használ a regisztráláshoz.
- Az eszközregisztráció a [Windows AutoPilot](enrollment-autopilot.md) használatával történik.
- Az eszköz a Windows Autopilottal van regisztrálva, de az nem egy csak MDM-regisztrációs lehetőség a Windows-beállításokban.
- Az eszköz IMEI-száma szerepel az **Eszközregisztráció** > **[Vállalati eszközazonosítók](corporate-identifiers-add.md)** listán. (Windows Phone 8.1-hez nem támogatott)
- Az eszközregisztráció [tömeges kiépítési csomagban](windows-bulk-enroll.md) történik.
- Regisztrálja az eszközt a csoportházirend-objektum, keresztül vagy [megosztott kezelésre az SCCM-ből az automatikus regisztráció](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management.md).
 
Az alábbi regisztrációkat cégesként jelzi az Intune, de le lesznek tiltva, mert nem kínálják fel az Intune-rendszergazdának az eszközönkénti szabályozást:
 - [Automatikus MDM-regisztráció](windows-enroll.md#enable-windows-10-automatic-enrollment) és [Azure Active Directory-csatlakozás a Windows beállítása során](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Automatikus MDM-regisztráció](windows-enroll.md#enable-windows-10-automatic-enrollment) és [Azure Active Directory-csatlakozás a Windows beállításaiból](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)*.
 
Az alábbi személyes regisztrációs módszerek is le lesznek tiltva:
- [Automatikus MDM-regisztráció](windows-enroll.md#enable-windows-10-automatic-enrollment) és [munkahelyi fiók hozzáadása a Windows-beállításokból](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- [Csak MDM-regisztráció]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) lehetősége a Windows-beállításokból.

\* Ha az AutoPilottal regisztrált, ezek nincsenek letiltva.

## <a name="set-device-limit-restrictions"></a>Regisztrált eszközök maximális számának beállítása

Az eszközszámkorlátok beállításait az alábbi lépésekkel módosíthatja:

1. Jelentkezzen be az Azure portálra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Az **Eszközszámkorlátok** területen válassza ki a beállítani kívánt korlátot.
5. Válassza az **Eszközszámkorlát** lehetőséget, majd a legördülő listában válassza ki a felhasználó által regisztrálható eszközök maximális számát.
    ![Az Eszközszámkorlátok panel az eszközszámkorlátokkal](./media/device-restrictions-limit.png)
6. Kattintson a **Mentés** gombra.


BYOD regisztrációk során a felhasználóknak megjelenik egy értesítés, értesíti, ha a regisztrált eszközök maximális számát. iOS rendszer esetében ez az alábbi módon jelenik meg:

![Az iOS-eszközön megjelenő limitértesítés](./media/enrollment-restrictions-ios-set-limit-notification.png)

> [!IMPORTANT]
> Eszközszámkorlát nem vonatkozik a következő Windows-regisztráció típusok:
> - Közösen kezelt regisztrációk
> - Csoportházirend-objektum regisztrációk
> - Az Azure Active Directoryhoz csatlakoztatott regisztrációk
> - Tömeges Azure Active Directoryhoz csatlakoztatott regisztrációk
> - Az autopilot-regisztrációk
>
> Eszközszámkorlát nincs érvényes ezen regisztrációs típusok esetén, mert megosztott eszközzel kapcsolatos helyzetek minősülnek.
> Ezen regisztrációs típusok esetén beállíthatja a szigorú korlátok [az Azure Active Directoryban](https://docs.microsoft.com/en-us/azure/active-directory/devices/device-management-azure-portal#configure-device-settings).

## <a name="change-enrollment-restriction-priority"></a>A regisztrációs korlátozások prioritásának módosítása

A prioritást akkor használja a rendszer, ha egy felhasználó több olyan csoportnak is a tagja, amelyhez korlátozások vannak hozzárendelve. A felhasználókra a rendszer egyedül a vonatkozó csoportok legmagasabb prioritású korlátozását alkalmazza. Tegyük fel például, hogy Attila tagja az A csoportnak, melyhez egy 5-ös prioritású korlátozás van hozzárendelve, illetve tagja a B csoportnak is, melyhez egy 2-es prioritású korlátozás van hozzárendelve. Ez esetben Attilára csak a 2-es prioritású korlátozást alkalmazza a rendszer.

Az Ön által létrehozott korlátozások az alapértelmezettnél eggyel magasabb prioritást kapnak.

Az eszközregisztráció tartalmaz alapértelmezett korlátozásokat mind az eszköztípusra, mind az eszközszámra vonatkozóan. Ez a két korlátozás az összes felhasználóra érvényes, hacsak felül nem bírálják őket magasabb prioritású korlátozások.

Az összes egyéni korlátozás prioritását módosíthatja.

1. Jelentkezzen be az Azure portálra.
2. Válassza a **További szolgáltatások** lehetőséget, írja be az **Intune** keresési kifejezést, majd válassza az **Intune** lehetőséget.
3. Válassza az **Eszközök regisztrálása** > **Regisztrációs korlátozások** lehetőséget.
4. Vigye az egérmutatót a korlátozás fölé a prioritáslistában.
5. A három függőleges pontot alkotó ikon használatával húzza a prioritást a lista megfelelő helyére.
