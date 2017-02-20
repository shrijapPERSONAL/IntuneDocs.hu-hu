---
title: "Az Intune eszközkorlátozásokra vonatkozó beállításai Androidhoz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre az Android-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 74023866802eb4c13e7e9ff97e8048afe7d62409
ms.openlocfilehash: 40e04f1f8e7972bcd72cceae272d8295a496df7a


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-intune-azure-preview"></a>Adroid- és Samsung KNOX Standard-eszközök korlátozásaira vonatkozó beállítások az Azure-os Intune előzetes verziójában

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Általános
-   **Kamera** – Engedélyezi az eszköz kamerájának használatát.
-   **Másolás és beillesztés** – Az eszköz másolási és beillesztési funkcióinak engedélyezése.
-   **Vágólap megosztása az alkalmazások között** – Engedélyezi a vágólap használatát az alkalmazások közötti másolásra és beillesztésre (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Diagnosztikai adatok küldése** – Megakadályozza, hogy a felhasználó diagnosztikai adatokat küldjön az eszközről.    
-   **Gyári beállítások visszaállítása** – Lehetővé teszi, hogy a felhasználó visszaállítsa a gyári beállításokat az eszközön.
-   **Földrajzi hely** – Lehetővé teszi, hogy az eszköz felhasználja a földrajzi helyre vonatkozó adatokat (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Kikapcsolás** – Engedélyezi az eszköz felhasználó általi kikapcsolását.<br>Ha ez a beállítás le van tiltva, a **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** beállítás Samsung KNOX Standard-eszközökön nem működik.
-   **Képernyőfelvétel** – Lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.
-   **Beszédfelismerési asszisztens** – Engedélyezi a Beszédfelismerési asszisztens szoftver használatát az eszközön (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **YouTube** – Engedélyezi a YouTube alkalmazás használatát az eszközön (csak Samsung KNOX Standard-eszközökre vonatkozik).

## <a name="password"></a>Jelszó
-   **Jelszó megkövetelése** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
-   **Jelszó minimális hossza** – Megadja a felhasználó által beállítandó jelszó minimális hosszát (4 és 16 karakter között).
-   **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – Az eszköz az itt megadott számú perc elteltével automatikusan zárolja magát.
-   **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – Megadja, hogy hány sikertelen bejelentkezés legyen megengedett, mielőtt az eszközön tárolt adatok törölődnének.
-   **Jelszó érvényessége (nap)** – Meghatározza, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát.
-   **Kötelező jelszó típusa** – Megadja a jelszó erősségének szintjét, valamint azt, hogy használható-e biometrikus eszköz.
-   **Korábbi jelszavak újbóli használatának tiltása** – Megakadályozza, hogy a végfelhasználó általa korábban már használt jelszót hozzon létre.
-   **Ujjlenyomattal történő zárolásfeloldás** – Engedélyezi az ujjlenyomattal történő zárolásfeloldást a támogatott eszközökön.
-   **Smart Lock és egyéb megbízhatósági ügynökök** – A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót (Samsung KNOX Standard 5.0 és újabb verziók). Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van, például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.
-   **Titkosítás** – Megköveteli, hogy az eszközön minden fájl titkosítva legyen.

## <a name="google-play-store"></a>Google Play Áruház

-   **Google Play Áruház** – Engedélyezi a felhasználó számára a Google Play Áruház elérését az eszközön (csak Samsung KNOX Standard-eszközökre vonatkozik).

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

A **Letiltott alkalmazások** listája – Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyeknek a telepítése és futtatása nincs engedélyezve a felhasználók számára.
A **Jóváhagyott alkalmazások** listája – Azokat az alkalmazásokat tartalmazza, amelyeknek a telepítése engedélyezve van a felhasználók számára. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.
A tiltott alkalmazások beállításait tartalmazó eszközprofilokat hozzá kell rendelni a kívánt felhasználócsoportokhoz.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet. Tetszés szerint megadhatja az alkalmazás kiadóját, valamint az alkalmazásnak az alkalmazás-áruházbeli URL-címét.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Az alkalmazás áruházbeli URL-címének megadása

Ha szeretné megadni egy alkalmazás URL-címét a megfelelő és nem megfelelő alkalmazások listájában, végezze el az alábbiakat:

A [Google Play Alkalmazások szakaszában](https://play.google.com/store/apps) keresse meg a használni kívánt alkalmazást.

Nyissa meg az alkalmazás telepítési lapját, és másolja az URL-címet a vágólapra. Most ezt a címet felhasználhatja URL-címként a kompatibilis vagy a nem kompatibilis alkalmazások listájában.

Például: Keressen rá a Google Play-ben a Microsoft Office Mobile kifejezésre. A használt URL-cím a következő: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>További beállítások

Az **Importálás** gombra kattintva egy CSV formátumú fájlt is beolvashat. Ennek a következő formátumúnak kell lennie: <*az alkalmazás URL-címe*>, <*az alkalmazás neve*>, <*az alkalmazás kiadója*>. Az **Exportálás** gombra kattintva egy olyan CSV-fájlt hozhat létre, amely ugyanebben a formátumban tartalmazza a korlátozott alkalmazások listáját.      

## <a name="browser"></a>Böngésző
-   **Webböngésző** – Ezzel a beállítással adható meg, hogy engedélyezve van-e az eszköz alapértelmezett webböngészőjének használata.
-   **Automatikus kitöltés** – A böngésző automatikus kitöltési funkciójának engedélyezése.
-   **Cookie-k** – Engedélyezi, hogy az eszköz webböngészője cookie-kat használjon.
-   **JavaScript** – Engedélyezi, hogy az eszköz webböngészője Java-szkripteket futtasson.
-   **Előugró ablakok** – A böngésző előugróablak-blokkoló funkciójának engedélyezése.

## <a name="cloud-and-storage"></a>Felhő és tárolás
-   **Google biztonsági mentés** – Engedélyezi a Google-fiók biztonsági mentését.
-   **Google-fiók automatikus szinkronizálása** – Engedélyezi a Google-fiókbeállítások automatikus szinkronizálását.
-   **Cserélhető tárolók** – Engedélyezi az eszköz számára cserélhető tárolók, például SD-kártyák használatát (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Tárolókártyák titkosítása** – Ez a beállítás határozza meg, hogy kötelező legyen-e az eszköz tárolókártyájának titkosítása.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok
-   **Adatroaming** – Engedélyezi adatroaming használatát arra az esetre, ha az eszköz mobilhálózathoz csatlakozik (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **SMS- és MMS-funkciók** – Engedélyezi az SMS- és MMS-üzenetküldést az eszközön (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Hangtárcsázás** – Engedélyezi vagy letiltja a hangtárcsázás funkciót az eszközön (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Hangroaming** – Engedélyezi hangroaming használatát arra az esetre, ha az eszköz mobilhálózathoz csatlakozik (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Bluetooth** – Engedélyezi a Bluetooth használatát az eszközön (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **NFC** – Engedélyezi kis hatótávolságú kommunikációt (NFC) használó műveleteket, ha az eszköz támogatja ezt a funkciót (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Wi-Fi** – Engedélyezi az eszköz Wi-Fi képességeinek használatát (csak Samsung KNOX Standard-eszközökre vonatkozik).
-   **Wi-Fi-alapú internetmegosztás** – Engedélyezi a Wi-Fi-alapú internetmegosztást az eszközön (csak Samsung KNOX Standard-eszközökre vonatkozik).

## <a name="kiosk"></a>Kioszkmód
-   **Felügyelt alkalmazás kiválasztása** – Keresse meg, majd jelölje ki azt a felügyelt alkalmazást, amelynek engedélyezni szeretné, hogy az eszköz teljes képernyős módban futtassa (az áruházra mutató hivatkozásként megadott alkalmazások jelenleg nem támogatottak). Az itt megadotton kívül más alkalmazás nem futtatható az eszközön.
-   **Képernyőalvás gombja** – Engedélyezi vagy letiltja a képernyő ébresztőgombját az eszközön.
-   **Hangerőgombok** – Engedélyezheti vagy letilthatja a hangerőszabályzó gombok használatát az eszközön.



<!--HONumber=Feb17_HO1-->


