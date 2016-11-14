---
title: "Android-alkalmazások MAM-szabályzatokkal | Microsoft Intune"
description: "Ez a témakör bemutatja, mire számítson, ha az alkalmazását mobilalkalmazás-felügyeleti szabályzatok felügyelik."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 546b909737b4ea34bd747880fe8ed2d366c6b18a


---

# Mi várható az Android-alkalmazás MAM-szabályzatok általi kezelésekor
Ez a témakör a MAM-szabályzatokat használó alkalmazásokkal kapcsolatos végfelhasználói élményt ismerteti. A mobilalkalmazás-kezelési (MAM) szabályzatok csak akkor kerülnek alkalmazásra, amikor az alkalmazások munkakörnyezetben vannak használva: például amikor a munkahelyi fiókkal fér hozzá alkalmazásokhoz, vagy ha a vállalata OneDrive vállalati helyén tárolt fájlokhoz fér hozzá.
##  Alkalmazásokhoz való hozzáférés

A Vállalati portál alkalmazásra szükség van a MAM-szabályzatokhoz hozzárendelt összes alkalmazáshoz az Android-eszközökön.

Olyan eszközökön, melyek nincsenek regisztrálva az Intune-ban, a Vállalati portál alkalmazásnak telepítve kell lennie. Azonban a felhasználónak nem kell elindítania vagy bejelentkeznie a Vállalati portál alkalmazásba a MAM-szabályzatok által kezelt alkalmazások használatához.
A Vállalati portál alkalmazás segítségével az Intune biztonságos helyen tudja megosztani az adatokat, emiatt ez akkor is követelmény, ha az eszköz nincs regisztrálva az Intune-ban.


##  A többszörös identitást támogató alkalmazások használata

A MAM-szabályzatok csak az alkalmazások munkakörnyezetben való használatakor kerülnek alkalmazásra, így a környezettől függően két különböző alkalmazásműködést figyelhet meg: munkahelyi vagy személyes.

Többszörös identitást támogató alkalmazások esetén az Intune csak akkor alkalmazza a MAM-szabályzatokat, amikor a végfelhasználó munkakörnyezetben használja az alkalmazást.  Például a munkaadathoz való hozzáférésekor a végfelhasználónak PIN-kódot kell megadnia.  Az **Outlook alkalmazás** esetén a végfelhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazás** esetén ez akkor fordul elő, amikor a végfelhasználó beírja a munkahelyi fiókot.  A Microsoft **Word**, **PowerPoint*, és **Excel** esetén ez akkor fordul elő, amikor a végfelhasználó a vállalat OneDrive vállalati helyén tárolt dokumentumhoz fér hozzá.
##  Felhasználói fiókok kezelése az eszközön

Az Intune a MAM-szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a második felhasználó blokkolva lesz vagy nem lesz blokkolva az eszközön. Minden esetben azonban csak a MAM-szabályzatokat megkapó első felhasználóra lesznek érvényesek a szabályzatok.

  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de a MAM-szabályzatok nem érvényesek a második felhasználói fiókra.

  * A **OneDrive és az Outlook alkalmazáshoz** csak egy munkahelyi fiókot használhat.  A további munkahelyi fiókok hozzáadását ezek az alkalmazások blokkolják.  Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.


* Ha egy eszközhöz több meglévő felhasználói fiók tartozik a MAM-szabályzatok telepítése előtt, az Intune MAM-szabályzatai azt a fiókot kezelik, amelyikre elsőként lettek telepítve a MAM-szabályzatok.


A következő példák részletesen bemutatják, hogyan történik a több felhasználói fiók kezelése.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja a MAM-szabályzatok telepítéséhez. Az **X vállalat** telepíti elsőként a MAM-szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja a MAM-szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy a MAM-szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.
### Második fiók hozzáadása
####  Android
Android-eszközön blokkoló üzenet jelenhet meg, amely ismerteti a meglévő fiók eltávolításának és új fiók felvételének lépéseit.  A meglévő fiók eltávolításához válassza a **Beállítások &gt;Általános &gt; Alkalmazáskezelő &gt;Vállalati portál, végül az Adatok törlése** lehetőséget.

![Képernyőfelvétel a hibaüzenetről és a fiók eltávolítására vonatkozó utasításokról](../media/AppManagement/Android_SwitchUser.png)

##  Médiafájlok megtekintése az Azure Information Protection alkalmazással (korábbi nevén Rights Management megosztóalkalmazással)
A vállalati AV-, PDF- és képfájlok Android-eszközökön való megtekintéséhez használja az [Azure Information Protection alkalmazást](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Ezt az alkalmazást a Google Play áruházból töltheti le.  

A rendszer a következő fájltípusokat támogatja:

* **Hang:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (kibővített AAC+), AAC ELD (kibővített, alacsony késleltetésű AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Vorbis, PCM/WAVE.
* **Videó:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Kép:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Dokumentumok:** PDF, PPDF

------------
|**pfile**|**szöveg**|
|----|----|
|A pfile egy olyan általános „burkoló” formátum a védett fájloknak, amely magában foglalja a titkosított tartalmakat és az Azure Information Protection-licenceket, és bármilyen fájltípus védelmére használható.|A szövegfájlok, beleértve az XML, a CSV és a hasonló típusú fájlokat, akkor is megnyithatók az alkalmazásban, ha védelem alatt állnak. Fájltípusok: txt ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## További lépések
[Mi várható az iOS-alkalmazás MAM-szabályzatok általi kezelésekor](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### További információ
[Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


