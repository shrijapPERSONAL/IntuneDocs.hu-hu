---
title: "Eszközkorlátozásokra vonatkozó beállítások az Intune-ban Android esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre az Android-eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 0c3a5ef16da3e2c395cb71a0fc8a23d531cfa02c
ms.contentlocale: hu-hu
ms.lasthandoff: 05/05/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Android- és Samsung KNOX Standard-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Általános

|||||
|-|-|-|-|
|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|**Fényképezőgép**|Engedélyezi az eszköz kamerájának használatát.|Igen|Igen|
|**Másolás és beillesztés**|Az eszköz másolási és beillesztési funkcióinak engedélyezése.|Nem|Igen|
|**Vágólap megosztása az alkalmazások között**|A vágólap használatának engedélyezése az alkalmazások közötti másoláshoz.|Nem|Igen|
|**Diagnosztikai adatok beküldése**|Megakadályozza, hogy a felhasználó diagnosztikai adatokat küldjön az eszközről.|Nem|Igen|
|**Gyári beállítások visszaállítása**|Lehetővé teszi, hogy a felhasználó visszaállítsa a gyári beállításokat az eszközön.|Nem|Igen|
|**Földrajzi hely**|Lehetővé teszi, hogy az eszköz felhasználja a földrajzi helyre vonatkozó adatokat (csak Samsung KNOX Standard-eszközökre vonatkozik).|Nem|Igen|
|**Kikapcsolás**|Az eszköz felhasználó általi kikapcsolásának engedélyezése.<br>Ha ez a beállítás le van tiltva, a **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** beállítás Samsung KNOX Standard-eszközökön nem működik.|Nem|Igen|
|**Képernyőfelvétel**|Lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.|Nem|Igen|
|**Hangsegéd**|Hangsegéd szoftverek használatának engedélyezése az eszközön.|Nem|Igen|
|**YouTube**|A YouTube alkalmazás használatának engedélyezése az eszközön.|Nem|Igen|
|**Megosztott eszközök**|Felügyelt Samsung KNOX Standard-eszközök konfigurálása megosztáshoz. Ebben a módban a felhasználók Azure AD-beli hitelesítő adataikkal jelentkezhetnek be és ki az eszközön, de az központi felügyelet alatt marad, akár használatban van, akár nem.<br>A bejelentkezett végfelhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.|Nem|Igen|

## <a name="password"></a>Jelszó

|||||
|-|-|-|-|
|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|**Jelszó**|Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.|Igen|Igen|
|**Jelszó minimális hossza**|Megadja a felhasználó által beállítandó jelszó minimális hosszát (4 és 16 karakter között).|Igen|Igen|
|**Képernyőzárolás legfeljebb ennyi perc inaktivitás után**|Az eszköz az itt megadott számú másodperc elteltével automatikusan zárolja magát.|Igen|Igen|
|**Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat**|Megadja, hogy hány sikertelen bejelentkezés legyen megengedett, mielőtt az eszközön tárolt adatok törölve lennének.|Igen|Igen|
|**Jelszó lejárata (nap)**|Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.|Igen|Igen|
|**Kötelező jelszótípus**|Megadja a jelszó erősségének szintjét, valamint azt, hogy használható-e biometrikus eszköz. A következő lehetőségek közül választhat:<br><br>    -     **Eszköz alapértelmezése**<br>-     **Alacsony biztonságú biometrikus**<br>    -     **Legalább számok**<br>    -     **Összetett numerikus** (ismétlődő vagy egymást követő számok, mint a „1111” vagy „1234” nem engedélyezettek)<sup>1</sup><br>    -     **Legalább betűk**<br>    -     **Legalább alfanumerikus karakterek**<br>    -     **Legalább alfanumerikus karakterek és szimbólumok**|Igen|Igen|
|**Korábbi jelszavak újbóli használatának tiltása**|Megakadályozza, hogy a végfelhasználó általa korábban már használt jelszót hozzon létre.|Igen|Igen|
|**Ujjlenyomattal történő zárolásfeloldás**|Engedélyezi az ujjlenyomattal történő zárolásfeloldást a támogatott eszközökön.|Nem|Igen|
|**Smart Lock és egyéb megbízhatósági ügynökök**|A kompatibilis Android-eszközökön vezérelheti vele az intelligens zárolás funkciót (Samsung KNOX Standard 5.0 és újabb verziók). Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van, például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.|Igen (5.0 és újabb verziók)|Nem|
|**Titkosítás**|Az eszközön található összes fájlnak titkosítva kell lennie.|Igen|Igen|

<sup>1</sup> Mielőtt ezt e beállítást eszközökhöz rendeli, győződjön meg arról, hogy a Vállalati portál alkalmazás a legújabb verzióra van frissítve az érintett eszközökön.

Ha az **Összetett numerikus** beállítást konfigurálja, majd azt egy 5.0-nál korábbi verziójú Androidot futtató eszközhöz rendeli, az az alábbi jelenségeket eredményezi.
- A Vállalati portál alkalmazás 1704-esnél korábbi verziója esetén nem érvényesül PIN-kód-szabályzat az eszközön, és hibaüzenet jelenik meg az Intune-portálon.
- Amennyiben a Vállalati portál az 1704-es verzióra van frissítve, csupán egyszerű PIN-kód alkalmazható. Az Android 5.0-nál korábbi verziói nem támogatják ezt a beállítást. Hibaüzenet nem jelenik meg az Intune-portálon.


## <a name="google-play-store"></a>Google Play Áruház

|||||
|-|-|-|-|
|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|**Google Play Áruház**|A Google Play Áruház használatának engedélyezése az eszközön|Nem|Igen|

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

Az **Importálás** gombra kattintva feltöltheti a listát egy CSV-fájlból, mely a következő formátumú: <*alkalmazás URL-címe*>, <*alkalmazás neve*>, <*alkalmazás kiadója*>. Az **Exportálás** gombra kattintva pedig létrehozhat egy CSV-fájlt, amely ugyanebben a formátumban tartalmazza a korlátozott alkalmazások listáját.        

## <a name="browser"></a>Böngésző
|||||
|-|-|-|-|
|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|**Webböngésző**|Ezzel a beállítással adható meg, hogy engedélyezett-e az eszköz alapértelmezett webböngészőjének használata.|Nem|Igen|
|**Automatikus kitöltés**|A böngésző automatikus kitöltési funkciójának engedélyezése.|Nem|Igen|
|**Cookie-k**|Engedélyezi, hogy az eszköz webböngészője cookie-kat használjon.|Nem|Igen|
|**Javascript**|Engedélyezi, hogy az eszköz webböngészője Javascript-parancsprogramokat futtasson.|Nem|Igen|
|**Előugró ablakok**|A böngésző előugróablak-blokkoló funkciójának engedélyezése.|Nem|Igen|

## <a name="cloud-and-storage"></a>Felhő és tárolás
|||||
|-|-|-|-|
|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|**Google-biztonsági mentés**|A Google-fiók biztonsági mentésének engedélyezése.|Nem|Igen|
|**Google-fiók automatikus szinkronizálása**|Google-fiókbeállítások automatikus szinkronizálásának engedélyezése.|Nem|Igen|
|**Cserélhető tároló**|Cserélhető tárolók (például SD-kártya) használatának engedélyezése az eszközön.|Nem|Igen|
|**Titkosítás tárolókártyákon**|Ez a beállítás határozza meg, hogy kötelező legyen-e az eszköz tárolókártyájának titkosítása.|Nem|Igen|

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok
|||||
|-|-|-|-|
|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|**Adatroaming**|Adatroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|Nem|Igen|
|**SMS- és MMS-funkciók**|SMS- és MMS-üzenetek engedélyezése az eszközön.|Nem|Igen|
|**Hangtárcsázás**|A hangtárcsázási funkció engedélyezése vagy letiltása az eszközön.|Nem|Igen|
|**Hangroaming**|Hangroaming használatának engedélyezése, ha az eszköz mobilhálózathoz csatlakozik.|Nem|Igen|
|**Bluetooth**|Az eszköz Bluetooth-funkciójának engedélyezése.|Nem|Igen|
|**NFC**|A kis hatótávolságú kommunikációt használó műveletek engedélyezése (ha az eszköz támogatja ezt a funkciót).|Nem|Igen|
|**Wi-Fi**|Az eszköz Wi-Fi-funkciójának engedélyezése.|Nem|Igen|
|**Wi-Fi tethering**|Az eszköz Wi-Fi-alapú internetmegosztási funkciójának engedélyezése.|Nem|Igen|

## <a name="kiosk"></a>Kioszkmód
|||||
|-|-|-|-|
|Beállítás neve|Részletek|Android 4.0+|Samsung KNOX Standard|
|**Felügyelt alkalmazás kiválasztása**|Keresse meg, majd jelölje ki azt a felügyelt alkalmazást, amelynek engedélyezni szeretné, hogy az eszköz teljes képernyős módban futtassa (az áruházra mutató hivatkozásként megadott alkalmazások jelenleg nem támogatottak). Az itt megadotton kívül más alkalmazás nem futtatható az eszközön.|Nem|Igen|
|**Alvás gomb megnyomásakor**|Engedélyezheti vagy letilthatja a képernyő ébresztőgombját az eszközön.|Nem|Igen|
|**Hangerő gombok**|Engedélyezheti vagy letilthatja a hangerőszabályzó gombok használatát az eszközön.|Nem|Igen|

