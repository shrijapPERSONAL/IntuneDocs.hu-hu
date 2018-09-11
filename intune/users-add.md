---
title: Felhasználók hozzáadása és engedélyek megadása
titlesuffix: Microsoft Intune
description: A helyszíni felhasználók szinkronizálása az Azure AD-vel és rendszergazdai jogosultság megadása az Intune-előfizetéshez.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-classic; get-started
ms.openlocfilehash: 643f118414862e1644e6bb15d56a8e903d958d0c
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44254173"
---
# <a name="add-users-and-grant-administrative-permission-to-intune"></a>Felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-hoz

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

A rendszergazdák jogosultak közvetlenül felvenni az új felhasználókat, vagy szinkronizálni a felhasználókat a helyszíni Active Directoryból. Ha felvették a felhasználókat a szolgáltatásba, regisztrálhatják az eszközeiket, és elérhetik a vállalati erőforrásokat. További jogosultságokat is adhat a felhasználóknak, többek között *globális rendszergazdai* és *szolgáltatásadminisztrátori* engedélyeket.

## <a name="add-users-to-intune"></a>Felhasználók hozzáadása az Intune-hoz
Az Intune-előfizetéshez manuálisan is hozzáadhat felhasználókat az [Office 365-portálon](https://www.office.com/signin) vagy az [Azure Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) webhelyen. A rendszergazda módosíthatja a felhasználói fiókokat az Intune-licencek hozzárendeléséhez. A licenceket az Office 365-portálról vagy az Intune Azure-portálról oszthatja ki. Az Office 365-portál használatával kapcsolatos további tudnivalókért lásd: [Felhasználók felvétele egyenként és tömegesen az Office 365-portálra](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Intune-felhasználók felvétele az Office 365 Felügyeleti központban
1. Jelentkezzen be az [Office 365-portálon](https://www.office.com/signin) egy globális rendszergazdai vagy felhasználókezelő rendszergazdai fiókkal.
2. Az Office 365 menüjében válassza a **Rendszergazda** elemet.
3. A Felügyeleti központban válassza a **Felhasználó hozzáadása** elemet.

   ![Képernyőkép a Felhasználó hozzáadása szakaszról](media/office-add-user.png)

4. Adja meg a következő felhasználói adatokat:
   - **Utónév**
   - **Vezetéknév**
   - **Megjelenítendő név**
   - **Felhasználói név** – A szolgáltatás eléréséhez használt és az Azure Active Directoryban tárolt egyszerű felhasználónév (UPN)
   - **Hely**
   - **Kapcsolattartási adatok** (nem kötelező)
   - **Jelszó** –automatikus létrehozás vagy adja meg

     ![Képernyőkép az új felhasználó szakaszról](media/office-add-user-details.png)

5. Rendeljen hozzá egy Intune-licencet. Válassza a **Terméklicencek** lehetőséget, és válassza ki a terméklicencet. Szükség van egy Intune-ra is vonatkozó licencre.
6. Válassza a **Hozzáadás** gombot az új felhasználó létrehozásához.

### <a name="add-intune-users-in-the-azure-portal"></a>Intune-felhasználók felvétele az Azure Portalon
1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com), majd lépjen a **Minden szolgáltatás** > **Monitoring + Management** > **Intune** elemre. *Kereshet erőforrásokat* is az **Intune-hoz**.
2. Válassza a **Felhasználók** > **Minden felhasználó** lehetőséget.
3. A Felügyeleti központban válassza az **Új felhasználó** elemet.
   ![Képernyőkép az Új felhasználó hozzáadása elemről](media/intune-add-user.png)
4. Adja meg a következő felhasználói adatokat:
   - **Név**
   - **Felhasználónév** – Az új név az Azure Active Directory portálon ![Képernyőkép a név és a felhasználónév hozzáadásáról](media/intune-add-user-info.png) Válassza az **OK** gombot a folytatáshoz.
5. Szükség esetén a következő felhasználói tulajdonságokat is megadhatja:
   - **Profil** – Munkahelyi adatok, többek között a **Beosztás megnevezése** és a **Részleg**
   -  **Csoportok** – Válasszon a felhasználó által felehető csoportokat
   - **Címtár szerepkör** – Rendszergazdai jogosultságok adása a felhasználónak (többek között szolgáltatásadminisztrátor szerepkör az Intune-hoz).

   Az új felhasználó Intune-hoz adásához válassza a **Létrehozás** gombot.
6. Válassza a **Profil** lehetőséget, majd válasszon egy **Felhasználási helyet** az új felhasználónak. A felhasználási hely megadása szükséges, mielőtt az új felhasználóhoz hozzárendelhetne egy Intune-licencet. A folytatáshoz válassza a **Mentés** gombot.
    ![A felhasználási hely képernyőképe](media/intune-add-user-loc.png)
7. Intune-licenc felhasználóhoz rendeléséhez válassza a **Licencek** lehetőséget, majd a **Hozzárendelés** elemet. Az eszközök regisztrálásához és a vállalati erőforrások eléréséhez Intune-licenc szükséges. Válassza a **Termékek** lehetőséget, válassza ki a licenctípust, aztán a **Kiválasztás** lehetőséget, majd a **Hozzárendelés** elemet.

## <a name="grant-admin-permissions"></a>Rendszergazdai jogosultságok megadása

Javasoljuk, hogy a felhasználók Intune-előfizetéshez történő hozzáadása után biztosítson néhány felhasználó számára rendszergazdai engedélyt.  Rendszergazdai jogosultságokat az alábbi lépéseket követve adhat:

### <a name="give-admin-permissions-in-office-365"></a>Rendszergazdai jogosultságok biztosítása az Office 365-ben
1. Jelentkezzen be az [Office 365-portálra](https://www.office.com/signin) egy globális rendszergazdai fiókkal.
2. Az Office 365 menüjében válassza a **Rendszergazda** elemet.
3. A Felügyeleti központban válassza az **Aktív felhasználók** lehetőséget, majd válassza ki azt a felhasználót, akinek rendszergazdai jogosultságot szeretne adni.

4. A **Szerepkörök** oszlopban válassza a **Szerkesztés** lehetőséget.

    ![Képernyőkép a Rendszergazdai felhasználóról](./media/office-assign-roles-open.png)

5. Az elérhető szerepkörök listájából válassza ki a hozzárendelni kívánt rendszergazdai jogosultságot.
![Képernyőkép a szerepkörök hozzárendeléséről](./media/office-assign-roles.png)
6. Válassza a **Mentés** elemet.

### <a name="give-admin-permissions-in-the-azure-portal"></a>Rendszergazdai jogosultságok megadása az Azure Portalon
1. Jelentkezzen be az [Azure Portalra](https://www.office.com/signin) egy globális rendszergazdai fiókkal.
2. Az Azure Portalon válassza a **Felhasználó** lehetőséget, majd válassza ki azt a felhasználót, akinek rendszergazdai jogosultságot szeretne adni.
3. Válassza a **Címtárbeli szerepkör** elemet, majd pedig a kívánt jogosultságot.
  ![Képernyőkép a Címtárszerepkörről](./media/add-intune-directory-role.png)
4. Válassza a **Mentés** elemet.

### <a name="types-of-administrators"></a>Rendszergazdatípusok

Rendeljen hozzá egy vagy több rendszergazdai jogosultságot a felhasználókhoz. Ezek az engedélyek definiálják a felügyeleti hatókört a felhasználók és az általuk kezelhető feladatokra vonatkozóan. A Microsoft különböző felhőszolgáltatásai ugyanazokat a rendszergazdai jogosultságokat használják, azonban előfordulhat, hogy egyes szolgáltatások nem támogatnak bizonyos jogosultságokat. Mind az Azure Portalon, mind pedig az Office 365-portálon megtalálható az Intune által nem használt korlátozott rendszergazdai szerepkörök listája. Az Intune-beli rendszergazdai jogosultságok az alábbiak lehetnek:

- **Globális rendszergazda** – (Office 365 és Intune) Az Intune összes rendszergazdai funkciójához hozzáfér. Alapértelmezés szerint a rendszer az Intune-ba regisztráló felhasználót állítja be globális rendszergazdának. Kizárólag a globális rendszergazdák jogosultak a többi rendszergazdai szerepkör kiosztására. A szervezetben egynél több globális rendszergazda is működhet. Javasoljuk, hogy a kockázat minimalizálása érdekében ne adja meg túl sok személynek ezt a szerepkört.
- **Jelszókezelő** – (Office 365 és Intune) Átállítja a jelszavakat, kezeli a szolgáltatáskéréseket, illetve figyeli a szolgáltatás állapotát. A jelszókezelők kizárólag a felhasználók jelszavának átállítására jogosultak.
- **Szolgáltatásadminisztrátor** – (Office 365 és Intune) Benyújtja a támogatási kéréseket a Microsoftnak, és jogosult megtekinteni a szolgáltatás irányítópultját és üzenetközpontját. Ezekhez kizárólag „csak olvasási” hozzáféréssel rendelkeznek, csak a támogatási jegyeket nyithatják meg és olvashatják el.
- **Számlázási adminisztrátor** – (Office 365 és Intune) Lebonyolítja a vásárlásokat, kezeli az előfizetéseket és a támogatási jegyeket, valamint figyeli a szolgáltatás állapotát.
- **Felhasználókezelő rendszergazda** – (Office 365 és Intune) Visszaállítja a jelszavakat, figyeli a szolgáltatás állapotát, hozzáadja és törli a felhasználói fiókokat, valamint kezeli a szolgáltatáskéréseket. A felhasználókezelő rendszergazda nem törölheti a globális rendszergazdákat, nem hozhat létre más rendszergazdai szerepköröket, és nem állíthatja át más rendszergazdák jelszavát.
- **Intune-szolgáltatásadminisztrátor** – A **címtárbeli szerepkör** biztosítására vonatkozó jogosultságot kivéve az Intune-beli globális rendszergazdai jogosultságok mindegyikével rendelkezik.

A Microsoft Intune-előfizetés létrehozásához használt fiók globális rendszergazdai fiók. A napi felügyeleti feladatok elvégzéséhez nem ajánlott globális rendszergazdai jogosultságokat használni. Noha a rendszergazda licenc nélkül is elérheti az Intune-t az Azure Portalon, bizonyos felügyeleti feladatokat, például az Exchange szolgáltatás összekötőjének beállítását csak Intune-licenc birtokában végezhet el.

Az Office 365-portál eléréséhez a fióknak **Bejelentkezés engedélyezve** beállítással kell rendelkeznie. Az Azure Portalon a **Profil** szakaszban a **Nem** értékre állítsa a **Bejelentkezés blokkolása** beállítást. Ez az állapot nem ugyanaz, mint amikor a fióknak licence van az előfizetéshez. Alapértelmezés szerint az összes felhasználói fiók **Engedélyezett** állapotú. A rendszergazdai engedélyekkel nem rendelkező felhasználók az Office 365-portál segítségével állíthatják vissza az Intune-jelszavukat.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz
A címtár-szinkronizálás konfigurálásával importálhatja a helyi Active Directoryban lévő felhasználói fiókokat a Microsoft Azure Active Directory (Azure AD) szolgáltatásba (ide tartoznak az Intune-felhasználók is). A helyi Active Directory szolgáltatás Azure Active Directory-alapú szolgáltatásokkal való összekapcsolásával jóval egyszerűbbé válik az identitásfelügyelet. Az egyszeri bejelentkezési funkciók konfigurálásával ismerőssé és könnyebbé teheti a felhasználók számára a hitelesítést. Ha egy [Azure AD-bérlőt](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) egyszerre több szolgáltatáshoz is társít, a korábban már szinkronizált felhasználói fiókok is elérhetővé válnak az összes felhőalapú szolgáltatásban.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Helyi felhasználók szinkronizálása az Azure AD szolgáltatással
A felhasználói fiókoknak az Azure AD-val való szinkronizálásához kizárólag az [Azure AD Connect varázslóra](https://www.microsoft.com/download/details.aspx?id=47594) van szüksége. Az Azure AD Connect varázsló egyszerűsített és irányított kezelőfelülettel segíti a helyszíni identitási infrastruktúrának a felhőhöz történő csatlakoztatását. Válassza ki a topológiát és a vonatkozó igényeket (egyetlen vagy több címtár, jelszókivonatok szinkronizálása, átmenő hitelesítés vagy összevonás). A varázsló telepíti és konfigurálja a kapcsolat működéséhez szükséges az összes összetevőt. Ilyen összetevők többek között: a szinkronizálási szolgáltatások, az Active Directory összevonási szolgáltatások (AD FS) és az Azure AD PowerShell modul.

> [!TIP]
> Az Azure AD Connect a korábban Dirsync és Azure AD Sync néven kibocsátott eszközök valamennyi funkcióját tartalmazza. További tájékoztatás a [Címtár-integrációra](http://technet.microsoft.com/library/jj573653.aspx) vonatkozóan. További tudnivalók a helyi címtárban lévő felhasználói fiókok Azure AD-vel való szinkronizálásáról: [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx) (Az Active Directory és az Azure AD közötti hasonlóságok).
