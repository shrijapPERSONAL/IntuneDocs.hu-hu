---
title: Közös endpoint protection üzenetek a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg a közös üzenetek és a lehetséges megoldást használ, és az endpoint protection és a Microsoft Intune-ban a Windows Defender hibáinak elhárítása.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4f749ab85d283ed9743d227476f8229dc1cf7c3
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402646"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Végpontvédelmi problémákkal és a lehetséges megoldások a Microsoft Intune-ban

Ez a cikk felsorolja és ismerteti a lehetséges okait és megoldásait bizonyos hibák és figyelmeztetések. Az információk használatával kapcsolatos problémák megoldásához, az endpoint protection használata esetén.

## <a name="windows-defender-error-codes"></a>A Windows Defender-hibakódok

Tekintse át az eseménynaplókat és a hibakódok [Windows Defender Víruskereső hibáinak elhárítása](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

## <a name="common-intune-errors-and-possible-resolutions"></a>Az Intune előforduló gyakori hibák és a lehetséges megoldások

#### <a name="endpoint-protection-engine-unavailable"></a>Az Endpoint Protection-motor nem érhető el

**Lehetséges ok**: Az Intune végpontvédelmi motorja sérült vagy törölték.

**A lehetséges megoldásokról**:

- Ha az endpoint protection sérült, vagy nem frissít, majd frissítse, vagy telepítse újra a programot.
- Azonnali frissítés kényszerítéséhez. Az endpoint protection ügyfélprogram (valószínűleg a tálcán), válasszon **frissítés**.
- A Vezérlőpult > programokat, válassza ki azokat **a Microsoft Intune Endpoint Protection-ügynök**. Az alkalmazás telepítésének eltávolításához.
- A következő frissítési szinkronizálás során a Microsoft Online Management frissítéskezelője észleli a hiányzó programot, és az ütemezés szerinti telepítési időpontban újratelepíti.

#### <a name="features-are-disabled"></a>Szolgáltatások le vannak tiltva.

Előfordulhat, hogy kap egy üzenetet, hogy néhány funkció le van-e tiltva. Ezeket az üzeneteket akkor fordulhat elő, ha az Intune endpoint protection vagy a Windows Defender konfigurációs profil segítségével a rendszergazda által le van tiltva. Vagy le van tiltva az eszközön a felhasználó által. Lehetséges üzenetek:

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**A lehetséges megoldásokról**: Ezek a funkciók engedélyezéséhez. Útmutatásért lásd:

- [Endpoint protection-beállítások hozzáadása](endpoint-protection-configure.md)
- [A Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus)
- [Végfelhasználók: Vállalati erőforrások eléréséhez a valós idejű védelem bekapcsolása](/intune-user-help/turn-on-defender-windows)

#### <a name="malware-definitions-out-of-date"></a>A kártevő-definíciók elavultak

Ez az állapot mutatja, ha az eszközön a kártevőszoftver-leírások elavultak legalább 14 napja. Az üzenet valószínűleg például, ha az eszköz nem kapcsolódik az internethez, vagy a kártevő-definíciók elavultak.

**A lehetséges megoldásokról**: Kártevőszoftver-leírások elavultak, frissítheti használatával [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus).

#### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Teljes vizsgálat késésben vagy Gyorsvizsgálat késésben

A teljes vizsgálat vagy Gyorsvizsgálat 14 napig nem befejeződött. Ez akkor fordulhat elő, ha az eszköz újraindul a teljes vizsgálat során.

**A lehetséges megoldásokról**: Ha a vizsgálat késésben, futtathat egy egyszeri vizsgálatot, vagy ismétlődő vizsgálatokat. Lásd: [Windows Defender víruskereső](device-restrictions-windows-10.md#windows-defender-antivirus).

#### <a name="another-endpoint-protection-application-running"></a>Egy másik végpontvédelmi alkalmazás fut

Egy másik végpontvédelmi alkalmazás fut, és az eszköz nem kifogástalan állapotú.

**A lehetséges megoldásokról**: Ha egy másik végpontvédelmi alkalmazás telepítve van, és az Intune érzékeli azt, az eszköz instabillá válhat.

## <a name="next-steps"></a>További lépések

Első [segítséget a Microsoft támogatási](get-support.md), vagy használja a [közösségi fórumokat is talál](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
