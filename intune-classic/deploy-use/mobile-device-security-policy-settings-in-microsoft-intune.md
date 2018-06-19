---
title: Mobileszközök biztonsági házirendjének beállításai
description: Az Intune használatával konfigurálhatja azokat a beállításokat, amelyeket a vállalat felügyelt eszközein kíván érvénybe léptetni.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 83536a4d9858454505a84a2e394ace1119255049
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31031855"
---
# <a name="mobile-device-security-policy-settings-in-microsoft-intune"></a>Mobileszközök biztonsági házirendjének beállításai a Microsoft Intune-nal

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

> [!IMPORTANT]
> A Microsoft Intune most már külön konfigurációs szabályzatokat biztosít a különböző eszközplatformokhoz. Ezek a szabályzatok a felhasználható legfrissebb beállításokat tartalmazzák. Továbbra is használhatja a mobileszköz-biztonsági szabályzatot, és a meglévő telepítések továbbra is működni fognak. Mindazonáltal fel kell készülnie az új konfigurációs szabályzatokra való mielőbbi áttérésre, mivel a későbbiekben el lesz távolítva a mobileszköz-biztonsági szabályzat.

Az Intune mobileszköz-biztonsági szabályzataival konfigurálhatja mindazokat a beállításokat, amelyeket a vállalat felügyelt eszközein kíván érvénybe léptetni. Ezek a beállítások az eszközök működésének és biztonsági funkcióinak szabályozására szolgálnak.

Mobileszköz-biztonsági szabályzatokat a következő eszköztípusok esetében hozhat létre és léptethet érvénybe:

-   Windows RT 8.1- és regisztrált Windows 8.1-eszközök

-   Windows RT

-   Windows Phone 8 és Windows Phone 8.1

-   iOS

-   Android és Samsung KNOX Standard

> [!NOTE]
> Egyes beállítások csak bizonyos eszközökre alkalmazhatók. A konfigurálható beállítások teljes listáját lásd az alábbi táblázatokban.
> 2016 októberétől kivezetjük a Windows 8 Vállalati portál alkalmazásainak támogatását a Microsoft Intune-ban. Egyúttal a Windows Phone 8 és WinRT platform Microsoft Intune-beli támogatását is kivezetjük. Ennek következményeképpen nem fog tudni Windows Phone 8 vagy WinRT rendszerű eszközöket regisztrálni vagy frissíteni. A már regisztrált Windows Phone 8, WinRT és Windows 8 rendszerű eszközöket továbbra is felügyelheti. Frissítse a Windows Phone 8 és Windows 8 rendszerű eszközöket Windows 8.1-es és a Windows Phone 8.1-es verzióra, és használja a megfelelő Windows 8.1-es és Windows Phone 8.1-es Vállalati portál alkalmazásokat az alkalmazások további zökkenőmentes terjesztéséhez ezekre az eszközökre.

## <a name="security-settings"></a>Biztonsági beállítások

|                                                                                                                                                                                        Beállítás neve                                                                                                                                                                                         | Windows 8.1 és Windows RT 8.1 | Windows RT | Windows Phone 8 és Windows Phone 8.1 |       iOS       | Android és Samsung KNOX Standard |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------|------------|---------------------------------------|-----------------|-----------------------------------|
|                                                                                                                                                                <strong>Jelszó megkövetelése a mobileszköz-zárolás feloldásához</strong>                                                                                                                                                                 |               Nem               |     Nem     |                  Igen                  |       Igen       |                Igen                |
|                                                                                                                 <strong>Kötelező jelszótípus</strong><br /><br />Ez a beállítás határozza meg a kötelező jelszótípust, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.                                                                                                                 |              Igen               |    Igen     |                  Igen                  |       Igen       |                Nem                 |
| <strong>Megkövetelt jelszótípus – a karakterkészletek minimális száma</strong><br /><br />A következő négy karakterkészlet létezik: kisbetűk, nagybetűk, számok és szimbólumok. Ez a beállítás azt határozza meg, hány különböző karakterkészletnek kell szerepelnie a jelszóban. iOS-eszközök esetén azonban azt határozza meg, hány szimbólumnak kell szerepelnie a jelszóban. |              Igen               |    Igen     |                  Igen                  |       Igen       |                Nem                 |
|                                                                                                                                                                          <strong>Jelszó minimális hossza</strong>                                                                                                                                                                           |              Igen               |    Igen     |                  Igen                  |       Igen       |                Igen                |
|                                                                                                                                               <strong>Egyszerű jelszavak engedélyezése</strong><br /><br />Egyszerű jelszó például a „0000” és az „1234”.                                                                                                                                                |               Nem               |     Nem     |                  Igen                  |       Igen       |                Nem                 |
|                                                                                                                                                  <strong>Ennyi ismétlődő sikertelen bejelentkezés után törlődnek végleg az adatok az eszközről</strong>                                                                                                                                                   |              Igen               |    Igen     |                  Igen                  |       Igen       |                Igen                |
|                                                                                                                                                         <strong>Képernyő kikapcsolása ennyi perc inaktivitás után</strong><sup>1</sup>                                                                                                                                                          |              Igen               |    Igen     |                  Igen                  |       Igen       |                Igen                |
|                                                                                                                                                                         <strong>Jelszó érvényessége (nap)</strong>                                                                                                                                                                         |              Igen               |    Igen     |                  Igen                  |       Igen       |                Igen                |
|                                                                                                                                                                         <strong>Korábbi jelszavak megjegyzése</strong>                                                                                                                                                                          |              Igen               |    Igen     |                  Igen                  |       Igen       |                Igen                |
|                                                                                                                                              <strong>Korábbi jelszavak megjegyzése</strong> – <strong>Korábbi jelszavak újbóli használatának tiltása</strong>                                                                                                                                              |              Igen               |    Igen     |                  Igen                  |       Igen       |                Igen                |
|                                                                                                                                                                              <strong>Jelszó erőssége</strong>                                                                                                                                                                              |               Nem               |     Nem     |                  Nem                   |       Nem        |                Igen                |
|                                                                                                                                                                       <strong>Képjelszó és PIN-kód engedélyezése</strong>                                                                                                                                                                       |              Igen               |    Igen     |                  Nem                   |       Nem        |                Nem                 |
|                                                                                                                                                             <strong>Jelszó kérése ennyi perc inaktivitás után</strong>                                                                                                                                                              |               Nem               |     Nem     |                  Nem                   |       Igen       |                Nem                 |
|                                                                                                                                                                          <strong>Ujjlenyomattal történő zárolásfeloldás engedélyezése</strong>                                                                                                                                                                          |               Nem               |     Nem     |                  Nem                   | iOS 7 és újabb verziók |                Nem                 |

<sup>1</sup>Ha iOS-eszközön konfigurálja a **Képernyő kikapcsolása ennyi perc inaktivitás után** és a **Jelszó kérése ennyi perc inaktivitás után** beállítást is, egymás után alkalmazza őket a rendszer. Ha például mindkét beállítást az **5** perc értékre állítja be, a képernyő 5 perc után automatikusan ki fog kapcsolni, és az eszköz további 5 perc után lesz zárolva. Ha azonban a felhasználó manuálisan kapcsolja ki a képernyőt, azonnal a második beállítás lesz alkalmazva. Ugyanebben a példában az eszköz 5 perccel azután lesz zárolva, hogy a felhasználó kikapcsolta a képernyőt.

Ha Windows RT rendszerű eszközökön léptet érvénybe jelszóhosszúságra vonatkozó szabályzatot, a rendszer a felhasználókat a jelszavuk módosítására kényszeríti, még akkor is, ha az aktuális jelszó megfelel a szabályzat követelményeinek.

## <a name="encryption-settings"></a>Titkosítási beállítások

|                                                                                                                                     Beállítás neve                                                                                                                                     | Windows 8.1 és Windows RT 8.1 | Windows RT |              Windows Phone 8 és Windows Phone 8.1              | iOS | Android és Samsung KNOX Standard |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------|------------|-----------------------------------------------------------------|-----|-----------------------------------|
| <strong>Titkosítás megkövetelése mobileszközön</strong><sup>1</sup><br /><br />A Windows Phone 8-telefonokon ezt <strong>Igen</strong>értékre kell állítani.<br /><br />Az iOS-eszközök titkosításának engedélyezéséhez <strong>A mobileszközök zárolásának feloldásához jelszó szükséges</strong>beállítást engedélyezni kell. |              Igen               |     Nem     |                               Igen                               | Nem  |                Igen                |
|                                                                    <strong>Titkosítás megkövetelése tárolókártyákon</strong><br /><br />Az Exchange ActiveSync által felügyelt eszközökre is vonatkozik.                                                                     |              nem áll rendelkezésre               |    nem áll rendelkezésre     | nem áll rendelkezésre <br />Az alkalmazások és a kapcsolódó adatok titkosítása automatikusan megtörténik. | nem áll rendelkezésre |                Igen                |

<sup>1</sup>További információ a Windows 8.1 rendszerű eszközökkel kapcsolatban:

-   A Windows 8.1 rendszerű eszközökön a titkosítás kényszerítéséhez minden egyes eszközön telepíteni kell a következőt: [2014. decemberi MDM-ügyfélfrissítés Windows rendszerre](http://support.microsoft.com/kb/3013816) .

-   Ha engedélyezi ezt a beállítást a Windows 8.1 rendszerű eszközökön, az eszköz valamennyi felhasználójának rendelkeznie kell Microsoft-fiókkal.

-   A titkosítás működéséhez az eszköznek teljesítenie kell a Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardvertanúsítvány követelményeit.

-   Amikor kényszeríti az eszközön a titkosítást, a helyreállítási kulcs csak a felhasználó OneDrive-fiókon keresztül elérhető Microsoft-fiókjából érhető el. Ez a kulcs nem állítható vissza egy felhasználó nevében.

## <a name="malware-settings"></a>Kártevőkre vonatkozó beállítások

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Hálózati tűzfal megkövetelése**|Igen|Nem|Nem|Nem|Nem|
|**SmartScreen engedélyezése**|Igen|Nem|Nem|Nem|Nem|

## <a name="system-settings"></a>Rendszerbeállítások

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Automatikus frissítések megkövetelése**|Igen|Nem|Nem|Nem|Nem|
|**Automatikus frissítések megkövetelése – Az automatikusan telepített frissítések minimális besorolása**<br /><br />Válassza ki az automatikus telepítésű frissítések besorolását:<br /><br />- **Fontos:** Minden fontosként megjelölt frissítést telepít.<br /><br />- **Ajánlott**: Minden fontosként vagy ajánlottként megjelölt frissítést telepít.|Igen|Nem|Nem|Nem|Nem|
|**Képernyőfelvétel engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Igen|Igen (csak Samsung KNOX Standard)|
|**Vezérlőközpont zárolási képernyőn való használatának engedélyezése**|Nem|Nem|Nem|iOS 7 és újabb verziók|Nem|
|**Értesítési nézet zárolási képernyőn való használatának engedélyezése**|Nem|Nem|Nem|iOS 7 és újabb verziók|Nem|
|**Ma nézet zárolási képernyőn való használatának engedélyezése**|Nem|Nem|Nem|iOS 7 és újabb verziók|Nem|
|**Felhasználói fiókok felügyelete**|Igen|Nem|Nem|Nem|Nem|
|**Diagnosztikai adatok küldésének engedélyezése**|Igen|Nem|Csak Windows Phone 8.1 esetén|Igen|Igen (csak Samsung KNOX Standard)|
|**Nem megbízható TLS-tanúsítványok engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**Személyespénztárca-szoftver használatának engedélyezése az eszköz zárolt állapotában**|Nem|Nem|Nem|Igen|Nem|
|**Gyári beállítások visszaállításának engedélyezése**|Nem|Nem|Nem|Nem|Igen (csak Samsung KNOX Standard)|


## <a name="cloud-settings--documents-and-data"></a>Felhőbeállítások – dokumentumok és adatok

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**iCloudba történő biztonsági mentés engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**Dokumentum iCloudba szinkronizálásának engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**Fényképadatfolyamok iCloudba szinkronizálásának engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**Biztonsági másolat titkosításának megkövetelése**|Nem|Nem|Nem|Igen|Nem|
|**Munkahelyi mappák URL-címe**<br /><br />Ez a beállítás adja meg munkahelyi mappa URL-címét, hogy lehetővé tegye a dokumentumok szinkronizálását az eszközök között.|Igen|Nem|Nem|Nem|Nem|
|**Google-fiók biztonsági mentésének engedélyezése**|Nem|Nem|Nem|Nem|Igen (csak Samsung KNOX Standard)|

## <a name="cloud-settings--accounts-and-synchronization"></a>Felhőbeállítások – fiókok és szinkronizálás

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Microsoft-fiók használatának engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Nem|
|**Google-fiók automatikus szinkronizálásának engedélyezése**|Nem|Nem|Nem|Nem|Igen (csak Samsung KNOX Standard)|

## <a name="email-settings"></a>E-mail beállítások

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**E-mail-mellékletek letöltésének engedélyezése a felhasználók számára**<sup>1</sup>|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|
|**E-mail-szinkronizálási időszak** <br /><br />Az Exchange ActiveSync által felügyelt eszközökre is vonatkozik.|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|
|**Engedélyezi az e beállításokat teljes mértékben nem támogató mobileszközök számára az Exchange felé történő szinkronizálást (Exchange ActiveSync)** <br /><br />Az Exchange ActiveSync által felügyelt eszközökre is vonatkozik.|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|nem áll rendelkezésre|
|**A Microsoft-fiók használata nem kötelező a Windows Mail alkalmazásban**|Igen|Nem|Nem|Nem|Nem|
|**Egyéni e-mail fiókok engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Nem|

## <a name="application-settings---browser"></a>Alkalmazásbeállítások – böngésző

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Webböngésző engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Igen|Igen (csak Samsung KNOX Standard)|
|**Automatikus kitöltés engedélyezése**|Igen|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Előugróablak-blokkoló engedélyezése**|Igen|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Cookie-k engedélyezése**|Nem|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Beépülő modulok engedélyezése**|Igen|Nem|Nem|Nem|Nem|
|**Active Scripting engedélyezése**|Igen|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Csalás elleni figyelmeztetés engedélyezése**|Igen|Nem|Nem|Igen|Nem|
|**Intranetes webhelyek engedélyezése egyszavas kereséshez**<br /><br />(Ez a beállítás engedélyezi, hogy az Internet Explorer egyetlen szó – például a „Bing” – megadása esetén megnyisson egy webhelyet.)|Igen|Nem|Nem|Nem|Nem|
|**Intranetes hálózatok automatikus felderítésének engedélyezése**|Igen|Nem|Nem|Nem|Nem|
|**Internetes biztonsági szint**|Igen|Nem|Nem|Nem|Nem|
|**Intranetes biztonsági szint**|Igen|Nem|Nem|Nem|Nem|
|**Megbízható helyek biztonsági szintje**|Igen|Nem|Nem|Nem|Nem|
|**Tiltott helyek biztonsági szintje**|Igen|Nem|Nem|Nem|Nem|
|**„Do Not Track” fejléc küldése**|Igen|Nem|Nem|Nem|Nem|
|**Vállalati üzemmód menüpont használatának engedélyezése**|Igen|Nem|Nem|Nem|Nem|
|**Vállalati üzemmód webhelylistájának helye**|Igen|Nem|Nem|Nem|Nem|

## <a name="application-settings---apps"></a>Alkalmazásbeállítások – alkalmazások

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Alkalmazás-áruház engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Igen|Igen (csak Samsung KNOX Standard)|
|**Jelszó kérése az alkalmazás-áruház használatához**|Nem|Nem|Nem|Igen|Nem|
|**Alkalmazáson belüli vásárlás engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**Felügyelt dokumentumok engedélyezése más nem felügyelt alkalmazásokban**|Nem|Nem|Nem|iOS 7 és újabb verziók|Nem|
|**Nem felügyelt dokumentumok engedélyezése más felügyelt alkalmazásokban**|Nem|Nem|Nem|iOS 7 és újabb verziók|Nem|
|**Videokonferenciák engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**Felnőtt tartalom engedélyezése a médiatárban**|Nem|Nem|Nem|Igen|Nem|
|**Alkalmazástelepítés engedélyezése**|Nem|Nem|Nem|iOS 6 és újabb verziók|Nem|

## <a name="application-settings---gaming"></a>Alkalmazásbeállítások – játékok

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Game Centerbeli ismerősök felvételének engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**Több résztvevős játék engedélyezése**|Nem|Nem|Nem|Igen|Nem|

## <a name="device-capabilities-settings---hardware"></a>Eszközképességek beállításai – hardver

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Kamera engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Igen|Igen|
|**Cserélhető tároló engedélyezése**|Nem|Nem|Igen|Nem|Igen (csak Samsung KNOX Standard)|
|**Wi-Fi engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Igen (csak Samsung KNOX Standard)|
|**Wi-Fi alapú internetmegosztás használatának engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Igen (csak Samsung KNOX Standard)|
|**Ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozás engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Nem|
|**Wi-Fi elérési pontok jelentésének engedélyezése**<br /><br />Ez a beállítás információt küld a Wi-Fi-kapcsolatokról a közeli kapcsolatok felderítésének elősegítése érdekében.|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Nem|
|**Földrajzi hely meghatározásának engedélyezése**<br /><br />Ez a beállítás engedélyezi az eszköz számára a helyadatok használatát.|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Igen (csak Samsung KNOX Standard)|
|**NFC használatának engedélyezése**<br /><br />Ez a beállítás engedélyezi a kis hatótávolságú kommunikációt használó műveleteket.|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Igen (csak Samsung KNOX Standard)|
|**Bluetooth engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Igen (csak Samsung KNOX Standard)|
|**Kikapcsolás engedélyezése**<br>Ha ez a beállítás le van tiltva, a **Megengedett sikertelen bejelentkezések száma az eszközön tárolt adatok törléséig** beállítás Samsung KNOX Standard-eszközökön nem működik.|Nem|Nem|Nem|Nem|Igen (csak Samsung KNOX Standard)|

## <a name="device-capabilities-settings---cellular"></a>Eszközképességek beállításai – mobilhálózat

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Hangroaming engedélyezése**|Nem|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Adatroaming engedélyezése**|Igen|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Roamingolás közbeni automatikus szinkronizálás engedélyezése**|Nem|Nem|Nem|Igen|Nem|
|**SMS- és MMS-funkciók engedélyezése**|Nem|Nem|Nem|Nem|Igen (csak Samsung KNOX Standard)|

## <a name="device-capabilities-settings---features"></a>Eszközképességek beállításai – szolgáltatások

|Beállítás neve|Windows 8.1 és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|iOS|Android és Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Beszédfelismerési asszisztens engedélyezése**|Nem|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Beszédfelismerés használatának engedélyezése az eszköz zárolt állapotában**|Nem|Nem|Nem|Igen|Nem|
|**Hangtárcsázás engedélyezése**|Nem|Nem|Nem|Igen|Igen (csak Samsung KNOX Standard)|
|**Másolás és beillesztés engedélyezése**|Nem|Nem|Csak Windows Phone 8.1 esetén|Nem|Igen (csak Samsung KNOX Standard)|
|**Vágólap alkalmazások közötti megosztásának engedélyezése**|Nem|Nem|Nem|Nem|Igen (csak Samsung KNOX Standard)|
|**YouTube engedélyezése**|Nem|Nem|Nem|Nem|Igen (csak Samsung KNOX Standard)|

### <a name="see-also"></a>Lásd még:
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
