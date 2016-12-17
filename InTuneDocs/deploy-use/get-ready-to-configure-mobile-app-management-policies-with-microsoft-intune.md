---
title: "A mobilalkalmazás-felügyeleti szabályzatok előfeltételei | Microsoft Intune"
description: "Ez a témakör ismerteti a mobilalkalmazás-felügyeleti szabályzatok létrehozásához szükséges, felhasználókra vonatkozó előfeltételeket és beállításokat."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: ac820146d81fb121a60f7029f6a52a0056d6ab0a


---

# <a name="get-ready-to-configure-mobile-app-management-policies-on-the-azure-portal"></a>Felkészülés a mobilalkalmazás-felügyeleti szabályzatok konfigurálására az Azure Portalon
Ebből a témakörből megismerheti, hogy milyen előfeltételek megléte és lépések elvégzése szükséges, **mielőtt** mobilalkalmazás-felügyeleti (MAM) szabályokat hozhat létre az Azure Portalon.

Ha kíváncsi rá, hogy az Intune MAM-szabályzatai hogyan segítenek a vállalati adatok védelmében, olvassa el a [Protect apps and data using mobile app management policies](protect-apps-and-data-with-microsoft-intune.md) (Alkalmazások és adatok védelme mobilalkalmazás-felügyeleti szabályzatokkal) című cikket.

## <a name="what-is-the-azure-portal"></a>Mi az az Azure Portal?

A mobilalkalmazás-felügyeleti szabályzatok létrehozására szolgáló új felügyeleti konzol az Azure-portál. A portál a következő MAM-forgatókönyveket teszi lehetővé:
- Az Intune-ban regisztrált eszközök
- Más mobileszköz-felügyeleti (MDM) megoldások által felügyelt eszközök
- MDM-megoldással (BYOD) nem kezelt eszközök

Jelenleg az **Intune felügyeleti konzoljában** és az **Azure Portalon** is beállíthat MAM-szabályzatokat.  Ügyeljen a következőkre:

* Az **Azure Portalon** létrehozott szabályzatok az előzőekben felsorolt **összes MAM-forgatókönyv** esetében támogatást élveznek. Az **Intune felügyeleti konzolja** csak **az Intune-ban regisztrált, és az Intune által felügyelt eszközökre vonatkozóan** teszi lehetővé szabályzatok létrehozását.

* Elképzelhető, hogy az Intune felügyeleti konzoljában nem érhető el a MAM-szabályzatokkal kapcsolatos összes lehetőség, mivel az **új beállítások** esetenként csak az **Azure Portalba** kerülnek be.

* Ha az Intune felügyeleti konzoljában és az Azure Portalon **egyaránt** létrehoz MAM-szabályzatokat, a rendszer az **Azure Portalon érvényes szabályzatot alkalmazza az alkalmazásokra, illetve telepíti a felhasználók számára**.
    * Az Intune felügyeleti konzolon létrehozott MAM-szabályzatokat nem lehet az Azure portálon importálni.  A MAM-szabályzatokat az Azure portálon kell újból létrehozni.


* Egyes **alkalmazásfelügyeleti funkciók** (például az alkalmazások központi telepítése, illetve az alkalmazáskonfigurációs szabályzatok életbe léptetése) csak az **Intune felügyeleti konzoljában** érhetők el.


Ha most ismerkedik az Azure Portallal, érdemes elolvasni az [Azure Portal a Microsoft Intune mobilalkalmazás-felügyeleti szabályzatainak kezeléséhez](azure-portal-for-microsoft-intune-mam-policies.md) című témakört, amelyből megismerheti a portál használatának alapjait.

További útmutatás a MAM-szabályzatok Intune segítségével történő létrehozásáról: [Mobilalkalmazás-felügyeleti szabályzatok konfigurálása és telepítése a Microsoft Intune-konzolban](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Támogatott platformok
- iOS 8.1-es vagy újabb verzió
- Android 4 vagy újabb verzió

>[!NOTE]
>A Windows-eszközök nem támogatják ezeket a mobilalkalmazás-felügyeleti szabályzatokat. A Windows 10-eszközöket azonban regisztrálhatja az Intune-ba, amelyben lehetőség van a hasonló funkciókat biztosító Windows Információvédelem használatára. További információk: [Vállalati adatok védelme a Windows információvédelemmel (WIP)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  <a name="supported-apps"></a>Támogatott alkalmazások
* **Microsoft-alkalmazások:** Ezeknek az alkalmazásoknak a beépített része az Intune App SDK, és nincs szükség további intézkedésre a MAM-szabályzatok használata előtt.
A támogatott Microsoft-alkalmazások teljes listájának megtekintéséhez keresse fel a [Microsoft Intune mobilalkalmazás-galériát](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) a Microsoft Intune alkalmazáspartnerek oldalán. Ha szeretné megtekinteni a támogatott forgatókönyveket és platformokat, illetve, hogy az alkalmazás támogatja-e a többszörös identitásokat, válassza ki az adott alkalmazást.

* **A szervezete üzletági alkalmazásai:** Ezeket az alkalmazásokat először elő kell készíteni az Intune App SDK használatára, és csak ezt követően alkalmazhatja a MAM-szabályzatokat.

  * Az Intune által felügyelt eszközök esetében lásd: [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

  * A nem felügyelt eszközök (például az alkalmazottak saját tulajdonú eszközei) vagy a más mobileszköz-felügyeleti megoldások által felügyelt eszközök esetén lásd: [Üzletági alkalmazások és adatok védelme az Intune-ban nem regisztrált eszközökön](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Előfeltételek

-   **Microsoft Intune-előfizetés**. A felhasználóknak [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-licencekre van szükségek a MAM-szabályzatokkal rendelkező alkalmazások lekéréséhez.
Már van [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-előfizetése, ha jelenleg is az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-t használja az eszközök kezeléséhez. Akkor is rendelkezik [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-előfizetéssel, ha Nagyvállalati mobilitási csomag (EMS) licencet vásárolt. Ha a mobilalkalmazás-felügyeleti funkciók miatt próbálná ki az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-t, érdemes létrehozni egy próbafiókot a [Microsoft Intune webhelyen](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Az Office portál **Számlázás** oldalán ellenőrizheti, hagy rendelkezik-e [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-előfizetéssel.  Ha van előfizetése, az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] állapota az előfizetések alatt **Aktív**.

-   **Office 365-előfizetés**, amely a következőkhöz szükséges:

  - MAM-szabályzatok alkalmazása többszörös identitások támogatását használó alkalmazásokhoz.

  - SharePoint Online- és Exchange Online munkahelyi fiókok létrehozása. A helyi Exchange-et és a helyi SharePointot nem támogatjuk.

-   **A Skype Vállalati online verzió beállítása modern hitelesítéshez**. További információkért lásd [Enable modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (A modern hitelesítés engedélyezése) című cikket.


- Microsoft Azure Active Directory (Azure AD) a felhasználók létrehozásához. Az Azure AD akkor hitelesíti a felhasználókat, amikor azok végfelhasználóként elindítják az alkalmazást, és megadják a munkahelyi hitelesítő adataikat.

    > [!NOTE]
    > Be kell állítani a felhasználói csoportokat az Azure AD-ben. Intune felhasználói csoportokat nem használhat a MAM-szabályzatoknak az Azure Portalon történő életbe léptetésére.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Felhasználók létrehozása és Microsoft Intune-licencek kiosztása

1.  Jelentkezzen be az   [Office portálra](http://portal.office.com) a rendszergazdai hitelesítő adataival.

2.  Vegye fel a felhasználókat az [Útmutató az Intune próbaverziójához](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) című cikk **az Intune 30 napos próbaverziójának használatba vételének lépéseit ismertető részének** megfelelően, majd ossza ki az Intune-licenceket. A felhasználók számára a **Globális rendszergazdai szerepkör** hozzárendelésével biztosíthat hozzáférést az Office-, az Azure AD- és az Azure-portálhoz.

5.  A MAM-szabályzatok az Azure Active Directorybeli felhasználói csoportokra vonatkoznak. A MAM-szabályzatokhoz használható felhasználói csoport létrehozásához kövesse a [Csoportok létrehozása a próba-előfizetés felhasználóinak és eszközeinek rendszerezésére](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) című témakör **Felhasználói csoport létrehozása** című fejezetében leírtakat.

### <a name="assign-roles-to-non-global-admin-users"></a>Szerepkörök kiosztása a nem globális rendszergazdáknak

A globális rendszergazdák hozzáférhetnek az [Azure-portálhoz](https://portal.azure.com).  Ha a nem globális rendszergazda felhasználók számára is engedélyezni szeretné a szabályzatok konfigurálását, valamint a többi mobilalkalmazás-felügyeleti feladat elvégzését, rendelje hozzá a kívánt felhasználókhoz a közreműködői szerepkört. Részletes utasításokért lásd: [Use role assignments to manage access to your Azure subscription resources](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/) (Az Azure-előfizetéshez tartozó erőforrások elérésének kezelése a szerepkörök hozzárendelésével).



Az alábbi táblázat a rendszergazdai jogosultságú felhasználókhoz hozzárendelhető szerepköröket és engedélyeket sorolja fel.



|||
|--|----|
|**Szerepkör**|**Engedélyek**|
|Globális rendszergazda (Office 365 portál)|Hozzáférés az Office 365 portálhoz és az Azure AD portálhoz.<br /><br />Hozzáférés az Azure-portálhoz (mobilalkalmazás- és szerepkör-felügyeleti feladatokat is végrehajthat).|
|Tulajdonosi (Azure portál)|Hozzáférés az Azure-portálhoz (mobilalkalmazás- és szerepkör-felügyeleti feladatokat is végrehajthat).|
|Közreműködő (Azure portál)|Hozzáférés az Azure portálhoz (csak mobilalkalmazás-felügyeleti feladatokat hajthat végre).|




## <a name="next-steps"></a>További lépések
[Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


