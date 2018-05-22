---
title: Office 365-alkalmazások telepítése a Microsoft Intune használatával
titlesuffix: ''
description: Az Office 365-alkalmazások a Windows 10-es eszközökre való telepítésének egyszerűsítése a Microsoft Intune használatával.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11f1a48b5b2dcff421603dd4538ff054d174fe66
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/17/2018
---
# <a name="assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Office 365-alkalmazások hozzárendelése Windows 10-es eszközökhöz a Microsoft Intune-nal

Ezzel az alkalmazástípussal könnyedén hozzárendelhet Office 365-alkalmazásokat a Windows 10 rendszerű kezelt eszközökhöz. Emellett telepíthet alkalmazásokat a Microsoft Project Online asztali ügyfeléhez és a Microsoft Visio Pro for Office 365 szolgáltatáshoz is, amennyiben rendelkezik hozzájuk licenccel. A kívánt alkalmazások egyetlen bejegyzésként jelennek meg az Intune-konzol alkalmazáslistájában.


## <a name="before-you-start"></a>Előkészületek

>[!IMPORTANT]
>Az Office telepítésének ezen módja csak akkor támogatott, ha a Microsoft Office más verziói nincsenek telepítve az eszközön.

- Azokon az eszközökön, melyekre telepíti az alkalmazásokat, a Windows 10 alkotói frissítésének vagy újabb verziójának kell futnia.
- Az Intune csak az Office 365 csomagból származó Office-alkalmazások hozzáadását támogatja.
- Ha bármely Office-alkalmazás meg van nyitva, amikor az Intune telepíti az alkalmazáscsomagot, előfordulhat, hogy a telepítés sikertelen lesz, és elvesznek a végfelhasználók adatai a nem mentett fájlokból.
- Ez a telepítési mód nincs támogatva Windows 10 S, Windows Home, Windows Team, Windows Holographic és Windows Holographic for Business rendszert futtató eszközökön.
- Az Intune nem támogatja az asztali Office 365-programok (más néven az Office Centennial-alkalmazások) Microsoft Áruházból történő telepítését olyan eszközök esetében, amelyekre korábban már telepítettek valamilyen Office 365-alkalmazást az Intune segítségével. Ha ezt a konfigurációt telepíti, az adatvesztést vagy adatsérülést okozhat.
- Több kötelező vagy elérhető alkalmazás-hozzárendelés nem adódik össze. A későbbi alkalmazás-hozzárendelés felülírja a már meglévő alkalmazás-hozzárendeléseket. Ha például az első Office-alkalmazáscsomag tartalmazta a Wordöt, de az újabb már nem, akkor a Word el lesz távolítva. Ez a feltétel a Visio- és Project-alkalmazásokra nem vonatkozik.


## <a name="get-started"></a>Első lépések

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Mobilalkalmazások** lehetőséget.
4. A **Mobilalkalmazások** munkaterületen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Válassza a **Hozzáadás** elemet.
6. Az **Alkalmazások hozzáadása** ablaktáblán, az **Alkalmazástípus** listában, az **Office 365 Office** alatt válassza a **Windows 10** lehetőséget.

Mostantól konfigurálhatja az alkalmazáscsomagot.

## <a name="configure-the-app-suite"></a>Az alkalmazáscsomag konfigurálása

Válassza ki azokat az Office-alkalmazásokat, melyeket szeretne eszközökhöz hozzárendelni.

1. Az **Alkalmazás felvétele** ablaktáblán válassza az **Alkalmazáscsomag konfigurálása** lehetőséget.
2. Az **Alkalmazáscsomag konfigurálása** ablaktáblán válassza ki a szokásos Office-alkalmazásokat, melyeket szeretne eszközökhöz hozzárendelni.  
    Emellett telepíthet alkalmazásokat a Microsoft Project Online asztali ügyfeléhez és a Microsoft Visio Pro for Office 365 szolgáltatáshoz, amennyiben rendelkezik hozzájuk licenccel.
3. Válassza az **OK** gombot.

>[!IMPORTANT]
> Az alkalmazáscsomag létrehozása után annak tulajdonságai már nem szerkeszthetők. Ha eltérő tulajdonságokat szeretne beállítani, törölje az alkalmazáscsomagot, és hozzon létre egy újat.

## <a name="configure-app-information"></a>Az alkalmazásadatok konfigurálása

Ebben a lépésben adhatja meg az alkalmazáscsomag adatait. Ezek alapján azonosíthatja az alkalmazáscsomagot az Intune-ban, és a felhasználók is ezek alapján találhatják meg azt a céges portálon.

1. Az **Alkalmazás hozzáadása** ablaktáblán válassza az **Alkalmazáscsomag adatai** lehetőséget.
2. Az **Alkalmazáscsomag adatai** ablaktáblán tegye a következőket:
    - **Csomag neve:** Itt adhatja meg az alkalmazáscsomag céges portálon megjelenő nevét. Ügyeljen arra, hogy minden megadott csomagnév egyedi legyen. Ha ugyanazt a csomagnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    - **Csomag leírása:** Itt adhatja meg az alkalmazáscsomag leírását. Felsorolhatja például a kiválasztott belefoglalt alkalmazásokat.
    - **Kiadó:** Adja meg az alkalmazás kiadójának nevét.
    - **Kategória:** Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ez a beállítás megkönnyíti a Céges portálon kereső felhasználóknak az alkalmazás megtalálását.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon:** Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazáscsomagot a céges portál főoldalán az alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím:** Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe:** Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő**: Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például *HR-osztály*).
    - **Megjegyzések**: Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Logó**: Töltsön fel egy ikont, mely megjelenik az alkalmazással a céges portálon böngésző felhasználók számára.
3. Válassza az **OK** gombot.

## <a name="configure-app-settings"></a>Alkalmazásbeállítások konfigurálása

Ebben a lépésben az alkalmazáscsomag telepítési beállításait konfigurálhatja. A beállítások minden, a csomaghoz hozzáadott alkalmazásra vonatkoznak.

1. Az **Alkalmazás hozzáadása** ablaktáblán válassza az **Alkalmazáscsomag beállításai** lehetőséget.
2. Az **Alkalmazáscsomag beállításai** ablaktáblán tegye a következőket:
    - **Office-verzió**: Itt választhatja ki, hogy az Office 32 bites vagy 64 bites verzióját szeretné hozzárendelni. A 32 bites verziót 32 bites és 64 bites eszközökön is, a 64 bites verziót viszont csak 64 bites eszközökön telepítheti.
    - **Frissítési csatorna**: Itt választhatja ki, hogyan történjen az Office frissítése az eszközökön. A különböző frissítési csatornákkal kapcsolatban az [Office 365 ProPlus frissítési csatornáinak áttekintése](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) című témakörben találhat további információt. A következő lehetőségek közül választhat:
        - **Havonta**
        - **Havonta (megcélzott)**
        - **Semi-Annual**
        - **Féléves (megcélzott)**
    - **Alkalmazás végfelhasználói licencszerződésének automatikus elfogadása**: Ezt a beállítást akkor jelölje be, ha nem követeli meg a végfelhasználóktól, hogy elfogadják a licencszerződést. Ebben az esetben az Intune automatikusan elfogadja a szerződést.
    - **Megosztott aktiválás használata**: A megosztott aktiválás akkor használatos, amikor több felhasználó használja ugyanazt a számítógépet. További információt az Overview of shared computer activation for Office 365 (Az Office 365 megosztott aktiválásának áttekintése) című témakörben találhat.
    - **Nyelvek**: Az Office automatikusan telepít minden támogatott nyelvet, mely telepítve van a Windowsban a végfelhasználói eszközön. Ezt a beállítást akkor jelölje be, ha az alkalmazáscsomaghoz további nyelveket szeretne telepíteni.

>[!IMPORTANT]
> Az alkalmazáscsomag létrehozása után annak tulajdonságai már nem szerkeszthetők. Ha eltérő tulajdonságokat szeretne beállítani, törölje az alkalmazáscsomagot, és hozzon létre egy újat.

## <a name="finish-up"></a>Befejezés

Amikor elkészült, válassza az **Alkalmazás hozzáadása** ablaktáblán a **Hozzáadás** lehetőséget. A létrehozott alkalmazás megjelenik az alkalmazáslistában.

## <a name="errors-during-installation-of-the-app-suite"></a>Hiba történt az alkalmazáscsomag telepítésekor

Az alábbi táblázatban az esetlegesen megjelenő gyakori hibakódok és azok jelentése található.

### <a name="status-for-office-csp"></a>Az Office felhőszolgáltatójának állapota

||||
|-|-|-|
|Állapot|Fázis|Description|
|1460 (ERROR_TIMEOUT)|Letöltés|Nem sikerült letölteni az Office-telepítő eszközt|    
|13 (ERROR_INVALID_DATA)|-|Nem sikerült ellenőrizni a letöltött Office-telepítő eszköz aláírását|
|A CertVerifyCertificateChainPolicy függvény által visszaadott hibakód|-|Nem sikerült a letöltött Office-telepítő eszköz hitelesítési ellenőrzése|    
|997|WIP|Telepítés|
|0|Telepítés után|A telepítés sikeres volt|    
|1603 (ERROR_INSTALL_FAILURE)|-|Valamilyen előfeltétel ellenőrzése sikertelen volt, például:<ul><li>SxS (Kísérlet a telepítésre, miközben a 2016-os MSI telepítve van)</li><li>Verzióeltérés</li><li>Egyebek</li></ul>|  
|0x8000ffff (E_UNEXPECTED)|-|Kísérlet történt az eltávolításra, miközben a számítógépen nem található meg az Office Kattintásra|     
|17002|-|Nem sikerült befejezni a forgatókönyv végrehajtását (telepítés). Lehetséges okok:<ul><li>A felhasználó megszakította a telepítést</li><li>Egy másik telepítés megszakította a telepítést</li><li>A telepítés során elfogyott a lemezterület</li><li>Ismeretlen nyelvi azonosító</li></ul>|
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

- Az alkalmazásoknak a választott csoportokhoz való hozzárendeléséhez tekintse meg az [Alkalmazások hozzárendelése csoportokhoz](/intune-azure/manage-apps/deploy-apps) című cikket.
