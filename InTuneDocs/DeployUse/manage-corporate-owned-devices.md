---
# required metadata

title: A vállalat által birtokolt eszközök felügyelete | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# A vállalat által birtokolt eszközök regisztrálása a Microsoft Intune-ban
A szervezet vagy vállalat által birtokolt eszközök (COD) az adott eszköztől, vásárlásának módjától, illetve a szervezet igényeitől függően több különböző módon is felügyelet alá vonhatók.

## Vállalat által birtokolt iOS-eszközök
Ezek a regisztrációs módszerek a „Saját eszköz kiválasztása” (CYOD) típusú esetekben megfelelőek, vagyis amikor a szervezet megvásárolja az eszközöket a felhasználóknak, de szeretné megőrizni az eszközök feletti felügyeletet. Ha a szervezete iOS-eszközöket vásárolt, a regisztrációt előre beállíthatja, így amikor a felhasználó első alkalommal bekapcsolja a készüléket, az eszköz felügyelete is megkezdődik. Az Intune támogatja az [Apple készülékregisztrációs programján (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) keresztüli, illetve a Mac számítógépen futó Apple Configurator eszköz segítségével történő [közvetlen](ios-direct-enrollment-in-microsoft-intune.md) vagy [Beállítási asszisztenssel](ios-setup-assistant-enrollment-in-microsoft-intune.md) végzett regisztrációt.

[A vállalat által birtokolt iOS-eszközök regisztrálása](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Eszközregisztráció-kezelő
A szervezetek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói, úgynevezett készülékregisztráció-kezelői fiókkal. A készülékregisztráció-kezelői fiók létrehozását követően a fiókot használó kezelő a normál felhasználók számára alapértelmezés szerint engedélyezett szokásos öt eszköznél többet is regisztrálhat. A készülékregisztráció-kezelő által végzett regisztráció csak konkrét felhasználóval nem rendelkező eszközök esetén lehetséges. Ezek az eszközök például POS- vagy segédprogram-alkalmazásokhoz megfelelőek, de nem alkalmasak olyan felhasználók számára, akik hozzá szeretnének férni a levelezésükhöz vagy a vállalati erőforrásokhoz.

[Vállalati tulajdonban lévő eszközök regisztrálása az eszközregisztráció-kezelővel](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Nemzetközi mobilkészülék-azonosító (IMEI)
Az egyedi nemzetközi mobileszköz-azonosító, az úgynevezett az IMEI-szám, egy olyan eszköztulajdonság, amelyet számos mobileszköz-gyártó általánosan alkalmaz. Az Intune-rendszergazdák importálni tudják a vállalat tulajdonában lévő eszközök IMEI-számát. Amikor az Intune-nal megkezdődik egy eszköz felügyelete, az eszköz megjelölhető vállalati tulajdonként, illetve a megfelelő szabályzattal megcélozható.

[Vállalati tulajdonban lévő eszközök megadása IMEI-számokkal](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Vállalati tulajdonú eszközök regisztrálási módszereinek áttekintése

A következő táblázat a vállalati tulajdonú eszközök regisztrálási módszereit, valamint azok előnyeit foglalja össze.

**iOS-eszközök regisztrálási módszerei**

| **Módszer** |  **[Reset](#Reset)** |   **[Affinitás](#Affinity)**   |   **[Zárolás](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nem|    Igen |   Nem |
|**[DEM](#DEM)**|   Nem |Nem |Nem  |
|**[DEP](#DEP)**|   Igen |   Választható |   Választható|
|**[USB-SA](#USB-SA)**| Igen |   Választható |   Nem|
|**[USB-Direct](#USB-Direct)**| Nem |    Nem  | Nem|

**Windows- és Android-eszközök regisztrálási módszerei**

| **Módszer** |  **[Törlés](#Wipe)** | **[Felhasználói](#User)**   |   **[Zárolás](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nem|    Igen |   Nem |
|**[DEM](#DEM)**|   Nem |Nem |Nem  |

**A vállalati tulajdonú eszközök regisztrálási módszerei**

### BYOD
„Saját eszközök használata” (Bring Your Own Device). A felhasználók telepítik a Vállalati portál alkalmazást, és ők regisztrálják az eszközt. Az eszközök Vállalati portálon keresztüli regisztrálása az eszközt munkahelyi csatlakoztatással csatlakoztatja. iOS-eszközök Vállalati portálon keresztüli beléptetéséhez Apple ID azonosító szükséges. A BYOD módszer esetén nincs szükség a vállalati tulajdonú eszközök további konfigurálására. Lásd az [eszközkezelés beállításának](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md) lépéseit.

### DEM
Eszközregisztráció-kezelő. A rendszergazda DEM-fiókokat hoz létre. A kezelők ezután telepíteni tudják a Vállalati portált, és több, felhasználó nélküli eszközt regisztrálhatnak. További információ a [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) módszerről. ([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Apple Device Enrollment Program (Apple Készülékregisztrációs program). A rendszergazda a DEP-en keresztül vásárolt és kezelt iOS-eszközökön „vezeték nélkül” szabályzatokat hoz létre és telepít. Az eszköz regisztrálása akkor történik meg, amikor a felhasználó az iOS-alapú Beállítási asszisztenst futtatja. Ez a módszer támogatja az **iOS-eszközök Felügyelt** módját, amely a következő funkciókat engedélyezi:
  - Zárolt regisztráció
  - Feltételes hozzáférés
  - Függetlenítés észlelése
  - Mobilalkalmazás-kezelés

További információk a [DEP](ios-device-enrollment-program-in-microsoft-intune.md) programról. ([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
USB-kapcsolaton keresztüli, a Beállítási asszisztens használatával történő regisztrálás. A rendszergazda létrehoz egy Intune-szabályzatot, és exportálja azt az Apple Configuratorba. Az USB-csatlakozóval csatlakoztatott eszközök előkészítése Intune-szabályzatokkal zajlik. A rendszergazdának minden eszközt manuálisan kell regisztrálnia. A felhasználók megkapják eszközüket, majd a Beállítási asszisztens futtatásával regisztrálják azt. Ez a módszer támogatja az **iOS-eszközök Felügyelt** módját, amely a következő funkciókat engedélyezi:
  - Zárolt regisztráció
  - Feltételes hozzáférés
  - Függetlenítés észlelése
  - Mobilalkalmazás-kezelés

További információk [az eszközök Apple Configurator és Beállítási asszisztens segítségével történő regisztrálásáról](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
Közvetlen regisztráció. A rendszergazda létrehoz egy Intune-szabályzatot, és exportálja azt az Apple Configuratorba. Az USB-csatlakozóval csatlakoztatott eszközök regisztrálása közvetlenül történik, a gyári beállítások visszaállítása nem szükséges. A rendszergazdának minden eszközt manuálisan kell regisztrálnia. Az eszközöket a rendszer felhasználó nélküli eszközökként kezeli. Ezeket a rendszer nem zárolja és nem felügyeli, és nem képesek a feltételes hozzáférés, a függetlenítésészlelés és a mobilalkalmazás-kezelés támogatására. További információk [az Apple Configurator segítségével történő közvetlen regisztrálásáról](ios-direct-enrollment-in-microsoft-intune.md). ([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods))

**A vállalati tulajdonú mobileszközök működése**

### Reset
Meghatározza, hogy az eszköz beléptetéséhez szükség van-e az eszköz gyári beállításainak visszaállítására, amely eltávolít minden adatot az eszközről, és az eredeti állapotba állítja azt vissza.
([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods))

### Affinitás
Meghatározza, hogy a regisztrálási módszer támogatja-e a „Felhasználói affinitást”, amely az eszközt egy adott felhasználóval kapcsolja össze. A „Választható” jelölésű eszközök felhasználói affinitással és anélkül egyaránt regisztrálhatók. Felhasználói affinitás szükséges az alábbiak támogatásához:
  - Mobilalkalmazás-felügyeleti (MAM) alkalmazások
  - Feltételes hozzáférés az e-mailekhez és a vállalati adatokhoz
  - Vállalati portál alkalmazás

([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods)) ([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods))

### Zárolás
Meghatározza, hogy lehet-e az eszközt zárolni annak megakadályozása érdekében, hogy a felhasználó el tudja távolítani az Intune-szabályzatot, ezzel gyakorlatilag kivonva az eszközt a felügyelet alól. iOS-eszközök zárolásához az eszköznek Felügyelt módban kell lennie.
([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods)) ([Vissza a táblázathoz](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO1-->


