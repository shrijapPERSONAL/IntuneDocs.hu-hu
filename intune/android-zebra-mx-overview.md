---
title: Zebra mobilitási-bővítmények használata az Android-eszközökön a Microsoft Intune – Azure |} A Microsoft Docs
description: A Microsoft Intune segítségével kezelheti és Android rendszerű Zebra mobilitási Extensions (MX) Zebra eszközökről. Tekintse meg az összes lépését, beleértve a vállalati portál alkalmazást, az alkalmazás közvetlen telepítéséhez, eszköz-rendszergazdai szerepkör hozzárendelése, hozzon létre egy StageNow profilt, és több.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 69814b91978aa3cd74c4dc239b099883ae402af9
ms.sourcegitcommit: b0cf661145ccc6e3518db620af199786a623a0d9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64764771"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Használhatja és kezelheti a Zebra eszközök Zebra mobilitási bővítmények Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune szolgáltatások és alkalmazások kezelését és az eszköz beállítások konfigurálásával gazdag készletét tartalmazza. Ezek a beépített funkciók és beállítások Android-eszközök Zebra technológiák, más néven "Zebra eszközök" által gyártott kezelésére használhatók.

Android-eszközön használja **mobilitási bővítmények MX** profilok testreszabásához, vagy adjon hozzá további Zebra-specifikus beállításokat.

Ez a cikk bemutatja, hogyan Zebra mobilitási bővítmények MX használandó Zebra eszközökön a Microsoft Intune-ban.

Ez a funkció az alábbiakra vonatkozik:

- Android

A vállalat a kiskereskedelmi, a gyári és másokról Zebra eszközök használjuk. Például egy közvetítő Ön és a környezet tartalmaz Zebra mobileszközök értékesítési hozzárendeli által használt több ezer. Az Intune segítségével kezelheti ezeket az eszközöket a mobileszköz-felügyelet (MDM) megoldás részeként.

Az Intune-ban, Zebra eszközöket regisztrálhatja, az üzleti alkalmazások telepítése az eszközökre. "Eszköz" profilok lehetővé teszik a Zebra-specifikus beállítások kezeléséhez MX-profilok létrehozása.

## <a name="before-you-begin"></a>Előkészületek

- Győződjön meg arról, hogy az StageNow Zebra technológiák asztali alkalmazás legújabb verziójával rendelkezik.
- Ügyeljen arra, hogy ellenőrizze, hogy [Zebra a teljes MX funkció mátrix](http://techdocs.zebra.com/mx/compatibility) (Zebra a webhely megnyitása) ellenőrizze, hogy a létrehozott profilok kompatibilisek-e az eszköz MX verziója, az operációs rendszer verziója és modell.
- Bizonyos eszközök, például TC20/25-eszközök nem támogatják a rendelkezésre álló MX a funkciók StageNow. Ügyeljen arra, hogy ellenőrizze, hogy [Zebra a szolgáltatás mátrix](http://techdocs.zebra.com/mx/tc2x/) (Zebra a webhely megnyitása) frissített támogatási információkat.

## <a name="step-1-install-the-latest-company-portal-app"></a>1. lépés: A legújabb vállalati portál alkalmazás telepítésekor

Az eszközön nyissa meg a Google Play áruházban, és töltse le, és az Intune vállalati portál alkalmazás telepítése a Microsoft. Amikor telepíti a Google Play áruházból, a vállalati portál alkalmazás lekérdezi a frissítéseket, és automatikusan kijavítja.

Ha a Google Play áruházban nem érhető el, töltse le a [a Microsoft Intune vállalati portál Android](https://www.microsoft.com/download/details.aspx?id=49140) (nyit meg egy másik Microsoft-webhelyhez), és [közvetlen telepítése,](#sideload-the-company-portal-app) (a jelen cikkben). Ha ezzel a módszerrel telepíti, az alkalmazás nem kapják a frissítéseket, vagy automatikusan kijavítja. Érdemes rendszeresen frissíteni, és manuálisan javítása az alkalmazás.

### <a name="sideload-the-company-portal-app"></a>A céges portál alkalmazás közvetlen telepítése

"Saját telepítési" akkor, ha a Google Play alkalmazás telepítése nem használja. A vállalati portál alkalmazás közvetlen telepítése StageNow használja. 

Az alábbi lépéseket működéséről nyújt áttekintést. Részletes Zebra a dokumentációjában talál. [Egy mobileszköz-felügyeleti StageNow használatával regisztrálása](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (Zebra a webhely megnyitása) jól lehet.

1. StageNow, hozzon létre egy profilt **Regisztrálás az MDM-ben**.
2. A **üzembe helyezési**, válassza ki a mobileszköz-kezelési ügynök fájl letöltéséhez.
3. Állítsa be a **támogatási alkalmazás** és **konfiguráció letöltése** lépések **nem**.
4. A **letöltése MDM**válassza **fájl adatátviteli/másolása**. Adja hozzá a forrás- és a vállalati portál Android csomag-(APK-).
5. A **indítsa el a mobileszköz-kezelési**, módosítsa az alapértelmezett értékeket, mint-akkor. Adja hozzá a következő adatokat:

    - **Csomag neve**: `com.microsoft.windowsintune.companyportal`
    - **Osztálynév**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Továbbra is a profil közzétételét és felhasználását, a StageNow alkalmazást az eszközön. A vállalati portál alkalmazás van telepítve, és megnyitja az eszközön.

> [!TIP]
> StageNow, és hogyan kezeli a további információkért lásd: [StageNow Android-eszköz átmeneti](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (Zebra a webhely megnyitása).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>2. lépés: Győződjön meg róla a vállalati portál alkalmazás eszköz-rendszergazdai szerepkör

A vállalati portál alkalmazás eszköz-rendszergazdai Android-eszközök kezeléséhez szükséges. Az eszköz-rendszergazdai szerepkör aktiválásához bizonyos Zebra eszközök közé tartozik a felhasználói felület (UI) az eszközön. Ha az eszköz felhasználói Felületet is tartalmaz, a vállalati portál alkalmazást a kéri megadni az eszköz-rendszergazdai során [regisztrációs](#step-3-enroll-the-device-in-to-intune) (a jelen cikkben).

Ha egy felhasználói felület nem érhető el, használja a **DevAdmin Manager** StageNow hozhat létre egy profilt, amely manuálisan engedélyezi az eszköz-rendszergazdai a vállalati portál alkalmazásba a.

Az alábbi lépéseket működéséről nyújt áttekintést. Részletes Zebra a dokumentációjában talál. 
[Lapozófájl-kapacitás mód beállítása akkumulátor, eszköz-rendszergazdai](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (Zebra a webhely megnyitása) jól lehet.

1. StageNow, hozzon létre egy profilt, és válassza **Xpert mód**.
2. Adjon hozzá **DevAdmin Manager** a profilhoz.
3. Állítsa be **felügyeleti művelet** való **eszköz rendszergazdaként bekapcsolása**.
4. Állítsa be **eszköz felügyeleti csomag neve** való `com.microsoft.windowsintune.companyportal`.
5. Állítsa be **eszközt rendszergazdai osztálynév** való `com.microsoft.omadm.client.PolicyManagerReceiver`.

Továbbra is a profil közzétételét és felhasználását, a StageNow alkalmazást az eszközön. A vállalati portál alkalmazást az eszköz-rendszergazdai szerepkör kapnak.

## <a name="step-3-enroll-the-device-in-to-intune"></a>3. lépés: Az eszköz regisztrálása az Intune-bA

Az első két lépések elvégzése után a vállalati portál alkalmazás telepítve van az eszközön. Az eszköz készen áll a regisztrálhatók az Intune-hoz.

[Android-eszközök regisztrálása](android-enroll.md) felsorolja azokat a lépéseket. Ha sok Zebra eszköze van, előfordulhat, hogy használni kívánt egy [eszközregisztráció-kezelői (DEM-) fiók](device-enrollment-manager-enroll.md). DEM-fiókkal is eltávolítja az a lehetőség törli a regisztrációt a céges portál alkalmazásból, úgy, hogy a felhasználók nem könnyű az eszköz regisztrációját az.

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>4. lépés: StageNow a felügyeleti profil létrehozása

StageNow használatával hozzon létre egy profilt, amely az eszköz a kezelni kívánt beállításait konfigurálja. Részletes Zebra a dokumentációjában talál. [Profilok](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (Zebra a webhely megnyitása) jól lehet.

A profil létrehozásakor a StageNow, a legutóbbi lépésben, válasszon **exportálása az MDM-**. Ez létrehoz egy XML-fájlt. Mentse el ezt a fájlt. Egy későbbi lépésben kell.

> [!TIP]
> Azt javasoljuk, hogy a profil tesztelése előtt eszközökre telepíti központilag azt a szervezetében. Az utolsó lépésben a számítógépen, a StageNow-profilok létrehozása során teszteléséhez használja a **tesztelése** beállítások. Ezt követően lefoglalhatja a StageNow által létrehozott fájlt a StageNow alkalmazást az eszközön. 
> 
> A StageNow alkalmazást az eszközön a profil tesztelésekor létrehozott naplók jeleníti meg. [Használat StageNow naplók Zebra az Intune-ban Android rendszerű eszközökön](android-zebra-mx-logs-troubleshoot.md) StageNow naplók segítségével megismerheti a hibák szóló információt tartalmaz.

> [!NOTE]
> Alkalmazások hivatkozhat, frissítési csomagok vagy más frissítésfájlok StageNow profilját szeretné-e az eszközt, ezeket a frissítéseket. A frissítések beszerzéséhez a eszköz kell csatlakozni a StageNow rendszerbe állítási kiszolgáló a profil alkalmazása esetén. 
> 
> Vagy használhatja a beépített funkciók az Intune-ban ezeket a módosításokat, beleértve a beolvasásához: 
> - Az alkalmazás-felügyeleti funkciót [hozzáadása](apps-add.md), [üzembe helyezése](apps-deploy.md), frissítéséhez és [figyelő](apps-monitor.md) alkalmazások.
> - Kezelése [rendszer és alkalmazás-frissítések](device-restrictions-android-for-work.md#device-owner-only) Android Enterprise rendszerű eszközökön

Miután a fájl teszteléséhez a következő lépés az telepítse a profilt az eszközök Intune-nal.

> [!NOTE]
> Minden eszköz egy profilt. Ha több StageNow profilt az eszközökön telepítendő, a StageNow profilok exportálása, és a beállítások egyetlen XML-fájlban egyesíteni, az Intune-hoz való hozzáadása előtt. 
> 
> Két, ugyanabban a XML-fájlban ugyanahhoz a tulajdonsághoz konfiguráló beállítások nem szeretné. A célja, hogy az eszköz beállításai között.

## <a name="step-5-create-a-profile-in-intune"></a>5. lépés: Hozzon létre egy profilt az Intune-ban

Az Intune-ban eszközkonfigurációs profil létrehozása:

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza az **Android** lehetőséget.
    - **Profil típusa**: Válassza ki **MX-profil (csak Zebra)**.

4. A **MX profil .xml formátumú**, adja hozzá az XML-profil fájl [StageNow exportált](#step-4-create-a-device-management-profile-in-stagenow) (a jelen cikkben).
5. A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. A házirend létrehozása és jelennek meg a listában.

A profil létrejött, de egyelőre nem csinál semmit. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

A következő alkalommal ellenőrzi az eszköz konfigurációs frissítések, az MX-profil telepítve azon az eszközön. Eszközök szinkronizálása az Intune-nal, amikor regisztrálják az eszközöket, és körülbelül 8 óránként. Emellett [kényszerítheti az Intune-ban](device-sync.md). Vagy nyissa meg az eszközön a **céges portál alkalmazás** > **beállítások** > **szinkronizálási**. 

> [!TIP]
> - Biztonsági okokból nem jelenik meg a profil XML-szöveg után mentse. A szöveg van titkosítva, és megjelenik csak csillagot (`****`). Referenciaként azt javasoljuk, hogy az MX-profilok másolatának mentése, mielőtt hozzáadhatná őket az Intune-hoz.
> 
> - Profil frissítése után Zebra eszközökhöz van hozzárendelve, hozzon létre egy frissített StageNow XML-fájlt, módosítsa a meglévő Intune-profilt, és adja hozzá az új StageNow XML-fájlt. Ez az új fájl felülírja az előző StageNow házirendet a profilban.

## <a name="next-steps"></a>További lépések

- [Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
- [StageNow naplók használata a hibaelhárításhoz Zebra eszközök](android-zebra-mx-logs-troubleshoot.md).
