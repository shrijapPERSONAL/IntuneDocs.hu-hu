---
title: "Android for Work-eszközök felügyeletének beállítása | Microsoft Intune"
description: "Mobileszközök felügyeletének engedélyezése Android for Work-eszközökhöz a Microsoft Intune-nal."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
translationtype: Human Translation
ms.sourcegitcommit: 519b66c94f3d056e060ed11e1a3d7d6d118a94fb
ms.openlocfilehash: 5f48303dd28627f961f8c2cfd38f8977354e2724


---

# Android for Work-eszközök regisztrálásának engedélyezése

Az Android for Work-eszközök felügyeletének engedélyezéséhez létre kell hoznia egy Android for Work-kötést az Intune-ban. Az Android for Worköt támogató, de korábban normál Andriod-eszközként regisztrált eszközök regisztrációját törölni kell, majd újra kell regisztrálni őket.

## Android for Work-kötés létrehozása az Intune-ban

1. **Az Intune beállítása**<br>
Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként](prerequisites-for-enrollment.md#set-mobile-device-management-authority), valamint beállítja a mobileszköz-kezelést.

2. **Android for Work-kötés konfigurálása**<br>
    Rendszergazdaként nyissa meg a [Microsoft Intune felügyeleti konzolját](http://manage.microsoft.com), lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Android for Work** felületre, majd a **Konfigurálás** gombra kattintva nyissa meg a Google Play Android for Work-webhelyét. Ez egy új lapon nyílik meg a böngészőben.

3. **Bejelentkezés a Google-fiókba**<br>
   A Google bejelentkezési oldalán lépjen be az adott bérlő összes Android for Work-alapú felügyeleti feladatához társítandó Google-fiókkal. Ez lehet az Intune-t felügyelő rendszergazdák közös Google-fiókja. Ezt a Google-fiókot használja a szervezet az alkalmazások felügyeletére és közzétételére a Play for Work konzolon.

4. **A szervezet adatainak megadása**<br>
   Az **Organization name** (Szervezet neve) mezőben adja meg a vállalat nevét. Az **Enterprise mobility management (EMM) provider** (Nagyvállalati mobileszköz-felügyeleti (EMM-) szolgáltató) mezőben a *Microsoft Intune* értéknek kell megjelennie. Fogadja el azAndroid for Work-szerződést, majd kattintson a **Confirm** (Jóváhagyás) gombra. Megtörténik a kérelem feldolgozása.

## Android for Work-regisztrációs beállítások megadása
   Az Android for Work csak bizonyos Android-eszközökön támogatott. Az [Android for Workre vonatkozó követelményeket](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") megtalálja a Google webhelyén.  Az Android for Worköt támogató eszközök mindegyike támogatja a hagyományos Android-alapú felügyeletet is.  Az Intune-ban megadhatja, hogyan történjen az Android for Worköt támogató eszközök felügyelete:

   - **Minden eszköz felügyelete Android-eszközként** – (Letiltva) Minden Android-eszköz, az Android for Worköt támogatókat is beleértve, hagyományos Android-eszközként lesz regisztrálva.
   - **Minden támogatott eszköz felügyelete Android for Work-eszközként** – (Engedélyezve) Az Android for Worköt támogató eszközök mindegyike Android for Work-eszközként lesz regisztrálva. Az Android for Worköt nem támogató eszközök hagyományos Android-eszközként lesznek regisztrálva.
   - **Csak a megadott csoportokban szereplő felhasználók támogatott eszközeinek felügyelete Android for Work-eszközként** – (Tesztelés) Beállítható az Android for Work-alapú felügyelet a felhasználók egy korlátozott halmaza számára. Csak a kijelölt csoportok tagjai által regisztrált, Android for Worköt támogató eszközök lesznek Android for Work-eszközként lesz regisztrálva. Minden más eszköz Android-eszközként lesz regisztrálva.

## Az Android for Work-alapú felügyelet további lépései
Az Android for Work-kötés és -beállítások konfigurálása után a következőket tudja felügyelni:
- [Android for Work-alkalmazások telepítése](android-for-work-apps.md)
- [Android for Work konfigurációs szabályzatok létrehozása](android-for-work-policy-settings-in-microsoft-intune.md)

## Az Android for Work rendszergazdai fiókja kötésének megszüntetése

Az Android for Work-regisztrációt és -felügyeletet ki is kapcsolhatja. A **Leválasztás** gombra kattintva megszünteti a regisztrált Android for Work eszközök regisztrációját és felbontja az Android for Work fiók és az Intune közötti kapcsolatot.

### Android for Work fiók leválasztása

1. **Android for Work kötés feloldása**<br>
    Rendszergazdaként nyissa meg a [Microsoft Intune felügyeleti konzolját](http://manage.microsoft.com), lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Android for Work** felületre, majd kattintson a **Kötés megszüntetése** gombra.

2. **Android for Work-kötés törlésének jóváhagyása**<br>
  A kötés törléséhez és az összes Android for Work-eszköz Intune-regisztrációjának megszüntetéséhez kattintson az **Igen** gombra.



<!--HONumber=Oct16_HO2-->


