---
title: Feltételes hozzáférés áttelepítése az Azure Portalra
titlesuffix: Microsoft Intune
description: Az Intune klasszikus portálján korábban létrehozott feltételes hozzáférési szabályzatokat újra hozzárendelheti az Azure Portalhoz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6dbd7d9079bdb826f83cce76650cacebee056b68
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184488"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Feltételes hozzáférési szabályzatok ismételt társítása az Intune klasszikus portáljáról az Azure Portalra való áttéréskor

Az új Azure Portallal kezdődően a feltételes hozzáférési ajánlatok alkalmazásonként több szabályzatot is támogatnak, és több testre szabási lehetőséget kínálnak. Ha korábban már létrehozott feltételes hozzáférési szabályzatokat az Intune klasszikus portálján, áttelepítheti azokat az Azure Portalra. 

## <a name="before-you-begin"></a>Előkészületek

Ha készen áll az Azure Portalra való áttérésre, akkor a következő lépéseket követve újra hozzárendelheti a korábban az Intune klasszikus portálján létrehozott feltételes hozzáférési szabályzatokat:

- Gyűjtse össze a korábban létrehozott feltételes hozzáférési szabályzatokat, hogy tudja, milyen beállításokat kell később újra társítania.

- Az ebben a témakörben leírt lépéseket követve újraalkothatja ezeket a szabályzatokat az Azure Portalon.

- Miután meggyőződött róla, hogy az új szabályzatok a várt módon működnek az Azure Portalon, tiltsa le a feltételes szabályzatokat az Intune klasszikus portálján.
<br /><br />
    - **Mielőtt letiltaná** a feltételes hozzáférési szabályzatokat az Intune klasszikus portálján, tervezze meg a felhasználók átmozgatását az új szabályzat hatálya alá. Két módszer létezik:
<br /><br />
        - **Használhatja ugyanazt a belefoglaló csoportot az Azure Portalon létrehozott szabályzatok alkalmazására úgy, hogy létrehoz egy új kizárt csoportot az Intune klasszikus portál által alkalmazott szabályzatokhoz**.
            - A felhasználók egy részét fokozatosan helyezze át a klasszikus portálon megadott kizárt csoportba. Ez megakadályozza az Intune klasszikus portálja által meghatározott szabályzatok alkalmazását. Az ugyanazon felhasználói csoporthoz az Azure Portalon létrehozott szabályzatok az Intune klasszikus portálon alkalmazottak mellett érvényesülnek. 
<br /><br />
        - **Hozzon létre egy új csoportot, amelyre az Azure Portalon alkalmazza a feltételes hozzáférési szabályzatokat**. Ha ezt a módszert választja, akkor a következőket kell tennie:
            - Fokozatosan távolítsa el a felhasználókat azokból a biztonsági csoportokból, amelyekre feltételes hozzáférési szabályzatok érvényesek az Intune klasszikus portálján.
            - Miután meggyőződött róla, hogy az új szabályzat ezen felhasználók esetében működik, letilthatja a szabályzatot az Intune klasszikus portálján. 
<br /><br />
- Ha a feltételes hozzáférési szabályzat az Exchange Active Sync (EAS) használatára van konfigurálva az Intune klasszikus portálján, akkor az [ebben a témakörben megadott utasítások](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) alapján **társítsa újra a feltételes hozzáférési szabályzat EAS-re vonatkozó beállításait az Azure Portalon**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Eszközalapú feltételes hozzáférési szabályzatok ellenőrzése az Intune klasszikus portálján

1.  Jelentkezzen be hitelesítő adataival az [Intune klasszikus portálon](https://manage.microsoft.com).

2.  Válassza a bal oldali menü **Szabályzat** pontját.

3.  Válassza a **Feltételes hozzáférést**, majd azt a Microsoft felhőszolgáltatást (például Exchange Online, SharePoint Online stb.), amelyhez feltételes hozzáférési szabályzatot hozott létre.

4.  Jegyezze fel a feltételes hozzáférés beállításait, és ezek felhasználásával hozza létre ugyanezeket a feltételes hozzáférési szabályzatokat az Azure Portalon.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Alkalmazás- és eszközalapú feltételes hozzáférési szabályzatok együttműködése

Az Azure Portal **Intune App Protection** paneljén a rendszergazdák alkalmazásalapú feltételes szabályokat állíthatnak be, így csak az Intune alkalmazásvédelmi szabályzatait támogató alkalmazások férhetnek hozzá a vállalati erőforrásokhoz. Dönthet úgy, hogy ezekkel az alkalmazásalapú feltételes hozzáférési szabályzatokkal átfedésben eszközalapú feltételes hozzáférési szabályzatokat is alkalmaz. Az eszközalapú és alkalmazásalapú feltételes szabályzatokat kombinálhatja (logikai ÉS) vagy választási lehetőséget kínálhat fel (logikai VAGY). A feltételes hozzáférési szabályzat követelményei szerint:

- Követelmény a megfelelő eszköz **ÉS** az engedélyezett alkalmazás használata.
    - A feltételes hozzáférési szabályzatot az [Azure Active Directory feltételes hozzáférés paneljén](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) és az [Intune App Protection paneljén](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kell beállítania.
<br /><br />
- Követelmény a megfelelő eszköz **VAGY** az engedélyezett alkalmazás használata.
    - A feltételes hozzáférési szabályzatot az [Intune klasszikus portálon](https://manage.microsoft.com) és az [Intune App Protection paneljén](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kell beállítania.

> [!TIP] 
> Ezt a témakört az Intune klasszikus portál és az Azure Portal felhasználói felületét összehasonlító képernyőképek illusztrálják.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Az Intune eszközalapú feltételes hozzáférési szabályzatok ismételt hozzárendelése

1. Ugorjon a [Feltételes hozzáférés az Azure Portalon](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) lapra, és jelentkezzen be a hitelesítő adataival.

2. Válassza az **Új szabályzat** lehetőséget.

3. Adja meg a szabályzat nevét.

4. A **Hozzárendelések** alatt válassza a **Felhasználók és csoportok** lehetőséget az új feltételes hozzáférési szabályzat létrehozásához.
    
    ![A kép egy felhasználói csoport kezelőfelületét hasonlítja össze az Intune portálján és az Azure Portalon](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Az Azure Portalon és a klasszikus portálon végzett kiválasztásnak meg kell egyeznie. Például ha a Minden felhasználó lehetőséget jelölte meg az Intune klasszikus portálján, akkor az Azure Portalon is a **Minden felhasználó** lehetőséget válassza. Ezen kívül, ha használta a **Kivételt képző csoportok** lehetőséget az Intune klasszikus portálon, akkor az ott kijelölt csoportokat ki kell zárnia az Azure Portalon is.

5. A csoport kijelölése után kattintson a **Kiválaszt**, majd a **Kész** gombra.

6. A **Hozzárendelések** szakaszban válassza a **Felhőalkalmazások** lehetőséget.

7. A **Felhőalkalmazások** panelen válassza az **Alkalmazások kijelölése** lehetőséget.

8. Jelölje ki az alkalmazást, amelyre alkalmazni kívánja az új feltételes hozzáférési szabályzatot, és kattintson a **Kiválaszt** gombra.

9. Kattintson a **Kész** gombra.

    ![A kép egy felhőalkalmazás kezelőfelületét hasonlítja össze az Intune portálján és az Azure Portalon](./media/reassign-ca-3.png)

    > [!TIP] 
    > Ha több alkalmazásra ugyanaz a szabályzat vonatkozik, akkor érdemes lehet egyetlen szabályzatba összevonni őket az Azure Portalon.

10. A **Hozzárendelések** szakaszban válassza a **Feltételek** lehetőséget.

11. A **Feltételek** panelen az **Eszközplatformok** alatt válassza ki az alkalmazható eszközplatformokat.

12. Ha végzett az eszközplatformok kijelölésével, kattintson kétszer a **Kész** gombra.

    ![A kép egy eszközplatform kezelőfelületét hasonlítja össze az Intune-portálján és az Azure Portalon](./media/reassign-ca-4.png)

    > [!TIP] 
    > Ha egyedi platformokat jelölt ki az Intune klasszikus portálon, akkor az Azure Portalon is válassza ki az egyes platformokat.

    > [!NOTE] 
    > A tartományhoz való csatlakozás és a Windows megfelelőség beállításait később is megadhatja.

13. A **Hozzárendelések** szakaszban válassza a **Feltételek** lehetőséget.

14. A **Feltételek** panelen az **Ügyfélalkalmazások** alatt válassza ki a megfelelő ügyfélalkalmazást.

15. Ha végzett az ügyfélalkalmazás kijelölésével, kattintson kétszer a **Kész** gombra.

    ![A kép egy ügyfélalkalmazás kezelőfelületét hasonlítja össze az Intune portálján és az Azure Portalon](./media/reassign-ca-6.png)

16. Ha kijelölte a böngészőbeállításokat az Intune klasszikus portálon, akkor az Azure Portalon jelölje ki a **Böngésző** és a **Mobilalkalmazások és asztali ügyfelek** lehetőséget is. Ha nem jelölte ki a böngészőbeállításokat az Intune klasszikus portálon, akkor csak a **Mobilalkalmazások és asztali ügyfelek** lehetőséget jelölje meg. 

17. A **Hozzáférés-vezérlés** területen válassza az **Engedélyezés** elemet.

18. A **Hozzáférési engedély feltételei** alatt jelölje ki a **Eszköz megfelelőként való megjelölésének megkövetelése** lehetőséget, majd kattintson a **Kiválaszt** gombra.

19. Ha van tartományba léptetett Windows-eszközöket megkövetelő szabályzata, és engedélyezi az Intune-ban regisztrált és megfelelő Windows-eszközöket is, akkor válassza a **Tartományba léptetett eszköz megkövetelése** és a **Megfelelőként megjelölt eszköz megkövetelése** feltételt, valamint **A kijelölt feltételek egyikének megkövetelése** lehetőséget.

20. Ha nem engedélyezi az Intune-ban regisztrált és megfelelő Windows-eszközöket, zárja ki a Windows-szabályzatot a jelenlegiből. Ezután hozzon létre külön szabályzatot az **Eszközplatform** értékét **Windows**ra állítva, belefoglalva a fentiek szerint beállított többi feltételt, és válassza a **Tartományba léptetett eszköz megkövetelése** feltételt a **Hozzáférési engedély feltételei** alatt.

21. Az **Új** feltételes hozzáférési szabályzat panelen kapcsolja be a **Szabályzat engedélyezése** kapcsolót, majd kattintson a **Létrehozás** gombra.

    ![A kép a feltételes hozzáférési szabályzat engedélyezésének kezelőfelületét hasonlítja össze az Intune klasszikus portálján és az Azure Portalon](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Az Intune eszközalapú feltételes hozzáférési szabályzatok ismételt hozzárendelése EAS-ügyfelek esetén

Ha az Exchange Online szabályzat részeként az Exchange Active Sync szolgáltatást is konfigurálta az Intune klasszikus portálján, akkor egy második feltételes hozzáférési szabályzatot is létre kell hoznia az Azure Portalon.

1. Ugorjon a [Feltételes hozzáférés az Azure Portalon](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) lapra, és jelentkezzen be a hitelesítő adataival.

2. Válassza az **Új szabályzat** lehetőséget.

3. Adja meg a szabályzat nevét.

4. A **Hozzárendelések** alatt válassza a **Felhasználók és csoportok** lehetőséget az új feltételes hozzáférési szabályzat létrehozásához.

    ![A kép egy felhasználói csoport kezelőfelületét hasonlítja össze az Intune portálján és az Azure Portalon](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Az Azure Portalon és az Intune-portálon végzett kiválasztásnak meg kell egyeznie. Például ha a Minden felhasználó lehetőséget jelölte meg az Intune klasszikus portálján, akkor az Azure Portalon is a **Minden felhasználó** lehetőséget válassza. Ezen kívül, ha használta a **Kivételt képző csoportok** lehetőséget az Intune klasszikus portálon, akkor az ott kijelölt csoportokat ki kell zárnia az Azure Portalon is.

5. A csoport kijelölése után kattintson a **Kiválaszt**, majd a **Kész** gombra.

6. A **Hozzárendelések** szakaszban válassza a **Felhőalkalmazások** lehetőséget.

7. A **Felhőalkalmazások** panelen kattintson a **Kijelölt alkalmazások**, majd az **Exchange Online** elemre. Kattintson a **Kiválaszt**, majd a **Kész** gombra.

    ![A kép egy felhőalkalmazás kezelőfelületét hasonlítja össze az Intune portálján és az Azure portalon](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Az EAS-ügyfelek feltételes hozzáférési szabályzatai nem vonatkozhatnak másik felhőalkalmazásra.

8. A **Feltételek** panelen az **Ügyfélalkalmazások** alatt válassza ki a megfelelő ügyfélalkalmazást. Ha az Intune által nem támogatott ügyfelek kitiltása mellett döntött, akkor válassza a **Szabályzat alkalmazása csak a támogatott platformokon** lehetőséget.

    ![A kép egy ügyfélalkalmazás kezelőfelületét hasonlítja össze az Intune portálján és az Azure Portalon](./media/reassign-ca-15.png)

9. Ha végzett az ügyfélalkalmazás kijelölésével, kattintson kétszer a **Kész** gombra.

10. A **Hozzáférés-vezérlés** területen válassza az **Engedélyezés** elemet.

11. A **Hozzáférési engedély feltételei** alatt jelölje ki a **Eszköz megfelelőként való megjelölésének megkövetelése** lehetőséget, majd kattintson a **Kiválaszt** gombra.

    ![A kép a hozzáférési engedélyek kezelőfelületét hasonlítja össze az Intune portálján és az Azure Portalon](./media/reassign-ca-16.png)

12. Az **Új** feltételes hozzáférési szabályzat panelen kapcsolja be a **Szabályzat engedélyezése** kapcsolót, majd kattintson a **Létrehozás** gombra.

    ![A kép a feltételes hozzáférési szabályzatok engedélyezésének kezelőfelületét hasonlítja össze az Intune portálján és az Azure Portalon](./media/reassign-ca-17.png)

> [!NOTE]
> Ha konfigurálja az **Eszközplatformokat**, a szabályzat mentése sikertelen lesz, és a „Szabályzat konfigurálása nem támogatott” üzenetet kapja. Az Exchange ActiveSync nem tudja azonosítani a csatlakozó eszköz által használt platformot. Az egyes eszközplatformok konfigurálása ezért nem támogatott az Exchange ActiveSync-eszközök szabályzatainak létrehozásakor.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Feltételes hozzáférési szabályzatok letiltása az Intune klasszikus portálján

Fontos, hogy miután újra hozzárendelte a feltételes hozzáférési szabályzatokat az Azure Portalon, fokozatosan letiltsa az Intune klasszikus portálján korábban létrehozott feltételes hozzáférési szabályzatokat. Emellett szükség lehet ugyanarra a biztonsági csoportra az Azure Portalon létrehozott feltételes hozzáférési szabályzatok alkalmazásához.

> [!NOTE]
> Mielőtt letiltaná a feltételes hozzáférési szabályzatokat az Intune klasszikus portálján, olvassa el az [Előkészületek](#before-you-begin) című fejezetet a témakör elején.

### <a name="to-disable-the-conditional-access-policies"></a>Feltételes hozzáférési szabályzatok letiltása

1.  Jelentkezzen be hitelesítő adataival az [Intune klasszikus portálon](https://manage.microsoft.com).

2.  Válassza a bal oldali menü **Szabályzat** pontját.

3.  Válassza a **Feltételes hozzáférést**, majd azt a Microsoft felhőszolgáltatást (például Exchange Online, SharePoint Online stb.), amelyhez feltételes hozzáférési szabályzatot hozott létre.

4.  Szüntesse meg a jelölést a **Feltételes hozzáférési szabályzat engedélyezése** lehetőség mellett, majd kattintson a **Mentés** elemre.

    ![A kép a feltételes hozzáférési szabályzatok letiltását ábrázolja az Intune klasszikus portálján](./media/reassign-ca-18.png)

## <a name="see-also"></a>Lásd még:

- [A feltételes hozzáférés szokásos módjai az Intune-nal](conditional-access-intune-common-ways-use.md)
- [alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md)
- [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
