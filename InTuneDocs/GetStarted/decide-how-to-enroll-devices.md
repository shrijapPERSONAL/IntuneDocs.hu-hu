---
title: "A mobileszközök regisztrálásának módjai | Microsoft Intune"
description: "Néhány egyszerű kérdés megválaszolásával eldöntheti, hogyan végzi el a mobileszközök regisztrálását az Intune-ban"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: c671610b9c56d8b92d126d9902cce9c8c689ed63
ms.openlocfilehash: 9f1612ffd9ab85e38058edb09870297a44b37c16


---

# A mobileszközök regisztrálásának módjai

A mobileszköz regisztrálása az a folyamat, amely az okostelefonokat, a táblagépeket és a számítógépeket a menedzsment részévi teszi a Microsoft Intune segítségével. Rendszergazdaként el kell döntenie, hogy hogyan érdemes regisztrálni az eszközeit az alábbi szempontok alapján:

 -  Tulajdonjog (személyi vagy vállalati tulajdonban lévő eszköz)
 -  Használat (megosztott vagy személyes)
 -  Platform (iOS, Android, Windows Phone, Windows-számítógép, Mac számítógép)

Az alábbi kérdésekre adott válaszaiból megtudhatja, hogy melyik regisztrációs módszer felel meg a legjobban az Ön által kezelt eszközöknek.

## **Az alkalmazottak saját eszközeiket használják, vagy a szervezet biztosítja nekik ezeket az eszközöket?**

  - **Felhasználók saját eszközei** – „BYOD-regisztráció” (Bring your own device – hozd a saját eszközöd) – A felhasználók telepítik az eszközeikre az Intune Vállalati portál alkalmazást, majd regisztrálják az eszközöket, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és adatok, valamint az ügyfélszolgálat.  

  - **Vállalati eszközök** A vállalati tulajdonban lévő eszközök többféleképpen is regisztrálhatók a szervezet igényeitől és az eszközök típusától függően.

> [!div class="button"]
[BYOD-regisztráció >](#what-byod-devices-can-your-users-enroll)   [COD-regisztráció >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Milyen BYOD-eszközöket regisztrálhatnak a felhasználói?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS és Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile & Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows rendszerű számítógépek](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **A vállalati tulajdonban lévő eszközök megosztott eszközök, vagy dedikált felhasználókkal rendelkeznek?**

- **Megosztott vállalati eszközök** – Ezekhez az eszközökhöz több felhasználó is hozzáfér, és általában nem használhatók levelezésre. Ilyen eszköz például az interaktív terminál, vagy a feladatközpontú, egy helyen tárolt, közös használatú eszközök. Az ajánlott regisztrációs módszer az eszköz platformjától függ.

- **Dedikált felhasználók** – Az egyéni félhasználókkal rendelkező vállalati tulajdonban lévő eszközök egyszerre nyomon követendő vállalati eszközök és személyes eszközök, amelyről a felhasználók elérhetik e-mail postafiókjukat és adataikat. Az ajánlott regisztrációs módszer az eszköz platformjától függ.

> [!div class="button"]
[Megosztott >](#what-operating-system-are-your-shared-devices-running)   [Dedikált >](#how-will-you-manage-dedicated-ios-devices)


## **Milyen operációs rendszert futtatnak megosztott eszközei?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Hogyan kezelheti a megosztott iOS-eszközeit?**

- **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökre regisztrációs profil telepíthető. Amikor a felhasználók először kapcsolják be az eszközt, az letölti a DEP-profilt és regisztrálja az eszközt

- **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt. Ha nem szeretné a gyári beállításokat visszaállítani az eszközökön, használja Közvetlen regisztrációt.

- **Eszközregisztráció-kezelő** - Az Intune eszközregisztráció-kezelő funkciója lehetővé teszi, hogy a vezető vagy rendszergazda egyetlen felhasználói fiókkal több mobileszközt regisztráljon. Ezek az eszközök nem rendelkezhetnek felhasználói affinitással (azaz dedikált felhasználókkal), és regisztrálásuk a Vállalati portál alkalmazás telepítésével és az abba való bejelentkezéssel történik.

  > [!div class="button"]
  [iOS-eszközök regisztrálása a DEP segítségével >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS-eszközök közvetlen regisztrálása >>  ](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)[DEM-regisztráció >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## **Hogyan kezelheti a dedikált iOS-eszközeit?**

A vállalati eszközök az alábbi módokon regisztrálhatók dedikált felhasználókkal:

- **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökre regisztrációs profil telepíthető. Amikor a felhasználók először kapcsolják be az eszközt, az letölti a DEP-profilt és regisztrál az Intune-ban.

- **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt.

- **Megjelölés IMEI-számmal** - A vállalati eszközök nemzetközi mobilkészülék-azonosító számainak (IMEI) importálásával azokat vállalati eszközökként jelölheti meg az Intune-ban. A felhasználók ezután személyes eszközként regisztrálhatják az eszközeiket a Vállalati portál telepítésével, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és az adatok.

  > [!div class="button"]
  [Címkézés IMEI azonosítóval >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Beállítási asszisztens](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Címkézés IMEI azonosítóval](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Aug16_HO1-->


