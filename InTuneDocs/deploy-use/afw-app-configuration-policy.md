---
title: "Az Android for Work alkalmazáskonfigurációs szabályzata | Microsoft Docs"
description: "Az Intune-ban a mobilalkalmazások konfigurációs szabályzataival adhatja meg az olyan beállításokat, amelyekre szükség lehet, amikor a felhasználók Android for Work-alkalmazásokat futtatnak."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 31e28514ab4bdb0f5af261a1f7c87633ca0bd4a6
ms.openlocfilehash: 58671d037c7f62e5fdaa56657737a4470c90bdb7
ms.lasthandoff: 02/04/2017


---

# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Android for Work-alkalmazások konfigurálása a mobilalkalmazások konfigurációs szabályzataival Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune mobilalkalmazás-konfigurációs szabályzataival automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor a felhasználók iOS-alkalmazásokat futtatnak. Egy alkalmazás kérheti a felhasználótól például a következők megadását:

-   Egyéni portszám
-   Nyelvi beállítások
-   Márkajelzési beállítások, például a vállalat logója

Ha a felhasználó helytelenül adja meg a beállításokat, az növelheti az segélyszolgálatra nehezedő terheket, és lelassíthatja az új alkalmazások bevezetését.

A mobilalkalmazás-konfigurációs szabályzatokkal még azelőtt érvénybe léptetheti ezeket a beállításokat az eszközökön, hogy a felhasználók futtatnák az alkalmazást. A beállítások megadása automatikusan történik, és nincs szükség felhasználói beavatkozásra.

Az alkalmazás-konfigurációs szabályzatok akkor használhatók, ha a fejlesztő az alkalmazás létrehozásakor közzétette a vállalati alkalmazáskonfigurációkat. Így például a Google Chrome olyan beállításokat tesz közzé, amelyek segítségével alapértelmezett könyvjelzőket, engedélyezett és letiltott webhelyeket és egyebeket állíthat be. Vegye fel a kapcsolatot az alkalmazás fejlesztőjével, hogy megtudja, hogy támogatottak-e ezek a beállítások és hogyan tudja megadni azokat a szabályzatban.

Az alkalmazás-konfigurációs szabályzatot ugyanazon felhasználók részére telepíti központilag, akikhez a konfigurálni kívánt alkalmazást telepítette. Az alkalmazás futtatásakor a rendszer érvénybe lépteti az alkalmazásbeállításokat.

## <a name="configure-a-mobile-app-configuration-policy"></a>Mobilalkalmazás-konfigurációs házirend konfigurálása

1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Házirend** &gt; **Áttekintés** &gt; **Házirend hozzáadása** elemet.

2.  A szabályzatok listájában bontsa ki az **Anroid for Work** csomópontot, válassza a **Mobilalkalmazás konfigurációs szabályzata** lehetőséget, majd a **Szabályzat létrehozása** elemet.

    > [!TIP]
    > Ehhez a szabályzattípushoz csak egyéni beállításokat lehet megadni. Ajánlott beállítások nem állnak rendelkezésre.

3.  A **Házirend létrehozása** lap **Általános** részében adja meg a mobilalkalmazás-konfigurációs szabályzat nevét és, ha szeretné, a leírását.

4. A **Mobilalkalmazás konfigurációs szabályzata** részben adja meg a következő információkat:
    - **Annak az alkalmazásnak a csomagazonosítója, amelyre az adott konfiguráció vonatkozik** - a csomagazonosító az alkalmazás URL-címének „id=” részében található az alkalmazás oldalán a Google Play lapon. Például a Microsoft Excel alkalmazás csomagazonosítója **com.microsoft.office.excel**.
    - A szövegmezőben adja meg a konfigurálni kívánt alkalmazásbeállítások adatait. Ezeket a beállításokat az alkalmazás szállítójától kapta. Nem minden alkalmazás támogatja ezeket a beállításokat.
5.  Annak ellenőrzésére, hogy a megadott adatok formátuma érvényes tulajdonságlista, kattintson az **Ellenőrzés** lehetőségre.

    > [!IMPORTANT]
    > Amikor az **Ellenőrzés**lehetőségre kattint, az Intune ellenőrzi, hogy érvényes-e a megadott konfigurációs adatok formátuma. Azt azonban nem ellenőrzi, hogy az adatok működni fognak-e az alkalmazással, amelyhez társítva vannak.

6.  Amikor elkészült, kattintson a **Házirend mentése**gombra.

Az új szabályzat megjelenik a **Konfigurációs szabályzatok** csomópontban.


## <a name="deploy-the-app-configuration-policy"></a>Az alkalmazás-konfigurációs szabályzat telepítése
Miután létrehozta a mobilalkalmazás konfigurációs szabályzatát, azt telepítenie kell ugyanazokhoz a felhasználókhoz, akikhez azt az alkalmazást telepítette, amelyre a beállítások vonatkoznak.

A szabályzatok telepítésével kapcsolatos tudnivalókért lásd a [konfigurációs szabályzat telepítéséről](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) szóló részt.

Az alkalmazások munkahelyi Android eszközökre való központi telepítéséről itt talál információt: [Android for Work-alkalmazások központi telepítése az Intune-nal](android-for-work-apps.md).

Amikor a telepített alkalmazást futtatják egy eszközön, akkor az a mobilalkalmazás-konfigurációs szabályzatban megadott beállításokkal fog futni.

> [!TIP]
> Csak egy alkalmazás-konfigurációs szabályzatot telepítsen minden egyes alkalmazáshoz a felhasználók számára.

