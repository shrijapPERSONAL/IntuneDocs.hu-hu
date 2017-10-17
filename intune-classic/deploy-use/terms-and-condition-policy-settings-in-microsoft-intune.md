---
title: "Használati feltételek szabályzatbeállításai"
description: "A felhasználói csoportok számára megjelenítheti az Intune használati feltételeit. Ezek elmagyarázzák, hogyan érinti az eszközöket és a felhasználókat a regisztráció, a munkahelyi erőforrásokhoz való hozzáférés és a Vállalati portál alkalmazás használata."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 75e68a49fb8437bb7742cfa1e458edab5c0b1836
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a>Használati feltételek házirend-beállításai a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A felhasználói csoportok számára megjelenítheti az Intune használati feltételeit. Ezek elmagyarázzák, hogy hogyan érinti az eszközöket és a felhasználókat a regisztráció, a munkahelyi erőforrásokhoz való hozzáférés, valamint a Munkahelyi portál alkalmazás használata. A felhasználóknak el kell fogadniuk a használati feltételeket ahhoz, hogy regisztrálhassanak a vállalati portálon, és így hozzáférhessenek a munkájukhoz.

Több, különböző használati feltételeket tartalmazó házirendet is létrehozhat és telepíthet. Emellett ugyanazon használati feltételek különböző nyelvű verzióit is elkészítheti, majd telepítheti azokat a megfelelő csoportokban.

## <a name="create-a-terms-and-conditions-policy"></a>Használati feltételekre vonatkozó szabályzat létrehozása

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Házirend** &gt; **Feltételek és kikötések** elemre.

    ![Képernyőfelvétel a Feltételek és kikötések szabályzatról](./media/pol-sa-terms-conditions.png)

2.  Egy új, használati feltételekre vonatkozó házirend létrehozásához kattintson a **Hozzáadás** elemre.

    A meglévő házirendeket **szerkesztheti** és **törölheti** is.

3.  A **Használati feltételek létrehozása** lapon adja meg a következő adatokat:

    -   **Név**&mdash;a szabályzatnak az Intune-konzolon megjelenő egyedi neve.

    -   **Leírás**&mdash;a szabályzatnak az Intune-konzolon való azonosítását segítő részletek.

    -   **Cím**&mdash;a cím, amely a felhasználók számára is megjelenik a munkahelyi portálban.

    -   **Annak magyarázata, hogy mit jelent a feltételek elfogadása a felhasználó részéről**&mdash;a felhasználók számára megjelenő, az elfogadásra vonatkozó címke. Például: „Elfogadom a feltételeket és kikötéseket.”

4.  Amikor végzett, kattintson a **Mentés** gombra. Az új házirend megjelenik a **Házirend** munkaterület **Feltételek és kikötések** csomópontjában.

## <a name="deploy-a-terms-and-conditions-policy"></a>A használati feltételekre vonatkozó szabályzat telepítése

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Házirend** &gt; **Feltételek és kikötések** elemre.

2.  A **Használati feltételekkel kapcsolatos házirendek** listáról válassza ki a bevezetni kívánt házirendet, majd kattintson a **Központi telepítés kezelése** elemre.

3.  Az **Üzembe helyezés kezelése** párbeszédpanelen válassza ki azt a felhasználói csoportot, amelynek telepíteni kívánja a szabályzatot, majd kattintson az **OK** gombra.

    Amikor a megcélzott felhasználók hozzáférnek a vállalati portálhoz, az Intune megjeleníti a telepített feltételeket és kikötéseket. Ahhoz, hogy hozzáférhessenek a vállalati erőforrásokhoz, a felhasználóknak el kell fogadniuk ezeket a feltételeket.

## <a name="monitor-a-terms-and-conditions-policy"></a>A használati feltételekre vonatkozó szabályzat figyelése

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Házirend** &gt; **Feltételek és kikötések** elemre.

2.  Kattintson a **Jelentés megtekintése** lehetőségre az **Új jelentés létrehozása** ablakban. Ekkor megnyílik a jelentés, és részletesen leírja, hogy mely felhasználók fogadták el a telepített használati feltételeket.

### <a name="updates-and-version-control-for-terms-and-conditions"></a>A használati feltételek frissítése és a verziókövetése
Egy meglévő használati feltételekre vonatkozó szabályzat szerkesztésekor beállíthatja, hogy mi történjen a szabályzat telepítésekor. Az alábbi eljárással frissítheti a meglévő használati feltételekre vonatkozó házirendeket.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>A használati feltételek több változatának használata

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Házirend** &gt; **Feltételek és kikötések** elemre.

2.  Jelölje ki a szerkeszteni kívánt használati feltételekre vonatkozó házirendet, majd kattintson a **Szerkesztés** elemre.

3.  A **Használati feltételek szerkesztése** lapon végezze el a szükséges módosításokat, majd adja meg, hogy az új verzió minden felhasználótól megkövetelje-e a használati feltételek elfogadását, vagy az új verzió csak az új felhasználók számára jelenjen meg.

    Javasoljuk, hogy amikor jelentős módosításokat végez a használati feltételeken, mindig növelje meg a verziószámot, és követelje meg az új feltételek elfogadását. Akkor tartsa meg az aktuális verziószámot, ha például gépelési hibákat javít vagy a formázást módosítja.

### <a name="see-also"></a>További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
