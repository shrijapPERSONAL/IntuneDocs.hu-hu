---
title: "Az iOS MAM-szabályzat beállításai | Microsoft Intune"
description: "Ez a témakör bemutatja a mobilalkalmazás-felügyeleti szabályzat beállításait iOS-eszközökhöz."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 913008568226621de4824c5bac287e8a65dc6533


---

#  <a name="ios-mobile-app-management-policy-settings"></a>iOS mobilalkalmazás-felügyeleti szabályzat konfigurálása
A jelen témakörben ismertetett szabályzatbeállításokat az Azure Portal **Beállítások** paneljén lehet [konfigurálni](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) a mobilakalmazás-kezelési (MAM) szabályzatokhoz.

A szabályzatbeállításoknak két kategóriájuk van: adatáthelyezési beállítások és hozzáférési beállítások. A jelen témakörben a *szabályzattal felügyelt alkalmazások* kifejezés olyan alkalmazásokra utal, amelyekhez MAM-szabályzatot állítottak be.

##  <a name="data-relocation-settings"></a>Adatáthelyezési beállítások

- **Az iTunes és az iCloud biztonsági mentéseinek letiltása:** az **Igen** gombbal letilthatja, a **Nem** gombbal engedélyezheti a vállalati adatok biztonsági mentését a szabályzattal felügyelt alkalmazásokban.

  Alapértelmezett érték = **Igen**.

- **Az alkalmazás átadhat adatokat más alkalmazásoknak:** Valamelyik beállítás kiválasztásával jelezze, hogy mely alkalmazások fogadhassanak adatokat a szabályzat által felügyelt alkalmazásoktól:
  - **Házirend által felügyelt alkalmazások**: adatátvitel engedélyezése csak MAM-szabályzattal ellátott alkalmazásokba.
  - **Minden alkalmazás**: Az adatátvitel engedélyezett minden alkalmazásnál.
  - **Nincs**: Minden alkalmazásba tiltott az adatátvitel., ideértve a szabályzat által felügyelt többi alkalmazást is.

  A **Szabályzat által felügyelt alkalmazások** vagy a **Nincs** beállítás alkalmazása esetén le lesz tiltva az iOS 9 rendszer azon funkciója, amely lehetővé teszi, hogy a Spotlight-kereső adatokat kereshessen az alkalmazásokon belül.

  >[!NOTE]
  >Ez a beállítás nem szabályozza a mobileszközök Megnyitás a következőben funkciójának használatát. A Megnyitás a következőben funkció kezeléséről az [iOS-alkalmazások közti adatátvitel felügyelete a Microsoft Intune-nal](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) című cikkben olvashat.

  Alapértelmezett érték = **Szabályzattal felügyelt alkalmazások**.

- **Az alkalmazás fogadhat adatokat más alkalmazásokból**: Azon alkalmazások körét határozza meg, amelyek adatokat adhatnak át a szabályzattal felügyelt alkalmazásoknak:
  -  **Szabályzattal felügyelt alkalmazások**: Az adatátvitel csak más szabályzattal felügyelt alkalmazásokból engedélyezett.
  -  **Minden alkalmazás**: Az adatátvitel minden alkalmazásból engedélyezett.
  -  **Nincs**: az adatátvitel minden alkalmazásból tiltva van.

  Alapértelmezett érték = **Minden alkalmazás**.

- **A Mentés másként művelet letiltása**: Az **Igen** gombot választva letilthatja a Mentés másként funkció használatát bármely olyan alkalmazásban, amelyet ez a szabályzat felügyel. A **Nem** gombot választva engedélyezheti a Mentés másként funkció használatát.

  Alapértelmezett érték = **Igen**.

- **Kivágási, másolási és beillesztési műveletek korlátozása más alkalmazásokkal**: Megadhatja, hogy a rendszer milyen esetekben korlátozza a kivágási, másolási és beillesztési műveleteket. A következő lehetőségek közül választhat:
  -   **Letiltva**: A kivágási, másolási és beillesztési műveletek tiltása a szabályzattal felügyelt alkalmazások között.
  -   **Szabályzat által felügyelt alkalmazások**: A kivágási, másolási és beillesztési műveletek csak a szabályzat által felügyelt alkalmazások között engedélyezettek.
  -   **Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**: A kivágási vagy másolási művelet csak a szabályzat által felügyelt alkalmazások között engedélyezett. A bármelyik alkalmazásból kivágott vagy másolt adatok beilleszthetők ebbe az alkalmazásba.
  - **Bármely alkalmazás**: Az alkalmazások közötti kivágási, másolási és beillesztési műveletek nincsenek korlátozva.

  Alapértelmezett érték = **Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**.

- **A Managed Browser (felügyelt böngésző) alkalmazásban megjelenítendő webes tartalom korlátozása**: Ha engedélyezve van ez a beállítás, az alkalmazás hivatkozásai a Managed Browser alkalmazásban nyílnak meg.

  Az Intune-ban nem regisztrált eszközök esetében a szabályzat által felügyelt alkalmazások webhivatkozásai kizárólag a Managed Browser alkalmazásban nyílnak meg.

  Ha az Intune-t használja az eszközök kezeléséhez, olvassa el [Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](manage-internet-access-using-managed-browser-policies.md) című témakört.

  Alapértelmezett érték = **Igen**.

- **Alkalmazás adatainak titkosítása:** Az Intune valamely MAM-szabályzatához társított alkalmazások esetében az adatok titkosítása az operációs rendszer által biztosított eszközszintű titkosítással történik. Ha PIN-kódra van szükség, az adattitkosítás a MAM-szabályzatban megadott beállítások szerint történik. Az Apple dokumentációjában leírtaknak megfelelően [az iOS 7 által használt modulok a FIPS 140-2 szerint tanúsítottak](http://support.apple.com/en-us/HT202739).

  A szabályzat-beállításokban megadhatja a PIN-kód titkosítási értékét. Ezek az értékek meghatározzák, hogy mikor titkosítsa a rendszer az adatokat. Az alábbi lehetőségek állnak rendelkezésére:
  -   **Ha az eszköz zárolva van:** A rendszer a szabályzathoz társított összes alkalmazásadatot az eszköz zárolt állapotában titkosítja.
  -   **Ha az eszköz zárolva van (kivéve a megnyitott fájlokat):** A rendszer a szabályzathoz társított összes alkalmazásadatot az eszköz zárolt állapotában titkosítja, kivéve az alkalmazásban aktuálisan megnyitott fájlok adatait.
  -   **Az eszköz újraindítása után:** A rendszer az eszköz újraindításakor a szabályzathoz társított összes alkalmazásadatot titkosítja, amíg fel nem oldják a zárolást az eszközön.
  -   **Eszközbeállítások használata:** A rendszer az eszköz alapértelmezett beállításai alapján titkosítja az alkalmazásadatokat.
  Ha engedélyezi ezt a beállítást, a felhasználónak PIN-kódot kell beállítania és használnia az eszköz eléréséhez.  Ha nincs beállítva PIN-kód, nem indulnak el az alkalmazások, és a felhasználót egy üzenet értesíti arról, hogy a vállalat követelményei szerint PIN-kód beállítása szükséges az adott alkalmazás eléréséhez.

  Alapértelmezett érték = A titkosítási beállítás nincs megadva.
- **Névjegy-szinkronizálás letiltása**: Válassza az **Igen** lehetőséget, ha nem szeretné, hogy a rendszer szinkronizálja a névjegyadatokat az eszköz natív címjegyzék-alkalmazásával. Ha a **Nem** lehetőséget választja, az alkalmazás az eszköz natív címjegyzék-alkalmazásába menti a névjegyadatokat.

  Ha szelektív törléssel távolítja el a vállalati adatokat, a rendszer törli az alkalmazásból közvetlenül a natív címjegyzékbe szinkronizált névjegyeket. A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes.

  Alapértelmezett érték = **Igen**.

- **Nyomtatás letiltása**: Válassza az **Igen** lehetőséget, így megakadályozhatja a vállalati adatok nyomtatását a MAM-szabályzattal társított alkalmazásokban.

    Alapértelmezett érték = **Igen**.

##  <a name="access-settings"></a>Hozzáférési beállítások

- **PIN-kód megkövetelése a hozzáféréshez**: Ha azt szeretné, hogy a szabályzattal felügyelt alkalmazások használatához PIN-kód megadása legyen szükséges, válassza az **Igen** lehetőséget. Ha a felhasználó első alkalommal futtatja az alkalmazást munkahelyi környezetben, a rendszer a kód beállítására kéri.

  Alapértelmezett érték = **Igen**.
    -  **Egyszerű PIN-kód engedélyezése**: Azt határozza meg, hogy a felhasználó használhat-e egyszerű PIN-kódokat (például 1234 vagy 1111). Alapértelmezett érték = **Igen**.
    - **PIN-kód hossza**: Azt határozza meg, hogy a PIN-kódoknak legalább hány számjegyet kell tartalmazniuk. Alapértelmezett érték = **4**.
    - **Próbálkozások száma a PIN kód alaphelyzetbe állítása előtt**: Itt adhatja meg, hogy a felhasználó hányszor tehet kísérletet a PIN-kód megadására, mielőtt a rendszer a PIN-kód alaphelyzetbe állítását kérné. A beállításnak nincs alapértelmezett értéke.

- **Ujjlenyomat kérése PIN-kód helyett (iOS 8.0 és újabb)**: válassza az **Igen** lehetőséget, ha szeretné, hogy a rendszer számokból álló PIN-kód helyett ujjlenyomat-azonosítót kérjen az alkalmazás eléréséhez.
iOS-eszközökön engedélyezheti, hogy a felhasználók számjegyes PIN-kód helyett ujjlenyomattal azonosítsák magukat. Ha a felhasználó a munkahelyi fiókjával próbál hozzáférni az alkalmazáshoz, a rendszer a PIN-kód megadása helyett ujjlenyomat-azonosítót fog kérni.

  Alapértelmezett érték = **Igen**.
- **Vállalati hitelesítő adatok szükségesek a hozzáféréshez**: Az **Igen** lehetőséget választva a rendszer a számokból álló PIN-kód helyett vállalati hitelesítő adatokat kér az alkalmazás eléréséhez. Az **Igen** érték megadásával a rendszer felülírja a PIN-kóddal vagy az ujjlenyomatos azonosítással kapcsolatos követelményeket. A rendszer a vállalati hitelesítő adatok megadását fogja kérni a felhasználótól.

  Alapértelmezett érték = **Nem**.
- **A felügyelt alkalmazások futásának letiltása a függetlenített vagy feltört eszközökön**: Az **Igen** lehetőség kiválasztásával letilthatja az alkalmazások futtatását a függetlenített vagy feltört eszközökön. A felhasználó továbbra is használhatja az alkalmazásokat személyes feladatokhoz, de a munkavégzéshez másik eszközt kell használnia.

  Alapértelmezett érték = **Igen**.
- **A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc)**
  -   **Időtúllépés**: Itt adhatja meg az alkalmazás hozzáférési követelményeinek újbóli ellenőrzéséig fennmaradó időt (percben).
  -   **Offline türelmi időszak**: Ennyi idő elteltével kerül sor újra az alkalmazás hozzáférési követelményeinek ismételt ellenőrzésére (percben), ha az eszköz offline állapotban van.

  Alapértelmezett érték = **30** perces időkorlát és **720** perces offline türelmi időszak.
- **Offline időszak az alkalmazásadatok törlése előtt (nap)**: Ha egy eszköz már bizonyos ideje offline állapotban van, a rendszer törölheti róla a vállalati adatokat. A szabályzatbeállítások paneljén adhatja meg, hány napig lehet az eszköz offline állapotban, mielőtt a rendszer eltávolítaná róla a vállalati adatokat.

  >[!TIP]
  >A **0** érték megadásával kikapcsolhatja ezt a beállítást.

  Alapértelmezett érték = **90** nap.



<!--HONumber=Oct16_HO5-->


