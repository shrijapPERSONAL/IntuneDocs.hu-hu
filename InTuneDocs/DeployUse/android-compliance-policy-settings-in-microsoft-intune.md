---
title: "Megfelelőségi szabályzat beállításai Android-eszközökhöz | Microsoft Intune"
description: "Ez a témakör bemutatja az eszközmegfelelőségi szabályzat beállításait Android-eszközökhöz."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 777c0ac6ea309db81b127fb254e0c5f88444e475
ms.openlocfilehash: cf1fde5b5ed55552e573c724b6165203033683da


---


# Megfelelőségi szabályzat beállításai Android-eszközökhöz a Microsoft Intune-ban

A jelen témakörben leírt szabályzati beállítások az Android 4.0-s és újabb verzióival, illetve a Samsung KNOX 4.0-s és újabb verzióival futó eszközökre vonatkoznak.

Ha más platformokra vonatkozó információkat keres, válassza az alábbiak egyikét:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai iOS-eszközökhöz](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Windows-eszközökhöz](windows-compliance-policy-settings-in-microsoft-intune.md)

## A rendszer biztonsági beállításai
### Jelszó
- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához:** Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget.

-  **Jelszó minimális hossza:** meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

- **Jelszó erőssége:** a beállítás bekapcsolása esetén konfigurálhatja az Android-eszközök jelszókövetelményeit. A következő lehetőségek közül választhat:
  -   **Alacsony biztonságú biometrikus**
  - **Kötelező**
  -   **Legalább számok**
  -   **Legalább betűk**
  -   **Legalább alfanumerikus karakterek**
  -   **Alfanumerikus karakterek és szimbólumok**

- **Jelszó kérése ennyi perc inaktivitás után:** arra a tétlenségi időre vonatkozik, amin belül a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban):** Válassza ki, hány nap elteltével járjon le a felhasználó jelszava, ami után újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése:** Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban már használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.

- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból:** Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt kell használni. A rendszer jelszó beírását kéri a végfelhasználótól a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz eléréséhez.

### Titkosítás
- **Titkosítás megkövetelése mobileszközön:** Állítsa ezt a beállítást **Igen** értékre, ha szeretné előírni, hogy az eszközök csak titkosítás használata esetén csatlakozhassanak az erőforrásokhoz. Az eszközök **A mobileszközök zárolásának feloldásához jelszó szükséges** beállítás konfigurálásával titkosíthatók.

## Eszközállapot és biztonsági beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz:** Ha bekapcsolja ezt a beállítást, a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.
- **Annak megkövetelése, hogy az ismeretlen forrásból származó alkalmazások telepítését a rendszer megakadályozza az eszközökön (Android 4.0 vagy újabb)** A beállítás engedélyezésével és az **Igen** lehetőség beállításával letilthatja azokat az eszközöket, amelyeken engedélyezve van a **Biztonság > Ismeretlen források** beállítás.  
>[!IMPORTANT]
>Az alkalmazások közvetlen telepítéséhez engedélyezni kell az **Ismeretlen források** beállítást.  Csak akkor szükséges ennek a megfelelőségi szabályzatnak a kényszerítése, ha nem Android-alkalmazások közvetlen telepítését végzi az eszközökön.

- **Az USB-hibakeresés letiltásának megkövetelése (Android 4.2 vagy újabb)**: Ezzel a beállítás szabja meg, hogy a rendszer ellenőrizze-e az USB-hibakeresés engedélyezését az eszközön.
- **A Biztonsági fenyegetések keresése az eszközön beállítás engedélyezésének megkövetelése az eszközökön (Android 4.2-4.4)**: Ezzel a beállítás szabja meg, hogy az **Alkalmazások ellenőrzése** funkció engedélyezve van-e az eszközön.
- **Az Android minimálisan előírt biztonsági javítási szintje (Android 6.0 vagy újabb)**: Ezzel a beállítással adható meg az Android minimálisan előírt javítási szintje.  Az ennél régebbi javítási szintű eszközök nem megfelelőek. A dátumot a következő formátumban kell megadni: ÉÉÉÉ-HH-NN.
- **Veszélyforrások elleni eszközvédelem engedélyezése**: ezzel a beállítással megfelelési feltételként kiveszi a kockázatelemzést Lookout MTP-megoldásból. Válassza ki a maximális megengedett kockázati szintet, ami az alábbiak egyike lehet:

  - **Semmilyen (védett)**: Ez a legbiztonságosabb lehetőség. Annyit jelent, hogy az eszköz esetében semmilyen fenyegetés nem engedélyezett. Bármilyen szintű fenyegetés észlelése esetén az eszköz értékelése nem megfelelő lesz.
  - **Alacsony**: Az eszköz csak abban az esetben minősül megfelelőnek, ha vonatkozásában kizárólag alacsony szintű fenyegetések állnak fenn. Bármilyen magasabb szintű fenyegetés esetén az eszköz nem megfelelő státuszúnak minősül.
  - **Közepes**: Az eszköz abban az esetben minősül megfelelőnek, ha az eszköz vonatkozásában fennálló fenyegetések alacsony vagy közepes szintűek. Magas szintű fenyegetés észlelése esetén az eszköz nem megfelelőnek minősül.
  - **Magas**: Ez a legkevésbé biztonságos beállítás. Lényegében minden kockázati szintet engedélyez, ezért valószínűleg csak jelentéskészítési célokra használható.

  További információ: [az eszközök fenyegetések elleni védelmét szolgáló szabály engedélyezése a megfelelőségi szabályzatban](enable-device-threat-protection-rule-in-compliance-policy.md).

## Eszköztulajdonság-beállítások
- **Az operációs rendszer szükséges minimális verziója:** Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni.
  Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, ezt követően pedig hozzáférhet a vállalati erőforrásokhoz.

- **Maximálisan engedélyezett operációsrendszer-verzió:** Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.



<!--HONumber=Sep16_HO3-->


