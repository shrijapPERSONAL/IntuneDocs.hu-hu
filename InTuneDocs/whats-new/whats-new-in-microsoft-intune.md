---
title: "Újdonságok | Microsoft Docs"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c473a1f05b0a7b0ce5205598b2b9a9b86bfe6c1d
ms.openlocfilehash: bddd8c0dc74835f74a71af1d900d43d84aab894c
ms.lasthandoff: 03/29/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Újdonságok a Microsoft Intune-ban – 2017. március
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

> [!Note]
> Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="support-for-skycure"></a>A Skycure támogatása

A Microsoft Intune-nal mostantól már integrálható, Skycure nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése. A kockázatfelmérés a Skycure által az eszközökről gyűjtött telemetriai adatokon alapul, például:

- Fizikai védelem
- Hálózatvédelem
- Alkalmazásvédelem
- Biztonsági rések elleni védelem

Az Intune eszközmegfelelőségi szabályzatai által engedélyezett, a Skycure által jelentett kockázatértékelés alapján EMS feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban. Ezen szabályzatok használatával engedélyezheti vagy letilthatja a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz az észlelt fenyegetések alapján. További információ: [Skycure Mobile Threat Defense-összekötő](/intune/deploy-use/skycure-mobile-threat-defense-connector).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622-->

Az Androidhoz készült Céges portál alkalmazás új, modern megjelenésű és jobb élményt biztosító felhasználói felületet kap. Fontosabb frissítések:

- Színek: a Céges portál lapfejléceinek színe meghatározható az informatikai részleg által.
- Alkalmazások: az **Alkalmazások** lapon frissítettük a **Kiemelt alkalmazások** és a **Minden alkalmazás** gombokat.
- Keresés: az **Alkalmazások** lapon a **Keresés** gomb lebegő műveletgombként jelenik meg.
- Navigáció az alkalmazások között: a **Minden alkalmazás** gomb lapnézetben jeleníti meg a **Kiemelt alkalmazásokat**, az **Összes alkalmazást** és a **Kategóriákat**, így a navigálás egyszerűbb.
- Támogatás: a **Saját eszközök** és az **IT-csoport elérhetősége** lapok olvashatósága javult.

A változásokkal kapcsolatos további részletekért lásd: [Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban](whats-new-in-intune-app-ui.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>A nem felügyelt eszközök hozzáférhetnek a hozzárendelt alkalmazásokhoz <!--664691-->

A Céges portál webhely átalakításának részeként az iOS-es és az Androidos felhasználók olyan alkalmazásokat telepíthetnek, amelyek hozzárendelés esetén a nem felügyelt eszközökön regisztráció nélkül érhetők el. Miután a felhasználók az Intune-beli hitelesítő adataikkal bejelentkeztek a Céges portál webhelyre, megtekinthetik a hozzájuk rendelt alkalmazások listáját. A regisztráció nélkül elérhető alkalmazások csomagjait a Céges portál webhelyről lehet letölteni. A telepítéskor regisztrációt kérő alkalmazásokat ez a változás nem érinti, mivel a rendszer az ilyen alkalmazások telepítésekor felszólítja a felhasználókat az eszközök regisztrációjára.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>A Windows 10-es Céges portálhoz készült aláírási szkript <!--941642-->

A Windows 10-es Céges portál alkalmazás letöltésekor és közvetlen telepítésekor mostantól rendelkezésre áll egy olyan szkript, amely egyszerűbbé és hatékonyabbá teszi az alkalmazások aláírását a munkahelyen.   A szkript letöltéséhez és használati útmutatójához tekintse meg a [Windows 10-es Céges portálhoz készült Microsoft Intune aláírási szkriptet](https://aka.ms/win10cpscript) a TechNet gyűjteményében. A bejelentéssel kapcsolatos további részletekért olvassa el [A Windows 10-es Céges portál alkalmazás frissítése](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) című bejegyzést az Intune ügyfélszolgálati csapat blogján.


## <a name="notices"></a>Értesítések

### <a name="support-for-ios-103"></a>Az iOS 10.3 támogatása

Az iOS 10.3-as kiadása 2017. március 27-től jelent meg az iOS felhasználók számára. Minden meglévő Intune MDM- és MAM-forgatókönyv kompatibilis a legújabb verziójú Apple operációs rendszerrel. Várakozásaink szerint a jelenleg rendelkezésre álló iOS-eszközökhöz elérhető összes meglévő Intune-szolgáltatás továbbra is működni fog, amikor a felhasználók az iOS 10.3-as verzióra frissítik az eszközeiket és az alkalmazásaikat.

Jelenleg nem tudunk ismert problémáról. Ha problémákat tapasztal az iOS 10.3-ban, forduljon [Intune támogatási csapatunkhoz](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Megújult támogatás az Android rendszert Kínában használó ügyfelek számára <!--720444-->

Kínában nem érhető el a Google Play Áruház, ezért az androidos eszközöknek kínai áruházakból kell beszerezniük az alkalmazásokat. A Céges portál alkalmazás ezt azzal segíti, hogy az Android rendszert Kínában használó ügyfeleket a Céges portál és az Outlook alkalmazások letöltéséhez helyi alkalmazásáruházakba irányítja át. Ezzel javul a mobileszköz-felügyelet és a mobilalkalmazás-felügyelet felhasználói élményének minősége, ha a feltételes hozzáférési szabályzatok engedélyezve vannak. Az androidos Céges portál és Outlook alkalmazások az alábbi kínai alkalmazásáruházakból tölthetők le:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Ajánlott eljárás: Gondoskodjon arról, hogy a Céges portál alkalmazásai naprakészek legyenek <!--879465-->

2016 decemberében kiadtunk egy olyan frissítést, amely lehetővé tette a többtényezős hitelesítés kényszerítését a felhasználók egy adott csoportjában Android, Windows 8.1+ vagy Windows Phone 8.1+ rendszerű eszközök regisztrációjakor. Ez a szolgáltatás nem működik az Androidhoz és az iOS-hez készült Céges portál alkalmazás bizonyos alapverziói nélkül (Android: v5.0.3419.0+ és iOS: v2.1.17+).

A Microsoft folyamatosan fejleszti az Intune-t, és az összes támogatott platformon új szolgáltatásokat vezet be a konzolhoz és a Céges portál alkalmazásokhoz kapcsolódóan. Ennek eredményeként a Microsoft csak olyan hibák javításait teszi közzé, amelyek a Céges portál alkalmazás jelenlegi verziójában találhatók meg. Javasoljuk, hogy az optimális felhasználói élmény érdekében a Céges portál alkalmazásainak legújabb verzióit használja.

>[!Tip]
> Gondoskodjon arról, hogy a felhasználók beállítsák az eszközeiket az alkalmazások megfelelő áruházból történő automatikus frissítésére. Ha az androidos Céges portál alkalmazást hálózati megosztáson tette elérhetővé, a legújabb verziót a [Microsoft letöltőközpontból](https://www.microsoft.com/download/details.aspx?id=49140) töltheti le.

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>A Microsoft Teams mostantól engedélyezve van az iOS és az Android rendszerű mobilalkalmazás-kezelés esetén

A Microsoft bejelentette a Microsoft Teams szolgáltatás általános rendelkezésre állását. Az iOS és az Android rendszerű frissített Microsoft Teams alkalmazások mostantól támogatják az Intune-beli mobilalkalmazás-kezelési képességeket, így a különböző csoportok mostantól többféle eszközön dolgozhatnak szabadon. A beszélgetések és a vállalati adatok védelme minden egyes ponton garantált. A [Microsoft Teams bejelentésével](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) kapcsolatos részleteket az Enterprise Mobility + Security blogon találja.


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója – újdonságok<!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](/intune-azure/introduction/whats-new).

> [!Note]
> Az Azure Portal előzetes verziójának frissítései ebben a hónapban jelennek meg. Azonban az Intune szolgáltatás bevezetési módja miatt elképzelhető, hogy a változások nem azonnal érhetők el.  A Portal új funkcióinak megjelenése előtt a szolgáltatás többféle összetevőjének egymás utáni frissítésére van szükség. Az Azure Portal előzetes verziójának változásai fokozatosan jelennek meg ebben a hónapban. A változások teljes listáját a [Microsoft Intune előzetes verziójának újdonságai](/intune-azure/introduction/whats-new) című témakörben találja.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Az Azure Portalon felváltott felügyeleti szerepkörök

A klasszikus Intune-portálon (Silverlight) meglévő mobilalkalmazás-kezelési (MAM) felügyeleti szerepköröket (közreműködői, tulajdonosi és csak olvasható) új szerepköralapú felügyeleti vezérlők (RBAC) teljes készlete váltotta fel az Intune Azure Portalon. Amennyiben az Azure Portalra migrált, újból hozzá kell rendelnie a rendszergazdákat ezen új felügyeleti szerepkörökhöz. További információ az RBAC-vel és az új szerepkörökről: [Szerepköralapú hozzáférés-vezérlés a Microsoft Intune-hoz](/intune-azure/access-control/role-based-access-control).


## <a name="whats-coming"></a>Mi várható?

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Az Apple frissítést tesz kötelezővé a Application Transport Security szolgáltatáshoz <!--748318-->

Az Apple bejelentette, hogy 2017 tavaszától bizonyos követelményeket ír elő az Application Transport Security (ATS, alkalmazás átviteli biztonsága) esetében. Az ATS szigorúbb biztonsági előírásokat érvényesít az alkalmazások közötti minden olyan kommunikációra, amely HTTPS-protokollon keresztül történik. Ez a változás minden olyan ügyfelet érint, aki az iOS rendszerű Céges portál alkalmazást használja. További információt az [Intune-támogatási blogban](https://aka.ms/compportalats) talál.

### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Az Azure előzetes verziójának újdonságai](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [A Céges portál felhasználói felületének újdonságai](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Újdonságok – Archívum](whats-new-archive.md)

