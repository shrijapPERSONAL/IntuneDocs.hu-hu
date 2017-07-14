---
title: "Android-alkalmazások alkalmazásvédelmi szabályzatokkal"
description: "Ez a témakör azt ismerteti, hogy milyen hatással vannak az alkalmazásokra az alkalmazásvédelmi szabályzatok."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 030e17a9f28a9476c82e89d4dd26151a2d3cb953
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2017
---
# Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?
<a id="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ez a témakör az alkalmazásvédelmi szabályzatokkal védett alkalmazások felhasználói élményét ismerteti. Az alkalmazásvédelmi szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkahelyi környezetben használják: például amikor egy munkahelyi fiókkal fér hozzá az alkalmazásokhoz, vagy a vállalata OneDrive vállalati helyén tárolt fájlokhoz fér hozzá.
##  Alkalmazások elérése
<a id="access-apps" class="xliff"></a>

Androidos eszközökön minden alkalmazásvédelmi szabályzathoz rendelt alkalmazás esetén szükség van a Céges portál alkalmazásra.

Azokon az eszközökön, amelyek nincsenek regisztrálva az Intune-ban, az eszközre telepíteni kell a Munkahelyi portál alkalmazást. A felhasználónak azonban nem kell elindítania a Céges portál alkalmazást, illetve nem kell bejelentkeznie az alkalmazásba ahhoz, hogy használhassa az alkalmazásvédelmi szabályzatok által felügyelt alkalmazásokat.

A Munkahelyi portál alkalmazás biztonságos helyet tesz elérhetővé az Intune számára, ahol a szolgáltatás megoszthatja az adatokat. A Céges portál alkalmazás ezért az összes alkalmazásvédelmi szabályzat alá vont alkalmazás esetében követelmény, még akkor is, ha maga az eszköz nincs regisztrálva az Intune-ban.


##  A többszörös identitást támogató alkalmazások használata
<a id="use-apps-with-multi-identity-support" class="xliff"></a>

Az alkalmazásvédelmi szabályzatokat a rendszer csak a munkahelyi használat esetén alkalmazza. Ez azt jelenti, hogy az alkalmazás eltérő módon működhet, attól függően, hogy munkahelyi vagy személyes célokra használják.

Például a munkahelyi adatok elérésekor a felhasználónak PIN-kódot kell megadnia. Az **Outlook alkalmazás** esetében a felhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazás** esetében a felhasználónak a munkahelyi fiók beírásakor kell megadnia a PIN-kódot. A Microsoft **Word**, a **PowerPoint** és az **Excel** esetében a felhasználónak akkor kell megadnia a PIN-kódot, ha a vállalat OneDrive vállalati helyén tárolt dokumentumhoz szeretne hozzáférni.

##  Felhasználói fiókok kezelése az eszközön
<a id="manage-user-accounts-on-the-device" class="xliff"></a>

Az Intune az alkalmazásvédelmi szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a rendszer akár le is tilthatja a második felhasználót az eszközön. Ugyanakkor az alkalmazásvédelmi szabályzatok minden esetben csak arra a felhasználóra lesznek érvényesek, aki először kapja meg a szabályzatokat.

  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de az alkalmazásvédelmi szabályzatok nem érvényesek a második felhasználói fiókra.

  * A **OneDrive** és az **Outlook alkalmazásokban** csak egy munkahelyi fiókot használhat.  Ezeknél az alkalmazásoknál nincs lehetőség további munkahelyi fiókok beállítására.  Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.


* Ha egy eszközhöz több meglévő felhasználói fiók tartozik az alkalmazásvédelmi szabályzatok telepítése előtt, az Intune alkalmazásvédelmi szabályzatai azt a fiókot kezelik, amelyikre elsőként lettek telepítve az alkalmazásvédelmi szabályzatok.


A következő példák részletesen bemutatják, hogy a rendszer hogyan kezeli a további felhasználói fiókokat.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja alkalmazásvédelmi szabályzatok telepítéséhez. Az **X vállalat** telepít elsőként alkalmazásvédelmi szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja az alkalmazásvédelmi szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy az alkalmazásvédelmi szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.
### Második fiók hozzáadása
<a id="add-a-second-account" class="xliff"></a>
####  Android
<a id="android" class="xliff"></a>
Android-eszközön blokkoló üzenet jelenhet meg, amely ismerteti a meglévő fiók eltávolításának és új fiók felvételének lépéseit.  A meglévő fiók eltávolításához válassza a **Beállítások &gt;Általános &gt; Alkalmazáskezelő &gt;Munkahelyi portál** lehetőséget, majd itt az **Adatok törlése** lehetőséget.

![Képernyőfelvétel a hibaüzenetről és a fiók eltávolítására vonatkozó utasításokról](./media/Android_SwitchUser.png)

##  Médiafájlok megtekintése az Azure Information Protection alkalmazással
<a id="view-media-files-with-the-azure-information-protection-app" class="xliff"></a>
A vállalati AV-, PDF- és képfájlok Android-eszközökön való megtekintéséhez használja az [Azure Information Protection alkalmazást](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (amelyet korábban Rights Management-megosztóalkalmazásnak neveztünk).

Ezt az alkalmazást a Google Play Áruházból töltheti le.  

A rendszer a következő fájltípusokat támogatja:

* **Hang:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (kibővített AAC+), AAC ELD (kibővített, alacsony késleltetésű AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Vorbis, PCM/WAVE
* **Videó:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Kép:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg
* **Dokumentumok:** PDF, PPDF


|**pfile**|**text**|
|----|----|
|A pfile egy általános „burkoló” formátum a védett fájlokhoz, amelyben a titkosított tartalom és az Azure Information Protection-licencek is megtalálhatók. Ez bármilyen fájltípus védelmére használható.|A szövegfájlok, beleértve az XML, a CSV és a hasonló típusú fájlokat, akkor is megnyithatók az alkalmazásban, ha védelem alatt állnak. Fájltípusok: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|

## További lépések
<a id="next-steps" class="xliff"></a>
[Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](end-user-mam-apps-ios.md)
