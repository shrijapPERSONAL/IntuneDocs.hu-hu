---
title: "Az Android MAM-szabályzat beállításai | Microsoft Intune"
description: "Ez a témakör bemutatja a mobilalkalmazás-felügyeleti szabályzat beállításait Android-eszközökhöz."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 13477a66ca8e89345334476445aae037ea8d9702
ms.openlocfilehash: 55bf3ebde7d1185aebdb874c46aae72d8e179d85


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Az Android mobilalkalmazás-felügyeleti szabályzatának beállításai a Microsoft Intune-ban
A jelen témakörben ismertetett szabályzatbeállításokat az Azure Portal **Beállítások** paneljén lehet [konfigurálni](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) a mobilakalmazás-felügyeleti (MAM-) szabályzatokhoz.
A szabályzatbeállításoknak két kategóriájuk van: adatáthelyezési beállítások és hozzáférési beállítások. A jelen témakörben a *szabályzattal felügyelt alkalmazások* kifejezés olyan alkalmazásokra utal, amelyekhez MAM-szabályzatot állítottak be.

##  <a name="data-relocation-settings"></a>Adatáthelyezési beállítások

- **Android-alapú biztonsági mentések tiltása:** Az **Igen** gombbal letilthatja, a **Nem** gombbal engedélyezheti a céges adatok biztonsági mentését a szabályzattal felügyelt alkalmazásokban.

  Alapértelmezett érték: **Igen**
- **Az alkalmazás átadhat adatokat más alkalmazásoknak**: Valamelyik beállítás kiválasztásával adja meg, hogy milyen típusú alkalmazások fogadhatnak vállalati adatokat a szabályzattal felügyelt alkalmazásokból:
  -   **Szabályzattal felügyelt alkalmazások**: Az adatátvitel csak MAM-szabályzattal ellátott alkalmazásokba engedélyezett.
  -   **Minden alkalmazás**: Az adatátvitel engedélyezett minden alkalmazásba.
  -   **Nincs**: Az adatátvitel tiltott minden alkalmazásba.

 Alapértelmezett érték = **Szabályzattal felügyelt alkalmazások**.
- **Az alkalmazás fogadhat adatokat más alkalmazásokból**: Azon alkalmazások körét határozza meg, amelyek adatokat adhatnak át a szabályzattal felügyelt alkalmazásoknak:
  -   **Szabályzattal felügyelt alkalmazások**: Az adatátvitel csak más, szabályzattal felügyelt alkalmazásokból engedélyezett.
  -   **Minden alkalmazás**: Az adatátvitel minden alkalmazásból engedélyezett.
  -   **Nincs**: Az adatátvitel minden alkalmazásból tiltva van.

  Alapértelmezett érték: **Minden alkalmazás**

-   **A Mentés másként művelet letiltása**: Az **Igen** gombot választva letilthatja a Mentés másként funkció használatát bármely olyan alkalmazásban, amelyet ez a szabályzat felügyel. A **Nem** gombot választva engedélyezheti a Mentés másként funkció használatát.

  Alapértelmezett érték: **Igen**
- **Kivágás, másolás és beillesztés tiltása más alkalmazásokkal**: Megadhatja, hogy a rendszer milyen esetekben korlátozza a kivágási, másolási és beillesztési műveleteket. A következő lehetőségek közül választhat:
  -   **Letiltva**: A kivágási, másolási és beillesztési műveletek tiltása a szabályzattal felügyelt alkalmazások között.
  -   **Szabályzattal felügyelt alkalmazások**: A kivágási, másolási és beillesztési műveletek elvégzése csak a szabályzattal felügyelt alkalmazások körében engedélyezett.
  -   **Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**: A kivágási vagy másolási művelet engedélyezett a szabályzattal felügyelt alkalmazások körében. A bármelyik alkalmazásból kivágott vagy másolt adatok beilleszthetők ebbe az alkalmazásba.
  -   **Bármely alkalmazás**: Az alkalmazások közötti kivágási, másolási és beillesztési műveletek nincsenek korlátozva.

  Alapértelmezett érték: **Szabályzattal felügyelt alkalmazások beillesztési lehetőséggel**
-   **A Managed Browser (felügyelt böngésző) alkalmazásban megjelenítendő webes tartalom korlátozása**: Ha az **igen** lehetőséget választja, az alkalmazás hivatkozásai a Managed Browser alkalmazásban nyílnak meg.

  Az Intune-ban nem regisztrált eszközök esetében a szabályzattal felügyelt alkalmazásokban a hivatkozások a MAM-szabályzat használatakor kizárólag a Managed Browser alkalmazásban nyithatók meg.

  Ha az Intune-t használja az eszközök kezeléséhez, olvassa el [Az internet-hozzáférés felügyelt böngészőszabályzatokkal való kezelése a Microsoft Intune-ban](manage-internet-access-using-managed-browser-policies.md) című témakört.

  Alapértelmezett érték: **Igen**
- **Alkalmazásadatok titkosítása**: Válassza az **Igen** lehetőséget a titkosítás engedélyezéséhez. Ha engedélyezve van ez a beállítás, a Microsoft gondoskodik a MAM-szabályzattal társított alkalmazások titkosításról. A rendszer szinkron módon titkosítja az adatokat a fájlok írási és olvasási műveletei során. Az eszköz tárhelyén található tartalom mindig titkosított marad.
  >[!NOTE]
  >A titkosítási módszerre nem érvényes a FIPS 140-2 típusú tanúsítvány.

  Alapértelmezett érték: **Igen**

- **Névjegy-szinkronizálás letiltása**: Válassza az **Igen** lehetőséget, ha nem szeretné, hogy a rendszer szinkronizálja a névjegyadatokat az eszköz natív címjegyzék-alkalmazásával. Ha a **Nem** lehetőséget választja, az alkalmazás az eszköz natív címjegyzék-alkalmazásába menti a névjegyadatokat.

  Ha szelektív törléssel távolítja el a céges adatokat, a rendszer törli a közvetlenül az alkalmazás és a natív címjegyzék között szinkronizált névjegyeket. A natív címjegyzék és egy másik külső forrás között szinkronizált névjegyek nem törölhetők. Ez jelenleg csak a Microsoft Outlook alkalmazásra érvényes.

  Alapértelmezett érték: **Igen**
- **Nyomtatás letiltása**: Válassza az **Igen** lehetőséget, így megakadályozhatja a céges adatok nyomtatását a MAM-szabályzattal társított alkalmazásokban.

  Alapértelmezett érték: **Igen**

##  <a name="access-settings"></a>Hozzáférési beállítások

- **PIN-kód megkövetelése a hozzáféréshez**: Ha azt szeretné, hogy a szabályzattal felügyelt alkalmazások használatához PIN-kód megadása legyen szükséges, válassza az **Igen** lehetőséget. Ha a felhasználó első alkalommal futtatja az alkalmazást munkahelyi környezetben, a rendszer a kód beállítására kéri.

 Alapértelmezett érték: **Igen**

 -  **Egyszerű PIN-kód engedélyezése**: Azt határozza meg, hogy a felhasználó használhat-e egyszerű PIN-kódokat (például 1234 vagy 1111). Alapértelmezett érték = **Igen**.
 - **PIN-kód hossza**: Azt határozza meg, hogy a PIN-kódoknak legalább hány számjegyet kell tartalmazniuk. Alapértelmezett érték = **4**.
 - **Próbálkozások száma a PIN kód alaphelyzetbe állítása előtt**: Itt adhatja meg, hogy a felhasználó hányszor tehet kísérletet a PIN-kód megadására, mielőtt a rendszer a PIN-kód alaphelyzetbe állítását kérné. A beállításnak nincs alapértelmezett értéke.
 - **Ujjlenyomat kérése PIN-kód helyett (Android 6.0 és újabb)**: válassza az **Igen** lehetőséget, ha szeretné, hogy a rendszer számokból álló PIN-kód helyett ujjlenyomat-azonosítót kérjen az alkalmazás eléréséhez.
 Az Android-eszközökön engedélyezheti a felhasználóknak, hogy a számokból álló PIN-kód helyett ujjlenyomattal azonosítsák magukat. Ha a felhasználó a munkahelyi fiókjával próbál hozzáférni az alkalmazáshoz, a rendszer a PIN-kód megadása helyett ujjlenyomat-azonosítót fog kérni.
 - **Vállalati hitelesítő adatok szükségesek a hozzáféréshez**: Ha az **Igen** lehetőséget választja, a rendszer a számokból álló PIN-kód vagy az ujjlenyomat helyett a vállalati hitelesítő adatokat kéri az alkalmazás eléréséhez. Az **Igen** érték megadásával a rendszer felülírja a PIN-kóddal vagy az ujjlenyomatos azonosítással kapcsolatos követelményeket. A rendszer a vállalati hitelesítő adatok megadását fogja kérni a felhasználótól. Alapértelmezett érték = **Nem**.


- **A felügyelt alkalmazások futásának letiltása a függetlenített vagy feltört eszközökön**: Az **Igen** lehetőség kiválasztásával letilthatja az alkalmazások futtatását a függetlenített vagy feltört eszközökön. A felhasználó továbbra is használhatja az alkalmazásokat személyes feladatokhoz, de a munkavégzéshez másik eszközt kell használnia.

  Alapértelmezett érték: **Igen**
- **A hozzáférési követelmények ismételt ellenőrzése ennyi idő után (perc)**
  -   **Időtúllépés**: Itt adhatja meg az alkalmazás hozzáférési követelményeinek újbóli ellenőrzéséig fennmaradó időt (percben).
  -   **Offline türelmi időszak**: Ennyi idő elteltével kerül sor újra az alkalmazás hozzáférési követelményeinek ismételt ellenőrzésére (percben), ha az eszköz offline állapotban van.

  Alapértelmezett érték: **30** perces időkorlát és **720** perces offline türelmi időszak

-   **Offline időszak az alkalmazásadatok törlése előtt (nap)**: Ha egy eszköz már bizonyos ideje offline állapotban van, a rendszer törölheti róla a céges adatokat.  A szabályzatbeállítások paneljén adhatja meg, hány napig lehet az eszköz offline állapotban, mielőtt a rendszer eltávolítaná róla a vállalati adatokat.

    >[!TIP]
    >A **0** érték megadásával kikapcsolhatja ezt a beállítást.

  Alapértelmezett érték: **90** nap
- **Képernyőfelvétel és az Android Assistant alkalmazás tiltása (Android 6 Marshmallow vagy újabb)**: Válassza az **Igen** lehetőséget a képernyőfelvétel-készítés és az eszköz **Android Assistant**-funkcióinak letiltásához az alkalmazás használatakor.



<!--HONumber=Nov16_HO2-->


