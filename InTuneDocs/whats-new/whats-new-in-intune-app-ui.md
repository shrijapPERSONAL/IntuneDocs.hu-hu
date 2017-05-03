---
title: "Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban | Microsoft Docs"
description: "Ismerje meg, mi változott a végfelhasználói eszközökön Intune-nal működő alkalmazásokhoz tartozó felhasználói felületen."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: f4a48b889702147abe20fd513fdb0f774020a54a
ms.lasthandoff: 04/20/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Felhasználói felületi frissítések az Intune végfelhasználói alkalmazásaiban
A cikkből megismerheti, mit módosítottunk a végfelhasználók számára látható alkalmazások felhasználói felületén ebben a Microsoft Intune-kiadásban. Ez segítségére lehet a felhasználói kommunikációban és az Ön üzemeltetési környezetének támogatására létrehozott egyéni dokumentáció frissítésében. Annak megértését is megkönnyíti, hogy miképpen háríthatja el jobban a végfelhasználók által tapasztalt hibákat, ha telefonos segítséget igényelnek a Céges portál használatához.

> [!Note]
> Vegye figyelembe, hogy az alábbi képek az előzetes verziókra vonatkoznak, és a bejelentett termék eltérhet az itt bemutatott verzióktól.

## <a name="april-2017"></a>2017. április

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Jobb bejelentkezési élmény a Céges portál alkalmazásokhoz minden platformon <!--User Story 1132123-->

Javítottunk a bejelentkezési élményen az Intune Céges portál alkalmazásánál Android, iOS és Windows rendszereken.  A Céges portál alkalmazásnál az új felhasználói élmény automatikusan megjelenik minden platformon, miután az Azure AD-ban megjelenik a változtatás. Ezen kívül a felhasználók egy másik eszközről is bejelentkezhetnek a Céges portálba egy egyszeri használtra generált kóddal. Ez különösen akkor hasznos, ha a felhasználónak hitelesítő adatok nélkül kell bejelentkeznie.  

Alább képernyőképeket láthat a korábbi bejelentkezési módról, a hitelesítő adatokat használó új bejelentkezési élményről, és a másik eszközről történő bejelentkezési folyamatról.

__Korábbi bejelentkezési folyamat__

![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](./media/cp_ios_aad_signin_before_1704_001.png)

![A Bejelentkezés gombra kattintás után a felhasználónak meg kell adnia a hitelesítő adatait az oldalon. A rendszer a felhasználó e-mail-címét és jelszavát kéri, továbbá a jelszóval kapcsolatos hibák elhárításának módját is meg kell határoznia.](./media/cp_ios_aad_signin_before_1704_002.png)

![A jelszó megadása utána Céges portál alkalmazás elvégzi a bejelentkezést, amit egy betöltést jelző sáv jelez.](./media/cp_ios_aad_signin_before_1704_003.png)

__Új bejelentkezési folyamat__

![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](./media/cp_ios_aad_signin_after_1704_001.png)

![A felhasználónak ugyanazon az oldalon csak az e-mail-címét kell megadnia, nem pedig mind az e-mail-címét, mind a jelszavát.](./media/cp_ios_aad_signin_after_1704_002.png)

![A felhasználótól csak akkor kéri a rendszer a jelszavát ha már helyesen megadta az e-mail-címét.](./media/cp_ios_aad_signin_after_1704_003.png)

__Új bejelentkezési folyamat más eszközről való bejelentkezéskor__

![A Céges portál bejelentkezési oldala, amelyen egy webhely rajza előtt látható egy ember ikonja. Alatta látható a „Bejelentkezés” gomb. Az oldal alján látható egy hivatkozás, amely a Microsoft Adatvédelem és cookie-k oldalára mutat.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Koppintson a __Bejelentkezés más eszközről__ hivatkozásra.

![A felhasználónak ugyanazon az oldalon csak az e-mail-címét kell megadnia, nem pedig mind az e-mail-címét, mind a jelszavát. Az e-mail mező alatti hivatkozás szövege: „Bejelentkezés másik eszközről”.](./media/cp_ios_aad_signin_from_another_device_after_1704_002.png)

![A rendszer arra kéri a felhasználót, hogy látogassa meg a aka.ms/devicelogin oldalt a munkagéphez tartozó, megjelenített egyedi kódot használva a bejelentkezéshez.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Nyisson meg egy böngészőablakot és keresse fel az [http://aka.ms/devicelogin](https://aka.ms/devicelogin) webhelyet.

![A felhasználó munkagépén futó böngészőablak képe (nem pedig a Céges portál alkalmazásé). A megjelenített „Eszközbejelentkezés” oldal arra kéri a felhasználót, hogy adja meg a Céges portál alkalmazástól kapott kódot.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Írja be a Céges portál alkalmazás által megadott kódot. A __Folytatás__ elemet kiválasztva elvégezheti a hitelesítést a cége által támogatott bármely módszerrel, például intelligens kártyával.

![A felhasználó beírta a mezőbe az egyedi kódját, az „Eszközbejelentkezés” webhely pedig a felhasználó megerősítését kéri, hogy az Intune Céges portálnak kell-e bejelentkezési engedélyt kapnia.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Jóváhagyást jelző oldal, amely megerősíti, hogy a felhasználó bejelentkezett a Céges portál alkalmazásra az eszközén, és hogy ez az oldal bezárható.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

A Céges portál alkalmazás megkezdi a bejelentkezést.

![A hitelesítési folyamat végeztével a Céges portál alkalmazás bejelentkezik, amit egy betöltést jelző sáv jelez.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Új ikonok a Managed Browserhez és a Céges portálhoz <!--918433, 918431-->

A Managed Browser androidos és iOS-es verziója egyaránt megújult ikont kap. Ezen az Intune új jelvénye szerepel, így egységesebb lesz az Enterprise Mobility + Security (EM+S) programcsomag alkalmazásainak arculata.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
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
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

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
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>2017. január

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>A Céges portál webhely modernizálása <!--753980, announced 1701-->
A Céges portál webhely februártól kezdve támogatni fogja a felügyelt eszközökkel nem rendelkező felhasználóknak szánt alkalmazásokat. A webhely egy új kontrasztos színsémát, dinamikus ábrákat és egy, a segélyszolgálat kapcsolattartási adatait és a meglévő felügyelt eszközökre vonatkozó adatokat tartalmazó „hamburger” menüt ![A hamburger menü kis képe, amely mostantól a Céges portál webhely bal felső sarkában található](./media/CP_hamburger_menu.png) fog használni, igazodva más Microsoft-termékekhez és -szolgáltatásokhoz. A kezdőlapot át fogjuk rendezni, felhívva a figyelmet a felhasználók számára elérhető alkalmazásokra a kiemelt és a legutóbb frissített alkalmazásokat mutató körhintanézetekkel.

![Bal oldalt a Céges portál eddigi verziójának képe látható, rajta az Alkalmazások, az Eszközeim, illetve a Kiemelt és a Kategóriák nézet előző verziójával. Jobb oldalt a Céges portál átdolgozott verziójának képe látható, amelyen szerepel az új megjelenésű alkalmazásválasztó, a Legutóbb közzétett alkalmazások listája, illetve az átdolgozott Kategóriák nézet.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>További információ
* [A Microsoft Intune blogja](http://go.microsoft.com/fwlink/?LinkID=273882)
* [A felhőplatform ütemterve](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Az Azure előzetes verziójának újdonságai](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Újdonságok – Archívum](whats-new-archive.md)

