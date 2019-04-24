---
title: Rövid útmutató – Felhasználó létrehozása az Intune-ban
description: Rövid útmutató – Felhasználó létrehozása az Intune-ban.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/25/2019
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: b49595493b5db3e5735e0a4717c27e91f058b8d8
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511357"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Gyors útmutató: Hozzon létre egy felhasználót az Intune-ban, és licenceket rendel hozzájuk

Ebben a rövid útmutatóban hozzon létre egy felhasználót, és hozzárendelheti őket az Intune-ra. Ha az Intune-ban mindenki, aki szeretné engedélyezni a vállalati adatokhoz való hozzáférést a saját felhasználói fiókot kell rendelkeznie. Intune-rendszergazdák konfigurálhatják a később a felhasználóknak a hozzáférés-vezérlés kezelését.

Ha nem rendelkezik Intune-előfizetéssel, [regisztráljon egy ingyenes próbafiókkal](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Bejelentkezés az Intune-ba

Jelentkezzen be a [Intune](https://aka.ms/intuneportal) , egy [globális rendszergazda vagy egy Intune-szolgáltatásadminisztrátor](users-add.md#types-of-administrators). Ha létrehozott egy Intune próba-előfizetést, az a fiók lesz a globális rendszergazda, amelyikkel azt létrehozta.

## <a name="create-a-user"></a>Felhasználó létrehozása

Felhasználók regisztrálása az Intune-Eszközfelügyelet felhasználói fiókkal kell rendelkeznie. Új felhasználó létrehozása:

1. Válassza az Intune-ban a **Felhasználók** > **Minden felhasználó** > **Új felhasználó** lehetőséget.
![Böngésző](media/quickstart-create-user/create-user.png)
2. A **Név** mezőben adja meg például a *Pataki Tivadar* nevet.
3. A **Felhasználónév** mezőben adjon meg egy felhasználóazonosítót, például Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Ha még nem konfigurálta az ügyfél tartománynevet, használja az Intune-előfizetés létrehozásához használt ellenőrzött tartomány nevét (vagy [az ingyenes próbaidőszak](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Válassza a **Jelszó megjelenítése** lehetőséget, és jegyezze fel az automatikusan generált jelszót, hogy be tudjon jelentkezni a teszteszközre.
5. Válassza a **Létrehozás** lehetőséget.

## <a name="assign-a-license-to-the-user"></a>Licenc hozzárendelése a felhasználóhoz

Miután létrehozott egy felhasználó, kell használnia a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) az Intune-licencet rendelhet hozzájuk. Ha a felhasználói licenc nem rendel, fogják nem regisztrálják az eszközüket az Intune-ban. 

Az Intune-licencet hozzárendelni egy felhasználóhoz:

1. Jelentkezzen be a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) bejelentkezni az Intune-hoz használt hitelesítő adatokkal együtt.
2. Válasszon **felhasználók** > **aktív felhasználók** > Válassza ki az újonnan létrehozott felhasználót.
3. Válassza a **Terméklicencek** melletti **Szerkesztés** lehetőséget.
4. A **Hely** listában válassza ki a felhasználó helyét.
5. Kattintson az Intune-licenc (vagy a rendelkezésére álló más, az Intune-t magában foglaló licenc) melletti **Be** beállításra. A megjelenített [terméknév](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** lesz szolgáltatáscsomagként használva az Azure-felügyeletben. 

   > [!NOTE]
   > Ezzel a beállítással elhasználja a licencei egyikét ehhez a felhasználóhoz. Ha próbakörnyezetet használ, később újra hozzárendelheti ezt a licencet egy valódi felhasználóhoz, éles környezetben.
6. Válassza a **Mentés** > **Bezárás** lehetőséget.

Az új aktív Intune-felhasználónál ekkor már látható, hogy **Intune**-licencet használ.

## <a name="clean-up-resources"></a>Az erőforrások eltávolítása

Ez a felhasználó többé már nincs szüksége, ha a felhasználó törölheti az a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) válassza **felhasználók** > **aktív felhasználók**  >  *válasszon a listából a felhasználó* > **felhasználó törlése** > **felhasználó törlése** > **megerősítése módosítások** > **Bezárás**.

## <a name="next-steps"></a>További lépések

Ebben a rövid útmutatóban létrehozott egy felhasználó, és hozzájuk rendelt Intune-licencet. Felhasználók Intune-hoz való hozzáadásáról további információt a [Felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-hoz](users-add.md) szakaszban találhat.

Kövesse az Intune rövid útmutatóinak sorozatát a következő rövid útmutatóval.

> [!div class="nextstepaction"]
> [Gyors útmutató: Hozzon létre egy csoportot, hogy a felhasználók kezelése](quickstart-create-group.md)
