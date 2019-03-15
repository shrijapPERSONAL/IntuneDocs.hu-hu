---
title: Teljes körűen felügyelt eszközöket az Intune-ban vagy a dedikált vállalati Android-eszköz regisztrálása
titlesuffix: Microsoft Intune
description: Ismerje meg, hogy miként regisztrálhatják az Android Enterprise dedikált vagy teljes körűen felügyelt eszközökre az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 59891f042bed9602bd755e9320e0660ffaa6c3bc
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394400"
---
# <a name="enroll-your-android-enterprise-dedicated-devices-or-fully-managed-devices-preview"></a>A dedikált vállalati Android-eszköz vagy a teljes körűen felügyelt eszközök (előzetes verzió)

Miután beállította a [Android Enterprise dedikált eszközök](android-kiosk-enroll.md) vagy [teljes körűen felügyelt eszközök](android-fully-managed-enroll.md) az Intune-ban, az eszközöket regisztrálni. Az Android Enterprise-eszközök regisztrálásának módja attól függ, hogy az operációs rendszer.

| Regisztráció módszere | Android operációs rendszer minimális verziójának dedikált és teljes körűen felügyelt eszközök |
| ----- | ----- |
| Kis hatótávolságú kommunikáció | 5.1 |
| Biztonsági jogkivonat | 6.0 |
| QR-kód | 7.0 |
| Zero Touch  | 8.0\* |

\* A programban részt vevő gyártókat.

### <a name="enroll-by-using-near-field-communication-nfc"></a>Regisztráció kis hatótávolságú kommunikáció (NFC) használatával

Az NFC támogató eszközök regisztrálja az eszközöket egy speciálisan formázott Bizonyos NFC-címke létrehozásával. Használhatja saját alkalmazását vagy bármilyen NFC-címke létrehozására alkalmas eszközt. További információkért lásd: [Android Enterprise C-alapú eszközök regisztrációja a Microsoft Intune-nal](https://blogs.technet.microsoft.com/cbernier/2018/10/15/nfc-based-android-enterprise-device-enrollment-with-microsoft-intune/) és [a Google Android API dokumentációját](https://developers.google.com/android/management/provision-device#nfc_method).

### <a name="enroll-by-using-a-token"></a>Regisztráció jogkivonat használatával

Android 6 vagy újabb rendszerű eszközök esetén használhatja a jogkivonatot az eszköz regisztrálásához. 6.1-es és újabb verziók is használhatják a QR-kód beolvasásához használatakor a **afw #setup** regisztrációs módszer.

1. Kapcsolja be a törölt tartalmú eszközt.
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

> [!Note]
> A böngésző kicsinyítése miatt előfordulhat, hogy az eszközökkel nem lehet beolvasni a QR-kódot. A nagyítás növelése megoldja ezt a problémát.

1. A QR-kód olvasása az Android-eszközön úgy indítható el, hogy többször az összes adat törlése után először megjelenő képernyőre koppint.
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


## <a name="next-steps"></a>További lépések
- [Android-alkalmazások üzembe helyezése](apps-deploy.md)
- [Androidos alkalmazáskonfigurációs szabályzatok hozzáadása](device-profiles.md)

