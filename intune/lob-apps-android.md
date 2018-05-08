---
title: Androidos üzletági alkalmazások hozzáadása a Microsoft Intune-hoz
titlesuffix: ''
description: Az Androidos üzletági (LOB) alkalmazások a Microsoft Intune-hoz való hozzáadásának ismertetése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bd9d39373bc01cecd38c2fdbc675ca26861eb968
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="add-an-android-line-of-business-app-to-microsoft-intune"></a>Androidos üzletági alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az üzletági (LOB) alkalmazásokat egy alkalmazástelepítő fájlból adja hozzá az Intune-hoz. Az ilyen alkalmazásokat általában házon belül írják. Az Intune telepíti az üzletági alkalmazást a felhasználó eszközén. 

> [!Note]
> A Google Play for Work áruház üzletági alkalmazásairól [A Google Play for Work áruházból származó üzletági alkalmazások használata](apps-add-android-for-work.md?#working-with-a-line-of-business-app-from-the-google-play-for-work-store) című cikkben találhat további információt. 

## <a name="step-1-specify-the-software-setup-file"></a>1. lépés: A szoftvertelepítő fájl megadása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget.

## <a name="step-2-configure-the-app-package-file"></a>2. lépés: Az alkalmazáscsomag-fájl konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazáscsomag-fájl** lehetőséget.
2. Az **Alkalmazáscsomag-fájl** panelen válassza a tallózás gombot. Ez után válasszon ki egy **.apk** kiterjesztésű Android-telepítőfájlt.
3. Amikor végzett, válassza az **OK** gombot.


## <a name="step-3-configure-app-information"></a>3. lépés: Az alkalmazás adatainak konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazásadatok** lehetőséget.
2. Az **Alkalmazás adatai** panelen adja meg az alkalmazásadatokat. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen.
    - **Név**: Itt adhatja meg az alkalmazás a Céges portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a Céges portálon.
    - **Leírás**: Itt adhatja meg az alkalmazás leírását. A leírás megjelenik a Céges portálon.
    - **Kiadó**: Adja meg az alkalmazás kiadójának nevét.
    - **Minimális operációsrendszer-verzió**: A listából kiválaszthatja az operációs rendszer legkorábbi olyan verzióját, amelyre az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerrel rendelkező eszközhöz rendelik hozzá, akkor nem lesz telepítve.
    - **Alkalmazásverzió figyelmen kívül hagyása**: Állítsa **Igen** értékre, ha az alkalmazást automatikusan frissíti annak fejlesztője.
    - **Kategória**: Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. A kategóriákkal megkönnyítheti a felhasználók számára az alkalmazás megkeresését a Céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon**: Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím:** Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Az URL-cím megjelenik a Céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe:** Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Az URL-cím megjelenik a Céges portálon.
    - **Fejlesztő**: Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Igény esetén megadhatja az alkalmazás tulajdonosának nevét. Például **HR részleg**.
    - **Megjegyzések**: Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon**: Itt töltheti fel az alkalmazáshoz társított ikont. Ez az ikon jelenik meg az alkalmazásnál a Céges portálon böngésző felhasználók számára.
3. Amikor végzett, válassza az **OK** gombot.

## <a name="step-4-finish-up"></a>4. lépés: Befejezés

1. Az **Alkalmazás hozzáadása** panelen ellenőrizze, hogy helyesek-e az alkalmazáshoz megadott információk.
2. Az alkalmazást a **Hozzáadás** elem kiválasztásával töltheti fel az Intune-ba.

A létrehozott alkalmazás ekkor megjelenik az alkalmazások listájában. A listából hozzárendelheti az alkalmazást a választott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).

## <a name="step-5-update-a-line-of-business-app"></a>5. lépés: Üzletági alkalmazás frissítése

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note]
> Ahhoz, hogy az Intune szolgáltatás sikeresen üzembe tudja helyezni az új APK-fájlt az eszközön, az APK-csomagban található AndroidManifest.xml fájlban meg kell növelni az `android:versionCode` karakterlánc értékét.

## <a name="next-steps"></a>További lépések

- A létrehozott alkalmazás megjelenik az alkalmazások listájában. Mostantól hozzárendelheti az Ön által választott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).

- További tájékoztató az alkalmazás jellemzőinek és hozzárendelési állapotának figyeléséről. Lásd: [Alkalmazásadatok és -hozzárendelések figyelése](apps-monitor.md).

- További tudnivalók az Intune-beli alkalmazás környezetéről. Lásd: [Az eszközök és alkalmazások életciklusának áttekintése](introduction-device-app-lifecycles.md).
