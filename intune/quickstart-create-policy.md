---
title: 'Rövid útmutató: Windows 10-es eszközök megfelelőségi szabályzatainak hozzáadása'
description: A rövid útmutató alapján létrehozott szabályzatokkal megvédheti a vállalati adatait, és kezelheti a végfelhasználók által a céges erőforrások elérésére használt eszközöket. Valamint hozzárendelheti a szabályzatokat csoportokhoz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9d9169ab353da30e0f7b292cea4f5b9c93e316aa
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49391552"
---
# <a name="quickstart-add-a-device-compliance-policy-for-a-windows-10-device"></a>Rövid útmutató: Windows 10-es eszközök megfelelőségi szabályzatainak hozzáadása
A Windows-eszközmegfelelőségi szabályzatokkal megszabhatja a Windows-eszközöktől a megfelelőséghez kötelezően elvárt szabályokat és beállításokat. Ezeket a szabályzatokat [feltételes hozzáféréssel](https://docs.microsoft.com/intune/conditional-access) használva megakadályozható vagy engedélyezhető a vállalati erőforrásokhoz való hozzáférés. Emellett lekérhet eszközjelentéseket, és különböző műveleteket hajthat végre meg nem felelés esetén.

Ezt a rövid útmutatót követve létrehozhat egy megfelelőségi szabályzatot egy Windows 10-es eszközhöz, majd hozzárendelhet egy eszközcsoportot a szabályzathoz.

Ha nem rendelkezik Intune-előfizetéssel, [regisztráljon egy ingyenes próbafiókkal](free-trial-sign-up.md).

## <a name="prerequisites"></a>Előfeltételek
- Ennek a rövid útmutatónak a követéséhez [létre kell hoznia egy felhasználót](quickstart-create-user.md), majd [létre kell hoznia egy csoportot](quickstart-create-group.md).


## <a name="sign-in-to-intune"></a>Bejelentkezés az Intune-ba
Jelentkezzen be az [Intune-ba](https://aka.ms/intuneportal) globális rendszergazdaként vagy Intune-beli szolgáltatásadminisztrátorként.

## <a name="create-a-device-compliance-policy"></a>Eszközmegfelelőségi szabályzat létrehozása
1. Válassza az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** lehetőséget.
2. A **Név** mezőbe írja be a **Windows 10 megfelelőség**, a **Leírás** mezőbe pedig a **Minta megfelelőségi szabályzat Windows 10-hez** szöveget.
3. A **Platform** beállításnál válassza a **Windows 10 és újabb** lehetőséget.
4. A **Beállítások** részben válassza a **Rendszerbiztonság** elemet, majd adja meg a **Jelszó szükséges a mobileszközök feloldásához** lehetőséghez a **Kötelező** beállítást. Amikor befejezte a szabályzat beállítását, válassza az **OK** gombot.
   ![Megfelelőségi szabályzat](/intune/media/quickstart-create-policy/compliance-policy.png)
5. Zárja be a **Windows 10-re vonatkozó megfelelőségi szabályzat** panelt. 
6. A **Szabályzat létrehozása** panelen válassza a **Létrehozás** lehetőséget. Ezzel a lépéssel létrehozza a szabályzatot, és felveszi azt az **Eszközmegfelelőség** > **Szabályzatok** listára.
7. Válassza ki az új szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
8. Meglévő Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Válassza a **Contoso tesztelők** csoportot, majd a **Mentés** lehetőséget, hogy érvénybe léptesse a szabályzatot a csoportban lévő felhasználók számára. Ha nem hozta létre ezt a csoportot a [csoport létrehozása](quickstart-create-group.md) során, használhatja az Ön által választott csoportot. 

## <a name="clean-up-resources"></a>Erőforrások eltávolítása
Ha többé nincs szükség a szabályzatra, törölje. Ehhez jelölje ki a **Windows 10-re vonatkozó megfelelőségi** szabályzatot, és kattintson a **Törlés** lehetőségre. 

## <a name="next-steps"></a>További lépések
Ebben a rövid útmutatóban egyszerű eszközmegfelelőségi szabályzatot hozhatott létre és rendelhetett hozzá egy csoporthoz. Egy ezt a szabályzatot megkapó Windows 10-es eszköz regisztrálásához lépjen tovább az automatikus regisztráció beállítását ismertető rövid útmutatóra. 
 
> [!div class="nextstepaction"]
> [Hossz megadása az eszközök jelszavainál](quickstart-set-password-length-android.md)