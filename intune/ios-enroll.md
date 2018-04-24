---
title: Az iOS-eszközök regisztrálási módjának kiválasztása az Intune-ban
titlesuffix: Microsoft Intune
description: iOS-eszközök a Microsoft Intune-ban való regisztrációjának beállítása.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01523dc4c887214794d4600219ce0b77549b4734
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-ios-devices-in-intune"></a>iOS-eszközök regisztrálása az Intune-ban

Az Intune lehetőséget nyújt az iPadek és iPhone-ok mobileszköz-felügyeletére (MDM), és hozzáférést biztosít a felhasználóknak a vállalati e-mailjeikhez és alkalmazásaikhoz.

Intune-rendszergazdaként engedélyezheti az iOS-eszközök regisztrációját. Engedélyezheti a felhasználók számára a személyes tulajdonban lévő eszközök regisztrálását, azaz a BYOD-regisztrációt. Emellett vállalati tulajdonban lévő eszközök is regisztrálását is engedélyezheti.

## <a name="prerequisites-for-ios-enrollment"></a>Az iOS eszközök beléptetésének előfeltételei
iOS-eszközök engedélyezése előtt végezze el az alábbi lépéseket:
- [Az Intune beállítása](setup-steps.md) – Ezekkel a lépésekkel állíthatja be az Intune-infrastruktúrát. Különösen fontos, hogy az eszközregisztrációhoz szükség van [saját MDM-szolgáltató beállítására](mdm-authority-set.md).
- [Apple MDM push-tanúsítvány beszerzése](apple-mdm-push-certificate-get.md) – Az Apple tanúsítványt igényel az iOS- és macOS eszközök felügyeletének lehetővé tételéhez.

## <a name="user-owned-ios-devices-byod"></a>A felhasználó tulajdonában lévő iOS-eszközök (BYOD)

Azt is engedélyezheti, hogy a felhasználók saját személyes eszközeiket regisztrálják az Intune-felügyelethez. Ezt „saját eszköz használata” vagy BYOD (Bring Your Own Device) néven ismerjük. Az előfeltételek teljesítése és a felhasználói licencek hozzárendelése után a felhasználók letölthetik az Intune Céges portál alkalmazást az App Store-ból, és az alkalmazástól kapott utasításokat követve elvégezhetik a regisztrációt.

## <a name="company-owned-ios-devices"></a>Vállalati tulajdonban lévő iOS-eszközök
A felhasználóknak eszközöket vásárló szervezetek számára az Intune a következő módszereket támogatja a vállalati tulajdonban lévő iOS-eszközök regisztrálásához:

- Az Apple készülékregisztrációs programja (DEP)
- Apple School Manager
- Regisztrálás az Apple Configurator és a Beállítási asszisztens segítségével
- Apple Configurator – közvetlen regisztráció

A vállalati tulajdonban lévő iOS-eszközök [készülékregisztráció-kezelő](device-enrollment-manager-enroll.md) fiók használatával is regisztrálhatók.

## <a name="device-enrollment-program"></a>Készülékregisztrációs program
A szervezetek az Apple Device Enrollment készülékregisztrációs programján keresztül vásárolhatnak iOS-eszközöket. A DEP vezeték nélkül képes telepíteni egy regisztrációs profilt, amely felügyelet alá helyezi az eszközöket. További tudnivalók a [Készülékregisztrációs programról](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Az Apple School Manager egy eszközvásárlási és -regisztrációs program iskolák részére. A DEP-hez hasonlóan lehetőséget nyújt egy profil üzembe helyezésére az eszközök felügyeletben történő regisztrálásához. További információ az [Apple School Manager](apple-school-manager-set-up-ios.md) programról.

## <a name="apple-configurator"></a>Apple Configurator
iOS-eszközök regisztrálhatók a Mac számítógépen futó Apple Configuratorral is. Az eszközök előkészítéséhez csatlakoztassa őket USB-kapcsolaton keresztül, és telepítsen regisztrációs profilt. Az Apple Configurator használatával kétféle módon lehet regisztrálni az eszközöket:
- Regisztrálás a Beállítási asszisztenssel – ez a folyamat visszaállítja az eszközt gyári alaphelyzetbe, felkészíti az eszközt a Beállítási asszisztens futtatására, és telepíti a cég szabályzatait az eszköz új felhasználójának.
- Közvetlen regisztrálás – ez a folyamat nem állítja vissza az eszközt gyári alaphelyzetbe, és előre definiált szabályzattal regisztrálja azt. A módszer felhasználói affinitás nélküli eszközökkel használható.

További információ az [Apple Configurator-regisztrációról](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>A Vállalati portál használata a DEP vagy az Apple Configurator által regisztrált eszközökkel

A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez. Miután a felhasználók megkapják az eszközeiket, több további lépést kell végrehajtaniuk a Beállítási asszisztens befejezéséhez és a Vállalati portál alkalmazás telepítéséhez.

Felhasználói affinitás szükséges az alábbiak támogatásához:
  - Mobilalkalmazás-felügyeleti (MAM) alkalmazások
  - Feltételes hozzáférés az e-mailekhez és a vállalati adatokhoz
  - Vállalati portál alkalmazás

**A vállalat által birtokolt iOS-eszközök regisztrálása felhasználói affinitás használatával**
1. Amikor a felhasználók bekapcsolják az eszközüket, megjelenik a Beállítási asszisztens befejezését kérő üzenet. A telepítés során a rendszer kéri a felhasználóktól a hitelesítő adataik megadását. A felhasználóknak az Intune-előfizetésükhöz tartozó hitelesítő adataikat (vagyis az egyedi felhasználónevüket vagy az egyszerű felhasználónevüket) kell megadniuk.

2. A telepítés során a rendszer kéri a felhasználóktól az Apple ID azonosítójuk megadását. Az Apple ID azonosítót azért kell megadni, hogy az eszköz telepíthesse a Vállalati portál alkalmazást. Az azonosítót a telepítés után, az iOS-beállítások menüben is megadhatják.

3. A telepítés befejezése után az iOS-eszközön telepíteni kell a Vállalati portál alkalmazását az App Store áruházból.

4. A felhasználó ekkor bejelentkezhet a Vállalati portál alkalmazásba az eszköz beállításakor megadott egyszerű felhasználónév használatával.

5. A bejelentkezés után a rendszer kéri a felhasználótól az eszköz regisztrálását. Ennek első lépése az eszköz azonosítása. Az alkalmazás megjeleníti azon iOS-eszközök listáját, amelyek már a vállalat tulajdonában vannak, és amelyek hozzá vannak rendelve a felhasználók Intune-fiókjához. A felhasználónak ki kell választania a megfelelő eszközt.

   Ha az eszköz még nincs regisztrálva a vállalatnál, a normál regisztrálási művelet folytatásához a felhasználó válassza az **új eszköz** lehetőséget.

6. A következő képernyőn a felhasználónak meg kell erősítenie az új eszköz sorozatszámát. A felhasználó a **sorozatszám megerősítése** hivatkozásra koppinthat, és ezzel megnyithatja a beállítási alkalmazás a sorozatszám ellenőrzéséhez való használatára vonatkozó útmutatást. A felhasználónak ezután meg kell adnia a sorozatszám utolsó négy számjegyét a Vállalati portál alkalmazásban.

   Ez a lépés azt ellenőrzi, hogy az eszköz az Intune-ban regisztrált vállalati eszköz-e. Ha az eszközön található sorozatszám nem egyezik, nem a megfelelő eszköz választotta ki. A felhasználónak ekkor vissza kell lépnie az előző képernyőre, és ki kell választania egy másik eszközt.

7. A sorozatszám ellenőrzése után a Vállalati portál alkalmazás átirányítja a felhasználót a Vállalati portál webhelyre a regisztrálás véglegesítéséhez. Ekkor a webhely felajánlja a lehetőséget, hogy visszatérjen az alkalmazáshoz.

8. Ezzel befejeződött a regisztráció. Ezután a felhasználó az összes funkciójával együtt használhatja az eszközt.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>A felhasználói affinitás nélküli vállalati tulajdonú eszközök áttekintése

A felhasználói affinitás nélkül konfigurált eszközök nem támogatják a Vállalati portált, ezért ezekre az eszközökre ne telepítse az alkalmazást. A Vállalati portál az olyan felhasználók számára készült, akik rendelkeznek vállalati hitelesítő adatokkal, és hozzá kell férniük a személyre szabott vállalati erőforrásokhoz (pl. az e-mailhez). A felhasználói affinitás nélkül regisztrált eszközökhöz nem tartozhat dedikált felhasználói bejelentkezés. A felhasználói affinitás nélkül regisztrált eszközök jellemző példái közé tartoznak a kioszkok, a pénztári eszközök (POS) és a megosztott segédeszközök.

Ha szükség van a felhasználói affinitásra, az eszköz regisztrálása előtt adja meg a **Felhasználói affinitás** beállítást az eszközregisztrációs profilban. Ha egy eszközön módosítani kell az affinitási állapotot, ki kell vonnia az eszközt, majd újból regisztrálnia kell.

