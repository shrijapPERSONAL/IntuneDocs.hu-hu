---
title: Eszközkorlátozások az Android for Work rendszerhez a Microsoft Intune-ban – Azure | Microsoft Docs
description: Az Android for Work rendszert futtató eszközökön korlátozhatja az eszköz bizonyos beállításait, többek között a másolást és beillesztést, az értesítések megjelenítését, az alkalmazásengedélyeket, az adatmegosztást, a jelszóhosszt, a sikertelen bejelentkezéseket, a zárolás feloldását ujjlenyomattal, a jelszavak újbóli használatát és a munkahelyi kapcsolatok bluetooth-on keresztüli megosztásának engedélyezését.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11ce7fa7fa4d48d9cc292b7b6565b6b4f2be2dc4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="work-device-restriction-settings-in-intune"></a>A Work eszközkorlátozásainak beállításai az Intune-ban

A cikk felsorolja a Microsoft Intune összes olyan eszközkorlátozásokra vonatkozó beállítását, melyek konfigurálhatók Android for Work rendszerű eszközökhöz.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Munkahelyi profil beállításai

### <a name="general-settings"></a>Általános beállítások

- **Munkahelyi és személyes profilok közötti másolás**: A munkahelyi és személyes alkalmazások közötti másolást és beillesztést szabályozza. A letiltáshoz válassza a **Letiltás** lehetőséget. A **Nincs beállítva** lehetőség választásával nem alkalmazza a letiltást.
- **Munkahelyi és személyes profilok közötti adatmegosztás**: Ezzel a beállítással szabályozhatja, hogy a munkahelyi profilban szereplő alkalmazások megoszthatnak-e adatokat a személyes profilban szereplőkkel. A beállítás az alkalmazáson belüli megosztási műveleteket szabályozza (például a **Megosztás...** lehetőséget a Chrome böngészőalkalmazásban), és nem vonatkozik a vágólap másolási/beillesztési funkciójára. Az [alkalmazásvédelmi szabályzat beállításaitól](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) eltérően az eszközkorlátozási beállítások felügyelete az Intune-portálon történik, és az Android for Work típusú munkahelyiprofil-partíció szolgál a felügyelt alkalmazások elkülönítésére. A következő lehetőségek közül választhat:
  - **Alapértelmezett megosztási korlátozások**: Ez az eszköz alapértelmezett megosztási működésmódja, amely az Android-verziótól függően eltérő. Alapértelmezés szerint a személyes profilból lehet a munkahelyi profilba adatokat megosztani, a munkahelyiből a személyesbe viszont nem. A beállítás célja a munkahelyi profilból a személyesbe irányuló adatmegosztás megelőzése. A Google a 6.0-snál újabb verziójú eszközökön nem nyújt lehetőséget a személyesből a munkahelyi profilba irányuló adatmegosztás blokkolására.
  - **A munkahelyi profilban lévő alkalmazások kezelhetik a személyes profilból érkező megosztási kérelmeket**: Engedélyezi a személyesből a munkahelyi profilba irányuló adatmegosztásra szolgáló beépített Android-funkciót. Engedélyezéskor a személyes profil alkalmazásaiból származó megosztási kérések kezdeményezhetnek adatmegosztást a munkahelyi profil alkalmazásaival. A 6.0-snál korábbi verziójú androidos eszközökön ez az alapértelmezett beállítás.
  - **Határokon keresztüli megosztás engedélyezése**: Lehetővé teszi a munkahelyi profil határán kívüli megosztást mindkét irányban. Ilyenkor a munkahelyi profilban szereplő alkalmazások megoszthatnak adatokat a személyes profi jelöletlen alkalmazásaival. A beállítást csak körültekintően szabad használni, mert lehetővé teszi a munkahelyi profil alkalmazásainak az adatmegosztást az eszköz nem felügyelt részén található eszközökkel.

- **Munkahelyi profil értesítései az eszköz zárolt állapotában**: Ez a beállítás szabja meg, hogy a munkahelyi profilban szereplő alkalmazások megjeleníthetnek-e adatokat az értesítésekben, ha az eszköz zárolva van.
- **Alapértelmezett alkalmazásengedélyek**: Itt adhatja meg a munkahelyi profilban található összes alkalmazásra vonatkozó alapértelmezett engedélyszabályzatot. Az Android 6-os verziójától kezdve a rendszer alkalmazásindításkor felszólítja a felhasználót az alkalmazás által megkövetelt, konkrét engedélyek megadására. Ezzel a szabályzatbeállítással döntheti el, hogy a felhasználók megadhatják-e a munkahelyi profilban szereplő összes alkalmazás engedélyeit. Hozzárendelhet például egy olyan alkalmazást a munkahelyi profilhoz, amely helyadatokhoz kér hozzáférést. Általában az alkalmazás kéri a felhasználót a helyadatokhoz való hozzáférés megadására vagy elutasítására. Ezzel a szabályzattal kérdés nélkül automatikusan engedélyezhet vagy letilthat minden hozzáférést, vagy átadhatja az eseti döntés jogát a felhasználónak. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Rákérdezés**
  - **Automatikus engedélyezés**
  - **Automatikus elutasítás**

    Az engedélyezési állapotot részletesebben is lehet definiálni konkrét alkalmazások esetén, ha az adott alkalmazáshoz alkalmazáskonfigurációs szabályzatot használ (**Mobilalkalmazások** > **Alkalmazáskonfigurációs szabályzatok**).

- **Fiókok hozzáadása és eltávolítása**

   Letiltja a munkahelyi profilban található fiókok manuális hozzáadását vagy eltávolítását a végfelhasználók számára.

   Ha például a Gmail alkalmazást Android for Work-profilban telepíti, megakadályozhatja, hogy a végfelhasználók fiókokat adjanak hozzá vagy távolítsanak el ebben a munkaprofilban.

- **Névjegyek megosztása Bluetooth-kapcsolattal**: Engedélyezi egy másik Bluetooth-eszköz (például egy autó) a munkahelyi névjegyekhez való hozzáférését. Alapértelmezés szerint ez a beállítás nincs konfigurálva, a munkahelyi névjegyek pedig nem jelennek meg. A megosztás engedélyezéséhez és a munkahelyi profil névjegyeinek megjelenítéséhez válassza az **Engedélyezés** lehetőséget. Ez a beállítás az Android munkahelyi profilos, Android v6.0 és újabb operációs rendszerekkel rendelkező eszközökre vonatkozik.

### <a name="work-profile-password"></a>Munkahelyi profilhoz tartozó jelszó

- **Munkahelyi profilhoz tartozó jelszó megkövetelése**: Az engedélyezett munkahelyi profillal rendelkező Android 7.0-s és újabb verziójú eszközökre vonatkozik. Meghatározhat csak a munkahelyi profilhoz tartozó alkalmazásokra vonatkozó PIN-kód-szabályzatot. Alapértelmezés szerint a végfelhasználónak lehetősége van két külön-külön definiált PIN-kód használatára, vagy a felhasználók dönthetnek úgy, hogy a két meghatározott PIN-kód összevonásával csak az erősebbet használják.
- **Jelszó minimális hossza**: Itt adhatja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát (**4**-**16**)
- **A munkahelyi profil zárolása legfeljebb ennyi perc inaktivitás után**: Itt adhatja meg, hogy mennyi idő után zárolódjon a munkahelyi profil. A felhasználónak ezután meg kell adnia a hitelesítő adatait a hozzáférés visszanyeréséhez.
- **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat**: Itt adhatja meg, hogy hányszor lehet helytelen jelszót megadni, mielőtt a rendszer törölné az eszközről a munkahelyi profil összes adatát.
- **Jelszó érvényessége (nap)**: Itt adhatja meg, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát (**1**-**255**).
- **Kötelező jelszótípus**: Itt adhatja meg az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Kötelező**
  - **Legalább számok**
  - **Komplex numerikus**: Nem lehet ismétlődő vagy egymást követő számokat megadni, például az „1111”-et vagy az „1234”-et
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása**: Itt adhatja meg, hogy hány új jelszót kell beállítani, mielőtt egy korábbit újból használhatna (**1**-**24**).
- **Ujjlenyomattal történő zárolásfeloldás**: Letilthatja, hogy a végfelhasználók az eszközt annak ujjlenyomat-olvasójával oldják fel
- **Smart Lock és egyéb megbízhatósági ügynökök**: Kompatibilis eszközökön ezzel vezérelheti az intelligens zárolási funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi a munkahelyi profil jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van. Így például abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

## <a name="device-password"></a>Eszköz jelszava

- **Jelszó minimális hossza**: Itt adhatja meg a felhasználók jelszavában szereplő karakterek minimális számát (**4**-**14**)
- **Képernyőzárolás legfeljebb ennyi perc inaktivitás után**: Itt adhatja meg, hogy mennyi idő után zárolódjanak a tétlen eszközök
- **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat**: Itt adhatja meg, hogy hányszor lehet helytelen jelszót megadni, mielőtt a rendszer törölné az eszközről az adatokat
- **Jelszó érvényessége (nap)**: Itt adhatja meg, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát (**1**-**255**)
- **Kötelező jelszótípus**: Itt adhatja meg az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Kötelező**
  - **Legalább számok**
  - **Komplex numerikus**: Nem lehet ismétlődő vagy egymást követő számokat megadni, például az „1111”-et vagy az „1234”-et
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása**: Itt adhatja meg, hogy hány új jelszót kell beállítani, mielőtt egy korábbit újból használhatna (**1**-**24**).
- **Ujjlenyomattal történő zárolásfeloldás**: Letilthatja, hogy a végfelhasználók az eszközt annak ujjlenyomat-olvasójával oldják fel
- **Smart Lock és egyéb megbízhatósági ügynökök**: Kompatibilis eszközökön ezzel vezérelheti az intelligens zárolási funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van. Így például abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

## <a name="system-security"></a>Rendszerbiztonság

- **Alkalmazások fenyegetettségvizsgálata**: Az **Alkalmazások ellenőrzése** (Verify Apps) beállítást kötelező bekapcsolni a munkahelyi és személyes profiloknál.

   > [!Note]
   > Ez a beállítás csak Android O vagy újabb rendszerű eszközök esetén érvényesül.

## <a name="next-step"></a>Következő lépés

Olvassa el az [Eszközkorlátozási profilok konfigurálása](device-restrictions-configure.md) szakaszt a profil mentéséhez, majd hozzárendeléséhez a felhasználókhoz és eszközökhöz.