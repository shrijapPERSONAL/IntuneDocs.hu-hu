---
title: Hibaelhárítás az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Tekintse meg a beépített hibaelhárítás szolgáltatással, és olvassa el kapcsolatos gyakori problémák vagy a problémákat és azok megoldásait a megfelelőségi szabályzatokról és alkalmazáskonfigurációs profilok használata a Microsoft Intune-ban
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d1f790aeedff1e13ecc220ed7a6d8f311e12585
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57460512"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>Házirendek és profilok hibaelhárítása és az Intune-ban

A Microsoft Intune hibaelhárítási szolgáltatásai néhány beépített. Ezek a funkciók használatával hibaelhárításához a megfelelőségi szabályzatokról és konfigurációs profilokat a környezetben.

Ez a cikk néhány gyakori hibaelhárítási eljárásokat, és ismerteti a problémák léphetnek fel.

## <a name="use-built-in-troubleshooting"></a>Használja a beépített hibáinak elhárítása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza ki **hibaelhárítása**:

    ![Az Intune-ban nyissa meg a Súgó és támogatás, és válassza ki a hibaelhárítás](./media/help-and-support-troubleshoot.png)

3. Válasszon **felhasználó kiválasztása** > Válassza ki a felhasználót, hogy a probléma > **kiválasztása**.
4. Ellenőrizze, hogy **Intune-licencet** és **fiók állapota** is zöld ellenőrzések megjelenítése:

    ![Az Intune-ban válassza ki a felhasználót, és ellenőrizze a fiók állapota és az Intune-licencet az állapot zöld ellenőrzések jelek megjelenítése](./media/account-status-intune-license-show-green.png)

    **Hasznos hivatkozások**:

    - [Licencek hozzárendelése, így a felhasználók regisztrálhatják eszközeiket](licenses-assign.md)
    - [Felhasználók hozzáadása az Intune-hoz](users-add.md)

5. A **eszközök**, keresse meg az eszközt, hogy a probléma. Tekintse át a különböző oszlopból:

    - **Felügyelt**: Egy eszköz megfelelőségi vagy konfigurációs szabályzatokkal fogadására, ezt a tulajdonságot kell megjelennie **MDM** vagy **EAS-/ MDM**.

      - Ha **felügyelt** nincs beállítva **MDM** vagy **EAS-/ MDM**, majd az eszköz nincs regisztrálva. Megfelelőségi vagy konfigurációs szabályzatokat, nem kap, amíg a rendszer regisztrálja az eszközöket.

      - Az alkalmazásvédelmi szabályzatok (mobilalkalmazás-kezelés) az eszközöknek nincs szükségük. További információkért lásd: [létrehozása és hozzárendelése az alkalmazásvédelmi szabályzatok](app-protection-policies.md).

    - **Azure AD-csatlakozás típusa**: Jelölje meg **munkahelyi** vagy **AzureAD**.
 
      - Ha ez az oszlop **nincs regisztrálva**, előfordulhat, hogy regisztrációs problémáját. Általában regisztrációjának törlése, és az eszköz adták feloldása ebben az állapotban.

    - **Intune-kompatibilis**: Meg kell **Igen**. Ha **nem** jelenik meg, előfordulhat, hogy egy problémát a megfelelőségi szabályzatok, vagy az eszköz nem csatlakozik az Intune szolgáltatáshoz. Például az eszköz ki van kapcsolva, vagy nincs hálózati kapcsolat. Végül, az eszköz nem megfelelővé válik, akár 30 nap letelte után.

      További információkért lásd: [eszközmegfelelőségi szabályzatok – első lépések](device-compliance-get-started.md).

    - **Az Azure AD-kompatibilis**: Meg kell **Igen**. Ha **nem** jelenik meg, előfordulhat, hogy egy problémát a megfelelőségi szabályzatok, vagy az eszköz nem csatlakozik az Intune szolgáltatáshoz. Például az eszköz ki van kapcsolva, vagy nincs hálózati kapcsolat. Végül, az eszköz nem megfelelővé válik, akár 30 nap letelte után.

      További információkért lásd: [eszközmegfelelőségi szabályzatok – első lépések](device-compliance-get-started.md).

    - **Utolsó beadás**: Kell egy legutóbbi dátuma és időpontja. Alapértelmezés szerint az Intune-eszközök ellenőrzés 8 óránként.

      - Ha **utolsó beadás** 24 óránál tovább áll, előfordulhat, hogy egy hiba történt az eszközön. Olyan eszköz, amely nem vehető fel a szabályzatok nem kapnak az Intune-ból.

      - Bejelentkezés kényszerítése:
        - Az Android-eszközön nyissa meg a céges portál alkalmazás > **eszközök** > Válassza ki az eszközt a listából > **eszközbeállítások ellenőrzése**.
        - Az iOS-eszközön nyissa meg a céges portál alkalmazás > **eszközök** > Válassza ki az eszközt a listából > **beállítások ellenőrzése**. 
        - A Windows-eszközön nyissa meg a **beállítások** > **fiókok** > **hozzáférés munkahelyi vagy iskolai** > Válassza ki a fiók vagy MDM-regisztráció >  **Adatok** > **szinkronizálási**.

    - Válassza ki az eszközt, a házirend-specifikus információk megtekintéséhez.

      **Eszközmegfelelőség** jeleníti meg a tartományvezérlők állapotait az eszközhöz rendelt megfelelőségi szabályzatok.

      **Eszközkonfiguráció** jeleníti meg a állapotok konfigurációs házirendek hozzárendeli az eszközhöz.

      Ha a várt szabályzatok nem jelennek meg a **Eszközmegfelelőség** vagy **eszközkonfiguráció**, majd a házirendek nem célzott megfelelően. Nyissa meg a szabályzatot, és rendelje hozzá a szabályzatot a felhasználó vagy eszköz számára.

      **Szabályzatok**:

      - **Nem alkalmazható**: Ez a szabályzat ezen a platformon nem támogatott. Például az iOS-szabályzatok az Android nem működnek. Samsung KNOX-szabályzatok nem működnek a Windows-eszközökön.
      - **Ütközés**: Nincs az eszközt, hogy az Intune nem írhatja felül a meglévő beállításokat. Vagy az ugyanazt a beállítást különböző értékekkel telepített két szabályzat.
      - **Függőben lévő**: Az eszköz az Intune-ban, hogy lekérje a házirendet nem jelentkezett. Vagy az eszköz megkapta a házirendet, de az nem jelentette az állapotot az Intune-hoz.
      - **Hibák**: Hibák és a lehetséges megoldásokért keresse ki [vállalati erőforrás-hozzáférési problémák hibaelhárítása](troubleshoot-company-resource-access-problems.md).

      **Hasznos hivatkozások**: 

      - [Az eszközmegfelelőségi szabályzatok üzembe helyezésének módjai](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
      - [Eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Nem tudja biztosan, ha a profil megfelelően van-e érvényben

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza ki **eszközök** > **minden eszköz** > Válassza ki az eszközt > **eszközkonfiguráció**. 

    Minden eszköz a profilok listája. Minden profil egy **állapot**. Az állapot vonatkozik, az összes hardver és az operációs rendszer korlátozásokat és követelményeket, ideértve a hozzárendelt profilok együttese. Lehetséges állapotok a következők:

    - **Megfelel**: Az eszköz kapott a profil és a jelentések az Intune-hoz, amely megfelel a beállításnak.

    - **Nem alkalmazható**: A profil beállítás nem alkalmazható. IOS-eszközök e-mail beállításai például egy Android-eszközre nem vonatkoznak.

    - **Függőben lévő**: A profilt az eszköznek továbbítja, de az állapot nem jelentette az Intune-ban. Például az Android rendszeren csak akkor működik a titkosítás, ha a felhasználó engedélyezi, ezért függőben lehet.

**Hasznos hivatkozás**: [Konfigurációs eszközprofilok figyelése](device-profile-monitor.md)

> [!NOTE]
> Ha két különböző korlátozási szintű szabályzat vonatkozik egy eszközre vagy felhasználóra, akkor a gyakorlatban a szigorúbb szabályzat lesz érvényes.

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Riasztás: Az Exchange hozzáférési szabályok mentése sikertelen volt

**A probléma**: A riasztás **a hozzáférési szabályok mentése az Exchange-hez nem sikerült** a felügyeleti konzolon.

Szabályzatok létrehozása a helyszíni Exchange-szabályzat munkaterületen (felügyeleti konzol), de az Office 365-höz használ, ha a konfigurált szabályzatbeállítások kényszeríti nem Intune-ban. Kattintson a riasztásra jegyezze fel. A helyszíni Exchange-szabályzat munkaterületen törölje az örökölt szabályokat. Az örökölt szabályokat globális Exchange-szabályok a helyszíni Exchange-hez az Intune-ban, és nem releváns, az Office 365-höz. Ezután hozzon létre új szabályzatot az Office 365-höz.

[Az Intune helyszíni Exchange connector hibaelhárítása](troubleshoot-exchange-connector.md) jól lehet.

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Biztonsági házirendek a regisztrált eszközökhöz nem módosítható.

Windows Phone-eszközök nem teszik lehetővé a biztonsági szabályzatok beállítása az MDM-en vagy az EAS használatával, hogy a beállításukat követően őket. Például, ha beállítja egy **legalább hány karakterből álló jelszót** 8, és próbálja meg a 4-re csökkenteni. A szigorúbb szabályzat az eszközre érvényes.

Az eszköz platformjától függően meg szeretné változtatni a szabályzatot egy kevésbé biztonságos értékre, ha, előfordulhat, hogy alaphelyzetbe kell állítania a biztonsági szabályzatokat.

A Windowsban például jobbról befelé pöccintve nyissa meg az asztalon a **Gombok** sávot. Válasszon **beállítások** > **vezérlőpultot** > **felhasználói fiókok**. A bal oldalon válassza a **Biztonsági szabályzatok alaphelyzetbe állítása** hivatkozást, majd válassza a **Szabályzatok alaphelyzetbe állítása** lehetőséget.

Más mobileszköz-kezelési eszközök, például Android, iOS és Windows Phone 8.1-es, szükség lehet kevésbé korlátozó szabályzat alkalmazásához vonni, majd.

[Eszközök regisztrálásával kapcsolatos problémák elhárítása](troubleshoot-device-enrollment-in-intune.md) jól lehet.

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Számítógépek az Intune szoftveres ügyfele – klasszikus portál használatával

> [!NOTE]
> Ez a szakasz a klasszikus portálon vonatkozik. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Microsoft Intune-házirendekkel kapcsolatos hibák a policyplatform.log fájlban

Az Intune szoftveres ügyfele, a hibák házirend által felügyelt Windows rendszerű számítógépekhez a `policyplatform.log` fájl lehet a nem alapértelmezett beállítások a a Windows felhasználói fiókok felügyelete (UAC) az eszközön. Néhány nem alapértelmezett UAC-beállítás hatással lehet a Microsoft Intune ügyféltelepítéseire és a házirendek érvénybe léptetésére.

#### <a name="resolve-uac-issues"></a>UAC-problémák megoldása

1. Vonja ki a számítógépet. Lásd: [Eszközök eltávolítása](devices-wipe.md).

2. Várjon 20 percet az ügyfélszoftver eltávolításáig.

    > [!NOTE]
    > Ne próbálja meg eltávolítani az ügyfelet a Programok és szolgáltatások területről.

3. A start menüben írja be a **UAC** a felhasználói fiókok felügyelete beállításainak megnyitásához.

4. Az értesítési csúszkát az alapértelmezett beállítás.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>HIBA: Nem szerezhető be érték a számítógépről, 0x80041013

Ez akkor fordulhat elő, ha a helyi rendszeren lévő idő legalább öt perccel eltér a szinkronizált értéktől. Ha a helyi számítógépen lévő idő nincs szinkronban, a biztonságos tranzakciók sikertelen, mert az időbélyegek érvénytelenek.

A probléma megoldásához állítsa a helyi rendszeridő legközelebb az internetes időhöz. Vagy állítsa be az idő a tartományvezérlőkön a hálózaton.

## <a name="next-steps"></a>További lépések

Ha segítségre van szüksége bizonyos, [kérhet támogatást a Microsoft Intune](get-support.md).
