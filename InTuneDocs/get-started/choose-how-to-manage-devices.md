---
title: "Az eszközkezelés módjának kiválasztása | Microsoft Intune"
description: "Ismerje meg az eszközök regisztrálására és kezelésére szolgáló különböző módszereket."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: b97ee1e99778c2a39e92061dd5aa051ecdf35caa


---

# <a name="choose-how-to-manage-devices"></a>Az eszközkezelés módjának kiválasztása

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
Az Intune által támogatott eszközökről és számítógépekről lásd: [Támogatott mobileszközök és számítógépek](/intune/get-started/supported-mobile-devices-and-computers).

## <a name="next-steps"></a>További lépések

- [A mobileszközök regisztrálásának módjai](/intune/get-started/choose-how-to-enroll-devices1)
- [Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)
- [Exchange ActiveSync mobileszköz-felügyelet a Microsoft Intune-nal](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



<!--HONumber=Dec16_HO2-->


