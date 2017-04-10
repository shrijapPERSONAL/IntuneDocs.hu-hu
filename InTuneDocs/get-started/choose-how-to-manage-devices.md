---
title: "Az eszközkezelés módjának kiválasztása | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: e13a9c426e07ebb2443bd403d1a5c7274afd387e
ms.openlocfilehash: dea0700e2901bfed566a87d7c599569219de85a2
ms.lasthandoff: 12/20/2016


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

Az egyes módszerekkel elérhető felügyeleti képességek részletes felsorolását lásd: [Mobileszköz-kezelési képességek](mobile-device-management-capabilities-in-microsoft-intune.md) és [Az Intune PC-szoftverügyfél képességei](windows-pc-management-capabilities-in-microsoft-intune.md).
Az Intune által támogatott eszközökről és számítógépekről lásd: [Támogatott mobileszközök és számítógépek](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune#intune-supported-devices).

## <a name="next-steps"></a>További lépések

- [A mobileszközök regisztrálásának módjai](/intune/get-started/choose-how-to-enroll-devices1)
- [Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)
- [Exchange ActiveSync mobileszköz-felügyelet a Microsoft Intune-nal](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).

