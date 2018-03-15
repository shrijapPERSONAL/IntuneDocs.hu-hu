---
title: "Eszközkorlátozásokra vonatkozó beállítások a Microsoft Intune-ban Android for Work rendszer esetén"
titlesuffix: 
description: "A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre az Android for Work rendszerű eszközökön."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d4d8089d7ae57c4bf95038e5f9dc88f4949f069e
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="microsoft-intune-android-for-work-device-restriction-settings"></a>Az Android for Work-eszközök korlátozásaira vonatkozó beállítások a Microsoft Intune-ban

A cikk bemutatja a Microsoft Intune összes olyan eszközkorlátozásokra vonatkozó beállítását, melyek konfigurálhatók Android for Work rendszerű eszközökhöz.

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Munkahelyi profil beállításai

### <a name="general-settings"></a>Általános beállítások

-   **Munkahelyi és a személyes profilok közötti másolás** – A munkahelyi és személyes alkalmazások közötti másolást és beillesztést szabályozza. A letiltáshoz válassza a **Letiltás** lehetőséget. A **Nincs beállítva** lehetőség választásával nem alkalmazza a letiltást.
- **Munkahelyi és személyes profilok közötti adatmegosztás** – ezzel a beállítással szabályozhatja, hogy a munkahelyi profilban szereplő alkalmazások megoszthatnak-e adatokat a személyes profilban szereplőkkel. A beállítás az alkalmazáson belüli megosztási műveleteket szabályozza (például a **Megosztás...** lehetőséget a Chrome böngészőalkalmazásban), és nem vonatkozik a vágólap másolási/beillesztési funkciójára. Az [alkalmazásvédelmi szabályzat beállításaitól](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) eltérően az eszközkorlátozási beállítások felügyelete az Intune-portálon történik, és az Android for Work típusú munkahelyiprofil-partíció szolgál a felügyelt alkalmazások elkülönítésére. A következő lehetőségek közül választhat:
    - **Alapértelmezett megosztási korlátozások** – ez a beállítás az eszköz alapértelmezett megosztási működésmódja, amely a futtatott Android-verziótól függően eltérő. Alapértelmezés szerint a személyes profilból lehet a munkahelyi profilba adatokat megosztani, a munkahelyiből a személyesbe viszont nem. A beállítás célja a munkahelyi profilból a személyesbe irányuló adatmegosztás megelőzése. A Google a 6.0-snál újabb verziójú eszközökön nem nyújt lehetőséget a személyesből a munkahelyi profilba irányuló adatmegosztás blokkolására.   
    - **A munkahelyi profilban lévő alkalmazások kezelhetik a személyes profilból érkező megosztási kérelmeket** – ezzel a lehetőséggel engedélyezheti a személyesből a munkahelyi profilba irányuló adatmegosztásra szolgáló beépített Android-funkciót. Engedélyezéskor a személyes profil alkalmazásaiból származó megosztási kérések kezdeményezhetnek adatmegosztást a munkahelyi profil alkalmazásaival. A 6.0-snál korábbi verziójú androidos eszközökön ez az alapértelmezett beállítás.
    - **Határokon keresztüli megosztás engedélyezése** – lehetővé teszi a munkahelyi profil határán kívüli megosztást mindkét irányban. Ilyenkor a munkahelyi profilban szereplő alkalmazások megoszthatnak adatokat a személyes profi jelöletlen alkalmazásaival. A beállítást csak körültekintően szabad használni, mert lehetővé teszi a munkahelyi profil alkalmazásainak az adatmegosztást az eszköz nem felügyelt részével.

-   **Munkahelyi profil értesítései az eszköz zárolt állapotában** – ez a beállítás szabja meg, hogy a munkahelyi profilban szereplő alkalmazások megjeleníthetnek-e adatokat az értesítésekben, ha az eszköz zárolva van.
-   **Alapértelmezett alkalmazásengedélyek** – itt adhatja meg a munkahelyi profilban található összes alkalmazásra vonatkozó alapértelmezett engedélyszabályzatot. Az Android 6-os verziójától kezdve a rendszer alkalmazásindításkor felszólítja a felhasználót az alkalmazás által megkövetelt, konkrét engedélyek megadására. Ezzel a szabályzatbeállítással döntheti el, hogy a felhasználók megadhatják-e a munkahelyi profilban szereplő összes alkalmazás engedélyeit. Hozzárendelhet például egy olyan alkalmazást a munkahelyi profilhoz, amely helyadatokhoz kér hozzáférést. Általában az alkalmazás kéri a felhasználót a helyadatokhoz való hozzáférés megadására vagy elutasítására. Ezzel a szabályzattal kérdés nélkül automatikusan engedélyezhet vagy letilthat minden hozzáférést, vagy átadhatja az eseti döntés jogát a felhasználónak. A következő lehetőségek közül választhat:
    -   **Eszköz alapértelmezése**
    -   **Rákérdezés**
    -   **Automatikus engedélyezés**
    -   **Automatikus elutasítás**

    Az engedélyezési állapotot részletesebben is lehet definiálni konkrét alkalmazások esetén, ha az adott alkalmazáshoz alkalmazáskonfigurációs szabályzatot határoz meg (**Mobilalkalmazások** > **Alkalmazáskonfigurációs szabályzatok**).

- **Fiókok hozzáadása és eltávolítása**

   Letiltja a munkahelyi profilban található fiókok manuális hozzáadását vagy eltávolítását a végfelhasználók számára.

   Ha például a Gmail alkalmazást Android for Work-profilban telepíti, megakadályozhatja, hogy a végfelhasználók fiókokat adjanak hozzá vagy távolítsanak el ebben a munkaprofilban.

### <a name="work-profile-password"></a>Munkahelyi profilhoz tartozó jelszó
- **Munkahelyi profilhoz tartozó jelszó megkövetelése** – (Android 7.0 és újabb verziók esetén, amelyekben engedélyezve van a munkahelyi profil) olyan jelszószabályzatot határozhat meg, amely csak a munkahelyi profil alkalmazásaira vonatkozik. Alapértelmezés szerint a végfelhasználónak lehetősége van két külön-külön definiált PIN-kód használatára, vagy dönthet úgy, hogy a két PIN-kód összevonásával csak az erősebbet használja.
- **Jelszó minimális hossza** – itt adhatja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát (**4**-**16**)
- **A munkahelyi profil zárolása legfeljebb ennyi perc inaktivitás után** – itt adhatja meg, hogy mennyi idő után zárolódjon a munkahelyi profil. A felhasználónak ezután meg kell adnia a hitelesítő adatait a hozzáférés visszanyeréséhez.
- **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – itt adhatja meg, hogy hányszor lehet helytelen jelszót megadni, mielőtt a rendszer törölné az eszközről a munkahelyi profil összes adatát.
- **Jelszó érvényessége (nap)** – itt adhatja meg, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát (**1**-**255**).
- **Kötelező jelszótípus** – itt adhatja meg az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
    - **Eszköz alapértelmezése**
    - **Alacsony biztonságú biometrikus**
    - **Kötelező**
    - **Legalább számok**
    - **Komplex numerikus** – (nem lehet ismétlődő vagy egymást követő számokat megadni, például az „1111”-et vagy az „1234”-et)
    - **Legalább betűk**
    - **Legalább alfanumerikus karakterek**
    - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása** – itt adhatja meg, hogy hány új jelszót kell beállítani, mielőtt egy korábbit újból használhatna (**1**-**24**).
- **Ujjlenyomattal történő zárolásfeloldás** – letilthatja, hogy a végfelhasználók az eszközt annak ujjlenyomat-olvasójával oldják fel.
- **Smart Lock és egyéb megbízhatósági ügynökök** – kompatibilis eszközökön ezzel vezérelheti az intelligens zárolási funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi a munkahelyi profil jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van (például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van). Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

## <a name="device-password"></a>Eszköz jelszava

- **Jelszó minimális hossza** – itt adhatja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát (**4**-**14**).
- **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – itt adhatja meg, hogy mennyi idő után zárolódjanak a tétlen eszközök.
- **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat** – itt adhatja meg, hogy hányszor lehet helytelen jelszót megadni, mielőtt a rendszer törölné az eszközről az adatokat.
- **Jelszó érvényessége (nap)** – itt adhatja meg, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát (**1**-**255**).
- **Kötelező jelszótípus** – itt adhatja meg az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
    - **Eszköz alapértelmezése**
    - **Alacsony biztonságú biometrikus**
    - **Kötelező**
    - **Legalább számok**
    - **Komplex numerikus** – (nem lehet ismétlődő vagy egymást követő számokat megadni, például az „1111”-et vagy az „1234”-et)
    - **Legalább betűk**
    - **Legalább alfanumerikus karakterek**
    - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása** – itt adhatja meg, hogy hány új jelszót kell beállítani, mielőtt egy korábbit újból használhatna (**1**-**24**).
- **Ujjlenyomattal történő zárolásfeloldás** – letilthatja, hogy a végfelhasználók az eszközt annak ujjlenyomat-olvasójával oldják fel.
- **Smart Lock és egyéb megbízhatósági ügynökök** – kompatibilis eszközökön ezzel vezérelheti az intelligens zárolási funkciót. Ez a „bizalmi ügynök” néven is ismert telefonos funkció lehetővé teszi az eszköz zárolási képernyője jelszavának letiltását vagy megkerülését, ha az eszköz megbízható helyen van (például ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van). Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

## <a name="system-security"></a>Rendszerbiztonság

 - **Alkalmazások fenyegetettségvizsgálata** ‒ az **Alkalmazások ellenőrzése** (Verify Apps) beállítást kötelező bekapcsolni a munkahelyi és személyes profiloknál.

   > [!Note]  
   > Ez a beállítás csak Android O vagy újabb rendszerű eszközök esetén érvényesül. 

## <a name="next-steps"></a>További lépések

Olvassa el az [Eszközkorlátozási profilok konfigurálása](device-restrictions-configure.md) szakaszt a profil mentéséhez, majd hozzárendeléséhez a felhasználók és eszközök számára.
