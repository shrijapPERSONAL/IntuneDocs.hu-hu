---
title: "Az eszközkezelés módjának kiválasztása"
description: "Ismerje meg az eszközök regisztrálására és kezelésére szolgáló különböző módszereket."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0dbe387ee6b8130e3dc64323f89b38e868087dfe
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-manage-devices"></a>Az eszközkezelés módjának kiválasztása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ahhoz, hogy kihasználhassa az Intune által kínált számos funkciót, így például az alkalmazástelepítést és az eszközbeállítások szabályozását, az eszközöket *kezelni* kell. Az eszközkezelés módja attól függ, hogy az Intune mely képességeit szeretné használni. Ez a témakör segít az igényeinek legmegfelelőbb módszer kiválasztásában.

iOS, Mac OS X, Android vagy Windows Phone rendszerű eszközök kezeléséhez az eszközöket *regisztrálni* kell.

Windows rendszerű számítógépek kezelésére két lehetősége van:

1. Az eszköz regisztrálása **vagy**
2. Az *Intune-szoftverügyfél* telepítése.

## <a name="decide-which-method-to-use"></a>A megfelelő módszer meghatározása
Az alábbi döntési folyamat segítségével döntheti el, hogyan kezelje eszközeit.

![Döntési folyamat az eszközök kezeléséhez.](./media/choose-manage-method.png)

A lehető legtöbb funkció eléréséhez regisztrálja a Windows rendszerű számítógépeket. Ugyanakkor előfordulhat, hogy az Intune-szoftverügyfél jobban megfelel az igényeinek a következő esetekben:

- Windows 7
- Windows-szoftverfrissítések és licenchasználat
- Endpoint Protection és a Windows tűzfal használata
- A TeamViewer szoftver segítségével távsegítséget kíván nyújtani a felhasználóknak

Az egyes módszerekkel elérhető felügyeleti képességek részletes felsorolását a következő cikkben találja: [Mobile device managem/intune/supported-devices-browserssoft-intune).
Az Intune által támogatott eszközökről és számítógépekről lásd: [Támogatott mobileszközök és számítógépek](/intune/supported-devices-browsers#intune-supported-devices).

## <a name="next-steps"></a>További lépések

- [A mobileszközök regisztrálásának módjai](/intune-classic/get-started/choose-how-to-enroll-devices1)
- [Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune)
- [Exchange ActiveSync mobileszköz-felügyelet a Microsoft Intune-nal](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).
