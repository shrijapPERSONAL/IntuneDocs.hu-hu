---
title: "Feltételes hozzáférési szabályzatok áttelepítése az Intune klasszikus portáljáról az új Azure Portalra."
titleSuffix: Intune on Azure
description: "Feltételes hozzáférési szabályzatok áttelepítése az Intune klasszikus portáljáról az új Azure Portalra."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>Feltételes hozzáférési szabályzatok ismételt társítása az Intune klasszikus portáljáról az új Azure Portalra való áttéréskor

Az új Azure Portallal kezdődően a feltételes hozzáférési ajánlatok alkalmazásonként több szabályzatot is támogatnak és több testre szabási lehetőséget kínálnak.

## <a name="before-you-begin"></a>Előkészületek

Ha készen áll az új Azure Portalra való áttérésre, akkor a következő lépéseket követve újra hozzárendelheti a korábban, akár az Intune klasszikus portálján létrehozott feltételes hozzáférési szabályzatokat:

- Gyűjtse össze az Intune klasszikus portálján korábban létrehozott feltételes hozzáférési szabályzatokat, hogy tudja, milyen beállításokat kell később újra társítania.

- Az ebben a témakörben leírt lépéseket követve újraalkothatja ezeket a szabályzatokat az új Azure Portalon.

- Miután meggyőződött róla, hogy az új szabályzatok a várt módon működnek az új Azure Portalon, tiltsa le a feltételes szabályzatokat az Intune klasszikus konzolján.
<br /><br />
    - **Mielőtt letiltaná** a feltételes hozzáférési szabályzatokat az Intune klasszikus portálján, tervezze meg a felhasználók átmozgatását az új szabályzat hatálya alá. Két módszer létezik:
<br /><br />
        - **Használhatja ugyanazt a belefoglaló csoportot az új Azure Portalon létrehozott szabályzatok alkalmazására úgy, hogy létrehoz egy új kizárt csoportot az Intune klasszikus portál által alkalmazott szabályzatokhoz**.
            - A felhasználók egy részét fokozatosan helyezze át a klasszikus portálon megadott kizárt csoportba.  Ez megakadályozza az Intune klasszikus portálja által meghatározott szabályzatok alkalmazását. Az ugyanazon felhasználói csoporthoz az új Azure Portalon létrehozott szabályzatok az Intune klasszikus portálon alkalmazottak mellett érvényesülnek. 
<br /><br />
        - **Hozzon létre egy új csoportot, amelyre az új Azure Portalon alkalmazza a feltételes hozzáférési szabályzatokat**. Ha ezt a módszert választja, akkor a következőket kell tennie:
            - Fokozatosan távolítsa el a felhasználókat azokból a biztonsági csoportokból, amelyekre feltételes hozzáférési szabályzatok érvényesek az Intune klasszikus portálján.
            - Miután meggyőződött róla, hogy az új szabályzat ezen felhasználók esetében működik, letilthatja a szabályzatot az Intune klasszikus portálján. 
<br /><br />
- Ha a feltételes hozzáférési szabályzat az Exchange Active Sync (EAS) használatára van konfigurálva az Intune klasszikus portálján, akkor az [ebben a témakörben megadott utasítások](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) alapján **társítsa újra a feltételes hozzáférési szabályzat EAS-re vonatkozó beállításait az új Azure Portalon**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Eszközalapú feltételes hozzáférési szabályzatok ellenőrzése az Intune klasszikus portálján

1.  Jelentkezzen be hitelesítő adataival az [Intune klasszikus portálon](https://manage.microsoft.com).

2.  Válassza a bal oldali menü **Szabályzat** pontját.

3.  Válassza a **Feltételes hozzáférést**, majd a Microsoft felhőszolgáltatást (Exchange Online, SharePoint Online, stb.), amelyhez feltételes hozzáférési szabályzatot hozott létre.

4.  Jegyezze fel a feltételes hozzáférés beállításait, és ezeknek a jegyzeteknek a felhasználásával hozza létre ugyanezeket a feltételes hozzáférési szabályzatokat az új Azure Portalon.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Alkalmazás- és eszközalapú feltételes hozzáférési szabályzatok együttműködése

Az új Azure Portal **Intune App Protection** paneljén a rendszergazdák alkalmazásalapú feltételes szabályokat állíthatnak be, így csak az Intune alkalmazásvédelmi szabályzatait támogató alkalmazások férhetnek hozzá a vállalati erőforrásokhoz. Dönthet úgy, hogy ezekkel az alkalmazásalapú feltételes hozzáférési szabályzatokkal átfedésben eszközalapú feltételes hozzáférési szabályzatokat is alkalmaz. Az eszközalapú és alkalmazásalapú feltételes szabályzatokat a célnak megfelelően kombinálhatja (logikai ÉS) vagy választási lehetőséget kínálhat fel (logikai VAGY). A feltételes hozzáférési szabályzat követelményei szerint:

- Ha követelmény a megfelelő eszköz **ÉS** az engedélyezett alkalmazás használata.
    - A feltételes hozzáférési szabályzatot az [Azure AD feltételes hozzáférés paneljén](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) és az [Intune App Protection paneljén](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kell beállítania.
<br /><br />
- Ha követelmény a megfelelő eszköz **VAGY** az engedélyezett alkalmazás használata.
    - A feltételes hozzáférési szabályzatot az [Intune klasszikus portálon](https://manage.microsoft.com) és az [Intune App Protection paneljén](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kell beállítania.

> [!TIP] 
> Ezt a témakört az Intune klasszikus portál és az új Azure Portal felhasználói felületét összehasonlító képernyőképek illusztrálják.

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>Az Intune eszközalapú feltételes hozzáférési szabályzatok ismételt hozzárendelése

1. Ugorjon a [Feltételes hozzáférés az új Azure Portalon](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) lapra, és jelentkezzen be a hitelesítő adataival.

2. Válassza az **Új szabályzat** lehetőséget.

3. Adja meg a szabályzat nevét.

4. A **Hozzárendelések** alatt válassza a **Felhasználók és csoportok** lehetőséget az új feltételes hozzáférési szabályzat létrehozásához.
    
    ![Felhasználói csoportok kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Ha a Minden felhasználó lehetőséget jelölte meg az Intune klasszikus portálján, akkor foglaljon bele minden felhasználót. Ugyanez a csoportokra is vonatkozik. Ha jelölt ki csoportokat, akkor az **egyes felhasználók és csoportok kijelölése** alatt bele kell foglalnia ezeket a csoportokat. Ezen kívül, ha használta a **Kivételt képző csoportok** lehetőséget az Intune klasszikus portálon, akkor az ott kijelölt csoportokat ki kell zárnia az új Azure Portalon.

5. A csoport kijelölése után kattintson a **Kiválaszt**, majd a **Kész** gombra.

6. A **Hozzárendelések** alatt válassza a **Felhőalkalmazások** lehetőséget.

7. A **Felhőalkalmazások** panelen válassza az **Alkalmazások kijelölése** lehetőséget.

8. Jelölje ki az alkalmazást, amelyre alkalmazni kívánja az új feltételes hozzáférési szabályzatot, és kattintson a **Kiválaszt** gombra.

9. Kattintson a **Kész** gombra.

    ![Felhőalkalmazások kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-3.png)

    > [!TIP] 
    > Ha több alkalmazásra ugyanaz a szabályzat vonatkozik, akkor érdemes lehet egyetlen szabályzatba összevonni őket az új Azure Portalon.

10. A **Hozzárendelések** alatt válassza a **Feltételek** lehetőséget.

11. A **Feltételek** panelen az **Eszközplatformok** alatt válassza ki az alkalmazható eszközplatformokat.

12. Ha végzett az eszközplatformok kijelölésével, kattintson kétszer a **Kész** gombra.

    ![Eszközplatformok kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-4.png)

    > [!TIP] 
    > Ha egyedi platformokat jelölt ki az Intune klasszikus portálon, akkor az új Azure Portalon is válassza ki az egyes platformokat.

    > [!NOTE] 
    > A tartományhoz való csatlakozás és a Windows megfelelőség beállításait később is megadhatja.

13. A **Hozzárendelések** alatt válassza a **Feltételek** lehetőséget.

14. A **Feltételek** panelen az **Ügyfélalkalmazások** alatt válassza ki az alkalmazható ügyfélalkalmazást.

15. Ha végzett az ügyfélalkalmazás kijelölésével, kattintson kétszer a **Kész** gombra.

    ![Ügyfélalkalmazások kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-6.png)

16. Ha kijelölte a böngészőbeállításokat az Intune klasszikus portálon, akkor az új Azure Portalon jelölje ki a **Böngésző** és a **Mobilalkalmazások és asztali ügyfelek** lehetőséget is. Ha nem jelölte ki a böngészőbeállításokat az Intune klasszikus portálon, akkor csak a **Mobilalkalmazások és asztali ügyfelek** lehetőséget jelölje meg. 

17. A **Hozzáférés-vezérlés** alatt válassza az **Engedélyezés** elemet.

18. A **Hozzáférési engedély feltételei** alatt jelölje ki a **Eszköz megfelelőként való megjelölésének megkövetelése** lehetőséget, majd kattintson a **Kiválaszt** gombra.

19. Ha van tartományba léptetett Windows-eszközöket megkövetelő szabályzata, és engedélyezi az Intune-ban regisztrált és megfelelő Windows-eszközöket is, akkor válassza a **Tartományba léptetett eszköz megkövetelése** és a **Megfelelőként megjelölt eszköz megkövetelése** feltételt, valamint **A kijelölt feltételek egyikének megkövetelése** lehetőséget.

20. Ha nem engedélyezi az Intune-ban regisztrált és megfelelő Windows-eszközöket, zárja ki a Windows-szabályzatot a jelenlegiből, majd hozzon létre külön szabályzatot az **Eszközplatform** értékét **Windows**ra állítva, belefoglalva a fentiek szerint beállított többi feltételt, és válassza a **Tartományba léptetett eszköz megkövetelése** feltételt a **Hozzáférési engedély feltételei** alatt.

21. Kapcsolja be a **Szabályzat engedélyezése** kapcsolót az **Új** feltételes hozzáférési szabályzat panelen, majd kattintson a **Létrehozás** gombra.

    ![A feltételes hozzáférési szabályzat engedélyezésre szolgáló kezelőfelületek összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Az Intune eszközalapú feltételes hozzáférési szabályzatok ismételt hozzárendelése EAS-ügyfelek esetén

Ha az Exchange Online szabályzat részeként az Exchange Active Sync (EAS) szolgáltatást is konfigurálta az Intune klasszikus portálján, akkor egy második feltételes hozzáférési szabályzatot is létre kell hoznia az új Azure Portalon.

1. Ugorjon a [Feltételes hozzáférés az új Azure Portalon](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) lapra, és jelentkezzen be a hitelesítő adataival.

2. Válassza az **Új szabályzat** lehetőséget.

3. Adja meg a szabályzat nevét.

4. A **Hozzárendelések** alatt válassza a **Felhasználók és csoportok** lehetőséget az új feltételes hozzáférési szabályzat létrehozásához.

    ![Felhasználói csoportok kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Ha a Minden felhasználó lehetőséget jelölte meg az Intune klasszikus portálján, akkor foglaljon bele minden felhasználót. Ugyanez a csoportokra is vonatkozik. Ha jelölt ki csoportokat, akkor az **egyes felhasználók és csoportok kijelölése** alatt bele kell foglalnia ezeket a csoportokat. Ezen kívül, ha használta a **Kivételt képző csoportok** lehetőséget az Intune klasszikus portálon, akkor az ott kijelölt csoportokat ki kell zárnia az új Azure Portalon.

5. A csoport kijelölése után kattintson a **Kiválaszt**, majd a **Kész** gombra.

6. A **Hozzárendelések** alatt válassza a **Felhőalkalmazások** lehetőséget.

7. A **Felhőalkalmazások** panelen kattintson a **Kijelölt alkalmazások**, **Exchange Online**, **Kiválaszt**, majd a **Kész** gombra.

    ![Felhőalkalmazások kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Az EAS-ügyfelek feltételes hozzáférési szabályzatai nem vonatkozhatnak másik felhőalkalmazásra.

8. A **Feltételek** panelen az **Ügyfélalkalmazások** alatt válassza ki az alkalmazható ügyfélalkalmazást. Ha az Intune által nem támogatott ügyfelek kitiltása mellett döntött, akkor válassza a **Szabályzat alkalmazása csak a támogatott platformokon** lehetőséget.

    ![Ügyfélalkalmazások kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-15.png)

9. Ha végzett az ügyfélalkalmazás kijelölésével, kattintson kétszer a **Kész** gombra.

10. A **Hozzáférés-vezérlés** alatt válassza az **Engedélyezés** elemet.

11. A **Hozzáférési engedély feltételei** alatt jelölje ki a **Eszköz megfelelőként való megjelölésének megkövetelése** lehetőséget, majd kattintson a **Kiválaszt** gombra.

    ![Hozzáférés-engedélyezés kezelőfelületének összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-16.png)

12. Kapcsolja be a **Szabályzat engedélyezése** kapcsolót az **Új** feltételes hozzáférési szabályzat panelen, majd kattintson a **Létrehozás** gombra.

    ![A feltételes hozzáférési szabályzat engedélyezésre szolgáló kezelőfelületek összehasonlítása az Intune klasszikus portálján és az új Azure Portalon](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Feltételes hozzáférési szabályzatok letiltása az Intune klasszikus portálján
### <a name="before-you-start"></a>Előkészületek

Fontos, hogy miután újra hozzárendelte a feltételes hozzáférési szabályzatokat az új Azure Portalon, fokozatosan letiltsa az Intune klasszikus portálján korábban létrehozott feltételes hozzáférési szabályzatokat. Emellett szükség lehet ugyanarra a biztonsági csoportra az új Azure Portalon létrehozott feltételes hozzáférési szabályzatok alkalmazásához

- Mielőtt letiltaná a feltételes hozzáférési szabályzatokat az Intune klasszikus portálján, olvassa el az [Előkészületek](#before-you-begin) című fejezetet a témakör elején.

### <a name="to-disable-the-conditional-access-policies"></a>Feltételes hozzáférési szabályzatok letiltása

1.  Jelentkezzen be hitelesítő adataival az [Intune klasszikus portálon](https://manage.microsoft.com).

2.  Válassza a bal oldali menü **Szabályzat** pontját.

3.  Válassza a **Feltételes hozzáférést**, majd a Microsoft felhőszolgáltatást (Exchange Online, SharePoint Online, stb.), amelyhez feltételes hozzáférési szabályzatot hozott létre.

4.  Szüntesse meg a jelölést a **Feltételes hozzáférési házirend engedélyezése Exchange Online-hoz** lehetőség mellett, majd kattintson a **Mentés** gombra.

    ![Feltételes hozzáférési szabályzatok letiltása – Intune klasszikus portál](./media/reassign-ca-18.png)

## <a name="see-also"></a>További információ

- [A feltételes hozzáférés szokásos módjai az Intune-nal](conditional-access-intune-common-ways-use.md)
- [Alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md)
- [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)