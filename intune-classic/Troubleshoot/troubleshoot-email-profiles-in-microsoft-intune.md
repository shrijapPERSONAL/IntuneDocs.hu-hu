---
title: "Az e-mail-profilok hibaelhárítása"
description: "Az e-mail-profilokkal kapcsolatos problémák, valamint az elhárításuk és megoldásuk ismertetése."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3f7daebb118f73bf5bbb5c331996d95f779cd8b5
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>E-mail profilok hibaelhárítása a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az alábbiakban néhány, az e-mail profilokkal kapcsolatos problémát ismertetünk, az elhárításukkal és a megoldásukkal együtt.

Ha ezekkel az információkkal nem tudja megoldani a problémát, a [Hogyan kérhet támogatást az Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben talál további részleteket a segítségkéréshez.


## <a name="unable-to-send-images-from--email-account"></a>Nem sikerül képeket küldeni az e-mail fiókból
Az automatikusan konfigurált e-mail fiókkal rendelkező felhasználók nem tudnak képeket küldeni az eszközeikről.
Ez akkor fordul elő, ha a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** beállítás nincs engedélyezve.

### <a name="intune-solution"></a>Intune-megoldás

1.  Nyissa meg a Microsoft Intune felügyeleti konzolját, és válassza a **Házirend** &gt; **Konfigurációs szabályzat** lehetőséget.

2.  Válassza ki a kívánt e-mail-profilt, majd válassza a **Szerkesztés** lehetőséget.

3.  Válassza ki a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** beállítást.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Intune-megoldással integrált Configuration Manager

1.  Nyissa meg a Configuration Manager-konzol &gt; **Eszközök és megfelelőség** elemét.

2.  Bontsa ki az **Áttekintés** -&gt; **Megfelelőségi beállítások** -&gt; **Hozzáférés a vállalati erőforrásokhoz** csomópontot, és válassza az **E-mail profilok** lehetőséget.

3.  Kattintson a jobb gombbal az e-mail-profilra, és nyissa meg a **Tulajdonságok** menüt.

4.  A **Szinkronizációs beállítások** lapon válassza a **Harmadik felek alkalmazásaiból is engedélyezett az e-mailek küldése** lehetőséget.


## <a name="device-already-has-an-email-profile-installed"></a>Az eszköz már rendelkezik telepített e-mail profillal

Ha a felhasználó azelőtt telepített egy e-mail profilt, hogy az Intune létesített volna egyet, akkor az Intune e-mail profil telepítésének eredménye az eszköz platformjától függ:

-**iOS:** az Intune az állomásnév és az e-mail cím alapján észleli a meglévő, duplikált e-mail-profilt. A felhasználó által létrehozott, duplikált e-mail profil meggátolja az Intune-rendszergazda által létrehozott profil telepítését. Ez gyakori probléma, mivel az iOS-felhasználók gyakran hoznak létre egy e-mail-profilt a regisztráció előtt. A vállalati portál tájékoztatja a felhasználót, hogy a manuálisan beállított e-mail-profil sérti a megfelelőségi házirendet, és megkéri, hogy távolítsa el a profilt. A felhasználónak ekkor törölnie kell az e-mail-profilt, hogy az Intune-profilt telepíthesse. A probléma elkerülése érdekében kérje meg a felhasználókat, hogy az e-mail profil telepítése előtt regisztráljanak, és engedélyezzék az Intune-nak, hogy telepítse a profilt.

-**Windows:** az Intune az állomásnév és az e-mail cím alapján észleli a meglévő, duplikált e-mail-profilt. Az Intune felülírja a felhasználó által létrehozott meglévő e-mail profilt.

-**Samsung KNOX Standard**: Az Intune az e-mail cím alapján azonosítja a duplikált e-mail-fiókot, és felülírja az Intune-profillal. Ha a felhasználó azt a fiókot állítja be, az Intune-profil ismételten felülírja. Ez összezavarhatja azt a felhasználót, akinek a fiókbeállítása felülíródik.

Mivel a Samsung KNOX nem használja az állomásnevet a profil azonosításához, azt javasoljuk, hogy ne hozzon létre több e-mail profilt azért, hogy ugyanahhoz az e-mail címhez telepítse őket a különböző gazdagépeken, mivel ezek felülírják egymást.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>KNOX Standard-eszköz 0x87D1FDE8-as hibája
**Probléma:** Miután létrehozott és telepített egy Exchange Active Sync e-mail-profilt különféle Samsung KNOX Standard rendszerű androidos eszközökhöz, az eszköz tulajdonságok &gt; szabályzat lapján a **0x87D1FDE8**-as vagy a **sikertelen szervizelés** hiba jelenik meg.

Ellenőrizze a Samsung KNOX EAS-profil és a forrásszabályzat konfigurációját. A Samsung Note eszközök szinkronizálási lehetősége a továbbiakban nem támogatott, és ez a lehetőség nem választható a profilban. Ellenőrizze, hogy az eszközök rendelkezésére állt-e elegendő idő (akár 24 óra) a szabályzat feldolgozásához.

## <a name="next-steps"></a>További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.
