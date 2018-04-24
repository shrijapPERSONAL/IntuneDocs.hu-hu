---
title: iOS-alkalmazások alkalmazásvédelmi szabályzatokkal
titlesuffix: Microsoft Intune
description: A védelmi szabályzatokkal rendelkező iOS-alkalmazások várható működésének ismertetése.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2804003a0f1acac56ecaae5e24dcf34b4eb0c256
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Milyen hatással vannak az iOS-alkalmazásokra az alkalmazásvédelmi szabályzatok?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az alkalmazásvédelmi szabályzatokkal védett iOS-alkalmazások felhasználói élményének ismertetése. Az alkalmazásvédelmi szabályzatok csak akkor lépnek érvénybe, ha az adott alkalmazásokat munkahelyi környezetben használják. Például akkor, ha egy munkahelyi fiókkal fér hozzá egy alkalmazáshoz, vagy ha a cég OneDrive-tárhelyén található fájlokhoz fér hozzá.
##  <a name="accessing-apps"></a>Alkalmazásokhoz való hozzáférés

Ha az eszköz **nincs regisztrálva az Intune-ban**, a rendszer az alkalmazás első használatakor felkéri a felhasználót, hogy indítsa újra az alkalmazást.  Az újraindítás azért szükséges, hogy a rendszer alkalmazni tudja az alkalmazásvédelmi szabályzatokat az alkalmazásra. Az alábbi képernyőképen ezt láthatja a Skype alkalmazásban:


![Az iOS-eszköz a PIN-kódot kérő felületét bemutató képernyőkép](./media/ios-pin-prompt.png)

Az **Intune-kezelésre regisztrált** eszközöknél üzenet jelenik meg, amely tájékoztatja a felhasználót, hogy az alkalmazás mostantól felügyelet alatt áll:

![„A munkahely kezeli” üzenetet és a PIN-kód megadását kérő felületet megjelenítő képernyőkép az iOS-eszközön](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>A többszörös identitást támogató alkalmazások használata

Az alkalmazásvédelmi szabályzatok csak akkor lépnek hatályba, amikor egy felhasználó munkához kapcsolódó adatokhoz próbál meg hozzáférni.  A működés eltérő lehet, ha a felhasználó személyes használatra nyitja meg az alkalmazást. 

A többszörös identitást támogató alkalmazások esetében az Intune csak akkor alkalmaz alkalmazásvédelmi szabályzatokat, ha egy felhasználó munkahelyi adatokhoz fér hozzá.  A rendszer például bekérheti a felhasználótól a PIN-kódot.  Az **Outlook alkalmazásban** akkor jelenik meg adatkérdés, ha egy felhasználó elindítja az alkalmazást. A **OneDrive alkalmazásban** akkor jelenik meg adatkérdés, ha egy felhasználó megadja a munkahelyi fiókot.  A Microsoft **Word**, **PowerPoint** és **Excel** alkalmazásban akkor jelenik meg adatkérdés, ha egy felhasználó a céges OneDrive-on található dokumentumokhoz fér hozzá.
##  <a name="managing-user-accounts-on-the-device"></a>Felhasználói fiókok kezelése az eszközön

Az Intune az alkalmazásvédelmi szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a második felhasználó blokkolva lesz vagy nem lesz blokkolva az eszközön. Ugyanakkor az alkalmazásvédelmi szabályzatok minden esetben csak arra a felhasználóra lesznek érvényesek, aki először kapja meg a szabályzatokat.
  * A **Microsoft Word**, **Excel** és **PowerPoint** alkalmazás nem tiltja le egy további felhasználói fiók elérését. Erre a felhasználói fiókra azonban nem lesznek érvényesek az alkalmazásvédelmi szabályzatok.

  * A **OneDrive és az Outlook alkalmazáshoz** csak egy munkahelyi fiókot használhat.  A további munkahelyi fiókok hozzáadását ezek az alkalmazások blokkolják.  A felhasználók ugyanakkor eltávolíthatók az eszközökről, és ezután hozzáadható egy másik felhasználó az adott eszközön.

* Az alkalmazásvédelmi szabályzatok érvénybe léptetése előtt egy adott eszközön több meglévő felhasználói fiók is lehet. Ebben az esetben az Intune alkalmazásvédelmi szabályzatai az első olyan fiókot fogják felügyelni, melyre vonatkozóan a rendszer érvénybe lépteti az alkalmazásvédelmi szabályzatokat.


A következő példa ismerteti, hogyan kezel az Intune több felhasználói fiókot.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja alkalmazásvédelmi szabályzatok telepítéséhez. Az **X vállalat** telepít elsőként alkalmazásvédelmi szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja az alkalmazásvédelmi szabályzatot, de az Y vállalathoz tartozó fiók nem. Ahhoz, hogy az alkalmazásvédelmi szabályzatok az Y vállalat felhasználói fiókját kezeljék, az A felhasználónak el kell távolítania az X vállalat felhasználói fiókját.
### <a name="adding-a-second-account"></a>Második fiók hozzáadása

Ha iOS-eszközt használ, és egy második munkahelyi fiókot próbál felvenni ugyanazon az eszközön, blokkoló üzenet jelenhet meg.  Megjelennek a fiókok, és Ön kiválaszthatja, hogy melyiket kívánja eltávolítani.

![Képernyőfelvétel a blokkolási üzenetről és az Igen és a Nem lehetőségről](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>További lépések
[Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Lásd még:
[Alkalmazásvédelmi szabályzatok létrehozása és telepítése a Microsoft Intune-ban](app-protection-policies.md)
