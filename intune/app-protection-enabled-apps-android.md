---
title: Android-alkalmazások alkalmazásvédelmi szabályzatokkal
titlesuffix: Microsoft Intune
description: A védelmi szabályzatokkal rendelkező Android-alkalmazások várható működésének ismertetése.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16cef0b3e72c2e7815aada1c45c0e312b84931ab
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
ms.locfileid: "31833017"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok? 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az alkalmazásvédelmi szabályzatokkal rendelkező Android-alkalmazások várható működésének ismertetése. Az alkalmazásvédelmi szabályzatok csak akkor lépnek érvénybe, ha az adott alkalmazásokat munkahelyi környezetben használják. Például akkor, ha egy munkahelyi fiókkal fér hozzá egy alkalmazáshoz, vagy ha a cég OneDrive-tárhelyén található fájlokhoz fér hozzá.
##  <a name="accessing-apps"></a>Alkalmazásokhoz való hozzáférés

Minden Android rendszerű eszközökön található és alkalmazásvédelmi szabályzattal rendelkező alkalmazáshoz szükség van a Céges portál alkalmazásra.

Minden olyan eszközön telepítse a Céges portált, amely nincs regisztrálva az Intune-ban. A felhasználóknak az alkalmazásvédelmi szabályzatokkal rendelkező alkalmazások használatához nem szükséges bejelentkezniük a Céges portál alkalmazásba.
A Céges portál alkalmazás lehetővé teszi az adatok biztonságos helyen való megosztását. Ezért a használata még nem regisztrált eszközök esetében is kötelező.


##  <a name="using-apps-with-multi-identity-support"></a>A többszörös identitást támogató alkalmazások használata

Az alkalmazásvédelmi szabályzatok csak akkor lépnek hatályba, amikor egy felhasználó munkához kapcsolódó adatokhoz próbál meg hozzáférni.  A működés eltérő lehet, ha a felhasználó személyes használatra nyitja meg az alkalmazást.

Egyes alkalmazások támogatják a többszörös identitás használatát. Ebben az esetben az Intune csak akkor alkalmazza az alkalmazásvédelmi szabályzatokat, ha egy felhasználó munkahelyi adatokhoz fér hozzá.  A rendszer például bekérheti a felhasználótól a PIN-kódot.  Az **Outlook alkalmazásban** akkor jelenik meg adatkérdés, ha egy felhasználó elindítja az alkalmazást. A **OneDrive alkalmazásban** akkor jelenik meg adatkérdés, ha egy felhasználó megadja a munkahelyi fiókot.  A Microsoft **Word**, **PowerPoint** és **Excel** alkalmazásban akkor jelenik meg adatkérdés, ha egy felhasználó a céges OneDrive-on található dokumentumokhoz fér hozzá.
##  <a name="managing-user-accounts-on-the-device"></a>Felhasználói fiókok kezelése az eszközön

Az Intune az alkalmazásvédelmi szabályzatok telepítését eszközönként egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a második felhasználó blokkolva lesz vagy nem lesz blokkolva az eszközön. Ugyanakkor az alkalmazásvédelmi szabályzatok minden esetben csak arra a felhasználóra lesznek érvényesek, aki először kapja meg a szabályzatokat.

  * A **Microsoft Word**, **Excel** és **PowerPoint** alkalmazás nem tiltja le egy további felhasználói fiók elérését. Erre a felhasználói fiókra azonban nem lesznek érvényesek az alkalmazásvédelmi szabályzatok.

  * A **OneDrive és az Outlook alkalmazáshoz** csak egy munkahelyi fiókot használhat.  A további munkahelyi fiókok hozzáadását ezek az alkalmazások blokkolják.  A felhasználók ugyanakkor eltávolíthatók az eszközökről, és ezután hozzáadható egy másik felhasználó az adott eszközön.


* Az alkalmazásvédelmi szabályzatok érvénybe léptetése előtt egy adott eszközön több meglévő felhasználói fiók is lehet. Ebben az esetben az Intune alkalmazásvédelmi szabályzatai az első olyan fiókot fogják felügyelni, melyre vonatkozóan a rendszer érvénybe lépteti az alkalmazásvédelmi szabályzatokat.


A következő példa ismerteti, hogyan kezel az Intune több felhasználói fiókot.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja alkalmazásvédelmi szabályzatok telepítéséhez. Az **X vállalat** telepít elsőként alkalmazásvédelmi szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja az alkalmazásvédelmi szabályzatot, de az Y vállalathoz tartozó fiók nem. Ahhoz, hogy az alkalmazásvédelmi szabályzatok az Y vállalat felhasználói fiókját kezeljék, az A felhasználónak el kell távolítania az X vállalat felhasználói fiókját.
### <a name="adding-a-second-account"></a>Második fiók hozzáadása
####  <a name="android"></a>Android
A rendszer kérheti, hogy távolítsa el a meglévő fiókot, és új fiókot vegyen fel.  A meglévő fiók eltávolításához válassza a **Beállítások &gt;Általános &gt; Alkalmazáskezelő &gt;Munkahelyi portál lehetőséget, majd válassza az Adatok törlése lehetőséget.**

![Képernyőfelvétel a hibaüzenetről és a fiók eltávolítására vonatkozó utasításokról](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Médiafájlok megtekintése az Azure Information Protection alkalmazással (korábbi nevén Rights Management megosztóalkalmazással)
A vállalati AV-, PDF- és képfájlok Android-eszközökön való megtekintéséhez használja az [Azure Information Protection alkalmazást](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Ezt az alkalmazást a Google Play áruházból töltheti le.  

A rendszer a következő fájltípusokat támogatja:

* **Hang:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (kibővített AAC+), AAC ELD (kibővített, alacsony késleltetésű AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Vorbis, PCM/WAVE.
* **Videó:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Kép:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Dokumentumok:** PDF, PPDF

------------

|                                                                                 <strong>pfile</strong>                                                                                 |                                                                      <strong>text</strong>                                                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A Pfile egy általános „burkoló” formátum védett fájlok számára. Magába foglalja a titkosított tartalmat és az Azure Information Protection-licenceket. Ez bármilyen fájltípus védelmére használható. | A szövegfájlok, beleértve az XML, a CSV és a hasonló típusú fájlokat, akkor is megnyithatók az alkalmazásban, ha védelem alatt állnak. Fájltípusok: txt ptxt, csv, pcsv, log, plog, xml, pxml. |

---------------
## <a name="next-steps"></a>További lépések
[Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Lásd még:
[Alkalmazásvédelmi szabályzatok létrehozása és telepítése a Microsoft Intune-ban](app-protection-policies.md)
