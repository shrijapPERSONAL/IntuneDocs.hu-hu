---
title: "Intune-os konfigurációs szabályzatok használata az Android for Workhöz"
titleSuffix: Intune on Azure
description: "Ez a témakör azt ismerteti, hogyan lehet alkalmazáskonfigurációs szabályzatokkal konfigurációs adatokat szolgáltatni a futtatott Android for Work-alkalmazásoknak.”"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7486a62ed11b83f00414a74b2d816f6048826f73
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>A Microsoft Intune alkalmazáskonfigurációs szabályzatainak használata az Android for Workhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A Microsoft Intune alkalmazáskonfigurációs szabályzataival adhatja meg az olyan beállításokat, amelyek elérhetők, amikor a felhasználók Android for Work-alkalmazásokat futtatnak. Nem minden alkalmazás támogatja az alkalmazáskonfigurációt. Kérdezze meg az alkalmazás fejlesztőjétől, hogy az alkalmazás az alkalmazáskonfigurációs szabályzatok támogatásához készült-e.

Az alkalmazáskonfigurációs szabályzatok segítségével az alkalmazás futtatása előtt előre konfigurálhatja a felhasználók számára elérhető alkalmazásbeállításokat. Néhány Android-alkalmazás támogatja a felügyelt konfigurációk az Intune-konzolon a [configuration designer](#use-configuration-designer) használatával megadható beállításait. Az alkalmazások bizonyos konfigurációs beállításai (például a kötegtípussal rendelkezőkéi) a configuration designerrel nem állíthatók be.  Ezen értékekhez a [JSON-szerkesztőt](#use-json-editor) kell használnia.   A beállítások megadása ezen alkalmazások számára az alkalmazás telepítésekor automatikusan történik.

A házirendeket nem kell közvetlenül felhasználókhoz vagy eszközökhöz rendelni. Ehelyett a szabályzatot egy alkalmazáshoz kell társítani, majd az alkalmazást hozzárendelni a felhasználókhoz vagy eszközökhöz. A szabályzat-beállítások akkor használatosak, amikor egy alkalmazás keresi azokat (általában az első futtatáskor).

## <a name="use-configuration-designer"></a>A configuration designer használata

1. Az Intune-portálon válassza a **Mobilalkalmazások** lehetőséget. A **Felügyelet** csoportban válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget, majd kattintson a **Hozzáadás** gombra.
2. Adja meg a következő adatokat:
    - **Név** – Az Intune-konzolon megjelenítendő profilnév
    - **Leírás** – Az Intune-konzolon megjelenítendő profilleírás
    - **Platform** – Válassza az **Android** lehetőséget
    - **Eszközregisztráció típusa** -  Az **Intune-ban regisztrált** beállítás van előre kijelölve.
3. Válassza a **Társított alkalmazás** lehetőséget azon alkalmazás kiválasztásához, amelyhez a konfigurációs szabályzatot definiálni szeretné.  Válassza ki a listából azon Android for Work alkalmazásokat, amelyeket jóváhagyott az Intune-nal való szinkronizáláshoz
4. Válassza a **Konfigurációs beállítások** lehetőséget.
5. A **Konfigurációs beállítások formátuma** beállításban válassza **A configuration designer használata** lehetőséget.
6. Válassza a **Hozzáadás** lehetőséget. Ekkor megjelenik a rendelkezésre álló konfigurációs beállítások listája. A lista a következőket tartalmazza:
    - **Konfigurációs kulcsok** – A beállítás neve.
    - **Értéktípus** – A konfigurálható beállítás típusa, például **Logikai** vagy **Karakterlánc**.
    - **Leírás** – A konfigurációs beállítás leírását jeleníti meg.
7. Jelölje be a profillal konfigurálni kívánt beállításokhoz tartozó jelölőnégyzeteket, és kattintson az **OK** gombra.
8. Ekkor megjelenik a kiválasztott beállítások listája a rendelkezésre álló **konfigurációs értékkel** együtt. Adja meg minden egyes beállítások értékét, és kattintson az **OK** gombra.

## <a name="use-json-editor"></a>A JSON-szerkesztő használata

1. Az Intune-portálon válassza a **Mobilalkalmazások** lehetőséget. A **Felügyelet** csoportban válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget, majd kattintson a **Hozzáadás** gombra.
2. Adja meg a következő adatokat:
    - **Név** – Az Intune-konzolon megjelenítendő profilnév
    - **Leírás** – Az Intune-konzolon megjelenítendő profilleírás
    - **Platform** – Válassza az **Android** lehetőséget
    - **Eszközregisztráció típusa** -  Az **Intune-ban regisztrált** beállítás van előre kijelölve.
3. Válassza a **Társított alkalmazás** lehetőséget azon alkalmazás kiválasztásához, amelyhez a konfigurációs szabályzatot definiálni szeretné.  Válassza ki a listából azon Android for Work alkalmazásokat, amelyeket jóváhagyott az Intune-nal való szinkronizáláshoz.
5. Válassza a **Konfigurációs beállítások** lehetőséget.
6. A **Konfigurációs beállítások formátuma** beállításban válassza a **Belépés a JSON-szerkesztőbe** lehetőséget.
7. A szerkesztőben definiálhatja konfigurációs beállítások JSON-értékeit. Választhatja a **JSON-sablon letöltése** lehetőséget a mintafájl letöltéséhez, amelyet ezután konfigurálhat.
8. Amikor elkészült, kattintson az **OK** majd a **Hozzáadás** gombra.

Ekkor létrejön a szabályzat, és megjelenik a szabályzatok listáját tartalmazó panelen.



Amikor a kiosztott alkalmazást futtatják egy eszközön, az alkalmazáskonfigurációs szabályzatban megadott beállításokkal fog futni.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Engedélyek engedélyezési állapotának előzetes konfigurálása az alkalmazásokhoz

Az alkalmazások az Android-eszköz funkcióinak eléréséhez szükséges engedélyét is megadhatja előre. Alapértelmezés szerint az eszközengedélyeket (például hozzáférés a tartózkodási hely adataihoz vagy az eszköz kamerájához) megkövetelő androidos alkalmazások felszólítják a felhasználókat az engedélyek elfogadására vagy elutasítására. Például ha egy alkalmazás az eszköz mikrofonját használja, a rendszer felszólítja a végfelhasználót, hogy adjon engedélyt az alkalmazásnak a mikrofon használatára.

1. Az Intune-portálon válassza a **Mobilalkalmazások** lehetőséget. A **Felügyelet** csoportban válassza az **Alkalmazáskonfigurációs szabályzatok** lehetőséget, majd kattintson a **Hozzáadás** gombra.
2. Adja meg a következő adatokat:
    - **Név** – Az Intune-konzolon megjelenítendő profilnév
    - **Leírás** – Az Intune-konzolon megjelenítendő profilleírás
    - **Platform** – Válassza az **Android** lehetőséget
    - **Eszközregisztráció típusa** -  Az **Intune-ban regisztrált** beállítás van előre kijelölve.
3. Válassza a **Társított alkalmazás** lehetőséget azon alkalmazás kiválasztásához, amelyhez a konfigurációs szabályzatot definiálni szeretné.  Válassza ki a listából azon Android for Work alkalmazásokat, amelyeket jóváhagyott az Intune-nal való szinkronizáláshoz.
5. Válassza az **Engedélyek** majd **Hozzáadás** lehetőséget.
6. Válasszon a rendelkezésre álló alkalmazásengedélyek listájából, és kattintson az **OK** gombra.
7. Válasszon beállítást az ehhez a szabályzathoz megadandó egyes engedélyekhez:
    - **Rákérdezés** – A felhasználó elfogadásra vagy elutasításra való felszólítása.
    - **Automatikus engedélyezés** – Automatikus jóváhagyás a felhasználó értesítése nélkül.
    - **Automatikus elutasítás** – Automatikus elutasítás a felhasználó értesítése nélkül.
8. Az alkalmazáskonfigurációs szabályzat hozzárendeléséhez jelölje ki a szabályzatot, és válassza a **Hozzárendelés**, majd a **Csoportok kiválasztása** lehetőséget.
9. Jelölje ki a hozzárendelendő felhasználói csoportokat, majd válassza a **Kijelölés** lehetőséget.
10. A szabályzat hozzárendeléséhez kattintson a **Mentés** gombra.

## <a name="next-steps"></a>További lépések

Ezt követően a szokott módon gondoskodhat az alkalmazás valamely csoporthoz történő [hozzárendeléséről](apps-deploy.md) és [figyeléséről](apps-monitor.md).

