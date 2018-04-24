---
title: A Windows 10-es Céges portál alkalmazás manuális hozzáadása
titleSuffix: Microsoft Intune
description: A Windows 10-es Céges portál alkalmazás manuális hozzáadásának ismertetése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f2c7e449e9931bccd5e736bd09c33e0b42c623e9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-using-microsoft-intune"></a>A Windows 10-es Céges portál alkalmazás manuális hozzáadása a Microsoft Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A végfelhasználók a Microsoft Áruházból telepíthetik a Céges portál alkalmazást eszközkezelés és alkalmazástelepítés céljára. Ha azonban a cég megköveteli, hogy hozzárendelje a Céges portál alkalmazást, Ön akkor is hozzárendelheti manuálisan, közvetlenül az Intune-ból a Windows 10-es Céges portál alkalmazást, ha az Intune-t nem integrálta a Vállalati Microsoft Áruházzal.

 > [!NOTE]
 > Ha ezt a lehetőséget választja, manuális frissítést kell hozzárendelnie minden alkalommal, amikor új frissítés válik elérhetővé az alkalmazáshoz.

## <a name="configure-settings-to-show-offline-apps"></a>A beállítások konfigurálása offline alkalmazások megjelenítéséhez
1. Lépjen a [Vállalati Microsoft Áruház](https://www.microsoft.com/business-store) oldalára. Fontos, hogy a rendszergazdai fiókkal kell bejelentkeznie.
2. Válassza a **Felügyelet** lapot az ablak tetején.
3. Válassza a **Beállítások** lehetőséget a bal oldali navigációs oszlopban.
4. Kacsolja **be** a **Shopping experience** (Vásárlási élmény) terület **Show offline apps** (Offline alkalmazások megjelenítése) beállítását. Így megjelennek az offline licencelt alkalmazások a Vállalati Microsoft Áruházban.

## <a name="download-the-offline-company-portal-app"></a>Az Intune Céges portál alkalmazás letöltése
1. Keresse meg és válassza ki a **Céges portál** alkalmazást.
2. Állítsa a **licenc típusát** **offline-ra**.
3. Kattintson **Az alkalmazás letöltése** lehetőségre az offline Céges portál letöltéséhez és a leltárhoz adásához.
4. Kattintson a **Felügyelet**lehetőségre a **Céges portál** alkalmazásoldalán.
5. A **Platform** listából válassza ki a **Windows 10 minden eszközre** lehetőséget, majd válassza ki a megfelelő értékeket a **Minimális verzió**, az **Architektúra** és az Alkalmazás metaadatainak letöltése** elemekhez. 
6. Kattintson a **Letöltés** lehetőségre a fájl a helyi gépen való mentéséhez.

    ![Kép a Windows 10 minden eszközre, X86 architektúrával csomag letöltési részleteiről](./media/Win10CP-all-devices.png)

7. Töltse le a „Szükséges keretrendszer” cím alatt található összes csomagot. Ezt az x86, az x64 és az ARM architektúrákkal kell elvégezni, összesen 12 csomaggal.
8. Mielőtt feltöltené a Céges portál alkalmazást az Intune-ra, hozzon létre egy mappát (például: C:&#92;Céges portál) a következőképpen felépített csomagokkal:
   - Helyezze el a Céges portál csomagot a C:\Céges portál helyen. Ugyanitt hozzon létre egy Függőségek almappát is.  

     ![APPXBUN fájllal mentett Függőségek mappa képe](./media/Win10CP-Dependencies-save.png)

   - Helyezze el a függőségcsomagokat a *Dependencies* mappában. 

     > [!NOTE]
     > Ha a függőségeket nem a megfelelő formátumban helyezi el, az Intune nem tudja majd felismerni és feltölteni a fájlokat a csomag feltöltésekor, így a folyamat sikertelen lesz, és egy hibaüzenetet jelenít meg.

9. Lépjen vissza az Azure Portalbeli Microsoft Intune-ba.
10. Töltse fel a Vállalati portál alkalmazást egy új alkalmazásként. Rendelje hozzá szükséges alkalmazásként a kívánt felhasználói célcsoport számára.  

Itt talál további információkat arról, hogy az Intune miképpen kezeli az univerzális alkalmazások függőségeit: [appxbundle telepítése függőségekkel a Microsoft Intune MDM-en keresztül](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

## <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Hogyan frissítsem a Céges portált olyan felhasználói eszközökön, amelyeken telepítve vannak az áruházból származó régebbi alkalmazások?
Ha a felhasználók már telepítették az áruházból a Windows 8.1-es vagy a Windows Phone 8.1-es Céges portál alkalmazást, az eszközöknek automatikusan, saját vagy felhasználói beavatkozás nélkül is frissíteniük kell az új verzióra. Ha a frissítés elmarad, kérje meg a felhasználókat, hogy ellenőrizzék, engedélyezték-e az áruház-alkalmazások automatikus frissítését az eszközükön.   

## <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hogyan frissítsem a közvetlen telepítésű, Windows 8.1-es Céges portál alkalmazást Windows 10-es Céges portál alkalmazásra?
A javasolt áttelepítési út a Windows 8.1-es Céges portál alkalmazás hozzárendelésének átállítása az „Eltávolítás” lehetőségre, ami törli az alkalmazás hozzárendelését. Miután ez megtörtént, a Windows 10-es Céges portál alkalmazás a fenti lehetőségek bármelyikével hozzárendelhető lesz.  

Ha közvetlenül kell telepíteni az alkalmazást, és a Windows 8.1-es Céges portált a Symantec Tanúsítvány aláírása nélkül rendelte hozzá, a frissítéshez kövesse az Intune-on keresztül történő közvetlen telepítés fentebb leírt lépéseit.

Ha közvetlenül kell telepíteni az alkalmazást, és a Windows 8.1-es Céges portált a Symantec kódaláíró tanúsítvány aláírásával rendelte hozzá, kövesse az alábbi részben olvasható lépéseket.  

## <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hogyan frissítsem az aláírt és közvetlen telepítésű Windows Phone 8.1-es Céges portál alkalmazást vagy Windows 8.1-es Céges portál alkalmazást a Windows 10-es Céges portál alkalmazásra?
A javasolt áttelepítési út a Windows Phone 8.1-es Céges portál alkalmazás vagy a Windows 8.1-es Céges portál alkalmazás hozzárendelésének átállítása az „Eltávolítás” lehetőségre, ami törli az alkalmazás hozzárendelését. Miután ez megtörtént, a Windows 10-es Céges portál alkalmazás a szokásos módon rendelhető hozzá.  

Ellenkező esetben a frissítési út betartásának biztosításához a Windows 10-es Céges portál alkalmazás frissítésére és aláírására van szükség.  

Az így aláírt és hozzárendelt Windows 10-es Céges portál alkalmazás esetében mindig meg kell ismételni ezt a folyamatot, ha az áruházban elérhetővé válik az alkalmazás új frissítése. Az alkalmazás nem frissül automatikusan az áruház frissítésekor.  

Itt ismertetjük az alkalmazás aláírásának és hozzárendelésének ezt a módját:

1. Töltse le a Microsoft Intune Windows 10-es Céges portál alkalmazás aláírása parancsfájlt a [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) lapról.  A parancsfájlhoz olyan gazdagépre van szükség, amelyen telepítve van a Windows 10-hez készült Windows SDK. A Windows 10 rendszerhez készült Windows SDK letöltéséhez látogasson el a [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) lapra.
2. Töltse le a Windows 10-es Céges portál alkalmazást a Vállalati Microsoft Áruházból a fenti útmutató szerint.  
3. Futtassa a parancsfájlt azokkal a bemeneti paraméterekkel, amelyek a Windows 10-es Céges portál alkalmazás aláírásához használt parancsfájl fejlécén találhatók (alább kivonatolva). A függőségeket nem kell hozzáadni a parancsprogramhoz. Csak akkor van rájuk szükség, amikor éppen folyamatban van az alkalmazás feltöltése az Intune felügyeleti konzolra.

|       Paraméter       |                                                                        Description                                                                        |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                                  Az appxbundle forrásfájl elérési útja                                                  |
| OutputWin10AppxBundle | Az aláírt appxbundle fájl kimeneti útja.  Win81Appx A Windows 8.1 vagy Windows Phone 8.1 Céges portál (.APPX) fájl elérési útja. |
|      PfxFilePath      |                                       A Symantec vállalati mobil-kódaláíró tanúsítvány (.PFX) fájl elérési útja.                                        |
|      PfxPassword      |                                         A Symantec vállalati mobil-kódaláíró tanúsítvány jelszava.                                          |
|      PublisherId      |          A vállalat gyártóazonosítója. Ha nincs megadva, a program a Symantec Enterprise Mobile Code Signing Certificate tanúsítvány Subject (Tulajdonos) mezőjének értékét használja.           |
|        SdkPath        |     A Windows 10-hez készült Windows SDK gyökérmappájának elérési útja. Ezt az argumentumot nem kötelező megadni, és az alapértelmezett értéke ${env:ProgramFiles(x86)}\Windows Kits\10     |

A parancsfájl kimenete a futtatás végeztével a Windows 10-es Céges portál alkalmazás aláírt verziója lesz. Ekkor az Intune-on keresztül rendelheti hozzá az alkalmazás aláírt verzióját LOB-alkalmazásként, ami frissíteni fogja a jelenleg hozzárendelt verziókat erre az új alkalmazásra.  

## <a name="next-steps"></a>További lépések

- [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md)

