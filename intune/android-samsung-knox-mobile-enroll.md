---
title: Eszközök automatikus regisztrációja a Samsung Knox Mobile Enrollmenttel
titlesuffix: Microsoft Intune
description: Útmutató az Android-eszközök a Samsung KME-vel történő regisztrálásához
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f7565972d37c5df5acb83012bb7cebbdc1fa1cec
ms.sourcegitcommit: 378474debffbc85010c54e20151d81b59b7a7828
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028647"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Eszközök automatikus regisztrációja a Samsung Knox Mobile Enrollmenttel

Ez a témakör segít beállítani az Intune-t támogatott Android-eszközök a Samsung Knox Mobile Enrollmenttel (KME-vel) történő regisztrációjához. Az Intune a Samsung Knox Mobile Enrollmenttel (KME-vel) való használatával nagy mennyiségű céges tulajdonú Android-eszközt regisztrálhat, amikor a végfelhasználók először bekapcsolják az eszközüket, és egy Wi-Fi- vagy mobilhálózathoz csatlakoznak. A Knox Deployment App használatával az eszközök Bluetooth vagy NFC segítségével is regisztrálhatók.

Ha engedélyezni szeretné a Samsung KME-vel történő Intune-regisztrációt, az Intune és a Samsung Knox portálját is használnia kell, ebben a sorrendben:

1. A Knox portálján:
    1. [Hozzon létre egy MDM-profilt](#create-mdm-profile)
    2. [Adjon hozzá eszközöket](#add-devices)
    3. [Rendeljen hozzá MDM-profilokat az eszközökhöz](#assign-an-mdm-profile-to-devices)
2. A Knox portálon [konfigurálja a végfelhasználói bejelentkezést](#configure-how-end-users-sign-in).
3. [Terjessze az eszközöket](#distribute-devices).


A rendszer automatikusan hozzáadja az eszközazonosítókat (a sorozatszámokat és az IMEI-ket) a Knox portálhoz, amikor a Knox Deployment Programban részt vevő hivatalos viszonteladóktól vásárol eszközöket.


## <a name="prerequisites"></a>Előfeltételek

Ha regisztrálni szeretne eszközöket az Intune-ban a KME-vel, először a cégét kell regisztrálnia a Samsung Knox portálon. Ehhez kövesse az alábbi lépéseket:
1.  [Győződjön meg róla, hogy a KME elérhető az Ön régiójában](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): A KME több mint 55 országban érhető el. Győződjön meg róla, hogy az üzembe helyezés országa támogatott.

2.  [Támogatott eszközök](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): A KME minden, legalább Knox 2.4-et futtató Samsung-eszközön elérhető.

3.  [Hálózati követelmények](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Győződjön meg róla, hogy engedélyezte a megfelelő, tűzfallal és hálózati hozzáféréssel kapcsolatos szabályokat a hálózatán.

4.  [Samsung-fiók regisztrálása](https://www2.samsungknox.com/en/user/register): A KME engedélyezéséhez és a regisztrációhoz, valamint a Knox Enterprise-jogosultságok egyetlen helyen történő kezeléséhez egy Samsung-fiókra van szüksége.

5.  Regisztráció felülvizsgálata: Miután létrehozta és beküldte a profilt, a Samsung felülvizsgálja az alkalmazást, és vagy azonnal jóváhagyja, vagy „ellenőrzésre vár” állapottal továbbküldi részletesebb elemzésre. A fiók jóváhagyása után továbbhaladhat a következő lépésekre.

## <a name="create-mdm-profile"></a>MDM-profil létrehozása

Miután sikeresen regisztrálta a cégét, az alábbi adatokkal létrehozhat egy Microsoft Intune-os MDM-profilt a Knox portálon. Lépésenkénti útmutatásért tekintse meg a [ Samsung Knox-profil telepítővarázslójának](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) utasításait.

| MDM-profil – mezők| Kötelező? | Értékek |
|-------------------|-----------|-------|
|MDM-kiszolgáló URI-azonosítója     | Nem        |Hagyja üresen a mezőt.
|Profilnév       | Igen       |Adjon meg egy profilnevet.
|leírás        | Nem        |Adjon meg egy leírást a profilhoz.
|MDM-ügynök APK-ja      | Igen       |https://aka.ms/intune_kme
|A telepítővarázsló kihagyása  | Nem        |Válassza ezt a beállítást, ha ki szeretné hagyni a szabványos eszközbeállítási lépéseket a végfelhasználó nevében.
|Regisztráció megszakításának engedélyezése a végfelhasználó számára | Nem | Válassza ezt a beállítást, ha engedélyezni szeretné a felhasználók számára, hogy megszakítsák a KME-t.
|Egyéni JSON        | Nem        |Hagyja üresen a mezőt.
| Licencfeltételek, szolgáltatási feltételek és felhasználói szerződés| Nem | Válassza ezt a beállítást, ha meg szeretné jeleníteni a Knoxszal kapcsolatos szerződéseket a felhasználók számára.
Knox-licenc társítása a profilhoz | Nem | Hagyja üresen a beállítást. A KME-vel történő Intune-regisztrációhoz nincs szükség Knox-licencre.

## <a name="add-devices"></a>Eszközök felvétele

Ha MDM-profilokat szeretne hozzárendelni az eszközökhöz, a támogatott Samsung Knox-eszközöket hozzá kell adnia a Knox portálhoz az alábbi módszerek egyikével:
- **Samsung által jóváhagyott viszonteladók segítségével:** Használja ezt a módszert, ha egy Samsung által jóváhagyott viszonteladótól vásáról. Ha jóváhagyja, a viszonteladók automatikusan feltölthetnek eszközöket. [A viszonteladók hozzáadásáról tájékoztatást a Samsung Knox regisztrációs útmutatójában találhat](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **A Knox Deployment App (KDA) segítségével:** Használja ezt a módszert, ha a meglévő eszközeit szeretné regisztrálni a KME-vel. Ezzel a módszerrel Bluetooth vagy NFC használatával adhat hozzá eszközöket a Knox portálhoz. [A KDA használatáról tájékoztatást a Samsung Knox regisztrációs útmutatójában találhat](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>MDM-profil hozzárendelése az eszközökhöz
A regisztráció előtt a Knox portálon hozzá kell rendelnie egy MDM-profilt a hozzáadott eszközökhöz. [Az eszközkonfigurációról tájékoztatást a Samsung Knox regisztrációs útmutatójában találhat](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>A végfelhasználói bejelentkezés konfigurálása

Az Intune-ba a KME-vel regisztrált eszközök esetében a következőképp konfigurálhatja a végfelhasználói bejelentkezést:

- **Felhasználónév-hozzárendelés nélkül:** A Knox portál **Eszközadatok** területén hagyja üresen a hozzáadott eszközök **Felhasználóazonosító** és a **Jelszó** mezőit. Így a végfelhasználónak az Intune-regisztráció során nevet és jelszót is meg kell adnia.

- **Felhasználónév-hozzárendeléssel:** A Knox portál **Eszközadatok** területén adjon meg egy **Felhasználóazonosítót** (például a hozzárendelt felhasználó vagy a [Készülékregisztráció-kezelő](https://docs.microsoft.com/intune/device-enrollment-manager-enroll) fiókjának felhasználónevét) a hozzáadott eszközöknek. Így a végfelhasználó felhasználó neve előre ki lesz töltve, az Intune-regisztráció során pedig neki egy jelszót kell megadnia.

> [!NOTE]
>
>Ha meghatároz egy felhasználó-hozzárendelést, csak a hozzárendelt felhasználó regisztrálhatja az eszközt a KME-vel. Ez az eszköz összes adatának törlése után is így marad. Ha nem határoz meg felhasználó-hozzárendelést a Knox portálon, bármely, érvényes Intune-licenccel rendelkező felhasználó regisztrálhatja az eszközt a KME-vel.
>

## <a name="distribute-devices"></a>Eszközök terjesztése

Az MDM-profil létrehozása és hozzárendelése, a felhasználónév társítása és az eszközök vállalati tulajdonúként való azonosítása után megkezdheti az eszközök terjesztését a felhasználók között.

További segítségre van szüksége? Tekintse meg a teljes [Knox mobileszköz-regisztrációs felhasználói útmutatót](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm).

## <a name="frequently-asked-questions"></a>Gyakori kérdések
- **Google Play-fiók:** Nem szükséges Google Play-fiók az eszköz Microsoft Intune-regisztrációjához. Az Intune Céges portál alkalmazás jövőbeli frissítései azonban ezt kötelezővé tehetik.

- **Google eszköztulajdonos mód:** A Google eszköztulajdonos módban történő KME-regisztráció nem támogatott az előzetes verzióban. Ezt a forgatókönyvet jelenleg vizsgáljuk.

- **Az alkalmazás nem veszi figyelembe a „Jelszó” mezőt:** Ha a **Jelszó** ki van töltve a Knox portál **Eszközadatok** területén, az Intune Céges portál alkalmazás nem veszi figyelembe azt. A végfelhasználónak meg kell adnia egy jelszót az eszközön az eszközregisztráció befejezéséhez.

- **Vállalati Android-regisztráció:** A KME nem támogatja a vállalati Android-regisztrációt.

## <a name="getting-support"></a>Támogatás igénybevétele
További információ [a Samsung KME támogatásáról](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm).


