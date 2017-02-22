---
title: "Felhasználók hozzáadása és engedélyek megadása | Microsoft Docs"
description: "A helyszíni felhasználók szinkronizálása az Azure AD-vel és rendszergazdai jogosultság megadása az Intune-előfizetésnek"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: b1f16df329c01aeb45885f3981e2d9d7ef854e8b


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Felhasználók hozzáadása és rendszergazdai engedély biztosítása az Intune-hoz

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör arról tájékoztatja a rendszergazdákat, hogy miképpen vehetnek fel felhasználókat az Intune-ba, és milyen felügyeleti engedélyek érhetők el az Intune szolgáltatásban.

A rendszergazdák jogosultak közvetlenül felvenni az új felhasználókat, vagy szinkronizálni a felhasználókat a helyszíni Active Directoryból. Ha felvették a felhasználókat a szolgáltatásba, regisztrálhatják az eszközeiket, és elérhetik a vállalati erőforrásokat. A felhasználóknak további engedélyeket is biztosíthat, például a következőket: *bérlői rendszergazda*, *szolgáltatásadminisztrátor* vagy *készülékregisztráció-kezelő*.

Ez a témakör a következőkben nyújt segítséget:

- [Felhasználók hozzáadása az Intune-hoz](#add-users-to-intune)
- [További Intune-engedélyek biztosítása](#grant-intune-permissions), többek között:
  - [Bérlői rendszergazda](#tenant-administrator)
  - [Szolgáltatásadminisztrátor ](#service-administrator)
  - [Készülékregisztráció-kezelő](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Felhasználók hozzáadása az Intune-hoz
Manuálisan is hozzáadhat felhasználókat az Intune-előfizetéshez az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854), de ezeket a felhasználókat a rendszer nem látja el automatikusan Intune-licenccel. Ehelyett egy későbbi időpontban egy Intune bérlői rendszergazdának az Office 365 portálról kell egy licencet a felhasználóhoz rendelnie a felhasználói fiók szerkesztésével. További tájékoztatást a [Felhasználók felvétele egyenként és tömegesen az Office 365-be](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) című cikkben olvashat.

### <a name="sync-active-directory-and-add-users-to-intune"></a>Az Active Directory szinkronizálása és felhasználók hozzáadása az Intune szolgáltatáshoz
A címtár-szinkronizálás konfigurálásával importálhatja a helyi Active Directoryban lévő felhasználói fiókokat a Microsoft Azure Active Directory (Azure AD) szolgáltatásba (ide tartoznak az Intune-felhasználók is). A helyi Active Directory szolgáltatás Azure Active Directory-alapú szolgáltatásokkal való összekapcsolásával jóval egyszerűbbé válik az identitásfelügyelet. Az egyszeri bejelentkezési funkciók konfigurálásával ismerőssé és könnyebbé teheti a felhasználók számára a hitelesítést. Ha egy [Azure AD-bérlőt](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) egyszerre több szolgáltatáshoz is társít, a korábban már szinkronizált felhasználói fiókok is elérhetővé válnak az összes felhőalapú szolgáltatásban.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Helyi felhasználók szinkronizálása az Azure AD szolgáltatással
A felhasználói fiókoknak az Azure AD-val való szinkronizálásához kizárólag az [Azure AD Connect varázslóra](https://www.microsoft.com/download/details.aspx?id=47594) van szüksége. Az Azure AD Connect varázsló egyszerűsített és irányított kezelőfelülettel segíti a helyszíni identitási infrastruktúrának a felhőhöz történő csatlakoztatását.  Válassza ki a topológiát és a vonatkozó igényeket (egyetlen vagy többszörös címtárak, jelszavak szinkronizálása vagy összevonása), a varázsló pedig a kapcsolat létrehozásához és működéséhez szükséges valamennyi összetevő telepítését és konfigurálását elvégzi. Ilyen összetevők többek között: a szinkronizálási szolgáltatások, az Active Directory összevonási szolgáltatások (AD FS) és az Azure AD PowerShell modul.

> [!TIP]
> Az Azure AD Connect a korábban Dirsync és Azure AD Sync néven kibocsátott eszközök valamennyi funkcióját tartalmazza. További tájékoztatás a [Címtár-integrációra](http://technet.microsoft.com/library/jj573653.aspx) vonatkozóan. További tudnivalók a helyi címtárban lévő felhasználói fiókok Azure AD-vel való szinkronizálásának előnyeiről: [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx) (Az Active Directory és az Azure AD közötti hasonlóságok).

## <a name="grant-intune-permissions"></a>Intune-engedélyek megadása

Javasoljuk, hogy a felhasználók Intune-előfizetéshez történő hozzáadása után biztosítson néhány felhasználói fiók számára rendszergazdai engedélyt. Háromféle, az Intune felügyeletét lehetővé tevő Intune-engedély érhető el:
-   **Bérlői rendszergazda**: Ezt a rendszergazdatípust az Office 365-portálon állíthatja be az előfizetés kezelése céljából, ideértve a számlázást, a felhőalapú tárolást, illetve azoknak a felhasználóknak a felügyeletét, akik számára engedélyezte az Intune használatát.
-   **Szolgáltatás-rendszergazda**: Ezt a rendszergazdatípust a Microsoft Intune felügyeleti konzoljával állíthatja be a napi rutinfeladatok elvégzése céljából, ideértve az eszközök és a számítógépek felügyeletét, a szabályzatok érvénybe léptetését, az alkalmazások telepítését, illetve a jelentéskészítést.
-   **Készülékregisztráció-kezelő**: Ezt a rendszergazdatípust a Microsoft Intune felügyeleti konzoljával állíthatja be a napi rutinfeladatok elvégzése céljából, ideértve az eszközök és a számítógépek felügyeletét, a szabályzatok érvénybe léptetését, az alkalmazások telepítését, illetve a jelentéskészítést.


### <a name="tenant-administrator"></a>Bérlői rendszergazda


A bérlői rendszergazdák egy rendszergazdai szerepkörrel rendelkeznek, amely meghatározza az adott felhasználó felügyeleti hatókörét és az általa kezelhető feladatokat. A Microsoft különböző felhőszolgáltatásai ugyanazokat a rendszergazdai szerepköröket használják, azonban előfordulhat, hogy egyes szolgáltatások nem támogatnak bizonyos szerepköröket. Az Intune az alábbi szerepköröket használja:
- **Globális rendszergazda**: Az Intune összes rendszergazdai funkciójához hozzáfér. Alapértelmezés szerint a rendszer az Intune-ba regisztráló felhasználót állítja be globális rendszergazdának. Kizárólag a globális rendszergazdák jogosultak a többi rendszergazdai szerepkör kiosztására. A szervezetben egynél több globális rendszergazda is működhet. Javasoljuk, hogy a kockázat minimalizálása érdekében ne adja meg túl sok személynek ezt a szerepkört.
- **Számlázási adminisztrátor**: Lebonyolítja a vásárlásokat, kezeli az előfizetéseket és a támogatási jegyeket, valamint figyeli a szolgáltatás állapotát.
- **Jelszókezelő**: Átállítja a jelszavakat, kezeli a szolgáltatáskéréseket, illetve figyeli a szolgáltatás állapotát. A jelszókezelők kizárólag a felhasználók jelszavának átállítására jogosultak.
- **Szolgáltatástámogatási rendszergazda**: Benyújtja a támogatási kéréseket a Microsoftnak, és jogosult megtekinteni a szolgáltatás irányítópultját és üzenetközpontját. Ezekhez kizárólag „csak olvasási” hozzáféréssel rendelkeznek, csak a támogatási jegyeket nyithatják meg és olvashatják el.
- **Felhasználókezelő rendszergazda**: Visszaállítja a jelszavakat, figyeli a szolgáltatás állapotát, hozzáadja és törli a felhasználói fiókokat, valamint kezeli a szolgáltatáskéréseket. A felhasználókezelő rendszergazda nem törölheti a globális rendszergazdákat, nem hozhat létre más rendszergazdai szerepköröket, és nem állíthatja át a számlázási, a globális és a szolgáltatástámogatási rendszergazdák jelszavát.

A Microsoft Intune-előfizetés létrehozásához használt fiók alapértelmezés szerint egy bérlői rendszergazda, aki megkapja a globális rendszergazdai szerepkört. A bérlő rendszergazdák az Intune felügyeleti konzolja segítségével kezelhetik az Intune-előfizetést, valamint kijelölhetik a bérlő rendszergazdákat az [Office 365-portál](http://go.microsoft.com/fwlink/p/?LinkId=698854) felületén. A globális rendszergazdai szerepkörrel rendelkező bérlői rendszergazdákkal hozzáférhet a portálhoz, és kijelölheti az első szolgáltatás-rendszergazdát. A napi felügyeleti feladatok elvégzéséhez nem ajánlott bérlői rendszergazdát alkalmazni. A bérlői rendszergazdának nincs szüksége Intune-licencre az Intune felügyeleti konzoljához való hozzáféréshez. A bérlői rendszergazda a Microsoft felhőszolgáltatásaiban általánosan használt fogalom. Amikor előfizet az Intune-ra, az Ön szolgáltatása az Azure AD bérlője lesz. További információkért lásd az Azure AD-bérlőről szóló részt a következő cikkben: [Mi az az Azure AD címtár?](http://technet.microsoft.com/library/jj573650.aspx).

Bérlői rendszergazdaként az [Office 365-portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854) kezelheti előfizetését, beleértve a következő feladatokat, ha a rendszergazdai szerepköre lehetővé teszi őket:

- A felhasználói fiókok kezelése, illetve a helyszíni Active Directoryból való címtár-szinkronizálás beállítása
- A biztonsági csoportnak nevezett felhasználói csoportok kezelése
- Felhasználói licencek kiosztása az Intune-hoz
- Az előfizetéshez tartozó tartománynév beállítása, amelynek segítségével a felhasználók bejelentkezhetnek (például contoso.com)
- A számlázás és a vásárlások kezelése, ideértve a licenceket és a felhőtárhelyet is
- Az Intune szolgáltatás állapotának megtekintésére szolgáló hivatkozások használata

Az Office 365 portál eléréséhez a fióknak **Engedélyezett** bejelentkezési állapotúnak kell lennie. Ez az állapot nem ugyanaz, mint amikor a fióknak licence van az előfizetéshez. Alapértelmezés szerint az összes felhasználói fiók **Engedélyezett** állapotú. A rendszergazdai engedélyekkel nem rendelkező felhasználók az Office 365-portál segítségével állíthatják vissza az Intune-jelszavukat.

### <a name="service-administrator"></a>Szolgáltatás-rendszergazda

Az Intune alapértelmezés szerint nem jelöl ki szolgáltatás-rendszergazdát. Ehelyett egy globális rendszergazdai szerepkörrel rendelkező bérlői rendszergazda használatával kell kijelölnie az első szolgáltatás-rendszergazdát az előfizetéshez. A szolgáltatás-rendszergazdák az [Intune felügyeleti konzoljában](https://manage.microsoft.com/) végezhetik el az Intune-hoz kapcsolódó napi rutinfeladatokat. A szolgáltatás-rendszergazdákat a felügyeleti konzolon lehet kijelölni. A szolgáltatás-rendszergazdáknak rendelkezniük kell Intune-licenccel ahhoz, hogy hozzáférjenek a felügyeleti konzolhoz.

A szolgáltatás-rendszergazdák a következő jogosultságok egyikével rendelkeznek:
- **Teljes hozzáférés**: Az Intune felügyeleti konzoljának összes menüpontját korlátozás nélkül elérik és használhatják, illetve jogosultak más szolgáltatás-rendszergazdák beállítására, illetve felügyeletére.
- **Olvasási hozzáférés**: Az Intune felügyeleti konzoljának összes menüpontját megtekinthetik, de nem módosíthatják az adatokat. Jogosultak jelentések készítésére.
- **Segélyszolgálat - Csoportok csomópont**: Csak a segélyszolgálati forgatókönyvekhez tartozó feladatok elvégzését engedélyezi a szolgáltatás-rendszergazdának. Lásd: [Az Intune-konzolnézetek testre szabása a rendszergazdai szerepköröknek megfelelően](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).

A szolgáltatás-rendszergazdák ezen a portálon végezhetik el a napi rutinfeladatokat, beleértve az alábbiakat:

- Számítógépekre és mobileszközökre vonatkozó szabályzatok létrehozása, illetve felügyelete
- Szoftverfrissítések és alkalmazások feltöltése és telepítése
- A számítógépeken futó Endpoint Protection szolgáltatás kezelése
- Eszközállapot megtekintése és jelentések futtatása

### <a name="device-enrollment-managers"></a>Eszközregisztráció-kezelők

A készülékregisztráció-kezelők normál felhasználói fiókok, amelyeknek további felhasználó nélküli eszközök regisztrálására adtak engedélyt. Alapértelmezés szerint minden Intune-felhasználó legfeljebb tizenöt eszközt regisztrálhat. A felhasználóknak a rendszergazdák megadhatják a készülékregisztráció-kezelői engedélyt. Ezek a fiókok aztán a korlátozásnál nagyobb számú vállalati eszközt is regisztrálhatnak a szolgáltatásba. Ez akkor hasznos, ha előfordulhat, hogy az eszközöket csak ideiglenesen rendelik hozzá a felhasználókhoz, vagy kioszkmódban működnek, amelyben a felhasználók eszközökhöz való társítása nem szükséges. További információk: [Készülékregisztráció-kezelő](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Tartományi beállítások**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune-licencek kezelése** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Feb17_HO3-->


