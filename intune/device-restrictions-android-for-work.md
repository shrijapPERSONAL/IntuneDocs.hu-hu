---
title: Eszközkorlátozások az androidos munkahelyi profilokhoz a Microsoft Intune-ban – Azure | Microsoft Docs
description: A Vállalati Androidos profilt használó eszközökön korlátozhatja az eszköz bizonyos beállításait, többek között a másolást és beillesztést, az értesítések megjelenítését, az alkalmazásengedélyeket, az adatmegosztást, a jelszóhosszt, a sikertelen bejelentkezéseket, a zárolás feloldását ujjlenyomattal, a jelszavak újbóli használatát és a munkahelyi kapcsolatok Bluetoothon keresztüli megosztásának engedélyezését.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5f153e738aff28cae6481c0502f0682d10b8f104
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2018
ms.locfileid: "52729092"
---
# <a name="work-device-restriction-settings-in-intune"></a>A Work eszközkorlátozásainak beállításai az Intune-ban

A cikk felsorolja a Microsoft Intune összes olyan eszközkorlátozásokra vonatkozó beállítását, melyek konfigurálhatók Vállalati Android-profilos eszközökhöz.

## <a name="device-owner-only"></a>Csak az eszköz tulajdonosa

### <a name="general-settings"></a>Általános beállítások

- **Képernyőfelvétel**: válasszon **blokk** képernyőképek megelőzése, illetve a képernyőfelvétel-készítés, az eszközön. Ezen kívül megakadályozza a tartalom megjelenítését a biztonságos videokimenettel nem rendelkező megjelenítő eszközökön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.
- **Kamera**: válasszon **blokk** kívánja tagadni a hozzáférést az eszközön a kamera. **Nem szükséges** engedélyezi a hozzáférést az eszköz kamerájának használatát.
- **Alapértelmezett engedélyezési szabályzat**: Ez a beállítás adja meg a futásidejű engedélykérésekre vonatkozó alapértelmezett engedélyezési szabályzatot. Lehetséges értékei többek között a következők:
  - **Eszköz alapértelmezése**: Az eszköz alapértelmezett beállításának használata.
  - **Rákérdezés**: A rendszer felszólítja a felhasználót az engedély jóváhagyására.
  - **Automatikus engedélyezés**: Az engedélyek automatikusan meg lesznek adva.
  - **Automatikus elutasítás**: Az engedélyek automatikusan meg lesznek tagadva.
- **Dátum-és időmódosítás**: válasszon **blokk** megakadályozza, hogy a felhasználók manuális beállítása dátuma és időpontja. **Nincs konfigurálva** lehetővé teszi a felhasználóknak az beállított dátumot és időt az eszközön.
- **Hangerő-módosítás**: A **Tiltás** lehetőség választásával megakadályozza a felhasználókat az eszköz hangerejének módosításában. **Nincs konfigurálva** lehetővé teszi, hogy a kötet beállításokat az eszközön.
- **Gyári beállítások visszaállítása**: válasszon **blokk** megakadályozza, hogy a felhasználók segítségével a gyári alaphelyzetbe az eszköz beállításaiban. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók számára ez a beállítás használatát az eszközön.
- **Csökkentett üzemmódú indítás**: A **Tiltás** lehetőség választásával megakadályozza a felhasználókat az eszköz csökkentett módban való újraindításában. **Nincs konfigurálva** lehetővé teszi a felhasználóknak indítsa újra az eszközt a csökkentett módban.
- **Állapotsor**: válasszon **blokk** , hogy megakadályozza a hozzáférést az állapotsorhoz való, beleértve az értesítéseket és a gyors beállításokat. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók az állapotsor való hozzáférést.
- **Data services központi**: válassza ki **letiltása** a mobilhálózati adatroaming elkerülése érdekében. **Nincs konfigurálva** engedélyezi az adatroaming használatát, ha az eszköz mobilhálózati.
- **Wi-Fi-beállítások módosításai**: válasszon **blokk** , az eszköz tulajdonosa által létrehozott Wi-Fi-beállítások módosításának megakadályozása. Felhasználók saját Wi-Fi-beállításokat hozhat létre. **Nincs konfigurálva** lehetővé teszi a felhasználóknak, hogy a Wi-Fi-beállításokat az eszközön.
- **Wi-Fi hozzáférési pont konfigurációja**: válasszon **blokk** , hogy a felhasználók létrehozása vagy módosítása a Wi-Fi-konfigurációkat. **Nincs konfigurálva** lehetővé teszi a felhasználóknak, hogy a Wi-Fi-beállításokat az eszközön.
- **Bluetooth-konfiguráció**: válasszon **blokk** meg, hogy a felhasználók a Bluetooth konfigurálását az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy az eszköz Bluetooth használatával.
- **Megosztása Bluetooth használatával**: válasszon **blokk** kívánja tagadni a hozzáférést a munkahelyi névjegyekhez egy másik eszköz, például egy autó rendszer, ha egy Android-eszközön a Bluetooth segítségével. **Nincs konfigurálva** lehetővé teszi, hogy az egy másik Bluetooth-eszközhöz, amely az Android-eszközre van párosítva a munkahelyi névjegyekhez való hozzáférést.
- **-Alapú internetmegosztás és hozzáférési pontokhoz**: válasszon **letiltása** hordozható pontokhoz-alapú internetmegosztás és a hozzáférés megelőzése érdekében. **Nincs konfigurálva** -alapú internetmegosztás és hordozható elérési pontokhoz való hozzáférést.
- **USB-tárolók**: válasszon **engedélyezése** az eszköz USB-tároló elérése érdekében. **Nincs konfigurálva** megakadályozza a USB-tároló.
- **USB-fájlátvitel**: válasszon **blokk** elkerülése érdekében fájlok átvitelével az USB-kapcsolaton keresztül. **Nincs konfigurálva** lehetővé teszi a fájlok átviteléhez.
- **Külső adathordozó**: válasszon **blokk** megakadályozza a használatával, és kapcsolódás bármilyen külső adathordozó az eszközön. **Nincs konfigurálva** külső adathordozó engedélyezi az eszközön.
- **Az NFC segítségével adatokat fényt**: válassza a **letiltása** , hogy a kis hatótávolságú kommunikációs (NFC) technológia használatával távolsági adatokat az alkalmazásokból. **Nincs konfigurálva** lehetővé teszi, hogy az NFC segítségével végzett eszközök között adatokat megosztani.
- **Hibakeresési funkciók**: válasszon **engedélyezése** , hogy a felhasználók hibakeresési funkciók használata az eszközön. **Nincs konfigurálva** megakadályozza, hogy a felhasználók a hibakeresési funkciók használata az eszközön.
- **Mikrofon beállítása**: válasszon **blokk** , hogy a felhasználók a mikrofon visszahangosításának és a mikrofon hangereje. **Nincs konfigurálva** lehetővé teszi a felhasználó használhatja, és állítsa be a mikrofon az eszközön.
- **Gyári visszaállítás elleni védelem e-mail-címei**: válasszon **Google-fiók e-mail-címek**. Adja meg, amely oldhatja fel az eszköz tartalma törlődik, miután eszközadminisztrátorok e-mail címét. Ügyeljen arra, hogy az e-mail-címeket egymástól pontosvesszővel, mint például `admin1@gmail.com;admin2@gmail.com`. Ha egy e-mailt nem adott meg, bárki is az eszköz feloldásához, a gyári beállítások visszaállítása után.
- **Hálózati vészkijárat**: válasszon **engedélyezése** , hogy a felhasználók a hálózat escape csíkozási funkció bekapcsolása. Ha a hálózati kapcsolat az eszköz nem végzett, majd a vészkijárat kéri ideiglenesen csatlakozzon egy hálózathoz, és frissítenie kell az szabályzat. A szabályzat alkalmazása után a rendszer elfelejti az átmeneti hálózatot, és az eszköz folytatja a rendszerindítást. Ez a funkció eszköz csatlakozik a hálózathoz, ha:
  - Nincs megfelelő hálózati a legutóbbi házirendben.
  - Az eszköz zárolási feladat üzemmódban alkalmazás indul.
  - A felhasználó nem tudja elérni az Eszközbeállítások között.

  **Nincs konfigurálva** megakadályozza, hogy a felhasználók ne tudják bekapcsolni a a hálózat escape csíkozási funkciót az eszközön.

- **Lehetővé teszi az ismeretlen forrásból történő telepítést**: válasszon **engedélyezése** így a felhasználók bekapcsolhatja a **ismeretlen források**. Ez a beállítás lehetővé teszi, hogy a telepítéséhez az ismeretlen forrásból származó alkalmazások. **Nincs konfigurálva** megakadályozza, hogy a felhasználók ne tudják bekapcsolni a **ismeretlen források**.
- **Rendszerfrissítés**: Válasszon egy lehetőséget adja meg, hogyan kezeli az eszköz a vezeték nélküli frissítések:
  - **Eszköz alapértelmezése**: Az eszköz alapértelmezett beállításának használata.
  - **Automatikus**: A rendszer automatikusan, felhasználói beavatkozás nélkül telepíti a frissítéseket. Ennek a szabályzatnak a beállításakor minden függőben lévő frissítés azonnal települ.
  - **Elhalasztva**: A frissítések 30 nappal el lesznek halasztva. A 30 nap végén Android kéri a felhasználót, hogy a frissítés telepítéséhez. Az eszközgyártók vagy a szolgáltatók megakadályozhatják (kivételként) a fontos biztonsági frissítések elhalasztását. A kivételként kezelt frissítések rendszerértesítést jelenítenek meg a felhasználó számára az eszközön. 
  - **Karbantartási időszak**: Automatikusan telepíti a frissítéseket az Ön által az Intune-ban beállított napi karbantartási időszakban. Telepítés megkísérli naponta 30 napig, és meghiúsulhat, ha nincs elegendő terület vagy akkumulátor szintjét. A 30 nap elteltével Android kéri a felhasználót, hogy telepítse. Ez az időszak szolgál a Play-alkalmazások frissítéseinek telepítésére is. Dedikált eszközök, például kioszkok, a beállítást használja, Egyalkalmazásos kioszk előtérben futó alkalmazások frissíthetők.
- **Alkalmazás automatikusan frissül**: válassza ki, ha az automatikus frissítések telepítve vannak. A választható lehetőségek:
  - **Nincs konfigurálva**
  - **Felhasználói választási lehetőség**
  - **Soha nem**
  - **Wi-Fi csak**
  - **Mindig**

### <a name="system-security-settings"></a>A rendszer biztonsági beállításai

- **Alkalmazások fenyegetettségvizsgálata**: **megkövetelése** érvényesíti a **alkalmazások ellenőrzése** beállítás engedélyezve van a munkahelyi és személyes profiloknál.

### <a name="kiosk-settings"></a>Kioszkbeállítások

Beállíthatja, hogy egy alkalmazás vagy alkalmazás számos eszközön. Ha egy eszköz kioszk módban van, csak a hozzáadott alkalmazások érhetők el.

**Teljes képernyős mód**: válassza ki, ha az eszköz elindul, egy alkalmazás vagy több alkalmazás.

- **Egyalkalmazásos kioszk**: csak a felhasználók egyetlen alkalmazást az eszközön. Amikor az eszköz elindul, csak az adott alkalmazás elindul. A felhasználók nem nyithatnak meg új alkalmazásokat, és nem módosíthatják a futó alkalmazást.

  **Lépések**
  1. Válasszon **felügyelt alkalmazás kiválasztása**, és válassza ki a felügyelt Google Play-alkalmazást a listából. 

      Ha nem rendelkezik az összes alkalmazás szerepel a listában, majd [bizonyos Android-alkalmazások hozzáadása](apps-add-android-for-work.md) az eszközön. Ügyeljen arra, hogy [rendelni az alkalmazást a teljes képernyős eszközökhöz létrehozott eszközcsoporthoz](apps-deploy.md).

  2. Válasszon **OK** > **OK** az alkalmazás hozzáadásához.

- **Többalkalmazásos kioszk**: a felhasználók egy korlátozott számú alkalmazások az eszközön. Amikor az eszköz elindul, csak a hozzáadott alkalmazások indítsa el. Bizonyos webes hivatkozások, amelyek a felhasználó meg tudja nyitni is hozzáadhat. A házirend van érvényben, amikor megjelenik a felhasználók számára az engedélyezett alkalmazások ikonjai a kezdőképernyőn.

  > [FONTOS] Többalkalmazásos kioszk-eszközök esetén a [kezdőlap képernyő felügyelt alkalmazás](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) a Google Play áruházból **kell**:
  >   - [Egy ügyfélalkalmazás hozzáadott](apps-add-android-for-work.md) az Intune-ban
  >   - [Az eszköz csoporthoz rendelt](apps-deploy.md) teljes képernyős eszközökhöz létrehozott
  > 
  > A **kezdőlap képernyő felügyelt** alkalmazás nem található a konfigurációs profil feltétlenül szükséges, de ügyfélalkalmazásként hozzá kell adni. Ha a **kezdőlap képernyő felügyelt** alkalmazás ügyfélalkalmazásként adnak, adja hozzá a configiration profil a minden más alkalmazás ikonok jelennek meg a a a **kezdőlap képernyő felügyelt** alkalmazást. 

  - Válasszon **Hozzáadás**, és válassza ki az alkalmazások a listából.

    Ha a **kezdőlap képernyő felügyelt** alkalmazás nem szerepel a listán, majd [adja hozzá a Google Play áruházból](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Ügyeljen arra, hogy [rendelni az alkalmazást](apps-deploy.md) a teljes képernyős eszközökhöz létrehozott eszközcsoport számára.

    Is hozzáadhat más [Android-alkalmazások](apps-add-android-for-work.md) és [webes alkalmazások](web-app.md) hozta létre a szervezet az eszköz számára. Ügyeljen arra, hogy [rendelni az alkalmazást a teljes képernyős eszközökhöz létrehozott eszközcsoporthoz](apps-deploy.md).

  - **Virtuális kezdőlap gombjának**: válasszon **engedélyezése** , a kezdőlap gombjának megjelenítése a teljes képernyős eszközön. Kiválasztásakor visszaadja a felhasználó az eszköz kezdőképernyőjére így a felhasználók egyszerűen válthat az alkalmazások között. Néhány Android-eszközön a felhasználók valószínűleg a pöccintsen felfelé a kezdőlap gombjának megjelenítése a képernyőn. **Tiltsa le** egy otthoni gomb nem jelenik meg, így a felhasználók alkalmazások közötti váltás kell használnia a Vissza gombra.
  - **Hagyja meg a teljes képernyős mód**: válasszon **engedélyezése** , hogy a rendszergazdák számára, hogy ideiglenesen letilthatja a teljes képernyős mód az eszköz frissítéséhez. Ez a funkció használatához a rendszergazdának a következőket teszi: 
  
    1. Folytassa mindaddig, amíg megjelenik a "Kilépés a teljes képernyős" gombra, válassza ki a Vissza gombra. 
    2. Válassza ki a gombot, és adja meg a **hagyja meg a teljes képernyős mód kód** PIN-kódot.
    3. Amikor végzett a módosításokkal, válassza ki a **kezdőlap képernyő felügyelt** alkalmazást. Ez a lépés az eszköz relocks többalkalmazásos kioszk módba. 
    
    **Tiltsa le** nem lehetővé teheti a teljes képernyős mód felfüggesztése. Ha a rendszergazda továbbra is fennáll, kattintson a Vissza gombra, és a "Kilépés a teljes képernyős" gombot választja, egy üzenet tájékoztatja, hogy egy PIN-kód megadása kötelező.
    
    - **Hagyja meg a teljes képernyős mód kód**: Adjon meg egy 4 – 6 számjegyű numerikus PIN-kód. A rendszergazda ideiglenesen letilthatja a teljes képernyős mód a PIN-kódot használja.
 
  - **Állítsa be az egyéni URL-cím hátterének**: Adja meg a teljes képernyős eszközön a háttérben futó képernyő testreszabása URL-CÍMÉT.

### <a name="device-password-settings"></a>Eszköz jelszóbeállításai

- **Keyguard**: válasszon **letiltása** megakadályozza, hogy a használt Keyguard zárolási képernyő funkció használatát az eszközön. **Nincs konfigurálva** lehetővé teszi a felhasználó Keyguard funkcióinak használatát.
- **Megkövetelt jelszótípus**: Adja meg az eszközön megkövetelt jelszótípust. A választható lehetőségek:
  - **Legalább számok**
  - **Komplex numerikus**: ismétlődő vagy egymást követő számokat, például az "1111" vagy "1234", nem engedélyezett.
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Jelszó minimális hossza**: Adja meg a minimális hosszát (4 és 16 karakter között) adjon meg egy felhasználói jelszót.
- **Bejelentkezési hibák eszköz törlése előtt**: Itt adhatja meg, mielőtt a rendszer törölné az eszközt (között 1 – 11.) a sikertelen bejelentkezéseket.

### <a name="power-settings"></a>Energiaellátási beállítások

- **A képernyő zárolásáig eltelt idő**: Adja meg, mennyi tétlenség után legyen az eszköz zárolva.
- **Bekapcsolt képernyő, amikor az eszköz áramforráshoz van csatlakoztatva**: Válassza ki, mely áramforrások csatlakoztatásakor maradjon bekapcsolva az eszköz képernyője.

### <a name="users-and-accounts-settings"></a>Felhasználói és fiókbeállítások

- **Új felhasználók hozzáadása**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat új felhasználók hozzáadásában. Minden felhasználó rendelkezik személyes munkaterülettel az eszközön az egyéni kezdőlap képernyők, fiókok, alkalmazások és beállítások. **Nincs konfigurálva** lehetővé teszi a felhasználóknak más felhasználók felvétele az eszközre.
- **Felhasználó eltávolítása**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat felhasználók eltávolításában. **Nincs konfigurálva** lehetővé teszi a felhasználóknak más felhasználók eltávolítása az eszközről.
- **Fiókmódosítások**: Válassza a **Tiltás** lehetőséget, hogy megakadályozza a felhasználókat a fiókok módosításában. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók frissíthetik a felhasználói fiókokat az eszközön.

## <a name="work-profile-only"></a>Csak munkahelyi profil 

### <a name="work-profile-settings"></a>Munkahelyi profil beállításai

#### <a name="general"></a>Általános

- **Munkahelyi és személyes profilok közötti másolást és beillesztést**: válasszon **blokk** , hogy a másolás és beillesztés a munkahelyi és személyes alkalmazások között. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók megoszthassák az adatokat a személyes profilban szereplő alkalmazások használata a másolás és beillesztés 
- **Munkahelyi és személyes profilok közötti adatmegosztás**: válassza ki, ha a munkahelyi profilban szereplő alkalmazások alkalmazások megoszthatnak a személyes profilban. Például szabályozhatja megosztási műveletek alkalmazásokban, mint például a **megosztás...** lehetőséget a Chrome böngészőalkalmazásban). Ez a beállítás nem vonatkozik a másolás/beillesztés vágólapi viselkedésre. A megosztási beállítások:
  - **Alapértelmezett megosztási korlátozások**: Ez az eszköz alapértelmezett megosztási működésmódja, amely az Android-verziótól függően eltérő. Alapértelmezés szerint a személyes profilból lehet a munkahelyi profilba adatokat megosztani, a munkahelyiből a személyesbe viszont nem. A beállítás célja a munkahelyi profilból a személyesbe irányuló adatmegosztás megelőzése. A Google a 6.0-snál újabb verziójú eszközökön nem nyújt lehetőséget a személyesből a munkahelyi profilba irányuló adatmegosztás blokkolására.
  - **A munkahelyi profilban lévő alkalmazások kezelhetik a személyes profilból érkező megosztási kérelmeket**: Engedélyezi a személyesből a munkahelyi profilba irányuló adatmegosztásra szolgáló beépített Android-funkciót. Engedélyezéskor a személyes profil alkalmazásaiból származó megosztási kérések kezdeményezhetnek adatmegosztást a munkahelyi profil alkalmazásaival. A 6.0-snál korábbi verziójú androidos eszközökön ez az alapértelmezett beállítás.
  - **Határokon keresztüli megosztás engedélyezése**: Lehetővé teszi a munkahelyi profil határán kívüli megosztást mindkét irányban. Ilyenkor a munkahelyi profilban szereplő alkalmazások megoszthatnak adatokat a személyes profi jelöletlen alkalmazásaival. A beállítással lehetővé teszi a munkahelyi profil alkalmazásainak az adatmegosztást az eszköz nem felügyelt részével. Így körültekintően használja ezt a lehetőséget.

- **Munkahelyi profil értesítései az eszköz zárolt**: szabályozza-e a munkahelyi profilban lévő alkalmazások adatokat megjelenítheti az értesítésekben, ha az eszköz zárolva van. **Blokk** nem jelenik meg az adatokat. **Nincs konfigurálva** adatokat mutatja.
- **Alapértelmezett alkalmazásengedélyek**: Itt adhatja meg a munkahelyi profilban található összes alkalmazásra vonatkozó alapértelmezett engedélyszabályzatot. Az Android 6-os verziójától kezdve a rendszer alkalmazásindításkor felszólítja a felhasználót az alkalmazás által megkövetelt, konkrét engedélyek megadására. Ezzel a szabályzatbeállítással döntheti el, hogy a felhasználók megadhatják-e a munkahelyi profilban szereplő összes alkalmazás engedélyeit. Hozzárendelhet például egy olyan alkalmazást a munkahelyi profilhoz, amely helyadatokhoz kér hozzáférést. Általában az alkalmazás kéri a felhasználót a helyadatokhoz való hozzáférés megadására vagy elutasítására. Ezzel a szabályzattal kérdés nélkül automatikusan engedélyezhet vagy letilthat minden hozzáférést, vagy átadhatja a döntés jogát a felhasználónak. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Rákérdezés**
  - **Automatikus engedélyezés**
  - **Automatikus elutasítás**

  Alkalmazáskonfigurációs szabályzatokkal is engedélyeket adhat egyes alkalmazásoknak (**Ügyfélalkalmazások** > **Alkalmazáskonfigurációs szabályzatok**).

- **Fiókok hozzáadása és eltávolítása**: válasszon **blokk** , hogy a végfelhasználók manuálisan fiókok hozzáadásának vagy eltávolításának a munkahelyi profilban található. Ha például a Gmail alkalmazást androidos munkahelyi profilban telepíti, megakadályozhatja, hogy a végfelhasználók fiókokat adjanak hozzá vagy távolítsanak el ebben a munkaprofilban. **Nincs konfigurálva** lehetővé teszi, hogy a munkahelyi profilban található fiókok hozzáadásának.  

- **Névjegyek megosztása Bluetooth-kapcsolattal**: Engedélyezi egy másik Bluetooth-eszköz (például egy autó) a munkahelyi névjegyekhez való hozzáférését. Alapértelmezés szerint ez a beállítás nincs konfigurálva, a munkahelyi névjegyek pedig nem jelennek meg. A megosztás engedélyezéséhez és a munkahelyi profil névjegyeinek megjelenítéséhez válassza az **Engedélyezés** lehetőséget. Ez a beállítás az Android munkahelyi profilos, Android v6.0 és újabb operációs rendszerekkel rendelkező eszközökre vonatkozik. A beállítás engedélyezésével megengedheti bizonyos Bluetooth-eszközöknek, hogy az első kapcsolat alkalmával gyorsítótárazzák a munkahelyi kapcsolatokat. Ennek a szabályzatnak az eredeti párosítás/szinkronizálás utáni letiltása nem feltétlenül távolítja el a munkahelyi kapcsolatokat a Bluetooth-eszközről.

- **Képernyőfelvétel**: válasszon **blokk** képernyőképek megelőzése, illetve a képernyőfelvétel-készítés, az eszköz a munkahelyi profilban található. Ezen kívül megakadályozza a tartalom megjelenítését a biztonságos videokimenettel nem rendelkező megjelenítő eszközökön. **Nincs konfigurálva** lehetővé teszi, hogy a képernyőképek beolvasása.

- **Munkahelyi kapcsolattartási hívóazonosító megjelenítése a személyes profilban**: engedélyezésekor (**nincs konfigurálva**), a munkahelyi hívó részletei megjelennek a személyes profilban szereplőkkel. Ha a beállítása **blokk**, a munkahelyi hívó nem jelenik meg a személyes profilban. Az Android operációs rendszer 6.0-ás és újabb verzióira vonatkozik.

- **Keresés a munkahelyi névjegyek személyes profiltól érkező**: válasszon **letiltása** megakadályozza, hogy a felhasználók a személyes profilban szereplő alkalmazások a munkahelyi névjegyek keresése. **Nem szükséges** lehetővé teszi, hogy a személyes profilban munkahelyi névjegyek keresése.

- **Kamera**: válasszon **blokk** kívánja tagadni a hozzáférést a munkahelyi profilban található az eszközön a kamera. A beállítás nincs hatással a fényképezőkép személyes profilban való használatára. **Nem szükséges** a kamerához való hozzáférés lehetővé teszi a munkahelyi profil.

#### <a name="work-profile-password"></a>Munkahelyi profilhoz tartozó jelszó

- **Munkahelyi profilhoz tartozó jelszó megkövetelése**: Az engedélyezett munkahelyi profillal rendelkező Android 7.0-s és újabb verziójú eszközökre vonatkozik. Válasszon **megkövetelése** megadnia a PIN-kód-szabályzatot, amely csak a munkahelyi profilban szereplő alkalmazások vonatkozik. Alapértelmezés szerint a végfelhasználónak lehetősége van két külön-külön definiált PIN-kód használatára, vagy a felhasználók dönthetnek úgy, hogy a két meghatározott PIN-kód összevonásával csak az erősebbet használják. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó használja a munkahelyi alkalmazásokat, anélkül, hogy jelszót írna be.
- **Jelszó minimális hossza**: Itt adhatja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát (**4**-**16**).
- **A munkahelyi profil zárolása legfeljebb ennyi perc inaktivitás után**: Itt adhatja meg, hogy mennyi idő után zárolódjon a munkahelyi profil. A felhasználónak ezután meg kell adnia a hitelesítő adatait a hozzáférés visszanyeréséhez.
- **Sikertelen bejelentkezések száma, mielőtt törlődne az eszközön lévő összes adat**: Itt adhatja meg, hogy hányszor lehet helytelen jelszót megadni, mielőtt a rendszer törölné az eszközről a munkahelyi profil összes adatát.
- **Jelszó érvényessége (nap)**: Itt adhatja meg, hogy hány nap elteltével kell megváltoztatni az eszköz jelszavát (**1**-**255**).
- **Kötelező jelszótípus**: Itt adhatja meg az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Kötelező**
  - **Legalább számok**
  - **Komplex numerikus**: Nem lehet ismétlődő vagy egymást követő számokat megadni, például az „1111-et” vagy az „1234-et”
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása**: Itt adhatja meg, hogy hány új jelszót kell beállítani, mielőtt egy korábbit újból használhatna (**1**-**24**).
- **Ujjlenyomattal történő Zárolásfeloldás**: válasszon **blokk** megakadályozza, hogy a végfelhasználók számára az eszköz ujjlenyomat-olvasót használja az eszköz zárolásának feloldásához. **Nincs konfigurálva** lehetővé teszi a felhasználók a munkahelyi profilban szereplő ujjlenyomat a zárolás feloldásához.
- **Smart Lock és más megbízhatósági ügynökök**: válasszon **blokk** , hogy a Smart Lock és más megbízhatósági ügynökök módosíthassák a zárolási képernyő beállításai kompatibilis eszközökön. Ez a funkció, más néven bizalmi ügynök lehetővé teszi, hogy letiltását vagy megkerülését az eszköz zárolási képernyője jelszavának, ha az eszköz megbízható helyen van. Így például megkerülheti a munkahelyi profil jelszavát abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

### <a name="device-password"></a>Eszköz jelszava

A jelszó-beállításokat alkalmazni a munkahelyi profilt használó eszközök személyes profilok.

- **Jelszó minimális hossza**: Itt adhatja meg a jelszóban szereplő számjegyek vagy karakterek minimális számát (**4**-**14**).
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
- **Ujjlenyomattal történő Zárolásfeloldás**: válasszon **blokk** megakadályozza, hogy a végfelhasználó számára az eszköz ujjlenyomat-olvasót használja az eszköz zárolásának feloldásához. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó számára az eszközzárolás ujjlenyomattal történő használatával.
- **Smart Lock és más megbízhatósági ügynökök**: válasszon **blokk** , hogy a Smart Lock és más megbízhatósági ügynökök módosíthassák a zárolási képernyő beállításai kompatibilis eszközökön. Ez a funkció, más néven bizalmi ügynök lehetővé teszi, hogy letiltását vagy megkerülését az eszköz zárolási képernyője jelszavának, ha az eszköz megbízható helyen van. Így például megkerülheti a munkahelyi profil jelszavát abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

### <a name="system-security"></a>Rendszerbiztonság

- **Alkalmazások fenyegetettségvizsgálata**: **megkövetelése** érvényesíti a **alkalmazások ellenőrzése** beállítás engedélyezve van a munkahelyi és személyes profiloknál.

   > [!Note]
   > Ez a beállítás csak Android O vagy újabb rendszerű eszközök esetén érvényesül.

### <a name="connectivity"></a>Kapcsolat

- **Mindig bekapcsolt VPN**: Az **Engedélyezés** beállítással a VPN-ügyfél automatikusan csatlakozik és újracsatlakozik a VPN-hez. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal elindítható, ha a felhasználó zárolja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. 

  A mindig bekapcsolt VPN beállítás az összes VPN-ügyfél számára való letiltásához válassza a **Nincs konfigurálva** lehetőséget.

  > [!IMPORTANT]
  > Egy eszközön egyszerre csak egy mindig bekapcsolt VPN-szabályzatot helyezzen üzembe. Több ilyen szabályzat üzembe helyezése egyetlen eszközön nem támogatott.

- **VPN-ügyfél**: Válasszon egy Mindig bekapcsolt állapotot támogató VPN-ügyfelet. A választható lehetőségek:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Hálózatok GlobalProtect
  - Pulse Secure
  - Egyéni
    - **Csomagazonosító**: Adja meg az alkalmazás csomagazonosítóját a Google Play Áruházban. Ha például az áruházban levő alkalmazás URL-címe `https://play.google.com/store/details?id=com.contosovpn.android.prod`, a csomagazonosító `com.contosovpn.android.prod` lesz.

  > [!IMPORTANT]
  >  - A kiválasztott VPN-ügyfelet az eszközön kell telepíteni, és támogatnia kell az alkalmazásonkénti VPN-t a munkahelyi profilokban. Ellenkező esetben hiba történik. 
  >  - A VPN-ügyfélalkalmazást jóvá kell hagynia a **felügyelt Google Play Áruházban**, szinkronizálnia kell az alkalmazást az Intune-nal, majd üzembe helyeznie az eszközön. Ezt követően az alkalmazás telepítve lesz a felhasználó munkahelyi profiljában.
  >  - Az alkalmazásonkénti VPN és az F5 Access for Android 3.0.3 együttes használatával kapcsolatban több probléma is ismert. További információt az [F5 Access for Android 3.0.3 kibocsátási megjegyzéseiben](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-3.html#relnotes_known_issues_f5_access_android) talál.

- **Zárolt mód**: Ennek **engedélyezésével** minden hálózati forgalma a VPN-alagútra irányíthat. Ha a VPN-kapcsolat nincs kiépítve, az eszköznek nem lesz hálózati hozzáférése.

  A **Nincs konfigurálva** beállítással a forgalom a VPN-alagúton vagy a mobilhálózaton is áthaladhat.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Teljes képernyős profilok is létrehozhat [Android](device-restrictions-android.md#kiosk) és [Windows 10-es](kiosk-settings.md) eszközök.
