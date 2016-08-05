---
title: "A vállalat által birtokolt eszközök felügyelete | Microsoft Intune"
description: "A vállalat által birtokolt eszközök (COD) az adott eszköztől, a vásárlásának módjától, illetve a szervezet igényeitől függően több különböző módon is felügyelet alá vonhatók."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ecfeb73efed4a47256275120c52de232c556adfe
ms.openlocfilehash: 58efadf2f9fc34a31070aff93e86083583630caa


---

# A vállalat által birtokolt eszközök regisztrálása a Microsoft Intune-ban
A szervezet vagy vállalat által birtokolt eszközök (COD) az adott eszköztől, vásárlásának módjától, illetve a szervezet igényeitől függően több különböző módon is felügyelet alá vonhatók. A vállalati tulajdonban lévő eszközöket a Vállalati portál alkalmazás „Saját eszköz használata” (BYOD) forgatókönyvei szerint is regisztrálhatja és felügyelheti.

## Vállalat által birtokolt iOS-eszközök
Ezek a regisztrációs módszerek a „Saját eszköz kiválasztása” (CYOD) típusú esetekben megfelelőek, vagyis amikor a szervezet megvásárolja az eszközöket a felhasználóknak, de szeretné megőrizni az eszközök feletti felügyeletet. Ha a szervezete iOS-eszközöket vásárolt, a regisztrációt előre beállíthatja, így amikor a felhasználó első alkalommal bekapcsolja a készüléket, az eszköz felügyelete is megkezdődik. Az Intune támogatja az [Apple készülékregisztrációs programján (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) keresztüli, illetve a Mac számítógépen futó Apple Configurator eszköz segítségével történő [közvetlen](ios-direct-enrollment-in-microsoft-intune.md) vagy [Beállítási asszisztenssel](ios-setup-assistant-enrollment-in-microsoft-intune.md) végzett regisztrációt.

[A vállalat által birtokolt iOS-eszközök regisztrálása](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Eszközregisztráció-kezelő
A szervezetek az Intune használatával nagyszámú mobileszközt felügyelhetnek egyetlen felhasználói, úgynevezett készülékregisztráció-kezelői fiókkal. A készülékregisztráció-kezelői fiók létrehozását követően a fiókot használó kezelő a normál felhasználók számára alapértelmezés szerint engedélyezett szokásos öt eszköznél többet is regisztrálhat. A készülékregisztráció-kezelő által végzett regisztráció csak konkrét felhasználóval nem rendelkező eszközök esetén lehetséges. Ezek az eszközök például POS- vagy segédprogram-alkalmazásokhoz megfelelőek, de nem alkalmasak olyan felhasználók számára, akik hozzá szeretnének férni a levelezésükhöz vagy a vállalati erőforrásokhoz.

[Vállalati tulajdonban lévő eszközök regisztrálása az eszközregisztráció-kezelővel](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Vállalati tulajdonú Windows 10-asztalok

Ha a szervezete rendelkezik Prémium szintű Azure Active Directory (AADP) vagy Nagyvállalati felügyeleti csomag (EMS) előfizetéssel, [regisztrálhatja a Windows 10 vállalati verzióját](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview), és az automatikusan „vállalati tulajdonúként” lesz megjelölve, amikor a felhasználók hozzáadják a munkahelyi vagy az iskolai fiókjaikat.

## Eszközök azonosítása vállalati tulajdonúként

A vállalati tulajdonú eszközökhöz az eszközök listáján a **Vállalati** megjelölés van beállítva a **Tulajdonjog** elemnél. Az eszközök az alábbi módokon azonosíthatók vállalati tulajdonúként:

 - [Készülékregisztráció-kezelővel (DEM) regisztrált eszközök](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Az Apple [készülékregisztrációs programjával (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) vagy az [Apple Configuratorral](ios-setup-assistant-enrollment-in-microsoft-intune.md) regisztrált eszközök
 - [Eszközök előzetes deklarálása IMEI-számokkal](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [A Windows 10-eszközök Azure Active Directoryval/Nagyvállalati felügyeleti csomaggal történő regisztrációja](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### Nemzetközi mobilkészülék-azonosító (IMEI)

Az egyedi nemzetközi mobileszköz-azonosító, az úgynevezett az IMEI-szám, egy olyan eszköztulajdonság, amelyet számos mobileszköz-gyártó általánosan alkalmaz. Az Intune-rendszergazdák importálni tudják a vállalat tulajdonában lévő eszközök IMEI-számát. Amikor az eszközt elkezdi az Intune felügyelni, vállalati tulajdonú eszközként lesz megjelölve.

[Vállalati tulajdonban lévő eszközök megadása IMEI-számokkal](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO4-->


