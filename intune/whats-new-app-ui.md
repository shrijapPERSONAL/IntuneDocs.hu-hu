---
title: "Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban"
description: "Ismerje meg, mi változott a végfelhasználói eszközökön Intune-nal működő alkalmazásokhoz tartozó felhasználói felületen."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6db9bc7a3bafd61d03513ea1b6e1f0246faaab57
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2017
---
# <a name="ui-updates-for-intune-end-user-apps"></a>Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban
A cikkből megismerheti, mit módosítottunk a végfelhasználók számára látható alkalmazások felhasználói felületén ebben a Microsoft Intune-kiadásban. Ez segítségére lehet a felhasználói kommunikációban és az Ön üzemeltetési környezetének támogatására létrehozott egyéni dokumentáció frissítésében. Annak megértését is megkönnyíti, hogy miképpen háríthatja el jobban a végfelhasználók által tapasztalt hibákat, ha telefonos segítséget igényelnek a Céges portál használatához.

## <a name="week-of-august-21-2017"></a>2017. augusztus 21-i hét

### <a name="intune-mobile-application-management-mam-dialog-boxes-will-have-a-modern-interface----1199015---"></a>Az Intune mobilalkalmazás-felügyelet (MAM) párbeszédpaneljei modern felületet kapnak <!-- 1199015 -->

Az Intune mobilalkalmazás-felügyelet (MAM) párbeszédpaneljei modern megjelenést és működést nyújtó frissített felületet fognak kapni. A párbeszédpanelek működése megegyezik az előző stíluséval.

**Korábbi felhasználói élmény**

![régi felület](media\NewUI_Old_AttachFileHandler.jpg)

**Modern felhasználói élmény**

![modern felület](media\NewUI_Modern_AttachFileHandler.jpg)


## <a name="week-of-august-14-2017"></a>2017. augusztus 14-i hét

### <a name="updates-to-the-device-details-page-on-the-company-portal-app-for-windows-10----1287448---"></a>A Windows 10-hez készült Céges portál alkalmazás Eszköz adatai lapjának frissítései.<!---1287448--->

A Windows 10-hez készült Céges portál alkalmazásban a __Kategória__ címke immár nem a cím alatt jelenik meg, hanem egy, az __Eszköz adatai__ lapon szereplő tulajdonság formájában.

![A windowsos Céges portál alkalmazás Eszköz adatai képernyője, amelyen a Kategóriák mező immár tulajdonságként jelenik meg, nem pedig közvetlenül a képernyő címe alatt szerepel.](./media/cp_win10_category_tag_move_after_1708.png)

## <a name="week-of-july-31-2017"></a>2017. július 31-i hét

### <a name="apps-details-pages-will-display-new-information-for-android-devices---1287476--"></a>Új eszközinformációk Android-eszközök esetén az Alkalmazások részletei lapon <!--1287476-->

Az Androidhoz készült Céges portál Alkalmazások részletei lapján meg fognak jelenni a rendszergazda által az alkalmazáshoz definiált alkalmazáskategóriák.

![Az Alkalmazások részletei lap frissített változata](./media/cp_android_appdetails_after_1708.png)

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Jobb bejelentkezési élmény a Céges portál alkalmazásokhoz minden platformon <!--User Story 1132123-->

Egy olyan változást jelentünk most be, amely a következő néhány hónapban érkezik, és amellyel javulni fog a bejelentkezési élmény az Intune Céges portál Android, iOS és Windows rendszerű alkalmazásaiban. A Céges portál alkalmazásnál az új felhasználói élmény automatikusan megjelenik minden platformon, miután az Azure AD-ban megjelenik a változtatás. Ezen kívül a felhasználók egy másik eszközről is bejelentkezhetnek a Céges portálba egy egyszeri használtra generált kóddal. Ez különösen akkor hasznos, ha a felhasználónak hitelesítő adatok nélkül kell bejelentkeznie.  

Alább képernyőképeket láthat a korábbi bejelentkezési módról, a hitelesítő adatokat használó új bejelentkezési élményről, és a másik eszközről történő bejelentkezési folyamatról.

__Korábbi bejelentkezési folyamat__

![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](./media/cp_ios_aad_signin_before_1704_001.png)

![A Bejelentkezés gombra kattintás után a felhasználónak meg kell adnia a hitelesítő adatait az oldalon. A rendszer a felhasználó e-mail-címét és jelszavát kéri, továbbá a jelszóval kapcsolatos hibák elhárításának módját is meg kell határoznia.](./media/cp_ios_aad_signin_before_1704_002.png)

![A jelszó megadása utána Céges portál alkalmazás elvégzi a bejelentkezést, amit egy betöltést jelző sáv jelez.](./media/cp_ios_aad_signin_before_1704_003.png)

__Új bejelentkezési folyamat__

![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](./media/cp_ios_aad_signin_after_1704_001.png)

![A felhasználónak ugyanazon az oldalon csak az e-mail-címét kell megadnia, nem pedig mind az e-mail-címét, mind a jelszavát.](./media/cp_ios_aad_signin_after_1704_002.png)

![A felhasználótól csak akkor kéri a rendszer a jelszavát ha már helyesen megadta az e-mail-címét.](./media/cp_ios_aad_signin_after_1704_003.png)

![A hitelesítési folyamat végeztével a Céges portál alkalmazás bejelentkezik, amit egy betöltést jelző sáv jelez.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Új bejelentkezési folyamat más eszközről való bejelentkezéskor__

![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Koppintson a __Bejelentkezés más eszközről__ hivatkozásra.

![A rendszer arra kéri a felhasználót, hogy látogassa meg a aka.ms/devicelogin oldalt a munkagéphez tartozó, megjelenített egyedi kódot használva a bejelentkezéshez.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Nyissa meg egy böngészőablakban az [http://aka.ms/devicelogin](https://aka.ms/devicelogin) webhelyet.

![A felhasználó munkagépén futó böngészőablak képe (nem pedig a Céges portál alkalmazásé). A megjelenített „Eszközbejelentkezés” oldal arra kéri a felhasználót, hogy adja meg a Céges portál alkalmazástól kapott kódot.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Írja be a Céges portál alkalmazás által megadott kódot. A __Folytatás__ elemet kiválasztva elvégezheti a hitelesítést a cége által támogatott bármely módszerrel, például intelligens kártyával.

![A felhasználó beírta a mezőbe az egyedi kódját, az „Eszközbejelentkezés” webhely pedig a felhasználó megerősítését kéri, hogy az Intune Céges portálnak kell-e bejelentkezési engedélyt kapnia.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Jóváhagyást jelző oldal, amely megerősíti, hogy a felhasználó bejelentkezett a Céges portál alkalmazásra az eszközén, és hogy ez az oldal bezárható.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

A Céges portál alkalmazás megkezdi a bejelentkezést.

![A hitelesítési folyamat végeztével a Céges portál alkalmazás bejelentkezik, amit egy betöltést jelző sáv jelez.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="week-of-june-12-2017"></a>2017. június 12-i hét

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Az Androidhoz készült Céges portál alkalmazás mostantól új felhasználói felületet nyújt az alkalmazásvédelmi szabályzatokhoz <!--1305217-->
A felhasználók visszajelzései alapján úgy módosítottuk az Androidhoz készült Céges portál alkalmazást, hogy egy **Céges tartalom elérése** gombot is hozzáadtunk. Ez mentesíti a végfelhasználót attól, hogy az egész regisztrációs folyamaton végig kelljen mennie, ha csak olyan alkalmazásokat kíván elérni, amelyek az Intune mobilalkalmazás-felügyelet egyik funkcióját, az alkalmazásvédelmi szabályzatokat támogatják.

A felhasználó az eszköz regisztrálása helyett a **Céges tartalom elérése** gombra koppint.

![Kép az Androidhoz készült Céges portál alkalmazásról, amelyen középen és nagybetűvel a „Céges tartalom elérése” szöveg látható, ellentétben a szokványos esettel, amely az azonnali regisztrálási lehetőségeket kínálja fel](./media/and_access_company_content_after_1706.png)

A felhasználó ezt követően a Céges portál webhelyre jut, ahol hitelesítheti az alkalmazás használatát az eszközén, majd a Céges portál webhely ellenőrzi a hitelesítő adatait.

![A Céges portál webhely képe a bejelentkezés megerősítésével.](./media/and_iwp_sign_in_auth_page_after_1706.png)

Az eszközt továbbra is regisztrálhatja teljes körű felügyeletre, ha a **művelet** menüre koppint.

![Kép az Androidhoz készült Céges portál alkalmazásról a képernyő jobb felső sarkában található menüvel, ahol továbbra is megtalálható az eszközregisztráció lehetősége.](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>A Windows 10 alkotói frissítésével való alkalmazás-szinkronizálás fejlesztései <!--676505-->

A Windows 10-es Céges portál alkalmazás automatikusan kezdeményez szinkronizálást alkalmazástelepítési kérésekhez Windows 10 alkotói frissítést (1703-as verziót) futtató eszközök esetén. Ez csökkenti a függőben lévő szinkronizálás során feltorlódó alkalmazástelepítési műveletek számát. Emellett a felhasználók manuálisan is kezdeményezhetnek szinkronizálást az alkalmazásban.

![Kép a Windows 10-es Céges Portál alkalmazásról, ahol éppen függőben van a Microsoft Word letöltése a Céges portál alkalmazásáruházából.](./media/w10_download_pending_after_1706.png)

![Kép a Windows 10-es Céges Portál alkalmazásról az új automatikus szinkronizálás állapotkijelzésével, melynek üzenete szerint az eszköz szinkronizálása folyamatban van, és megpróbálja letölteni az alkalmazást.](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Új interaktív felület a Windows 10-es Céges portálhoz<!---1058938--->
A Windows 10-es Céges portál alkalmazás tartalmazni fog egy interaktív Intune-útmutatót a nem azonosított vagy regisztrált eszközökhöz. Az új útmutató olyan részletes utasításokat tartalmaz, amelyek végigvezetik a felhasználókat a feltételes hozzáférési funkciók azonosításához szükséges Azure Active Directory-regisztrálás és az eszközkezelési funkciókhoz szükséges MDM-regisztrálás lépésein. Az útmutató a Céges portál kezdőlapján lesz elérhető. A felhasználók akkor is használhatják az alkalmazást, ha nem végezték el a regisztrálást és a beléptetést, de így korlátozottan használhatják csak a funkciókat.

Ez a frissítés csak a Windows 10 évfordulós frissítést (1607-es) vagy újabb verziókat futtató eszközökön látható.

![Kép a Windows 10-es Céges portál alkalmazás kezdőlapjáról: középen az „eszközök” listában látható az állapotüzenet, amely szerint a felhasználó által jelenleg használt eszközt még nem állították be céges használatra, és a felhasználónak rá kell koppintania az üzenetre a beállítás kezdeményezéséhez.](./media/win10_guided_enroll_select_setup_after_1706.png)

![Kép a Windows 10-es Céges portál alkalmazás beállítás-oldaláról a figyelmeztetéssel, amely szerint a felhasználónak előbb céges fiókot kell adnia az eszközhöz, és csak aztán regisztrálhatja azt a felügyeleti szolgáltatásban.](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Kép a Windows 10-es Céges portál alkalmazás céges fiók hozzáadása oldaláról, amely arra figyelmezteti a felhasználót, hogy a regisztráció befejezéséhez a Beállítások alkalmazásra kell váltania, és ott rá kell kattintania a „Kapcsolódás” elemre. Ezt követően a képernyőn megjelenő üzenet arra kéri a felhasználót, hogy a regisztráció befejezéséhez térjen vissza a Céges portálra.](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Kép a Windows 10-es Céges portál alkalmazás alkalmazásregisztráció a felügyeleti szolgáltatásban képernyőjéről, amelyen a kész állapotüzenet szerint az eszközt regisztrálta a rendszer, és a folytatáshoz a ’tovább’ gombra kell koppintani.](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Kép a Windows 10-es Céges portál alkalmazás befejezés képernyőjéről, amely szerint a beállítások elkészültek, és a céges fiók megfelelő hozzárendelése, valamint az eszközregisztráció befejeződött.](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Új menüművelet a Céges portál egyszerű eltávolításához <!--1164569-->
Felhasználói visszajelzések alapján az androidos Céges portál alkalmazásban új menüművelet jelent meg, amellyel a Céges portál eszközről való eltávolítása kezdeményezhető. A művelet megszünteti az eszköz Intune-felügyeletét, így a felhasználó az alkalmazást is eltávolíthatja az eszközről.

![Az androidos Céges portál alkalmazás képe, a jobb felső sarokban a megnyitott műveletmenüvel. A „Saját profil” és a „beállítások” lehetőség alatt harmadikként megjelenik az új „céges portál eltávolítása” lehetőség is, alatta a „használati feltételek”, a „súgó és visszajelzés” és végül a „névjegy”.](./media/android_remove_cp_menu_action_after_1705.png)

![A megerősítést kérő párbeszédpanel képe, amely az új „céges portál eltávolítása” lehetőség kiválasztása után jelenik meg. A párbeszédpanel tájékoztatja a felhasználót, hogy „a céges portál eltávolítása után az eszközt nem fogja felügyelni a rendszergazda, és megszűnhet a hozzáférés a céges adatokhoz, a céges alkalmazásokhoz és a céges e-mailekhez.” Megkérdezi a felhasználót, biztosan el akarja-e távolítani a Céges portál alkalmazást, mely esetben az „Igen” lehetőséget választhatja.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="week-of-june-5-2017"></a>2017. június 5-i hét

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios---1230777--"></a>Továbbfejlesztett alkalmazáscsempék az iOS-hez készült Céges portál alkalmazásban <!--1230777-->
Frissítettük a kezdőlapon található alkalmazáscsempék megjelenését annak érdekében, hogy a Céges portálhoz beállított márkaszínek jelenjenek meg rajtuk.

**Előtte**

![Az iOS-es Céges portál alkalmazás képe a frissítés előttről, amelyen az alkalmazások előre beállított szűrők használatával jelennek meg „Minden alkalmazás”, „Kiemelt alkalmazások” és „kategóriák” csoportosításban.](./media/cp_ios_homepage_before_1705.png)

**Utána**

![Az iOS-es Céges portál alkalmazása a frissítés utánról, amelyen már látható, hogy lehetőség van a cég által meghatározott színek kiválasztására.](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Az iOS-es Céges portál alkalmazásban elérhető a fiókválasztó
Ha a felhasználók iOS-eszközükön munkahelyi vagy iskolai fiókkal már jelentkeztek be más Microsoft-alkalmazásokba, akkor megjelenhet számukra az új fiókválasztó is, amikor először jelentkeznek be a Céges portálba.

![A fiókválasztó képe, amelyen „Robin Swanson” tesztfelhasználó két e-mail-címe közül választhat ki egyet. A két cím alatt egy újabb gomb is megjelenik, amely lehetővé teszi, hogy a felhasználó másik fiókkal is bejelentkezhessen.](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>2017. április

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Új ikonok a Managed Browserhez és a Céges portálhoz <!--918433, 918431-->

A Managed Browser androidos és iOS-es verziója egyaránt megújult ikont kap. Ezen az Intune új jelvénye szerepel, így egységesebb lesz az Enterprise Mobility + Security (EM+S) programcsomag alkalmazásainak arculata.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

A Céges portál androidos, iOS-es és windowsos verziója is új ikont kap az EM+S többi alkalmazásával való összhang jegyében. Ezek az ikonok fokozatosan jelennek majd meg az egyes platformokon áprilistól május végéig.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Bejelentkezési folyamatjelző az androidos Céges portálhoz <!--953374-->

Az androidos Céges portál alkalmazás frissítésének köszönhetően bejelentkezési folyamatjelző jelenik meg, ha a felhasználó elindítja az alkalmazást vagy folytatja a használatát. A folyamatjelző új állapotokon halad végig, ezek időrendben a következők: „Csatlakozás...”, „Bejelentkezés...” és „Biztonsági követelmények keresése...” – a felhasználó ezt követően fér hozzá az alkalmazáshoz.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Jobb telepítésiállapot-megjelenítés a Windows 10-es Céges portál alkalmazásban <!--676495-->
A Windows 10-es Céges portál alkalmazás mostantól telepítési folyamatjelző sávot tartalmaz az alkalmazás részleteit megjelenítő oldalon. A funkciót a Windows 10 évfordulós frissítését és újabb kiadásait futtató eszközök modern alkalmazásai támogatják.

__Előtte__ ![ Kép a betöltési képernyő előző verziójáról, amelyen az állapotra csak a „telepítés” kifejezés utal. ](./media/cp_win10_install_status_before_1704.png)

__Utána__ ![Kép a betöltési képernyő frissített verziójáról, amelyen mostantól a telepítés folyamatjelző sávja is látható.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>2017. február

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Új felhasználói élmény az Androidhoz készült Céges portál alkalmazásban <!--621622, announced 1702-->
Márciustól kezdve az Androidhoz készült Céges portál alkalmazásban a [material design irányelveinek](https://material.io/guidelines/material-design/introduction.html) követésével gondoskodunk a még modernebb megjelenésről és működésről. A jobb felhasználói élményt többek között az alábbiak alkotják:

* __Színek__: a lapfejlécek színét módosítani lehet az egyéni színpaletta alapján.

![A bal oldalon az Androidhoz készült Céges portál alkalmazás képe látható a frissítés előtt. A jobb oldalon az Androidhoz készült Céges portál alkalmazás képe látható a frissítés után. Mindkét képen az Eszközök lap van kijelölve a három elérhető lap közül (Alkalmazások, Eszközök és IT-csoport elérhetősége).](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Felület__: az __Alkalmazások__ lapon frissítettük a __Kiemelt alkalmazások__ és a __Minden alkalmazás__ gombokat. A __Keresés__ gomb mostantól lebegő műveletgombként jelenik meg.

![A bal oldalon az Androidhoz készült Céges portál alkalmazás képe látható a frissítés előtt. A jobb oldalon az Androidhoz készült Céges portál alkalmazás képe látható a frissítés után. Mindkét képen az Alkalmazások lap van kijelölve a három elérhető lap közül (Alkalmazások, Eszközök és IT-csoport elérhetősége).](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navigáció__: a Minden alkalmazás gomb lapnézetben jeleníti meg a __kiemelt alkalmazásokat__, az __összes alkalmazást__ és a __kategóriákat__, így a navigálás egyszerűbb. Az __IT-csoport elérhetősége__ lapot egyszerűsítettük a jobb olvashatóság érdekében.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>2017. január

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>A Céges portál webhely modernizálása <!--753980, announced 1701-->
A Céges portál webhely februártól kezdve támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![A hamburger menü kis képe, amely mostantól a Céges portál webhely bal felső sarkában található](./media/CP_hamburger_menu.png) fog használni, igazodva más Microsoft-termékekhez és -szolgáltatásokhoz. A kezdőlapot át fogjuk rendezni, felhívva a figyelmet a felhasználók számára elérhető alkalmazásokra a kiemelt és a legutóbb frissített alkalmazásokat mutató körhintanézetekkel.

![Bal oldalt a Céges portál eddigi verziójának képe látható, rajta az Alkalmazások, az Eszközeim, illetve a Kiemelt és a Kategóriák nézet előző verziójával. Jobb oldalt a Céges portál átdolgozott verziójának képe látható, amelyen szerepel az új megjelenésű alkalmazásválasztó, a Legutóbb közzétett alkalmazások listája, illetve az átdolgozott Kategóriák nézet.](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a>Hamarosan elérhető a felhasználói felületen
Ezek azok a tervezett megoldások, amelyekkel a felhasználói felület frissítésén keresztül javulni fog a felhasználói élmény.

> [!Note]
> Vegye figyelembe, hogy az alábbi képek előzetes verziókra vonatkozhatnak, és a bejelentett termék eltérhet az itt bemutatott verzióktól.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>A Céges portál felhasználói felületének frissítései <!--1313244 part 2-->

__Kiemelt alkalmazások frissítései__ A webhelyhez hozzáadtunk egy új oldalt, ahol a felhasználók a megadott kiemelt alkalmazások között böngészhetnek, és finomhangolásokat végeztünk a honlap Kiemelt szakaszán.

![Az alkalmazásokat jelölő színes csempék. Minden alkalmazás alatt nagy színes négyzet látható, melynek színe megegyezik az alkalmazáslogó elsődleges színével. A „Kiemelt alkalmazások” szakasz a Céges portál alkalmazás felső részében látható.](./media/cp_win10_colorful_tiles_after_1708.png)

### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Az Intune újdonságai](https://docs.microsoft.com/intune/whats-new)
