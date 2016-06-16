---
# required metadata

title: A mobileszközök regisztrálásának módjai | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# A mobileszközök regisztrálásának módjai

A mobileszköz regisztrálása az a folyamat, amely az okostelefonokat, a táblagépeket és a számítógépeket a menedzsment részévi teszi a Microsoft Intune segítségével. Rendszergazdaként el kell döntenie, hogy hogyan érdemes regisztrálni az eszközeit az alábbi szempontok alapján:

 -  Tulajdonjog (személyi vagy vállalati tulajdonban lévő eszköz)
 -  Használat (megosztott vagy személyes)
 -  Platform (iOS, Android, Windows Phone, Windows-számítógép, Mac számítógép)

Az alábbi kérdésekre adott válaszaiból megtudhatja, hogy melyik regisztrációs módszer felel meg a legjobban az Ön által kezelt eszközöknek.

## Az alkalmazottak saját eszközeiket használják, vagy a szervezet biztosítja nekik ezeket az erőforrásokat?

  **Felhasználók saját eszközei** – „BYOD-regisztráció” (Bring your own device – hozd a saját eszközöd) – A felhasználók telepítik az eszközeikre az Intune Vállalati portál alkalmazást, majd regisztrálják az eszközöket, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és adatok, valamint az ügyfélszolgálat.  
  > [!div class="button"]   [BYOD-regisztráció >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)

  **Vállalati eszközök** A vállalati tulajdonban lévő eszközök többféleképpen is regisztrálhatók a szervezet igényeitől és az eszközök típusától függően. Következő kérdés...

## A vállalati eszközök megosztott vagy egyéni használat alatt állnak?

**Megosztott vállalati eszközök** – Ezekhez az eszközökhöz több felhasználó is hozzáfér, és általában nem használhatók levelezésre. Ilyen eszköz például az interaktív terminál, vagy a feladatközpontú, egy helyen tárolt, közös használatú eszközök. Az ajánlott regisztrációs módszer az eszköz platformjától függ.

  - **Windows- és Android-eszközök** – A *készülékregisztráció-kezelő* egy olyan Intune-fiók, amelyen több megosztott eszközt is regisztrálhat a Vállalati portál alkalmazással.
  > [!div class="button"]   [Készülékregisztráció-kezelő >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **iOS-eszközök** – A megosztott iOS-eszközök háromféleképpen kezelhetők.  **Hogyan regisztrálja a megosztott iOS-eszközöket?**

    - **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökre regisztrációs profil telepíthető. Amikor a felhasználók először kapcsolják be az eszközt, az letölti a DEP-profilt és regisztrálja az eszközt
    > [!div class="button"]     [DEP-regisztráció >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune)

    - **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt. Ha nem szeretné a gyári beállításokat visszaállítani az eszközökön, használja Közvetlen regisztrációt.

    > [!div class="button"]     [Regisztráció a Beállítási asszisztenssel >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) vagy [Közvetlen regisztráció >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)

    - **Egyik sem** – Ha nem tudja vagy nem kívánja az Apple DEP- vagy az Apple Configurator-regisztrációt használni, használja az Intune készülékregisztráció-kezelőjét (Device Enrollment Manager – DEM).
    > [!div class="button"]     [DEM-regisztráció >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Egyéni felhasználók** – Az egyéni félhasználókkal rendelkező vállalati tulajdonban lévő eszközök egyszerre nyomon követendő vállalati eszközök és személyes eszközök, amelyről a felhasználók elérhetik e-mail postafiókjukat és adataikat. Az ajánlott regisztrációs módszer az eszköz platformjától függ.

  - **Windows- és Android-eszközök** – A vállalati eszközök IMEI-számainak importálásával vállalati eszközként jelölheti meg őket az Intune-ban. A felhasználók ezután személyes eszközként regisztrálhatják az eszközeiket a Vállalati portál telepítésével, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és az adatok.
  > [!div class="button"]   [Megjelölés IMEI-számokkal >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **iOS-eszközök** – A megosztott iOS-eszközök háromféleképpen kezelhetők.  **Hogyan regisztrálja a megosztott iOS-eszközöket?**

    - **Az Apple Készülékregisztrációs programja (Device Enrollment Program – DEP)** – A DEP-pel vásárolt vagy kezelt iOS-eszközökre regisztrációs profil telepíthető. Amikor a felhasználók először kapcsolják be az eszközt, az letölti a DEP-profilt és annak megfelelően regisztrálja az eszközt.
    > [!div class="button"]     [DEP-regisztráció](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Az Apple Configurator Mac számítógépen** – Az Apple Configurator egy Mac-számítógépekre tervezett Apple-alkalmazás. Az iOS-eszközeit egy USB-kábellel csatlakoztathatja a Mac-számítógéphez, majd feltelepítheti rájuk a regisztrációs profilt. Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt.

    Ha nem szeretné a gyári beállításokat visszaállítani az eszközökön, használja Közvetlen regisztrációt.
    Ha az eszközöket a gyári beállítások visszaállításával szeretné regisztrálni, használja a Beállítási asszisztenssel való regisztrációt.
    > [!div class="button"] [Regisztráció az iOS Beállítási asszisztenssel](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][iOS közvetlen regisztráció](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Egyik sem** – Ha nem tudja vagy nem kívánja az Apple DEP- vagy az Apple Configurator-regisztrációt használni, a vállalati eszközök IMEI-számának importálásával vállalati eszközként jelölheti meg az eszközöket az Intune-ban. A felhasználók ezután személyes eszközként regisztrálhatják az eszközeiket a Vállalati portál telepítésével, így hozzáférhetnek az olyan vállalati erőforrásokhoz, mint a levelezés, a vállalati alkalmazások és az adatok. > [!div class="button"][Eszközök megjelölése IMEI-számokkal](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO1-->


