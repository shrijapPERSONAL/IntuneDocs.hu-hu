---
title: "Előzetes kiadás | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0936051b5c33a2e98f275ef7a3a32be2e8f5a8b0
ms.openlocfilehash: 0ba6695b595849f72eb44d8e6f095e8b1aae39eb
ms.lasthandoff: 03/10/2017


---


# <a name="the-early-edition-for-microsoft-intune---march-2017"></a>A Microsoft Intune előzetes kiadása – 2017. március

Ez az **Előzetes kiadás** a Microsoft Intune következő verzióiban található funkciók listáját tartalmazza. Ezekre az információkra igen szigorú titoktartási szerződés vonatkozik. Az információk változhatnak. Fennáll a kockázata, hogy az itt felsorolt funkciók nem készülnek el a kitűzött határidőig, és csak egy későbbi kiadásban lesznek elérhetők. Más funkciók próbaüzemben működnek (fokozatos bevezetéssel), hogy meggyőződjünk arról, hogy készen állnak a használatra. Esetleges kérdéseivel és észrevételeivel kérjük, forduljon Intune/PM-partneréhez.

A lap tartalmát rendszeresen frissítjük. További hírekért látogasson vissza.

> [!Note]
> A következő változtatások vannak fejlesztés alatt az Intune-hoz. Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622-->

Az Androidhoz készült Céges portál alkalmazás új, modern megjelenésű és jobb élményt biztosító felhasználói felületet kap. Fontosabb frissítések:

- Színek: a Céges portál lapfejléceinek színe meghatározható az informatikai részleg által.
- Alkalmazások: az **Alkalmazások** lapon frissítettük a **Kiemelt alkalmazások** és a **Minden alkalmazás** gombokat.
- Keresés: az **Alkalmazások** lapon a **Keresés** gomb lebegő műveletgombként jelenik meg.
- Navigáció az alkalmazások között: a **Minden alkalmazás** gomb lapnézetben jeleníti meg a **Kiemelt alkalmazásokat**, az **Összes alkalmazást** és a **Kategóriákat**, így a navigálás egyszerűbb.
- Támogatás: a **Saját eszközök** és az **IT-csoport elérhetősége** lapok olvashatósága javult.

A változásokról további információt talál az [alkalmazások felhasználói felületének frissítései témakörben](whats-new-in-intune-app-ui.md].

## <a name="notices"></a>Értesítések

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Megújult támogatás az Android rendszert Kínában használó ügyfelek számára <!--720444-->

Kínában nem érhető el a Google Play Áruház, ezért az androidos eszközöknek kínai áruházakból kell beszerezniük az alkalmazásokat. A Céges portál alkalmazás ezt azzal segíti, hogy az Android rendszert Kínában használó ügyfeleket a Céges portál és az Outlook alkalmazások letöltéséhez helyi alkalmazásáruházakba irányítja át. Ezzel javul a mobileszköz-felügyelet és a mobilalkalmazás-felügyelet felhasználói élményének minősége, ha a feltételes hozzáférési szabályzatok engedélyezve vannak. Az androidos Céges portál és Outlook alkalmazások az alábbi kínai alkalmazásáruházakból tölthetők le: 

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->

Az Apple bejelentette, hogy 2017 tavaszától bizonyos követelményeket ír elő az Application Transport Security (ATS, alkalmazás átviteli biztonsága) esetében. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS vagy macOS rendszerű Céges portál alkalmazást használja. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója <!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>A nem felügyelt eszközök hozzáférhetnek a hozzárendelt alkalmazásokhoz <!--664691-->

A Céges portál webhely átalakításának részeként az iOS-es és az Androidos felhasználók olyan alkalmazásokat telepíthetnek, amelyek hozzárendelés esetén a nem felügyelt eszközökön regisztráció nélkül érhetők el. Miután a felhasználók az Intune-beli hitelesítő adataikkal bejelentkeztek a Céges portál webhelyre, megtekinthetik a hozzájuk rendelt alkalmazások listáját. A regisztráció nélkül elérhető alkalmazások csomagjait a Céges portál webhelyről lehet letölteni. A telepítéskor regisztrációt kérő alkalmazásokat ez a változás nem érinti, mivel a rendszer az ilyen alkalmazások telepítésekor felszólítja a felhasználókat az eszközök regisztrációjára.

### <a name="improvements-to-device-actions-report---677150--"></a>Fejlesztések az eszközműveleti jelentéseknél <!--677150-->

A jobb teljesítmény érdekében fejlesztéseket végeztünk az eszközműveleti jelentéseknél. A jelentéseken ezen kívül állapot szerinti szűrések is végezhetők. Például olyan módon is szűrhetőek a jelentések, hogy csak a végrehajtott eszközműveletek jelenjenek meg.”

### <a name="actions-for-non-compliance---730266--"></a>Meg nem felelés esetén végrehajtandó műveletek <!--730266-->

A **Meg nem felelés esetén végrehajtandó műveletek** a megfelelési szabályzatokkal kapcsolatos új funkció, amellyel a nem megfelelő eszközökön lehet műveleteket végezni. Akár több műveletet is megadhat végrehajtásuk időpontjával együtt. E-mailben értesítheti például a nem megfelelő eszközök felhasználóit abban a pillanatban, amikor az eszköz nem megfelelővé válik, vagy a Feltételes hozzáférés funkcióval 3 napos türelmi időszak után letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

### <a name="custom-app-categories---748805--"></a>Egyéni alkalmazáskategóriák <!--748805-->

Mostantól kategóriákat hozhat létre, szerkeszthet és rendelhet hozzá az Intune-ba felvett alkalmazásokhoz. Jelenleg csak angol nyelven lehet kategóriákat megadni.
Lásd: [Alkalmazás hozzáadása az Intune-hoz](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Üzletági alkalmazások hozzárendelése nem regisztrált eszközökkel rendelkező felhasználókhoz <!--748823-->

Mostantól attól függetlenül kioszthat üzletági alkalmazásokat a felhasználóknak, hogy az eszközeik regisztrálva vannak-e az Intune-ban. Ha valamely felhasználó eszköze nincs regisztrálva az Intune-ban, a Munkahelyi portál alkalmazás helyett a Munkahelyi portál webhelyen telepíthetik az alkalmazást.

### <a name="new-compliance-reports---846671--"></a>Új megfelelőségi jelentések <!--846671-->

A megfelelőségi jelentések megmutatják a cég eszközeinek megfelelőségi helyzetét, így lehetővé válik a felhasználók által tapasztalt megfelelőségi problémák gyors elhárítása. Az alábbi információkat tekintheti meg:

- Az eszközök összesített megfelelőségi állapota
- Az egyes beállítások megfelelőségi állapota
- Az egyes szabályzatok megfelelőségi állapota

A jelentések segítségével egy-egy eszköz részletesebben is megvizsgálható, és ellenőrizhető, hogy mely beállítások és szabályzatok vonatkoznak rá.

### <a name="additional-windows-10-upgrade-paths---903672--"></a>További Windows 10-es frissítési útvonalak <!--903672-->

Mostantól olyan kiadásfrissítési szabályzatok is létrehozhatók, amelyekkel az alábbi Windows 10-kiadásokra frissíthetők az eszközök:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Az Apple regisztrálási forgatókönyvek közvetlen elérése <!--951869-->

A 2017. január után létrehozott Intune-fiókok esetében az Intune lehetővé tette az Apple regisztrálási forgatókönyvek közvetlen elérését az Azure Betekintő portálon elérhető Eszközregisztrációs munkafolyamat használatával. Korábban az Apple-regisztrálási betekintés csak a klasszikus Intune-portálon található hivatkozásokkal volt elérhető. A 2017 januárja előtt létrehozott Intune-fiókok esetében ezek a funkciók egy egyszeri áttelepítést követően válnak elérhetővé az Azure-ban. Az áttelepítés menetrendje még nem elérhető, de a lehető legrövidebb időn belül tájékoztatást adunk róla. Ha a jelenlegi fiókkal nem érhető el a betekintés, javasoljuk, hogy hozzon létre egy próbafiókot az új lehetőségek kipróbálásához.

### <a name="see-also"></a>További információ
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new-in-microsoft-intune.md).

