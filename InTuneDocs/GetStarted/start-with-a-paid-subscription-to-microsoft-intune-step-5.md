---
title: "Csoportok létrehozása a felhasználók és eszközök rendszerezéséhez | Microsoft Intune"
description: "A felhasználók és csoportok létrehozása az Intune-előfizetéséhez"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4f8db75ed17e70dae5d3507b6af33a835c1658e9
ms.openlocfilehash: 5195de40f35085c45ae63957da1a9058ed7d6493


---


# <a name="create-groups-to-organize-users-and-devices"></a>Csoportok létrehozása a felhasználók és eszközök rendszerezéséhez
Az Intune csoportjai az eszközök és felhasználók rendkívül rugalmas kezelését teszik lehetővé. Különböző, a szervezet igényeinek megfelelő csoportokat állíthat be (például földrajzi hely, részleg vagy hardverjellemzők alapján), melyekkel számos felügyeleti feladatot elvégezhet, a házirendek felhasználók csoportjai számára történő telepítésétől az alkalmazások eszközök csoportjaira való telepítéséig.

## <a name="group-management-moving-to-azure-ad"></a>A csoportfelügyelet áthelyezése az Azure AD-be

**2016 novemberétől kezdve** az új ügyfelek az Azure Acitve Directory (AD) portálon kezelik a felhasználócsoportokat és az eszközcsoportokat. 2016 decemberében az Intune-termékcsapat megkezdi a meglévő ügyfelek áttelepítését az új, Azure AD-alapú csoportfelügyeleti rendszerbe. A felhasználó- és eszközcsoportok mindegyikét át fogjuk telepíteni az Azure AD-alapú biztonsági csoportokba. Az áttelepítést nem kezdjük mindaddig, amíg nem tudjuk minimálisra csökkenteni a napi munkára gyakorolt hatását és nem látjuk úgy, hogy az várhatóan semmiféle hatással nem lesz a felhasználókra. A fiókja áttelepítését megelőzően értesíteni fogjuk.


>[!IMPORTANT]
>
>Ha az Intune-portál Csoportok munkaterületének megnyitásakor megjelenik **Az Intune-beli felhasználócsoportok most már Azure Active Directory-beli csoportokként vannak kezelve** hivatkozás, amely az Azure Active Directory portálra mutat, akkor Ön már az *új*, az Azure AD biztonsági csoportjain alapuló csoportkezelést használja az Intune-ban. A csoportok létrehozásáról és kezeléséről a [Csoportkezelés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-manage-groups) című cikk nyújt tájékoztatást.
>
>Ha nem látja az Azure AD portálra mutató hivatkozást, akkor még mindig Intune-t használja a csoportok kezelésére.

## <a name="group-management-in-the-intune-portal"></a>Csoportkezelés az Intune-portálon

Az eszközcsoportok és felhasználói csoportok létrehozása egyaránt az Intune felügyeleti konzol CSOPORTOK munkaterületén történik.

![A felügyeleti konzol Csoportok munkaterülete](./media/groups.png)


> [!TIP]
> A csoportok használatáról további tájékoztatást a [Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) című témakörben olvashat.


## <a name="create-a-device-group"></a>Eszközcsoport létrehozása
Az eszközcsoportokat alkalmazások és frissítések telepítésére, valamint egyéb funkciók konfigurálására használhatja. Például állítsa be az „Eszközök” csoportot a következő lépések alapján:

1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) válassza a **Csoportok** > **Áttekintés** > **Csoport létrehozása** elemet.

2.  A **Csoport neve** mezőbe írja be az „Eszközök” értéket, a szülőcsoportok listájából válassza ki a **Minden eszköz** lehetőséget, majd válassza a **Tovább** gombot.

3.  A **Tagság feltételeinek meghatározása** lapon a **Minden eszköz** lehetőséget kiválasztva jelezze, hogy a csoport mobileszközöket és számítógépeket is tartalmaz.

4.  A **Közvetlen tagság meghatározása** lapon válassza a **Tovább** gombot. Ha előzőleg olyan csoportot hozott létre, amely nem tartalmazza az összes eszközt, és konkrét eszközöket szeretne hozzáadni az új csoporthoz, azt itt teheti meg.

5.  Az **Összefoglalás** lapon tekintse át a végrehajtandó műveleteket, majd kattintson a **Befejezés** gombra.

Az újonnan létrehozott csoportot megtalálhatja a **Csoportok** munkaterület **Csoportok** listájának **Minden eszköz** lapján. Itt szerkesztheti és törölheti is a csoportot.

## <a name="create-a-user-group"></a>Felhasználói csoport létrehozása
A felhasználói csoportokat szoftverek és eszköz- házirendek telepítésére használhatja. Például állítsa be az „Intune-felhasználók” csoportot a következő lépések alapján:

1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) válassza a **Csoportok** > **Áttekintés** > **Csoport létrehozása** elemet.

2.  A **Csoport neve** mezőbe írja be az „Intune-felhasználók” értéket, a szülőcsoportok listájából válassza ki a **Minden felhasználó** lehetőséget, majd kattintson a **Tovább** gombra.

3.  A **Tagság feltételeinek meghatározása** lap **Csoporttagság kezdése a következővel** beállítását állítsa **A szülőcsoport összes felhasználója**értékre.

4.  Kattintson a **Tagok kizárása ezekből a biztonsági csoportokból** lehetőség melletti **Tallózás** gombra, és válassza a **Vállalati rendszergazda** lehetőséget. Ez a kizárás lehetővé teszi, hogy az Intune-felhasználók csoportot a vállalati rendszergazda fiók (más néven a bérlői rendszergazda) érintése nélkül kezelhesse.

5.  A **Közvetlen tagság meghatározása** lapon válassza a **Tovább** gombot. Itt semmit nem kell tennie, mivel a vállalati rendszergazdán kívül minden felhasználónak bele kell tartoznia az Intune-felhasználók csoportba.

6.  Az **Összefoglalás** lapon tekintse át a végrehajtandó műveleteket, majd válassza a **Befejezés** gombot.

Az újonnan létrehozott csoportot megtalálhatja a **Csoportok** munkaterület **Csoportok** listájának **Minden felhasználó** lapján. Itt szerkesztheti és törölheti is a csoportot.



### <a name="next-steps"></a>További lépések
Gratulálunk! Ezzel befejezte az *Intune – Első lépések* útmutató 5. lépését.

>[!div class="step-by-step"]

>[&larr; **Az Intune-licencek kezelése**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**Szabályzatok és alkalmazások létrehozása** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  



<!--HONumber=Nov16_HO4-->


