---
title: Windows-eszköz manuális szinkronizálása | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: aa556b2939986759aa92e63750fd161c05afbc38
ms.sourcegitcommit: 6a9830de768dd97a0e95b366fd5d2f93980cee05
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2018
ms.locfileid: "34048019"
---
# <a name="sync-your-windows-device-manually"></a>Windows-eszköz manuális szinkronizálása

Ha nem elég gyors az alkalmazástelepítés, kezdeményezzen manuális eszközszinkronizálást. A manuális szinkronizálással kényszerítheti az eszközt az Intune-hoz való csatlakozásra és a legújabb frissítések és kommunikáció letöltésére. Az eszközszinkronizálás után felgyorsulhat a telepítés.

Az Intune a Céges portál alkalmazásból és az eszköz Beállítások alkalmazásából támogatja a manuális szinkronizálást. 

A Céges portál alkalmazás csak a Windows 10 alkotói frissítését (1703) vagy újabb verziót futtató eszközökön érhető el. 
* [Szinkronizálás a Céges portál alkalmazásból](#Sync-from-Company-Portal-app-for-Windows)  

Minden Windows-eszköz szinkronizálható az eszköz Beállítások alkalmazásából, beleértve a következőket:

* [Windows 10 asztali verzió](#windows-10-desktop)  
* [Microsoft HoloLens](#microsoft-hololens)   
* [Windows 10 Mobile](#windows-10-mobile)  
* [Windows Phone 8.1](#windows-phone-81)    

## <a name="sync-from-company-portal-app-for-windows"></a>Szinkronizálás a Windows Céges portál alkalmazásból
Az alkotói frissítést (1703) vagy újabb verziót futtató Windows 10-es eszközök manuális szinkronizálásához kövesse az alábbi lépéseket.

1.  Nyissa meg az eszközén a Céges portál alkalmazást.

2.  Válassza a **Beállítások** > **Szinkronizálás** lehetőséget.

    ![Képernyőkép a Céges portál alkalmazásról, kiemelt Beállítások elemmel](./media/RS1_homePage_settings_04.png)  
    
    ![Képernyőkép a Céges portál beállítások lapjáról, kiemelt Szinkronizálás gombbal](./media/RS1_settingspage_sync05.png)    

## <a name="sync-from-settings-app"></a>Szinkronizálás a Beállítások alkalmazásból 
A Microsoft HoloLenses, Windows 10 asztali verziós, Windows 10 Mobile-os vagy Windows Phone 8.1-es eszközének a Beállítások alkalmazásból történő szinkronizálásához kövesse az alábbi lépéseket.

### <a name="windows-10-desktop"></a>Windows 10 asztali verzió
1. Az eszközön válassza a **Start** > **Beállítások** lehetőséget.

2. Válassza a **Fiókok** elemet.

    ![A Fiókok lehetőség kiválasztása a Beállítások lapon](./media/win10pc-sync-2-settings-accounts.png)  

3. A Windows 10 több asztali verzióval is rendelkezik. Hasonlítsa össze a képernyőjét a lenti képernyőképekkel, így megtudhatja, melyik útmutatást kell követnie. 

    * Ha a képernyőjén **Hozzáférés munkahelyi vagy iskolai rendszerhez** felirat látható, ugorjon a [Hozzáférés munkahelyi vagy iskolai rendszerhez](#access-work-or-school) szakaszhoz.

    ![A Hozzáférés munkahelyi vagy iskolai rendszerhez lehetőség a beállítások alkalmazásban](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

    * Ha a képernyőn a **Munkahelyi hozzáférés** felirat jelenik meg, ugorjon a [Munkahelyi hozzáférés](#work-access) szakaszhoz.  

    ![Munkahelyi hozzáférés kiválasztása a fiók típusaként](./media/win10pc-sync-3-work-access.png)

#### <a name="access-work-or-school-steps"></a>Hozzáférés munkahelyi vagy iskolai rendszerhez – lépések

1. Kattintson a **Hozzáférés munkahelyi vagy iskolai rendszerhez** elemre.

    ![Képernyőkép a Hozzáférés munkahelyi vagy iskolai rendszerhez lehetőségről](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

2. Válassza ki azt a fiókot, amely mellett egy aktatáska ikon látható. Ha nem lát ilyen fiókot, előfordulhat, hogy a cége másképp konfigurálta a beállításokat. Ebben az esetben kattintson arra a fiókra, amely mellett egy Microsoft-embléma látható.

     ![Válassza ki az aktatáska vagy a Microsoft emblémája melletti fiókot](./media/win10pc-rs1-sync-info-button.png)

3. Kattintson az **Információ** lehetőségre. 

4. Kattintson a **Szinkronizálás** elemre. 

#### <a name="work-access-steps"></a>Munkahelyi hozzáférés – lépések

1.  Kattintson a **Munkahelyi hozzáférés** elemre.

    ![Munkahelyi hozzáférés kiválasztása a fiók típusaként](./media/win10pc-sync-3-work-access.png)

2. A **Regisztrálás eszközfelügyeletre** részen válassza ki a cég nevét.

    ![A cég nevének kiválasztása az eszközfelügyelethez](./media/win10pc-sync-4-tap-com-name.png)

3. Kattintson a **Szinkronizálás** elemre. A gomb a szinkronizálás végéig le van tiltva.

    ![Kattintás a Szinkronizálás gombra](./media/win10pc-sync-5-tap-sync.png)  


### <a name="windows-10-mobile"></a>Windows 10 mobil verzió

   1. Az eszközön lépjen a **Minden alkalmazás** > **Beállítások** > **Fiókok** menüpontra.

       ![Fiókok kiválasztása a Beállítások képernyőn](./media/win10m-sync-1-settings-accounts.png)

   2. Válassza a **Munkahelyi hozzáférés** lehetőséget.

       ![Munkahelyi hozzáférés kiválasztása a fiók típusaként](./media/win10m-sync-2-work-access.png)

   3. A **Regisztrálás eszközfelügyeletre** területen válassza ki a cég nevét.

       ![A cég nevének kiválasztása az eszközfelügyelethez](./media/win10m-sync-3-tap-comp-name.png)

   4. Kattintson a **Szinkronizálás** ikonra. A gomb a szinkronizálás végéig le van tiltva.

       ![Kattintás a Szinkronizálás ikonra](./media/win10m-sync-4-tap-sync.png)  
### <a name="microsoft-hololens"></a>Microsoft HoloLens  
Ezek az utasítások a Windows 10 évforduló frissítés (más néven RS1-et) futtató HoloLens-eszközökre vonatkoznak. 
1.  Nyissa meg a Beállítások alkalmazást az eszközön.  

2.  Kattintson a **Fiókok** > **Munkahelyi hozzáférés** elemre.  
    ![Képernyőkép a HoloLens beállítások alkalmazásáról, kiemelt Fiókok hivatkozással](./media/RS1_holoLens_SettingsRS1_Accounts_06.png)  

3.  Válassza ki a csatlakoztatott fiókot, majd válassza a **Szinkronizálás** lehetőséget. ![Képernyőkép a HoloLens beállítások alkalmazásáról, kiemelt szinkronizálás gombbal](./media/RS1_holoLens_SyncRS1_Sync_08.png)  

### <a name="windows-phone-81"></a>Windows Phone 8.1

1. Lépjen a **Minden alkalmazás** > **Beállítások** > **Munkahely** menüpontra.

    ![Beállítások listája](./media/wp81-1-sync-settings-workplace.png)

2. Válassza ki a cég nevét.

    ![Cég nevének kiválasztása munkahelyi fiókhoz](./media/wp81-2-sync-tap-compname.png)

3. Kattintson a **Szinkronizálás** ikonra.

    ![Kattintás a Szinkronizálás ikonra](./media/wp81-3-sync-tap-sync-button.png)

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://portal.manage.microsoft.com#HelpDeskDialog).
