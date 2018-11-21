---
title: Rövid útmutató – Felhasználó létrehozása az Intune-ban
description: Rövid útmutató – Felhasználó létrehozása az Intune-ban.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 10/30/2018
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: b5653c67766a3312cf7ce2872e8b0cd4301b0e8b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189489"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Rövid útmutató – Felhasználó létrehozása és licenc hozzárendelése az Intune-ban

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

A felhasználó létrehozása után az [Office 365-portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854) kell Intune-licencet rendelnie az új felhasználóhoz. Ha nem oszt ki neki licencet, akkor nem fogja tudni regisztrálni az eszközét az Intune-ban. 

1. Jelentkezzen be a [Office 365-portálra](http://go.microsoft.com/fwlink/p/?LinkId=698854) az Intune-ba való bejelentkezéshez használt hitelesítő adatokkal.
2. Válassza a **Felhasználók** > **Aktív felhasználók** lehetőséget, majd válassza ki az imént létrehozott felhasználót.
3. Válassza a **Terméklicencek** melletti **Szerkesztés** lehetőséget.
4. A **Hely** listában válassza ki a felhasználó helyét.
5. Kattintson az Intune-licenc (vagy a rendelkezésére álló más, az Intune-t magában foglaló licenc) melletti **Be** beállításra. A megjelenített [terméknév](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** lesz szolgáltatáscsomagként használva az Azure-felügyeletben. 

   > [!NOTE]
   > Ezzel a beállítással elhasználja a licencei egyikét ehhez a felhasználóhoz. Ha próbakörnyezetet használ, később újra hozzárendelheti ezt a licencet egy valódi felhasználóhoz, éles környezetben.
6. Válassza a **Mentés** > **Bezárás** lehetőséget.

Az új aktív Intune-felhasználónál ekkor már látható, hogy **Intune**-licencet használ.

## <a name="clean-up-resources"></a>Erőforrások eltávolítása

Ha többé nincs szüksége erre a felhasználóra, törölje az [Office 365 portál](http://go.microsoft.com/fwlink/p/?LinkId=698854) megnyitásával, ott pedig a **Felhasználók** > **Aktív felhasználók** > *a felhasználó kiválasztása a listából* > **Felhasználó törlése** > **Felhasználó törlése** > **Módosítások jóváhagyása** > **Bezárás** műveletsorral.

## <a name="next-steps"></a>További lépések

Ezt a rövid útmutatót követve létrehozott egy felhasználót, és hozzárendelt egy licencet. Felhasználók Intune-hoz való hozzáadásáról további információt a [Felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-hoz](users-add.md) szakaszban találhat.

Kövesse az Intune rövid útmutatóinak sorozatát a következő rövid útmutatóval.

> [!div class="nextstepaction"]
> [Rövid útmutató: Csoport létrehozása felhasználók kezeléséhez](quickstart-create-group.md)
