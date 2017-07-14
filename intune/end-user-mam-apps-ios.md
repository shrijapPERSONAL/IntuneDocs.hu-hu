---
title: "iOS-alkalmazások alkalmazásvédelmi szabályzatokkal"
description: "Ez a témakör azt ismerteti, hogy milyen hatással vannak az iOS-alkalmazásokra az alkalmazásvédelmi szabályzatok."
keywords: 
author: barlanmsft
ms.author: barlan
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
ms.openlocfilehash: e66042e5198b76ec484fe0218127acb653394cce
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2017
---
# Milyen hatással vannak az iOS-alkalmazásokra az alkalmazásvédelmi szabályzatok?
<a id="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

 Ez a témakör az olyan alkalmazásokkal kapcsolatos felhasználói élményt ismerteti, melyekre alkalmazásvédelmi szabályzatok vannak alkalmazva. Az alkalmazásvédelmi szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkahelyi környezetben használják; például ha a felhasználó munkahelyi fiókkal fér hozzá az alkalmazásokhoz, vagy a cég OneDrive Vállalati verzióbeli helyén tárolt fájlokhoz fér hozzá.

##  Alkalmazások elérése
<a id="access-apps" class="xliff"></a>

Ha az eszköz **nincs regisztrálva az Intune-ban**, a rendszer az alkalmazás első használatakor felkéri a felhasználót, hogy indítsa újra az alkalmazást. Az újraindítás azért szükséges, hogy a rendszer alkalmazni tudja az alkalmazásvédelmi szabályzatokat az alkalmazásra.

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Az **Intune-felügyeletre regisztrált** eszközöknél üzenet jelenik meg, amely tájékoztatja a felhasználót, hogy az alkalmazás mostantól felügyelet alatt áll.

##  A többszörös identitást támogató alkalmazások használata
<a id="use-apps-with-multi-identity-support" class="xliff"></a>

A több identitást támogató alkalmazások esetében az alkalmazás különböző (munkahelyi és személyes) fiókokkal is elérhető, ilyenkor az alkalmazásvédelmi szabályzatokat csak az alkalmazások munkahelyi környezetben való használata esetén alkalmazza a rendszer.  

Például a munkahelyi adatok elérésekor a felhasználónak PIN-kódot kell megadnia. Az **Outlook alkalmazás** esetében a felhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazás** esetében a felhasználónak a munkahelyi fiók beírásakor kell megadnia a PIN-kódot.  A Microsoft **Word**, a **PowerPoint** és az **Excel** esetében a felhasználónak akkor kell megadnia a PIN-kódot, ha a vállalat OneDrive vállalati helyén tárolt dokumentumhoz szeretne hozzáférni.

- További információ azon alkalmazásokról, amelyek támogatják az [MAM-et és a többszörös identitást](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) az Intune-nal.

Az alkalmazásvédelmi szabályzatokat a rendszer csak a munkahelyi használat esetén alkalmazza. Ez azt jelenti, hogy az alkalmazás eltérő módon működhet, attól függően, hogy munkahelyi vagy személyes célokra használják.

##  Felhasználói fiókok kezelése az eszközön
<a id="manage-user-accounts-on-the-device" class="xliff"></a>

Az Intune az alkalmazásvédelmi szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a rendszer akár le is tilthatja a második felhasználót az eszközön. Ugyanakkor az alkalmazásvédelmi szabályzatok minden esetben csak arra a felhasználóra lesznek érvényesek, aki először kapja meg a szabályzatokat.
  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de az alkalmazásvédelmi szabályzatok nem érvényesek a második felhasználói fiókra.  

  * A **OneDrive** és az **Outlook alkalmazásokban** csak egy munkahelyi fiókot használhat. Ezeknél az alkalmazásoknál nincs lehetőség további munkahelyi fiókok beállítására. Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.

* Ha egy eszközhöz több meglévő felhasználói fiók tartozik az alkalmazásvédelmi szabályzatok telepítése előtt, az Intune alkalmazásvédelmi szabályzatai azt a fiókot kezelik, amelyikre elsőként lettek telepítve az alkalmazásvédelmi szabályzatok.


A következő példák részletesen bemutatják, hogy a rendszer hogyan kezeli a további felhasználói fiókokat.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja alkalmazásvédelmi szabályzatok telepítéséhez. Az **X vállalat** telepít elsőként alkalmazásvédelmi szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja az alkalmazásvédelmi szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy az alkalmazásvédelmi szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.

### Második fiók hozzáadása
<a id="add-a-second-account" class="xliff"></a>

Ha iOS-eszközt használ, és egy második munkahelyi fiókot szeretne felvenni ezen az eszközön, a blokkolásról tájékoztató üzenet jelenhet meg. Megjelennek a fiókok, és Ön kiválaszthatja, hogy melyiket kívánja eltávolítani.

## További lépések
<a id="next-steps" class="xliff"></a>
[Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](end-user-mam-apps-android.md)
