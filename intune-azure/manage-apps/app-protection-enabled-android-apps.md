---
title: "Alkalmazásvédelmi szabályzatok és Android-alkalmazások | Azure-beli Intune – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: ez a témakör azt ismerteti, hogy milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 949686ea8a13072e820d1fdc4f14a22e2730e8f1


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok? 
[!INCLUDE[azure_preview](../includes/azure_preview.md)] Ez a témakör az alkalmazásvédelmi szabályzatokkal védett alkalmazások felhasználói élményét ismerteti. Az alkalmazásvédelmi szabályzatok csak az alkalmazások munkakörnyezetben való használatakor lépnek életbe, például ha a munkahelyi fiókjával használ egy alkalmazást, vagy ha a céges OneDrive-tárhelyen tárolt fájlokhoz próbál hozzáférni.
##  <a name="accessing-apps"></a>Alkalmazásokhoz való hozzáférés

Androidos eszközökön minden alkalmazásvédelmi szabályzathoz rendelt alkalmazás esetén szükség van a Céges portál alkalmazásra.

Az Intune-ban nem regisztrált eszközökre telepíteni kell a Céges portál alkalmazást, a felhasználónak azonban nem kell elindítania vagy bejelentkeznie ahhoz, hogy alkalmazásvédelmi szabályzatokkal felügyelt alkalmazást használjon.
A Vállalati portál alkalmazás segítségével az Intune biztonságos helyen tudja megosztani az adatokat, emiatt ez akkor is követelmény, ha az eszköz nincs regisztrálva az Intune-ban.


##  <a name="using-apps-with-multi-identity-support"></a>A többszörös identitást támogató alkalmazások használata

Az alkalmazásvédelmi szabályzatok csak az alkalmazások munkakörnyezetben való használatakor lépnek életbe, így a környezettől függően két különböző alkalmazásműködést (munkahelyi és személyes) figyelhet meg.

A több identitást támogató alkalmazások esetében az Intune csak akkor lépteti életbe az alkalmazásvédelmi szabályzatokat, amikor a végfelhasználó munkakörnyezetben használja az alkalmazást.  Például a munkaadathoz való hozzáférésekor a végfelhasználónak PIN-kódot kell megadnia.  Az **Outlook alkalmazás** esetén a végfelhasználónak az alkalmazás indításakor kell megadnia a PIN-kódot. A **OneDrive alkalmazásnál** ez akkor fordul elő, amikor a végfelhasználó beírja a munkahelyi fiókot.  A Microsoft **Word**, **PowerPoint*, és **Excel** esetén ez akkor fordul elő, amikor a végfelhasználó a vállalat OneDrive vállalati helyén tárolt dokumentumhoz fér hozzá.
##  <a name="managing-user-accounts-on-the-device"></a>Felhasználói fiókok kezelése az eszközön

Az Intune-nal eszközönként csak egy felhasználói fiókhoz lehet alkalmazásvédelmi szabályzatokat telepíteni.

* A használt alkalmazástól függően a második felhasználó blokkolva lesz vagy nem lesz blokkolva az eszközön. Az alkalmazásvédelmi szabályzatok azonban mindig csak az őket megkapó első felhasználóra lesznek érvényesek.

  * A **Microsoft Word**, az **Excel** és a **PowerPoint** nem blokkolja a második felhasználói fiókot, de az alkalmazásvédelmi szabályzatok nem érvényesek rá.

  * A **OneDrive és az Outlook alkalmazáshoz** csak egy munkahelyi fiókot használhat.  A további munkahelyi fiókok hozzáadását ezek az alkalmazások blokkolják.  Ugyanakkor eltávolíthat egy adott felhasználót, és másik felhasználót vehet fel helyette az eszközön.


* Ha egy eszközön több felhasználói fiók is van az alkalmazásvédelmi szabályzatok telepítése előtt, az Intune alkalmazásvédelmi szabályzatai azt a fiókot felügyelik, amelyikre elsőként lettek telepítve.


A következő példák részletesen bemutatják, hogyan történik a több felhasználói fiók kezelése.

Az A felhasználó két vállalatnak dolgozik: az **X vállalatnak** és az **Y vállalatnak**. Az A felhasználónak munkahelyi fiókja van mindként vállalatnál, és mindkettő az Intune-nal telepít alkalmazásvédelmi szabályzatokat. Az **X vállalat** telepít elsőként alkalmazásvédelmi szabályzatokat, **megelőzve** az **Y vállalatot**. Az **X vállalathoz** tartozó fiók megkapja az alkalmazásvédelmi szabályzatot, de az Y vállalat fiókja nem. Ha azt szeretné, hogy az alkalmazásvédelmi szabályzatok az Y vállalathoz tartozó fiókot felügyeljék, akkor el kell távolítania az X vállalathoz tartozó fiókot.
### <a name="adding-a-second-account"></a>Második fiók hozzáadása
####  <a name="android"></a>Android
Android-eszközön blokkoló üzenet jelenhet meg, amely ismerteti a meglévő fiók eltávolításának és új fiók felvételének lépéseit.  A meglévő fiók eltávolításához válassza a **Beállítások &gt;Általános &gt; Alkalmazáskezelő &gt;Vállalati portál, végül az Adatok törlése** lehetőséget.

![Képernyőfelvétel a hibaüzenetről és a fiók eltávolítására vonatkozó utasításokról](../media/android-switch-user.png)

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
[Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-ios-apps.md)

### <a name="see-also"></a>További információ
[Alkalmazásvédelmi szabályzatok létrehozása és telepítése Microsoft Intune-ban](app-protection-policies.md)



<!--HONumber=Feb17_HO1-->


