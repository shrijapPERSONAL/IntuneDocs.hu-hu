---
title: "Üzletági Android-alkalmazások hozzáadása az Intune-hoz"
titlesuffix: Azure portal
description: "Útmutató az üzletági Android-alkalmazások Intune-ba való felvételéhez."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3d421889f5c271770c2c97fe37ff82cedc531985
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Androidos üzletági (LOB) alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>1. lépés – A szoftvertelepítő fájl megadása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** + **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget.

## <a name="step-2---configure-the-app-package-file"></a>2. lépés – az alkalmazáscsomag-fájl konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazáscsomag** fájlt.
2. Az **Alkalmazáscsomag** fájl panelen válassza a tallózás gombot, majd válasszon egy **.apk** kiterjesztésű androidos telepítési fájlt.
3. Ha elkészült, válassza az **OK** elemet.


## <a name="step-3---configure-app-information"></a>3. lépés – Az alkalmazás adatainak konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazáscsomag** fájlt.
2. Az **Alkalmazás adatai** panelen adja meg az alkalmazásadatokat. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Név** – Itt adhatja meg az alkalmazás céges portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a vállalati portálon.
    - **Leírás** – Adja meg az alkalmazás leírását, amelyet a felhasználók is láthatnak majd a céges portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Minimális operációsrendszer-verzió** – A listából kiválaszthatja az operációs rendszer legrégebbi olyan verzióját, amelyre az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerrel rendelkező eszközhöz rendelik hozzá, akkor nem lesz telepítve.
    - **Kategória** – Választhat egyet vagy többet a beépített kategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Így megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a vállalati portálon böngésző felhasználók számára.
3. Ha elkészült, válassza az **OK** elemet.

## <a name="step-4---finish-up"></a>4. lépés – befejezés

1. Az **Alkalmazás hozzáadása** panelen ellenőrizze az alkalmazás adatait.
2. Az alkalmazást a **Hozzáadás** elem kiválasztásával töltheti fel az Intune-ba.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).

## <a name="step-5---update-a-line-of-business-app"></a>5. lépés – üzletági alkalmazás frissítése

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)] Megjegyzés: Ahhoz, hogy az Intune szolgáltatás sikeresen üzembe tudja helyezni az új APK-fájlt az eszközön, az APK-csomagban található AndroidManifest.xml fájlban meg kell növelni az android:versionCode karakterlánc értékét

## <a name="next-steps"></a>További lépések

A létrehozott alkalmazás megjelenik az alkalmazáslistában. Mostantól hozzárendelheti az Ön által választott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).

További tájékoztató az alkalmazás jellemzőinek és hozzárendelési állapotának figyeléséről. További információt az [Alkalmazásinformációk és -hozzárendelések figyelése](apps-monitor.md) című témakörben talál.

További tudnivalók az Intune-beli alkalmazás környezetéről. További információt az [Eszközök és alkalmazások életciklusa](introduction-device-app-lifecycles.md) című témakörben talál.
