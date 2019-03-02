---
title: Ellenőrizze a sikeres vagy sikertelen biztonsági előírások a Microsoft Intune – Azure |} A Microsoft Docs
description: Ellenőrizze a hiba történt, ütközés és sikerességének állapotát, amikor a biztonsági előírások telepítése felhasználók és eszközök a Microsoft Intune mobileszköz-kezelést. Hibaelhárítás a naplókba, és a jelentési szolgáltatások használatával az Intune-ban való használatáról.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/24/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b853d42efc247f6080cc4ed6ad8b4943b85b3215
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230822"
---
# <a name="monitor-the-security-baseline-and-profile-in-microsoft-intune"></a>A biztonsági alapkonfiguráció és a Microsoft Intune-ban profil figyelése

Nincsenek különböző megfigyelési lehetőségek, amikor biztonsági alapterv használatával. Figyelheti a biztonsági alaptervek profilt, amely a felhasználókra és eszközökre alkalmazható. A tényleges alapkonfiguráció és azokat az eszközöket, amelyek az ajánlott értékek egyeznie (vagy nem egyezik) is figyelheti.

Ez a cikk végigvezeti mindkét megfigyelési lehetőségeket.

[Az Intune-ban biztonsági előírások](security-baselines.md) további részleteket a biztonsági alapterveket szolgáltatás a Microsoft Intune-ban.

## <a name="monitor-the-baseline-and-your-devices"></a>Az alapkonfiguráció és az eszközök figyelése

Az alapkonfiguráció monitorozásához kap betekintést a Microsoft javaslatok alapján az eszközök biztonsági állapotát.

> [!NOTE]
> Miután először az alapterv hozzá van rendelve, a jelentések is a frissítése akár 24 órát igénybe vehet. Ezt követően azok frissítése akár 6 órát vehet.

1. Az a [az Azure portal](https://portal.azure.com/), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza ki **biztonsági előírások (előzetes verzió)** > Válassza ki az alapkonfigurációt.
3. A **áttekintése**, a diagram mutatja be, hogy hány eszköz érinti az alapkonfiguráció választotta, és a különböző állapotok:

    ![Az eszközök állapotának ellenőrzése](./media/security-baselines-monitor/overview.png)

    Az alábbi állapotok lehetségesek:

    - **Egyezések alapkonfiguráció**: Az alapkonfiguráció beállításokról felel meg az ajánlott beállításokat.
    - **Nem felel meg a referenciakonfiguráció**: Legalább egy beállítást az alapkonfiguráció nem felel meg az ajánlott beállításokat.
    - **Nincs megfelelően konfigurálva**: Legalább egy beállítást nincs megfelelően konfigurálva. Ez az állapot azt jelenti, hogy a beállítás az ütközést, hiba vagy függőben van.
    - **Nem alkalmazható**: Legalább egy beállítást nem alkalmazható, és nem alkalmazza.

4. Válassza ki a állapotok rendelkező eszközök egyikét. Jelölje be például a **Misconfigured** állapotát.

5. Adott állapotú összes eszköz listája látható. Jelöljön ki egy adott eszközt, további információért. 

    Válassza ki a következő példában **eszközkonfiguráció** > Válassza ki a profilt a hibás állapotú:

    ![Az eszközök állapotának ellenőrzése](./media/security-baselines-monitor/device-configuration-profile-list.png)

    Válassza ki a hibát profilt. A profil, és azok állapotát az összes beállítás listája látható. Most görgethet keresse meg a hibát okozó beállítást:

    ![A hibát okozó beállítást](./media/security-baselines-monitor/profile-with-error-status.png)

Ez a jelentéskészítés segítségével tekintse meg a problémát okozó profil beállításait. A házirendek és profilok eszközökre telepített további részleteket is kaphat.

> [!NOTE]
> Ha egy tulajdonság értéke **nincs konfigurálva** az alaptervet, a rendszer figyelmen kívül hagyja, és nincs korlátozás érvényben vannak. A tulajdonság nem jelenik meg minden olyan jelentési.

## <a name="monitor-the-profile"></a>A profil figyelése

Figyelés a profil lehetővé teszi az eszközök üzembe helyezési állapotát, de nem a biztonsági állapotot az általános javaslatok alapján betekintést.

1. Válassza ki az Intune-ban **biztonsági előírások** > Válassza ki az alapkonfigurációt > **létrehozott profilok**.

2. Válasszon egy profilt. A **áttekintése**, a kép bemutatja, hogy hány eszköz és a felhasználók rendelkeznek a hozzárendelt profil:

    ![Tekintse meg, hány eszközök és felhasználók hozzárendelése biztonsági alapterveket profiljának](./media/security-baselines-monitor/existing-profile-overview.png)

3. A **kezelés** > **tulajdonságok**, az összes jelennek meg a beállításokat az alaptervet. Ezek a beállítások bármelyikét is módosíthatja:

    ![Tekintse meg, és a biztonsági alapterveket profil beállításainak frissítése](./media/security-baselines-monitor/manage-settings.png)

4. A **figyelő**, a profil telepítési állapotát láthatja az egyes eszközöket, a felhasználók állapotát és az egyes beállítások az alapkonfiguráció állapotát:

    ![Biztonsági alapterveket profil különböző figyelő beállításainak megjelenítéséhez](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Hibaelhárítás a használatával állapot beállításonként

Üzembe helyezett egy biztonsági alaptervet, de a központi telepítés állapota: Hiba történt. Az alábbi lépéseket a hiba elhárításáról útmutatást nyújtanak.

1. Válassza ki az Intune-ban **biztonsági előírások** > Válassza ki az alapkonfigurációt > **létrehozott profilok**.
2. Profil kiválasztása > alatt **figyelő** > **állapot beállításonként**.
3. A tábla összes beállítás és az egyes beállítások állapotát mutatja. Válassza ki a **hiba** oszlop vagy a **ütközés** oszlop a hibát okozó beállítást.

### <a name="mdm-diagnostic-information"></a>Mobileszköz-kezelési diagnosztikai információk

Most már ismeri a problémás beállítást. A következő lépés, hogy ismerje meg, hogy miért Ez a beállítás okozza-e hiba vagy ütközés. 

A Windows 10-eszközökön nincs MDM beépített diagnosztikai adatokat jelentést. Ez a jelentés az alapértelmezett értékeket, aktuális értékeit tartalmazza, sorolja fel a szabályzat, jeleníti meg, ha az eszköz és a felhasználó több telepítették. Ez a jelentés a segítségével megállapítható, hogy miért a beállítás egy ütközés vagy hiba okozza.

1. Az eszközön, Ugrás **beállítások** > **fiókok** > **hozzáférés munkahelyi vagy iskolai**.
2. Válassza ki a fiókot > **Info** > **speciális diagnosztikai jelentés** > **jelentés létrehozása**.
3. Válasszon **exportálása**, és nyissa meg a létrehozott fájlt.
4. Keresse meg a jelentést, a hiba vagy ütközés beállítás a jelentés különböző szakaszaiban.

  Keresse meg például a **konfigurációs források és célerőforrások regisztrált** szakasz vagy a **házirendek nem felügyelt** szakaszban. Miért hiba vagy ütközés miatt képet kaphat.

[A Windows 10 MDM hibáinak diagnosztizálása](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) további információkkal szolgál a beépített jelentés.

> [!TIP]
> - Egyes beállítások is listázza a GUID Azonosítót. Ez a helyi beállításjegyzékben (regedit) minden olyan értékek beállítása a GUID kereshet.
> - Az eseménynaplókat is tartalmazhat néhány hiba adatok a problémás (**Eseménynapló** > **alkalmazások és szolgáltatásnaplók**  >   **A Microsoft** > **Windows** > **DeviceManagement – Enterprise-diagnosztikai-szolgáltató** > **rendszergazda** ).

## <a name="next-steps"></a>További lépések

[Eszközprofilok figyelése](device-profile-monitor.md) és [tekintse meg néhány gyakori problémák és megoldásuk](device-profile-troubleshoot.md).
