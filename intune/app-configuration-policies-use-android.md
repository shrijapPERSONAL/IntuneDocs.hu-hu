---
title: Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt Android-eszközökhöz
titlesuffix: Microsoft Intune
description: A Microsoft Intune alkalmazáskonfigurációs szabályzataival beállításokat adhat meg a felhasználók által futtatott, androidos munkahelyi profilt használó alkalmazásokhoz.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ee53dd02fa008a2e885b789439e88c766205d13
ms.sourcegitcommit: 0a2e737c5520c1a1dec5d732e5df52b5614b27e1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268872"
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Alkalmazáskonfigurációs szabályzatok hozzáadása felügyelt Android-eszközökhöz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Alkalmazáskonfigurációs szabályzatok használata a Microsoft Intune-ban az androidos munkahelyi profilt használó alkalmazások beállításainak megadásához. Az alkalmazásfejlesztőnek közzé kell tennie az Androidos kezelt alkalmazás konfigurációs beállításait az alkalmazás konfigurációs beállításainak megadásához. Rendelje hozzá az alkalmazáskonfigurációs szabályzatot ahhoz a felhasználói csoporthoz, amelyre alkalmazni szeretné a beállításokat.  A szabályzatbeállítások akkor használatosak, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

> [!Note]  
> Az alkalmazáskonfigurációt nem minden alkalmazás támogatja. Érdeklődjön az alkalmazás fejlesztőjénél, hogy az alkalmazás az alkalmazáskonfigurációs szabályzatok támogatásához készült-e.

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza a **Mobilalkalmazások** panelt.
4. Válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget a **Felügyelet** csoportban, majd a **Hozzáadás** lehetőséget.
5. Adja meg a következő adatokat:
    - **Név** – Az Azure Portalon megjelenítendő profilnév.
    - **Leírás** – Az Azure Portalon megjelenítendő profilleírás.
    - **Eszközregisztráció típusa** – Válassza a **Felügyelt eszközök** lehetőséget.
6. A **Platform** beállításban válassza az **Android** lehetőséget.
7. Válassza a **Társított alkalmazás** lehetőséget azon alkalmazás kiválasztásához, amelyhez a konfigurációs szabályzatot definiálni szeretné. Válassza ki a listából azokat az androidos munkahelyi profilt használó alkalmazásokat, amelyeket jóváhagyott és szinkronizált az Intune-nal.
8. Válassza az **Engedélyek** lehetőséget. A konfigurációkat a következőkkel adhatja meg:
    - [A konfigurációtervező](#Use-the-configuration-designer)
    - [A JSON-szerkesztő](#Enter-the-JSON-editor)
9. Válassza az **OK**, majd a **Hozzáadás** gombot.

## <a name="use-the-configuration-designer"></a>A konfigurációtervező használata

A konfigurációtervezőt a konfigurációkat támogató Android-alkalmazásokhoz használhatja. A konfiguráció az Intune-ban regisztrált eszközökre fog vonatkozni. A tervezővel konkrét konfigurációs értékeket adhat meg az alkalmazás által közzétett beállításokhoz.

Az alkalmazáshoz megadni kívánt konfigurációs beállítások kiválasztásához válassza a **Hozzáadás** lehetőséget.  
A konfiguráció minden kulcsához és értékéhez állítsa be az alábbiakat:

  - **Érték típusa**  
    A konfigurációs érték adattípusa. Sztring értéktípusok esetében igény szerint megadhat egy változót vagy tanúsítványprofilt értéktípusnak.
  - **Konfigurációs érték**  
    A konfiguráció értéke. Ha értéktípusnak egy változót vagy tanúsítványt ad meg, a konfigurációs érték legördülő menüjében változók és tanúsítványprofilok közül választhat.  Ha egy tanúsítványt választ, az eszközre alkalmazott tanúsítványalias a futásidő során lesz feltöltve.
    
### <a name="supported-variables-for-configuration-values"></a>A konfigurációs értékek támogatott változói

Ha változót szeretne megadni értéktípusnak, az alábbi lehetőségek közül választhat:
- Egyszerű felhasználónév, például **John@contoso.com**
- E-mail, például **John@contoso.com**
- Részleges egyszerű felhasználónév, például **János**
- Fiókazonosító, például **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- Eszközazonosító, például **b9841cd9-9843-405f-be28-b2265c59ef97**
- Felhasználóazonosító, például **3ec2c00f-b125-4519-acf0-302ac3761822**
- Felhasználónév, például **Szabó János**


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
    - **Platform**. Válassza az **Android** lehetőséget.
5. Válassza a **Társított alkalmazás** lehetőséget azon alkalmazás kiválasztásához, amelyhez a konfigurációs szabályzatot definiálni szeretné. Válassza ki a listából azokat az androidos munkahelyi profilt használó alkalmazásokat, amelyeket jóváhagyott és szinkronizált az Intune-nal.
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

