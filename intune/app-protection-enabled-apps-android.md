---
title: "Android-alkalmazások alkalmazásvédelmi szabályzatokkal"
titlesuffix: Azure portal
description: "Ez a témakör azt ismerteti, hogy milyen hatással vannak az Android-alkalmazásokra az alkalmazásvédelmi szabályzatok.”"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d6fce4a48245bc8ba7533380fa5a365d44705ee
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok? 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör az alkalmazásvédelmi szabályzatokkal védett alkalmazások felhasználói élményét ismerteti. Az alkalmazásvédelmi szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkakörnyezetben használják: például amikor a munkahelyi fiókkal fér hozzá alkalmazásokhoz, vagy ha a cég OneDrive Vállalati verzióbeli helyén tárolt fájlokhoz fér hozzá.
##  <a name="accessing-apps"></a>Alkalmazásokhoz való hozzáférés

Androidos eszközökön minden alkalmazásvédelmi szabályzathoz rendelt alkalmazás esetén szükség van a Céges portál alkalmazásra.

Az Intune-ban nem regisztrált eszközökre telepíteni kell a Céges portál alkalmazást, a felhasználónak azonban nem kell elindítania vagy bejelentkeznie ahhoz, hogy alkalmazásvédelmi szabályzatokkal felügyelt alkalmazást használjon.
A Vállalati portál alkalmazás segítségével az Intune biztonságos helyen tudja megosztani az adatokat, emiatt ez akkor is követelmény, ha az eszköz nincs regisztrálva az Intune-ban.


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
####  <a name="android"></a>Android
Android-eszközön blokkoló üzenet jelenhet meg, amely ismerteti a meglévő fiók eltávolításának és új fiók felvételének lépéseit.  A meglévő fiók eltávolításához válassza a **Beállítások &gt;Általános &gt; Alkalmazáskezelő &gt;Vállalati portál, végül az Adatok törlése** lehetőséget.

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
|**pfile**|**text**|
|----|----|
|A pfile egy olyan általános „burkoló” formátum a védett fájloknak, amely magában foglalja a titkosított tartalmakat és az Azure Information Protection-licenceket, és bármilyen fájltípus védelmére használható.|A szövegfájlok, beleértve az XML, a CSV és a hasonló típusú fájlokat, akkor is megnyithatók az alkalmazásban, ha védelem alatt állnak. Fájltípusok: txt ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## <a name="next-steps"></a>További lépések
[Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>További információ
[Alkalmazásvédelmi szabályzatok létrehozása és telepítése a Microsoft Intune-ban](app-protection-policies.md)
