---
title: A vállalat által biztosított macOS-eszköz felügyeleti regisztrálása | Microsoft Docs
description: Azt mutatja be, hogyan regisztrálhat az Intune-ban egy, a cég által vásárolt és rendelkezésre bocsátott macOS-eszközt.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: a5808a0ac80390b76058827d2ca0870249b043b9
ms.sourcegitcommit: 11cad61c565c474a8d653181675cc1109d562626
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43241830"
---
# <a name="enroll-your-organization-provided-macos-device-in-management"></a>A vállalat által biztosított macOS-eszköz felügyeleti regisztrálása

Útmutató új macOS-eszköz Intune-felügyelet alá helyezéséhez.  

A munkahelye vagy iskolája által biztosított eszközöket gyakran előre konfigurálják, mielőtt Ön megkapja azokat. A vállalat akkor küldi az eszközre ezeket az előre konfigurált beállításokat, miután Ön először bekapcsolta azt, és bejelentkezett. Miután az eszköz elvégezte a beállításokat, Ön hozzáférhet munkahelyi vagy iskolai erőforrásaihoz. 

A felügyelet beállításának megkezdéséhez kapcsolja be az eszközt, majd jelentkezzen be a munkahelyi vagy iskolai fiókjával. A cikk a továbbiakban azokat a lépéseket és képernyőket ismerteti, amelyekkel a Beállítási asszisztensben találkozni fog.   

## <a name="what-is-apple-dep"></a>Mi az Apple DEP?
Lehetséges, hogy vállalata az úgynevezett *Apple Készülékregisztrációs programon* (DEP) keresztül vásárolta meg eszközeit. Az Apple DEP nagy mennyiségű iOS- vagy macOS-eszköz vásárlását teszi lehetővé a vállalatok számára. Ezt követően ezeket az eszközöket egy általuk preferált mobileszköz-felügyeleti szolgáltatóval, például az Intune-nal konfigurálják és felügyelik. Ha Ön rendszergazda, és információt szeretne az Apple DEP-vel kapcsolatban, tekintse át a [macOS-eszközök automatikus regisztrálása az Apple készülékregisztrációs programjával (DEP)](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos) című cikket.  

## <a name="set-up-your-macos-device"></a>A macOS-eszköz beállítása  
Az alábbi lépésekkel regisztrálhatja macOS-eszközét a felügyeleti szolgáltatásban. Ha nem a vállalat által biztosított, hanem saját eszközt használ, kövesse a [személyes és saját eszközökre](enroll-your-device-in-intune-macos-cp.md) vonatkozó lépéseket.  

1. Kapcsolja be a macOS-eszközt. 
2. Válasszon egy **nyelvet**, és kattintson a **Folytatás** gombra.  

   ![Képernyőkép egy macOS-eszköz Beállítási asszisztensének üdvözlőképernyőjéről, a nyelvválasztó listával.](./media/macos-dep-welcome-1808.png)   
3. Válasszon egy billentyűzetkiosztást. A lista a választott nyelvtől függően egy vagy több lehetőséget is felkínálhat. Nyelvtől függetlenül az összes lehetséges kiosztás megjelenítéséhez kattintson az **Összes megjelenítése** elemre. Ha végzett, kattintson a **Folytatás** gombra.  

   ![Képernyőkép egy macOS-eszköz Beállítási asszisztensének billentyűzetkiosztási képernyőjéről. Látható a választható nyelvek listája, egy bejelöletlen Összes megjelenítése lehetőség, illetve a Vissza és Folytatás gombok.](./media/macos-dep-keyboard-1808.png)  
4. Válassza ki a Wi-Fi-hálózatot. A beállítás folytatásához internetkapcsolat szükséges. Ha nem látja a saját hálózatát, vagy vezetékes hálózattal szeretne kapcsolódni, kattintson az **Egyéb hálózati beállítások** lehetőségre. Ha végzett, kattintson a **Folytatás** gombra.  

   ![Képernyőkép egy macOS-eszköz Beállítási asszisztensének Wi-Fi-hálózatot kiválasztó képernyőjéről, a választható hálózatok listájával. Az Egyéb hálózati beállítások, illetve a Vissza és a Folytatás gomb is látható.](./media/macos-dep-wifi-1808.png)  
5. Miután csatlakozott a Wi-Fi-hálózathoz, megjelenik a **Távoli felügyelet** képernyő. A távoli felügyelet lehetővé teszi, hogy a cég rendszergazdája távolról konfigurálja az eszközön a vállalat által előírt fiókokat, beállításokat, alkalmazásokat, hálózatokat. Mielőtt továbblépne, olvassa el a dokumentációban az eszköz felügyeletéről szóló részt. Ezután kattintson a **Folytatás** gombra.  

   ![Képernyőkép egy macOS-eszköz Beállítási asszisztensének távoli felügyeleti képernyőjéről. Látható a távoli felügyeletet ismertető szöveg, valamint egy hivatkozás, amely a további információkat tartalmazó dokumentációra mutat. A Vissza és a Folytatás gomb is látható.](./media/macos-dep-remote-management-1-1808.png)  
6. Ha az eszköz kéri, jelentkezzen be a munkahelyi vagy iskolai fiókjával. A hitelesítést követően az eszköz telepít egy felügyeleti profilt. Ez a profil konfigurálja és engedélyezi a hozzáférést a céges erőforrásokhoz.  
7. Olvassa el az Apple adatkezelést és adatvédelmet jelölő ikonjának ismertetését, hogy később meg tudja állapítani, mikor kerül sor személyes adatok gyűjtésére. Ezután kattintson a **Folytatás** gombra.  

   ![Képernyőkép egy macOS-eszköz Beállítási asszisztensének Adatkezelés és adatvédelem képernyőjéről. Látható egy illusztráció, rajta két kezet fogó alakkal, és annak az ismertetése, hogyan használja fel az Apple a személyes adatokat. A Vissza és a Folytatás gomb is látható.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Az eszköz regisztrálását követően előfordulhat, hogy további lépéseket is el kell végeznie. A megjelenő lépések attól függnek, hogy a cég hogyan szabta személyre a beállítási folyamatot. Az alábbi lépésekre lehet szükség:
    * Bejelentkezés egy Apple-fiókba
    * A használati feltételek elfogadása
    * Egy számítógépes fiók létrehozása
    * Egy gyorstelepítési folyamat elvégzése
    * A Mac gép beállítása  
## <a name="get-the-company-portal-app"></a>A Céges portál alkalmazás beszerzése      
Nyissa meg az App Store áruházat, és telepítse az eszközre a Céges portál alkalmazást. Ezzel az alkalmazással monitorozhatja, szinkronizálhatja, hozzáadhatja és eltávolíthatja az eszközt a felügyeletből, és további alkalmazásokat is telepíthet.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).
