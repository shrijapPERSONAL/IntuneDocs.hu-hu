---
title: "Szabályzatokkal kapcsolatos problémák elhárítása"
description: "Elháríthat szabályzatok konfigurációjával kapcsolatos problémákat."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e97c47dc2d1744f539f569de4c20ee994d05ffd
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/12/2017
---
# <a name="troubleshoot-policies-in-microsoft-intune"></a>Szabályzatokkal kapcsolatos problémák elhárítása a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ha problémába ütközik az Intune-szabályzatok érvénybe léptetése vagy kezelése során, kezdje itt. Ez a témakör néhány gyakori problémát és azok megoldását ismerteti.

## <a name="general-issues"></a>Általános problémák

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Az eszközre vonatkozott bármilyen telepített házirend?
**A probléma leírása:** Nem biztos benne, hogy helyesen lett alkalmazva a házirend.

Az Intune felügyeleti konzoljában az **Eszköztulajdonságok**csoportban minden eszközhöz tartozik egy szabályzatlap. Minden egyes házirend rendelkezik egy **Kívánt érték** és egy **Állapot**jellemzővel. A kívánt érték az az érték, amelyet a házirend hozzárendelésekor el kívánt érni. Az állapot az eszközre érvényes összes házirend alkalmazása, valamint a hardver és az operációs rendszer által szabott korlátozások és rendszerkövetelmények együttese alapján elért érték. A lehetséges állapotok az alábbiak:

-   **Megfelelő:**Az eszköz megkapta a szabályzatot, és jelenti a szolgáltatásnak, hogy megfelel a beállításnak.

-   **Nem alkalmazható:**A szabályzatbeállítás nem alkalmazható. Az iOS-eszközök e-mail beállításai például nem alkalmazhatók az androidos eszközökre.

-   **Folyamatban:**A rendszer elküldte a szabályzatot az eszköznek, de az nem jelentette az állapotot a szolgáltatásnak. Például az Android rendszeren csak akkor működik a titkosítás, ha a felhasználó engedélyezi, ezért függőben lehet.

Az alábbi képernyőképen két világos példa látható:

-   Az **Egyszerű jelszavak engedélyezése** beállított értéke **Igen**, ahogy az a **Kívánt érték** oszlopban látható, az **Állapot** értéke azonban **Nem alkalmazható**. Ez azért van, mert az egyszerű jelszavak az Android-eszközökön nem támogatottak.

-   Ehhez hasonlóan az **iOS-eszközök e-mail beállításai** kiterjesztett szabályzat erre az eszközre nem alkalmazható, mert ez Android-eszköz.

![Az Intune eszközszabályzat](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Ne felejtse el, hogy ha két különböző korlátozási szintű házirend vonatkozik egy eszközre vagy felhasználóra, akkor gyakorlatban a szigorúbb házirend lesz érvényes.


## <a name="issues-with-enrolled-devices"></a>A regisztrált eszközök problémái

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Figyelmeztetés: A hozzáférési szabályok mentése az Exchange szolgáltatásba sikertelen
**Probléma:**A felügyeleti konzolban megjelenik **A hozzáférési szabályok mentése az Exchange szolgáltatásba sikertelen**  figyelmeztetés.

Ha a felügyeleti konzol Helyszíni Exchange-szabályzat munkaterületén szabályzatot hozott létre, de O365-öt használ, az Intune nem kényszeríti ki a konfigurált szabályzatbeállítások használatát. Jegyezze fel a figyelmeztetésben szereplő szabályzatforrást.  A Helyszíni Exchange-szabályzat munkaterületen törölje az örökölt szabályokat, mivel azok a helyszíni Exchange-hez készült Intune-on belüli globális Exchange-szabályok, és nem vonatkoznak az O365-re. Ezután hozzon létre új szabályzatot az O365-höz.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Nem módosítható a különféle regisztrált eszközök biztonsági házirendje
A Windows Phone-telefonok nem teszik lehetővé, hogy a beállításukat követően a felhasználó alacsonyabb biztonsági értékeket konfiguráljon az MDM-en vagy az EAS-en keresztül megadott biztonsági szabályzatokhoz. Ilyen eset például, ha beállítja a **jelszó minimális karakterszámát** 8-ra, majd megpróbálja 4-re csökkenteni. Az eszközhöz már a szigorúbb szabályzat tartozik.

Az eszköz platformjától függően előfordulhat, hogy ha módosítani szeretné a szabályzatot egy kevésbé biztonságos értékre, alaphelyzetbe kell állítania a biztonsági szabályzatokat.
A Windowsban például jobbról befelé pöccintve nyissa meg az asztalon a **Gombok** sávot, és válassza a **Gépház** &gt; **Vezérlőpult** lehetőséget.  Válassza a **Felhasználói fiókok** kisalkalmazást.
A bal oldali navigációs menü alján található egy **Biztonsági házirendek mellőzése** hivatkozás. Válassza ki, majd kattintson a **Házirendek mellőzése** gombra.
Előfordulhat, hogy egyéb MDM-eszközöket (például Android, Windows Phone 8.1 és újabb, valamint iOS) ki kell vonni, majd újból regisztrálni kell a szolgáltatásba egy kevésbé korlátozó házirend alkalmazásához.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Az Intune szoftverügyfelet futtató számítógépek problémái

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Microsoft Intune-házirendekkel kapcsolatos hibák a policyplatform.log fájlban
Az Intune szoftverügyféllel kezelt Windows számítógépek esetén a policyplatform.log fájlban lévő házirendhibák az eszközön lévő Windows Felhasználói fiókok felügyelete (UAC) nem alapértelmezett beállításainak eredményei lehetnek. Néhány nem alapértelmezett UAC-beállítás hatással lehet a Microsoft Intune ügyféltelepítéseire és a házirendek érvénybe léptetésére.

#### <a name="to-resolve-uac-issues"></a>Az UAC-problémák megoldása

1.  Vonja ki a számítógépet az [Eszközök kivonása a Microsoft Intune-nal való felügyelet alól](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management) szakaszban leírtak szerint.

2.  Várjon 20 percet az ügyfélszoftver eltávolításáig.

    > [!NOTE]
    > Ne próbálja meg eltávolítani az ügyfelet a Programok és szolgáltatások területről.

3.  A Start menüben írja be az **UAC** kifejezést a Felhasználói fiókok felügyelete beállításainak megnyitásához.

4.  Mozgassa az értesítési csúszkát az alapértelmezett beállításhoz.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>HIBA: Nem szerezhető be érték a számítógépről, 0x80041013
Ez akkor fordulhat elő, ha a helyi rendszeren lévő idő legalább öt perccel eltér a szinkronizált értéktől. Ha a helyi számítógépen lévő idő nincs szinkronban, a biztonságos tranzakciók meghiúsulnak, mert az időbélyegek érvénytelenek lesznek.

A hiba megoldásához állítsa a helyi időt a lehető legközelebb az internetes időhöz, vagy a hálózaton lévő tartományvezérlőkben megadott időhöz.








### <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.
