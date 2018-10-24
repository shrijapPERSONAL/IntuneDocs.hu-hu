---
title: Microsoft Intune-dokumentáció
titlesuffix: ''
description: A Microsoft Intune dokumentációs útmutatójának megtekintése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/12/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 12d5d1f5-8452-4270-9975-f3a98e0eb746
ms.suite: ems
ms.custom: get-started
ms.openlocfilehash: 5bd37dbe6a24916bf3637999bd914c2e231c086e
ms.sourcegitcommit: cd73ef164e0df79429b97c3090adbba49592c150
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448712"
---
# <a name="microsoft-intune-documentation-guide"></a>A Microsoft Intune-dokumentáció útmutatója

Ezt a témát a Microsoft Intune teljes dokumentációjához hasonlóan folyamatosan frissítjük. Ha bármilyen javaslata van, a témakör végén írhatja meg a visszajelzéseit. Véleménye sokat jelent számunkra.

A dokumentáció a szükséges információk könnyebb megtalálhatósága érdekében a Microsoft Intune (alább látható) Azure Portalbeli elrendezését tükrözi.

![Az Azure Portal munkafolyamatai](./media/azure-portal-workloads.png)

Az alábbi táblázatban gyorsan megtalálhatja a Microsoft Intune használatához szükséges főbb információkat.

| Szakasz                                                      | Leírás                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Bevezetés és az első lépések](introduction-intune.md)       | Az Intune alapjai, többek között:<br /> – Gyakran használt megoldások<br /> – Hogyan működik a Microsoft Intune<br /> – Eszközkezelés az Intune-ban<br /> – Alkalmazáskezelés az Intune-ban<br /> – Nagyvállalati mobilitási felügyelet (EMM) eszközregisztrálással és anélkül                                                         |
| [Tervezés és kialakítás](planning-guide.md)                         | Útmutató a Microsoft Intune-környezet megtervezéséhez és kialakításához.                                                                                                                                                                                                             |
| [Eszközök regisztrálása](device-enrollment.md)                    | Azt ismerteti, hogyan segít a Microsoft Intune a munkahelyi eszközök felügyeletében az eszközök Intune-ban való regisztrálásával. A dolgozók eszközeit többféleképpen is lehet regisztrálni.                                                                                                         |
| [Eszközmegfelelőség](device-compliance.md)                    | Az eszközöknek az Intune eszközmegfelelőségi szabályzatai által meghatározott szabályok és beállítások szerint kell működnie, hogy a Microsoft Intune megfelelőnek tekintse azokat. Megfelelőségre példa lehet többek között az, ha az eszközhöz való hozzáféréshez jelszót követel meg, ha titkosítja az eszközt, vagy ha az operációs rendszer egy adott minimális verziószámát írja elő. |
| [Eszközök konfigurálása](device-profiles.md)                   | A Microsoft Intune-nal eszközprofilok létrehozásával konfigurálhatja az összes felügyelt eszközre vonatkozó beállításokat és funkciókat. Beállíthatja például az értesítéseket, az adatmegosztást, az e-mailes támogatást, a Wi-Fi-kapcsolatot, a tanúsítványokat vagy a végpontok védelmét.              |
| [Eszközök](device-management.md)                              | Biztosítani szükséges, hogy a felügyelt eszközök rendelkezzenek minden olyan erőforrással, amelyekre a felhasználóknak a munkavégzéshez szükségük lehet, miközben a céges adatokat is védeni kell a kockázatoktól. Az eszközöket a munkahelyi eszközleltár ellenőrzésével felügyelheti, és távoli eszközműveleteket is végrehajthat.                                                      |
| [Mobilalkalmazások](app-management.md)                             | Információ az alkalmazások hozzáadásáról, üzembe helyezéséről, figyeléséről, konfigurálásáról és védelméről.                                                                                                                                                                                                                             |
| [Feltételes hozzáférés](conditional-access.md)                  | A céges adatok védelmét szolgáló eszközalapú és alkalmazásalapú feltételeket határozhat meg.                                                                                                                                                                                                            |
| [Felhasználók](users-add.md)                                        | Információ arról, hogyan adhat hozzá felhasználókat a felügyelt eszközökhöz és alkalmazásokhoz.                                                                                                                                                                                                                                           |
| [Csoportok](groups-get-started.md)                              | Információ arról, hogyan hozhatók létre és hogyan kezelhetők csoportok az Intune-ban. A csoportok használatával gyorsan hozzárendelhet eszköz- és alkalmazáskonfigurációs védelmi szabályzatokat.                                                                                                                                             |
| [Intune-szerepkörök](role-based-access-control.md)                 | Szabályozhatja, hogy kik hajthatnak végre különböző műveleteket az Intune-ban, és hogyan lesznek alkalmazva ezek a műveletek. A beépített szerepköröket bizonyos gyakori Intune-os helyzetekben használhatja, de saját szerepköröket is létrehozhat.                                                                                 |
| [Szoftverfrissítések](windows-update-for-business-configure.md) | Információ arról, hogyan konfigurálhatja a szoftverfrissítéseket Windows 10-es eszközök esetén.                                                                                                                                                                                                                                  |

## <a name="next-steps"></a>További lépések

- Az Intune alapjainak elsajátításáról lásd: [Bevezetés és az első lépések](introduction-intune.md).
