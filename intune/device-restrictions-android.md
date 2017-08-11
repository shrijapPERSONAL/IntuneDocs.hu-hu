---
title: "Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Android esetén"
titleSuffix: Intune on Azure
description: "A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre androidos eszközökön.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b9e009e94fb4d9bdb99960e0d238d5471d1f4b50
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Android- és Samsung KNOX Standard-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az androidos eszköz korlátozási szabályzatával használva ezen beállításokkal konfigurálhatja az eszközöket a szervezetben.

## <a name="general"></a>Általános

- **Kamera** – Engedélyezi az eszköz kamerájának használatát.
- **Másolás és beillesztés (csak Samsung KNOX esetén)** – Az eszköz másolási és beillesztési funkcióinak engedélyezése.
- **Vágólap megosztása az alkalmazások között (csak Samsung KNOX esetén)** – Engedélyezi a vágólap használatát az alkalmazások közötti másolásra és beillesztésre.
- **Diagnosztikai adatok küldése (csak Samsung KNOX esetén)** – Megakadályozza, hogy a felhasználó diagnosztikai adatokat küldjön az eszközről.
- **Gyári beállítások visszaállítása (csak Samsung KNOX esetén)** – Lehetővé teszi, hogy a felhasználó visszaállítsa a gyári beállításokat az eszközön.
- **Földrajzi hely meghatározása (csak Samsung KNOX esetén)** – Lehetővé teszi, hogy az eszköz felhasználja a földrajzi helyre vonatkozó adatokat.
- **Kikapcsolás (csak Samsung KNOX esetén)** – Engedélyezi az eszköz felhasználó általi kikapcsolását.<br>Ha le van tiltva, a **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** beállítás nem adható meg.
- **Képernyőfelvétel (csak Samsung KNOX esetén)** – Lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.
- **Beszédfelismerési asszisztens (csak Samsung KNOX esetén)** – Engedélyezi a Beszédfelismerési asszisztens szoftver használatát az eszközön.
- **YouTube (csak Samsung KNOX esetén)** – Engedélyezi a YouTube alkalmazás használatát az eszközön.
- **Megosztott eszközök** – Felügyelt Samsung KNOX Standard-eszközök konfigurálása megosztáshoz. Ebben a módban a végfelhasználók Azure AD-beli hitelesítő adataikkal jelentkezhetnek be az eszközön. Az eszköz felügyelt marad, függetlenül attól, hogy használatban van-e vagy sem.<br>A bejelentkezett végfelhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.

## <a name="password"></a>Jelszó

- **Jelszó** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.|Yes|Yes|
- **Jelszó minimális hossza** – Megadja a felhasználó által beállítandó jelszó minimális hosszát (4 és 16 karakter között).
- **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – Az eszköz az itt megadott számú perc elteltével automatikusan zárolja magát.
- **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – Megadja, hogy hány sikertelen bejelentkezés legyen megengedett, mielőtt az eszközön tárolt adatok törölődnének.
- **Jelszó érvényessége (napokban)** – Meghatározza, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát.
-  **Kötelező jelszótípus** – Megadja a jelszó erősségének szintjét, valamint azt, hogy használható-e biometrikus eszköz. A következő lehetőségek közül választhat:
    - **Eszköz alapértelmezése**
    - **Alacsony biztonságú biometrikus**
    - **Legalább számok**
    - **Komplex numerikus** – Ismétlődő vagy egymást követő számokat, mint például az ’1111’ vagy az ’1234’ nem szabad megadni<sup>1</sup>
    - **Legalább betűk**
    - **Legalább alfanumerikus karakterek**
    - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása** – Megakadályozza, hogy a végfelhasználó általa korábban már használt jelszót hozzon létre.
- **Ujjlenyomattal történő zárolásfeloldás (csak Samsung KNOX esetén)** – Engedélyezi a támogatott eszközök ujjlenyomattal történő zárolásfeloldását.
- **Smart Lock és egyéb megbízhatósági ügynökök** – A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót (Samsung KNOX Standard 5.0 és újabb verziók). Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van. Így például abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.
- **Titkosítás** – Megköveteli, hogy az eszközön minden fájl titkosítva legyen.

<sup>1</sup> Mielőtt ezt e beállítást eszközökhöz rendeli, győződjön meg arról, hogy a Céges portál alkalmazás a legújabb verzióra van frissítve az érintett eszközökön.

Ha az **Összetett numerikus** beállítást konfigurálja, majd azt egy 5.0-nál korábbi verziójú Androidot futtató eszközhöz rendeli, az az alábbi jelenségeket eredményezi.
- A Céges portál alkalmazás 1704-esnél korábbi verziója esetén nem érvényesül PIN-kód-szabályzat az eszközön, és hibaüzenet jelenik meg az Intune-portálon.
- Ha a Céges portál alkalmazás 1704-es vagy későbbi verzióját futtatja, csak egyszerű PIN-kód alkalmazható. Az Android 5.0-nál korábbi verziói nem támogatják ezt a beállítást. Hibaüzenet nem jelenik meg az Intune-portálon.


## <a name="google-play-store"></a>Google Play Áruház

- **Google Play Áruház (csak Samsung KNOX esetén)** – Engedélyezi a felhasználó számára a Google Play Áruház elérését az eszközön.

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában konfigurálhatja az alábbi listák egyikét mind androidos, mind Samsung KNOX Standard-alapú eszközökhöz:

A **Letiltott alkalmazások** listája – Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyeknek a telepítése és futtatása nincs engedélyezve a felhasználók számára.
A **Jóváhagyott alkalmazások** listája – Azokat az alkalmazásokat tartalmazza, amelyeknek a telepítése engedélyezve van a felhasználók számára. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek egyéb alkalmazásokat. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.
A tiltott alkalmazások beállításait tartalmazó eszközprofilokat hozzá kell rendelni a kívánt felhasználócsoportokhoz.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet. Tetszés szerint megadhatja az alkalmazás kiadóját, valamint az alkalmazásnak az alkalmazás-áruházbeli URL-címét.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Az alkalmazás áruházbeli URL-címének megadása

Ha szeretné megadni egy alkalmazás URL-címét a megfelelő és nem megfelelő alkalmazások listájában, végezze el az alábbiakat:

A [Google Play Alkalmazások szakaszában](https://play.google.com/store/apps) keresse meg a használni kívánt alkalmazást.

Nyissa meg az alkalmazás telepítési lapját, és másolja az URL-címet a vágólapra. Most ezt a címet felhasználhatja URL-címként a kompatibilis vagy a nem kompatibilis alkalmazások listájában.

Például: Keressen rá a Google Play-ben a Microsoft Office Mobile kifejezésre. Használja a következő URL-címet: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>További beállítások

Az **Importálás** elemre is kattinthat a lista csv-fájlból való betöltéséhez. A használandó formátum: <*alkalmazás URL-címe*>, <*alkalmazás neve*>, <*alkalmazás kiadója*>. Az **Exportálás** gombra kattintva pedig létrehozhat egy CSV-fájlt, amely ugyanebben a formátumban tartalmazza a korlátozott alkalmazások listáját.      

## <a name="browser"></a>Böngésző

- **Webböngésző (csak Samsung KNOX esetén)** – Meghatározza, hogy lehet-e használni az eszköz alapértelmezett webböngészőjét.
- **Automatikus kitöltés (csak Samsung KNOX esetén)** – Engedélyezi a használni kívánt webböngésző automatikus kitöltési funkcióját.
- **Cookie-k (csak Samsung KNOX esetén)** – Engedélyezi, hogy az eszköz webböngészője cookie-kat használjon.
- **Javascript (csak Samsung KNOX esetén)** – Engedélyezi az eszköz webböngészője számára a Java-szkriptek futtatását.
- **Előugró ablakok (csak Samsung KNOX esetén)** – A böngésző előugróablak-funkciójának engedélyezése.

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Google biztonsági mentés (csak Samsung KNOX esetén)** – Engedélyezi a Google-fiók biztonsági mentését.
- **Google-fiók automatikus szinkronizálása (csak Samsung KNOX esetén)** – Engedélyezi a Google-fiókbeállítások automatikus szinkronizálását.
- **Cserélhető tárolók (csak Samsung KNOX esetén)** – Engedélyezi az eszköz számára a cserélhető tárolók, például SD-kártyák használatát.
- **Tárolókártyák titkosítása (csak Samsung KNOX esetén)** – Meghatározza, hogy kötelező legyen-e az eszköz tárolókártyájának titkosítása.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

- **Adatroaming (csak Samsung KNOX esetén)** – Engedélyezi az adatroaming használatát, ha az eszköz mobilhálózathoz csatlakozik.
- **SMS- és MMS-funkciók (csak Samsung KNOX esetén)** – Engedélyezi az SMS- és MMS-üzenetküldést az eszközön.
- **Hangtárcsázás (csak Samsung KNOX esetén)** – Engedélyezi vagy letiltja a hangtárcsázás funkciót az eszközön.
- **Hangroaming (csak Samsung KNOX esetén)** – Engedélyezi a hangroaming használatát, ha az eszköz mobilhálózathoz csatlakozik.
- **Bluetooth (csak Samsung KNOX esetén)** – Engedélyezi a Bluetooth használatát az eszközön.
- **NFC (csak Samsung KNOX esetén)** – Engedélyezi a kis hatótávolságú kommunikációt használó műveleteket a támogatott eszközön.
- **Wi-Fi (csak Samsung KNOX esetén)** – Engedélyezi az eszköz Wi-Fi-funkcióinak használatát.
- **Wi-Fi-alapú internetmegosztás (csak Samsung KNOX esetén)** – Engedélyezi a Wi-Fi-alapú internetmegosztást az eszközön.

## <a name="kiosk"></a>Kioszkmód

A kioszkmód-beállítások csak a Samsung KNOX Standard-eszközökre vonatkoznak.

- **Felügyelt alkalmazás kiválasztása** – Válassza ki a következők egyikét egy vagy több, az eszköz kioszkmódjában futtatható alkalmazás hozzáadásához. Az itt megadotton kívül más alkalmazás nem futtatható az eszközön.
    - **Alkalmazások hozzáadása csomagnév szerint**
    - **Alkalmazások hozzáadása URL-cím szerint**
    - **Felügyelt alkalmazások hozzáadása**.
- **Képernyőalvás gombja** – Engedélyezi vagy letiltja a képernyő ébresztőgombját az eszközön.
- **Hangerőgombok** – Engedélyezheti vagy letilthatja a hangerőszabályzó gombok használatát az eszközön.
