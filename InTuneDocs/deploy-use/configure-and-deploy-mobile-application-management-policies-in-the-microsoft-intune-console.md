---
title: "MAM-szabályzatok konfigurálása az Intune-konzolban | Microsoft Docs"
description: "A Microsoft Intune mobilalkalmazás-felügyeleti szabályzatai lehetővé teszik a telepített alkalmazások funkcióinak módosítását, ezzel segítenek elérni, hogy azok összhangba kerüljenek vállalata megfelelőségi és biztonsági szabályzataival."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: f7504657f5fb2d73242f25f2f059c8c4e7ab1547
ms.lasthandoff: 12/30/2016


---

# <a name="configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console"></a>Configure and deploy mobile application management policies in the Microsoft Intune console

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune mobilalkalmazás-felügyeleti (MAM) szabályzatai lehetővé teszik a telepített alkalmazások funkcióinak módosítását, ezzel segítenek elérni, hogy azok összhangba kerüljenek vállalata megfelelőségi és biztonsági szabályzataival. Például korlátozhatja a felügyelt alkalmazások kivágási, másolási és beillesztési műveleteit, vagy konfigurálhat egy alkalmazást arra, hogy az összes webes hivatkozás egy felügyelt böngészőben nyíljon meg.

A mobilalkalmazás-kezelési házirendek a következőket támogatják:

-   Az Android 4-es vagy újabb verzióját futtató eszközök

-   Az iOS 8.0-s vagy újabb verzióját futtató eszközök

> [!TIP]
> A mobilalkalmazás-kezelési szabályzatok az Intune-ban regisztrált eszközökre alkalmazhatók.
>
> Ha a nem az Intune által felügyelt eszközökre vonatkozóan szeretne alkalmazásfelügyeleti szabályzatokat létrehozni, olvassa el a következő cikket: [Alkalmazásadatok védelme mobilalkalmazás-kezelési szabályzatokkal a Microsoft Intune segítségével](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Az Intune más szabályzataitól eltérően a mobilalkalmazás-kezelési szabályzatok alkalmazása nem közvetlenül történik, hanem úgy, hogy a házirendet társítja a korlátozni kívánt alkalmazással. Az alkalmazás központi és az eszközökön való telepítése után az Ön által megadott beállítások lépnek életbe.

Ahhoz, hogy korlátozásokat lehessen alkalmazni egy alkalmazásra, az alkalmazásnak tartalmaznia kell a Microsoft Intune App SDK-t. Ilyen típusú alkalmazást az alábbi három módszerrel lehet beszerezni:

-   **Szabályzat által felügyelt alkalmazás használata**. Ezek az alkalmazások beépített App SDK-val rendelkeznek. Ilyen típusú alkalmazások hozzáadásához meg kell adnia az alkalmazás hivatkozását egy alkalmazás-áruházból, például az iTunes vagy Google Play áruházból. Az ilyen típusú alkalmazáshoz nincs szükség további feldolgozásra. További információt [a Microsoft Intune mobilalkalmazás-felügyeleti szabályzataival használható alkalmazások listájában](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) találhat.

-   **Becsomagolt alkalmazás használata**. A becsomagolt alkalmazások abból a célból lettek újracsomagolva a Microsoft Intune alkalmazásburkoló eszközével, hogy tartalmazzák az App SDK-t. Ezt az eszközt általában a házon belül létrehozott vállalati alkalmazások feldolgozásához használják, az alkalmazásáruházból letöltött alkalmazások feldolgozásához nem használható. További információ: [iOS-alkalmazások mobilalkalmazás-kezeléshez való előkészítése a Microsoft Intune alkalmazásburkoló eszközével](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) és [Android-alkalmazások előkészítése mobilalkalmazás-felügyelethez a Microsoft Intune alkalmazásburkoló eszközével](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Saját, az Intune App SDK-t tartalmazó alkalmazás írása**. Az Intune App SDK lehetővé teszi alkalmazásfelügyeleti funkciók beépítését a készülő alkalmazásokba. További információ: [Az Intune App SDK áttekintése](/intune/develop/intune-app-sdk).

Ha segítségre van szüksége az alkalmazásburkoló eszköz és az Intune App SDK közötti választáshoz, olvassa el a következő cikket: [Annak eldöntése, hogyan készíti elő az alkalmazásokat a mobilalkalmazás-kezeléshez a Microsoft Intune-nal](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

Néhány felügyelt alkalmazás, például az iOS és az Android rendszerhez készült Outlook támogatja a *többszörös identitást*. Ez azt jelenti, hogy az Intune csak az alkalmazásban lévő vállalati fiókokra vagy adatokra alkalmazza a felügyeleti beállításokat.

Az Outlook alkalmazás használata esetén például:

-   Ha a felhasználó egy vállalati és egy személyes e-mail-fiókot konfigurál, az Intune csak a vállalati fiókra alkalmazza a felügyeleti beállításokat, és a személyes fiókot nem felügyeli.

-   Az eszköz kivonása vagy a regisztráció megszüntetése esetén a rendszer csak a vállalati Outlook-adatokat távolítja el az eszközről.

-   A vállalati fióknak egyeznie kell azzal a fiókkal, amelyet az eszköz az Intune-nal végzett regisztrációhoz használt.

> [!TIP]
> Ha a Configuration Managerrel használja az Intune-t, olvassa el az [Alkalmazások vezérlése mobilalkalmazás-felügyeleti szabályzatokkal a Configuration Managerben](https://technet.microsoft.com/library/mt131414.aspx) című témakört.

## <a name="create-and-deploy-an-app-with-a-mobile-application-management-policy"></a>Alkalmazás létrehozása és telepítése mobilalkalmazás-kezelési házirenddel

-   **1. lépés:** Hivatkozás beszerzése egy házirend által kezelt alkalmazáshoz, becsomagolt alkalmazás létrehozása, vagy az Intune App SDK használata MAM-kompatibilis alkalmazások írásához.

-   **2. lépés:** Az alkalmazás közzététele a felhőalapú tárhelyén.

-   **3. lépés:** Mobilalkalmazás-kezelési házirend létrehozása.

-   **4. lépés:** Az alkalmazás társítása egy mobilalkalmazás-felügyeleti szabályzattal, majd az alkalmazás telepítése.

-   **5. lépés:** Az alkalmazás telepítésének figyelése.

## <a name="step-1-get-the-link-to-a-policy-managed-app-create-a-wrapped-app-or-use-the-intune-app-sdk-to-write-a-mam-enabled-app"></a>1. lépés: Hivatkozás beszerzése egy szabályzat által felügyelt alkalmazáshoz, becsomagolt alkalmazás létrehozása, vagy az Intune App SDK használata MAM-kompatibilis alkalmazások írásához

Az alkalmazásáruházban keresse meg és jegyezze fel a telepíteni kívánt, szabályzat által felügyelt alkalmazásnak az URL-címét. Az iPadhez készült Microsoft Word alkalmazás URL-címe például a következő: **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## <a name="step-2-publish-the-app-to-your-cloud-storage-space"></a>2. lépés: Az alkalmazás közzététele a felhőalapú tárhelyen
Amikor közzétesz egy felügyelt alkalmazást, az eljárások különbözhetnek attól függően, hogy az alkalmazás szabályzat által felügyelt-e, vagy olyan alkalmazás, amelynek a feldolgozása a Microsoft Intune iOS rendszerhez készült alkalmazásburkoló eszközével történt.

#### <a name="to-publish-a-policy-managed-app"></a>Házirend által kezelt alkalmazás közzététele

1.  Ha készen áll rá, hogy feltöltse az alkalmazást a felhőtárhelyre, járjon el a következő cikk utasításai szerint: [Alkalmazások hozzáadása Microsoft Intune-beli mobileszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  iOS-alkalmazások esetén válassza a **Felügyelt iOS-alkalmazás az App Store-ból** lehetőséget a **Válassza ki, hogyan szeretné elérhetővé tenni ezt a szoftvert az eszközök számára** csoportban.

    Android-alkalmazások esetén válassza a **Külső hivatkozás**lehetőséget.

3.  Az **URL-cím megadása**csoportban írja be a házirend által kezelt alkalmazás korábban feljegyzett URL-címét.

Ha befejeződött a feltöltés, a feltöltött alkalmazás **Szoftver tulajdonságai** lapján az **Igen** szó lesz látható az **Alkalmazásfelügyeleti szabályzatok** beállításnál.

Ha meggyőződött arról, hogy az alkalmazás sikeresen feltöltődött, folytassa a 3. lépéssel.

#### <a name="to-publish-an-app-that-was-processed-through-the-microsoft-intune-app-wrapping-tool"></a>A Microsoft Intune alkalmazásburkoló eszközével feldolgozott alkalmazások közzététele

1.  Ha készen áll rá, hogy feltöltse az alkalmazást a felhőtárhelyre, járjon el a következő cikk utasításai szerint: [Alkalmazások hozzáadása Microsoft Intune-beli mobileszközökhöz](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  Válassza a **Szoftvertelepítő** lehetőséget a **Válassza ki, hogyan szeretné elérhetővé tenni ezt a szoftvert az eszközök számára** csoportban.

3.  Válassza a **Csomag hozzáadása iOS-hez (&#42;.ipa-fájl)** lehetőséget a **Szoftvertelepítő fájltípusa** csoportban.

Ha befejeződött a feltöltés, a feltöltött alkalmazás **Szoftver tulajdonságai** lapján az **Igen** szó lesz látható az **Alkalmazásfelügyeleti szabályzatok** beállításnál.

Ha meggyőződött arról, hogy az alkalmazás sikeresen feltöltődött, folytassa a 3. lépéssel.

## <a name="step-3-create-a-mobile-application-management-policy"></a>3. lépés: Mobilalkalmazás-kezelési házirend létrehozása

1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Házirend** &gt; **Áttekintés** &gt; **Házirend hozzáadása** elemet.

2.  Konfigurálja és alkalmazza az alábbi **szoftverszabályzatok** egyikét attól függően, hogy milyen típusú eszközhöz szeretne alkalmazásokat konfigurálni:

    -   **Mobilalkalmazás-felügyeleti szabályzat (Android 4 és újabb verziók)**

    -   **Mobilalkalmazás-kezelési szabályzat (iOS 8.0 és újabb verziók)**

    Használhatja az ajánlott beállításokat, vagy testre is szabhatja a beállításokat. További információt [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) című témakörben találhat.

3.  Adja meg saját igényeinek megfelelően a következő beállításokat: A beállítások eltérhetnek attól függően, hogy a házirendet milyen típusú eszközhöz konfigurálja.

|Beállítás neve|Részletek|
    |---------|--------------------|
    |**Név**|Adja meg a házirend nevét.|
    |**Leírás**|Ha szeretne, adjon meg egy leírást a házirendhez.|
    |**A vállalat által kezelt böngészőben megjelenő webtartalom korlátozása**|Ha engedélyezve van ez a beállítás, az alkalmazásban szereplő esetleges hivatkozások a felügyelt böngészőben fognak megnyílni. Ahhoz, hogy működjön ez a beállítás, az alkalmazásnak telepítve kell lennie az eszközökön.|
    |**Android-biztonsági mentések tiltása** vagy **iTunes- és iCloud-biztonsági mentések tiltása**|Ez a beállítás letiltja az alkalmazás adatainak biztonsági mentését.|
    |**Más alkalmazásokból való adatátvitel engedélyezése az alkalmazásnak**|Ezzel a beállítással megadhatja azokat az alkalmazásokat, amelyeknek ez az alkalmazás adatokat küldhet. Választhat, hogy letiltja, illetve csak más felügyelt alkalmazásokba vagy bármely alkalmazásba engedélyezi az adatátvitelt. <br /><br />Például ha nem engedélyezi az adatátvitelt, azzal megakadályozza az olyan szolgáltatásoknak való adatátvitelt, mint az SMS-üzenetkezelés, képek hozzárendelése a kapcsolatokhoz és a közzététel a Facebook-on vagy a Twitteren.<br /><br />iOS-eszközök esetén a kezelt és nem kezelt alkalmazások közötti dokumentumátvitel letiltásához egy olyan mobileszköz-biztonsági házirendet is konfigurálnia és alkalmaznia kell, amely letiltja a **Kezelt dokumentumok engedélyezése más nem kezelt alkalmazásokban**beállítást. Ha csak más felügyelt alkalmazásokba engedélyezi az átvitelt, az Intune PDF- és képmegtekintői lesznek használva a megfelelő típusú tartalmak megnyitásához (ha telepítve vannak).<br /><br />A **Házirend által felügyelt alkalmazások** vagy a **Nincs** beállítás alkalmazása esetén le lesz tiltva az iOS 9 rendszernek az a funkciója, amely lehetővé teszi, hogy a Spotlight-keresés adatokat keressen az alkalmazásokon belül.<br><br>Ez a beállítás nem szabályozza a mobileszközök Megnyitás a következőben funkciójának használatát. A Megnyitás a következőben funkció kezeléséről az [iOS-alkalmazások közti adatátvitel felügyelete a Microsoft Intune-nal](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) című cikkben olvashat.|
    |**Más alkalmazásokból való adatfogadás engedélyezése az alkalmazásnak**|Ezzel a beállítással megadhatja azokat az alkalmazásokat, amelyekből ez az alkalmazás adatokat fogadhat. Választhat, hogy teljesen letiltja, vagy csak más felügyelt alkalmazásokból, illetve bármely alkalmazásból engedélyezi az adatátvitelt.<br /><br />Amikor a felhasználók egy mobilalkalmazás-felügyeleti szabályzat által nem felügyelt alkalmazás adataihoz férnek hozzá, azokat a rendszer a szabályzat által védett vállalati adatokként kezeli. Ez vagy a többszörös identitást támogató iOS-alkalmazásokra vonatkozik (ahol az Intune csak vállalati fiókokra vagy adatokra alkalmazza a felügyeleti beállításokat az alkalmazásban), vagy az olyan regisztrált eszközökre, amelyeket mobilalkalmazás-felügyeleti szabályzat felügyel.|
    |**A „Mentés másként” művelet letiltása**|Ezzel a beállítással bármely, ezt a szabályzatot alkalmazó alkalmazásban letilthatja a **Mentés másként** művelet az adatok személyes felhőbeli tárolókba (mint például személyes OneDrive- vagy Dropbox-tárhelyre) mentéséhez való használatát.|
    |**Kivágási, másolási és beillesztési műveletek korlátozása más alkalmazásokkal**|Ezzel a beállítással megadhatja, hogy miként legyen használható a kivágási, a másolási és a beillesztési művelet az alkalmazással. A következő lehetőségek közül választhat:<br /><br />**Letiltva**. A kivágási, másolási és beillesztési műveletek letiltása az alkalmazás és más alkalmazások között.<br /><br />**Szabályzattal felügyelt alkalmazások**. A kivágási, másolási és beillesztési műveletek engedélyezése csak az alkalmazás és más felügyelt alkalmazások között.<br /><br />**Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**. Az alkalmazásból kivágott vagy másolt adatok beillesztésének engedélyezése csak más felügyelt alkalmazásokba. Egy tetszőleges alkalmazásból kivágott vagy másolt adatok beillesztésének engedélyezése ebbe az alkalmazásba.<br /><br />**Bármely alkalmazás**. Nincs korlátozás az alkalmazásba vagy alkalmazásból történő kivágási, másolási és beillesztési műveletekre vonatkozóan.<br /><br />Az adatok felügyelt alkalmazások közötti másolásához és beillesztéséhez mindkét alkalmazásban a **Szabályzattal felügyelt alkalmazások** vagy a **Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel** beállítást kell engedélyezni.|
    |**Egyszerű PIN-kód szükséges a hozzáféréshez**|Ha ez a beállítás aktív, a felhasználónak meg kell adnia az alkalmazás használatához megadott PIN-kódot. A felhasználót a rendszer az alkalmazás első futtatásakor kéri a kód beállítására.|
    |**Kísérletek száma a PIN-kód alaphelyzetbe állítása előtt**|Beállíthatja, hányszor tehet kísérletet a felhasználó a PIN-kód megadására, mielőtt a rendszer a PIN-kód alaphelyzetbe állítását kérné.|
    |**Vállalati hitelesítő adatok szükségesek a hozzáféréshez**|Ha ez a beállítás aktív, a felhasználónak meg kell adnia vállalati bejelentkezési adatait, mielőtt hozzáférhetne az alkalmazáshoz.|
    |**A vállalati házirenddel való eszközkompatibilitás szükséges a hozzáféréshez**|Ezzel a beállítással az alkalmazás használata csak akkor engedélyezett, ha az eszköz nem jailbreakelt vagy rootolt.|
    |**A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc)**|Az **Időtúllépés** mezőben adja meg azt az időtartamot, amennyi elteltével szeretné, hogy megtörténjen az alkalmazás hozzáférési követelményeinek ismételt ellenőrzése az alkalmazás elindítása után.|
    |**Offline türelmi időszak**|Ha az eszköz offline állapotban van, itt megadhatja azt az időtartamot, amennyi elteltével szeretné, hogy megtörténjen az alkalmazás hozzáférési követelményeinek ismételt ellenőrzése.|
    |**Alkalmazásadatok titkosítása**|Ezzel a beállítással megadhatja, hogy az alkalmazáshoz kapcsolódó összes adat titkosítva legyen, beleértve a külsőleg (például SD-kártyán) tárolt adatokat is.<br /><br />**Titkosítás iOS rendszerhez**<br /><br />Az Intune valamely mobilalkalmazás-felügyeleti szabályzatával társított alkalmazások esetén az adatok titkosítása az operációs rendszer által biztosított eszközszintű titkosítással történik. Ez az eszköz PIN-szabályzatán keresztül engedélyezhető, amelyet a rendszergazda állít be. PIN-kód megadása esetén az adattitkosítás a mobilalkalmazás-felügyeleti szabályzatban megadott beállítások szerint történik. Az Apple dokumentációjában leírtaknak megfelelően [az iOS által használt modulok FIPS 140-2 hitelesítéssel rendelkeznek](http://support.apple.com/en-us/HT202739).<br /><br />**Titkosítás Android rendszerhez**<br /><br />Az Intune valamely mobilalkalmazás-felügyeleti szabályzatával társított alkalmazások esetén a titkosítást a Microsoft biztosítja. A rendszer szinkron módon titkosítja az adatokat a fájlok írási és olvasási műveletei során.  Az eszköz tárhelyén található tartalom mindig titkosított marad. A titkosítási módszerre nem érvényes a FIPS 140-2 típusú tanúsítvány.|
    |**Képernyőrögzítés letiltása** (csak Android-eszközök esetén)|Ezzel a beállítással megadhatja, hogy az eszköz képernyőfelvétel-funkciói le legyenek tiltva az alkalmazás használatakor.|

4. Ha elkészült, válassza a **Házirend mentése** elemet.

Az új szabályzat a **Házirend** munkaterület **Konfigurációs szabályzatok** csomópontjában jelenik meg.

## <a name="step-4-associate-the-app-with-a-mobile-application-management-policy-and-then-deploy-the-app"></a>4. lépés: Az alkalmazás társítása egy mobilalkalmazás-felügyeleti szabályzattal, majd az alkalmazás telepítése
Gondoskodjon arról, hogy az **Üzembe helyezés kezelése** párbeszédpanel **Mobilalkalmazás-kezelés** lapján a mobilalkalmazás-felügyeleti szabályzat kiválasztásával társítja a szabályzatot az alkalmazással.

További információt az [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps.md) című témakörben találhat.

> [!IMPORTANT]
> Ha az eszköz Intune-regisztrációját megszüntetik, a szabályzatok alkalmazásokból való eltávolítása nem történik meg. A szabályzatokkal felügyelt alkalmazások megőrzik a szabályzat beállításait még azt követően is, hogy az alkalmazást eltávolították és újratelepítették.

### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>Teendők, ha egy alkalmazás már üzembe van helyezve az eszközökön
Előfordulhat, hogy egy alkalmazás telepítésekor a célcsoportba tartozó felhasználók vagy eszközök egyike már rendelkezik a telepített alkalmazás nem felügyelt verziójával, például telepítette a Microsoft Wordöt az alkalmazásáruházból.

Ilyenkor meg kell kérnie a felhasználót, hogy manuálisan távolítsa el a nem felügyelt verziót, hogy telepíthető legyen az Ön által konfigurált felügyelt verzió.

Az iOS 9-es vagy újabb verziójával futó eszközök esetében az Intune automatikusan engedélyt kér a felhasználótól a meglévő alkalmazás felügyeletének átvételére. Ha az engedélyt megadják, az alkalmazás az Intune felügyelete alá kerül, és az összes Ön által hozzárendelt mobilalkalmazás-felügyeleti szabályzat érvényes lesz rá.

> [!TIP]
> Ha az eszköz felügyelt módban van, az Intune a felhasználó engedélyének kikérése nélkül átveszi a meglévő alkalmazás felügyeletét.

## <a name="step-5-monitor-the-app-deployment"></a>5. lépés: Az alkalmazás telepítésének figyelése
Miután létrehozott és telepített egy mobilalkalmazás-felügyeleti szabályzattal társított alkalmazást, a következő eljárásokkal figyelheti az alkalmazást, és feloldhatja az esetleges szabályzatütközéseket.

#### <a name="to-view-the-status-of-the-deployment"></a>A telepítés állapotának megtekintése

1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Csoportok** &gt; **Áttekintés** lehetőséget.

2.  Hajtsa végre az alábbi lépések egyikét:

    -   Válassza a **Minden felhasználó** elemet, majd kattintson duplán arra a felhasználóra, akinek az eszközét meg szeretné vizsgálni. A **Felhasználó tulajdonságai** lapon válassza az **Eszközök** elemet, majd kattintson duplán arra az eszközre, amelyet meg szeretne vizsgálni.

    -   Válassza a **Minden eszköz** &gt; **Minden mobileszköz** elemet. Az **Eszközcsoport tulajdonságai** lapon válassza az **Eszközök** elemet, majd kattintson duplán arra az eszközre, amelyet meg szeretne vizsgálni.

3.  A **Mobileszköz tulajdonságai** lapon válassza a **Házirend** elemet az eszközre alkalmazott mobilalkalmazás-kezelési házirendek megtekintéséhez.

4.  Jelölje ki azt a mobilalkalmazás-kezelési házirendet, amelynek meg szeretné tekinteni az állapotát. A házirend adatait az alsó ablaktáblában, a beállításait pedig a hozzá tartozó csomópont kibontásával tekintheti meg.

5.  Az egyes mobilalkalmazás-felügyeleti szabályzatok **Állapot** oszlopában a **Megfelel**, **Megfelel (folyamatban)**vagy a **Hiba** szó jelenik meg. Ha a kijelölt szabályzat egy vagy több beállítása ütközik, a mezőben a **Hiba** szó fog megjelenni.

6.  Ha azonosított egy ütközést, felülvizsgálhatja az ütköző szabályzatbeállításokat, vagy alkalmazhat csupán egy szabályzatot az alkalmazásra és a felhasználóra.

### <a name="how-policy-conflicts-are-resolved"></a>Házirend-ütközések feloldása
Ha a felhasználó vagy eszköz első telepített példányán ütközik egy mobilalkalmazás-felügyeleti szabályzat, az ütközésben lévő beállításérték el lesz távolítva az alkalmazásra alkalmazott szabályzatból, és az alkalmazás egy beépített ütközési értéket fog használni.

Ha az alkalmazás vagy felhasználó későbbi telepített példányain ütközik egy mobilalkalmazás-felügyeleti szabályzat, az ütközésben lévő beállításérték nem fog frissülni az alkalmazásra alkalmazott mobilalkalmazás-felügyeleti szabályzaton, az alkalmazás pedig a beállítás meglévő értékét fogja használni.

Azokban az esetekben, amikor az eszköz vagy a felhasználó két ütköző házirendet kap, a következő viselkedés tapasztalható:

-   Ha egy házirend már alkalmazva lett az eszközre, a meglévő házirend-beállítások nem íródnak felül.

-   Ha még nem lett alkalmazva házirend az eszközre, és két ütköző beállítás van használatban, az eszközbe épített alapértelmezett beállítás használatos.

