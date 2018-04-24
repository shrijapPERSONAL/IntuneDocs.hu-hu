---
title: Windows Phone 8.1-es szabályzatbeállítások
description: Az Intune a Windows Phone 8.1-eszközökön beállítható, beépített általános beállítások széles választékát kínálja. Ezenkívül megadhatja az OMA-URI-értékeket is olyan egyéni beállítások létrehozásához, amelyek nem érhetők el az Intune-ban.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b44215e301bb712cc4d27722515d2e51b124101b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a>Windows Phone 8.1-es házirend-beállítások a Microsoft Intune-ban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Az Intune a Windows Phone 8.1-eszközökön beállítható, beépített általános beállítások széles választékát kínálja. Ezek mellett megadhat Open Mobile Alliance Uniform Resource Identifier (OMA-URI) értékeket is olyan egyéni beállítások létrehozásához, amelyek nem érhetők el az Intune-ban.

## <a name="general-configuration-settings"></a>Általános konfigurációs beállítások

A Microsoft Intune **Windows Phone-eszközökhöz készült általános konfigurációs szabályzatával (Windows Phone 8.1 és újabb rendszereknél)** a következő beállításokat adhatja meg a Windows 8.1-eszközökön:

-   **Mobileszköz-biztonsági beállítások** – előre meghatározott beállítások egy listájából választva számos szolgáltatást és funkciót szabályozhat az eszközökön.

-   **Megfelelő és nem megfelelő alkalmazások** – egy listában megadhatja a vállalatban megfelelőnek vagy nem megfelelőnek ítélt alkalmazásokat. A Windows Phone-telefonok blokkolhatják vagy engedélyezhetik ezeknek az alkalmazásoknak a telepítését.

### <a name="applicability-settings"></a>Alkalmazhatósági beállítások

|Beállítás neve|Részletek|
|----------------|----------------------------------|
|**Az összes konfiguráció alkalmazása a Windows 10-re**|Ezzel a beállítással engedélyezheti, hogy a szabályzatban szereplő beállítások a rendszer Windows Phone 8.1-eszközökön felül a Windows 10 Mobile-eszközökre is alkalmazza.|

### <a name="password-settings"></a>Jelszóbeállítások

|                                           Beállítás neve                                            |                                                                                                                                    Részletek                                                                                                                                     |
|---------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   <strong>Jelszó szükséges a mobileszközök feloldásához</strong>                    |                                                                                                     Ez a beállítás azt határozza meg, hogy a felhasználóknak kell-e jelszót megadniuk az eszközükhöz való hozzáféréshez.                                                                                                     |
|                              <strong>Kötelező jelszótípus</strong>                              |                                                                                          Meghatározza a megkövetelt jelszótípust, például hogy a jelszó csak számokat, vagy számokat és betűket is tartalmazhat.                                                                                           |
|            <strong>Megkövetelt jelszótípus – a karakterkészletek minimális száma</strong>             | Azt határozza meg, hány különböző karakterkészletnek kell szerepelnie a jelszóban. A következő négy karakterkészlet létezik: kisbetűk, nagybetűk, számok és szimbólumok. iOS-eszközök esetén azonban ez azt határozza meg, hány szimbólumnak kell szerepelnie a jelszóban. |
|                             <strong>Jelszó minimális hossza</strong>                              |                                                                                                 A jelszóban használandó karakterek minimális számát határozza meg.                                                                                                  |
|                              <strong>Egyszerű jelszavak engedélyezése</strong>                              |                                                                                                     Engedélyezi az egyszerű jelszavak (például a „0000”vagy az”1234”) használatát.                                                                                                     |
|     <strong>Ennyi ismétlődő sikertelen bejelentkezés után törlődnek végleg az adatok az eszközről</strong>      |                                                                                         Meghatározza, hogy a felhasználó hányszor adhat meg helytelen jelszót, mielőtt a rendszer törölné az eszközt.                                                                                         |
|                <strong>Képernyő kikapcsolása ennyi perc inaktivitás után</strong>                 |                                                                                       Meghatározza, hogy az eszköznek mennyi ideig kell tétlennek lennie a képernyő automatikus zárolása előtt.                                                                                        |
|                            <strong>Jelszó lejárata (nap)</strong>                            |                                                                                                    Ennyi nap elteltével kell megváltoztatni az eszköz jelszavát.                                                                                                    |
|                            <strong>Jelszóelőzmények megjegyzése</strong>                             |                                                                                     Meghatározza, hogy a korábban használt jelszavak rendszer megjegyezze annak megakadályozásához, hogy a felhasználó újra használni.                                                                                      |
| <strong>Korábbi jelszavak megjegyzése</strong> – <strong>Korábbi jelszavak újbóli használatának tiltása</strong> |                                                                                                          Meghatározza, hogy a rendszer hány korábban használt jelszót jegyezzen meg.                                                                                                          |

### <a name="encryption-settings"></a>Titkosítási beállítások

|Beállítás neve|Részletek|
|----------------|------|
|**Mobileszköz titkosításának kötelezővé tétele**|Kötelezővé teszi az adatok titkosítását a támogatott mobileszközökön.|

### <a name="system-settings"></a>Rendszerbeállítások

|Beállítás neve|Részletek|
|----------------|-----|
|**Képernyőfelvétel engedélyezése**|A képernyőtartalom képfájlban történő rögzítésének engedélyezése a felhasználó számára.|
|**Diagnosztikai adatok küldésének engedélyezése**|Engedélyezése esetén az eszköz diagnosztikai adatokat küld a Microsoftnak.|

### <a name="cloud-settings--accounts-and-synchronization"></a>Felhőbeállítások – fiókok és szinkronizálás

|Beállítás neve|Részletek|
|----------------|------|
|**Microsoft-fiók használatának engedélyezése**|Engedélyezi Microsoft-fiók társítását az eszközzel.|

### <a name="email-settings"></a>E-mail beállítások

|Beállítás neve|Részletek|
|----------------|-----|
|**Egyéni e-mail fiókok engedélyezése**|Nem Microsoft e-mail fiókokhoz való kapcsolódás engedélyezése az eszköz számára.|

### <a name="application-settings---browser"></a>Alkalmazásbeállítások – böngésző

|Beállítás neve|Részletek|
|----------------|-----|
|**Webböngésző engedélyezése**|Engedélyezi vagy letiltja az eszköz beépített webböngészőjét.|

### <a name="application-settings---apps"></a>Alkalmazásbeállítások – alkalmazások

|Beállítás neve|Részletek|
|----------------|-----|
|**Alkalmazás-áruház engedélyezése**|Lehetővé teszi a felhasználók számára az alkalmazás-áruház elérését az eszközről.|

### <a name="device-capabilities-settings---hardware"></a>Eszközképességek beállításai – hardver

|Beállítás neve|Részletek|
|----------------|-----|
|**Kamera engedélyezése**|Engedélyezi vagy letiltja az eszköz kamerájának használatát.|
|**Cserélhető tároló engedélyezése**|Cserélhető tárolók (például SD-kártya) használatának engedélyezése az eszközön.|
|**Wi-Fi engedélyezése**|Az eszköz Wi-Fi funkciójának engedélyezése vagy letiltása.|
|**Wi-Fi alapú internetmegosztás használatának engedélyezése**|Engedélyezi az eszköz Wi-Fi-alapú internetmegosztási funkciójának használatát.|
|**Ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozás engedélyezése**|Engedélyezi az eszközön az ingyenes Wi-Fi elérési pontokhoz történő automatikus csatlakozást és a vonatkozó használati feltételek automatikus elfogadását.|
|**Wi-Fi elérési pontok jelentésének engedélyezése**|Információt küld a Wi-Fi kapcsolatokról a közeli kapcsolatok felderítésének elősegítése érdekében.|
|**Földrajzi hely meghatározásának engedélyezése**|Engedélyezi az eszköz számára a helyadatok használatát.|
|**NFC használatának engedélyezése**|Engedélyezi a kis hatótávolságú kommunikációt használó műveleteket.|
|**Bluetooth engedélyezése**|Az eszköz Bluetooth funkciójának engedélyezése vagy letiltása.|

### <a name="device-capabilities-settings---features"></a>Eszközképességek beállításai – szolgáltatások

|Beállítás neve|Részletek|
|----------------|----|
|**Másolás és beillesztés engedélyezése**|Engedélyezi az eszköznek a másolási és a beillesztési funkció használatát.|

### <a name="settings-for-allowed-and-blocked-apps"></a>Az engedélyezett és letiltott alkalmazások beállításai
Az **Engedélyezett és letiltott alkalmazások** listában adja meg az engedélyezni vagy letiltani kívánt alkalmazásokat a következő információk alapján:

> [!NOTE]
> Egyetlen szabályzatban csak egy, vagy engedélyezett, vagy letiltott alkalmazásokat tartalmazó lista szerepelhet. Mindkét típusú lista nem adható meg ugyanabban a házirendben.

|                          Beállítás neve                          |                                                                                                      Részletek                                                                                                      |
|----------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Nem engedélyezi, hogy az eszközök megnyissák a listázott alkalmazásokat</strong>   |                                                        Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyek telepítése és futtatása nem engedélyezett a felhasználóknak.                                                         |
| <strong>Engedélyezi, hogy az eszközök kizárólag a listázott alkalmazásokat telepítsék</strong> |                                 Azokat az alkalmazásokat tartalmazza, amelyeket a felhasználók telepíthetnek. A felhasználók ezeken kívül más alkalmazásokat nem telepíthetnek. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.                                 |
|                      <strong>Hozzáadás</strong>                      | Hozzáadhat egy alkalmazást a kijelölt listához. Meg kell adnia egy szabadon választott nevet, valamint tetszés szerint megadhatja az alkalmazás kiadóját, valamint alkalmazás-áruházbeli URL-címét. További segítségért olvassa el az Alkalmazás-áruházak URL-címének megadása című részt a jelen témakörben. |
|                  <strong>Alkalmazások importálása</strong>                  |                              Importálja az Ön által vesszővel tagolt fájlban megadott alkalmazásokat. Használja a fájlban megadott formátumot, alkalmazásnevet, kiadót és URL-címet.                               |
|                     <strong>Szerkesztés</strong>                      |                                                                          Segítségével szerkesztheti a kijelölt alkalmazás nevét, kiadóját és URL-címét.                                                                          |
|                    <strong>Törlés</strong>                     |                                                                                      Törölheti a kijelölt alkalmazást a listából.                                                                                      |

> [!IMPORTANT]
> Ha megadja a kompatibilis alkalmazások listáját a Windows Phone 8.1 rendszerű eszközökhöz, fel kell vennie a Vállalati portál alkalmazást, mert ellenkező esetben az le lesz tiltva.


### <a name="reference-information-for-allowed-and-blocked-apps"></a>Referenciainformációk az engedélyezett és letiltott alkalmazásokhoz

#### <a name="how-to-specify-urls-to-app-stores"></a>Alkalmazás-áruházak URL-címének megadása
Ha meg szeretné adni egy alkalmazás URL-címét az engedélyezett vagy letiltott alkalmazások listájában, használja a következő formátumot:

A [Windows Phone Alkalmazások+játékok](http://www.windowsphone.com/store/overview) lapon keressen rá a használni kívánt alkalmazásra.

Nyissa meg az alkalmazás lapját, és másolja az URL-címet a vágólapra. Ezt a címet az engedélyezett és a tiltott alkalmazások listájában egyaránt használhatja URL-címként.

**Például:** Keressen rá az áruházban a Skype alkalmazásra. Az Ön által használt URL-cím a következő lesz: **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## <a name="custom-policy-settings"></a>Egyéni szabályzatbeállítások
A Microsoft Intune **Windows Phone-os egyéni konfigurációs szabályzatával** OMA-URI-beállításokat léptethet érvénybe, amelyekkel vezérelhetők a **Windows Phone 8.1-eszközökön** elérhető szolgáltatások. Ezek szabványos beállítások, amelyeket számos mobileszköz-gyártó alkalmaz az eszközök szolgáltatásainak vezérlésére.

Ezzel a funkcióval olyan Windows Phone-beállításokat léptethet érvénybe, amelyek nem konfigurálhatók az Intune általános konfigurációs házirendjével. Az ezen házirendekkel konfigurálható beállításokkal kapcsolatos további információkért lásd: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

A Windows Phone-telefonokra érvényes OMA-URI beállítások létrehozásához lásd a [Windows Phone 8.1 MDM-protokoll dokumentációját](http://technet.microsoft.com/library/dn499787.aspx).

### <a name="general-settings"></a>Általános beállítások

|Beállítás neve|Részletek|
|----------------|--------------------|
|**Név**|Adjon meg egy egyedi nevet a házirend számára, hogy azonosítható legyen az Intune konzolján.|
|**Leírás**|Adjon meg egy olyan leírást, amely áttekintést nyújt a szabályzatról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek megkeresésében.|

### <a name="oma-uri-settings"></a>OMA-URI-beállítások

Az **OMA-URI beállítások** szakaszban kattintson a **Hozzáadás** elemre egy beállítás hozzáadásához. Szerkesztheti és törölheti is a meglévő beállításokat.

Az **OMA-URI beállítás hozzáadása vagy szerkesztése** párbeszédpanelen adja meg a következő információkat:

|Beállítás neve|Részletek|
    |--------|--------------------|
    |**A beállítás neve**|Adjon meg egy egyedi nevet az OMA-URI beállítás számára, amellyel az egyszerűen azonosítható a beállítások listájában.|
    |**A beállítás leírása**|Adjon meg egy olyan leírást, amely áttekintést nyújt az adott beállításról, valamint más olyan releváns információkat tartalmaz, amelyek segítenek a megkeresésében.|
    |**Adattípus**|Válassza ki az adattípust az OMA-URI-beállítás megadásához. A következő lehetőségek közül választhat:<br /><br />-   **Karakterlánc**<br />-   **Karakterlánc (XML)**<br />-   **Dátum és időpont**<br />-   **Egész**<br />-   **Lebegőpontos szám**<br />-   **Logikai**|
    |**OMA-URI (megkülönbözteti a kis- és nagybetűket)**|Adja meg az OMA-URI azonosítót, amelyhez beállítást kíván megadni.|
    |**Érték**|Adja meg a korábban megadott OMA-URI-azonosítóhoz társítandó értéket.|

### <a name="see-also"></a>Lásd még:
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
