---
title: "iOS-alkalmazások felügyelete MAM-szabályzatokkal | Microsoft Intune"
description: "Ez a témakör bemutatja, mire számítson, ha iOS-alkalmazását mobilalkalmazás-felügyeleti szabályzatok felügyelik."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 3aa6728036ff66ea489176063af2d136bef4c7cc


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-mam-policies"></a>Mi várható az iOS-alkalmazás MAM-szabályzatok általi kezelésekor
 Ez a témakör a mobilalkalmazás-felügyeleti szabályzatokat használó alkalmazásokkal kapcsolatos felhasználói élményt ismerteti. A MAM-szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkahelyi környezetben használják: például amikor egy munkahelyi fiókkal fér hozzá az alkalmazásokhoz, vagy a vállalata OneDrive vállalati helyén tárolt fájlokhoz fér hozzá.

##  <a name="access-apps"></a>Alkalmazások elérése

Ha az eszköz **nincs regisztrálva az Intune-ban**, a rendszer az alkalmazás első használatakor felkéri a felhasználót, hogy indítsa újra az alkalmazást.  Az újraindítás azért szükséges, hogy a rendszer alkalmazni tudja a MAM-szabályzatokat. Az alábbi képernyőképen azt láthatja, hogy a Skype alkalmazás újraindítást kér:


![Az iOS-eszköz a PIN-kódot kérő felületét bemutató képernyőkép](../media/appmanagement/iOS_AppPINPrompt.png)

Az **Intune-felügyeletre regisztrált** eszközöknél üzenet jelenik meg, amely tájékoztatja a felhasználót, hogy az alkalmazás mostantól felügyelet alatt áll:

![Az iOS-eszközt bemutató képernyőkép, amelyen látható az üzenet, amely tájékoztatja a felhasználót, hogy az alkalmazást most már a vállalat felügyeli, és kéri a PIN-kód megadását](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  <a name="use-apps-with-multi-identity-support"></a>A többszörös identitást támogató alkalmazások használata

A MAM-szabályzatokat a rendszer csak a munkahelyi használat esetén alkalmazza. Ez azt jelenti, hogy az alkalmazás eltérő módon működik, attól függően, hogy munkahelyi vagy személyes célokra használják.

 Például a munkahelyi adatok elérésekor a felhasználónak PIN-kódot kell megadnia. Az **Outlook alkalmazás** esetében a felhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazás** esetében a felhasználónak a munkahelyi fiók beírásakor kell megadnia a PIN-kódot.  A Microsoft **Word**, a **PowerPoint** és az **Excel** esetében a felhasználónak akkor kell megadnia a PIN-kódot, ha a vállalat OneDrive vállalati helyén tárolt dokumentumhoz szeretne hozzáférni.

##  <a name="manage-user-accounts-on-the-device"></a>Felhasználói fiókok kezelése az eszközön

Az Intune a MAM-szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a rendszer akár le is tilthatja a második felhasználót az eszközön. Minden esetben azonban csak a MAM-szabályzatokat megkapó első felhasználóra lesznek érvényesek a szabályzatok.
  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de a MAM-szabályzatok nem érvényesek a második felhasználói fiókra.  

  * A **OneDrive** és az **Outlook alkalmazásokban** csak egy munkahelyi fiókot használhat. Ezeknél az alkalmazásoknál nincs lehetőség további munkahelyi fiókok beállítására. Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.

* Ha egy eszközhöz több felhasználói fiók tartozik a MAM-szabályzatok telepítése előtt, az Intune MAM-szabályzatai azt a fiókot kezelik, amelyikre elsőként telepítik a MAM-szabályzatokat.


A következő példák részletesen bemutatják, hogy a rendszer hogyan kezeli a további felhasználói fiókokat.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja a MAM-szabályzatok telepítéséhez. Az **X vállalat** telepíti elsőként a MAM-szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja a MAM-szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy a MAM-szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.

### <a name="add-a-second-account"></a>Második fiók hozzáadása

Ha iOS-eszközt használ, és egy második munkahelyi fiókot szeretne felvenni ezen az eszközön, a blokkolásról tájékoztató üzenet jelenhet meg. Megjelennek a fiókok, és Ön kiválaszthatja, hogy melyiket kívánja eltávolítani.

![Képernyőfelvétel a blokkolási üzenetről és az Igen és a Nem lehetőségről](../media/AppManagement/iOS_SwitchUser.PNG)
## <a name="next-steps"></a>További lépések
[Mi várható az Android-alkalmazás MAM-szabályzatok általi kezelésekor](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>További információ
[Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


