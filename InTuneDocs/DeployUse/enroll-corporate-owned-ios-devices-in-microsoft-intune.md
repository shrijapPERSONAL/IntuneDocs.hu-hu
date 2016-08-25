---
title: "A vállalat által birtokolt iOS-eszközök regisztrálása | Microsoft Intune"
description: "A vállalat által birtokolt iOS-eszközök regisztrálása az Apple eszközregisztrációs program (DEP) vagy az Apple Configurator eszköz segítségével"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9b7b8f6e5182e228458f5ea75e804a638f1e2a2b
ms.openlocfilehash: ca05e94e72269c11db24b667f1d113c794cd8b23


---

# A vállalat által birtokolt iOS-eszközök regisztrálása a Microsoft Intune-ban[1502]
A Microsoft Intune támogatja a vállalat által birtokolt iOS-eszközök regisztrálását az Apple Device Enrollment Program (DEP) vagy a Mac számítógépeken futó [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) eszköz segítségével.

**Előfeltétel:** [Apple Push Notification szolgáltatásbeli tanúsítvány](set-up-ios-and-mac-management-with-microsoft-intune.md)

A vállalat által birtokolt iOS-eszközöket háromféleképpen regisztrálhatja:

-   **Apple Configurator** – Az iOS-eszközök regisztrálhatók egy Vállalati regisztrációs profil exportálásával, majd a mobileszközök csatlakoztatásával egy Apple Configurator eszközt futtató Mac számítógéphez. Az Apple Configurator a regisztráció két formáját támogatja:

    - **Regisztráció a telepítő segéddel** – A gyár állítja alaphelyzetbe az eszközt, és felkészíti a beállításhoz az új felhasználó számára. Ennél a módszernél a rendszergazdának a regisztráció előkonfigurálásához az iOS-eszközt USB kapcsolaton keresztül egy [Apple Configuratort](http://go.microsoft.com/fwlink/?LinkId=518017) futtató Mac számítógéphez kell csatlakoztatnia. Az eszközök ezután a felhasználóikhoz kerülnek, akik a Beállítási asszisztens folyamatának futtatása során munkahelyi vagy iskolai hitelesítő adataikkal konfigurálják az eszközt, és befejezik a regisztrációs folyamatot. [Apple Configuratort és Beállítási asszisztenst futtató iOS-eszközök regisztrálása](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Közvetlen regisztrálás** – Létrejön egy Apple Configurator-kompatibilis fájl, amely az eszköz előkészítésez szükséges. A regisztrált eszköz nincs gyári alaphelyzetbe állítva, de egyetlen felhasználóhoz sem kapcsolódik. Ennél a módszernél a rendszergazdának az iOS-eszköz regisztrálásához az eszközt USB kapcsolaton keresztül egy [Apple Configuratort](http://go.microsoft.com/fwlink/?LinkId=518017) futtató Mac számítógéphez kell csatlakoznia. [Az Apple Configurator közvetlen regisztrációját használó iOS-eszközök regisztrálása](ios-direct-enrollment-in-microsoft-intune.md)

-   **Készülékregisztrációs program (DEP)** – Vezeték nélkül telepít egy regisztrációs profilt az Apple készülékregisztrációs programjában megvásárolt készülékekre. Amikor a felhasználó a Beállítási asszisztenst futtatja az eszközön, az eszköz regisztrálódik az Intune-ban.  A DEP programon keresztül regisztrált eszközök regisztrációját a felhasználók nem törölhetik. [A készülékregisztrációs programban (DEP) részt vevő iOS-eszközök regisztrálása](ios-device-enrollment-program-in-microsoft-intune.md)

## A vállalati portál használata a DEP vagy az Apple Configurator által regisztrált eszközökkel

A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez. Miután a felhasználók megkapják az eszközeiket, több további lépést kell végrehajtaniuk a telepítősegéd befejezéséhez és a Vállalati portál alkalmazás telepítéséhez.

A vállalat által birtokolt iOS-eszközök regisztrálása felhasználói affinitás használatával
1. Amikor a felhasználók bekapcsolják az eszközüket, megjelenik a telepítősegéd befejezését kérő üzenet. A telepítés során a rendszer kéri a felhasználóktól a hitelesítő adataik megadását. A felhasználóknak az Intune-előfizetésükhöz tartozó hitelesítő adataikat (vagyis az egyedi felhasználónevüket vagy az egyszerű felhasználónevüket) kell megadniuk.

2. A telepítés során a rendszer kéri a felhasználóktól az Apple ID azonosítójuk megadását. Az Apple ID azonosítót azért kell megadni, hogy az eszköz telepíthesse a Vállalati portál alkalmazást. Az Apple ID azonosító a telepítés befejezése után is megadható az iOS-beállítások menüjében.

3. A telepítés befejezése után az iOS-eszközön telepíteni kell a vállalati portál alkalmazását az App Store áruházból, például a Vállalati portál alkalmazást.

4. A felhasználó ekkor bejelentkezhet a Vállalati portál alkalmazásba az eszköz beállításakor megadott egyszerű felhasználónév használatával.

5. A bejelentkezés után a rendszer kéri a felhasználótól az eszköz regisztrálását. Ennek első lépése az eszköz azonosítása. Az alkalmazás megjeleníti azon iOS-eszközök listáját, amelyek már a vállalat tulajdonában vannak, és amelyek hozzá vannak rendelve a végfelhasználók Intune-fiókjához. Válassza ki a megfelelő eszközt.

  Ha az eszköz még nincs regisztrálva a vállalatnál, a normál regisztrálási művelet folytatásához válassza az „új eszköz” lehetőséget.

6. A következő képernyőn a felhasználónak meg kell erősítenie az új eszköz sorozatszámát. A felhasználó a „sorozatszám megerősítése” hivatkozásra koppintva indíthatja el a beállítási alkalmazást a sorozatszám ellenőrzéséhez. A felhasználónak ezután meg kell adnia a sorozatszám utolsó 4 számjegyét a Vállalati portál alkalmazásban.

  Ez a lépés azt ellenőrzi, hogy az eszköz az Intune-ban regisztrált vállalati eszköz-e. Ha az eszközön található sorozatszám nem egyezik, nem a megfelelő eszköz választotta ki. Lépjen vissza az előző képernyőre, és válasszon ki másik eszközt.

7. A sorozatszám ellenőrzése után a Vállalati portál alkalmazás átirányítja a felhasználót a Vállalati portál webhelyre a regisztrálás véglegesítéséhez, majd felszólítja a felhasználót az alkalmazáshoz való visszatérésre.

8. Ezzel befejeződött a regisztráció. Ezután az összes funkciójával együtt használhatja az eszközt.

### A felhasználói affinitás nélküli vállalati tulajdonú eszközök áttekintése

A felhasználói affinitás nélkül konfigurált eszközök nem támogatják a Vállalati portált, ezért ezekre az eszközökre ne telepítse az alkalmazást. A Vállalati portál az olyan felhasználók számára készült, akik rendelkeznek vállalati hitelesítő adatokkal, és hozzá kell férniük a személyre szabott vállalati erőforrásokhoz (pl. az e-mailhez). A felhasználói affinitás nélkül regisztrált eszközökhöz nem tartozhat dedikált felhasználói bejelentkezés. A felhasználói affinitás nélkül regisztrált eszközök jellemző példái közé tartoznak a kioszkok, a pénztári eszközök (POS) és a megosztott segédeszközök. Ha szükség van a felhasználói affinitásra, az eszköz regisztrálása előtt adja meg a Felhasználói affinitás beállítást az eszközregisztrációs profilban. Ha egy eszközön módosítani kell az affinitási állapotot, ki kell vonnia az eszközt, majd újból regisztrálnia kell.



### További információ
[Felkészülés az eszközök regisztrálására a Microsoft Intune-ban](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


