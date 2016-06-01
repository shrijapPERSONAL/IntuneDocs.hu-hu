---
# required metadata

title: A vállalat által birtokolt eszközök kezelése a Microsoft Intune-nal | Microsoft Intune
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
A szervezet vagy vállalat által birtokolt eszközök (COD) az adott eszköztől, illetve vásárlásának módjától függően többféleképpen is felügyelet alá vonhatók.

## Vállalat által birtokolt iOS-eszközök
Ezek a regisztrációs módszerek a „Saját eszköz kiválasztása” (CYOD) típusú esetekben megfelelőek, vagyis amikor a szervezet megvásárolja az eszközöket a felhasználóknak, de szeretné megőrizni az eszközök feletti felügyeletet. Ha a szervezete iOS-eszközöket vásárolt, a regisztrációt előre beállíthatja, így amikor a felhasználó első alkalommal bekapcsolja a készüléket, az eszköz felügyelete is megkezdődik. Az Intune támogatja az [Apple készülékregisztrációs programján (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) keresztüli, illetve a Mac számítógépen futó Apple Configurator eszköz segítségével történő [közvetlen](ios-direct-enrollment-in-microsoft-intune.md) vagy [Beállítási asszisztenssel](ios-setup-assistant-enrollment-in-microsoft-intune.md) végzett regisztrációt.

[A vállalat által birtokolt iOS-eszközök regisztrálása](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Eszközregisztráció-kezelő
A szervezetek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói, úgynevezett készülékregisztráció-kezelői fiókkal. A készülékregisztráció-kezelői fiók létrehozását követően a fiókot használó kezelő a normál felhasználók számára alapértelmezés szerint engedélyezett szokásos öt eszköznél többet is regisztrálhat. A készülékregisztráció-kezelő által végzett regisztráció csak konkrét felhasználóval nem rendelkező eszközök esetén lehetséges. Ezek az eszközök például POS- vagy segédprogram-alkalmazásokhoz megfelelőek, de nem alkalmasak olyan felhasználók számára, akik hozzá szeretnének férni a levelezésükhöz vagy a vállalati erőforrásokhoz.

[Vállalati tulajdonban lévő eszközök regisztrálása az eszközregisztráció-kezelővel](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Vállalati tulajdonban lévő eszközök megadása IMEI-számokkal
Az egyedi nemzetközi mobileszköz-azonosító, az úgynevezett az IMEI-szám, egy olyan eszköztulajdonság, amelyet számos mobileszköz-gyártó általánosan alkalmaz. Az Intune-rendszergazdák importálni tudják a vállalat tulajdonában lévő eszközök IMEI-számát. Amikor az Intune-nal megkezdődik egy eszköz felügyelete, az eszköz megjelölhető vállalati tulajdonként, illetve a megfelelő szabályzattal megcélozható.

[Vállalati tulajdonban lévő eszközök megadása IMEI-számokkal](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO1-->


