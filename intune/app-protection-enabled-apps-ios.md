---
title: "iOS-alkalmazások alkalmazásvédelmi szabályzatokkal"
titleSuffix: Intune on Azure
description: "Ez a témakör azt ismerteti, hogy milyen hatással vannak az iOS-alkalmazásokra az alkalmazásvédelmi szabályzatok.”"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4527e82ae9fa7226a0b7753111886882d85801e3
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2017
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Milyen hatással vannak az iOS-alkalmazásokra az alkalmazásvédelmi szabályzatok?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör az alkalmazásvédelmi szabályzatokkal védett alkalmazások felhasználói élményét ismerteti. Az alkalmazásvédelmi szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkakörnyezetben használják: például amikor a munkahelyi fiókkal fér hozzá alkalmazásokhoz, vagy ha a cég OneDrive Vállalati verzióbeli helyén tárolt fájlokhoz fér hozzá.
##  <a name="accessing-apps"></a>Alkalmazásokhoz való hozzáférés

Ha az eszköz **nincs regisztrálva az Intune-ban**, a rendszer az alkalmazás első használatakor felkéri a felhasználót, hogy indítsa újra az alkalmazást.  Az újraindítás azért szükséges, hogy a rendszer alkalmazni tudja az alkalmazásvédelmi szabályzatokat az alkalmazásra. Az alábbi képernyőképen ezt láthatja a Skype alkalmazásban:


![Az iOS-eszköz a PIN-kódot kérő felületét bemutató képernyőkép](./media/ios-pin-prompt.png)

Az **Intune-felügyeletre regisztrált** eszközöknél üzenet jelenik meg, amely tájékoztatja a végfelhasználót, hogy az alkalmazás mostantól felügyelet alatt áll:

![„A munkahely kezeli” üzenetet és a PIN-kód megadását kérő felületet megjelenítő képernyőkép az iOS-eszközön](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>A többszörös identitást támogató alkalmazások használata

Az alkalmazásvédelmi szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkakörnyezetben használják, így az alkalmazásnak a környezettől függően két különböző működése figyelhető meg: munkahelyi vagy személyes.  

Az Intune többszörös identitást támogató alkalmazásokra csak akkor alkalmaz alkalmazásvédelmi szabályzatokat, amikor a végfelhasználó a munkahelyi környezetben használja az alkalmazást.  Például a munkaadathoz való hozzáférésekor a végfelhasználónak PIN-kódot kell megadnia.  Az **Outlook alkalmazás** esetén a végfelhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazásnál** ez akkor fordul elő, amikor a végfelhasználó beírja a munkahelyi fiókot.  A Microsoft **Word**, **PowerPoint* és **Excel** esetén ez akkor fordul elő, amikor a végfelhasználó a cég OneDrive vállalati helyén tárolt dokumentumhoz fér hozzá.
##  <a name="managing-user-accounts-on-the-device"></a>Felhasználói fiókok kezelése az eszközön

Az Intune az alkalmazásvédelmi szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a második felhasználó blokkolva lesz vagy nem lesz blokkolva az eszközön. Ugyanakkor az alkalmazásvédelmi szabályzatok minden esetben csak arra a felhasználóra lesznek érvényesek, aki először kapja meg a szabályzatokat.
  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de az alkalmazásvédelmi szabályzatok nem érvényesek a második felhasználói fiókra.  

  * A **OneDrive és az Outlook alkalmazáshoz** csak egy munkahelyi fiókot használhat.  A további munkahelyi fiókok hozzáadását ezek az alkalmazások blokkolják.  Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.

* Ha egy eszközhöz több meglévő felhasználói fiók tartozik az alkalmazásvédelmi szabályzatok telepítése előtt, az Intune alkalmazásvédelmi szabályzatai azt a fiókot kezelik, amelyikre elsőként lettek telepítve az alkalmazásvédelmi szabályzatok.


A következő példák részletesen bemutatják, hogyan történik a több felhasználói fiók kezelése.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja alkalmazásvédelmi szabályzatok telepítéséhez. Az **X vállalat** telepít elsőként alkalmazásvédelmi szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja az alkalmazásvédelmi szabályzatot, de az Y vállalathoz tartozó fiók nem. Ha azt szeretné, hogy az alkalmazásvédelmi szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.
### <a name="adding-a-second-account"></a>Második fiók hozzáadása

Ha iOS-eszközt használ, és egy második munkahelyi fiókot próbál felvenni ugyanazon az eszközön, blokkoló üzenet jelenhet meg.  Megjelennek a fiókok, és Ön kiválaszthatja, hogy melyiket kívánja eltávolítani.

![Képernyőfelvétel a blokkolási üzenetről és az Igen és a Nem lehetőségről](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>További lépések
[Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>További információ
[Alkalmazásvédelmi szabályzatok létrehozása és telepítése a Microsoft Intune-ban](app-protection-policies.md)
