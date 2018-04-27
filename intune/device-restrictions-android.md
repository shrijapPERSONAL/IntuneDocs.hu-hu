---
title: Eszközkorlátozásokra vonatkozó beállítások a Microsoft Intune-ban Android esetén
titlesuffix: ''
description: A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre az Android rendszerű eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 619d9e86bd130a617155d262f3e09882ce26ec1e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-android-and-samsung-knox-standard-device-restriction-settings"></a>Android- és Samsung Knox Standard-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cikk bemutatja a Microsoft Intune összes olyan eszközkorlátozásokra vonatkozó beállítását, melyek konfigurálhatók Android rendszerű eszközökhöz.

>[!TIP]
>Ha a kívánt beállítások nem elérhetőek, lehet, hogy konfigurálni tudja az eszközöket egy [egyéni profil](custom-settings-android.md) használatával.

## <a name="general"></a>Általános

- **Kamera** – Engedélyezi az eszköz kamerájának használatát.
- **Másolás és beillesztés (csak Samsung Knox esetén)** – Az eszköz másolási és beillesztési funkcióinak engedélyezése.
- **Vágólap megosztása az alkalmazások között (csak Samsung Knox esetén)** – Engedélyezi a vágólap használatát az alkalmazások közötti másolásra és beillesztésre.
- **Diagnosztikai adatok küldése (csak Samsung Knox esetén)** – Megakadályozza, hogy a felhasználó diagnosztikai adatokat küldjön az eszközről.
- **Gyári beállítások visszaállítása (csak Samsung Knox esetén)** – Lehetővé teszi, hogy a felhasználó visszaállítsa a gyári beállításokat az eszközön.
- **Földrajzi hely meghatározása (csak Samsung Knox esetén)** – Lehetővé teszi, hogy az eszköz felhasználja a földrajzi helyre vonatkozó adatokat.
- **Kikapcsolás (csak Samsung Knox esetén)** – Engedélyezi az eszköz felhasználó általi kikapcsolását.<br>Ha le van tiltva, a **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** beállítás nem adható meg.
- **Képernyőfelvétel (csak Samsung Knox esetén)** – Lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.
- **Beszédfelismerési asszisztens (csak Samsung Knox esetén)** – Engedélyezi a Beszédfelismerési asszisztens szoftver használatát az eszközön.
- **YouTube (csak Samsung Knox esetén)** – Engedélyezi a YouTube alkalmazás használatát az eszközön.
- **Megosztott eszközök (csak Samsung Knox esetében)** – Felügyelt Samsung Knox Standard-eszközök konfigurálása megosztáshoz. Ebben a módban a végfelhasználók Azure AD-beli hitelesítő adataikkal jelentkezhetnek be az eszközön. Az eszköz felügyelt marad, függetlenül attól, hogy használatban van-e vagy sem.<br>Az SCEP-tanúsítványprofillal együtt használva ez a szolgáltatás lehetővé teszi a végfelhasználóknak, hogy megosszanak egy eszközt úgy, hogy az összes felhasználónak ugyanazok az alkalmazások legyenek elérhetők, de a saját SCEP-felhasználói tanúsítványukkal.  A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.  Ez a szolgáltatás csak az üzletági alkalmazásokra érvényes.
- **Dátum- és időmódosítás letiltása (Samsung Knox)** – Megakadályozza, hogy a felhasználók módosítsák az eszköz dátum- és időbeállításait. 

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
- **Ujjlenyomattal történő zárolásfeloldás (csak Samsung Knox esetén)** – Engedélyezi a támogatott eszközök ujjlenyomattal történő zárolásfeloldását.
- **Smart Lock és egyéb megbízhatósági ügynökök** – A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót (Samsung Knox Standard 5.0 és újabb verziók). Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van. Így például abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.
- **Titkosítás** – Megköveteli, hogy az eszközön minden fájl titkosítva legyen.

<sup>1</sup> Mielőtt ezt e beállítást eszközökhöz rendeli, győződjön meg arról, hogy a Céges portál alkalmazás a legújabb verzióra van frissítve az érintett eszközökön.

Ha az **Összetett numerikus** beállítást konfigurálja, majd azt egy 5.0-nál korábbi verziójú Androidot futtató eszközhöz rendeli, az az alábbi jelenségeket eredményezi.
- A Céges portál alkalmazás 1704-esnél korábbi verziója esetén nem érvényesül PIN-kód-szabályzat az eszközön, és hibaüzenet jelenik meg az Azure Portalon.
- Ha a Céges portál alkalmazás 1704-es vagy későbbi verzióját futtatja, csak egyszerű PIN-kód alkalmazható. Az Android 5.0-nál korábbi verziói nem támogatják ezt a beállítást. Hibaüzenet nem jelenik meg az Azure Portalon.


## <a name="google-play-store"></a>Google Play Áruház

- **Google Play Áruház (csak Samsung Knox esetén)** – Engedélyezi a felhasználó számára a Google Play Áruház elérését az eszközön.

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában konfigurálhatja az alábbi listák egyikét mind androidos, mind Samsung Knox Standard-alapú eszközökhöz:

A **Letiltott alkalmazások** listája – Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyeknek a felhasználó általi telepítését és futtatását jelenti a rendszer.
A **Jóváhagyott alkalmazások** listája – Azokat az alkalmazásokat tartalmazza, amelyeknek a telepítése engedélyezve van a felhasználók számára. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek egyéb alkalmazásokat. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.
A tiltott alkalmazások beállításait tartalmazó eszközprofilokat hozzá kell rendelni a kívánt felhasználócsoportokhoz.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet. Tetszés szerint megadhatja az alkalmazás kiadóját, valamint az alkalmazásnak az alkalmazás-áruházbeli URL-címét.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Az alkalmazás áruházbeli URL-címének megadása

Ha szeretné megadni egy alkalmazás URL-címét a megfelelő és nem megfelelő alkalmazások listájában, végezze el az alábbiakat:

A [Google Play Alkalmazások szakaszában](https://play.google.com/store/apps) keresse meg a használni kívánt alkalmazást.

Nyissa meg az alkalmazás telepítési lapját, és másolja az URL-címet a vágólapra. Most ezt a címet felhasználhatja URL-címként a kompatibilis vagy a nem kompatibilis alkalmazások listájában.

Példa: Keressen rá a [Google Play Alkalmazások szakaszában](https://play.google.com/store/apps) a **Microsoft Plannerre**. Használja a következő URL-címet: **https://play.google.com/store/apps/details?id=com.microsoft.planner**.

### <a name="additional-options"></a>További beállítások

Az **Importálás** elemre is kattinthat a lista csv-fájlból való betöltéséhez. A használandó formátum: <*alkalmazás URL-címe*>, <*alkalmazás neve*>, <*alkalmazás kiadója*>. Az **Exportálás** gombra kattintva pedig létrehozhat egy CSV-fájlt, amely ugyanebben a formátumban tartalmazza a korlátozott alkalmazások listáját.      

## <a name="browser"></a>Böngésző

- **Webböngésző (csak Samsung Knox esetén)** – Meghatározza, hogy lehet-e használni az eszköz alapértelmezett webböngészőjét.
- **Automatikus kitöltés (csak Samsung Knox esetén)** – Engedélyezi a használni kívánt webböngésző automatikus kitöltési funkcióját.
- **Cookie-k (csak Samsung Knox esetén)** – Engedélyezi, hogy az eszköz webböngészője cookie-kat használjon.
- **Javascript (csak Samsung Knox esetén)** – Engedélyezi az eszköz webböngészője számára a Javascript-parancsfájlok futtatását.
- **Előugró ablakok (csak Samsung Knox esetén)** – A böngésző előugróablak-funkciójának engedélyezése.

## <a name="allow-or-block-apps"></a>Alkalmazások engedélyezése és letiltása

Ezzel a beállítással megadható azoknak az alkalmazásoknak a listája, amelyeket kizárólag Samsung Knox Standard eszközökön engedélyezett telepíteni és futtatni.
Ezen kívül megadhatóak olyan telepített alkalmazások is, amelyek rejtve vannak az eszköz elhasználója elől. A felhasználók ezeket az alkalmazásokat nem futtathatják.

- **Telepíthető alkalmazások (csak Samsung Knox Standard esetén)**
- **Nem indítható alkalmazások (csak Samsung Knox Standard esetén)**
- **Felhasználó elől elrejtett alkalmazások (csak Samsung Knox Standard esetén)**

Mindegyik beállításnál egy alkalmazáslistát kell konfigurálnia az alábbiak használatával:

- **Alkalmazások hozzáadása csomagnév szerint** – Elsősorban üzletági alkalmazásoknál használatos. Adja meg az alkalmazás nevét, majd az alkalmazáscsomag nevét.
- **Alkalmazások hozzáadása URL-cím alapján** – Adja meg az alkalmazás nevét, majd az alkalmazás Google Play Áruházbeli URL-címét.
- **Felügyelt alkalmazások hozzáadása** – Az Intune-nal felügyelt alkalmazások listájából válassza ki a kívánt alkalmazást.

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Google biztonsági mentés (csak Samsung Knox esetén)** – Engedélyezi a Google-fiók biztonsági mentését.
- **Google-fiók automatikus szinkronizálása (csak Samsung Knox esetén)** – Engedélyezi a Google-fiókbeállítások automatikus szinkronizálását.
- **Cserélhető tárolók (csak Samsung Knox esetén)** – Engedélyezi az eszköz számára a cserélhető tárolók, például SD-kártyák használatát.
- **Tárolókártyák titkosítása (csak Samsung Knox esetén)** – Meghatározza, hogy kötelező legyen-e az eszköz tárolókártyájának titkosítása.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

- **Adatroaming (csak Samsung Knox esetén)** – Engedélyezi az adatroaming használatát, ha az eszköz mobilhálózathoz csatlakozik.
- **SMS- és MMS-funkciók (csak Samsung Knox esetén)** – Engedélyezi az SMS- és MMS-üzenetküldést az eszközön.
- **Hangtárcsázás (csak Samsung Knox esetén)** – Engedélyezi vagy letiltja a hangtárcsázás funkciót az eszközön.
- **Hangroaming (csak Samsung Knox esetén)** – Engedélyezi a hangroaming használatát, ha az eszköz mobilhálózathoz csatlakozik.
- **Bluetooth (csak Samsung Knox esetén)** – Engedélyezi a Bluetooth használatát az eszközön.
- **NFC (csak Samsung Knox esetén)** – Engedélyezi a kis hatótávolságú kommunikációt használó műveleteket a támogatott eszközön.
- **Wi-Fi (csak Samsung Knox esetén)** – Engedélyezi az eszköz Wi-Fi-funkcióinak használatát.
- **Wi-Fi-alapú internetmegosztás (csak Samsung Knox esetén)** – Engedélyezi a Wi-Fi-alapú internetmegosztást az eszközön.

## <a name="kiosk"></a>Kioszkmód

A kioszkmód csak a Samsung Knox Standard eszközökre, és csak az Intune-nal felügyelt alkalmazásokra vonatkozik.

- **Felügyelt alkalmazás kiválasztása** – Válassza ki a következő lehetőségek egyikét egy vagy több, az eszköz kioszkmódjában futtatható felügyelt alkalmazás hozzáadásához. Az itt megadotton kívül más alkalmazás nem futtatható az eszközön. Előtelepített böngészők nem definiálhatók olyan alkalmazásként, amelynek engedélyezett a futás az eszköz kioszkmódban való használatakor. Ha böngészőre van szüksége, fontolja meg a [Felügyelt böngésző](app-configuration-managed-browser.md) használatát.
    - **Alkalmazások hozzáadása csomagnév szerint**
    - **Alkalmazások hozzáadása URL-cím szerint**
    - **Felügyelt alkalmazások hozzáadása**.
- **Képernyőalvás gombja** – Engedélyezi vagy letiltja a képernyő ébresztőgombját az eszközön.
- **Hangerőgombok** – Engedélyezheti vagy letilthatja a hangerőszabályzó gombok használatát az eszközön.


## <a name="next-steps"></a>További lépések

Az [Eszközkorlátozásokra vonatkozó beállítások konfigurálása](device-restrictions-configure.md) cikk utasításainak megfelelően a továbbiakban hozza létre és rendelje hozzá az eszközkorlátozási profilt.
