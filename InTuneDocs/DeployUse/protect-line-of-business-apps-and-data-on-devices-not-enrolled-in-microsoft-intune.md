---
title: "Üzletági (LOB) alkalmazások védelme nem regisztrált eszközökön | Microsoft Intune"
description: "Ez a témakör ezt ismerteti, hogyan készítheti elő az egyéni üzletági alkalmazásait arra, hogy alkalmazhassa az adatveszteség megakadályozását segítő mobilalkalmazás-kezelési szabályzatokat."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9bf5764d1e1bd73fd62e5033b2309fc8d5a912e4
ms.openlocfilehash: bc5d1b429157e6a6b24f4eb319be50b635466317


---

# <a name="protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune"></a>Az üzleti alkalmazások és az adatok védelme a nem regisztrált eszközökön a Microsoft Intune-ban

A mobilalkalmazás-felügyeleti (Mobile app management, MAM) szabályzatok azzal segítenek megvédeni a vállalati adatokat, hogy korlátozzák a vállalati adatok kiszivárgását kockáztató műveleteket, és betartatják az adatelérési követelményeket, például megkövetelik az alkalmazás PIN-kódját. A MAM-szabályzatok iOS vagy Android rendszeren futó üzleti alkalmazásokon való használatához először a Microsoft Intune alkalmazásburkolóval burkolnia kell az alkalmazást.  Az alkalmazásburkolás az a folyamat, amely során kezelési réteggel lát el egy mobilalkalmazást anélkül, hogy a mögöttes alkalmazást bárhogyan módosítaná.  Az alkalmazást a burkolása után MAM-szabályzattal láthatja el, és kioszthatja végfelhasználói között.  

Ez a témakör ismerteti a MAM-szabályzatoknak a **nem felügyelt, alkalmazotti eszközökön** és a **harmadik fél által nyújtott mobileszköz-kezelési (MDM) megoldások** által felügyelt eszközökön futó alkalmazásokhoz való hozzárendelését.  Az **Intune MDM-ben regisztrált eszközökön futó üzleti alkalmazások** előkészítéséhez tekintse meg az [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) című cikket.


##  <a name="step-1-prepare-the-app"></a>1. lépés: Az alkalmazás előkészítése
Mielőtt MAM-szabályzatot rendelne egy alkalmazáshoz, először burkolnia kell az alkalmazást a Microsoft Intune alkalmazásburkolóval.  Az alkalmazásburkoló eszköz letöltéséről és használatáról a következő lapokon olvashat útmutatást:

- [iOS-alkalmazások mobilalkalmazás-felügyeletre való előkészítése az alkalmazásburkoló eszközzel](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)
- [Android-alkalmazások előkészítése mobilalkalmazás-felügyelethez az Intune App Wrapping Tool eszközével](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

>[!IMPORTANT]  
>Az alkalmazásburkolónak ez a verziója, amely támogatja az Intune-ban nem regisztrált alkalmazásokat, iOS-re támogatott, Androidra pedig nyilvános előzetes verzióban érhető el. iOS-re [ebből a GitHub-adattárból](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios), Androidra pedig [ebből a GitHub-adattárból](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview) töltheti le az eszközt.

## <a name="step-2-add-the-app"></a>2. lépés: Az alkalmazás hozzáadása

Ha üzletági alkalmazását MAM-szabályzattal szeretné ellátni, az alkalmazás részleteit hozzá kell adnia az Intune-előfizetéséhez vagy a bérlőjéhez, az alábbi lépéseket követve:

1. Az [Azure-portálon](https://portal.azure.com/) válassza az **Intune mobilalkalmazás-kezelés > Beállítások** lehetőséget, majd az **Üzletági alkalmazások** elemet.

  ![Képernyőkép a beállítások panelről az üzletági beállítással](../media/mam-azure-portal-lob-on-settings.png)

2. Az **Üzletági alkalmazások** panelen válassza az **Egyéni alkalmazás hozzáadása** lehetőséget.

  ![Képernyőkép az üzletági alkalmazások panelről az Egyéni alkalmazás hozzáadása gombbal](../media/mam-azure-portal-add-lob-app-action.png)
3.  Adjon nevet az alkalmazásnak, valamint adja meg a csomagazonosítót az Alkalmazásazonosító mezőben, valamint a platformot (iOS vagy Android).

  ![Képernyőkép az Egyéni alkalmazás hozzáadása panelről ](../media/mam-azure-portal-add-app-details.png) Ezzel a lépéssel egyéni leírást hozhat létre az alkalmazáshoz.  Az alkalmazás a bérlő számára is megjelenik a MAM-szabályzatra váró Célzott alkalmazások listájában, ahogyan azt a következő lépés ismerteti.

## <a name="step-3-apply-mam-policies"></a>3. lépés: MAM-szabályzatok alkalmazása
Ha az alkalmazás metaadatai feltöltődtek a szolgáltatásra, az alkalmazás megjelenik az alkalmazáslistában.  Innentől kezdve [új vagy meglévő házirendet is létrehozhat](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md), és alkalmazhatja azt a 2. lépésben hozzáadott üzletági alkalmazásra.

>[!IMPORTANT]
>A mobilalkalmazás-kezelési házirendnek azokat a felhasználókat kell céloznia, akik a becsomagolt alkalmazást használni fogják.  Azok a felhasználók, akik nem rendelkeznek ilyen központilag telepített házirenddel, nem tudják használni az alkalmazást.


  ![Képernyőkép a Célzott alkalmazáslista panelről az új üzletági alkalmazással](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>4. lépés: Az alkalmazás terjesztése
Az alkalmazásokat az alábbi módszerekkel telepítheti a végfelhasználók számára:
* A harmadik felek által nyújtott MDM-megoldásokban regisztrált eszközökre az MDM-megoldáson keresztül juttathatja el az alkalmazásokat.
* A nem MDM-megoldásokkal felügyelt eszközökhöz egyéni megoldásra van szükség. A végfelhasználóknak maguknak kell letölteniük és telepíteniük az alkalmazást az eszközükre.

## <a name="changing-the-metadata"></a>A metaadatok módosítása
Ha módosítani szeretné az alkalmazás adatait, például az alkalmazás nevét vagy a csomagazonosítót, először [el kell távolítania az alkalmazást](#remove-apps), majd [hozzá kell adnia](#step-2-add-the-app) az új metaadatokkal.

##  <a name="remove-apps"></a>Alkalmazások eltávolítása
Az üzletági alkalmazásokat az alkalmazáslistából távolíthatja el.  Ezzel eltávolítja az alkalmazást a listából és megszünteti a MAM-szabályzatokhoz való hozzárendelést, de nem törli az alkalmazást a végfelhasználó eszközéről.  

1.  Az [Azure-portálon](https://portal.azure.com/) válassza az **Intune mobilalkalmazás-kezelés > Beállítások** lehetőséget.  A **Beállítások** panelen válassza az **Üzletági** lehetőséget a meglévő alkalmazások listájának megnyitásához.  
2.  Válassza ki az eltávolítani kívánt alkalmazást, és válassza a **(...) helyi** menüt.

  ![Képernyőkép az üzletági alkalmazások panelről a három ponttal](../media/mam-azure-portal-lob-context-menu.png)
3.  Válassza az **Alkalmazás törlése** lehetőséget az alkalmazás törléséhez.

  ![Képernyőkép az üzletági panelről az alkalmazás törlése lehetőséggel](../media/mam-azure-portal-delete-app.png)

  Ez eltávolítja az alkalmazást az üzletági alkalmazások listájából és a MAM-szabályzat Célzott alkalmazáslistájából.



<!--HONumber=Nov16_HO2-->


