---
title: "Windows 10 rendszerű eszközök frissítése az Azure-beli Microsoft Intune-nal | Microsoft Docs"
description: "Eszközprofilt hozhat létre a Microsoft Intune-ban a Windows 10 rendszerű eszközök új verziókra történő frissítéséhez. Tekintse meg a Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic és Mobile kiadások támogatott frissítési útvonalait is."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8084f1b2fbd513de596bd97f4ffec995b6f7aac4
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="configure-windows-10-edition-upgrade-profile-in-intune"></a>A Windows 10-kiadás frissítési profiljának konfigurálása az Intune-ban
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Frissítési profilt konfigurálhat az Intune-ban a Windows 10-kiadást futtató eszközök más kiadásra történő frissítéséhez. Tekintse meg a támogatott frissítési útvonalakat is.

## <a name="before-you-begin"></a>Előkészületek
Mielőtt a legújabb verzióra frissítené az eszközt, az alábbiak egyikére lesz szüksége:

- Érvényes termékkulcs a frissített Windows-verzió telepítéséhez a szabályzat céljaként meghatározott eszközökön (Windows 10 asztali verziók esetén). A Többszörös aktiválási kulcsok (MAK), a Kulcskezelési kiszolgálói (KMS) kulcsok, vagy egy, a licencelési adatokat tartalmazó Microsoft-licencfájl segítségével telepítheti a Windows frissített verzióját minden eszközön, amelyet a szabályzat céljaként határozott meg (Windows 10 mobilverzió és Windows 10 Holographic esetén).
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

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Eszközkorlátozási beállításokat tartalmazó eszközprofil létrehozása
1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a  **Microsoft Intune** elemet.
3. Válassza az **Eszközkonfiguráció** lehetőséget, kattintson a **Profilok** elemre, majd válassza a **Profil létrehozása** lehetőséget.
4. Adja meg a kiadásfrissítési profil nevét és leírását a **Név** és **Leírás** mezőben.
5. A **Platform** legördülő listából válassza a **Windows 10 és újabb** lehetőséget.
6. A **Profil típusa** legördülő listából válassza az **Kiadásfrissítés** lehetőséget.
7. A **Kiadásfrissítés** tulajdonságai területen adja meg a következő beállításokat:
  - **Frissítés erre a kiadásra** – A legördülő listából válassza ki a Windows 10 asztali verzió, a Windows 10 Holographic, vagy a Windows 10 Mobile rendszernek azt a verzióját, amelyre a megcélzott eszközöket frissíteni szeretné.
  - **Termékkulcs** – Adja meg azt a Microsofttól beszerzett termékkulcsot, amely minden megcélzott, a Windows 10 asztali verzióját futtató eszköz frissítéséhez használható. 
    Miután létrehozta a termékkulcsot tartalmazó szabályzatot, a termékkulcsot nem lehet többé frissíteni, és biztonsági okokból rejtve marad. A termékkulcs módosításához a teljes kulcsot újra meg kell adnia.
  - **Licencfájl** – a Microsofttól kapott licencfájl kiválasztásához válassza a **Böngészés** lehetőséget. A licencfájl arról a Windows Holographic vagy Windows 10 Mobile kiadásról tartalmaz licencinformációkat, amelyre a megcélzott eszközöket frissíteni kívánja.
8. Ha elkészült, a változások mentéséhez kattintson a **Létrehozás** elemre.

Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="next-steps"></a>További lépések

Ha csoportokhoz kívánja hozzárendelni a profilt, tekintse meg az [Eszközprofilok hozzárendelése](device-profile-assign.md) című témakört.

>[!NOTE]
>Ha később eltávolítja a szabályzat-hozzárendelést, az eszközön futó Windows-verzió nem áll vissza, és továbbra is megfelelően működik.