---
title: "Windows áruházbeli alkalmazások hozzáadása az Intune-hoz"
titleSuffix: Intune on Azure
description: "Útmutató Windows Áruházbeli alkalmazások Intune-ba való felvételéhez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 812bdf5bde724798289668937ed2502438c524e0
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2017
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Windows Áruházbeli alkalmazások hozzáadása a Microsoft Intune-hoz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazás adatai** elemet.
7. Az **Alkalmazás szerkesztése** panelen konfigurálja az alábbi adatokat. Amikor elkészült, kattintson a **Hozzáadás** lehetőségre. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Alkalmazás neve** – Itt adhatja meg az alkalmazásnak a Céges portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a vállalati portálon.
    - **Alkalmazás leírása** – Itt adhatja meg az alkalmazás leírását. amelyet meg szeretne jeleníteni a felhasználók számára a vállalati portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazás-áruház URL-címe** – Itt adhatja meg a létrehozni kívánt alkalmazás áruházbeli URL-címét.
    - **Minimális operációsrendszer-verzió** – A listából kiválaszthatja az operációs rendszer legkorábbi olyan verzióját, amelyre az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerű eszközhöz rendeli hozzá, nem fog települni.
    - **Kategória (nem kötelező)** – Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon** – Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon feltöltése** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a vállalati portálon böngésző felhasználók számára.
8. Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza a **Mentés** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).

## <a name="manually-assign-windows-10-company-portal-app"></a>A Windows 10-es Céges portál alkalmazás manuális hozzárendelése
A végfelhasználók a Microsoft Áruházból telepíthetik a Céges portál alkalmazást eszközkezelés és alkalmazástelepítés céljára. Ha azonban a cég megköveteli, hogy hozzárendelje a Céges portál alkalmazást, Ön akkor is hozzárendelheti manuálisan, közvetlenül az Intune-ból a Windows 10-es Céges portál alkalmazást, ha az Intune-t nem integrálta a Vállalati Microsoft Áruházzal.

 > [!NOTE]
 > Ha ezt a lehetőséget választja, manuális frissítést kell hozzárendelnie minden alkalommal, amikor új frissítés válik elérhetővé az alkalmazáshoz.

1. Jelentkezzen be [Vállalati Microsoft Áruház](https://www.microsoft.com/business-store) fiókjába, és szerezze be a Céges portál alkalmazás **offline licencű** verzióját.  
2. Miután beszerezte az alkalmazást, válassza ki a **Készlet** lapon.  
3. A **Platform** listából válassza ki a **Windows 10 minden eszközre** lehetőséget, majd válassza ki a megfelelő **architektúrát**, és töltse le az alkalmazást. Ehhez az alkalmazáshoz nincs szükség alkalmazás-licencfájlra.
![Kép a Windows 10 minden eszközre, X86 architektúrával csomag letöltési részleteiről](./media/Win10CP-all-devices.png)
4. Töltse le a „Szükséges keretrendszer” cím alatt található összes csomagot. Ezt az x86, az x64 és az ARM architektúrákkal kell elvégezni, összesen 9 csomaggal, ahogy az alábbi ábrán látható.

![Kép a letöltendő függőségi fájlokról ](./media/Win10CP-dependent-files.png)
5. Mielőtt feltöltené a Céges portál alkalmazást az Intune-ra, hozzon létre egy mappát (pl. C:&#92;Céges portál) a következőképpen felépített csomagokkal:
  1. Helyezze el a Céges portál csomagot a C:\Céges portál helyen. Ugyanitt hozzon létre egy Függőségek almappát is.  
  ![APPXBUN fájllal mentett Függőségek mappa képe](./media/Win10CP-Dependencies-save.png)
  2. Helyezze el a kilenc függőségcsomagot a Függőségek mappában.  
  Ha a függőségeket nem ebben a formátumban helyezi el, az Intune nem tudja majd felismerni és feltölteni őket a csomag feltöltésekor, így a folyamat sikertelen lesz a következő hiba miatt.  
  ![A szoftver telepítőjéhez tartozó Windows-alkalmazás nem található az alkalmazás mappájában. Továbbra is létrehozhatja és hozzárendelheti az alkalmazást, de az nem fog futni addig, amíg hozzá nem adja a hiányzó Windows alkalmazás-függőséget.](./media/Win10CP-error-message.png)
6. Lépjen vissza az Intune-ba, és töltse fel a Céges portál alkalmazást új alkalmazásként. Rendelje hozzá szükséges alkalmazásként a kívánt felhasználói célcsoport számára.  

Itt talál további információkat arról, hogy az Intune miképpen kezeli az univerzális alkalmazások függőségeit: [appxbundle telepítése függőségekkel a Microsoft Intune MDM-en keresztül](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Hogyan frissítsem a Céges portált olyan felhasználói eszközökön, amelyeken telepítve vannak az áruházból származó régebbi alkalmazások?
Ha a felhasználók már telepítették az áruházból a Windows 8.1-es vagy a Windows Phone 8.1-es Céges portál alkalmazást, az eszközöknek automatikusan, saját vagy felhasználói beavatkozás nélkül is frissíteniük kell az új verzióra. Ha a frissítés elmarad, kérje meg a felhasználókat, hogy ellenőrizzék, engedélyezték-e az áruház-alkalmazások automatikus frissítését az eszközükön.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hogyan frissítsem a közvetlen telepítésű, Windows 8.1-es Céges portál alkalmazást Windows 10-es Céges portál alkalmazásra?
A javasolt áttelepítési út a Windows 8.1-es Céges portál alkalmazás hozzárendelésének átállítása az „Eltávolítás” lehetőségre, ami törli az alkalmazás hozzárendelését. Miután ez megtörtént, a Windows 10-es Céges portál alkalmazás a fenti lehetőségek bármelyikével hozzárendelhető lesz.  

Ha közvetlenül kell telepíteni az alkalmazást, és a Windows 8.1-es Céges portált a Symantec Tanúsítvány aláírása nélkül rendelte hozzá, a frissítéshez kövesse az Intune-on keresztül történő közvetlen telepítés fentebb leírt lépéseit.

Ha közvetlenül kell telepíteni az alkalmazást, és a Windows 8.1-es Céges portált a Symantec kódaláíró tanúsítvány aláírásával rendelte hozzá, kövesse az alábbi részben olvasható lépéseket.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hogyan frissítsem az aláírt és közvetlen telepítésű Windows Phone 8.1-es Céges portál alkalmazást vagy Windows 8.1-es Céges portál alkalmazást a Windows 10-es Céges portál alkalmazásra?
A javasolt áttelepítési út a Windows Phone 8.1-es Céges portál alkalmazás vagy a Windows 8.1-es Céges portál alkalmazás hozzárendelésének átállítása az „Eltávolítás” lehetőségre, ami törli az alkalmazás hozzárendelését. Miután ez megtörtént, a Windows 10-es Céges portál alkalmazás a szokásos módon rendelhető hozzá.  

Ellenkező esetben a frissítési út betartásának biztosításához a Windows 10-es Céges portál alkalmazás frissítésére és aláírására van szükség.  

Az így aláírt és hozzárendelt Windows 10-es Céges portál alkalmazás esetében mindig meg kell ismételni ezt a folyamatot, ha az áruházban elérhetővé válik az alkalmazás új frissítése. Az alkalmazás nem frissül automatikusan az áruház frissítésekor.  

Itt ismertetjük az alkalmazás aláírásának és hozzárendelésének ezt a módját:

1. Töltse le a Microsoft Intune Windows 10-es Céges portál alkalmazás aláírása parancsfájlt a [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) oldalról.  A parancsfájlhoz olyan gazdagépre van szükség, amelyen telepítve van a Windows 10-hez készült Windows SDK. A Windows 10-hez készült Windows SDK letöltéséhez látogasson el a [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) oldalra.
2. Töltse le a Windows 10-es Céges portál alkalmazást a Vállalati Microsoft Áruházból a fenti útmutató szerint.  
3. Futtassa a parancsfájlt azokkal a bemeneti paraméterekkel, amelyek a Windows 10-es Céges portál alkalmazás aláírásához használt parancsfájl fejlécén találhatók (alább kivonatolva). A függőségeket nem kell hozzáadni a parancsprogramhoz. Csak akkor van rájuk szükség, amikor éppen folyamatban van az alkalmazás feltöltése az Intune felügyeleti konzolra.

|Paraméter | Leírás|
| ------------- | ------------- |
|InputWin10AppxBundle |Az appxbundle forrásfájl elérési útja |
|OutputWin10AppxBundle |Az aláírt appxbundle fájl kimeneti útja.  Win81Appx A Windows 8.1 vagy Windows Phone 8.1 Céges portál (.APPX) fájl elérési útja.|
|PfxFilePath |A Symantec vállalati mobil-kódaláíró tanúsítvány (.PFX) fájl elérési útja. |
|PfxPassword| A Symantec vállalati mobil-kódaláíró tanúsítvány jelszava. |
|PublisherId |A vállalat gyártóazonosítója. Ha nincs megadva, a program a Symantec Enterprise Mobile Code Signing Certificate tanúsítvány Subject (Tulajdonos) mezőjének értékét használja.|
|SdkPath | A Windows 10-hez készült Windows SDK gyökérmappájának elérési útja. Ezt az argumentumot nem kötelező megadni, és az alapértelmezett értéke ${env:ProgramFiles(x86)}\Windows Kits\10|
A parancsfájl kimenete a futtatás végeztével a Windows 10-es Céges portál alkalmazás aláírt verziója lesz. Ekkor az Intune-on keresztül rendelheti hozzá az alkalmazás aláírt verzióját LOB-alkalmazásként, ami frissíteni fogja a jelenleg hozzárendelt verziókat erre az új alkalmazásra.  
