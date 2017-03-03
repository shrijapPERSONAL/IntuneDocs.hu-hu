---
title: "Android-alkalmazások MAM-szabályzatokkal | Microsoft Docs"
description: "Ez a témakör bemutatja, mire számítson, ha az alkalmazását mobilalkalmazás-felügyeleti szabályzatok felügyelik."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: aeacfddb3ed42938dd9443e2734222c977436430
ms.lasthandoff: 12/10/2016


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-mam-policies"></a>Mi várható az Android-alkalmazás MAM-szabályzatok általi kezelésekor

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör a mobilalkalmazás-felügyeleti (MAM) szabályzatokat használó alkalmazásokkal kapcsolatos felhasználói élményt ismerteti. A MAM-szabályzatokat csak akkor alkalmazza a rendszer, amikor az alkalmazásokat munkahelyi környezetben használják: például amikor egy munkahelyi fiókkal fér hozzá az alkalmazásokhoz, vagy a vállalata OneDrive vállalati helyén tárolt fájlokhoz fér hozzá.
##  <a name="access-apps"></a>Alkalmazások elérése

A Munkahelyi portál alkalmazásra az Android-eszközökön a MAM-szabályzatokhoz rendelt összes alkalmazáshoz szükség van.

Azokon az eszközökön, amelyek nincsenek regisztrálva az Intune-ban, az eszközre telepíteni kell a Munkahelyi portál alkalmazást. Azonban a felhasználónak nem kell elindítania a Munkahelyi portál alkalmazást, illetve nem kell bejelentkeznie az alkalmazásba ahhoz, hogy használhassa a MAM-szabályzatok által felügyelt alkalmazásokat.

A Munkahelyi portál alkalmazás biztonságos helyet tesz elérhetővé az Intune számára, ahol a szolgáltatás megoszthatja az adatokat. A Munkahelyi portál alkalmazás ezért az összes MAM-szabályzat alá vont alkalmazás esetében követelmény, még akkor is, ha maga az eszköz nincs regisztrálva az Intune-ban.


##  <a name="use-apps-with-multi-identity-support"></a>A többszörös identitást támogató alkalmazások használata

A MAM-szabályzatokat a rendszer csak a munkahelyi használat esetén alkalmazza. Ez azt jelenti, hogy az alkalmazás eltérő módon működhet, attól függően, hogy munkahelyi vagy személyes célokra használják.

Például a munkahelyi adatok elérésekor a felhasználónak PIN-kódot kell megadnia. Az **Outlook alkalmazás** esetében a felhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazás** esetében a felhasználónak a munkahelyi fiók beírásakor kell megadnia a PIN-kódot. A Microsoft **Word**, a **PowerPoint** és az **Excel** esetében a felhasználónak akkor kell megadnia a PIN-kódot, ha a vállalat OneDrive vállalati helyén tárolt dokumentumhoz szeretne hozzáférni.

##  <a name="manage-user-accounts-on-the-device"></a>Felhasználói fiókok kezelése az eszközön

Az Intune a MAM-szabályzatok telepítését eszközönként csak egy felhasználói fiók esetében támogatja.

* A használt alkalmazástól függően a rendszer akár le is tilthatja a második felhasználót az eszközön. Minden esetben azonban csak a MAM-szabályzatokat megkapó első felhasználóra lesznek érvényesek a szabályzatok.

  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de a MAM-szabályzatok nem érvényesek a második felhasználói fiókra.

  * A **OneDrive** és az **Outlook alkalmazásokban** csak egy munkahelyi fiókot használhat.  Ezeknél az alkalmazásoknál nincs lehetőség további munkahelyi fiókok beállítására.  Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.


* Ha egy eszközhöz több felhasználói fiók tartozik a MAM-szabályzatok telepítése előtt, az Intune MAM-szabályzatai azt a fiókot kezelik, amelyikre elsőként telepítik a MAM-szabályzatokat.


A következő példák részletesen bemutatják, hogy a rendszer hogyan kezeli a további felhasználói fiókokat.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználó munkahelyi fiókkal rendelkezik mindként vállalatnál, és mindkettő az Intune-t használja a MAM-szabályzatok telepítéséhez. Az **X vállalat** telepíti elsőként a MAM-szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja a MAM-szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy a MAM-szabályzatok az Y vállalathoz tartozó fiókot kezeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.
### <a name="add-a-second-account"></a>Második fiók hozzáadása
####  <a name="android"></a>Android
Android-eszközön blokkoló üzenet jelenhet meg, amely ismerteti a meglévő fiók eltávolításának és új fiók felvételének lépéseit.  A meglévő fiók eltávolításához válassza a **Beállítások &gt;Általános &gt; Alkalmazáskezelő &gt;Munkahelyi portál** lehetőséget, majd itt az **Adatok törlése** lehetőséget.

![Képernyőfelvétel a hibaüzenetről és a fiók eltávolítására vonatkozó utasításokról](../media/AppManagement/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Médiafájlok megtekintése az Azure Information Protection alkalmazással
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

## <a name="next-steps"></a>További lépések
[Mi várható az iOS-alkalmazás MAM-szabályzatok általi kezelésekor](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>További információ
[Mobilalkalmazás-felügyeleti szabályzatok létrehozása és telepítése Microsoft Intune-ban](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

