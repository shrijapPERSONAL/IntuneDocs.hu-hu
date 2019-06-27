---
title: Azure-beli Microsoft Intune - kernel bővítmények profil létrehozása macOS |} A Microsoft Docs
titleSuffix: ''
description: Adja hozzá, vagy létrehozhat egy macOS-eszközprofilt, és konfigurálja kernel-bővítmények lehetővé teszik a felhasználó felülbírálása, a csoport azonosítóját, és a egy csomagot és a csoport azonosító hozzáadása a Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd2e03c09cb2bed49ee7607283bf63e2c3ae67da
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67404013"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>MacOS kernel-kiterjesztések hozzáadása az Intune-ban

MacOS rendszerű eszközökön a rendszermag szintjén funkciókat adhat hozzá. Ezek a szolgáltatások eléréséhez részek az operációs rendszer, amely a rendszeres programok nem fér hozzá. A szervezet konkrét igényeinek megfelelő vagy nem elérhető alkalmazás, egy eszközt a szolgáltatás, és így tovább előfordulhat, hogy rendelkeznek. 

Kernel-bővítmények, amelyek mindig engedélyezett az eszközök betöltése hozzáadásához adja hozzá a "kernel-bővítmények" (KEXT) a Microsoft Intune, és ezen bővítmények telepítését az eszközökön.

Például olyan vírus beolvasási program, amely ellenőrzi az eszköz rosszindulatú rendelkezik. A víruskereső program kernel bővítmény az Intune-ban engedélyezett kernel bővítményeként adhat hozzá. Ezután "hozzárendelése" a bővítményt a MacOS rendszerű eszközökhöz.

Ezzel a funkcióval a rendszergazdák engedélyezhetik a felhasználók felülbírálják a kernel-bővítmények, csapat azonosítók hozzáadása, és adott kernel-kiterjesztések hozzáadása az Intune-ban.

Ez a funkció az alábbiakra vonatkozik:

- a macOS 10.13.2 és újabb verziók

Ez a funkció használatához eszközök kell lennie:

- Az Apple eszköz beléptetési Program (DEP) segítségével Intune-ban regisztrált. [MacOS-eszközök automatikus regisztrálása](device-enrollment-program-enroll-macos.md) tartalmaz további információkat.

  VAGY

- A "jóváhagyott a felhasználó regisztrációja" Intune-ban regisztrált (az Apple-kifejezés). [A módosításokat a macOS High Sierra kernel-bővítmények előkészítése](https://support.apple.com/en-us/HT208019) (megnyílik az Apple webhelyén) is tartalmaz további információkat.

Az Intune használja a "profilok" hozhat létre, és ezeket a beállításokat a szervezet igényeinek megfelelően. Után ezeket a funkciókat ad hozzá egy profilt, amit leküldéses, vagy telepítse a profilt a macOS-eszközökhöz a szervezetben.

Ez a cikk bemutatja, hogyan hozhat létre eszközkonfigurációs profil kernel-bővítmények használata az Intune-ban.

> [!TIP]
> A rendszermag-bővítmények további információkért lásd: [kernel-bővítmény áttekintése](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (az Apple webhelyén nyílik meg).

## <a name="what-you-need-to-know"></a>Amit még tudnia kell

- Előjel nélküli, örökölt kernel bővítményeket adhat hozzá.
- Mindenképpen adja meg a megfelelő csoportnak azonosítóját és a csomagazonosítók a kernel-bővítmény. Az Intune nem ellenőrzi a beírt értékeket. Ha téves információkat ad meg, a bővítményt az eszközön nem fog működni.

> [!NOTE]
> Az Apple, amely aláírási és az összes szoftver notarization kapcsolatos információkat. MacOS-gépeken 10.14.5 és újabb, kernel Intune használatával telepített bővítmények nem felel meg az Apple notarization szabályzatnak kell.
>
> Információk a notarization a házirend, és frissítéseket vagy módosításokat lásd a következőket:
>
>  - [Az alkalmazás előtt terjesztési notarizing](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (nyitja meg az Apple webhelyén.) 
>  - [A módosításokat a macOS High Sierra kernel-bővítmények előkészítése](https://support.apple.com/en-us/HT208019) (nyitja meg az Apple webhelyén.)

## <a name="create-the-profile"></a>A profil létrehozása

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki **macOS**
    - **Profil típusa**: Válassza ki **bővítmények**.
    - **Beállítások**: Adja meg a konfigurálni kívánt beállításokat. Az összes beállítások listáját, és mit tesznek lásd:

        - [macOS](kernel-extensions-settings-macos.md)

4. Ha elkészült, a módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

A profil létrehozásáról és jelennek meg a listában. Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

## <a name="next-steps"></a>További lépések

A profil létrehozását követően készen áll hozzá kell rendelni. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).
