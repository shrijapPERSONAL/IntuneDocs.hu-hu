---
title: Eszközkorlátozási beállítások Windows 10 rendszerhez az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Megjelenítheti az összes beállítás és a hozzájuk tartozó leírások létrehozásához eszközkorlátozások Windows 10 és újabb rendszerű eszközök listáját. A konfigurációs profil ezek a beállítások segítségével szabályozhatja a képernyőfelvételt, jelszókövetelmények, a kioszkmód, a tárolóban, a Microsoft Edge böngészőt, a Windows defender-alkalmazások, a felhőbe, a start menüben, és több Microsoft Intune-ban.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8c62a9e6914402d65b215a1f722289bd5660b739
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728769"
---
# <a name="windows-10-and-newer-device-restriction-settings-in-microsoft-intune"></a>A Windows 10 (és újabb) eszköz eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune

Ez a cikk és az összes az eszközkorlátozási beállítások Windows 10 rendszerű eszközökhöz konfigurálható ismerteti. Ezek a beállítások hozzá eszközkonfigurációs profil, és ezután hozzárendelt vagy az eszközöket a Microsoft Intune segítségével telepítve.

> [!Note]
> Nem minden lehetőség áll rendelkezésre a Windows összes kiadásában

## <a name="general"></a>Általános

- **Képernyőfelvétel (csak mobil)**: lehetővé teszi, hogy a felhasználó rögzítheti képként a képernyőn.
- **Másolás és beillesztés (csak mobileszköz)**: másolás és beillesztés műveletek elvégzése az eszközön lévő alkalmazások engedélyezése.
- **Regisztráció manuális törlésének**: lehetővé teszi, hogy a felhasználó a munkahelyi fiók manuális törlését az eszközről.
  - A rendszer nem alkalmazza ezt a szabályzatbeállítást, ha a számítógép az Azure AD-hoz van csatlakoztatva, és engedélyezve van az automatikus regisztráció. 
  - A szabályzatbeállítás a Windows 10 Home rendszerű számítógépekre nem vonatkozik.
- **Főtanúsítvány manuális telepítése (csak mobil)**: megakadályozza a felhasználó legfelső szintű tanúsítványok és köztes szolgáltatói tanúsítványok manuális telepítése.

- **Kamera**: engedélyezi vagy letiltja az eszköz kamerájának használatát.
- **OneDrive-fájlszinkronizálás**: letiltja az eszköz szinkronizálja a fájlokat a onedrive-bA.
- **Cserélhető tároló**: Itt adhatja meg, hogy használható-e külső tárolóeszköz, például SD-kártya az eszközzel.
- **Földrajzi hely meghatározásának**: Itt adhatja meg, hogy az eszköz használhatja-e a helyalapú szolgáltatások adatait.
- **Internetkapcsolat megosztása**: az eszközön internetmegosztás használatának engedélyezése.
- **Telefon alaphelyzetbe állítása**: szabályozza, hogy a felhasználó visszaállíthatja-e a törlést az eszközön.
- **USB-kapcsolat (csak mobil)**: meghatározza, hogy eszköz hozzáférhet-e külső tárolóeszközöket USB-kapcsolaton keresztül.
- **Lopásgátló üzemmód (csak mobil)**: konfigurálja, hogy a Windows lopásgátló üzemmód engedélyezve van.
- **Cortana**: engedélyezi vagy letiltja a Cortana beszédfelismerési asszisztens.
- **Hangrögzítés (csak mobil)**: engedélyezi vagy letiltja az eszköz hangrögzítőjét.
- **Eszköznév módosításának**: megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz nevét (csak Windows 10 Mobile esetén)
- **Kiépítési csomagok hozzáadása**: letiltja a konfigurációs ügynök kiépítési csomagokat, amelyek a kiépítési csomagokat telepítsen.
- **Kiépítési csomagok eltávolítása**: letiltja a konfigurációs ügynök kiépítési csomagokat, amely eltávolítja a kiépítési csomagokat.
- **Eszközfelderítés**: letiltja az eszköz más eszközök általi felderíthetőségét.
- **Feladatváltó (csak mobil)**: letiltja a feladatváltót az eszközön.
- **SIM kártya hibát jelző párbeszédpanele (csak mobil)**: hibaüzenet megjelenítésének letiltása az eszközön, ha észlelhető SIM-kártya nem blokkolja.
- **Szabadkézi munkaterület**: letiltása a felhasználók hozzáférjenek a szabadkézi munkaterülethez. **Nincs konfigurálva** bekapcsolja az ink-munkaterületen, és a felhasználó számára engedélyezett, a zárolási képernyőn.
- **Automatikus újbóli üzembe helyezés**: lehetővé teszi, hogy törli az összes felhasználói adatot és beállítást rendszergazdai jogosultságokkal rendelkező felhasználóknak **CTRL + Win + R** , az eszköz zárolási képernyőjén. Ennek hatására automatikusan megtörténik az eszköz újbóli konfigurálása és regisztrálása felügyeletre.
- **Szeretne csatlakozni a hálózati eszköz telepítése (csak Windows Insider) során a felhasználók**: válassza a **megkövetelése** , az eszköz csatlakozik a hálózathoz, mielőtt folytatná a hálózat lap korábbi Windows 10-es telepítés során. Amíg ez a funkció előzetes verziójú, a beállítás használatához a Windows Insider 1809-es buildje, vagy annál újabb verzió szükséges.

## <a name="password"></a>Jelszó

- **Jelszó**: megköveteli a végfelhasználótól, adjon meg egy jelszót az eszköz elérésére.
  - **Kötelező jelszótípus**: meghatározza, hogy a jelszót kell numerikus csak, vagy számokat és.
  - **Jelszó minimális hossza**: csak Windows 10 Mobile vonatkozik.
  - **Bejelentkezési hibák eszköz törlése előtt**: Windows 10 rendszerű eszközök esetében: a BitLocker engedélyezve van az eszközön, ha azt van a BitLocker helyreállítási módjába jel után sikertelen a megadott hányszor. Ha az eszköz nincs engedélyezve a BitLocker, ez a beállítás nem vonatkozik. Windows 10 Mobile rendszerű eszközök esetében: után jelentkezzen be, hogy hányszor adja meg, hogy nem sikerül, a rendszer törölné az eszközt.
  - **Ennyi perc inaktivitás képernyőzárolás**: Megadja, mennyi ideig eszközt kell inaktívnak lennie a képernyő zárolása előtt.
  - **Jelszó érvényessége (napokban)**: Megadja, hogy mennyi idő elteltével meg kell megváltoztatni az eszköz jelszavát.
  - **Korábbi jelszavak újbóli használatának tiltása**: Itt adhatja meg a korábban használt jelszavak számát, amelyeket az eszköz által megjegyzett.
  - **Jelszó kérése, ha az eszköz visszatér inaktív állapotból (csak mobil)**: Itt adhatja meg, hogy a felhasználónak meg kell adnia egy jelszót az eszközön (csak Windows 10 Mobile esetén) zárolásának feloldásához.
  - **Egyszerű jelszavak**: lehetővé teszi egyszerű jelszavak, például 1111 vagy 1234 használatának engedélyezése. Ez a beállítás a Windows-képjelszavak használatát is engedélyezi vagy letiltja.
- **Titkosítási**: engedélyezze a titkosítást a megcélzott eszközökön.

## <a name="personalization"></a>Személyre szabás

- **Asztali háttérkép URL-címe (csak asztali verzióban)**: Adja meg a Windows asztali háttérképeként használandó JPEG formátumú kép URL-CÍMÉT. A felhasználók nem módosíthatják a képet.

## <a name="privacy"></a>Személyes adatok védelme

- **Bemenet személyre szabása**: használatát a Cortanához, diktáláshoz vagy a Microsoft Store apps felhőalapú beszédszolgáltatások. Ha engedélyezi ezeket a szolgáltatásokat, a Microsoft hangadatokat gyűjthet a szolgáltatás fejlesztéséhez.
- **A társításra és adatvédelemre vonatkozó felhasználói beleegyezést kérő automatikus elfogadása**: Windows lehetővé teszi, hogy automatikusan elfogadja a társítási és adatvédelmi beleegyezést kérő üzeneteket az alkalmazások futtatása közben.
- **Felhasználói tevékenységek közzététele**: **blokk** megakadályozza, hogy a megosztott élmények és a feladatváltóban nemrég használt erőforrások.
- **Csak a helyi tevékenységek**: **blokk** megakadályozza, hogy a megosztott élmények és a legutóbb használt erőforrások a feladatváltóban, csak a helyi tevékenység alapján.

Beállíthatja, hogy az eszközön lévő összes alkalmazás által elérhető információkat. Definiálhat kivételeket alkalmazásonként az **Alkalmazásonkénti adatvédelmi kivételek** segítségével.

### <a name="exceptions"></a>Kivételek

- **Fiókadatok**: határozza meg, hogy az alkalmazás hozzáférhet-e a felhasználónév, képéhez és egyéb kapcsolattartási adataihoz.
- **Háttérben futó alkalmazások**: határozza meg, hogy az alkalmazás futtatható-e a háttérben.
- **Naptár**: határozza meg, hogy az alkalmazás hozzáférhet-e a naptárhoz.
- **Híváslista**: határozza meg, hogy az alkalmazás hozzáférhet-e a hívási előzményekhez.
- **Kamera**: határozza meg, hogy az alkalmazás hozzáférhet-e a kamerához.
- **Névjegyek**: határozza meg, hogy az alkalmazás hozzáférhet-e a névjegyekhez.
- **E-mailek**: határozza meg, hogy ez az alkalmazás hozzáférhessen-e-mailt.
- **Hely**: határozza meg, hogy az alkalmazás hozzáférhet-e a helyadatokhoz.
- **Üzenetküldési**: határozza meg, hogy az alkalmazás olvashasson és küldhessen a szöveges vagy MMS-üzenetek.
- **Mikrofon**: határozza meg, hogy az alkalmazás használhat-e a mikrofont.
- **Mozgásérzékelő**: határozza meg, hogy az alkalmazás hozzáférhet-e eszköz mozgáskövetési adataihoz.
- **Értesítések**: határozza meg, hogy az alkalmazás hozzáférhet-e értesítéseket.
- **Telefonos**: határozza meg, hogy az alkalmazás hozzáférhet-e a telefonhoz.
- **Antennákhoz való**: egyes alkalmazások rádiófrekvenciás (például Bluetooth) az eszköz küldhet és fogadhat adatokat, és ezeket a rádiófrekvenciás kapcsolatokat kapcsolhatja be és ki kell. Megadhatja, hogy az alkalmazás kezelheti-e ezeket az antennákat.
- **Feladatok**: határozza meg, hogy az alkalmazás hozzáférhet-e a feladatokhoz.
- **Megbízható eszközök**: válassza ki, ha az alkalmazás használhat megbízható eszközök már csatlakoztatott hardverre vagy hardver, amely az eszköz is tartalmaz. Ha például használja televízióra, kivetítőkről, és így tovább megbízható eszközként.
- **Visszajelzés és diagnosztika**: válassza ki, ha az alkalmazás hozzáférhet-e diagnosztikai adatokat.
- **Szinkronizálás eszközökkel** – Megadhatja, hogy az alkalmazás oszthat-e meg és szinkronizálhat-e adatokat automatikusan olyan vezeték nélküli eszközökkel, amelyek nincsenek kifejezetten párosítva az adott PC-vel, táblagéppel vagy telefonnal.

## <a name="per-app-privacy-exceptions"></a>Alkalmazásonkénti adatvédelmi kivételek

Az egyes alkalmazásokhoz beállíthat az alapértelmezett adatvédelmi beállításoktól eltérő adatvédelmi működést.

- **Csomag neve**: alkalmazás csomagcsaládjának neve.
- **Alkalmazásnév**: az alkalmazás nevét.

### <a name="exceptions"></a>Kivételek

- **Fiókadatok**: határozza meg, hogy az alkalmazás hozzáférhet-e a felhasználónév, képéhez és egyéb kapcsolattartási adataihoz.
- **Háttérben futó alkalmazások**: határozza meg, hogy az alkalmazás futtatható-e a háttérben.
- **Naptár**: határozza meg, hogy az alkalmazás hozzáférhet-e a naptárhoz.
- **Híváslista**: határozza meg, hogy az alkalmazás hozzáférhet-e a hívási előzményekhez.
- **Kamera**: határozza meg, hogy az alkalmazás hozzáférhet-e a kamerához.
- **Névjegyek**: határozza meg, hogy az alkalmazás hozzáférhet-e a névjegyekhez.
- **E-mailek**: határozza meg, hogy ez az alkalmazás hozzáférhessen-e-mailt.
- **Hely**: határozza meg, hogy az alkalmazás hozzáférhet-e a helyadatokhoz.
- **Üzenetküldési**: határozza meg, hogy az alkalmazás olvashasson és küldhessen a szöveges vagy MMS-üzenetek.
- **Mikrofon**: határozza meg, hogy az alkalmazás használhat-e a mikrofont.
- **Mozgásérzékelő**: határozza meg, hogy az alkalmazás hozzáférhet-e eszköz mozgáskövetési adataihoz.
- **Értesítések**: határozza meg, hogy az alkalmazás hozzáférhet-e értesítéseket.
- **Telefonos**: határozza meg, hogy az alkalmazás hozzáférhet-e a telefonhoz.
- **Antennákhoz való**: egyes alkalmazások rádiófrekvenciás (például Bluetooth) az eszköz küldhet és fogadhat adatokat, és ezeket a rádiófrekvenciás kapcsolatokat kapcsolhatja be és ki kell. Megadhatja, hogy az alkalmazás kezelheti-e ezeket az antennákat.
- **Feladatok**: határozza meg, hogy az alkalmazás hozzáférhet-e a feladatokhoz.
- **Megbízható eszközök**: válassza ki, ha az alkalmazás használhat megbízható eszközök már csatlakoztatott hardverre vagy hardver, az eszköz. Ha például használja televízióra, kivetítőkről, és így tovább megbízható eszközként.
- **Visszajelzés és diagnosztika**: határozza meg, hogy az alkalmazás hozzáférhet-e diagnosztikai adatokat.
- **Szinkronizálás eszközökkel**: válassza ki, ha az alkalmazás automatikusan megoszthatja és szinkronizálhat-e olyan vezeték nélküli eszközökkel, amelyek nincsenek kifejezetten párosítva az eszköz az adatokat.

## <a name="locked-screen-experience"></a>Zárolási képernyő felülete

- **Műveletközpont értesítései (csak mobil)**: engedélyezi a Műveletközpont értesítéseinek megjelenését az eszköz zárolási képernyőjén (csak Windows 10 Mobile esetén).
- **Zárolt képernyőn kép URL-címe (csak asztali verzióban)**: Adja meg a Windows zárolási képernyőjének háttérképeként használt JPEG formátumú kép URL. Felhasználók nem módosíthatják ezt a beállítást.
- **Felhasználó által konfigurálható képernyő-időkorlát (csak mobil)**: lehetővé teszi a felhasználóknak idő beállítása 
- **Cortana zárolt képernyőn (csak asztali verzióban)**: nem engedélyezi a felhasználónak, a Cortana kommunikáljanak, ha az eszköz zárolási képernyőjén (csak Windows 10 asztali verzió).
- **Bejelentési értesítések zárolt képernyőn**: letiltása az eszköz zárolási képernyőjén ábrázoló értesítési üzeneteit.
- **Képernyő időkorlátja (csak mobil)**: Megadja azt az időtartamot másodpercben a képernyő zárolása után, amikor ki fog kapcsolni.

## <a name="app-store"></a>Alkalmazásáruház

- **Alkalmazás-áruház (csak mobil)**: engedélyezi vagy letiltja az alkalmazásáruházat a Windows 10 Mobile-eszközökön.
- **Áruházból származó alkalmazások automatikus frissítése**: lehetővé teszi, hogy a Microsoft Store automatikusan frissíteni kell a telepített alkalmazások.
- **Megbízható alkalmazás telepítése**: lehetővé teszi az alkalmazások közvetlen telepítését a megbízható tanúsítvánnyal aláírt.
- **Fejlesztői zárolás feloldása**: lehetővé teszi a Windows fejlesztői beállításait, például lehetővé teszi a végfelhasználók által módosítható a közvetlenül telepített alkalmazások.
- **Megosztott felhasználói alkalmazásadatok**: lehetővé teszi, hogy ugyanazon az eszközön a különböző felhasználók között adatokat megosztani alkalmazásokat.
- **Csak privát áruház használata**: engedélyezze a kizárólag a végfelhasználók számára a privát áruházból származó alkalmazásokat tölthetik le.
- **Store származó alkalmazások indítása**: minden olyan alkalmazás, amely előre telepítve az eszközön, vagy letölthető a Microsoft Store a letiltására szolgál.
- **Alkalmazásadatok telepítése a rendszerköteten**: leállítja az alkalmazások adatokat tároljanak az eszköz a rendszerköteten.
- **Alkalmazások telepítése a rendszermeghajtón**: leállítja az alkalmazások adatokat tároljanak az eszköz rendszermeghajtóján.
- **Játékvideó-rögzítő (csak asztali verzióban)**: megadható, hogy rögzítése és közvetítése játékok engedélyezett-e.
- **Csak áruházból származó alkalmazások**: konfigurálja, hogy a felhasználók telepíthetnek alkalmazásokat az app store intézményeknek portálon kívülről származó.

## <a name="microsoft-edge-browser"></a>Microsoft Edge böngésző

### <a name="start-experience"></a>Indítsa el a felhasználói élményt

- **Indítsa el a Microsoft Edge**: válassza ki, mely az oldalakat nyitja meg a Microsoft Edge indításakor. A választható lehetőségek:
  - **Indítsa el a lapok**: a Microsoft Edge az alapértelmezett start lap az operációs rendszer által definiált
  - **Új lap**: a Microsoft Edge betöltése akármilyen területen is definiálva van a **új lap URL-címe** beállítás
  - **Utolsó munkamenet oldal**: a Microsoft Edge betölti az utolsó munkamenet lap 
  - **Egyéni kezdőlap**: a Microsoft Edge betölti a rendszergazda által meghatározott úvodní stránku
- **A felhasználó megváltoztathatja a kezdőlapokat**: **engedélyezése** lehetővé teszi a felhasználók megváltoztassák az. A rendszergazdák használhatják a `EdgeHomepageUrls` , adja meg azon kezdőlapok, amelyeket a felhasználók alapértelmezés szerint amikor megnyitja a Microsoft Edge. **Nincs konfigurálva** letiltja a felhasználók módosítsák a kezdőlapokat.
- **Új lap URL-címe**: Adja meg az URL-cím, az új lap megnyitásához. Például írja be a következőt: `https://www.bing.com`.
- **Nyissa meg az új lapon jelenik meg a webes tartalom**: válasszon **letiltása** leállítani a Microsoft Edge megnyisson egy webhelyet egy új lapon. Le van tiltva, ha üres megnyitása új lapon. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett viselkedést az eszközön, amelyen lehetséges, hogy a felhasználók megjelenítendő elemek.
- **Kezdőlap gombjának**: válassza ki, mi történik, ha a kezdőképernyő gombra van kiválasztva. A választható lehetőségek:
  - **Indítsa el a lapok**: A választott beállítást a **indítsa el a Microsoft Edge-** megnyílik beállítása
  - **Új lap**: A választott beállítást a **új lap URL-címe** megnyílik beállítása
  - **Egyéni kezdőlap gombot URL-cím**: A választott beállítás a **gomb URL-cím otthoni** megnyílik beállítása
  - **Elrejtése kezdőképernyő gombra**: a kezdőlap gombjának elrejtése
- **A felhasználó megváltoztathatja a kezdőképernyő gombra**: **engedélyezése** lehetővé teszi a felhasználóknak, módosítsa a home gombra. A felhasználó módosításait felülbírálása bármely rendszergazdai beállításait a home gombra. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett viselkedést az eszközön, amelyek blokkolhatják a felhasználók nem módosíthatják, hogy a rendszergazda konfigurált home gombra.
- **Első futtatás élmény lap megjelenítése**: **blokk** leállítja a bemutató lap megjelenítését az első alkalommal futtatása a Microsoft Edge. Ez a funkció lehetővé teszi a vállalatok – például regisztrált nulla kibocsátási konfigurációkban blokkolja ezen a lapon. **Nincs konfigurálva** a bevezetés oldalt mutatja.
  - **Első futtatás élmény URL**: Adja meg az oldal URL-cím megjelenítéséhez egy felhasználó első alkalommal futtatja az Microsoft Edge (csak Windows 10 Mobile esetén).
- **Előugró ablakok**: válasszon **blokk** leállítani az előugró ablakokat a böngészőben. Csak a Windows 10 asztali verzióra vonatkozik. **Nincs konfigurálva** lehetővé teszi, hogy az előugró ablakokat a böngészőben.
- **Intranetes adatforgalom küldését az Internet Explorer**: **engedélyezése** lehetővé teszi a felhasználóknak az intranetes webhelyek megnyitását az Internet Explorer helyett a Microsoft Edge (csak Windows 10 asztali verzió). **Nincs konfigurálva** lehetővé teszi a felhasználóknak a Microsoft Edge használni.
- **Vállalati üzemmód webhelylistájának helye**: az URL-címét, amely tartalmazza a vállalati üzemmódban megnyíló webhelyek listája. Felhasználók nem módosíthatják ezt a listát. Csak a Windows 10 asztali verzióra vonatkozik.
- **Üzenet megnyitásakor webhelyek az Internet Explorer**: Ez a beállítás segítségével konfigurálhatja a Microsoft Edge az értesítések megjelenítése, mielőtt egy webhely megnyitása az Internet Explorer 11. A választható lehetőségek:
  - **Nincs konfigurálva**: az operációs rendszer alapértelmezett viselkedését használja, amely előfordulhat, hogy jelenjen meg egy üzenet.
  - **A Microsoft Edge-ben nyissa meg a helyek beállítás nélkül üzenet megjelenítése**: az üzenet megjelenítése, ha IE-ben. Nyissa meg a helyek Internet Explorer. Nem lehet beállítani a Microsoft Edge-ben nyissa meg a helyeket.
  - **Microsoft Edge-ben helyek üzenet megnyitásakor megjelenítése**: az üzenet megjelenítése, ha IE-ben. Az üzenet tartalmaz egy **folytathatja a munkát a Microsoft Edge-ben** hivatkozást, így a felhasználók eldönthetik, a Microsoft Edge helyett az Internet Explorer.

  > [!IMPORTANT]
  > Ez a beállítás megköveteli, hogy engedélyezze a **konfigurálása a vállalati üzemmód Webhelylistájának** beállítást, a **küldése az összes intranetes webhelyek az Internet Explorer 11** beállítás, vagy mindkét beállítást.

- **Microsoft kompatibilitási listájának**: **blokk** megakadályozza, hogy a Microsoft Edge-ben a Microsoft kompatibilitási listájának. A Microsoft ezen listája segítségével az Edge megfelelően tudja megjeleníteni az ismert kompatibilitási problémákkal rendelkező webhelyeket. **Nincs konfigurálva** lehetővé teszi, hogy a Microsoft kompatibilitási lista használatával.
- **Az előzetes betöltés kezdőlapokat és új lapot**: válasszon **letiltása** elkerülése érdekében konfigurálások a Microsoft Edge start lapokat és az új lapon. Betöltését minimalizálja a Microsoft Edge elindításához, és a egy új lap betöltése. **Nincs konfigurálva** az operációs rendszer alapértelmezett viselkedést, ezek az oldalak betöltésére, akkor használja.
- **Prelaunch kezdőlapokat és új lapot**: válasszon **blokk** megakadályozza, hogy a Microsoft Edge előre indítása a kezdőlapokat és új lapon. Előre indítása segít a Microsoft Edge teljesítményét, és minimálisra csökkenti a Microsoft Edge indításához szükséges időt. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett viselkedést, a prelaunch, akkor ezeket az oldalakat.

### <a name="favorites-and-search"></a>Kedvencek és keresés

- **Kedvencek sáv**: válassza ki, mi történik a Kedvencek sávra, bármely Microsoft Edge lapján. A választható lehetőségek:
  - **Nincs konfigurálva**: az lehet, ha el szeretné rejteni a Kedvencek sáv minden oldalon az operációs rendszer alapértelmezett viselkedést alkalmazza. Felhasználók módosíthatják ezt a beállítást.
  - **Elrejtése**: elrejti a Kedvencek sáv minden oldalon. Felhasználó nem módosíthatja ezt a beállítást.
  - **Megjelenítés**: minden oldalon a Kedvencek sáv mutatja. Felhasználó nem módosíthatja ezt a beállítást.
- **Kedvencek lista**: az URL-listák felvétele a Kedvencek fájl. Hozzáadhat például `http://contoso.com/favorites.html`.
- **Kedvencek módosításának korlátozása**: **blokk** , hogy a felhasználók hozzáadása, importálás, rendezés vagy szerkesztését a Kedvencek listájához. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely előfordulhat, hogy lehetővé teszi a felhasználóknak, hogy a listában.
- **Microsoft-böngészők között (csak asztali verzióban) Kedvencek szinkronizálása**: **megkövetelése** arra kényszeríti a Windows Internet Explorer és Microsoft Edge között a Kedvencek szinkronizálása. Kiegészítést, törlést, a módosítások és a sorrend változásait böngészők között vannak megosztva.  **Nincs konfigurálva** használ az operációs rendszer alapértelmezett, amelyet is biztosíthat a felhasználók számára a kiválasztott Kedvencek szinkronizálása a böngészők között.
- **Alapértelmezett keresőmotor**: válassza ki az eszközön az alapértelmezett keresőmotort. A végfelhasználók ezt az értéket bármikor módosíthatják. A választható lehetőségek:
  - Alapértelmezett
  - A Bing
  - Google
  - Yahoo
  - Egyéni érték
- **Keresési javaslatok**: **nincs konfigurálva** lehetővé teszi, hogy a keresőmotor webhelyeket javasoljon a keresőkifejezések beírása címet a címsorba. **Blokk** megakadályozza, hogy ez a funkció.

### <a name="privacy-and-security"></a>Adatvédelem és biztonság

- **InPrivate-böngészés**: **blokk** megakadályozza, hogy a végfelhasználók InPrivate-böngészési munkamenetet nyissanak. **Nincs konfigurálva** lehetővé teszi, hogy ez a funkció.
- **Mentse a böngészési előzmények**: **blokk** megakadályozza, hogy a Microsoft Edge mentése folyamatban van a böngészési előzményeket. **Nincs konfigurálva** a böngészési előzményeket mentésének engedélyezése.
- **Böngészési adatok kilépéskori (csak asztali verzióban) törlése**: **megkövetelése** előzmények és böngészési adatok, amikor a felhasználó bezárja a Microsoft Edge törli. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely előfordulhat, hogy gyorsítótárazza a böngészési adatok.
- **Szinkronizálja a böngésző beállításai között a felhasználó eszközei**: válassza ki, hogyan szeretné böngésző beállítások eszközök közötti szinkronizálása. A választható lehetőségek:
  - **Lehetővé teszi**: engedélyezése a Microsoft Edge böngésző beállításai között a felhasználó-eszköz szinkronizálása
  - **Letiltása és engedélyezése a felhasználó felülbírálás**: letiltása a Microsoft Edge böngésző beállításai között a felhasználó-eszköz szinkronizálása. Ezzel a beállítással a felhasználók felülbírálhatják.
  - **Blokk**: blokkolja a Microsoft Edge böngésző beállítás felhasználó eszközök közötti szinkronizálását. Felhasználók nem bírálja felül ezt a beállítást.
- **Jelszókezelő**: **blokk** letiltja a Microsoft Edge böngésző jelszókezelő szolgáltatását. **Nincs konfigurálva** lehetővé teszi, hogy ez a funkció.
- **A cookie-k**: válassza ki, hogyan kezelje a böngésző cookie-kat. A választható lehetőségek:
  - **Lehetővé teszi**: az eszközön tárolt cookie-kat.
  - **Az összes cookie blokkolása**: cookie-k sehol nincsenek tárolva az eszközön.
  - **Csak harmadik féltől származó cookie blokkolása**: harmadik féltől származó, vagy partner cookie-k sehol nincsenek tárolva az eszközön.
- **Automatikus kitöltés**: **blokk** letiltja az automatikus kitöltés funkciót az eszközön. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók számára a böngésző (csak Windows 10 asztali verzió) automatikus kiegészítési funkciója beállításainak módosítását.
- **"Do not track" fejlécek küldése**: **nincs konfigurálva** megköveteli az eszköz "do not track" fejlécek küldése (ajánlott) követési információkat kérő webhelyeknek. Válasszon **blokk** megakadályozza, hogy az eszköz küldése ezeket a fejléceket, amely lehetővé teszi a webhelyek nyomon követhetik a felhasználót.
- **WebRtc localhost IP-cím**: **blokk** megakadályozza, hogy a felhasználók localhost IP-cím jelenik meg a webes RTC protokoll telefonhívások kezdeményezésekor. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók localhost IP-cím jelennek meg a protokollt használó telefonhívások kezdeményezésekor.
- **Adatgyűjtés élő Csempéhez**: válasszon **blokk** Windows leállítja az adatgyűjtés a hely rögzítve van élő Csempét a start menüben, a Microsoft Edge-ből. **Nincs konfigurálva** lehetővé teszi, hogy ezt az információt kell gyűjteni.
- **Felhasználó felülbírálhatja a tanúsítványhibákat**: **blokk** megakadályozza, hogy a felhasználók hozzáférjenek a webhelyeket, amelyeket az SSL vagy TLS hibásak. **Nincs konfigurálva** lehetővé teszi, hogy a felhasználók hozzáférhessenek az ezeken a webhelyeken.

### <a name="additional"></a>További

- **A Microsoft Edge böngészőben (csak mobil)**: válasszon **blokk** , hogy a Microsoft Edge használata az eszközön. Ha letiltja a Microsoft Edge, az egyes beállítások csak asztali vonatkoznak. **Nincs konfigurálva** lehetővé teszi, hogy a Microsoft Edge böngésző az eszközön.
- **(Csak asztali verzióban) legördülő címsor**: **blokk** bemutató javaslatok listáját egy legördülő listában, amikor beírja a Microsoft Edge leáll. A funkció lehetővé teszi, hogy minimalizálja a Microsoft Edge és a Microsoft-szolgáltatások közötti hálózati sávszélességet. **Nincs konfigurálva** lehetővé teszi, hogy a Microsoft Edge a javaslatok listájának megtekintéséhez.
- **Teljes képernyős**: válasszon **blokk** csak a webes tartalom megjelenítése és elrejtése a Microsoft Edge (teljes képernyős mód) a Microsoft Edge elkerülése érdekében. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely lehetővé teszi, hogy a Microsoft Edge teljes képernyős mód használatára.
- **About: flags laphoz**: **blokk** megakadályozza, hogy a végfelhasználók hozzáférjenek a `about:flags` oldal, amely a fejlesztői és kísérleti beállításokat tartalmazza a Microsoft Edge-ben. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett, így fér hozzá a `about:flags` lapot.
- **Fejlesztői eszközök**: **blokk** megakadályozza, hogy a végfelhasználók megnyitása a Microsoft Edge fejlesztői eszközeit. **Nincs konfigurálva** lehetővé teszi a felhasználóknak nyissa meg a fejlesztői eszközöket.
- **Bővítmények**: **nincs konfigurálva** lehetővé teszi, hogy a végfelhasználók számára, hogy a Microsoft Edge-bővítményeket telepítsenek az eszközön. **Blokk** meggátolja a telepítést.
- **Közvetlen telepítési developer extensions**: **blokk** megakadályozza, hogy a Microsoft Edge közvetlen telepítést, amely telepíti és futtatja a nem ellenőrzött bővítmények használatával a **bővítmények betöltése** funkció. **Nincs konfigurálva** használ az operációs rendszer alapértelmezett beállítás, amely közvetlen telepítést lehetővé teheti.
- **Bővítmények szükséges**: válassza ki a Microsoft Edge-ben a végfelhasználók milyen kiterjesztésű nem kapcsolható ki. Adja meg a csomagcsaládok nevéről, és válassza ki **Hozzáadás**. [Keresse meg a csomagcsalád nevének (pfn Megkeresése)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) listák nyújt útmutatást.

  Emellett **importálás** CSV-fájl, amely tartalmazza a csomagcsaládok nevéről.

- **JavaScript**: válasszon **blokk** megakadályozza, hogy a Java-parancsfájlok a böngésző az eszközön. **Nincs konfigurálva** parancsprogramok, például Javascript, a Microsoft Edge böngészőben.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **A Microsoft Edge SmartScreen**: engedélyezze a Microsoft Edge SmartScreen webhely- és fájlletöltésekhez eléréséhez.
- **Rosszindulatú webhelyelérés**: felhasználók megakadályozása abban a Windows Defender SmartScreen szűrő figyelmeztetéseit, és letiltja a webhelyére.
- **Ellenőrizetlen fájlletöltés**: felhasználók megakadályozása abban a Windows Defender SmartScreen szűrő figyelmeztetéseit, és letiltja az ellenőrizetlen fájlok letöltésére.

## <a name="search"></a>Keresés

- **Biztonságos keresés (csak mobil)**: szabályozhatja, hogy Cortana hogyan szűrje a felnőtt tartalmat a keresési eredményekben. A megadható értékek a **Szigorú** és a **Közepes**, vagy engedélyezhető, hogy a végfelhasználó állítsa be az értékét.
- **Keresés webes eredményeinek megjelenítése**: letiltása vagy engedélyezése az eszközön kereséskor a webes találatokat.

## <a name="cloud-and-storage"></a>Felhő és tárolás

- **Microsoft-fiók**: lehetővé teszi, hogy a felhasználó Microsoft-fiókot társítson az eszközhöz.
- **Nem Microsoft-fiók**: lehetővé teszi a felhasználók e-mail fiókokat vegyen fel az eszközön, amelyek nem Microsoft-fiókhoz társítva.
- **Microsoft-fiók beállításszinkronizálása**: eszköz- és Alkalmazásbeállítások szinkronizálását az eszközök között Microsoft-fiókkal társított engedélyezése.

## <a name="cellular-and-connectivity"></a>Mobilhálózati és egyéb kapcsolatok

- **Mobilhálózati adatcsatorna**: állítsa le a felhasználók adathasználatát, például a webböngészést, amikor mobilhálózati elérését sem. 
- **Alkalmazásadat-barangolás**: adatok elérése közben hálózatok közötti barangolás engedélyezése.
- **Mobilhálózati VPN**: meghatározza, hogy az eszköz létesíthet-e VPN-kapcsolatot mobilhálózat használata esetén.
- **A mobilhálózati barangolás VPN**: szabályozza, hogy az eszköz létesíthet-e VPN-kapcsolatok, mobilhálózati roaming esetén.
- **Bluetooth**: meghatározza, hogy a felhasználó engedélyezése és az eszköz Bluetooth konfigurálásához.
- **Bluetooth-észlelhetőség**: észlelhetővé teszi az eszközt más Bluetooth-kompatibilis eszközök által.
- **Előzetes bluetooth-párosítás**: lehetővé teszi meghatározott Bluetooth-eszközök automatikus párosítását párosításuk konfigurálását.
- **Bluetooth-hirdetés**: lehetővé teszi, hogy az eszközök hirdetéseket fogadjanak Bluetooth-on keresztül.
- **Csatlakoztatott eszközök szolgáltatás**: kiválaszthatja, hogy a csatlakoztatott eszközök szolgáltatást, amely lehetővé teszi más Bluetooth-eszközök észlelését és engedélyezi-e.
- **NFC**: lehetővé teszi, hogy a felhasználó engedélyezze és konfigurálja az NFC-funkciók az eszközön.
- **Wi-Fi**: lehetővé teszi, hogy a felhasználó engedélyezze és konfigurálja a Wi-Fi (csak Windows 10 Mobile esetén) az eszközön.
- **Automatikus csatlakozás Wi-Fi elérési pontokhoz**: lehetővé teszi, hogy az eszköz automatikusan csatlakozni az ingyenes Wi-Fi elérési pontokhoz, és automatikusan elfogadja a és a feltételek a kapcsolathoz.
- **Manuális Wi-Fi konfigurációs**: azt szabályozza, a felhasználó konfigurálhat-e saját Wi-Fi kapcsolatokat, vagy lehet, ha csak egy Wi-Fi profil (csak Windows 10 Mobile esetén) által konfigurált kapcsolatokat használhatja azokat.
- **Wi-Fi-ellenőrzési időköz**: Adja meg, hogy milyen gyakran eszközök Wi-Fi-hálózatok keresése. Adjon meg egy 1 (leggyakoribb) és 500 (legritkább) közötti értéket.
- **Bluetooth-engedélyezett szolgáltatások**: Adja meg a hexadecimális karakterlánc, az engedélyezett Bluetooth-szolgáltatások és a profilok listáját.

## <a name="control-panel-and-settings"></a>Vezérlőpult és Gépház

- **Gépház alkalmazás**: a Windows gépház alkalmazás elérésének letiltása.
  - **Rendszer**: letiltja a hozzáférést a gépház alkalmazás rendszer területéhez.
    - **Energiagazdálkodási és alvási beállítások módosítása (csak asztali verzióban)**: megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz energiagazdálkodási és alvási beállításait.
  - **Eszközök**: letiltja a hozzáférést a gépház alkalmazás eszközök területéhez.
  - **Hálózat és Internet**: letiltja a hozzáférést a gépház alkalmazás hálózat és internet területéhez.
  - **Személyre szabás**: letiltja a hozzáférést a gépház alkalmazás személyre szabás területéhez.
  - **Fiókok**: letiltja a hozzáférést a gépház alkalmazás fiókok területéhez.
  - **Idő és nyelv**: letiltja a hozzáférést a gépház alkalmazás idő és nyelv területéhez.
    - **Rendszeridő módosítása**: megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz dátum és idő.
    - **Területi beállítások módosítása (csak asztali verzióban)**: megakadályozza, hogy a végfelhasználó megváltoztassa az eszköz területi beállításait.
    - **Nyelvi beállítások módosítása (csak asztali verzióban)**: e funkció felhasználó általi módosításának a nyelvi beállításokat az eszközön.
  - **Játékok**: letiltja a hozzáférést a beállítások alkalmazás játékok területéhez.
  - **Könnyű elérés**: letiltja a hozzáférést a gépház alkalmazás területén könnyű hozzáférést.
  - **Adatvédelmi**: letiltja a hozzáférést a gépház alkalmazás adatvédelem területéhez.
  - **Frissítés és biztonság**: letiltja a hozzáférést a frissítés és biztonság területéhez a gépház alkalmazásban.

## <a name="start"></a>Indítás

- **Start menü elrendezése**: testre szabhatja a start menüje olyan asztali eszközökön, feltölthet egy XML-fájlt, amely tartalmazza a testreszabásokat, többek között a sorrendben, az alkalmazások szerepelnek, és többet. Felhasználók nem módosíthatják a Start menü elrendezése, adja meg.
- **Rögzítheti a csempéket a webhelyek a Start menü**: olyan képek importálását, amely a Windows Start menü asztali eszközök hivatkozásokként jelennek meg a Microsoft Edge-ből.
- **Levétele a tálcáról alkalmazások**: válasszon **blokk** leállítja a felhasználó alkalmazásokat távolítson a Start menüből.
- **Gyors felhasználóváltás**: válasszon **blokk** egyidejűleg bejelentkezett kijelentkezés nélküli felhasználók közötti váltás elkerülése érdekében.
- **Legtöbbet használt alkalmazások**: válasszon **letiltása** elrejtése megjelenítése a start menüben a leggyakrabban használt alkalmazásokat. A Gépház alkalmazásban is letiltja a megfelelő váltógombot.
- **Nemrég hozzáadott alkalmazások**: válasszon **letiltása** megjelenítése a start menüből a nemrégiben hozzáadott alkalmazásokat elrejtése. A Gépház alkalmazásban is letiltja a megfelelő váltógombot.
- **Kezdőképernyő módja**: válassza ki, hogyan jelenik meg a kezdőképernyőn. Választhat a **Teljes képernyős** vagy a **Nem teljes képernyős** üzemmód között.
- **A legutóbb megnyitott elemek a Gyorslistákban**: válasszon **blokk** legutóbbi jump listák nem jelenik meg a start menüben és tálcán elrejtéséhez. A Gépház alkalmazásban is letiltja a megfelelő váltógombot.
- **Alkalmazáslista**: válassza ki, hogyan jelenik meg a gépház alkalmazásban. A választható lehetőségek: 
  - Összecsukás
  - A Gépház alkalmazás összecsukása és letiltása 
  - A Gépház alkalmazás eltávolítása és letiltása
- **Főkapcsoló**: válasszon **blokk** való megjelenítése a start menü főkapcsoló elrejtése.
- **Felhasználói csempe**: válasszon **blokk** elrejtése a megjelenítése a start menü felhasználói csempéjén.
  - **Zárolási**: válasszon **letiltása** elrejtése a `Lock` lehetőséget a start menü felhasználói csempéjén megjeleníthető.
  - **Jelentkezzen ki**: válasszon **blokk** elrejtése a `Sign out` lehetőséget a start menü felhasználói csempéjén megjeleníthető.
- **Leállítás**: válasszon **letiltása** elrejtése a `Update and shut down` és `Shut down` megjelenítése a start menü főkapcsoló elérhető beállításait.
- **Alvó állapotba**: válasszon **blokk** elrejtése a `Sleep` megjelenítése a start menü főkapcsoló lehetőségét.
- **Hibernálásra**: válassza a **letiltása** elrejtése a `Hibernate` megjelenítése a start menü főkapcsoló lehetőségét.
- **Váltás másik fiókra**: válasszon **blokk** elrejtése a `Switch account` csempére a felhasználók megjelenítése a start menüben.
- **Újraindítási lehetőségek**: válasszon **letiltása** elrejtése a `Update and restart` és `Restart` megjelenítése a start menü főkapcsoló elérhető beállításait.
- **Dokumentumok a Start menüben**: a Windows Start menü Dokumentumok mappájának megjelenítése vagy elrejtése.
- **Letöltések a Start menüben**: a Windows Start menü letöltések mappájának megjelenítése vagy elrejtése.
- **Fájlkezelő a Start**: a fájlkezelő alkalmazást a Windows Start menü megjelenítése vagy elrejtése.
- **Otthoni csoport a Start**: a Windows Start menü otthoni csoport mappájának megjelenítése vagy elrejtése.
- **Zene a Start menüben**: a Windows Start menü zene mappájának megjelenítése vagy elrejtése.
- **Hálózat a Start menüben**: a Windows Start menü hálózat mappájának megjelenítése vagy elrejtése.
- **Személyes mappa a Start menüben**: a Windows Start menü személyes mappájának megjelenítése vagy elrejtése.
- **Képek a Start menüben**: a Windows Start menü képeket tartalmazó a mappájának megjelenítése vagy elrejtése.
- **Gépház a Start menüben**: a beállítások alkalmazást a Windows Start menü megjelenítése vagy elrejtése.
- **Videók a Start menüben**: a Windows Start menü videókat tartalmazó mappájának megjelenítése vagy elrejtése.

## <a name="display"></a>Megjelenítés

- **GDI-méretezés bekapcsolása az alkalmazásoknál**
- **GDI-méretezés kikapcsolása az alkalmazásoknál**

  A GDI DPI-méretezés lehetővé teszi, hogy alkalmazásokat, amelyek a nem DPI figyelembe /-figyelő DPI tisztában lesz. Adja meg az örökölt alkalmazásokat, a GDI DPI-méretezés van kapcsolva. A GDI DPI-méretezés bekapcsolása és kikapcsolása alkalmazás konfigurálva, a méretezés ki van kapcsolva az alkalmazáshoz.

## <a name="kiosk-preview---obsolete"></a>Kioszk (Előzetes) – Elavult

Ezek a beállítások csak olvashatók, és nem módosíthatók. A kioszkmód a [Kioszkbeállítások Windows 10 vagy újabb rendszerekhez](kiosk-settings.md) lehetőség használatával konfigurálható.

A kioszkeszközök jellemzően egyetlen alkalmazást futtatnak, vagy az alkalmazások egy előre meghatározott készletét. A rendszer megakadályozza más funkcióinak és az eszköz hozzáférését.

- **Teljes képernyős mód**: azonosítja a szabályzat által támogatott teljes képernyős mód típusát. A lehetőségek a következők:

  - **Nincs konfigurálva** (alapértelmezett): A szabályzat nem teszi lehetővé az eszköz kioszkmódjában.
  - **Egyalkalmazásos kioszk**: A profil engedélyezi az eszköznek csak egyetlen alkalmazás futtatását. Amikor a felhasználó bejelentkezik, elindul az adott alkalmazás. Ez a mód emellett meggátolja a felhasználót abban, hogy új alkalmazásokat nyisson meg vagy másik futó alkalmazásra váltson.
  - **Többalkalmazásos kioszk**: A profil engedélyezi az eszköz számos alkalmazás futtatásához. Csak a hozzáadott alkalmazások lesznek elérhetők a felhasználónak. A többalkalmazásos kioszk (vagy fix célú eszköz) előnye az, hogy egy olyan, könnyen érthető környezetet nyújt a felhasználónak, amely csak a szükséges alkalmazások elérését engedélyezi, a többi alkalmazást pedig elrejti a felhasználó elől.

#### <a name="single-app-kiosks"></a>Egyalkalmazásos kioszk

Adja meg a következő beállításokat:

- **Felhasználói fiók**: Adja meg a helyi (eszközön létező) felhasználói fiók, egy AD-tartományi fiók vagy a teljes képernyős alkalmazáshoz társított Azure AD-fiókkal.
  - Helyi fiók: Adja meg így: `devicename\accountname`, `.\accountname` vagy `accountname`
  - Tartományi fiók: Adja meg így: `domain\accountname`
  - Azure AD-fiók: Adja meg így: `AzureAD\emailaddress`. Ügyeljen rá, hogy „AzureAD”-ként adja meg, mivel ez egy rögzített tartománynév. Ezt követően adja meg az Azure AD e-mail-címét. Például írja be a következőt: `AzureAD\user@contoso.onmicrosoft.com`.

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha kioszk módhoz Azure AD-fiókot használ, ügyeljen rá, hogy ezt írja be: `AzureAD\user@yourorganization.com`.

- **Alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID) alkalmazás**: Adja meg a teljes képernyős alkalmazás alkalmazásfelhasználói modellben használt AZONOSÍTÓJÁT. További információkat a [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Telepített alkalmazás alkalmazásfelhasználói modellben használt azonosítójának megkeresése) című témakörben találhat.

#### <a name="multi-app-kiosks"></a>Többalkalmazásos kioszk

A [többalkalmazásos kioszkeszközök](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) olyan kioszkkonfigurációt használnak, amely más beállítások mellett tartalmazza az engedélyezett alkalmazások listáját. 

Hozzon létre egy kioszkkonfigurációt a **Hozzáadás** gomb használatával (vagy válasszon egy meglévőt). Ezután adja meg a következő beállításokat:

- **Kioszkkonfiguráció neve**: Adja meg a konfiguráció azonosítására szolgáló felhasználóbarát nevet.

- **Teljes képernyős alkalmazás**: Adja meg a Start menüben elérhető alkalmazásokat. A felhasználó kizárólag a megadott alkalmazásokat fogja tudni elérni.

  - **Alkalmazás típusa**: válassza ki a teljes képernyős alkalmazás típusát:
    - **Win32-alkalmazás**: hagyományos asztali alkalmazás. A futtatható fájlnak az eszközön érvényes teljes elérési útja szükséges.
    - **UWP-alkalmazás**: egy univerzális Windows-alkalmazást. [Az alkalmazás alkalmazásfelhasználói modellben használt azonosítója (AUMID)](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) szükséges.

  - **Azonosító**: a végrehajtható fájl (Win32-alkalmazás), adja meg a teljes elérési útjával, vagy a [alkalmazás AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP-alkalmazások).

- **Tálca** – Válassza az **Engedélyezés** beállítást a tálca megjelenítéséhez, vagy hagyja meg az alapértelmezett **Nincs konfigurálva** beállítást a tálca kioszkeszközön való elrejtéséhez.

- **Start menü elrendezése**: Adjon meg egy XML-fájlt, amely azt ismerteti, hogyan jelenjenek meg az alkalmazások a Start menüben. A [Start menü elrendezésének testreszabása és exportálása](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) című cikkben találhat útmutatást és XML-mintát.

  [Alkalmazások futtatása Windows 10 rendszerű kioszk létrehozása](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) használatával és XML-fájlok létrehozásáról további információt talál.

- **Hozzárendelt felhasználók**: egy vagy több felhasználói fiókot, amellyel a hozzáadott alkalmazások. A fiókkal való bejelentkezéskor csak a konfigurációban meghatározott alkalmazások érhetők el. Ez lehet egy helyi fiók az eszközön, vagy egy Azure AD-fiók, amely a teljes képernyős alkalmazáshoz van társítva.

    Nyilvános környezetben működő, automatikus bejelentkezésű kioszkeszköz esetében ajánlott a legalacsonyabb szintű hozzáféréssel rendelkező felhasználótípust (például egyszerű helyi felhasználó fiókot) választania. Ha Azure Active Directory- (AD-) fiókot kíván konfigurálni a kioszkmódhoz, használja az `domain\user@tenant.com` formátumot.

## <a name="windows-defender-antivirus"></a>Windows Defender víruskereső

- **Valós idejű figyelés**: engedélyezi a kártevők, kémprogramok és más nemkívánatos szoftverek valós idejű vizsgálatát.
- **Viselkedésfigyelés engedélyezése**: engedélyezi a Defender ellenőrzés gyanús tevékenységekre utaló ismert mintákat keressen az eszközökön.
- **Hálózatvizsgáló rendszer (NIS)**: NIS segít megvédeni az eszközöket a hálózatalapú biztonsági rések ellen. A Microsoft Endpoint Protection-központból származó ismert sebezhető pontok mintázatai alapján segít észlelni és blokkolni a rosszindulatú hálózati forgalmat.
- **Minden letöltött fájl vizsgálata**: szabályozza, hogy a Defender megvizsgálja az internetről letöltött összes fájlt.
- **Microsoft-webböngészőkben betöltött szkriptek vizsgálata**: az Internet Explorer által használt engedélyezi a Defender vizsgálat parancsfájlok.
- **Végfelhasználói hozzáférés a Defenderhez**: meghatározza, hogy a végfelhasználók a Windows Defender kezelőfelülete rejtett. Módosítás esetén a beállítás a felhasználó számítógépének következő újraindításakor lép érvénybe.
- **Aláírás-frissítési időköz (óra)**: Adja meg, melyik Defender ellenőrzi időközönként keressen új aláírásfájlokat.
- **Fájl- és programtevékenység figyelése**: engedélyezi a Defender számára a fájl- és programtevékenység figyelése a eszközök.
- **Ennyi nap után törlődjenek karanténba zárt kártevők**: engedélyezi a Defender ártalmatlanított kártevő szoftverek követése, így manuálisan lehessen ellenőrizni a megadott napok száma korábban érintett eszközök továbbra is. Ha a napok száma **0**, kártevő a karanténban marad, és nem törlődik automatikusan.
- **CPU-használati korlát ellenőrzés közben**: lehetővé teszi, hogy korlátozza a CPU, a használata engedélyezett (a **1** való **100**).
- **Archív fájlok ellenőrzése**: engedélyezi a Defender számára az archív fájlok – például .zip- vagy .cab-fájlok vizsgálata.
- **A bejövő e-mailek vizsgálata**: lehetővé teszi, hogy a Defender számára e-mailek azonnali vizsgálatát az eszközön.
- **Cserélhető adathordozók vizsgálata teljes vizsgálat során**: engedélyezi a Defender számára a cserélhető meghajtók, például a pendrive.
- **Csatlakoztatott hálózati meghajtók vizsgálata teljes vizsgálat során**: engedélyezi a Defender vizsgálat fájlokat a csatlakoztatott hálózati meghajtókon.
  Ha a meghajtó a fájlok írásvédettek, a Defender nem távolítható el a bennük talált kártevőket.
- **Hálózati mappákból megnyitott fájlok vizsgálata**: engedélyezi a Defender vizsgálati fájlok a megosztott hálózati meghajtókon (például UNC elérési úton elért fájlok). Ha a meghajtó a fájlok írásvédettek, a Defender nem távolítható el a bennük talált kártevőket.
- **A felhő védelmi**: engedélyezi vagy letiltja a Microsoft Active Protection Service számára a kártevőkről információt kap a felügyelt eszközök. Ezek az adatok a szolgáltatás további fejlesztésére szolgálnak.
- **Rákérdezés a mintaküldés előtt**: e vélhetően kártevő fájlokat, előfordulhat, hogy amelyeken további vizsgálat szükséges vezérlők a rendszer automatikusan elküldje a Microsoftnak.
- **Napi Gyorsvizsgálat időpontja**: lehetővé teszi, hogy időben napi Gyorsvizsgálat ütemezett választja.
- **Rendszervizsgálat típusa**: amikor rendszervizsgálat ütemezése futtatott vizsgálata szintjét adja meg.
- **Vélhetően nemkívánatos alkalmazások észlelése**: válassza ki a védelmi szintet, ha a Windows észleli a vélhetően nemkívánatos alkalmazások:
  - **Tiltás**
  - **Naplózási** vélhetően nemkívánatos alkalmazásokkal kapcsolatos további információkért lásd: [észlelése és a blokk vélhetően nemkívánatos alkalmazások](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Kártevők észlelése műveletek**: használja ezt a beállítást válassza ki a műveleteket, amelyeket a Defender milyen fenyegetési szinteken (alacsony, közepes, magas és súlyos) észlel. A választható lehetőségek:
  - **Tisztítás**
  - **Karantén**
  - **Eltávolítás**
  - **Engedélyezés**
  - **Felhasználó által definiált**
  - **Tiltás**

### <a name="windows-defender-antivirus-exclusions"></a>Windows Defender víruskereső – kizárások

- **Fájlok és mappák kizárása a vizsgálatokból és a valós idejű védelem**: hozzáad egy vagy több fájlok és mappák – például **C:\Path** vagy **%ProgramFiles%\Path\filename.exe** a kivételek listájára. A rendszer a valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a fájlokat és mappákat.
- **A vizsgálatokból és a valós idejű védelemből kizárandó fájlkiterjesztések**: Adjon hozzá egy vagy több fájlkiterjesztéseket – például **jpg** vagy **txt** a kivételek listájára. A valós idejű és ütemezett vizsgálatok során nem vizsgálja az ilyen kiterjesztésű fájlokat.
- **A vizsgálatokból és a valós idejű védelemből kizárandó folyamatok**: Adjon hozzá egy vagy több kívánt típusú folyamatok **.exe**, **.com**, vagy **.scr** a kivételek listájára. A valós idejű és ütemezett vizsgálatok során nem vizsgálja ezeket a folyamatokat.

## <a name="network-proxy"></a>Hálózati proxy

- **Proxybeállítások automatikus észlelése**: Amikor engedélyezve van, az eszköz megpróbálja megkeresni egy PAC-szkript elérési útját.
- **Proxyparancsfájl használata**: válassza ezt a lehetőséget, adjon meg útvonalat kell konfigurálni a proxykiszolgáló PAC-szkript.
  - **Beállítási parancsfájl URL-címe**: Adja meg a proxykiszolgáló konfigurálásához használni kívánt PAC-szkript URL-CÍMÉT.
- **Manuális proxykiszolgáló használata**: válassza ezt a beállítást, manuálisan adja meg a proxykiszolgálóra vonatkozó információkat.
  - **Cím**: Adja meg a nevét, vagy a proxykiszolgáló IP-cím.
  - **Portszám**: Adja meg a proxykiszolgáló portszámát.
  - **Proxyhasználat alóli kivételek**: minden olyan URL-címeket, amelyek nem használhatják a proxykiszolgálót. Az egyes címeket pontosvesszővel választhatja el egymástól.
  - **Proxykiszolgáló kihagyása helyi cím esetén**: használni a proxykiszolgálót az intranet helyi címeinél nem szeretné, ha engedélyezi ezt a beállítást.

## <a name="windows-spotlight"></a>Windows Reflektorfény

- **Windows reflektorfény**: használja ezt a beállítást az összes Windows reflektorfény-funkciót a Windows 10-eszközök blokkolására. Ha letiltja ezt a beállítást, a következő beállítások nem érhetők el:
  - **Windows reflektorfény a zárolási képernyőn**: állítsa le Windows reflektorfény információt jelenítsen meg az eszköz zárolási képernyőjén a.
  - **Harmadik féltől származó javaslatok a Windows Reflektorfényben**: Windows reflektorfény állítsa le a nem Microsoft által közzétett jelenítsen.
  - **Fogyasztói funkciók**: letilthatja az olyan fogyasztói funkciókat, mint a Start menü javaslatai vagy a tagsági értesítések.
  - **Windows-tippek**: beállítással letilthatja az előugró tippek Windows megjelenítését.
  - **Windows reflektorfény a Műveletközpontban**: Block Windows reflektorfény-javaslatok, például új alkalmazásról vagy biztonsági tartalomról, Windows Műveletközpontban parancsot.
  - **Windows reflektorfény személyre szabása**: leállítja Windows reflektorfény személyre szabja az eredményeket az eszköz használata alapján.
  - **Windows-üdvözlőképernyőn**: letiltja a Windows üdvözlőprogramjának, amely az új vagy frissített funkciók felhasználói információkat tekinthet meg.

## <a name="projection"></a>Kivetítés

- **Felhasználói bevitel vezeték nélküli kijelzők vevőegységeiről**: letiltja a felhasználói bevitel vezeték nélküli kijelzők vevőegységeiről.
- **Kivetítés erre a számítógépre**: leállítja a Számítógépet kivetítéshez találjanak más eszközök.
- **PIN-kód kérése párosításhoz**: a PIN-kód megkövetelése vetítőeszközhöz való csatlakozáskor.

## <a name="cloud-printer"></a>Felhőbeli nyomtató

- **Nyomtató-felderítési URL-cím**: Adja meg az URL-cím keresése a felhőbeli nyomtatók.
- **Nyomtató hozzáférés szolgáltató URL-címe**: Adja meg a hitelesítési végpont URL-címe, az OAuth-jogkivonatok beolvasásához. Például: `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **Azure-beli natív ügyfélalkalmazás GUID**: Adja meg a szolgáltatótól OAuth-jogkivonatok kérhető ügyfélalkalmazás GUID-ja.
- **Nyomtatási szolgáltatás erőforrás-URI**: Adja meg a nyomtatási szolgáltatás az Azure Portal webhelyen konfigurált OAuth erőforrás URI azonosítója. Például: `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **(Csak mobil) lekérdezendő nyomtatók maximális száma**: Adja meg a lekérdezni kívánt nyomtatók maximális számát. Például írja be a következőt: `10`.
- **Nyomtatófelderítési szolgáltatás erőforrás URI**: Adja meg az OAuth-erőforrás URI-nyomtató discovery szolgáltatás beállítása az Azure Portalon. Például: `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Miután beállította a [Windows Serverhez a hibrid felhőnyomtatást](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), konfigurálhatja ezeket a beállításokat, majd telepítheti Windows rendszerű eszközökre.

## <a name="local-printer"></a>Helyi nyomtató

- **Nyomtatók**: hozzáadott helyi nyomtatók listája.
- **Alapértelmezett nyomtató**: az alapértelmezett nyomtató beállítása.
- **Felhasználói hozzáférés új nyomtatók hozzáadásához**: engedélyezi vagy letiltja a helyi nyomtatók.

## <a name="reporting-and-telemetry"></a>Jelentéskészítés és telemetria

- **Használati adatok megosztása**: válassza ki a diagnosztikai adatok beküldése szintet. A választható lehetőségek:
  - Biztonság
  - Egyszerű
  - Továbbfejlesztett
  - Összes
- **Böngészési adatok Microsoft 365 Analytics a Microsoft Edge küldése**: Ez a funkció használatához állítsa a **használati adatok megosztása** beállítások **bővített** vagy **teljes**. Ez a funkció szabályozza, mely adatok Microsoft Edge Microsoft 365 Analytics küld a vállalati eszközöknél a beállított kereskedelmi azonosítót. A választható lehetőségek:
  - **Nincs konfigurálva**: az operációs rendszer alapértelmezett beállítás, amely előfordulhat, hogy ne küldjön böngészési előzmények adatokat használ.
  - **Csak az intranetes adatok küldése**: lehetővé teszi a rendszergazdák küldése intranetes adatok előzményei
  - **Csak internetes adatküldés**: lehetővé teszi a rendszergazdák küldése az internet-adatok előzményei
  - **Intranetes és internetes adatküldés**: lehetővé teszi a rendszergazdák küldése az intranetes és internetes adatok előzményei
- **Telemetria proxykiszolgálója**: Adja meg a teljesen minősített tartománynevét (FQDN) vagy az összekapcsolt felhasználói élmények és Telemetria kérelmek, a Secure Sockets Layer (SSL)-kapcsolat használatával továbbítsa a proxykiszolgáló IP-címét. a következő formátumban: *kiszolgáló*:*port*. Ha az elnevezett proxy meghibásodik, vagy ha ez a szabályzat engedélyezve van a megadott proxy nem létezik, az összekapcsolt felhasználói élmények és Telemetria-adatokat nem érkezik meg, és a helyi eszközön marad.

  Példák a formátumra:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="messaging"></a>Üzenetkezelés

- **Üzenetszinkronizálás (csak mobil)**: letiltja az üzenetek mindenhol és SMS-üzenet biztonsági mentését és visszaállítását.
- **MMS (csak mobilon)**: az eszközön az MMS küldése/fogadása funkció letiltása.
- **RCS (csak mobil)**: az eszközön a gazdag kommunikációs szolgáltatások küldése/fogadása funkció letiltása.

## <a name="more-information"></a>További információ

További technikai részleteket az egyes beállításokról és a Windows támogatott kiadásairól a [Windows 10 szabályzatkonfigurációs szolgáltatói referenciájában](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) talál.
