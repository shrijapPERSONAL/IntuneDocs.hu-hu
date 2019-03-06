---
title: Android Enterprise eszközbeállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Android Enterprise vagy az Android for Work-eszközök korlátozása az eszköz beállításai, többek között másolás és beillesztés, show, értesítések, az Alkalmazásengedélyek, az adatok megosztásához, a jelszó hosszát, a bejelentkezési hibák használata ujjlenyomat a zárolás feloldásához újbóli jelszavak, és a bluetooth engedélyezése a munkahelyi névjegyek megosztása. Eszközök konfigurálása egy dedikált eszköz teljes képernyős alkalmazás egy vagy több alkalmazás futtatásához.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 85b831e0212a71c8b081aec625c017b13b921ead
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57391986"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Android Enterprise eszközbeállítások engedélyezett vagy korlátozott funkciók az Intune-nal

Ez a cikk és az Android Enterprise eszközökön szabályozhatja a különböző beállításokat ismerteti. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat engedélyezi vagy letiltja a szolgáltatások, a dedikált eszközök, a biztonság szabályozásához és a további futtatási alkalmazások.

## <a name="before-you-begin"></a>Előkészületek

[Eszközkonfigurációs profil létrehozása](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Csak az eszköz tulajdonosa

### <a name="general-settings"></a>Általános beállítások

- **Képernyőfelvétel**: Válasszon **blokk** megakadályozza a képernyőképek és a képernyő rögzíti az eszközön. Ezen kívül megakadályozza a tartalom megjelenítését a biztonságos videokimenettel nem rendelkező megjelenítő eszközökön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó képként rögzítse a képernyőn látható tartalmat.
- **Kamera**: Válasszon **blokk** kívánja tagadni a hozzáférést az eszközön a kamera. **Nem szükséges** engedélyezi a hozzáférést az eszköz kamerájának használatát.
- **Alapértelmezett alkalmazásengedélyezési szabályzat**: Ez a beállítás a futtatókörnyezeti engedélyekre irányuló kérelmek alapértelmezett engedélyházirendjének meghatározása. Lehetséges értékei többek között a következők:
  - **Eszköz alapértelmezése**: Az eszköz alapértelmezett beállítást használja.
  - **Rákérdezés**: Kéri a felhasználót, hogy az engedélyt jóvá.
  - **Automatikus engedélyezés**: Automatikusan engedélyekkel.
  - **Automatikus elutasítás**: Engedélyeket a rendszer automatikusan megtagadja.
- **Dátum-és időmódosítás**: Válasszon **blokk** megakadályozza, hogy a felhasználók manuális beállítása dátuma és időpontja. **Nincs konfigurálva** lehetővé teszi a felhasználóknak az beállított dátumot és időt az eszközön.
- **Hangerőmódosítások**: Válasszon **blokk** meg, hogy a felhasználók módosítsák az eszköz kötet. **Nincs konfigurálva** lehetővé teszi, hogy a kötet beállításokat az eszközön.
- **Gyári beállítások visszaállítása**: Válasszon **blokk** megakadályozza, hogy a felhasználók segítségével a gyári alaphelyzetbe az eszköz beállításaiban. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók számára ez a beállítás használatát az eszközön.
- **Biztonságos indítás**: Válasszon **blokk** meg, hogy a felhasználók biztonságosan módba az eszköz újraindítását. **Nincs konfigurálva** lehetővé teszi a felhasználóknak indítsa újra az eszközt a csökkentett módban.
- **Állapotsor**: Válasszon **blokk** , hogy megakadályozza a hozzáférést az állapotsorhoz való, beleértve az értesítéseket és a gyors beállításokat. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók az állapotsor való hozzáférést.
- **Data services központi**: Válasszon **blokk** a mobilhálózati adatroaming elkerülése érdekében. **Nincs konfigurálva** engedélyezi az adatroaming használatát, ha az eszköz mobilhálózati.
- **Wi-Fi-beállítások módosításai**: Válasszon **blokk** , az eszköz tulajdonosa által létrehozott Wi-Fi-beállítások módosításának megakadályozása. Felhasználók saját Wi-Fi-beállításokat hozhat létre. **Nincs konfigurálva** lehetővé teszi a felhasználóknak, hogy a Wi-Fi-beállításokat az eszközön.
- **Wi-Fi hozzáférési pont konfigurációja**: Válasszon **blokk** , hogy a felhasználók létrehozása vagy módosítása a Wi-Fi-konfigurációkat. **Nincs konfigurálva** lehetővé teszi a felhasználóknak, hogy a Wi-Fi-beállításokat az eszközön.
- **Bluetooth-konfiguráció**: Válasszon **blokk** meg, hogy a felhasználók a Bluetooth konfigurálását az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy az eszköz Bluetooth használatával.
- **-Alapú internetmegosztás és hozzáférési pontokhoz**: Válasszon **blokk** hordozható pontokhoz-alapú internetmegosztás és a hozzáférés megelőzése érdekében. **Nincs konfigurálva** -alapú internetmegosztás és hordozható elérési pontokhoz való hozzáférést.
- **USB-tárolók**: Válasszon **engedélyezése** az eszköz USB-tároló elérése érdekében. **Nincs konfigurálva** megakadályozza a USB-tároló.
- **USB-fájlátvitel**: Válasszon **blokk** elkerülése érdekében fájlok átvitelével az USB-kapcsolaton keresztül. **Nincs konfigurálva** lehetővé teszi a fájlok átviteléhez.
- **Külső adathordozó**: Válasszon **blokk** megakadályozza a használatával, és kapcsolódás bármilyen külső adathordozó az eszközön. **Nincs konfigurálva** külső adathordozó engedélyezi az eszközön.
- **Az NFC segítségével adatokat fényt**: Válasszon **blokk** , hogy a kis hatótávolságú kommunikációs (NFC) technológia használatával távolsági adatokat az alkalmazásokból. **Nincs konfigurálva** lehetővé teszi, hogy az NFC segítségével végzett eszközök között adatokat megosztani.
- **Hibakeresési funkciók**: Válasszon **engedélyezése** , hogy a felhasználók hibakeresési funkciók használata az eszközön. **Nincs konfigurálva** megakadályozza, hogy a felhasználók a hibakeresési funkciók használata az eszközön.
- **Mikrofon beállítása**: Válasszon **blokk** , hogy a felhasználók a mikrofon visszahangosításának és a mikrofon hangereje. **Nincs konfigurálva** lehetővé teszi a felhasználó használhatja, és állítsa be a mikrofon az eszközön.
- **Gyári visszaállítás elleni védelem e-mail-címei**: Válasszon **Google-fiók e-mail-címek**. Adja meg, amely oldhatja fel az eszköz tartalma törlődik, miután eszközadminisztrátorok e-mail címét. Ügyeljen arra, hogy az e-mail-címeket egymástól pontosvesszővel, mint például `admin1@gmail.com;admin2@gmail.com`. Ha egy e-mailt nem adott meg, bárki is az eszköz feloldásához, a gyári beállítások visszaállítása után.
- **Hálózati vészkijárat**: Válasszon **engedélyezése** , hogy a felhasználók a hálózat escape csíkozási funkció bekapcsolása. Ha a hálózati kapcsolat az eszköz nem végzett, majd a vészkijárat kéri ideiglenesen csatlakozzon egy hálózathoz, és frissítenie kell az szabályzat. A szabályzat alkalmazása után a rendszer elfelejti az átmeneti hálózatot, és az eszköz folytatja a rendszerindítást. Ez a funkció eszköz csatlakozik a hálózathoz, ha:
  - Nincs megfelelő hálózati a legutóbbi házirendben.
  - Az eszköz zárolási feladat üzemmódban alkalmazás indul.
  - A felhasználó nem tudja elérni az Eszközbeállítások között.

  **Nincs konfigurálva** megakadályozza, hogy a felhasználók ne tudják bekapcsolni a a hálózat escape csíkozási funkciót az eszközön.

- **Lehetővé teszi az ismeretlen forrásból történő telepítést**: Válasszon **engedélyezése** így a felhasználók bekapcsolhatja a **ismeretlen források**. Ez a beállítás lehetővé teszi, hogy a telepítéséhez az ismeretlen forrásból származó alkalmazások. **Nincs konfigurálva** megakadályozza, hogy a felhasználók ne tudják bekapcsolni a **ismeretlen források**.
- **Rendszerfrissítés**: Válasszon egy lehetőséget adja meg, hogyan kezeli az eszköz a vezeték nélküli frissítések:
  - **Eszköz alapértelmezése**: Az eszköz alapértelmezett beállítást használja.
  - **Automatikus**: Frissítések automatikusan települnek a felhasználói beavatkozás nélkül. Ennek a szabályzatnak a beállításakor minden függőben lévő frissítés azonnal települ.
  - **Elhalasztva**: Frissítések vannak Elhalasztva 30 napig. A 30 nap végén Android kéri a felhasználót, hogy a frissítés telepítéséhez. Az eszközgyártók vagy a szolgáltatók megakadályozhatják (kivételként) a fontos biztonsági frissítések elhalasztását. A kivételként kezelt frissítések rendszerértesítést jelenítenek meg a felhasználó számára az eszközön. 
  - **Karbantartási időszak**: Az Intune-ban beállított napi karbantartási időszak alatt automatikusan telepíti a frissítéseket. Telepítés megkísérli naponta 30 napig, és meghiúsulhat, ha nincs elegendő terület vagy akkumulátor szintjét. A 30 nap elteltével Android kéri a felhasználót, hogy telepítse. Ez az időszak szolgál a Play-alkalmazások frissítéseinek telepítésére is. Dedikált eszközök, például kioszkok, a beállítást használja, Egyalkalmazásos dedikált előtér eszközalkalmazások frissítheti.
- **Alkalmazás automatikusan frissül**: Válassza ki, ha az automatikus frissítések telepítve vannak. A választható lehetőségek:
  - **Nincs konfigurálva**
  - **Felhasználói választási lehetőség**
  - **Soha nem**
  - **Wi-Fi csak**
  - **Mindig**

- **A windows értesítési**: Ha a beállítása **letiltása**, ablakban értesítéseket, beleértve a toasts, a bejövő hívások, a kimenő hívások, a teljesítményriasztások és a rendszerhibák nem jelennek meg az eszközön. Ha a beállítása **nincs konfigurálva**, az operációs rendszer alapértelmezett értéket használja, amely lehet értesítéseket jeleníthet meg.
- **Kihagyás először a mutatók**: Válasszon **engedélyezése** elrejtése, vagy hagyja ki a javaslatok alkalmazások végighaladhat az oktatóanyagok, vagy olvassa el bármilyen bevezető mutatók, az alkalmazás indításakor. Ha a beállítása **nincs konfigurálva**, az operációs rendszer alapértelmezett szolgál, amely lehet ezek a javaslatok megjelenítése, az alkalmazás indításakor.


### <a name="system-security-settings"></a>A rendszer biztonsági beállításai

- **Alkalmazások fenyegetettségvizsgálata**: **Szükséges** érvényesíti a **alkalmazások ellenőrzése** beállítás engedélyezve van a munkahelyi és személyes profiloknál.

### <a name="dedicated-device-settings"></a>Dedikált eszközök beállításai

Ezek a beállítások használatával az dedikált eszközök kioszk stílusú felhasználói beállítása. Egyetlen alkalmazás-eszközök konfigurálása, vagy számos alkalmazás futtatásához. Ha egy eszköz teljes képernyős mód be van állítva, csak a hozzáadott alkalmazások elérhetők lesznek. Ezek a beállítások dedikált Android Enterprise-eszközökre vonatkoznak. Teljes körűen felügyelt Android Enterprise-eszközöket, nem vonatkoznak.

**Teljes képernyős mód**: Akkor válassza, ha az eszköz egy alkalmazást futtat, vagy több alkalmazást futtat.

- **Egyetlen alkalmazás**: Felhasználók csak érhetik el egy alkalmazást az eszközön. Amikor az eszköz elindul, csak az adott alkalmazás elindul. A felhasználók nem nyithatnak meg új alkalmazásokat, és nem módosíthatják a futó alkalmazást.

  **Lépések**
  1. Válasszon **felügyelt alkalmazás kiválasztása**, és válassza ki a felügyelt Google Play-alkalmazást a listából. 

      Ha nem rendelkezik az összes alkalmazás szerepel a listában, majd [bizonyos Android-alkalmazások hozzáadása](apps-add-android-for-work.md) az eszközön. Ügyeljen arra, hogy [rendeli az alkalmazást a dedikált eszközök számára létrehozott megfelelő eszközcsoporthoz](apps-deploy.md).

  2. Válasszon **OK** > **OK** az alkalmazás hozzáadásához.

- **Többalkalmazásos**: A felhasználók egy korlátozott számú alkalmazások az eszközön. Amikor az eszköz elindul, csak a hozzáadott alkalmazások indítsa el. Bizonyos webes hivatkozások, amelyek a felhasználó meg tudja nyitni is hozzáadhat. A házirend van érvényben, amikor megjelenik a felhasználók számára az engedélyezett alkalmazások ikonjai a kezdőképernyőn.

  > [!IMPORTANT]
  > A többalkalmazásos dedikált eszközök, a [kezdőlap képernyő felügyelt alkalmazás](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) a Google Play áruházból **kell**:
  >   - [Egy ügyfélalkalmazás hozzáadott](apps-add-android-for-work.md) az Intune-ban
  >   - [Az eszköz csoporthoz rendelt](apps-deploy.md) a dedikált eszközök számára létrehozott
  > 
  > A **kezdőlap képernyő felügyelt** alkalmazás nem található a konfigurációs profil feltétlenül szükséges, de ügyfélalkalmazásként hozzá kell adni. Ha a **kezdőlap képernyő felügyelt** alkalmazás ügyfélalkalmazásként adnak, adja hozzá a configiration profil a minden más alkalmazás ikonok jelennek meg a a a **kezdőlap képernyő felügyelt** alkalmazást. 

  - Válasszon **Hozzáadás**, és válassza ki az alkalmazások a listából.

    Ha a **kezdőlap képernyő felügyelt** alkalmazás nem szerepel a listán, majd [adja hozzá a Google Play áruházból](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Ügyeljen arra, hogy [rendelni az alkalmazást](apps-deploy.md) az eszközcsoporthoz a dedikált eszközök számára létrehozott.

    Is hozzáadhat más [Android-alkalmazások](apps-add-android-for-work.md) és [webes alkalmazások](web-app.md) hozta létre a szervezet az eszköz számára. Ügyeljen arra, hogy [rendeli az alkalmazást a dedikált eszközök számára létrehozott megfelelő eszközcsoporthoz](apps-deploy.md).

  - **Virtuális kezdőlap gombjának**: Válasszon **engedélyezése** , a kezdőlap gombjának megjelenítése a dedikált eszközön. Kiválasztásakor visszaadja a felhasználó az eszköz kezdőképernyőjére így a felhasználók egyszerűen válthat az alkalmazások között. Néhány Android-eszközön a felhasználók valószínűleg a pöccintsen felfelé a kezdőlap gombjának megjelenítése a képernyőn. **Tiltsa le** egy otthoni gomb nem jelenik meg, így a felhasználók alkalmazások közötti váltás kell használnia a Vissza gombra.
  - **Hagyja meg a teljes képernyős mód**: Válasszon **engedélyezése** , hogy a rendszergazdák számára, hogy ideiglenesen letilthatja a teljes képernyős mód az eszköz frissítéséhez. Ezzel a funkcióval a rendszergazda használata: 
  
    1. Továbbra is fennáll, addig, amíg megjelenik a "Kilépés a teljes képernyős" gombra, jelölje be a Vissza gombra. 
    2. A gombot választja, és beírja az **hagyja meg a teljes képernyős mód kód** PIN-kódot.
    3. Amikor végzett a módosításokkal, válassza ki a **kezdőlap képernyő felügyelt** alkalmazást. Ez a lépés az eszköz relocks többalkalmazásos kioszk módba. 
    
    **Tiltsa le** nem lehetővé teheti a teljes képernyős mód felfüggesztése. Ha a rendszergazda továbbra is fennáll, kattintson a Vissza gombra, és a "Kilépés a teljes képernyős" gombot választja, egy üzenet tájékoztatja, hogy egy PIN-kód megadása kötelező.
    
    - **Hagyja meg a teljes képernyős mód kód**: Adjon meg egy 4 – 6 számjegyű numerikus PIN-kód. A rendszergazda ideiglenesen letilthatja a teljes képernyős mód a PIN-kódot használja.
 
  - **Állítsa be az egyéni URL-cím hátterének**: Adja meg a dedikált eszközön a háttérben futó képernyő testreszabása URL-CÍMÉT.

### <a name="device-password-settings"></a>Eszköz jelszóbeállításai

- **Keyguard**: Válasszon **letiltása** megakadályozza, hogy a használt Keyguard zárolási képernyő funkció használatát az eszközön. **Nincs konfigurálva** lehetővé teszi a felhasználó Keyguard funkcióinak használatát.
- **Le van tiltva a keyguard funkciók**: Ha keyguard engedélyezve van az eszközön, válassza ki a fejlesztendő funkciók letiltása. Például, hogy amikor **biztonságos kamera** be van jelölve, a kamera funkció le van tiltva az eszközön. A szolgáltatásokat, nincs ellenőrizve engedélyezve van az eszközön.
- **Kötelező jelszótípus**: Az eszköz kötelező jelszó típusát határozza meg. A választható lehetőségek:
  - **Legalább számok**
  - **Komplex numerikus**: Ismétlődő vagy egymást követő számokat, például az "1111" vagy "1234", nem engedélyezett.
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Jelszó minimális hossza**: Adja meg a felhasználónak meg kell adnia, (4 és 16 karakter között) jelszó minimális hosszát.
- **Bejelentkezési hibák eszköz törlése előtt**: Adja meg, mielőtt a rendszer törölné az eszközt (között 1 – 11.) a sikertelen bejelentkezések száma.

### <a name="power-settings"></a>Energiaellátási beállítások

- **Képernyő zárolásáig eltelt idő**: Adja meg a üresjárati idő az eszköz zárolása előtt meg kell adni.
- **Képernyő bekapcsolása, amikor eszköz csatlakoztatva**: Válassza ki, melyik áramforrásokhoz okozhat, ha csatlakoztatva hagyja el a az eszköz képernyőjén.

### <a name="users-and-accounts-settings"></a>Felhasználói és fiókbeállítások

- **Új felhasználók hozzáadása**: Válasszon **blokk** megakadályozza, hogy a felhasználók új felhasználók hozzáadása. Minden felhasználó rendelkezik személyes munkaterülettel az eszközön az egyéni kezdőlap képernyők, fiókok, alkalmazások és beállítások. **Nincs konfigurálva** lehetővé teszi a felhasználóknak más felhasználók felvétele az eszközre.
- **Felhasználók eltávolítása**: Válasszon **blokk** megakadályozza, hogy a felhasználók felhasználók eltávolítását. **Nincs konfigurálva** lehetővé teszi a felhasználóknak más felhasználók eltávolítása az eszközről.
- **Módosítások fiók**: Válasszon **blokk** megakadályozza, hogy a felhasználók fiókok módosítása. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók frissíthetik a felhasználói fiókokat az eszközön.

### <a name="connectivity"></a>Kapcsolat

- **Always-on VPN**: Válasszon **engedélyezése** egy VPN-ügyfél automatikusan csatlakozhat, és újból csatlakozik a virtuális Magánhálózat beállításához. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal elindítható, ha a felhasználó zárolja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. 

  A mindig bekapcsolt VPN beállítás az összes VPN-ügyfél számára való letiltásához válassza a **Nincs konfigurálva** lehetőséget.

  > [!IMPORTANT]
  > Egy eszközön egyszerre csak egy mindig bekapcsolt VPN-szabályzatot helyezzen üzembe. Több ilyen szabályzat üzembe helyezése egyetlen eszközön nem támogatott.

- **VPN-ügyfél**: Válassza ki a VPN-ügyfél, amely támogatja az Always On. A választható lehetőségek:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Hálózatok GlobalProtect
  - Pulse Secure
  - Egyéni
    - **Csomagazonosító**: Adja meg a Google Play áruházban az alkalmazás Csomagazonosítóját. Ha például az áruházban levő alkalmazás URL-címe `https://play.google.com/store/details?id=com.contosovpn.android.prod`, a csomagazonosító `com.contosovpn.android.prod` lesz.

  > [!IMPORTANT]
  >  - A kiválasztott VPN-ügyfelet az eszközön kell telepíteni, és támogatnia kell az alkalmazásonkénti VPN-t a munkahelyi profilokban. Ellenkező esetben hiba történik. 
  >  - A VPN-ügyfélalkalmazást jóvá kell hagynia a **felügyelt Google Play Áruházban**, szinkronizálnia kell az alkalmazást az Intune-nal, majd üzembe helyeznie az eszközön. Ezt követően az alkalmazás telepítve lesz a felhasználó munkahelyi profiljában.
  >  - Van Előfordulhat, hogy ismert problémák alkalmazásonkénti VPN az Android 3.0.4 F5 hozzáféréssel rendelkező használatakor. Lásd: [F5 kibocsátási megjegyzések az F5 Access for Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) további információt.

- **Zárolt módban**: Válasszon **engedélyezése** kényszerítése minden hálózati forgalmat a VPN-alagút használatához. Ha a VPN-kapcsolat nincs kiépítve, az eszköznek nem lesz hálózati hozzáférése.

  A **Nincs konfigurálva** beállítással a forgalom a VPN-alagúton vagy a mobilhálózaton is áthaladhat.

## <a name="work-profile-only"></a>Csak munkahelyi profil 

### <a name="work-profile-settings"></a>Munkahelyi profil beállításai

#### <a name="general"></a>Általános

- **Munkahelyi és személyes profilok közötti másolást és beillesztést**: Válasszon **blokk** , hogy a másolás és beillesztés a munkahelyi és személyes alkalmazások között. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók megoszthassák az adatokat a személyes profilban szereplő alkalmazások használata a másolás és beillesztés 
- **Munkahelyi és személyes profilok közötti adatmegosztás**: Válassza ki, ha a munkahelyi profilban szereplő alkalmazások alkalmazások megoszthatnak a személyes profilban. Például szabályozhatja megosztási műveletek alkalmazásokban, mint például a **megosztás...** lehetőséget a Chrome böngészőalkalmazásban). Ez a beállítás nem vonatkozik a másolás/beillesztés vágólapi viselkedésre. A megosztási beállítások:
  - **Alapértelmezett megosztási korlátozások**: Alapértelmezett megosztási az eszköz, amely az Android-verziótól függően változik. Alapértelmezés szerint a személyes profilból lehet a munkahelyi profilba adatokat megosztani, a munkahelyiből a személyesbe viszont nem. A beállítás célja a munkahelyi profilból a személyesbe irányuló adatmegosztás megelőzése. A Google a 6.0-snál újabb verziójú eszközökön nem nyújt lehetőséget a személyesből a munkahelyi profilba irányuló adatmegosztás blokkolására.
  - **A munkahelyi profilban szereplő alkalmazások kezelhetik a személyes profilból érkező megosztási kérelmeket**: Lehetővé teszi a beépített Android-funkciót, amely engedélyezi a személyesből a munkahelyi profilba. Engedélyezéskor a személyes profil alkalmazásaiból származó megosztási kérések kezdeményezhetnek adatmegosztást a munkahelyi profil alkalmazásaival. A 6.0-snál korábbi verziójú androidos eszközökön ez az alapértelmezett beállítás.
  - **Határokon keresztüli megosztás engedélyezése**: Ezzel a lehetőséggel engedélyezheti a munkahelyi profil határán mindkét irányban. Ilyenkor a munkahelyi profilban szereplő alkalmazások megoszthatnak adatokat a személyes profi jelöletlen alkalmazásaival. A beállítással lehetővé teszi a munkahelyi profil alkalmazásainak az adatmegosztást az eszköz nem felügyelt részével. Így körültekintően használja ezt a lehetőséget.

- **Munkahelyi profil értesítései az eszköz zárolt**: Azt szabályozza, hogy a munkahelyi profilban szereplő alkalmazások adatait megjelenítheti értesítéseket, amikor az eszköz zárolva van. **Blokk** nem jelenik meg az adatokat. **Nincs konfigurálva** adatokat mutatja.
- **Alapértelmezett Alkalmazásengedélyek**: Meghatározza a munkahelyi profilban található összes alkalmazásra vonatkozó alapértelmezett szabályzatot. Az Android 6-os verziójától kezdve a rendszer alkalmazásindításkor felszólítja a felhasználót az alkalmazás által megkövetelt, konkrét engedélyek megadására. Ezzel a szabályzatbeállítással döntheti el, hogy a felhasználók megadhatják-e a munkahelyi profilban szereplő összes alkalmazás engedélyeit. Hozzárendelhet például egy olyan alkalmazást a munkahelyi profilhoz, amely helyadatokhoz kér hozzáférést. Általában az alkalmazás kéri a felhasználót a helyadatokhoz való hozzáférés megadására vagy elutasítására. Ezzel a szabályzattal kérdés nélkül automatikusan engedélyezhet vagy letilthat minden hozzáférést, vagy átadhatja a döntés jogát a felhasználónak. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Rákérdezés**
  - **Automatikus engedélyezés**
  - **Automatikus elutasítás**

  Alkalmazáskonfigurációs szabályzatokkal is engedélyeket adhat egyes alkalmazásoknak (**Ügyfélalkalmazások** > **Alkalmazáskonfigurációs szabályzatok**).

- **Fiókok hozzáadása és eltávolítása**: Válasszon **blokk** , hogy a végfelhasználók manuálisan fiókok hozzáadásának vagy eltávolításának a munkahelyi profilban található. Ha például a Gmail alkalmazást androidos munkahelyi profilban telepíti, megakadályozhatja, hogy a végfelhasználók fiókokat adjanak hozzá vagy távolítsanak el ebben a munkaprofilban. **Nincs konfigurálva** lehetővé teszi, hogy a munkahelyi profilban található fiókok hozzáadásának.  

- **Bluetooth-névjegyek megosztása**: Lehetővé teszi a hozzáférést a munkahelyi névjegyekhez egy másik eszköz, például egy autó párosítva van a Bluetooth segítségével. Alapértelmezés szerint ez a beállítás nincs konfigurálva, a munkahelyi névjegyek pedig nem jelennek meg. A megosztás engedélyezéséhez és a munkahelyi profil névjegyeinek megjelenítéséhez válassza az **Engedélyezés** lehetőséget. Ez a beállítás az Android munkahelyi profilos, Android v6.0 és újabb operációs rendszerekkel rendelkező eszközökre vonatkozik. A beállítás engedélyezésével megengedheti bizonyos Bluetooth-eszközöknek, hogy az első kapcsolat alkalmával gyorsítótárazzák a munkahelyi kapcsolatokat. Ennek a szabályzatnak az eredeti párosítás/szinkronizálás utáni letiltása nem feltétlenül távolítja el a munkahelyi kapcsolatokat a Bluetooth-eszközről.

- **Képernyőfelvétel**: Válasszon **blokk** megakadályozza a képernyőképek és a képernyő rögzíti a munkahelyi profilban található az eszközön. Ezen kívül megakadályozza a tartalom megjelenítését a biztonságos videokimenettel nem rendelkező megjelenítő eszközökön. **Nincs konfigurálva** lehetővé teszi, hogy a képernyőképek beolvasása.

- **Munkahelyi kapcsolattartási hívóazonosító megjelenítése a személyes profilban**: Ha engedélyezve van (**nincs konfigurálva**), a munkahelyi hívó részletei megjelennek a személyes profilban szereplőkkel. Ha a beállítása **blokk**, a munkahelyi hívó nem jelenik meg a személyes profilban. Az Android operációs rendszer 6.0-ás és újabb verzióira vonatkozik.

- **Keresés a munkahelyi névjegyek személyes profiltól érkező**: Válasszon **blokk** megakadályozza, hogy a felhasználók a személyes profilban szereplő alkalmazások a munkahelyi névjegyek keresése. **Nem szükséges** lehetővé teszi, hogy a személyes profilban munkahelyi névjegyek keresése.

- **Kamera**: Válasszon **blokk** kívánja tagadni a hozzáférést a munkahelyi profilban található az eszközön a kamera. A beállítás nincs hatással a fényképezőkép személyes profilban való használatára. **Nem szükséges** a kamerához való hozzáférés lehetővé teszi a munkahelyi profil.

#### <a name="work-profile-password"></a>Munkahelyi profilhoz tartozó jelszó

- **Munkahelyi profilhoz tartozó jelszó megkövetelése**: Engedélyezett munkahelyi profillal rendelkező Android 7.0-s és újabb vonatkozik. Válasszon **megkövetelése** megadnia a PIN-kód-szabályzatot, amely csak a munkahelyi profilban szereplő alkalmazások vonatkozik. Alapértelmezés szerint a végfelhasználónak lehetősége van két külön-külön definiált PIN-kód használatára, vagy a felhasználók dönthetnek úgy, hogy a két meghatározott PIN-kód összevonásával csak az erősebbet használják. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó használja a munkahelyi alkalmazásokat, anélkül, hogy jelszót írna be.
- **Jelszó minimális hossza**: Rendelkeznie kell a felhasználó jelszava, karakterek minimális számát adja meg a **4**-**16**.
- **Profil zárolása legfeljebb ennyi perc inaktivitás után a munkahelyi**: Válassza ki az idő a munkahelyi profil zárolása előtt. A felhasználónak ezután meg kell adnia a hitelesítő adatait a hozzáférés visszanyeréséhez.
- **Bejelentkezési hibák eszköz törlése előtt**: Adja meg, hogy hányszor helytelen jelszót megadni, mielőtt a munkahelyi profilt a rendszer törölné az eszközről.
- **Jelszó érvényessége (napokban)**: Adja meg, hány nap elteltével kell megváltoztatni a végfelhasználó jelszavát (a **1**-**255**).
- **Kötelező jelszótípus**: Válassza ki, hogy az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Kötelező**
  - **Legalább számok**
  - **Komplex numerikus**: Ismétlődő vagy egymást követő számokat, mint például a "1111" vagy "1234" nem engedélyezett
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása**: Adja meg az új jelszót használni kell, mielőtt egy korábbit újból használhatna (a **1**-**24**).
- **Ujjlenyomattal történő Zárolásfeloldás**: Válasszon **blokk** megakadályozza, hogy a végfelhasználók számára az eszköz ujjlenyomat-olvasót használja az eszköz zárolásának feloldásához. **Nincs konfigurálva** lehetővé teszi a felhasználók a munkahelyi profilban szereplő ujjlenyomat a zárolás feloldásához.
- **Smart Lock és más megbízhatósági ügynökök**: Válasszon **blokk** , hogy a Smart Lock és más megbízhatósági ügynökök módosíthassák a zárolási képernyő beállításai kompatibilis eszközökön. Ez a funkció, más néven bizalmi ügynök lehetővé teszi, hogy letiltását vagy megkerülését az eszköz zárolási képernyője jelszavának, ha az eszköz megbízható helyen van. Így például megkerülheti a munkahelyi profil jelszavát abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

### <a name="device-password"></a>Eszköz jelszava

A jelszó-beállításokat alkalmazni a munkahelyi profilt használó eszközök személyes profilok.

- **Jelszó minimális hossza**: Rendelkeznie kell a felhasználó jelszava, karakterek minimális számát adja meg a **4**-**14**.
- **Ennyi perc inaktivitás képernyőzárolás**: Válassza ki, hogy mennyi idő elteltével automatikusan zárolja magát az eszközök
- **Bejelentkezési hibák eszköz törlése előtt**: Adja meg, hogy hányszor helytelen jelszót megadni, mielőtt az összes adat végleg törlődne az eszközről
- **Jelszó érvényessége (napokban)**: Adja meg, hány nap elteltével kell megváltoztatni a végfelhasználó jelszavát (a **1**-**255**)
- **Kötelező jelszótípus**: Válassza ki, hogy az eszközön beállítandó jelszó típusát. A következő lehetőségek közül választhat:
  - **Eszköz alapértelmezése**
  - **Alacsony biztonságú biometrikus**
  - **Kötelező**
  - **Legalább számok**
  - **Komplex numerikus**: Ismétlődő vagy egymást követő számokat, mint például a "1111" vagy "1234" nem engedélyezettek.
  - **Legalább betűk**
  - **Legalább alfanumerikus karakterek**
  - **Legalább alfanumerikus karakterek és szimbólumok**
- **Korábbi jelszavak újbóli használatának tiltása**: Adja meg az új jelszót használni kell, mielőtt egy korábbit újból használhatna (a **1**-**24**).
- **Ujjlenyomattal történő Zárolásfeloldás**: Válasszon **blokk** megakadályozza, hogy a végfelhasználó számára az eszköz ujjlenyomat-olvasót használja az eszköz zárolásának feloldásához. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználó számára az eszközzárolás ujjlenyomattal történő használatával.
- **Smart Lock és más megbízhatósági ügynökök**: Válasszon **blokk** , hogy a Smart Lock és más megbízhatósági ügynökök módosíthassák a zárolási képernyő beállításai kompatibilis eszközökön. Ez a funkció, más néven bizalmi ügynök lehetővé teszi, hogy letiltását vagy megkerülését az eszköz zárolási képernyője jelszavának, ha az eszköz megbízható helyen van. Így például megkerülheti a munkahelyi profil jelszavát abban az esetben, ha egy adott Bluetooth-eszközhöz van csatlakoztatva, vagy egy bizonyos NFC-címke közelében van. Ezzel a beállítással letilthatja, hogy a felhasználók konfigurálják az intelligens zárolást.

### <a name="system-security"></a>Rendszerbiztonság

- **Alkalmazások fenyegetettségvizsgálata**: **Szükséges** érvényesíti a **alkalmazások ellenőrzése** beállítás engedélyezve van a munkahelyi és személyes profiloknál.

   > [!Note]
   > Ez a beállítás csak Android O vagy újabb rendszerű eszközök esetén érvényesül.

### <a name="connectivity"></a>Kapcsolat

- **Always-on VPN**: Válasszon **engedélyezése** egy VPN-ügyfél automatikusan csatlakozhat, és újból csatlakozik a virtuális Magánhálózat beállításához. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal elindítható, ha a felhasználó zárolja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. 

  A mindig bekapcsolt VPN beállítás az összes VPN-ügyfél számára való letiltásához válassza a **Nincs konfigurálva** lehetőséget.

  > [!IMPORTANT]
  > Egy eszközön egyszerre csak egy mindig bekapcsolt VPN-szabályzatot helyezzen üzembe. Több ilyen szabályzat üzembe helyezése egyetlen eszközön nem támogatott.

- **VPN-ügyfél**: Válassza ki a VPN-ügyfél, amely támogatja az Always On. A választható lehetőségek:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Hálózatok GlobalProtect
  - Pulse Secure
  - Egyéni
    - **Csomagazonosító**: Adja meg a Google Play áruházban az alkalmazás Csomagazonosítóját. Ha például az áruházban levő alkalmazás URL-címe `https://play.google.com/store/details?id=com.contosovpn.android.prod`, a csomagazonosító `com.contosovpn.android.prod` lesz.

  > [!IMPORTANT]
  >  - A kiválasztott VPN-ügyfelet az eszközön kell telepíteni, és támogatnia kell az alkalmazásonkénti VPN-t a munkahelyi profilokban. Ellenkező esetben hiba történik. 
  >  - A VPN-ügyfélalkalmazást jóvá kell hagynia a **felügyelt Google Play Áruházban**, szinkronizálnia kell az alkalmazást az Intune-nal, majd üzembe helyeznie az eszközön. Ezt követően az alkalmazás telepítve lesz a felhasználó munkahelyi profiljában.
  >  - Van Előfordulhat, hogy ismert problémák alkalmazásonkénti VPN az Android 3.0.4 F5 hozzáféréssel rendelkező használatakor. Lásd: [F5 kibocsátási megjegyzések az F5 Access for Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) további információt.

- **Zárolt módban**: Válasszon **engedélyezése** kényszerítése minden hálózati forgalmat a VPN-alagút használatához. Ha a VPN-kapcsolat nincs kiépítve, az eszköznek nem lesz hálózati hozzáférése.

  A **Nincs konfigurálva** beállítással a forgalom a VPN-alagúton vagy a mobilhálózaton is áthaladhat.

## <a name="next-steps"></a>További lépések

[Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).

Is létrehozhat dedikált eszköz teljes képernyős profilok [Android](device-restrictions-android.md#kiosk) és [Windows 10-es](kiosk-settings.md) eszközök.
