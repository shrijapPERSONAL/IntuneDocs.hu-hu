---
title: Windows 10 rendszerű eszközök frissítése vagy az S mód használata az Azure-beli Microsoft Intune-nal | Microsoft Docs
description: Eszközprofilt hozhat létre a Microsoft Intune-ban a Windows 10 rendszerű eszközök más kiadásokra történő frissítéséhez. Például a Windows 10 Professionalről a Windows 10 Enterprise-ra frissíthet. Emellett engedélyezheti vagy kikapcsolhatja az S módot egy eszközön a konfigurációs profillal. Tekintse meg a Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic és Mobile kiadások támogatott frissítési útvonalait is.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f0e4ba42559a068ebefb453aba18060803dc36e0
ms.sourcegitcommit: f3974c810e172f345853dacd7f2ca0abc11b1a5b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44389625"
---
# <a name="use-a-configuration-profile-to-upgrade-windows-10-or-switch-from-s-mode-in-intune"></a>Frissítés Windows 10-re vagy váltás az S módról az Intune-ban a konfigurációs profillal
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Frissítési profilt konfigurálhat az Intune-ban a Windows 10-kiadást futtató eszközök más kiadásra történő frissítéséhez. Tekintse meg a támogatott frissítési útvonalakat is.

## <a name="before-you-begin"></a>Előkészületek
Mielőtt a legújabb verzióra frissítené az eszközt, az alábbiakra lesz szüksége:

- Érvényes termékkulcs a frissített Windows-verzió telepítéséhez a szabályzat céljaként meghatározott eszközökön (Windows 10 asztali verziók esetén). Többször használható aktiválási kulcsokat (MAK) vagy kulcskezelő kiszolgálói (KMS) kulcsokat használhat. Windows 10 Mobile és Windows 10 Holographic kiadások esetén használhat egy Microsoft-licencfájlt, amely a Windows frissített verziójának – a szabályzat céljaként meghatározott összes eszközön történő – telepítéséhez szükséges licencelési adatokat tartalmazza.
- Már regisztrálva vannak a Microsoft Intune-ban azok a Windows 10 rendszerű eszközök, amelyekhez hozzárendeli a szabályzatot. A kiadásfrissítési szabályzat nem használható az Intune PC-ügyfélszoftvert futtató számítógépekkel.

## <a name="supported-upgrade-paths"></a>Támogatott frissítési útvonalak
A Windows 10-kiadás frissítési profiljának támogatott frissítési útvonalai az alábbi táblázatban tekinthetők meg.

| Frissítés erről a kiadásról | Frissítés erre a kiadásra |
|---|---|
| Windows 10 Pro | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Windows 10 Pro N kiadás | Windows 10 Education N kiadás <br/>Windows 10 Enterprise N kiadás <br/>Windows 10 Pro Education N kiadás | 
| Windows 10 Pro Education | Windows 10 Education | 
| Windows 10 Pro Education N kiadás | Windows 10 Education N kiadás |
| Windows 10 Cloud | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Windows 10 Cloud N kiadás | Windows 10 Education N kiadás <br/>Windows 10 Enterprise N kiadás <br/>Windows 10 Pro N kiadás <br/>Windows 10 Pro Education N kiadás | 
| Windows 10 Enterprise | Windows 10 Education | 
| Windows 10 Enterprise N kiadás | Windows 10 Education N kiadás | 
| Windows 10 Core | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Windows 10 Core N kiadás | Windows 10 Education N kiadás <br/>Windows 10 Enterprise N kiadás <br/>Windows 10 Pro Education N kiadás | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 mobil verzió | Windows 10 Mobile Enterprise |


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="upgrade-the-edition"></a>Kiadás frissítése

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adjon meg egy **nevet** és egy **leírást** a profil számára. Például: `Windows 10 edition upgrade`
4. A **Platform** beállításnál válassza a **Windows 10 és újabb** lehetőséget.
5. A **Profiltípus** területen válassza a **Kiadásfrissítés** elemet.
6. A **Kiadásfrissítés** tulajdonságai területen adja meg a következő beállításokat:

   - **Frissítés erre a kiadásra**: Válassza ki a Windows 10 azon kiadását, amelyre frissíteni kíván. A szabályzat hatókörébe tartozó eszközök ekkor frissülnek a választott kiadásra.
   - **Termékkulcs**: Adja meg a Microsofttól kapott termékkulcsot. Miután létrehozta a termékkulcsot tartalmazó szabályzatot, a termékkulcsot nem lehet többé frissíteni, és biztonsági okokból rejtve marad. A termékkulcs módosításához a teljes kulcsot újra meg kell adnia.
   - **Licencfájl**: **Windows 10 Holographic for Business** vagy **Windows 10 Mobile** esetén a Microsofttól kapott licencfájl kiválasztásához válassza a **Tallózás** lehetőséget. A licencfájl tartalmazza azon kiadások licencadatait, amelyekre frissíteni szeretne.

7. A módosítások mentéséhez válassza az **OK** gombot. Válassza a **Létrehozás** lehetőséget a profil létrehozásához.

## <a name="switch-out-of-s-mode"></a>Váltás S módból

[A Windows 10 S módot](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) biztonságra és teljesítményre terveztük. Ha az eszközei csak a Microsoft Store áruházból származó alkalmazásokat futtatnak, az S móddal biztonságban tarthatja az eszközeit. Ha az eszközeinek olyan alkalmazásokra van szüksége, amelyek nem érhetők el a Microsoft Store áruházban, váltson ki az S módból. Az S módból való váltás nem vonható vissza. Ha vált az S módból, nem válthat vissza később.

A következő lépések bemutatják, hogyan hozhat lére egy S módot vezérlő profilt Windows 10-es (1809 vagy újabb) eszközökön.

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adjon meg egy **nevet** és egy **leírást** a profil számára. Például: `Windows 10 switch off S mode`
4. A **Platform** beállításnál válassza a **Windows 10 és újabb** lehetőséget.
5. A **Profiltípus** területen válassza a **Kiadásfrissítés** elemet.
6. Válassza a **Módváltás (csak Windows Insider)** lehetőséget, és adja meg a **Váltás S módból** tulajdonságot. A választható lehetőségek:

    - **Nincs konfiguráció**: A S módban lévő eszköz S módban marad. A végfelhasználók válthatnak S módból.
    - **S módban tartás**: Letiltja az S módból való váltást a végfelhasználók számára.
    - **Váltás**: Kiváltja az eszközt az S módból.

7. A módosítások mentéséhez válassza az **OK** gombot. Válassza a **Létrehozás** lehetőséget a profil létrehozásához.

Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md) a csoportokhoz.

>[!NOTE]
>Ha később eltávolítja a szabályzat-hozzárendelést, az eszközön futó Windows-verzió nem áll vissza, és továbbra is megfelelően működik.
