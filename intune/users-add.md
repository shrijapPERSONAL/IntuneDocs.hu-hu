---
title: "Felhasználók hozzáadása és engedélyek megadása"
description: "A helyszíni felhasználók szinkronizálása az Azure AD-vel és rendszergazdai jogosultság megadása az Intune-előfizetésnek"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4289fdbdadbef34f06514b62722f84354534ae65
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/10/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-hoz

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ez a témakör arról tájékoztatja a rendszergazdákat, hogy miképpen vehetnek fel felhasználókat az Intune-ba, és milyen felügyeleti engedélyek érhetők el az Intune szolgáltatásban.

A rendszergazdák jogosultak közvetlenül felvenni az új felhasználókat, vagy szinkronizálni a felhasználókat a helyszíni Active Directoryból. Ha felvették a felhasználókat a szolgáltatásba, regisztrálhatják az eszközeiket, és elérhetik a vállalati erőforrásokat. További jogosultságokat is adhat a felhasználóknak, többek között *globális rendszergazdai* és *szolgáltatásadminisztrátori* engedélyeket.

## <a name="add-users-to-intune"></a>Felhasználók hozzáadása az Intune-hoz
Az Intune-előfizetéshez manuálisan is hozzáadhat felhasználókat az [Office 365-portál](https://www.office.com/signin) vagy az [Azure Intune-portál](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) segítségével. A rendszergazda módosíthatja a felhasználói fiókokat az Intune-licencek hozzárendeléséhez. A licenceket az Office 365-portálról vagy az Intune Azure-portálról oszthatja ki. Az Office 365-portál használatával kapcsolatos további tudnivalókért lásd: [Felhasználók felvétele egyenként és tömegesen az Office 365-portálra](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Intune-felhasználók felvétele az Office 365 Felügyeleti központban
1. Jelentkezzen be az [Office 365-portálra](https://www.office.com/signin).
2. Az Office 365 menüjében válassza a **Rendszergazda** elemet.
3. A Felügyeleti központban válassza a **Felhasználó hozzáadása** elemet.

  ![Az Office 365 Felügyeleti központ képernyőképe](media/office-add-user.png)

4. Adja meg a következő felhasználói adatokat:
  - **Utónév**
  - **Vezetéknév**
  - **Megjelenített név** – az Intune-portálon jelenik meg
  - **Felhasználónév** – egyszerű felhasználónév az Intune-portálon
  - **Hely**
  - **Kapcsolattartási adatok** (nem kötelező)
  - **Jelszó** –automatikus létrehozás vagy adja meg

     ![Az Office 365 Felügyeleti központ képernyőképe](media/office-add-user-details.png)

5. Rendeljen hozzá egy Intune-licencet. Válassza a **Terméklicencek** lehetőséget, és válassza ki a terméklicencet.
6. Válassza a **Hozzáadás** gombot az új felhasználó létrehozásához.

### <a name="add-intune-users-in-the-azure-intune-portal"></a>Intune-felhasználók felvétele az Azure Intune-portálon
1. Jelentkezzen be az [Azure portálra](https://portal.azure.com), majd lépjen a **Monitoring + Management** > **Intune** elemre. *Kereshet erőforrásokat* is az **Intune-hoz**.
2. Válassza a **Felhasználók** lehetőséget.
3. A Felügyeleti központban válassza a **Felhasználó hozzáadása** elemet.
  ![Az Office 365 Felügyeleti központ képernyőképe](media/intune-add-user.png)
4. Adja meg a következő felhasználói adatokat:
  - **Név**
  - **Felhasználónév** – Az új név az Azure Active Directory-portálon ![Az Office 365 Felügyeleti központ képernyőképe](media/intune-add-user-info.png) Válassza az **OK** gombot a folytatáshoz.
5. Szükség esetén a következő felhasználói tulajdonságokat is megadhatja:
  - **Profil** – Munkahelyi adatok, többek között a **Beosztás megnevezése** és a **Részleg**
  -  **Csoportok** – Válasszon a felhasználó által felehető csoportokat
  - **Címtár szerepkör** – Rendszergazdai jogosultságok adása a felhasználónak az Intune-hoz

  Az új felhasználó Intune-hoz adásához válassza a **Létrehozás** gombot.
6. Válassza a **Profil** lehetőséget, majd válasszon egy **Felhasználási helyet** az új felhasználónak. A felhasználási hely megadása szükséges, mielőtt az új felhasználóhoz hozzárendelhetne egy Intune-licencet. A folytatáshoz válassza a **Mentés** gombot.
    ![Az Office 365 Felügyeleti központ képernyőképe](media/intune-add-user-loc.png)
7. Intune-licenc felhasználóhoz rendeléséhez válassza a **Licencek** lehetőséget, majd a **Hozzárendelés** elemet. Az eszközök regisztrálásához és a vállalati erőforrások eléréséhez Intune-licenc szükséges. Válassza a **Termékek** lehetőséget, válassza ki a licenctípust, aztán a **Kiválasztás** lehetőséget, majd a **Hozzárendelés** elemet.

## <a name="grant-admin-permissions"></a>Rendszergazdai jogosultságok megadása

Javasoljuk, hogy a felhasználók Intune-előfizetéshez történő hozzáadása után biztosítson néhány felhasználó számára rendszergazdai engedélyt:
-   [Globális rendszergazda](#tenant-administrator): Ezt a rendszergazdatípust az Office 365-portál használatával rendelheti hozzá az előfizetés kezelése céljából, beleértve a számlázást, a felhőalapú tárolást és azon felhasználók felügyeletét, akik számára engedélyezte az Intune használatát.
-   [Testreszabott vagy korlátozott rendszergazda](#service-administrator): Ezt a rendszergazdatípust az Office 365 vagy az Azure Intune konzoljával állíthatja be a napi rutinfeladatok elvégzése céljából, ideértve az eszközök és a számítógépek felügyeletét, a szabályzatok érvénybe léptetését, az alkalmazások telepítését, illetve a jelentéskészítést.

![Az Office 365-portál hozzárendelési szabályainak képe.](./media/office-assign-roles.png)

### <a name="types-of-administrators"></a>Rendszergazdatípusok

Rendeljen hozzá egy vagy több rendszergazdai jogosultságot a felhasználókhoz. Ezek az engedélyek definiálják a felügyeleti hatókört a felhasználók és az általuk kezelhető feladatokra vonatkozóan. A Microsoft különböző felhőszolgáltatásai ugyanazokat a rendszergazdai jogosultságokat használják, azonban előfordulhat, hogy egyes szolgáltatások nem támogatnak bizonyos jogosultságokat. Az Intune a következő rendszergazdai jogosultságokat használja:

- **Globális rendszergazda** – (Office 365 és Intune) Az Intune összes rendszergazdai funkciójához hozzáfér. Alapértelmezés szerint a rendszer az Intune-ba regisztráló felhasználót állítja be globális rendszergazdának. Kizárólag a globális rendszergazdák jogosultak a többi rendszergazdai szerepkör kiosztására. A szervezetben egynél több globális rendszergazda is működhet. Javasoljuk, hogy a kockázat minimalizálása érdekében ne adja meg túl sok személynek ezt a szerepkört.
- **Számlázási adminisztrátor** – (Office 365 és Intune) Lebonyolítja a vásárlásokat, kezeli az előfizetéseket és a támogatási jegyeket, valamint figyeli a szolgáltatás állapotát.
- **Jelszókezelő** – (Office 365 és Intune) Átállítja a jelszavakat, kezeli a szolgáltatáskéréseket, illetve figyeli a szolgáltatás állapotát. A jelszókezelők kizárólag a felhasználók jelszavának átállítására jogosultak.
- **Szolgáltatásadminisztrátor** – (Office 365) Benyújtja a támogatási kéréseket a Microsoftnak, és jogosult megtekinteni a szolgáltatás irányítópultját és üzenetközpontját. Ezekhez kizárólag „csak olvasási” hozzáféréssel rendelkeznek, csak a támogatási jegyeket nyithatják meg és olvashatják el.
- **Felhasználókezelő rendszergazda** – (Office 365 és Intune) Visszaállítja a jelszavakat, figyeli a szolgáltatás állapotát, hozzáadja és törli a felhasználói fiókokat, valamint kezeli a szolgáltatáskéréseket. A felhasználókezelő rendszergazda nem törölheti a globális rendszergazdákat, nem hozhat létre más rendszergazdai szerepköröket, és nem állíthatja át más rendszergazdák jelszavát.

A Microsoft Intune-előfizetés létrehozásához használt fiók alapértelmezés szerint egy globális rendszergazdai fiók. A napi felügyeleti feladatok elvégzéséhez nem ajánlott globális rendszergazdai jogosultságokat használni. A rendszergazdának nincs szüksége Intune-licencre az Intune felügyeleti konzoljának eléréséhez. További információkért lásd az Azure AD-bérlőről szóló részt a következő cikkben: [Mi az az Azure AD címtár?](http://technet.microsoft.com/library/jj573650.aspx).

Az Office 365-portál eléréséhez a fióknak **Bejelentkezés engedélyezve** beállítással kell rendelkeznie. Az Intune-portálon a **Profil** alatt adjam meg a **Bejelentkezés blokkolva** értékeként a **Nem** beállítást. Ez az állapot nem ugyanaz, mint amikor a fióknak licence van az előfizetéshez. Alapértelmezés szerint az összes felhasználói fiók **Engedélyezett** állapotú. A rendszergazdai engedélyekkel nem rendelkező felhasználók az Office 365-portál segítségével állíthatják vissza az Intune-jelszavukat.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz
A címtár-szinkronizálás konfigurálásával importálhatja a helyi Active Directoryban lévő felhasználói fiókokat a Microsoft Azure Active Directory (Azure AD) szolgáltatásba (ide tartoznak az Intune-felhasználók is). A helyi Active Directory szolgáltatás Azure Active Directory-alapú szolgáltatásokkal való összekapcsolásával jóval egyszerűbbé válik az identitásfelügyelet. Az egyszeri bejelentkezési funkciók konfigurálásával ismerőssé és könnyebbé teheti a felhasználók számára a hitelesítést. Ha egy [Azure AD-bérlőt](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) egyszerre több szolgáltatáshoz is társít, a korábban már szinkronizált felhasználói fiókok is elérhetővé válnak az összes felhőalapú szolgáltatásban.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Helyi felhasználók szinkronizálása az Azure AD szolgáltatással
A felhasználói fiókoknak az Azure AD-val való szinkronizálásához kizárólag az [Azure AD Connect varázslóra](https://www.microsoft.com/download/details.aspx?id=47594) van szüksége. Az Azure AD Connect varázsló egyszerűsített és irányított kezelőfelülettel segíti a helyszíni identitási infrastruktúrának a felhőhöz történő csatlakoztatását.  Válassza ki a topológiát és a vonatkozó igényeket (egyetlen vagy több címtár, jelszavak szinkronizálása vagy összevonás). A varázsló telepíti és konfigurálja a kapcsolat működéséhez szükséges az összes összetevőt. Ilyen összetevők többek között: a szinkronizálási szolgáltatások, az Active Directory összevonási szolgáltatások (AD FS) és az Azure AD PowerShell modul.

> [!TIP]
> Az Azure AD Connect a korábban Dirsync és Azure AD Sync néven kibocsátott eszközök valamennyi funkcióját tartalmazza. További tájékoztatás a [Címtár-integrációra](http://technet.microsoft.com/library/jj573653.aspx) vonatkozóan. További tudnivalók a helyi címtárban lévő felhasználói fiókok Azure AD-vel való szinkronizálásáról: [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx) (Az Active Directory és az Azure AD közötti hasonlóságok).
