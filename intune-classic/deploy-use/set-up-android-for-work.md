---
title: "Az Android for Work beállítása"
description: "Mobileszközök felügyeletének engedélyezése Android for Work-eszközökhöz a Microsoft Intune-nal."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ms.custom: intune-classic
ms.openlocfilehash: 852997044cef22901e8133d76f327e98b2a1ee72
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work-eszközök regisztrálásának engedélyezése

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az Android for Work-eszközök felügyeletének engedélyezéséhez létre kell hoznia egy Android for Work-kötést az Intune-ban. Az Android for Worköt támogató, de korábban normál Android-eszközként regisztrált eszközök regisztrációját törölni kell, majd újra kell regisztrálni őket.

## <a name="add-android-for-work-binding-for-intune"></a>Android for Work-kötés létrehozása az Intune-ban

1. **Az Intune beállítása**<br>
Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** [állítja be a mobileszköz-kezelő szolgáltatóként](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment), valamint beállítja a mobileszköz-kezelést.

2. **Android for Work-kötés konfigurálása**<br>
    Intune-rendszergazdaként nyissa meg a [Microsoft Intune felügyeleti konzolját](https://manage.microsoft.com), lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Android for Work** felületre, majd a **Konfigurálás** elemre kattintva nyissa meg a Google Play Android for Work webhelyét. Ez egy új lapon nyílik meg a böngészőben.

3. **Bejelentkezés a Google-fiókba**<br>
   A Google bejelentkezési oldalán lépjen be az adott bérlő összes Android for Work-alapú felügyeleti feladatához társítandó Google-fiókkal. Ezt a Google-fiókot használja a szervezet összes rendszergazdája az alkalmazások felügyeletére és közzétételére a Play for Work konzolon.

4. **A szervezet adatainak megadása**<br>
   Az **Organization name** (Szervezet neve) mezőben adja meg a vállalat nevét. Az **Enterprise mobility management (EMM) provider** (Nagyvállalati mobileszköz-felügyeleti (EMM-) szolgáltató) mezőben a *Microsoft Intune* értéknek kell megjelennie. Fogadja el azAndroid for Work-szerződést, majd kattintson a **Confirm** (Jóváhagyás) gombra. Megtörténik a kérelem feldolgozása.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work-regisztrációs beállítások megadása
   Az Android for Work csak bizonyos Android-eszközökön támogatott. Az [Android for Workre vonatkozó követelményeket](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") megtalálja a Google webhelyén.  Az Android for Worköt támogató eszközök mindegyike támogatja a hagyományos Android-alapú felügyeletet is.  Az Intune-ban megadhatja, hogyan történjen az Android for Worköt támogató eszközök felügyelete:

   - **Minden eszköz felügyelete Android-eszközként** – Minden Android-eszköz, az Android for Worköt támogatókat is beleértve, hagyományos Android-eszközként lesz regisztrálva.
   - **Minden támogatott eszköz felügyelete Android for Work-eszközként** – Az Android for Worköt támogató eszközök mindegyike Android for Work-eszközként lesz regisztrálva. Az Android for Worköt nem támogató eszközök hagyományos Android-eszközként lesznek regisztrálva.
   - **Csak a megadott csoportokban szereplő felhasználók támogatott eszközeinek felügyelete Android for Work-eszközként** – Az Android for Work-alapú felügyeletet beállíthatja a felhasználók egy korlátozott halmaza számára. Csak a kijelölt csoportok tagjai által regisztrált, Android for Worköt támogató eszközök lesznek Android for Work-eszközként lesz regisztrálva. Minden más eszköz Android-eszközként lesz regisztrálva. Ez főleg Android for Workös próbák során hasznos.

## <a name="next-steps-for-android-for-work"></a>Az Android for Work-alapú felügyelet további lépései
Az Android for Work-kötés és -beállítások konfigurálása után a következőkre lesz lehetősége:
- [Android for Work-alkalmazások telepítése](android-for-work-apps.md)
- [Android for Work konfigurációs szabályzatok létrehozása](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Az Android for Work rendszergazdai fiókja kötésének megszüntetése

Az Android for Work-regisztrációt és -felügyeletet ki is kapcsolhatja. Ha az Intune felügyeleti konzolon a **Leválasztás** gombra kattint, azzal megszünteti a regisztrált Android for Work eszközök regisztrációját, és felbontja az Android for Work-fiók és az Intune közötti kapcsolatot.

### <a name="how-to-unbind-an-android-for-work-account"></a>Android for Work fiók leválasztása

1. **Android for Work-kötés feloldása**<br>
    Rendszergazdaként nyissa meg a [Microsoft Intune felügyeleti konzolját](https://manage.microsoft.com), lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Android for Work** felületre, majd kattintson a **Kötés megszüntetése** gombra.

2. **Android for Work-kötés törlésének jóváhagyása**<br>
  A kötés törléséhez és az összes Android for Work-eszköz Intune-regisztrációjának megszüntetéséhez kattintson az **Igen** gombra.
