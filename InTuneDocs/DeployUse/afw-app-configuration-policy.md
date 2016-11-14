---
title: "Az Android for Work-mobilalkalmazások konfigurációs szabályzatainak használata | Microsoft Intune"
description: "Az Intune-ban a mobilalkalmazások konfigurációs szabályzataival adhatja meg az olyan beállításokat, amelyekre szükség lehet, amikor a felhasználók Android for Work-alkalmazásokat futtatnak."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: a986e859e38e0936f53c57a75872dc86de3ee181


---

# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Android for Work-alkalmazások konfigurálása a mobilalkalmazások konfigurációs szabályzataival Microsoft Intune-ban

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

A Microsoft Intune mobilalkalmazás-konfigurációs szabályzataival automatikusan megadhatja az olyan beállításokat, amelyekre szükség lehet, amikor a felhasználók iOS-alkalmazásokat futtatnak. Egy alkalmazás kérheti a felhasználótól például a következők megadását:

-   Egyéni portszám.

-   Nyelvi beállítások.

-   Márkajelzési beállítások, például a vállalat logója.

Ha ezeket a beállításokat a felhasználó helytelenül adja meg, az növelheti az segélyszolgálatra nehezedő terheket, és lelassíthatja az új alkalmazások bevezetését.

A mobilalkalmazás-konfigurációs szabályzatok segítséget nyújthatnak ezeknek a problémáknak a megoldásában azáltal, hogy lehetővé teszik ezeknek a beállításoknak a központi telepítését a felhasználók számára még az alkalmazás futtatása előtt. A beállítások megadása ezek után automatikusan történik, és nincs szükség felhasználói beavatkozásra.

Az alkalmazás-konfigurációs szabályzatok akkor használhatók, ha az alkalmazás fejlesztője az alkalmazás létrehozásakor közzétette a vállalati alkalmazás-konfigurációkat. Így például a Google Chrome olyan beállításokat tesz közzé, amelyek segítségével alapértelmezett könyvjelzőket, engedélyezett és letiltott webhelyeket és egyebeket állíthat be. Vegye fel a kapcsolatot az alkalmazás fejlesztőjével, hogy megtudja, hogy támogatottak-e ezek a beállítások és hogyan tudja megadni azokat a szabályzatban.

Az alkalmazás-konfigurációs szabályzatot ugyanazon felhasználók részére telepíti központilag, akikhez a konfigurálni kívánt alkalmazást telepítette. A szabályzat-beállítások használatára az alkalmazás minden egyes futtatásakor sor kerül.

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



<!--HONumber=Oct16_HO2-->


