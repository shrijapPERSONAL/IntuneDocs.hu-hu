---
title: "iOS-alkalmazások felügyelete MAM-szabályzatokkal | Microsoft Intune"
description: "Ez a témakör bemutatja, mire számítson, ha iOS-alkalmazását mobilalkalmazás-felügyeleti szabályzatok felügyelik."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# Mi történik, ha az iOS-alkalmazást MAM-szabályzatok felügyelik?
 Ez a témakör a MAM-szabályzatokat használó alkalmazásokkal kapcsolatos végfelhasználói élményt ismerteti. A mobilalkalmazás-felügyeleti (MAM) szabályzatokat csak akkor érvényesíti a rendszer, amikor az alkalmazásokat a munkahelyi környezetben használják: ha például a munkahelyi fiókkal lép be egy alkalmazásba, vagy a vállalat OneDrive vállalati helyén tárolt fájlokat nyit meg.
##  Alkalmazásokhoz való hozzáférés

Ha az eszköz **nincs regisztrálva az Intune-ban**, a rendszer az alkalmazás első használatakor felkéri a felhasználót, hogy indítsa újra az alkalmazást.  Az újraindítás azért szükséges, hogy a rendszer alkalmazni tudja a MAM-szabályzatokat. Az alábbi képernyőképen ezt láthatja a Skype alkalmazásban:


![Az iOS-eszköz a PIN-kódot kérő felületét bemutató képernyőkép](../media/appmanagement/iOS_AppPINPrompt.png)

Az **Intune-felügyeletre regisztrált** eszközöknél üzenet jelenik meg, amely tájékoztatja a végfelhasználót, hogy az alkalmazás mostantól felügyelet alatt áll:

![„A munkahely kezeli” üzenetet és a PIN-kód megadását kérő felületet megjelenítő képernyőkép az iOS-eszközön](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  A többszörös identitást támogató alkalmazások használata

A MAM-szabályzatokat csak akkor érvényesíti a rendszer, ha az alkalmazást munkahelyi környezetben használják, így az alkalmazás működése a kontextustól (munkahelyi vagy személyes használat) függően eltérő lehet.  

A több identitást támogató alkalmazások esetében az Intune csak akkor alkalmazza a MAM-szabályzatokat, amikor a végfelhasználó a munkahelyi környezetben használja az alkalmazást.  Például a munkahelyi adatok elérésekor a rendszer felszólítja a végfelhasználót a PIN-kód megadására.  Az **Outlook alkalmazásnál** a végfelhasználó az alkalmazás indításakor kap kérést a PIN-kód megadására. A **OneDrive alkalmazásnál** ez akkor fordul elő, amikor a végfelhasználó beírja a munkahelyi fiókot.  A Microsoft **Word**, a **PowerPoint*, és az **Excel** esetében ez akkor történik meg, amikor a végfelhasználó a vállalat OneDrive vállalati helyén tárolt dokumentumokat nyit meg.
##  Felhasználói fiókok kezelése az eszközön

Az Intune a MAM-szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a második felhasználó blokkolva lesz vagy nem lesz blokkolva az eszközön. Minden esetben azonban csak a MAM-szabályzatokat megkapó első felhasználóra lesznek érvényesek a szabályzatok.
  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de a MAM-szabályzatok nem érvényesek a második felhasználói fiókra.  

  * A **OneDrive és az Outlook alkalmazáshoz** csak egy munkahelyi fiókot használhat.  A további munkahelyi fiókok hozzáadását ezek az alkalmazások blokkolják.  Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.

* Ha egy eszközhöz több meglévő felhasználói fiók tartozik a MAM-szabályzatok telepítése előtt, az Intune MAM-szabályzatai azt a fiókot kezelik, amelyikre elsőként lettek telepítve a MAM-szabályzatok.


A következő példák részletesen bemutatják, hogyan történik a több felhasználói fiók kezelése.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja a MAM-szabályzatok telepítéséhez. Az **X vállalat** telepíti elsőként a MAM-szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja a MAM-szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy a MAM-szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.
### Második fiók hozzáadása

Ha iOS-eszközt használ, és egy második munkahelyi fiókot próbál felvenni ugyanazon az eszközön, blokkoló üzenet jelenhet meg.  Megjelennek a fiókok, és Ön kiválaszthatja, hogy melyiket kívánja eltávolítani.

![Képernyőfelvétel a blokkolási üzenetről és az Igen és a Nem lehetőségről](../media/AppManagement/iOS_SwitchUser.PNG)
## További lépések
[Mi történik, ha az Android-alkalmazást MAM-szabályzatok felügyelik?](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### További információ
[Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


