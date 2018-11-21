---
title: Hibaelhárítás az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsoft Intune-beli szabályzathasználattal kapcsolatos gyakori problémák és megoldásaik
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: bb55ddc283ce4633b5057d5b96ae2ed6973dcf8a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181768"
---
# <a name="troubleshoot-policies-in-intune"></a>Szabályzatokkal kapcsolatos problémák elhárítása az Intune-ban

Ha problémába ütközik az Intune-szabályzatok érvénybe léptetése vagy kezelése során, kezdje itt. A cikk gyakori problémákat és azok lehetséges elhárítását ismerteti.

## <a name="general-issues"></a>Általános problémák

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Az eszközre vonatkozott bármilyen telepített házirend?
**A probléma leírása:** Nem biztos benne, hogy helyesen lett alkalmazva a szabályzat.

Az Intune-ban az **Eszközök** > **Minden eszköz** területen válassza ki az eszközt, majd válassza az **Eszközkonfiguráció** lehetőséget, ahol minden eszközhöz fel lesznek sorolva a szabályzatok. Minden szabályzat rendelkezik egy **Állapottal**. Az állapot az eszközre érvényes összes szabályzat alkalmazása, valamint a hardver és az operációs rendszer által szabott korlátozások és rendszerkövetelmények együttese alapján elért érték. A lehetséges állapotok az alábbiak:

- **Megfelelő:** Az eszköz megkapta a szabályzatot, és jelenti a szolgáltatásnak, hogy megfelel a beállításnak.

- **Nem alkalmazható:** A szabályzatbeállítás nem alkalmazható. Az iOS-eszközök e-mail beállításai például nem alkalmazhatók az androidos eszközökre.

- **Folyamatban:** A rendszer elküldte a szabályzatot az eszköznek, de az nem jelentette az állapotot a szolgáltatásnak. Például az Android rendszeren csak akkor működik a titkosítás, ha a felhasználó engedélyezi, ezért függőben lehet.

> [!NOTE]
> Ha két különböző korlátozási szintű szabályzat vonatkozik egy eszközre vagy felhasználóra, akkor a gyakorlatban a szigorúbb szabályzat lesz érvényes.

## <a name="issues-with-enrolled-devices"></a>A regisztrált eszközök problémái

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Figyelmeztetés: A hozzáférési szabályok mentése az Exchange szolgáltatásba sikertelen
**Probléma:** A felügyeleti konzolban megjelenik **A hozzáférési szabályok mentése az Exchange szolgáltatásba sikertelen**  figyelmeztetés.

Ha a felügyeleti konzol Helyszíni Exchange-szabályzat munkaterületén szabályzatot hozott létre, de O365-öt használ, az Intune nem kényszeríti ki a konfigurált szabályzatbeállítások használatát. Jegyezze fel a figyelmeztetésben szereplő szabályzatforrást.  Az Exchange helyszíni szabályzat munkaterületen törölje az örökölt szabályokat. Az örökölt szabályok globális Exchange-szabályok az Intune-ban a helyszíni Exchange-hez, és nem relevánsak az O365-nél. Ezután hozzon létre új szabályzatot az O365-höz.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Nem módosítható a különféle regisztrált eszközök biztonsági házirendje
A Windows Phone-telefonok nem teszik lehetővé, hogy a beállításukat követően a felhasználó alacsonyabb biztonsági értékeket konfiguráljon az MDM-en vagy az EAS-en keresztül megadott biztonsági szabályzatokhoz. Ilyen eset például, ha beállítja a **jelszó minimális karakterszámát** 8-ra, majd megpróbálja 4-re csökkenteni. Az eszközhöz már a szigorúbb szabályzat tartozik.

Az eszköz platformjától függően előfordulhat, hogy ha módosítani szeretné a szabályzatot egy kevésbé biztonságos értékre, alaphelyzetbe kell állítania a biztonsági szabályzatokat.

A Windowsban például jobbról befelé pöccintve nyissa meg az asztalon a **Gombok** sávot. Válassza a **Gépház** > **Vezérlőpult** lehetőséget, majd válassza a **Felhasználói fiókok** elemet. A bal oldalon válassza a **Biztonsági szabályzatok alaphelyzetbe állítása** hivatkozást, majd válassza a **Szabályzatok alaphelyzetbe állítása** lehetőséget.

Előfordulhat, hogy az egyéb, például Android, Windows Phone 8.1 vagy újabb, és iOS rendszerű MDM-eszközöket ki kell vonni, majd újból regisztrálni kell a szolgáltatásba egy kevésbé korlátozó szabályzat hozzárendeléséhez.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Az Intune szoftverügyfelet futtató számítógépek problémái

A klasszikus portálra vonatkozik.

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Microsoft Intune-házirendekkel kapcsolatos hibák a policyplatform.log fájlban
Az Intune szoftverügyféllel kezelt Windows számítógépek esetén a policyplatform.log fájlban lévő házirendhibák az eszközön lévő Windows Felhasználói fiókok felügyelete (UAC) nem alapértelmezett beállításainak eredményei lehetnek. Néhány nem alapértelmezett UAC-beállítás hatással lehet a Microsoft Intune ügyféltelepítéseire és a házirendek érvénybe léptetésére.

#### <a name="resolve-uac-issues"></a>UAC-problémák megoldása

1. Vonja ki a számítógépet. Lásd: [Eszközök eltávolítása](devices-wipe.md).

2. Várjon 20 percet az ügyfélszoftver eltávolításáig.

    > [!NOTE]
    > Ne próbálja meg eltávolítani az ügyfelet a Programok és szolgáltatások területről.

3. A Start menüben írja be az **UAC** kifejezést a Felhasználói fiókok felügyelete beállításainak megnyitásához.

4. Mozgassa az értesítési csúszkát az alapértelmezett beállításhoz.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>HIBA: Nem szerezhető be érték a számítógépről, 0x80041013
Ez akkor fordulhat elő, ha a helyi rendszeren lévő idő legalább öt perccel eltér a szinkronizált értéktől. Ha a helyi számítógépen lévő idő nincs szinkronban, a biztonságos tranzakciók meghiúsulnak, mert az időbélyegek érvénytelenek lesznek.

A hiba megoldásához állítsa a helyi időt a lehető legközelebb az internetes időhöz, vagy a hálózaton lévő tartományvezérlőkben megadott időhöz.

### <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](get-support.md) című témakörben leírtak szerint.
