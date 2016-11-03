---
title: "Eszközök regisztrálása az eszközregisztráció-kezelővel | Microsoft Intune"
description: "Az eszközregisztráció-kezelői (DEM-) fiók segítségével nagy számú megosztott, vállalati tulajdonban lévő, egy felhasználói fiókkal rendelkező mobileszköz kezelhető."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e332bbf9aa8f6543950eba7e1fd734b3fb4b1edb
ms.openlocfilehash: ca81a72fe98d454591765296445215a2b574243b


---


# Vállalati tulajdonban lévő eszközök regisztrálása az Eszközregisztráció-kezelővel
A szervezetek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói fiókkal. Az *eszközregisztráció-kezelői* (DEM-) fiók egy akár ezer eszköz regisztrálására képes, speciális Intune-fiók. Az ezzel a fiókkal regisztrált eszközöket célszerű nem személyes („BYOD”), hanem megosztott eszközökként használni. A felhasználók például nem használhatják a „natív” levelezőalkalmazásokat.

Például hozzárendelhet egy eszközregisztráció-kezelői felhasználói fiókot az üzletvezetőhöz vagy egy feletteshez, így ők az alábbi műveleteket hajthatják végre:

-   Eszközök regisztrálása az Intune-ban.

-   Bejelentkezés a Vállalati portálra vállalati alkalmazások beszerzéséhez.

-   Szoftverek telepítése és eltávolítása.

-   Vállalati adatok elérésének konfigurálása.


**Példa egy eszközregisztráció-kezelői forgatókönyvre:** Egy étterem POS táblagépeket szeretne rendelni a pincéreknek, és a rendeléseket megjelenítő kijelzőket a konyhai személyzetnek. Az alkalmazottaknak nem szükséges hozzáférni a céges adatokhoz, vagy felhasználóként bejelentkezni. Az Intune-rendszergazda létrehoz egy eszközregisztráció-kezelői fiókot, és a fiókot használva regisztrálja a vállalat tulajdonában álló eszközöket. Másik lehetőségként a rendszergazda eszközregisztráció-kezelői hitelesítő adatokat adhat egy étterem vezetőjének, lehetővé téve, hogy regisztrálja és felügyelje az eszközöket.

A rendszergazda vagy vezető szerepkör-specifikus alkalmazásokat telepíthet az éttermi eszközökre. A rendszergazdák kijelölhetik az eszközt az Intune-konzolon, és a felügyeleti konzollal kivonhatják a mobileszköz-felügyelet alól.

Az eszközregisztráció-kezelői fiókokkal regisztrált eszközökre a következő korlátozások vonatkoznak:
  - Nincs konkrét „felhasználója” az eszközöknek, így nincs szükség e-mail-fiókokra és a céges adatokhoz való hozzáférésre. Az adatok VPN-nel azonban továbbra is hozzáférhetővé tehetők az eszközökön.
  - Nincs feltételes hozzáférés, mivel az a felhasználókon alapul.
  - Az eszközöket nem lehet alaphelyzetbe állítani a Vállalati portálról.
  - A Vállalati portál alkalmazásban vagy a webhelyén csak a helyi eszköz jelenik meg.
  - Az eszközökön nem lehet az Apple Volume Purchase Program (VPP) keretében vásárolt alkalmazásokat futtatni, mivel az alkalmazások kezeléséhez felhasználói Apple ID azonosítóra van szükség.
  - Az eszközöket nem lehet az Apple Configuratorral vagy az Apple készülékregisztrációs programjában is regisztrálni (ez az iOS-eszközökre vonatkozik).

> [!NOTE]
> A vállalati alkalmazások eszközregisztráció-kezelővel felügyelt eszközökre történő telepítéséhez telepítse a Vállalati portál alkalmazást **Szükséges telepítésként** az eszközregisztráció-kezelő felhasználói fiókjára.
> A teljesítmény javítása érdekében a DEM-eszközökön a Vállalati portál alkalmazás kizárólag a helyi eszközt jeleníti meg. A többi DEM-eszköz távoli felügyelete kizárólag az Intune felügyeleti konzolból valósítható meg.

## Eszközregisztráció-kezelői fiókok létrehozása
Az eszközregisztráció-kezelői fiókok nagyszámú vállalati eszköz regisztrálására vonatkozó engedéllyel rendelkező felhasználói fiókok. Csak az Intune-konzolon szereplő felhasználók lehetnek eszközregisztráció-kezelők.

#### Eszközregisztráció-kezelő hozzáadása az Intune-hoz

1.  Nyissa meg a [Microsoft Intune fiókportált](http://go.microsoft.com/fwlink/?LinkId=698854), és jelentkezzen be a rendszergazdai fiókjával.

2.  Kattintson a **Felhasználó hozzáadása** lehetőségre.

3.  Győződjön meg arról, hogy a listán szerepel az a felhasználói fiók, amely az eszközregisztráció-kezelő lesz. Ha nem szerepel, adja hozzá a felhasználót: kattintson az **Új** gombra, majd végezze el a **Felhasználó hozzáadása** folyamatot. Minden felhasználónak előfizetéses licenccel kell rendelkeznie a szolgáltatás használatához. Az eszközregisztráció-kezelő nem lehet az Intune rendszergazdája. A funkció használata előtt ellenőrizze, hogy szükséges-e több licenc hozzáadása.

4.  Jelentkezzen be rendszergazdai azonosítójával a [Microsoft Intune felügyeleti konzoljába](http://manage.microsoft.com).

5.  A navigációs ablaktáblában kattintson a **Rendszergazda** elemre, lépjen a **Rendszergazdai felügyelet** beállításra, és válassza az **Eszközregisztráció-kezelő** lehetőséget. Ekkor megnyílik az **Eszközregisztráció-kezelő** lap.

6.  Kattintson a **Hozzáadás...** lehetőségre. Megnyílik az **Eszközregisztráció-kezelő hozzáadása** párbeszédpanel.

7.  Adja meg az Intune-fiók **felhasználói azonosítóját**, és kattintson az **OK** gombra. Az eszközregisztráció-kezelő felhasználó nem lehet Intune-rendszergazda.

8.  Az eszközregisztráció-kezelő most már ugyanazzal az eljárással regisztrálhat mobileszközöket, amelyet a végfelhasználók használnak a Vállalati portálon a saját eszközök használata esetén.

## Eszközregisztráció-kezelő törlése az Intune-ból

1.  Jelentkezzen be a [Microsoft Intune felügyeleti portálra](http://manage.microsoft.com) a rendszergazdai bejelentkezési adataival.

2.  A navigációs ablaktáblában kattintson a **Rendszergazda** elemre, lépjen a **Rendszergazdai felügyelet** beállításra, és válassza az **Eszközregisztráció-kezelő** lehetőséget. Ekkor megnyílik az **Eszközregisztráció-kezelő** lap.

3.  Jelölje ki a törölni kívánt eszközregisztráció-kezelő **felhasználót**, és kattintson a **Törlés** lehetőségre. Ez a felhasználó nem törlődik az Intune-ból, és a felhasználó által felügyelt eszközök regisztrációja megmarad az Intune-ban. Az eszközregisztráció-kezelő törlése megakadályozza, hogy az adott felhasználó további eszközöket regisztráljon az Intune-ban.

4.  Kattintson az **Igen** lehetőségre az eszközregisztráció-kezelő törlésének jóváhagyásához.

Az eszközregisztráció-kezelő törlése nincs hatással a regisztrált eszközökre. Az eszközregisztráció-kezelő törlésekor:

-   A folyamat a regisztrált eszközöket nem érinti.

-   A regisztrált eszközök továbbra is teljes mértékben felügyeltek.

-   A törölt eszközregisztráció-kezelői fiók hitelesítő adatai továbbra is érvényesek a Vállalati portálra való bejelentkezéshez és az alkalmazások eléréséhez.

-   A törölt eszközregisztráció-kezelői fiók hitelesítő adatai nem törölhetik vagy vonhatják vissza az eszközöket.

-   A törölt eszközregisztráció-kezelői fiók kapcsolata megmarad a regisztrált fiókokkal, de további eszközöket nem lehet regisztrálni.



<!--HONumber=Sep16_HO1-->


