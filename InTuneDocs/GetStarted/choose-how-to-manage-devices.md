---
title: "Az eszközkezelés módjának kiválasztása | Microsoft Intune"
description: "Ismerje meg az eszközök regisztrálására és kezelésére szolgáló különböző módszereket."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 7b5cadfbc759b025fdad995e34040762b15e0d30


---

# <a name="choose-how-to-manage-devices"></a>Az eszközkezelés módjának kiválasztása

Ahhoz, hogy kihasználhassa az Intune által kínált számos funkciót, így például az alkalmazástelepítést és az eszközbeállítások szabályozását, az eszközöket *kezelni* kell. Az eszközkezelés módja attól függ, hogy az Intune mely képességeit szeretné használni.
A jelen témakör segít kiválasztani az igényeinek megfelelő módszert.

iOS, Mac OS X, Android vagy Windows Phone rendszerű eszközök kezeléséhez az eszközöket *regisztrálni* kell.

Windows rendszerű számítógépek kezelésére két lehetősége van:

1. Az eszköz regisztrálása **vagy**
2. Az *Intune-szoftverügyfél* telepítése.

## <a name="decide-which-method-to-use"></a>A megfelelő módszer meghatározása
Az alábbi döntési folyamat segítségével döntheti el, hogyan kezelje eszközeit.

![Döntési folyamat az eszközök kezeléséhez.](./media/choose-manage-method.png)

A lehető legtöbb funkció eléréséhez regisztrálja a Windows rendszerű számítógépeket. Ugyanakkor előfordulhat, hogy az Intune-szoftverügyfél jobban megfelel az igényeinek a következő esetekben:

- A számítógépen Windows 7 fut
- Felügyelni kívánja a Windows-szoftverfrissítéseket és a licenchasználatot
- Az Endpoint Protection és a Windows tűzfal segítségével kívánja kezelni a kártevőket
- A TeamViewer szoftver segítségével távsegítséget kíván nyújtani a felhasználóknak


Az egyes módszerekkel elérhető felügyeleti képességek részletes felsorolását lásd: [Mobileszköz-kezelési képességek](mobile-device-management-capabilities-in-microsoft-intune.md) és [Az Intune PC-szoftverügyfél képességei](windows-pc-management-capabilities-in-microsoft-intune.md).
Az Intune által támogatott eszközökről és számítógépekről lásd: [Támogatott mobileszközök és számítógépek](/intune/get-started/supported-mobile-devices-and-computers)


## <a name="exchange-activesync-management"></a>Felügyelet az Exchange ActiveSync segítségével
Az eszköz regisztrációja vagy az Intune-szoftverügyfél telepítése mellett az [Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) segítségével is felügyelheti az eszközöket. Ehhez telepítenie kell az On-Premises Connector összekötőt, vagy a beépített Service-to-Service Connector összekötővel kell kapcsolódnia az Exchange Serverhez.
Bár ezen harmadik módszerrel is lehetséges az eszközök felügyelete, a másik két módszerhez képest ez korlátozott mennyiségű felügyeleti képességet biztosít.


## <a name="next-steps"></a>További lépések

- [A mobileszközök regisztrálásának módjai](/intune/get-started/choose-how-to-enroll-devices1)
- [Windows rendszerű számítógépek felügyelete az Intune számítógépügyféllel](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)



- [Exchange ActiveSync mobileszköz-felügyelet a Microsoft Intune-nal](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).




<!--HONumber=Nov16_HO1-->


