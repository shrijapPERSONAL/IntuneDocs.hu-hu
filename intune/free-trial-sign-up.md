---
title: Rövid útmutató – A Microsoft Intune ingyenes kipróbálása
titlesuffix: ''
description: Ezt a rövid útmutatót követve létrehoz majd egy ingyenes próbaelőfizetést, megismerheti a támogatott konfigurációkat és hálózati követelményeket, és ha kívánja, saját tartománynevét is konfigurálhatja.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b0ed363acca7fc0021569009b1f672a06101e29f
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55834177"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Gyors útmutató: A Microsoft Intune ingyenes kipróbálása 

A Microsoft Intune lehetővé teszi, hogy az eszközök és alkalmazások kezelésével védje a munkatársak vállalati adatait. Ezt a rövid útmutatót követve létrehoz majd egy ingyenes előfizetést az Intune tesztkörnyezetben történő kipróbálásához.

Az Intune a Microsoft Azure Portal használatával felügyelt, felhőalapú szolgáltatásból kínál mobileszköz-kezelést (MDM) és mobilalkalmazás-kezelést (MAM). Az Intune használatával vállalata megfelelőségi szabályzatainak és követelményeinek eleget téve biztosíthatja munkatársai vállalati erőforrásainak (adatok, eszközök és alkalmazások) megfelelő konfigurálását, elérését és frissítését. 

## <a name="prerequisites"></a>Előfeltételek
A Microsoft Intune beállítása előtt tekintse át az alábbi követelményeket:

   - [Támogatott operációs rendszerek és böngészők](supported-devices-browsers.md) 
   - [A hálózati konfiguráció követelményei és a sávszélesség](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Regisztráció a Microsoft Intune ingyenes próbaverziójára

Az Intune kipróbálása 30 napig ingyenes. Ha már rendelkezik munkahelyi vagy iskolai fiókkal, **jelentkezzen be** vele, és adja hozzá az Intune-t az előfizetéshez. Ha még nem, **regisztrálhat** egy új fiókot, amellyel használatba veheti az Intune-t a cégében.

> [!IMPORTANT]
> Meglévő munkahelyi vagy iskolai fiókok nem vonhatók össze újonnan regisztrált fiókokkal.

1. Nyissa meg a [Microsoft Intune próbaverziójának](https://go.microsoft.com/fwlink/?linkid=2019088) oldalát, és töltse ki az űrlapot.

    ![Képernyőkép a Microsoft Intune próbaverziójának fiókregisztrációs weboldaláról](./media/account-sign-up-site-full-browser.png)

    Ha az informatikai operatív tevékenység és a felhasználók túlnyomó része nem az Ön földrajzi helyén van, érdemes lehet azt az adott földrajzi helyet kiválasztania az **Ország vagy régió** legördülő listában. Az Azure a regionális információt használja fel, hogy a megfelelő szolgáltatásokat nyújtsa. Ez a beállítás később már nem módosítható.

2. Hozzon létre fiókot a **.onmicrosoft.com** utótaggal kiegészített vállalati nevével. 

    ![Képernyőkép az Intune-ban próbafiókot új hitelesítő adat folyamat](./media/account-sign-up-site-user-id.png)

    Ha vállalata saját egyéni tartománnyal rendelkezik, amelyet a **.onmicrosoft.com** utótag nélkül szeretne használni, ezt a cikk későbbi részében ismertetett módon megváltoztathatja az Office 365 felügyeleti portálján.

3. A regisztrációs folyamat végén megtekintheti az új fiók adatait.

    ![Fiókadatok képe](./media/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-the-azure-portal"></a>Jelentkezzen be az Azure Portalra

1. Nyisson meg egy böngészőablakot, és írja be a címsorba a következőt: **https://portal.azure.com**. 
2. A bejelentkezéshez használja a fenti lépésekben megadott hitelesítő adatokat.

    ![Az Azure Portal bejelentkezési oldalának képe](./media/azure-portal-signin.png)

3. A lap bal oldalán lévő oldalsávon lévő **Minden szolgáltatás** lehetőséggel megtekintheti a Microsoft Intune-t az Azure Portalon.
4. A szűrőmezőben keressen rá a **Microsoft Intune-ra**, majd jelölje ki azt.
5. Kattintson a **csillagra**, amivel felveszi az Intune-t a kedvenc szolgáltatásai listájának aljára. Nyissa meg az Intune irányítópultot.

Amikor próbaverziót regisztrál, e-mailben elküldjük a fiókadatait és a regisztráció során megadott e-mail címet. Az e-mail megerősíti, hogy a próbaverzió aktív.

> [!TIP]
> Az Azure Portalon történő munkavégzés közben jobb eredményeket érhet el, ha a böngésző normál módban van és nem privát módban.

## <a name="set-the-mdm-authority-to-intune"></a>Az Intune beállítása MDM-szolgáltatóként

Miután bejelentkezett az Azure Portalra, és kiválasztotta az Intune-t, megjelenhet egy narancs színű sáv, amely azt jelzi, hogy még nem állította be az MDM-szolgáltatót. A mobileszköz-felügyeleti (MDM-) szolgáltató beállítása szabja meg, hogy miként kezelheti mobileszközeit. Az MDM-szolgáltatót még azelőtt kell beállítani, hogy a felhasználók eszközöket regisztrálhatnának a kezeléshez.

Az Intune az alábbi lépésekkel állítható be MDM-szolgáltatóként.

1. Nyisson meg egy böngészőablakot, és írja be a címsorba a következőt: **https://portal.azure.com**. 
2. Válassza a **Minden szolgáltatás** > **Microsoft Intune** lehetőséget.
3. Válassza azt a sávot, amely jelzi, hogy nem engedélyezte az eszközkezelést, vagy ha még nem látható a sáv, válassza az **Eszközök beléptetése** lehetőséget. Ha még nem engedélyezte az eszközkezelést meg fog jelenni az **MDM-szolgáltató kiválasztása** panel.

    > [!NOTE]
    > A narancssárga szalagcím csak akkor jelenik meg, ha még nem állított be az MDM-szolgáltatót.

    ![Az MDM-szolgáltató kiválasztása panel képe](./media/choose-mdm-authority.png) 

4. Az **MDM-szolgáltató kiválasztása** szakaszban állítsa be MDM-szolgáltatóként az **Intune MDM-szolgáltatót**.

Az MDM-szolgáltatóról további információért lásd [A mobileszköz-felügyeleti szolgáltató beállítása](mdm-authority-set.md) szakaszt.

## <a name="configure-your-custom-domain-name-optional"></a>Egyéni tartománynév konfigurálása (nem kötelező)

A fentiekben már volt szó arról, hogy ha vállalata saját egyéni tartománnyal rendelkezik, amelyet a **.onmicrosoft.com** utótag nélkül szeretne használni, ezt az Office 365 felügyeleti portálján megváltoztathatja. Megadhatja, ellenőrizheti és konfigurálhatja saját egyéni tartománynevét.  

> [!IMPORTANT]
> A kezdeti **onmicrosoft.com** tartománynév nem nevezhető át és nem távolítható el. Hozzáadhat, ellenőrizhet vagy eltávolíthat az Intune-nal használt egyéni tartományneveket vállalata egyértelmű identitásának megőrzése érdekében.

1. Nyissa meg az [Office 365 felügyeleti portálját](https://portal.office.com/Admin/Default.aspx), és jelentkezzen be rendszergazdai fiókjával.

2. A navigációs panelen kattintson a **Beállítás** > **Tartományok** > **Tartomány hozzáadása** elemre.

3. Gépelje be egyéni tartománynevét. Végül válassza a **Tovább** lehetőséget.

   ![Képernyőkép az Office 365 felügyeleti központ - tartomány hozzáadása](./media/domain-custom-add.png)

4. Ellenőrizze, hogy az imént megadott tartománynak Ön-e a tulajdonosa. 
    
    A **Kód küldése e-mailben** lehetőséget választva e-mailt küld a tartománya regisztrált kapcsolattartójának. Az e-mail beérkezése után másolja ki a kódot, és illessze be az **Írja be az ellenőrzőkódot** címkéjű mezőbe. Ha az ellenőrző kód egyezik, a tartomány hozzá lesz adva a bérlőjéhez. Előfordulhat, hogy a megjelenő e-mail nem ismerős. Egyes regisztráló szervezetek elrejtik a tartomány regisztrálásakor megadott valódi e-mail-címet.

   ![Képernyőkép az Office 365 felügyeleti központ – a tartomány ellenőrzése](./media/domain-custom-verify.png)

   > [!NOTE]
   > TXT típusú rekordok ellenőrzésének részletes leírását a [DNS-rekordok létrehozása bármely DNS-szolgáltatón az Office 365-höz](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166).

## <a name="admin-experiences"></a>Rendszergazdai felületek

Két portált használhat:
- Az Intune-irányítópultot az Azure-on ([portal.azure.com](https://portal.azure.com)), ahol megismerheti [az Intune képességeit](what-is-intune.md). Többnyire az Intune-irányítópulton fog dolgozni.
- Az Office 365 felügyeleti központját ([portal.office.com](https://portal.office.com)), ahol a felhasználókat adhatja hozzá és kezelheti, ha nem az Azure Active Directoryt használja ezekre a feladatokra. Továbbá fiókjának számlázási- támogatási- és egyéb aspektusait is kezelheti itt.

## <a name="next-steps"></a>További lépések

Ezt a rövid útmutatót követve létrehozott egy ingyenes előfizetést az Intune tesztkörnyezetben történő kipróbálásához. További információ az Intune beállításáról: [Az Intune beállítása](setup-steps.md).

Kövesse az Intune rövid útmutatóinak sorozatát a következő rövid útmutatóval.

> [!div class="nextstepaction"]
> [Gyors útmutató: Hozzon létre egy felhasználót, és a licenc hozzárendelése](quickstart-create-user.md)
