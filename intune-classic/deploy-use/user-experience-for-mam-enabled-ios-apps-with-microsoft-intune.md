---
title: "iOS-alkalmazások alkalmazásvédelmi szabályzatokkal | Microsoft Docs"
description: "Ez a témakör azt ismerteti, hogy milyen hatással vannak az iOS-alkalmazásokra az alkalmazásvédelmi szabályzatok."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 92a91fab353c78c751ae5eb25c9853df5cbcfe53
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Milyen hatással vannak az iOS-alkalmazásokra az alkalmazásvédelmi szabályzatok?

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 Ez a témakör az olyan alkalmazásokkal kapcsolatos felhasználói élményt ismerteti, melyekre alkalmazásvédelmi szabályzatok vannak alkalmazva. Az alkalmazásvédelmi szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkahelyi környezetben használják; például ha a felhasználó munkahelyi fiókkal fér hozzá az alkalmazásokhoz, vagy a cég OneDrive Vállalati verzióbeli helyén tárolt fájlokhoz fér hozzá.

##  <a name="access-apps"></a>Alkalmazások elérése

Ha az eszköz **nincs regisztrálva az Intune-ban**, a rendszer az alkalmazás első használatakor felkéri a felhasználót, hogy indítsa újra az alkalmazást. Az újraindítás azért szükséges, hogy a rendszer alkalmazni tudja az alkalmazásvédelmi szabályzatokat az alkalmazásra. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Az **Intune-felügyeletre regisztrált** eszközöknél üzenet jelenik meg, amely tájékoztatja a felhasználót, hogy az alkalmazás mostantól felügyelet alatt áll.

##  <a name="use-apps-with-multi-identity-support"></a>A többszörös identitást támogató alkalmazások használata

A több identitást támogató alkalmazások esetében az alkalmazás különböző (munkahelyi és személyes) fiókokkal is elérhető, ilyenkor az alkalmazásvédelmi szabályzatokat csak az alkalmazások munkahelyi környezetben való használata esetén alkalmazza a rendszer.  

Például a munkahelyi adatok elérésekor a felhasználónak PIN-kódot kell megadnia. Az **Outlook alkalmazás** esetében a felhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazás** esetében a felhasználónak a munkahelyi fiók beírásakor kell megadnia a PIN-kódot.  A Microsoft **Word**, a **PowerPoint** és az **Excel** esetében a felhasználónak akkor kell megadnia a PIN-kódot, ha a vállalat OneDrive vállalati helyén tárolt dokumentumhoz szeretne hozzáférni.

- További információ azon alkalmazásokról, amelyek támogatják az [MAM-et és a többszörös identitást](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) az Intune-nal.

Az alkalmazásvédelmi szabályzatokat a rendszer csak a munkahelyi használat esetén alkalmazza. Ez azt jelenti, hogy az alkalmazás eltérő módon működhet, attól függően, hogy munkahelyi vagy személyes célokra használják.

##  <a name="manage-user-accounts-on-the-device"></a>Felhasználói fiókok kezelése az eszközön

Az Intune az alkalmazásvédelmi szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a rendszer akár le is tilthatja a második felhasználót az eszközön. Ugyanakkor az alkalmazásvédelmi szabályzatok minden esetben csak arra a felhasználóra lesznek érvényesek, aki először kapja meg a szabályzatokat.
  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de az alkalmazásvédelmi szabályzatok nem érvényesek a második felhasználói fiókra.  

  * A **OneDrive** és az **Outlook alkalmazásokban** csak egy munkahelyi fiókot használhat. Ezeknél az alkalmazásoknál nincs lehetőség további munkahelyi fiókok beállítására. Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.

* Ha egy eszközhöz több meglévő felhasználói fiók tartozik az alkalmazásvédelmi szabályzatok telepítése előtt, az Intune alkalmazásvédelmi szabályzatai azt a fiókot kezelik, amelyikre elsőként lettek telepítve az alkalmazásvédelmi szabályzatok.


A következő példák részletesen bemutatják, hogy a rendszer hogyan kezeli a további felhasználói fiókokat.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja alkalmazásvédelmi szabályzatok telepítéséhez. Az **X vállalat** telepít elsőként alkalmazásvédelmi szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja az alkalmazásvédelmi szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy az alkalmazásvédelmi szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.

### <a name="add-a-second-account"></a>Második fiók hozzáadása

Ha iOS-eszközt használ, és egy második munkahelyi fiókot szeretne felvenni ezen az eszközön, a blokkolásról tájékoztató üzenet jelenhet meg. Megjelennek a fiókok, és Ön kiválaszthatja, hogy melyiket kívánja eltávolítani.

## <a name="next-steps"></a>További lépések
[Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>További információ
[Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

