---
title: Vállalati androidos kioszkeszközök regisztrálása az Intune-ban
titlesuffix: Microsoft Intune
description: Útmutató vállalati androidos kioszkeszközök Intune-ban való regisztrálásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cd6aee30a88906c3f6ae078e338732589d88a5f0
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909133"
---
# <a name="set-up-enrollment-of-android-enterprise-kiosk-devices"></a>Vállalati androidos kioszkeszközök regisztrálásának beállítása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Android vállalati tulajdonú, egycélú (COSU) megoldáskészletével támogatja a kioszk-stílusú eszközök használatát. Az ilyen eszközöknek egyetlen rendeltetése van, például digitális aláírás, jegynyomtatás vagy leltárkezelés, hogy csak néhányat említsünk. A rendszergazdák alkalmazások és webes hivatkozások egy adott körére korlátozzák az eszköz használatát. Ez azt is megakadályozza, hogy a felhasználók más alkalmazásokat adjanak az eszközhöz, vagy más műveleteket hajtsanak végre rajta.

Az Intune segítséget nyújt az alkalmazások és beállítások androidos kioszkeszközökre való telepítéséhez. A Vállalati Androidra vonatkozó részletekről az [A Vállalati Android követelményei](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) című weboldal nyújt tájékoztatást.

Az ezen a módon felügyelt eszközök felhasználói fiók nélkül vannak regisztrálva az Intune-ban, és egyetlen végfelhasználóhoz sincsenek hozzárendelve. Nem rendeltetésük olyan személyes használatra szánt, vagy sok felhasználóspecifikus adatot igénylő alkalmazások futtatása, mint az Outlook vagy a Gmail.

## <a name="device-requirements"></a>Eszközkövetelmények

A vállalati androidos kioszkeszközként kezelt eszközöknek a következő feltételeknek kell megfelelniük:

- Android 5.1 vagy újabb operációs rendszer.
- Az eszközökön olyan Android-disztribúciónak kell futnia, amely kapcsolódni tud a Google Mobile Services (GMS) szolgáltatáshoz. Az eszközöknek el kell érniük a GMS-t, és képesnek kell lenniük a GMS-hez való kapcsolódásra.

## <a name="set-up-android-kiosk-management"></a>Az Android beállítása kioszk módú felügyelethez

A kioszkmód felügyelete a következő lépésekben állítható be:

1. A mobileszközök kezelésének előkészítését a [**Microsoft Intune** mint mobileszköz-felügyeleti (MDM) szolgáltató megadása](mdm-authority-set.md) című témakör ismerteti. Ezt elég egyszer beállítani, amikor először állítja be az Intune-t a mobileszközök felügyeletére.
2. [Az Intune-bérlő csatlakoztatása a Vállalati Android-fiókjához](connect-intune-android-enterprise.md).
3. [Regisztrációs profil létrehozása](#create-an-enrollment-profile).
4. [Eszközcsoport létrehozása](#create-a-device-group).
5. [A kioszkeszközök regisztrálása](#enroll-the-kiosk-devices).

### <a name="create-an-enrollment-profile"></a>Beléptetési profil létrehozása

Kioszkeszközei regisztrálásához létre kell hoznia egy regisztrációs profilt. A profil a létrehozásakor ad egy regisztrációs jogkivonatot (véletlenszerű karakterlánc) és egy QR-kódot. Az Android operációs rendszertől és az eszköz verziójától függően [a kioszkeszköz regisztrálásához](#enroll-the-kiosk-devices) vagy a jogkivonatot, vagy a QR-kódot használhatja.

1. Nyissa meg az [Intune portált](https://portal.azure.com), majd válassza az **Eszközregisztráció** > **Android-regisztráció** > **Kioszk- és feladatalapú eszközök regisztrációja** lehetőséget.
2. Válassza a **Létrehozás** lehetőséget, és töltse ki a kötelező mezőket.
    - **Név**: Adjon meg egy nevet, amelyet akkor fog használni, amikor a profilt a dinamikus eszközcsoporthoz rendeli.
    - **Jogkivonat lejárati dátuma**: Az a dátum, amikor a jogkivonat lejár. A Google legfeljebb 30 napot enged meg.
3. Válassza a **Létrehozás** elemet a profil mentéséhez.

### <a name="create-a-device-group"></a>Eszközcsoport létrehozása

A cél lehet alkalmazás, és hozzárendelt vagy dinamikus eszközcsoportokra vonatkozó szabályzat is. A dinamikus AAD-eszközcsoportokat a következő lépesekkel konfigurálhatja úgy, hogy automatikusan felvegyék a megadott regisztrációs profillal regisztrált eszközöket:

1. Nyissa meg az [Intune portált](https://portal.azure.com), majd válassza a **Csoportok** > **Minden csoport** > **Új csoport** lehetőséget.
2. A **Csoport** panelen töltse ki a kötelező mezőket az alábbiak szerint:
    - **Csoporttípus**: Biztonsági (Security)
    - **Csoport neve**: Adjon meg egy beszédes nevet (például 1. üzem eszközei)
    - **Tagság típusa**: Dinamikus eszköz (Dynamic device)
3. Válassza a **Dinamikus lekérdezés hozzáadása** lehetőséget.
4. A **Dinamikus tagsági szabályok** panelen töltse ki a mezőket az alábbiak szerint:
    - **Dinamikus tagsági szabály hozzáadása**: Egyszerű szabály (Simple rule)
    - **Eszközök hozzáadásának helye**: enrollmentProfileName
    - A középső mezőben válassza az **Egyezés** (Match) lehetőséget.
    - Az utolsó mezőben adja meg a korábban létrehozott regisztrációs profilt.
5. Válassza a **Lekérdezés hozzáadása** > **Létrehozás** lehetőséget.

### <a name="replace-or-remove-tokens"></a>Jogkivonatok cseréje vagy eltávolítása

A jogkivonatok és QR-kódok cserélhetők vagy eltávolíthatók.

- **Jogkivonat cseréje**: A Jogkivonat cseréje lehetőséggel új jogkivonatot/QR-kódot generálhat a hamarosan lejáró helyett.
- **Jogkivonat visszavonása**: Azonnal lejárttá minősítheti a jogkivonatot/QR-kódot. Ettől kezdve a jogkivonat/QR-kód többé nem használható. Ez a lehetőség a következő esetekben lehet hasznos:
    - a jogkivonat/QR-kód véletlenül meg lett osztva egy jogosulatlan féllel
    - minden regisztráció befejeződött, és a jogkivonatra/QR-kódra többé nincs szükség

Egy jogkivonat/QR-kód cseréje vagy visszavonása a már regisztrált eszközöket nem érinti.

1. Nyissa meg az [Intune portált](https://portal.azure.com), majd válassza az **Eszközregisztráció** > **Android-regisztráció** > **Kioszk- és feladatalapú eszközök regisztrációja** lehetőséget.
2. Válassza ki a profilt, amellyel dolgozni kíván.
3. Válassza a **Jogkivonat** lehetőséget.
4. A jogkivonat cseréjéhez válassza a **Jogkivonat cseréje** lehetőséget.
5. A jogkivonat visszavonásához válassza a **Jogkivonat visszavonása** lehetőséget.

## <a name="enroll-the-kiosk-devices"></a>A kioszkeszközök regisztrálása

A regisztrációs profil és a dinamikus eszközcsoport létrehozása után már regisztrálhatja kioszkeszközeit. Az Android-eszközök regisztrálásának módja az operációs rendszertől függ.

| Regisztráció módszere | Android operációs rendszer minimális támogatott verziója |
| ----- | ----- |
| Kis hatótávolságú kommunikáció | 5.1 |
| Biztonsági jogkivonat | 6.0 |
| QR-kód | 7.0 |
| Zero Touch | 8.0, a programban részt vevő gyártóknál |

### <a name="enroll-by-using-near-field-communication-nfc"></a>Regisztráció kis hatótávolságú kommunikáció (NFC) használatával

Az NFC-t támogató Android 5.1 vagy újabb rendszerű eszközöket egy speciálisan megformázott NFC-címke létrehozásával regisztrálhatja. Használhatja saját alkalmazását vagy bármilyen NFC-címke létrehozására alkalmas eszközt. További információ: [Google Android-felügyeleti API dokumentáció](https://developers.google.com/android/management/provision-device#nfc_method).

### <a name="enroll-by-using-a-token"></a>Regisztráció jogkivonat használatával

Android 6 vagy újabb rendszerű eszközök esetén használhatja a jogkivonatot az eszköz regisztrálásához.

1. Kapcsolja be a gyári alaphelyzetbe állított eszközt.
2. Az **Üdvözlőképernyőn** válasszon nyelvet.
3. Kapcsolódjon a **WiFi** hálózathoz, majd válassza a **TOVÁBB** lehetőséget.
4. Fogadja el a Google feltételeit és kikötéseit, majd válassza a **TOVÁBB** lehetőséget.
5. A Google bejelentkezési képernyőjén Gmail-fiók helyett adja meg az **afw#setup** értéket, majd válassza a **TOVÁBB** lehetőséget.
6. Válassza a **TELEPÍTÉS** lehetőséget az **Android eszközszabályzat** alkalmazáshoz.
7. Folytassa a szabályzat telepítését.  Bizonyos eszközök további feltételek elfogadását is kérhetik. 
8. Az **Eszköz regisztrálása** képernyőn olvastassa be a QR-kódot az eszközzel, vagy válassza a jogkivonat manuális megadását.
9. A regisztráció befejezéséhez kövesse a képernyőn megjelenő utasításokat. 

### <a name="enroll-by-using-a-qr-code"></a>Regisztráció QR-kód használatával

Android 7 vagy újabb rendszerű eszközökön az eszköz regisztrálásához beolvashatja a regisztrációs profilhoz tartozó QR-kódot.

1. A QR-kód olvasása az Android-eszközön úgy indítható el, hogy többször a gyári alaphelyzetbe állítás utáni első képernyőre koppint.
2. Android 7-es és 8-as eszközökön a rendszer kérni fogja egy QR-kódolvasó telepítését. Az Android 9 és újabb rendszerű eszközökön már van telepítve QR-kódolvasó.
3. Olvassa be a regisztrációs profil QR-kódját a QR-kódolvasóval, majd a regisztráláshoz kövesse a képernyőn megjelenő utasításokat.

### <a name="enroll-by-using-google-zero-touch"></a>Regisztráció a Google Zero Touch használatával

A Google Zero Touch rendszerének használatához az eszköznek támogatnia kell azt, és a szolgáltatásban részt vevő szállítótól kell származnia.  Erről a [Google Zero Touch programjának webhelyén](https://www.android.com/enterprise/management/zero-touch/) talál további információt. 


1. Hozzon létre új konfigurációt a Zero Touch-konzolon.
2. Az EMM DPC legördülő listából válassza a **Microsoft Intune** lehetőséget.
3. Másolja és illessze be a következő JSON-kódot a Google Zero Touch-konzoljának Egyéb DPC beállítások mezőjébe. A *YourEnrollmentToken* szöveget írja át a regisztrációs profilja részeként létrehozott regisztrációs jogkivonatra. Ügyeljen rá, hogy a regisztrációs jogkivonat időzőjelek között legyen.

```
{ 
    "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "com.google.android.apps.work.clouddpc/.receivers.CloudDeviceAdminReceiver", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "I5YvS0O5hXY46mb01BlRjq4oJJGs2kuUcHvVkAPEXlg", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://play.google.com/managed/downloadManagingApp?identifier=setup", 

    "android.app.extra.PROVISIONING_ADMIN_EXTRAS_BUNDLE": { 
        "com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "YourEnrollmentToken" 
    } 
} 
```
4. Válassza az **Alkalmaz** lehetőséget.

## <a name="managing-apps-on-android-kiosk-devices"></a>Alkalmazások kezelése androidos kioszkeszközökön

Androidos kioszkeszközökre csak [Kötelezőnek beállítva](apps-deploy.md#to-assign-an-app) hozzárendelés-típusú alkalmazások telepíthetők. Az alkalmazások a felügyelt Google Play Áruházból lesznek telepítve ugyanúgy, mint az androidos munkahelyi profilos eszközök esetében.

Az alkalmazások automatikusan frissítve lesznek a felügyelt eszközökön, amikor az alkalmazás fejlesztője frissítést tesz közzé a Google Playben.

Androidos kioszkeszközökről a következő módokon távolítható el alkalmazás:
-   Törölje az alkalmazástelepítés Kötelező értékét.
-   Hozzon létre központi eltávolítást az alkalmazáshoz.


## <a name="next-steps"></a>További lépések
- [Androidos kioszkalkalmazások telepítése](apps-deploy.md)
- [Androidos kioszkalkalmazás-konfigurációs szabályzatok létrehozása](device-profiles.md)