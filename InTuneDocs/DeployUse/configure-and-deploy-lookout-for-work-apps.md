---
title: "A Lookout for Work alkalmazás telepítése | Microsoft Intune"
description: "Lookout for Work alkalmazások konfigurálása és telepítése Android operációs rendszeren."
author: karthikaraman
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 99005e15268a60cd801ef1c717088dff2f82927b
ms.openlocfilehash: 8dce0689d5c4a0672b227eedf3ae738217eb17cf


---

# Lookout for Work alkalmazások konfigurálása és telepítése
Ez a cikk részletes információval szolgál arról, hogyan konfigurálhatja és telepítheti a Lookout for Work alkalmazást Android és iOS eszközökre.

## Android (Google Play Áruház alkalmazás)

* **1. lépés:**   Töltse fel a Lookout for Work Android alkalmazást a [Microsoft Intune felügyeleti konzoljába](https://manage.microsoft.com) az [Alkalmazások hozzáadása mobileszközökhöz a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) témakörben leírtaknak megfelelően.
>[!NOTE]
> Ne jelölje ki a kezelt böngészőt előíró jelölőnégyzetet.

![a listában lévő Lookout for work alkalmazásokat mutató képernyőkép az Intune felügyeleti konzol alkalmazások oldaláról](../media/mtp/lookout-app-listed-intune-console.png)

* **2. lépés:** Az alkalmazás telepítése a felhasználók számára. Jelölje ki a fenti képernyőképen látható Lookout for Work alkalmazást, és válassza a **Központi telepítés kezelése** lehetőséget.

  Ugyanazokat a felhasználókat kell kiválasztania, akiket a Lookout-konzolon az Enrollment Management (Regisztráció kezelése) beállítás alatt felvett.  A felhasználói csoportok Lookout MTP-hez történő hozzáadásáról bővebben lásd [Az előfizetés konfigurálása a Lookout veszélyforrások elleni eszközvédelmének használatához](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) című szakasz 3. lépését.
>[!IMPORTANT]
> Az Intune alkalmazástelepítési varázslója nem érzékeli az Azure AD-beli felhasználói csoportokat; ezek helyett az Intune-alapú felhasználói csoportokat használja, így azon az Azure AD-beli felhasználói csoporton alapuló Intune-os felhasználói csoportot kell létrehoznia, amely [ennek](plan-your-user-and-device-groups.md) a témakörnek megfelelően lett regisztrálva a Lookout-konzolon.

Válassza a **Szükséges telepítés** beállítást, hogy a Lookout alkalmazás telepítését kötelezővé tegye a felhasználók eszközein.


## iOS (A Lookout alkalmazás vállalat által aláírt verziója)

* **1. lépés:** Győződjön meg róla, hogy az **iOS-kezelés** be van állítva az eszközén. Utasítások az iOS-eszköz kezelésének beállításához:[ iOS- és Mac-eszközök kezelésének beállítása](Set up iOS and Mac device management.md).

* **2. lépés:** **Írja alá újra** a Lookout for work iOS alkalmazást. A Lookout az iOS App Store-on kívül terjeszti a Lookout for Work alkalmazását. **Az alkalmazás terjesztése előtt** újra alá kell írnia az alkalmazást az iOS vállalati fejlesztői tanúsítványával. A részletes leírást a Lookout for Work iOS alkalmazás újbóli aláírásáról lásd: [Lookout for Work iOS alkalmazás újbóli aláírásának folyamata](https://personal.support.lookout.com/hc/en-us/articles/114094038714) a Lookout oldalán.


* **3. lépés:** Engedélyezze az Azure Active Directory-hitelesítést iOS-felhasználók számára az alábbiak szerint:
  1.  Jelentkezzen be az [Azure Active Directory felügyeleti portálon](https://manage.windowsazure.com), és keresse meg az alkalmazáslapot.
  2.  Adja hozzá a **Lookout for Work iOS alkalmazást** **natív ügyfélalkalmazásként**.
  ![a natív ügyfélalkalmazás lehetőséget mutató képernyőkép az alkalmazás hozzáadása párbeszédpanelről](../media/mtp/aad-add-app.png)
  
  3. Cserélje le a **com.lookout.enterprise.yourcompanyname** sort az IPA aláírásakor választott ügyfélcsomag-azonosítóval.
  4.  Adjon hozzá további átirányítási URI-t: **&lt;companyportal://code/>**, valamint az eredeti átirányítási URI-ja URLencoded verzióját.
  5.  Adjon hozzá **Delegált engedélyeket** az alkalmazásához.

  További részletek: [Natív ügyfélalkalmazás konfigurálása](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).


* **4. lépés:** Töltse fel az újból aláírt .ipa fájlt az [Alkalmazások hozzáadása mobileszközökhöz a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) témakörben leírtaknak megfelelően. Állítsa a minimum OS verziót iOS 8.0-ra vagy újabbra.

  ![képernyőkép az alkalmazások oldalról az Intune felügyeleti konzoljában, amely a Lookout for work alkalmazást mutatja az alkalmazások listáján](../media/mtp/ios-app-uploaded-intune.png)

* **5. lépés:** Hozza létre a felügyelt alkalmazás konfigurációs szabályzatát az [iOS-alkalmazások konfigurálása mobilalkalmazás-konfigurációs szabályzatok segítségével a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) témakörben leírtaknak megfelelően.

  ![képernyőkép egy új szabályzat létrehozása varázslóról, kiemelve az iOS 8.0 vagy újabb alkalmazás-konfigurációs szabályzatot](../media/mtp/ios-app-config.png)

* **6.lépés:** **Telepítse az alkalmazást a felhasználók részére** úgy, hogy kiválasztja a Lookout for Work alkalmazást, és a **Központi telepítés kezelése** lehetőséget választja.

  Ugyanazokat a felhasználókat kell kiválasztania, akiket a Lookout-konzolon az Enrollment Management (Regisztráció kezelése) beállítás alatt felvett.  A felhasználói csoportok Lookout MTP-hez történő hozzáadásáról bővebben lásd [Az előfizetés konfigurálása a Lookout veszélyforrások elleni eszközvédelmének használatához](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) című szakasz 3. lépését.
>[!IMPORTANT]
> Az Intune alkalmazástelepítési varázslója nem érzékeli az Azure AD-beli felhasználói csoportokat; ezek helyett az Intune-alapú felhasználói csoportokat használja, így azon az Azure AD-beli felhasználói csoporton alapuló Intune-os felhasználói csoportot kell létrehoznia, amely [ennek](plan-your-user-and-device-groups.md) a témakörnek megfelelően lett regisztrálva a Lookout-konzolon.

Válassza a **Szükséges telepítés** beállítást, hogy a Lookout alkalmazás telepítését kötelezővé tegye a felhasználók eszközein.

## Mi történik ha telepített alkalmazást megnyitja az eszközön




Amikor a felhasználó megnyitja a Lookout for Work alkalmazást az eszközön, a rendszer felszólítja a felhasználót, hogy aktiválja az alkalmazást, majd válassza a Bejelentkezés Azure Active Directoryval opciót. A végfelhasználói folyamat részletes áttekintése a következő témakörökben található:

* [A rendszer felszólítja a Lookout for Work telepítésére az Android-eszközön](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [El kell hárítania egy fenyegetést, amit a Lookout for Work talált az Android-eszközön](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## További lépések
* [Az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Oct16_HO2-->


