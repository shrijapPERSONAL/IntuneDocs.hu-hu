---
title: "A mobilalkalmazás-felügyeleti szabályzatok előfeltételei | Microsoft Docs"
description: "Ez a témakör ismerteti a mobilalkalmazás-felügyeleti szabályzatok létrehozásához szükséges, felhasználókra vonatkozó előfeltételeket és beállításokat."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a85b9f603e022b3296cb16754effd06087074a72
ms.openlocfilehash: 9759c1331a3fb5308e1dbc53564059618a8ef45c
ms.lasthandoff: 04/01/2017


---

# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a>Felkészülés az alkalmazásvédelmi szabályzatoknak az Azure Portalon történő konfigurálására

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ebből a témakörből megismerheti, hogy milyen előfeltételek megléte és lépések elvégzése szükséges, **még mielőtt** alkalmazásvédelmi szabályzatokat hozhat létre az Azure Portalon.

Ha kíváncsi rá, hogy az Intune alkalmazásvédelmi szabályzatai hogyan segítenek a vállalati adatok védelmében, olvassa el az [Alkalmazásadatok védelme mobilalkalmazás-kezelési szabályzatokkal](protect-apps-and-data-with-microsoft-intune.md) című cikket.

## <a name="what-is-the-azure-portal"></a>Mi az az Azure Portal?

Az Azure Portal az alkalmazásvédelmi szabályzatok létrehozására szolgáló új felügyeleti konzol. A portál a következő MAM-forgatókönyveket teszi lehetővé:
- Az Intune-ban regisztrált eszközök
- Más mobileszköz-felügyeleti (MDM) megoldások által felügyelt eszközök
- MDM-megoldással (BYOD) nem kezelt eszközök

Jelenleg az **Intune felügyeleti konzoljában** és az **Azure Portalon** is beállíthat alkalmazásvédelmi szabályzatokat.  Ügyeljen a következőkre:

* Az **Azure Portalon** létrehozott szabályzatok az előzőekben felsorolt **összes MAM-forgatókönyv** esetében támogatást élveznek. Az **Intune felügyeleti konzolja** csak **az Intune-ban regisztrált, és az Intune által felügyelt eszközökre vonatkozóan** teszi lehetővé szabályzatok létrehozását.

* Elképzelhető, hogy az Intune felügyeleti konzoljában nem érhető el az alkalmazásszabályzatokkal kapcsolatos összes lehetőség, mert az **új beállítások** esetenként csak az **Azure Portalba** kerülnek be.

* Ha az Intune felügyeleti konzoljában és az Azure Portalon **egyaránt** létrehoz alkalmazásvédelmi szabályzatokat, a rendszer az **Azure Portalon megadott szabályzatot érvényesíti az alkalmazásokra, illetve telepíti a felhasználók számára**.
    * Az Intune felügyeleti konzolon létrehozott alkalmazásvédelmi szabályzatokat nem lehet importálni az Azure Portalra.  Újra létre kell hozni az alkalmazásvédelmi szabályzatokat az Azure Portalon.


* Egyes **alkalmazásfelügyeleti funkciók** (például az alkalmazások központi telepítése, illetve az alkalmazáskonfigurációs szabályzatok életbe léptetése) csak az **Intune felügyeleti konzoljában** érhetők el.


Ha most ismerkedik az Azure Portallal, érdemes elolvasni az [Azure Portal a Microsoft Intune alkalmazásvédelmi szabályzatainak kezeléséhez](azure-portal-for-microsoft-intune-mam-policies.md) című témakört, amelyből megismerheti a portál használatának alapjait.

További útmutatás az alkalmazásszabályzatoknak az Intune segítségével történő létrehozásáról: [Mobilalkalmazás-felügyeleti szabályzatok konfigurálása és telepítése a Microsoft Intune-konzolban](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Támogatott platformok
- iOS 8.1-es vagy újabb verzió
- Android 4 vagy újabb verzió
- Windows 10

>[!NOTE]
>A 1703-as verzióval kezdve a MAM-ban regisztráció nélkül is lehet alkalmazásvédelmi szabályzatokat definiálni Windows 10-es eszközökhöz. További információk: [Vállalati adatok védelme a Windows információvédelemmel (WIP)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  <a name="supported-apps"></a>Támogatott alkalmazások
* **Microsoft-alkalmazások:** Ezeknek az alkalmazásoknak beépített része az Intune App SDK, és nincs szükség további intézkedésre az alkalmazásvédelmi szabályzatok használata előtt.
A támogatott Microsoft-alkalmazások teljes listájának megtekintéséhez keresse fel a [Microsoft Intune mobilalkalmazás-galériát](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) a Microsoft Intune alkalmazáspartnerek oldalán. Ha szeretné megtekinteni a támogatott forgatókönyveket és platformokat, illetve, hogy az alkalmazás támogatja-e a többszörös identitásokat, válassza ki az adott alkalmazást.

* **A szervezete üzletági alkalmazásai:** Az ilyen alkalmazásokat elő kell készíteni (az Intune App SDK hozzáadásával), csak ezt követően lehet rájuk vonatkozó alkalmazásvédelmi szabályzatokat életbe léptetni.

  * Az Intune által felügyelt eszközök esetében lásd: [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

  * A nem felügyelt eszközök (például az alkalmazottak saját tulajdonú eszközei) vagy a más mobileszköz-felügyeleti megoldások által felügyelt eszközök esetén lásd: [Üzletági alkalmazások és adatok védelme az Intune-ban nem regisztrált eszközökön](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Előfeltételek

-   **Microsoft Intune-előfizetés**. A felhasználóknak [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-licencekre van szükségük ahhoz, hogy megkapják azokat az alkalmazásokat, amelyekre alkalmazásvédelmi szabályzat érvényes.
Már van [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-előfizetése, ha jelenleg is az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-t használja az eszközök kezeléséhez. Akkor is rendelkezik [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-előfizetéssel, ha Nagyvállalati mobilitási csomag (EMS) licencet vásárolt. Ha a mobilalkalmazás-felügyeleti funkciók miatt próbálná ki az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-t, érdemes létrehozni egy próbafiókot a [Microsoft Intune webhelyen](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Az Office portál **Számlázás** oldalán ellenőrizheti, hagy rendelkezik-e [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-előfizetéssel.  Ha van előfizetése, az [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] állapota az előfizetések alatt **Aktív**.

-   **Office 365-előfizetés**, amely a következőkhöz szükséges:

  - Alkalmazásvédelmi szabályzatok foganatosítása a több identitás használatát támogató alkalmazásokra.

  - SharePoint Online- és Exchange Online munkahelyi fiókok létrehozása. A helyi Exchange-et és a helyi SharePointot nem támogatjuk.

-   **A Skype Vállalati online verzió beállítása modern hitelesítéshez**. További információkért lásd [Enable modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (A modern hitelesítés engedélyezése) című cikket.


- Microsoft Azure Active Directory (Azure AD) a felhasználók létrehozásához. Az Azure AD akkor hitelesíti a felhasználókat, amikor azok végfelhasználóként elindítják az alkalmazást, és megadják a munkahelyi hitelesítő adataikat.

    > [!NOTE]
    > Be kell állítani a felhasználói csoportokat az Azure AD-ben. Az Intune felhasználói csoportjai nem használhatók az alkalmazásvédelmi szabályzatoknak az Azure Portalon történő életbe léptetésére.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Felhasználók létrehozása és Microsoft Intune-licencek kiosztása

1.  Jelentkezzen be az   [Office portálra](http://portal.office.com) a rendszergazdai hitelesítő adataival.

2.  Vegye fel a felhasználókat az [Útmutató az Intune próbaverziójához](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) című cikk **az Intune 30 napos próbaverziójának használatba vételének lépéseit ismertető részének** megfelelően, majd ossza ki az Intune-licenceket. A felhasználók számára a **Globális rendszergazdai szerepkör** hozzárendelésével biztosíthat hozzáférést az Office-, az Azure AD- és az Azure-portálhoz.

5.  Az alkalmazásvédelmi szabályzatok az Azure Active Directory-beli felhasználói csoportokra vonatkoznak. Az alkalmazásvédelmi szabályzatok felhasználói csoportjait a [Csoportok létrehozása a próba-előfizetés felhasználóinak és eszközeinek rendszerezésére](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) című témakör **Felhasználói csoport létrehozása** című részében leírtak szerint hozhatja létre.

### <a name="assign-roles-to-non-global-admin-users"></a>Szerepkörök kiosztása a nem globális rendszergazdáknak

A globális rendszergazdák hozzáférhetnek az [Azure-portálhoz](https://portal.azure.com).  Ha a nem globális rendszergazda felhasználók számára is engedélyezni szeretné a szabályzatok konfigurálását, valamint egyéb mobilalkalmazás-felügyeleti műveletek elvégzését, olvassa el [Az Azure-előfizetések erőforrásaihoz való hozzáférés kezelése szerepkör-hozzárendelésekkel](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/) című cikket.

## <a name="next-steps"></a>További lépések
[Alkalmazásvédelmi szabályzatok létrehozása és telepítése a Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

