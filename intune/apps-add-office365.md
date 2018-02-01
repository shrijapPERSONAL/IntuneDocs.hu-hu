---
title: "Office 365-alkalmazások telepítése mobileszközökre az Intune-nal"
titlesuffix: Azure portal
description: "Annak ismertetése, hogyan egyszerűsíthető az Office 365-alkalmazások a Windows 10-es eszközökre való telepítése az Intune használatával."
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ee1657351551ea83c6089c5ac52655b9cd64fc2
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-office-365-proplus-2016-apps-to-windows-10-devices-with-microsoft-intune"></a>Office 365 ProPlus 2016-alkalmazások hozzárendelése Windows 10-es eszközökhöz a Microsoft Intune-nal

Ezzel az alkalmazástípussal könnyedén hozzárendelhet Office 365 ProPlus 2016-alkalmazásokat a Windows 10 rendszerű kezelt eszközökhöz. Emellett telepíthet alkalmazásokat a Microsoft Project Online asztali ügyfeléhez és a Microsoft Visio Pro for Office 365 szolgáltatáshoz is, amennyiben rendelkezik hozzájuk licenccel. A kívánt alkalmazások egyetlen bejegyzésként jelennek meg az Intune-konzol alkalmazáslistájában.


## <a name="before-you-start"></a>Előkészületek

>[!IMPORTANT]
>Az Office telepítésének ezen módja csak akkor támogatott, ha a Microsoft Office más verziói nincsenek telepítve az eszközön.

- Azokon az eszközökön, melyekre telepíti az alkalmazásokat, a Windows 10 alkotói frissítésének vagy újabb verziójának kell futnia.
- Az Intune csak az Office 365 ProPlus 2016 csomagból származó Office-alkalmazások hozzáadását támogatja.
- Ha bármely Office-alkalmazás meg van nyitva, amikor az Intune telepíti az alkalmazáscsomagot, előfordulhat, hogy elvesznek a végfelhasználók adatai a nem mentett fájlokból.
- Ez a telepítési mód Windows 10 S-eszközökön nincs támogatva.
- Az Intune nem támogatja az asztali Office 365-programok (más néven az Office Centennial-alkalmazások) Microsoft Áruházból történő telepítését olyan eszközök esetében, amelyekre korábban már telepítettek valamilyen Office 365-alkalmazást az Intune segítségével. Ha ezt a konfigurációt telepíti, az adatvesztést vagy adatsérülést okozhat.


## <a name="get-started"></a>Első lépések

1.  Jelentkezzen be az Azure Portal webhelyre.
2.  Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3.  Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
4.  A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5.  Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6.  Az **Alkalmazás felvétele** panelen válassza **Office 365 ProPlus Suite (Windows 10)** (Office 365 ProPlus-csomag (Windows 10)) lehetőséget.

## <a name="configure-the-app-suite"></a>Az alkalmazáscsomag konfigurálása

Ebben a lépésben választhatja ki az Office-alkalmazásokat, melyeket szeretne eszközökhöz hozzárendelni.

1.  Az **Alkalmazás felvétele** panelen válassza a **Configure App Suite** (Alkalmazáscsomag konfigurálása) lehetőséget.
2.  A **Configure App Suite** (Alkalmazáscsomag konfigurálása) panelen válassza ki a szokásos Office-alkalmazásokat, melyeket szeretne eszközökhöz hozzárendelni. Emellett telepíthet alkalmazásokat a Microsoft Project Online asztali ügyfeléhez és a Microsoft Visio Pro for Office 365 szolgáltatáshoz, amennyiben rendelkezik hozzájuk licenccel.
3.  Amikor elkészült, kattintson az **OK**gombra.

>[!IMPORTANT]
> Az alkalmazáscsomag létrehozása után annak tulajdonságai már nem szerkeszthetők. Ha eltérő tulajdonságokat szeretne beállítani, törölje az alkalmazáscsomagot, és hozzon létre egy újat.

## <a name="configure-app-information"></a>Az alkalmazásadatok konfigurálása

Ebben a lépésben adhatja meg az alkalmazáscsomag adatait. Ezen adatok alapján azonosíthatja azt az Intune-ban, és a végfelhasználónak is segítenek megtalálni azt a Céges portál alkalmazásban.

1.  Az **Alkalmazás felvétele** panelen válassza az **App Suite Information** (Alkalmazáscsomag adatai) elemet.
2.  Az **App Suite Information** (Alkalmazáscsomag adatai) panelen adja meg az alábbi adatokat:
    - **Suite Name** (Csomag neve) – Itt adhatja meg az alkalmazáscsomag a céges portálon megjelenő nevét. Ügyeljen arra, hogy minden megadott csomagnév egyedi legyen. Ha ugyanazt a csomagnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    - **Suite Description** (Csomag leírása) – Itt adhatja meg az alkalmazáscsomag leírását. Felsorolhatja például a kiválasztott belefoglalt alkalmazásokat.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Kategória** – Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Így megkönnyítheti a felhasználók számára az alkalmazáscsomag megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazáscsomagot a Céges portál főoldalán az alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon feltöltése** – Feltölthet egy ikont, mely megjelenik az alkalmazással a céges portálon böngésző felhasználók számára.
3.  Amikor elkészült, kattintson az **OK**gombra.

## <a name="configure-app-settings"></a>Alkalmazásbeállítások konfigurálása

Ebben a lépésben az alkalmazáscsomag telepítési beállításait konfigurálhatja. A beállítások minden, a csomaghoz hozzáadott alkalmazásra vonatkoznak.

1.  Az **Alkalmazás felvétele** panelen válassza az **App Suite Settings** (Alkalmazáscsomag beállításai) elemet.
2.  Az **App Suite Settings** (Alkalmazáscsomag beállításai) panelen adja meg az alábbi adatokat:
    - **Office-verzió** – Itt választhatja ki, hogy az Office 32 bites vagy 64 bites verzióját szeretné hozzárendelni. A 32 bites verziót 32 bites és 64 bites eszközökön is, a 64 bites verziót viszont csak 64 bites eszközökön telepítheti.
    - **Frissítési csatorna** – Itt választhatja ki, hogyan történjen az Office frissítése az eszközökön. A különböző frissítési csatornákkal kapcsolatban az Overview of update channels for Office 365 ProPlus (Az Office 365 ProPlus frissítési csatornáinak áttekintése) című témakörben találhat további információt. A következő lehetőségek közül választhat:
        - **Aktuális**
        - **Késleltetett**
        - **Első kiadáshoz tartozó aktuális**
        - **Első kiadáshoz tartozó késleltetett**
    - **Automatically accept the app end user license agreement** (Az alkalmazás végfelhasználói licencszerződésének automatikus elfogadása) – Ezt a beállítást akkor jelölje be, ha nem követeli meg a végfelhasználóktól, hogy elfogadják a licencszerződést. Ebben az esetben az Intune automatikusan elfogadja a szerződést.
    - **Use shared computer activation** (Megosztott aktiválás használata) – A megosztott aktiválás akkor használatos, amikor több felhasználó használja ugyanazt a számítógépet. További információt az Overview of shared computer activation for Office 365 ProPlus (Az Office 365 ProPlus megosztott aktiválásának áttekintése) című témakörben találhat.
    - **Nyelvek** – Az Office automatikusan telepít minden támogatott nyelvet, mely telepítve van a Windowsban a végfelhasználói eszközön. Ezt a beállítást akkor jelölje be, ha az alkalmazáscsomaghoz további nyelveket szeretne telepíteni.

>[!IMPORTANT]
> Az alkalmazáscsomag létrehozása után annak tulajdonságai már nem szerkeszthetők. Ha eltérő tulajdonságokat szeretne beállítani, törölje az alkalmazáscsomagot, és hozzon létre egy újat.

## <a name="finish-up"></a>Befejezés

Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza a **Mentés** lehetőséget. A létrehozott alkalmazás megjelenik az alkalmazáslistában.

## <a name="error-codes-when-installing-the-app-suite"></a>Az alkalmazáscsomag telepítése során megjelenő hibakódok

Az alábbi táblázatban az esetlegesen megjelenő gyakori hibakódok és azok jelentése található meg.

### <a name="status-for-office-csp"></a>Az Office felhőszolgáltatójának állapota:

||||
|-|-|-|
|Állapot|Fázis|Description|
|1460 (ERROR_TIMEOUT)|Letöltés|Nem sikerült letölteni az Office-telepítő eszközt|    
|13 (ERROR_INVALID_DATA)|-|Nem sikerült ellenőrizni a letöltött Office-telepítő eszköz aláírását|
|A CertVerifyCertificateChainPolicy függvény által visszaadott hibakód|-|Nem sikerült a letöltött Office-telepítő eszköz hitelesítési ellenőrzése|    
|997|WIP|Telepítés|
|0|Telepítés után|A telepítés sikeres volt|    
|1603 (ERROR_INSTALL_FAILURE)|-|Egy előfeltétel ellenőrzése sikertelen volt, például:<br>-SxS (Kísérlet a telepítésre, miközben a 2016-os MSI telepítve van)<br>- verzióeltérés<br>- stb.|     
|0x8000ffff (E_UNEXPECTED)|-|Kísérlet történt az eltávolításra, miközben a számítógépen nem található meg az Office Kattintásra.|    
|17002|-|Nem sikerült befejezni a forgatókönyv végrehajtását (telepítés). Lehetséges okok:<br>- A felhasználó megszakította a telepítést<br>- Egy másik telepítés szakította meg a telepítést<br>- A telepítés során elfogyott a lemezterület<br>- Ismeretlen nyelvi azonosító|
|17004|-|Ismeretlen termékváltozatok|   


### <a name="office-deployment-tool-error-codes"></a>Az Office-telepítő eszköz hibakódjai

|||||
|-|-|-|-|
|Forgatókönyv|Visszatérési kód|Felhasználói felület|Megjegyzés|
|Kísérlet történt az eltávolításra, miközben nincs aktív Kattintásra-telepítés|-2147418113, 0x8000ffff vagy 2147549183|Hibakód: 30088-1008<br>Hibakód: 30125-1011 (404)|Office-telepítő eszköz|
|Telepítés, miközben telepítve van az MSI-verzió|1603|-|Office-telepítő eszköz|
|A felhasználó vagy egy másik telepítés megszakította a telepítést|17002|-|Kattintásra|
|Kísérlet a 64 bites verzió telepítésére egy olyan eszközön, amelyen telepítve van a 32 bites verzió.|1603|-|Az Office-telepítő eszköz visszatérési kódja|
|Kísérlet egy ismeretlen termékváltozat telepítésére (az Office-felhőszolgáltató esetében ez nem valós használati eset, mivel csak érvényes termékváltozatokat lehet beküldeni)|17004|-|Kattintásra|
|Nincs elegendő szabad terület|17002|-|Kattintásra|
|Nem sikerült elindítani a Kattintásra-ügyfelet (váratlan)|17000|-|Kattintásra|
|A Kattintásra-ügyfélnek nem sikerült várólistára helyeznie a forgatókönyvet (váratlan)|17001|-|Kattintásra|

## <a name="next-steps"></a>További lépések

Mostantól hozzárendelheti az alkalmazásokat a kiválasztott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](/intune-azure/manage-apps/deploy-apps).
