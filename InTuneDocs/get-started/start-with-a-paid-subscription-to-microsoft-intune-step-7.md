---
title: "A vállalati portál testreszabása | Microsoft Intune"
description: "Az Intune Munkahelyi portál a gyakori feladatok elvégzését teszi lehetővé a felhasználók számára (például az eszközök regisztrálását, az alkalmazások telepítését és az informatikai osztály adatainak megkeresését)."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 04cccd410417dca4477c0d6cd61b0940dda8c389


---

# <a name="customize-the-company-portal"></a>A vállalati portál testreszabása
A felhasználók az Intune Vállalati portálon érhetik el a vállalati adatokat, és olyan gyakori feladatokat hajthatnak végre, mint például az eszközök regisztrálása, az alkalmazások telepítése és az informatikai támogatási információk megtekintése.

Az Intune Munkahelyi portál a felhasználók számára hozzáférést biztosít a vállalati adatokhoz és alkalmazásokhoz. A Vállalati portál két formában érhető el:

-   **A Munkahelyi portál alkalmazás**: Az Intune által felügyelt eszközökön elérhető alkalmazás. További információk a Vállalati portál alkalmazásokról [Android](/Intune/EndUser/using-your-android-device-with-intune), [iOS](/Intune/EndUser/using-your-ios-or-mac-os-x-device-with-intune) és [Windows](/Intune/EndUser/using-your-windows-device-with-intune) rendszerekhez.


- **A Munkahelyi portál webhelye**: Webhely, amellyel többségükben elvégezhetők azok a műveletek, amelyek a Munkahelyi portál alkalmazásban. Az Intune Munkahelyi portál URL-címe: [http://portal.manage.microsoft.com](http://portal.manage.microsoft.com). A webhellyel kapcsolatos további információk [Az Intune vállalati portál webhelyének használata](/Intune/EndUser/using-the-intune-company-portal-website) című témakörben olvashatók.

> [!TIP]
> A vállalati portál testreszabása a vállalati portál webhelyére és a vállalati portál alkalmazásaira egyaránt hatással van.

Néhány művelet, amelyeket a felhasználók elvégezhetnek a Vállalati portálon:

-   Eszközök regisztrálása
-   Az eszközök állapotának megtekintése
-   Eszköz alaphelyzetbe állítása
-   Jelszó visszaállítása
-   Az eszköz távoli zárolása
-   A szervezet által telepített szoftverek letöltése
-   Támogatás kérése az informatikai részlegtől

> [!NOTE]
> A Munkahelyi portál alkalmazás nem érhető el minden országban.
> __iOS__: az iOS rendszerre készült Munkahelyi portál alkalmazást az Apple iOS App Store áruházban [elérhető összes régióban](https://go.microsoft.com/fwlink/?linkid=831284) megtalálható.
> __Android__: A Munkahelyi portál alkalmazás androidos változata Kínában jelenleg nem érhető el. Ezekben az országokban alternatív megoldásként [közvetlenül is telepíthető a Munkahelyi portál alkalmazás androidos verziója](https://www.microsoft.com/en-us/download/details.aspx?id=49140).  

## <a name="customize-company-portal-settings"></a>A Munkahelyi portál beállításainak testreszabása
A vállalati portál testreszabásával ismerős és könnyen használható környezetet teremthet felhasználóinak. Jelentkezzen be a [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) bérlői vagy szolgáltatás-rendszergazdaként, válassza a **Felügyelet** &gt; **Munkahelyi portál** lehetőséget, és konfigurálja a Munkahelyi portál beállításait.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## <a name="company-contact-information-and-privacy-statement"></a>Vállalat kapcsolattartási adatai és adatvédelmi nyilatkozata
A vállalat neve a Vállalati portál címeként jelenik meg. A kapcsolattartási adatokat és részleteket a felhasználók a Vállalati portál IT-csoport elérhetősége képernyőjén tekinthetik meg. Az adatvédelmi nyilatkozat az Adatvédelem hivatkozásra kattintva jeleníthető meg.

|Mező neve|Maximális hossz|További információ|
    |----------|------------------------|----------------|
    |A cég neve|40|Ez a név a Vállalati portál címeként jelenik meg.|
    |IT-részleg kapcsolattartójának a neve|40|Ez a név az **IT-csoport elérhetősége** lapon jelenik meg.|
    |IT-részleg telefonszáma|20|Ez a telefonszám az **IT-csoport elérhetősége** lapon jelenik meg.|
    |IT-részleg e-mail címe|40|Ez a cím az **IT-csoport elérhetősége** lapon jelenik meg. Meg kell adnia egy érvényes e-mail címet a következő formátumban: **alias@domainname.com**.|
    |További információ|120|Az **IT-csoport elérhetősége** lapon jelenik meg.|
    |Vállalat adatvédelmi nyilatkozatának URL-címe:|79|Itt adhatja meg vállalatának adatvédelmi nyilatkozatát, amely akkor jelenik meg, ha a felhasználó a Vállalati portál adatvédelmi hivatkozásaira kattint. Érvényes URL-címet kell megadnia, a következő formátumban: https://www.contoso.com.|

## <a name="support-contacts"></a>Támogatási kapcsolattartók
A támogatási webhely a Vállalati portálon jelenik meg, és lehetővé teszi a felhasználók számára az online támogatás elérését.

|Mező neve|Maximális hossz|További információ|
    |----------|------------------------|----------------|
    |Támogatási webhely URL-címe|150|Ha rendelkezik saját felhasználóinak szánt támogatási webhellyel, ide írja be az URL-címét. Az URL-címet a https://www.contoso.com formátumban kell megadni. Ha nem ad meg URL-címet, semmi sem jelenik meg a támogatási webhelyről a Vállalati portál **IT-csoport elérhetősége** lapján.|
    |Webhely neve|40|Ez a név a támogatási webhely URL-címének rövid neveként jelenik meg. Ha a támogatási webhelyhez csak URL-címet ad meg, de egyszerű nevet nem, akkor **Az IT-csoport weboldalának megnyitása** felirat jelenik meg a Vállalati portál **IT-csoport elérhetősége** lapján.|

## <a name="company-branding-customization"></a>Vállalati arculat szerinti testreszabás
A Vállalati portál testre szabható a vállalat emblémájának és nevének, valamint a téma színének és a háttérnek a megadásával.

|Mező neve|További információ|
    |----------|----------------|
    |Téma színe|A Vállalati portálra alkalmazni kívánt témaszín kiválasztása.|
    |Cég emblémájának megjelenítése|Ha engedélyezi ezt a beállítást, feltöltheti a Vállalati portálon megjeleníteni kívánt vállalati emblémát. Két emblémát tölthet fel: az egyik akkor jelenik meg, ha a Vállalati portál háttérszíne fehér, a másik pedig akkor, ha a Vállalati portál a témának megfelelő háttérszínnel jelenik meg. Mindkét emblémának egy .png vagy .jpg formátumú fájlnak kell lennie, melyek felbontása legfeljebb 400 x 100 képpont, mérete pedig legfeljebb 750 KB lehet.|
    |Háttér választása a [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Vállalati portál alkalmazás számára|Ez a beállítás csak a [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Vállalati portál alkalmazás hátterére van hatással.|


A módosítások mentése után a felügyeleti konzol **Vállalati portál** lapjának alján található hivatkozásokra kattintva megtekintheti a Vállalati portál webhelyét. Ezek a hivatkozások nem módosíthatók. A felhasználók bejelentkezésekor ezek a hivatkozások a Vállalati portálon megjelenítik az Ön előfizetéseit.

>[!div class="step-by-step"]

>[&larr; **Házirendek és alkalmazások létrehozása**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Eszközök regisztrálása** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  



<!--HONumber=Dec16_HO2-->


