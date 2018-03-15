---
title: "Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt Android-eszközökhöz"
titlesuffix: Microsoft Intune
description: "A Microsoft Intune alkalmazáskonfigurációs szabályzataival beállításokat adhat meg a felhasználók által futtatott Android for Work-alkalmazásokhoz."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a448c33e8324492c68d509a12d5901f41ed4873a
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt Android-eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune alkalmazáskonfigurációs szabályzataival beállításokat adhat meg a felhasználók által futtatott Android for Work-alkalmazásokhoz. A házirendeket nem kell közvetlenül felhasználókhoz vagy eszközökhöz rendelni. Ehelyett a szabályzatot egy alkalmazáshoz kell társítani, majd az alkalmazást hozzárendelni a felhasználókhoz vagy eszközökhöz. A szabályzatbeállítások akkor használatosak, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

> [!Note]  
> Az alkalmazáskonfigurációt nem minden alkalmazás támogatja. Érdeklődjön az alkalmazás fejlesztőjénél, hogy az alkalmazás az alkalmazáskonfigurációs szabályzatok támogatásához készült-e.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza a **Mobilalkalmazások** panelt.
4. Válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget a **Felügyelet** csoportban, majd a **Hozzáadás** lehetőséget.
5. Adja meg a következő adatokat:
    - **Név**  
      Az Azure Portalon megjelenő profilnév.
    - **Leírás**  
      Az Azure Portalon megjelenő profilleírás.
    - **Eszközbeléptetés típusa**  
      Válasza a **Felügyelt eszközök** lehetőséget.
6. A **Platform** beállításban válassza az **Android for Work** lehetőséget.
7. Válassza a **Társított alkalmazás** lehetőséget azon alkalmazás kiválasztásához, amelyhez a konfigurációs szabályzatot definiálni szeretné. Válassza ki a listából azon Android for Work alkalmazásokat, amelyeket jóváhagyott az Intune-nal való szinkronizáláshoz.
8. Válassza a **Konfigurációs beállítások** lehetőséget. A konfigurációkat a következőkkel adhatja meg:
    - [A konfigurációtervező](#Use-the-configuration-designer)
    - [A JSON-szerkesztő](#Enter-the-JSON-editor)
9. Válassza az **OK**, majd a **Hozzáadás** gombot.

## <a name="use-the-configuration-designer"></a>A konfigurációtervező használata

A konfigurációtervezőt olyan eszközökön található alkalmazásokhoz használhatja, amelyek regisztrálva vannak vagy nincsenek regisztrálva az Intune-ban. A tervezővel konkrét konfigurációs kulcsokat és értékeket konfigurálhat. Az értékekhez az adattípust is meg kell adnia.

A konfiguráció minden kulcsához és értékéhez állítsa be az alábbiakat:

  - **Konfigurációs kulcs**  
     Az adott beállításkonfigurációhoz egyedi azonosítóként szolgáló kulcs.
  - **Érték típusa**  
    A konfigurációs érték adattípusa. A típus az alábbiak egyike: egész szám, valós szám, karakterlánc vagy logikai.
  - **Konfigurációs érték**  
    A konfiguráció értéke. 

## <a name="enter-the-json-editor"></a>A JSON-szerkesztő megnyitása

Az alkalmazások bizonyos konfigurációs beállításai (például a kötegtípussal rendelkezőkéi) a configuration designerrel nem állíthatók be. Ezekhez az értékekhez a JSON-szerkesztőt kell használnia. A beállítások megadása ezen alkalmazások számára az alkalmazás telepítésekor automatikusan történik.

1. A **Konfigurációs beállítások formátuma** beállításban válassza a **Belépés a JSON-szerkesztőbe** lehetőséget.
2. A szerkesztőben definiálhatja konfigurációs beállítások JSON-értékeit. Választhatja a **JSON-sablon letöltése** lehetőséget a mintafájl letöltéséhez, amelyet ezután konfigurálhat.
3. Válassza az **OK**, majd a **Hozzáadás** gombot.

Ekkor létrejön a szabályzat, és megjelenik a szabályzatok listáját tartalmazó panelen.

Amikor valamelyik eszközön sor kerül az alkalmazáskonfigurációs szabályzathoz rendelt alkalmazás futtatására, akkor a rendszer a szabályzatban szereplő beállításoknak megfelelően fogja futtatni azt.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Az engedélyek engedélyezési állapotának előzetes konfigurálása az alkalmazásokhoz

Az alkalmazások az Android-eszköz funkcióinak eléréséhez szükséges engedélyét is megadhatja előre. Alapértelmezés szerint az eszközengedélyeket (például a tartózkodási hely adataihoz vagy az eszköz kamerájához való hozzáférést) megkövetelő Android-alkalmazások felszólítják a felhasználókat az engedélyek elfogadására vagy elutasítására. Ha például egy alkalmazás az eszköz mikrofonját használja, a rendszer felszólítja a felhasználót, hogy adjon engedélyt az alkalmazásnak a mikrofon használatára.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza a **Mobilalkalmazások** lehetőséget.
3. A **Felügyelet** csoportban válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget, majd a **Hozzáadás** lehetőséget.
4. Adja meg a következő adatokat:
    - **Név**. Az Azure Portalon megjelenő profilnév.
    - **Leírás**. Az Azure Portalon megjelenő profilleírás.
    - **Eszközregisztráció típusa**. Válassza a **Felügyelt eszközök** lehetőséget.
    - **Platform**. Válassza az **Android for Work** lehetőséget.
5. Válassza a **Társított alkalmazás** lehetőséget azon alkalmazás kiválasztásához, amelyhez a konfigurációs szabályzatot definiálni szeretné. Válassza ki a listából azon Android for Work alkalmazásokat, amelyeket jóváhagyott az Intune-nal való szinkronizáláshoz.
6. Válassza az **Engedélyek** majd **Hozzáadás** lehetőséget.
7. Válasszon a rendelkezésre álló alkalmazásengedélyek listájából, és kattintson az **OK** gombra.
8. Válasszon beállítást az ehhez a szabályzathoz megadandó egyes engedélyekhez:
    - **Rákérdezés**. A felhasználó elfogadásra vagy elutasításra való felszólítása.
    - **Automatikus engedélyezés**. Automatikus jóváhagyás a felhasználó értesítése nélkül.
    - **Automatikus elutasítás**. Automatikus elutasítás a felhasználó értesítése nélkül.
9. Az alkalmazáskonfigurációs szabályzat hozzárendeléséhez jelölje ki a szabályzatot, és válassza a **Hozzárendelés**, majd a **Csoportok kiválasztása** lehetőséget.
10. Jelölje ki a hozzárendelendő felhasználói csoportokat, majd válassza a **Kijelölés** lehetőséget.
11. A szabályzat hozzárendeléséhez kattintson a **Mentés** gombra.

## <a name="next-steps"></a>További lépések

Ezt követően gondoskodhat az alkalmazás valamely csoporthoz történő [hozzárendeléséről](apps-deploy.md) és [figyeléséről](apps-monitor.md).

