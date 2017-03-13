---
title: "Újdonságok | Microsoft Docs"
description: "Ismerkedjen meg a Microsoft Intune e havi és korábbi verzióinak újdonságaival"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: cb1679deda0ba325ee3bd7288713f12317489006
ms.openlocfilehash: 37d44dc2752815ef7abf47e5d4a658a126892a86
ms.lasthandoff: 02/18/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Újdonságok a Microsoft Intune-ban – 2017. február
Ismerkedjen meg a Microsoft Intune új verziójának újdonságaival. Emellett tájékozódhat a jövőbeni változtatásokról és a korábbi verziókról, és felkészülhet a következő kiadásra.

> [!Note]
> Idővel mindezek a funkciók hibrid ügyféltelepítések esetén is támogatottak lesznek (Intune-nal integrált Configuration Manager). Az új hibrid funkciókról további információért tekintse meg a [hibrid újdonságok oldalát](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Új képességek

### <a name="modernizing-the-company-portal-website---753980--"></a>A Céges portál webhely modernizálása <!--753980-->
A Céges portál webhely támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![A hamburger menü kis képe, amely mostantól a Céges portál webhely bal felső sarkában található](./media/CP_hamburger_menu.png) fog használni, igazodva más Microsoft-termékekhez és -szolgáltatásokhoz. A kezdőlapot át fogjuk rendezni, felhívva a figyelmet a felhasználók számára elérhető alkalmazásokra a kiemelt és a legutóbb frissített alkalmazásokat mutató körhintanézetekkel. A frissítés előtti és utáni képek a [felhasználói felület frissítéseit tartalmazó lapon](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) érhetők el.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Új interaktív felület a Windows 10-es Céges portálhoz<!--713927-->
Márciustól a Windows 10-es Céges portál tartalmazni fog egy olyan eszközökhöz készült interaktív Intune-útmutató felületet, amelyek nincsenek azonosítva vagy regisztrálva. Az új útmutató felület olyan, az adott felhasználó Windows 10-buildjére szabott részletes utasításokat tartalmaz, amely végigvezeti a felhasználókat az AAD-regisztráció (mely a feltételes hozzáférési funkciók azonosításához szükséges) és az MDM-regisztráció (mely az eszközkezelési funkciókhoz szükséges) lépésein. Az interaktív felület a Céges portál kezdőlapjáról lesz elérhető és nem lesz kötelező; a felhasználók folytathatják az alkalmazás használatát a regisztráció befejezése nélkül, de ekkor a funkciók korlátozottak lehetnek.

## <a name="notices"></a>Értesítések

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A csoportmigráláshoz nem lesz szükség az iOS-eszközök csoportjainak vagy szabályzatainak frissítésére <!--898837-->
A vállalati eszközbeléptetési profil által előre hozzárendelt összes Intune-beli eszközcsoport esetében és az Azure Active Directory-eszközcsoportokba történő migrálás során a rendszer egy megfelelő dinamikus eszközcsoportot hoz létre az AAD-ben a vállalati eszközbeléptetési profil neve alapján. A rendszer ezzel biztosítja azt, hogy az eszközök a regisztráció során automatikusan bekerüljenek a megfelelő csoportba, valamint hogy ugyanazokat a szabályzatokat és alkalmazásokat kapják meg, mint az eredeti Intune-csoport.

Amint egy bérlő belép a csoportosítást és célcsoport-kezelést szolgáló migrálási folyamatba, az Intune automatikusan létrehoz egy dinamikus AAD-csoportot, amely igazodik a vállalati eszközbeléptetési profil által célzott Intune-csoporthoz. A célzott Intune-csoport Intune-rendszergazdai törlésével a megfelelő dinamikus AD-csoport törlése nem történik meg. A rendszer eltávolítja ugyan a csoporttagokat és a dinamikus lekérdezést, de maga a csoport addig megmarad, amíg a rendszergazda el nem távolítja azt az AAD portálon keresztül.

Hasonlóképpen, ha a rendszergazda módosítja a vállalati eszközbeléptetési profil által célzott Intune-csoportot, az Intune egy új dinamikus csoportot hoz létre az új profil-hozzárendelésnek megfelelően, de nem távolítja el a régi hozzárendeléshez létrehozott dinamikus csoportot.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>A windowsos asztali eszközök felügyelete alapértelmezés szerint a Windows beállításain keresztül történik <!--663050-->
Megváltozik a Windows 10-es asztali rendszerek regisztrációjának alapértelmezett működése. Az új regisztrációk a tipikus MDM-ügynöki regisztrációs folyamatot követik, nem a PC-s ügynökön keresztül zajlanak. A Munkahelyi portál webhely olyan instrukciókat szolgáltat az asztali Windows 10-es felhasználóknak, amelyek alapján asztali Windows 10-es számítógépeiket mobileszközként regisztrálhatják. Ez nem érinti a korábban regisztrált PC-ket, és a cég továbbra is felügyelheti a Windows 10-es asztali rendszereket a PC-s ügynökkel, [ha erre van igény](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Jobb MAM-támogatás a szelektív törléshez <!--581242-->
A végfelhasználók részletes útmutatást kapnak, amely alapján visszaszerezhetik hozzáférésüket az „Offline időszak az alkalmazásadatok törlése előtt” szabályzat által automatikusan törölt munkahelyi vagy iskolai adataikhoz.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Az iOS-es Munkahelyi portál hivatkozásai az alkalmazáson belül nyílnak meg <!--665954-->
Az iOS-re készült Munkahelyi portál alkalmazásban látható hivatkozások (köztük a dokumentációra és az alkalmazásokra mutatók is) közvetlenül Munkahelyi portál alkalmazásban nyílnak meg, a Safari beágyazott nézetében. Ez a frissítés a januári szolgáltatásfrissítéstől külön jelenik meg.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows-eszközök új MDM-kiszolgálói címe <!--893007-->
Azok a Windows- és Windows Phone-felhasználók, akik megkísérelnek beléptetni egy eszközt, és a __manage.microsoft.com__ címet adják meg MDM-kiszolgálói címként (ha a rendszer kéri), hibaüzenetet kapnak. Az MDM-kiszolgálói cím __manage.microsoft.com__ címről __enrollment.manage.microsoft.com__ címre változik. Értesítse a felhasználókat, hogy ha a rendszer kéri, az __enrollment.manage.microsoft.com__ címet használják MDM-kiszolgálói címként egy Windows- vagy Windows Phone-eszköz regisztrációjakor. A CNAME felépítésében nincs szükség változtatásokra. A fenti változásról további információt az [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange) weboldalon kaphat.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622-->
Márciustól kezdve az Androidhoz készült Céges portál alkalmazásban a [material design irányelveinek](https://material.io/guidelines/material-design/introduction.html) követésével gondoskodunk a még modernebb megjelenésről és működésről. A jobb felhasználói élményt többek között az alábbiak alkotják:

* __Színek__: a lapfejlécek színét módosítani lehet az egyéni színpaletta alapján.
* __Felület__: az Alkalmazások lapon frissítettük a Kiemelt alkalmazások és a Minden alkalmazás gombokat. A Keresés gomb mostantól lebegő műveletgombként jelenik meg.
* __Navigáció__: a Minden alkalmazás gomb lapnézetben jeleníti meg a kiemelt alkalmazásokat, az összes alkalmazást és a kategóriákat, így a navigálás egyszerűbb.
* __Szolgáltatás__: a Saját eszközök és az IT-csoport elérhetősége lapok olvashatósága javult.

A frissítés előtti és utáni képek a [felhasználói felület frissítéseit tartalmazó lapon](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) érhetők el.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Több felügyeleti eszköz társítása a Vállalati Windows Áruházhoz <!--926135-->
Ha több felügyeleti eszközt is használ a Vállalati Windows Áruházbeli alkalmazások üzembe helyezésére, akkor korábban ezek közül csak egyet társíthatott a Vállalati Windows Áruházhoz. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel). A részleteket lásd: [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése a Microsoft Intune-nal](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Az Intune új, Azure-beli felügyeleti felületének nyilvános előzetes verziója – újdonságok<!--736542-->

A 2017-es év elején a felügyeleti funkciók teljes körét áthelyezzük az Azure-ra. Ezáltal az EMS legfontosabb munkafolyamatainak hatékony és integrált felügyeletére nyílik lehetőség egy korszerű, a Graph API-k segítségével bővíthető szolgáltatásplatformon.

Az új próbabérlők ettől a hónaptól kezdve láthatják az Azure Portalon az új felügyeleti felület nyilvános előzetesét. Amíg a funkció előzetes verziójú, a meglévő Intune konzollal való egyenértékűség és a konzol funkciói több lépésben valósulnak meg.

Az Azure Portal felügyeleti felületén elérhető lesz a már bejelentett új csoportkezelési és célzási funkció. Amikor az Ön bérlőjét migráljuk az új csoportkezelési felületre, azzal egyidejűleg a bérlőjét áthelyezzük az új felügyeleti felület előzetes verziójára is. Ha bérlőjének migrálása előtt tesztelni szeretné vagy meg szeretné nézni valamelyik új funkciót, regisztráljon egy új Intune-próbafiókra, vagy pillantson bele az [új dokumentációba](https://docs.microsoft.com/intune-azure/introduction/whats-new).

Ha bármilyen kérdései vannak bérlőjének migrálásáról, forduljon migrációs csapatunkhoz a következő címen: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Az Intune Azure-beli előzetes verziójának újdonságait [Ide kattintva](https://docs.microsoft.com/intune-azure/introduction/whats-new) tekintheti meg.

### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Az Azure előzetes verziójának újdonságai](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [A Céges portál felhasználói felületének újdonságai](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Újdonságok – Archívum](whats-new-archive.md)

