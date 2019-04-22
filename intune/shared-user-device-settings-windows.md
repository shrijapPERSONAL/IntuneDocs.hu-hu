---
title: Windows 10-es megosztott eszközbeállítások - beli Microsoft Intune - |} A Microsoft Docs
description: Adjon hozzá, és használja a Windows 10-es konfigurálhatja az eszközöket, amelyek megosztott, vagy a Microsoft Intune-ban több felhasználó használja. Tekintse meg az összes beállítás listáját, és mit tesznek az eszközökön, beleértve a Microsoft Surface. A Vendég fiók szabályozhatja, fiókok kezelése, és törli az inaktív fiókok, engedélyezése vagy letiltása helyi tárolójára történő mentése, állítsa be a power és beállítások alvó állapotba, válassza ki, amikor frissítések telepítve vannak, és eszközök használata az eszközkonfigurációs profil oktatási környezetben.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/01/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 535f66c68b066454ce9706b1dd1d7a4fce5c265c
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59900880"
---
# <a name="windows-10-and-later-settings-to-manage-shared-devices-using-intune"></a>Megosztott eszközök Intune-nal kezelheti a Windows 10-es és újabb beállításai

Windows 10-es és újabb rendszerű eszközök, például a Microsoft Surface sok felhasználó által használható. Több felhasználóval rendelkező eszközök megosztott eszközök nevezik, és részei a mobileszköz-felügyelet (MDM) megoldások.

A Microsoft Intune-nal, végfelhasználók jelentkezhetnek be a megosztott eszközökre Vendég fiókkal. Mint az eszközön, azok csak a get funkciókat engedélyezi a hozzáférést. Az Intune-rendszergazdaként konfigurálja a hozzáférést, válassza ki a fiókok törlésekor, vezérlő energiagazdálkodási beállításokat és egyéb, a megosztott Windows 10 rendszerű eszközökhöz.

Ez a cikk és ismerteti a rendelkezésre álló beállításokat a Windows 10 (és újabb) eszközkonfigurációs profilban. A profil létrehozásakor az Intune-ban üzembe helyezése, vagy rendelje hozzá a profilt az eszközcsoportok a szervezetben. Ez a profil eszközcsoportokra a vegyes eszköz típusa és operációsrendszer-verziók is hozzárendelhetők.

Ez a funkció az Intune-ban a további információkért lásd: [szabályozhatja a hozzáférést, a partnerek és a megosztott PC vagy több felhasználó-eszköz funkcióinak power](shared-user-device-settings.md). A Windows CSP további információkért lásd: [SharedPC CSP](https://docs.microsoft.com/windows/client-management/mdm/sharedpc-csp).

## <a name="before-your-begin"></a>A Kezdés előtt

[A profil létrehozásához](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Közös használatú eszköz több felhasználó beállításai

- **Megosztott PC mód**: Válasszon **engedélyezése** megosztott PC mód bekapcsolása. Ebben a módban csak egy felhasználó bejelentkezik az eszközre egy időben. Egy másik felhasználó nem tud bejelentkezni, amíg az első felhasználó kijelentkezésekor. **Nincs konfigurálva** (alapértelmezett) elhagyja ezt a beállítást, az Intune által nem felügyelt, és nem leküldéses minden házirendben ezt a beállítást, az eszközön.
- **Vendégfiók**: Válassza ki a bejelentkezési képernyőn egy Vendég beállítás létrehozásához. A vendég nem igényelnek felhasználói hitelesítő adatokat vagy hitelesítést. Ezzel a beállítással létrehoz egy új helyi fiókot minden alkalommal, amikor szolgál. A választható lehetőségek:
  - **Vendég**: Létrehoz egy vendégfiókba helyileg az eszközön.
  - **Tartomány**: Az Azure Active Directory (AD) hoz létre a Vendég fiók.
  - **Vendég- és tartományi**: Létrehoz egy vendégfiókba helyileg az eszközön, és az Azure Active Directory (AD).
- **Fiókkezelés**: Állítsa be **engedélyezése** automatikusan törli a vendégek által létrehozott helyi fiókoknak és az AD és az Azure ad-ben. A felhasználók bejelentkezésekor ki az eszközt, vagy Rendszerkarbantartás futtatásakor, a rendszer törli ezeket a fiókokat. Ha engedélyezve van, is állítsa be:
  - **Fiók törlése**: Válassza ki a fiókok törlésekor: **A storage tárterületre vonatkozó küszöbértéket**, **storage tárterületre vonatkozó küszöbértéket és inaktív küszöbérték**, vagy **jelentkezzen ki után azonnal**. Ezt is adja meg:
    - **Kezdő törlése threshold(%)**: Adja meg a lemezterület százalékában (0 – 100). Ha a teljes lemez-és tárterület a beírt érték alá csökken, a rendszer törli a gyorsítótárazott fiókokat. Folyamatosan törli a fiókok lemezterületet felszabadítása érdekében. A legrégebb inaktív fiókok először törlődnek.
    - **Állítsa le a delete threshold(%)**: Adja meg a lemezterület százalékában (0 – 100). A teljes lemez/tárhely megfelel-e a beírt érték, ha leállítja a törlése.

  Állítsa be **letiltása** , hogy a helyi AD-ben és a vendégek által létrehozott Azure AD-fiókokat.

- **Helyi tároló**: Válasszon **engedélyezve** , hogy a felhasználók mentése folyamatban van, és az eszköz merevlemez-meghajtó a fájlok megtekintéséhez. Válasszon **letiltott** , hogy a felhasználók megtekintéséhez, és mentse helyileg a fájlkezelő használata fájlok. **Nincs konfigurálva** (alapértelmezett) elhagyja ezt a beállítást, az Intune által nem felügyelt, és nem leküldéses minden házirendben ezt a beállítást, az eszközön.
- **Energiagazdálkodási házirendeket**: Ha beállítása **engedélyezve**, felhasználók nem kapcsolhatja ki hibernált állapotba lépni, nem bírálhatják felül minden alvási műveletek (például a fedél bezárása) és az energiagazdálkodási beállítások nem módosíthatók. Ha a beállítása **letiltott**, a felhasználók is hibernált állapot az eszközre, az eszköz alvó a fedél lehajtásakor, és módosíthatják az energiaellátási beállításokat. **Nincs konfigurálva** (alapértelmezett) elhagyja ezt a beállítást, az Intune által nem felügyelt, és nem leküldéses minden házirendben ezt a beállítást, az eszközön.
- **Alvó állapot időkorlátja (másodpercben)**: Adja meg a inaktív másodpercben (0 – 100), mielőtt az eszköz alvó állapotba kerül. Egy ideje nem állít be, ha az eszköz után 60 percig alvó állapotba kerül.
- **Jelentkezzen be, amikor a számítógép felébresztése**: Állítsa be **engedélyezve** jelentkezzen be a jelszót, amikor az eszköz alvó üzemmódban éles felhasználóknak kötelező. Válasszon **letiltott** így a felhasználóknak nem kell megadnia a felhasználónevüket és jelszavukat. **Nincs konfigurálva** (alapértelmezett) elhagyja ezt a beállítást, az Intune által nem felügyelt, és nem leküldéses minden házirendben ezt a beállítást, az eszközön.
- **Karbantartás kezdete (percben az éjfél)**: Adja meg az idő percben (0 – 1440), amikor az automatikus karbantartási feladatokat, például a Windows Update, futtassa. Az alapértelmezett kezdő érték nulla vagy éjfél (`0`) perc. Kezdési idő megadásával az éjfél percek alatt a kezdési idő módosítása Ha azt szeretné, hogy a karbantartási 14 órakor megkezdéséhez, írja be például `120`. Ha azt szeretné, hogy a karbantartási, 8-kor kezdődik, adja meg `1200`.
- **Oktatási házirendek**: Válasszon **engedélyezve** az ajánlott beállítások használatát az eszközöket használ a szigorúbb iskolák részére. Válasszon **letiltott** , az alapértelmezett és ajánlott oktatási házirendek nincsenek használva. **Nincs konfigurálva** (alapértelmezett) elhagyja ezt a beállítást, az Intune által nem felügyelt, és nem leküldéses minden házirendben ezt a beállítást, az eszközön.

  Az oktatási házirendek mire a további információkért lásd: [az oktatásban tevékenykedő felhasználók Windows 10-es konfigurációs javaslatokat](https://docs.microsoft.com/education/windows/configure-windows-for-education).

> [!TIP]
> [Állítsa be egy megosztott vagy Vendég PC](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc) (megnyílik egy másik docs-webhely) egy nagyszerű forrás a Windows 10 szolgáltatást, beleértve a fogalmakat és a csoportházirendeket, a közös módba állítható.

## <a name="next-steps"></a>További lépések

- [Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
- Tekintse meg a beállításokat a [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
