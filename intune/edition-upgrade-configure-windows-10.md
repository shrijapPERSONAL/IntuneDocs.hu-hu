---
title: Frissítés vagy S mód használata a Windows 10-eszközök – Microsoft Intune – Azure |} A Microsoft Docs
description: Egy másik kiadásra a Windows 10-eszközök frissítése a Microsoft Intune használatával, vagy váltson S mód. A rendszergazdák eszközkonfigurációs profil használatával frissítse a Windows 10 Professional, Windows 10 Enterprise, és váltson S módból. A támogatott frissítési útvonalakat Windows 10 Pro, N kiadás, Education, Cloud, Enterprise, Core, Holographic és Mobile talál.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f4195a2c622b68feb21a15faf23d4cca3f95b48
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "60164124"
---
# <a name="upgrade-windows-10-editions-or-switch-out-of-s-mode-on-devices-using-microsoft-intune"></a>A Windows 10-kiadás frissítése, vagy váltson ki S mód eszközökön a Microsoft Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A mobileszköz-felügyelet (MDM) megoldás részeként, előfordulhat, hogy frissíteni szeretné a Windows 10 rendszerű eszközök. Ha például szeretné a Windows 10 Professional-eszközök frissítése a Windows 10 Enterprise. Másik lehetőségként azt szeretné, hogy az eszköz S módból váltani.

[A Windows 10 S mód](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) (megnyílik egy másik Microsoft-webhely) lett tervezve, biztonságot és teljesítményt. Az Intune segítségével S módból váltani. Az S módból való váltás nem vonható vissza. Ha vált az S módból, nem válthat vissza később.

Ismerkedjen meg néhány [gyakran ismételt kérdések](https://support.microsoft.com/help/4020089/windows-10-in-s-mode-faq) S módjával kapcsolatban.

Ez a funkció az alábbiakra vonatkozik:

- Windows 10 és újabb
- A Windows 10-es 1809 vagy újabb S mód
- Windows Holographic for Business

Ezek a funkciók érhetők el az Intune-ban, és a rendszergazda által konfigurálható. Az Intune használja a "profilok" hozhat létre, és ezeket a beállításokat a szervezet igényeinek megfelelően. Után ezeket a funkciókat ad hozzá egy profilt, amit leküldéses, vagy telepítse a profilt a Windows 10-eszközökre a szervezetben. A profil központi telepítése, az Intune automatikusan frissíti az eszközök vagy kapcsolók S módból.

Ez a cikk a támogatott frissítési útvonalakat sorolja fel, és bemutatja, hogyan hozhat létre az eszközkonfigurációs profilban. Emellett megtekintheti az összes elérhető frissítés és S mód beállításainak [Windows 10-es](edition-upgrade-windows-settings.md).

> [!NOTE]
> Ha eltávolítja a szabályzat-hozzárendelés később, a Windows az eszközön lévő verziója nem állítja vissza a rendszer. Az eszköz továbbra is normál módon futnak.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt frissítené az eszközt, lehet, hogy a következő előfeltételek vonatkoznak:

- Érvényes termékkulcs a frissített Windows-verzió telepítéséhez a szabályzat céljaként meghatározott eszközökön (Windows 10 asztali verziók esetén). Többször használható aktiválási kulcsokat (MAK) vagy kulcskezelő kiszolgálói (KMS) kulcsokat használhat.
- Windows 10 Mobile és Windows 10 Holographic esetén használhatja a Microsoft-licencfájl. A licencfájl történő telepítése a frissített edition minden eszközön, amelyet céljaként a szabályzatot a licencelési adatokat tartalmazza.
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

## <a name="create-the-profile"></a>A profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét. Például adja meg az alábbihoz hasonló `Windows 10 edition upgrade profile` vagy `Windows 10 switch off S mode`.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki a platformot:  

        - **Windows 10 és újabb**

    - **Profil típusa**: Válassza ki **kiadásfrissítés**.
    - **Beállítások**: Adja meg a konfigurálni kívánt beállításokat. Az összes beállítások listáját, és mit tesznek lásd:

        - [Windows 10-es frissítés és S mód](edition-upgrade-windows-settings.md)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. 

A profil létrehozásáról és jelennek meg a listában. Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

## <a name="next-steps"></a>További lépések

A profil létrehozását követően készen áll hozzá kell rendelni. Ezután [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).

A frissítés és S mód beállításainak megtekintése [Windows 10-es](edition-upgrade-windows-settings.md) és [Windows Holographic for Business](holographic-upgrade.md) eszközök.
