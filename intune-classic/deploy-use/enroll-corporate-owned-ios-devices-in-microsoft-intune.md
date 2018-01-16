---
title: "A vállalat által birtokolt iOS-eszközök regisztrálása"
description: "A vállalat által birtokolt iOS-eszközök regisztrálása az Apple Device Enrollment program (DEP) vagy az Apple Configurator eszköz segítségével"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 15f549970494174d4f0764472f313f93b11f32a2
ms.sourcegitcommit: 229f9bf89efeac3eb3d28dff01e9a77ddbf618eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/05/2018
---
# <a name="enroll-corporate-owned-ios-devices-in-microsoft-intune"></a>A vállalat által birtokolt iOS-eszközök regisztrálása a Microsoft Intune-ban[1502]

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune támogatja a vállalat által birtokolt iOS-eszközök regisztrálását az Apple Device Enrollment Program (DEP) vagy a Mac számítógépeken futó [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) eszköz segítségével.

**Előfeltétel:** [Apple Push Notification szolgáltatásbeli tanúsítvány](set-up-ios-and-mac-management-with-microsoft-intune.md)

A vállalat által birtokolt iOS-eszközöket háromféleképpen lehet regisztrálni:

- Apple Configurator, beállítási asszisztens vagy közvetlen regisztráció
- Készülékregisztrációs program
- Vállalati portál alkalmazás

>[!NOTE]
>Az Apple Configurator és az Eszközök beléptetése program regisztrációs módszerei nem használhatók az [eszközregisztráció-kezelői](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) módszerrel.

Alapértelmezés szerint minden iOS-eszköz regisztrációja engedélyezett az Intune-ban. A személyes vagy vállalati tulajdonú eszközök regisztrációjának letiltásához jelentkezzen be a [Microsoft Intune felügyeleti portálra](https://manage.microsoft.com) a rendszergazdai hitelesítő adataival. Válassza a **Felügyelet** > **Mobileszköz-kezelés** > **Regisztráció szabályai** elemet, majd törölje a megfelelő beállítások jelölőnégyzeteit.

## <a name="use-apple-configurator"></a>Az Apple Configurator használata

Az iOS-eszközök egy Vállalati regisztrációs profil exportálásával, majd a mobileszközök egy Apple Configurator eszközt futtató Mac számítógéphez való csatlakoztatásával regisztrálhatók. Az Apple Configurator a regisztráció két formáját támogatja:

- **Regisztrálás a Beállítási asszisztenssel**: Gyári alaphelyzetbe állítja az eszközt, és felkészíti a beállításhoz az új felhasználó számára. Ennél a módszernél a rendszergazdának a regisztráció előkonfigurálásához az iOS-eszközt USB kapcsolaton keresztül egy [Apple Configuratort](https://go.microsoft.com/fwlink/?LinkId=518017) futtató Mac számítógéphez kell csatlakoztatnia. Az eszközöket ekkor el kell juttatni a felhasználókhoz, akik elindítják a Beállítási asszisztenst. A folyamat a felhasználók munkahelyi vagy iskolai azonosítójával konfigurálja az eszközt, és elvégzi a regisztrációt. További információt az [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével](ios-setup-assistant-enrollment-in-microsoft-intune.md) című témakörben találhat.

- **Közvetlen regisztrálás**: Létrejön egy Apple Configurator-kompatibilis fájl, amely az eszköz előkészítésez szükséges. A regisztrált eszköz nincs gyári alaphelyzetbe állítva, de egyetlen felhasználóhoz sem kapcsolódik. Ennél a módszernél a rendszergazdának az iOS-eszköz regisztrálásához az eszközt USB kapcsolaton keresztül egy [Apple Configuratort](https://go.microsoft.com/fwlink/?LinkId=518017) futtató Mac számítógéphez kell csatlakoznia. További információt az [iOS-eszközök közvetlen regisztrálása az Apple Configurator használatával](ios-direct-enrollment-in-microsoft-intune.md) című témakörben találhat.

## <a name="use-the-device-enrollment-program-dep"></a>A Device Enrollment Program (DEP) használata
A DEP a DEP-en keresztül megvásárolt eszközökre egy regisztrációs profilt telepít. Amikor a felhasználó a Beállítási asszisztenst futtatja az eszközön, az eszköz regisztrációja az Intune-ban rögzül. További információt az [A készülékregisztrációs programban részt vevő vállalati iOS-eszközök regisztrálása](ios-device-enrollment-program-in-microsoft-intune.md) című témakörben találhat.

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



### <a name="see-also"></a>Lásd még:
[A Microsoft Intune-beli eszközregisztráció előfeltételei](prerequisites-for-enrollment.md)
