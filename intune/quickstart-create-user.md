---
title: Rövid útmutató – Felhasználó létrehozása az Intune-ban
description: Rövid útmutató – Felhasználó létrehozása az Intune-ban.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 10/30/2018
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 98c71bd4c93e869b429b7677b4fb7c442aa58643
ms.sourcegitcommit: c4258bb5824daf3f7e0ac3bb8afc539bde4d95da
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/16/2019
ms.locfileid: "57991082"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Gyors útmutató: Hozzon létre egy felhasználót, és a licenc hozzárendelése

Ezt a rövid útmutatót követve létrehozhat egy felhasználót, majd hozzárendelhet egy licencet. Az Intune használata során mindenkinek, aki hozzá kíván férni a vállalati adatokhoz, rendelkeznie kell felhasználói fiókkal. Később az Intune-rendszergazdák az ilyen felhasználók konfigurálásával szabályozhatják a hozzáférést.

Ha nem rendelkezik Intune-előfizetéssel, [regisztráljon egy ingyenes próbafiókkal](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Bejelentkezés az Intune-ba

Jelentkezzen be az [Intune-ba](https://aka.ms/intuneportal) [globális rendszergazdaként vagy Intune-szolgáltatásadminisztrátorként](users-add.md#types-of-administrators). Ha létrehozott egy Intune próba-előfizetést, az a fiók lesz a globális rendszergazda, amelyikkel azt létrehozta.

## <a name="create-a-user"></a>Felhasználó létrehozása

Az Intune-eszközkezelésbe való regisztráláshoz az illetőnek felhasználói fiókkal kell rendelkeznie.

1. Válassza az Intune-ban a **Felhasználók** > **Minden felhasználó** > **Új felhasználó** lehetőséget.
![Böngésző](media/quickstart-create-user/create-user.png)
2. A **Név** mezőben adja meg például a *Pataki Tivadar* nevet.
3. A **Felhasználónév** mezőben adjon meg egy felhasználóazonosítót, például Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Ha még nem konfigurálta ügyfele tartománynevét, használja az Intune-előfizetés (vagy az [ingyenes próbalehetőség](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)) létrehozásához használt, ellenőrzött tartománynevet. 

4. Válassza a **Jelszó megjelenítése** lehetőséget, és jegyezze fel az automatikusan generált jelszót, hogy be tudjon jelentkezni a teszteszközre.
5. Válassza a **Létrehozás** lehetőséget.

## <a name="assign-a-license-to-the-user"></a>Licenc hozzárendelése a felhasználóhoz

Miután létrehozott egy felhasználó, kell használnia a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) , hogy a felhasználó Intune-licenc hozzárendelése. Ha nem oszt ki neki licencet, akkor nem fogja tudni regisztrálni az eszközét az Intune-ban. 

1. Jelentkezzen be a [Microsoft 365 felügyeleti központban](http://go.microsoft.com/fwlink/p/?LinkId=698854) bejelentkezni az Intune-hoz használt hitelesítő adatokkal együtt.
2. Válassza a **Felhasználók** > **Aktív felhasználók** lehetőséget, majd válassza ki az imént létrehozott felhasználót.
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

Ezt a rövid útmutatót követve létrehozott egy felhasználót, és hozzárendelt egy licencet. Felhasználók Intune-hoz való hozzáadásáról további információt a [Felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-hoz](users-add.md) szakaszban találhat.

Kövesse az Intune rövid útmutatóinak sorozatát a következő rövid útmutatóval.

> [!div class="nextstepaction"]
> [Gyors útmutató: Hozzon létre egy csoportot, hogy a felhasználók kezelése](quickstart-create-group.md)
