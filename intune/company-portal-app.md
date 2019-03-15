---
title: A Céges portál alkalmazás konfigurálása
titleSuffix: Microsoft Intune
description: További információ a vállalatspecifikus védjegyezés az Intune Céges portál alkalmazásban való alkalmazásáról.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50be92847922458a7145e02bcc2125ddadc6976f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57682640"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>A Microsoft Intune Céges portál alkalmazásának konfigurálása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A felhasználók a Microsoft Intune Céges portálon férhetnek hozzá a vállalati adatokhoz, és olyan gyakori feladatokat hajthatnak végre, mint például az eszközök regisztrálása, az alkalmazások telepítése és az informatikai támogatási információk megtekintése.        

> [!Tip]        
> A vállalati portál testreszabása a vállalati portál webhelyére és a vállalati portál alkalmazásaira egyaránt hatással van. Vegye figyelembe, hogy felhasználóknak rendelkezniük kell Intune-licencet a céges portál webhely eléréséhez.

A vállalati portál testreszabásával kapcsolatban, segít adjon meg egy ismerős és könnyen használható környezetet teremthet felhasználóinak. Ehhez az Intune-portálon válassza **ügyfélalkalmazások** > **Branding és testreszabási**, majd konfigurálja a szükséges beállításokat. 

> [!Note]       
> Az Azure Government használata esetében a végfelhasználó alkalmazásnaplókkal döntheti el, hogy hogyan végzi a megosztást, amikor segítségkérési folyamatot indít el egy probléma kapcsán. Ha azonban nem az Azure Governmentet használja, akkor a Windows 10 Céges portál közvetlenül a Microsoftnak küldi az alkalmazásnaplókat, amikor egy felhasználó segítségkérési folyamatot indít el egy probléma kapcsán. Az alkalmazásnaplók Microsoftnak való elküldésével könnyebben háríthatók el és oldhatók meg a problémák. 

## <a name="company-information-and-privacy-statement"></a>A vállalat adatai és adatvédelmi nyilatkozata        
A vállalat neve a Vállalati portál címeként jelenik meg. Az adatvédelmi nyilatkozat az Adatvédelem hivatkozásra kattintva jeleníthető meg.

A csillaggal (*) jelölt mezők kitöltése kötelező.       


| Mező neve | Maximális hossz | További információ |
|---|---|---|
|**Vállalat neve**| 40 | Ez a név a Céges portál címeként jelenik meg, és az Intune használata alatt végig szöveges formában olvasható. |
| **Az adatvédelmi nyilatkozat URL-címe** |     79     | Itt adhatja meg vállalatának adatvédelmi nyilatkozatát, amely akkor jelenik meg, ha a felhasználó a Vállalati portál adatvédelmi hivatkozásaira kattint. Érvényes URL-címet kell megadnia, a következő formátumban: `<https://www.contoso.com>`. |

## <a name="support-information"></a>Támogatási információk      
Adja meg a vállalat adatait egy ügyfél a munkatársak rendelkezésére az Intune-nal kapcsolatos kérdésekre.          

|Mező neve|Maximális hossz|További információ|
|---|---|---|
|**Kapcsolattartó neve** | 40 | Ez a név az **IT-csoport elérhetősége** lapon jelenik meg. |
|**Telefonszám** | 20 | A kapcsolattartási szám megjelenik az **IT-csoport elérhetősége** lapon, és lehetővé teszi munkatársai számára a támogatáskérést. |
|**E-mail cím**| 40 | Ez a cím az **IT-csoport elérhetősége** lapon jelenik meg. Meg kell adnia egy érvényes e-mail-címet a következő formátumban: `alias@domainname.com`. |
|**Webhely neve**| 40 | Ez a név a támogatási webhely URL-címének rövid neveként jelenik meg. Ha a támogatási webhelyhez csak URL-címet ad meg, de rövid nevet nem, akkor Az IT-csoport weboldalának megnyitása felirat jelenik meg a Céges portál **IT-csoport elérhetősége** lapján. |
|**Webhely URL-címe**| 150 | Ha rendelkezik saját felhasználóinak szánt támogatási webhellyel, ide írja be az URL-címét. Az URL-cím formátumának a következőnek kell lennie: `https://www.contoso.com`. Ha nem ad meg URL-címet, semmi sem jelenik meg a támogatási webhelyről a Vállalati portál **IT-csoport elérhetősége** lapján. |
| **További információ**| 120 | Az **IT-csoport elérhetősége** lapon jelenik meg. |


## <a name="company-identity-branding-customization"></a>Vállalati identitási arculat testreszabása      
A Vállalati portál testre szabható a vállalat emblémájának és nevének, valamint a téma színének és a háttérnek a megadásával.     

### <a name="theme-color-and-logo-in-the-company-portal"></a>Témaszín és embléma a Céges portálon
Témaszínt alkalmazhat a Céges portálon. Jelöljön ki egy szabványos színt, vagy adjon meg egy hexadecimális hatjegyű kódot az egyéni színhez.

|Mező neve|További információ|
|---|---|
|**Jelöljön ki egy szabványos színt, vagy adjon meg egy hexadecimális hatjegyű kódot**| Válasszon **Standard** vizuálisan válassza ki a színt. Válassza az **Egyéni** lehetőséget egy hexadecimális kódon alapuló meghatározott szín kiválasztásához.|
|**Téma színének kiválasztása**| A Vállalati portálra alkalmazni kívánt témaszín kiválasztása. Választhat a színválasztóból, vagy megadhat egy hexadecimális kódot. |
|**Megjelenítés**| Válassza ki, hogy mit szeretne megjeleníteni: **Cégembléma és -név**, **Csak cégembléma** vagy **Csak cégnév**. |
|**A céges embléma feltöltése**|Feltöltheti a Céges portálon megjeleníteni kívánt vállalati emblémát. Vegye figyelembe, hogy a szöveg színének kiválasztása automatikusan történik a legnagyobb kontraszt eléréséhez. Az optimális megjelenés érdekében töltsön fel egy áttetsző hátterű emblémát.<p><ul><li>Maximális Képméret: 400px x 400px</li><li>Maximális fájlméret: 750KB</li><li>Fájltípus: PNG, JPG vagy JPEG</li></ul>|

Miután feltöltötte az emblémát, az előnézeti területen meg fog jelenni az embléma a téma színével. Ha úgy dönt, hogy megjeleníti a cég nevét, az feketén vagy fehéren fog megjelenni a Céges portálon, és a téma színe alapján automatikusan a lehető legnagyobb kontraszttal fog megjelenni. A képernyő előnézeti területén nem fog megjelenni a cég neve. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Fehér vagy világos háttérrel használható embléma
Válasszon olyan emblémát, amely fehér vagy világos háttéren mutat a legjobban.

|Mező neve|További információ|
|---|---|
|**Embléma feltöltése**| Ez a lehetőség akkor érhető el, ha a céges embléma megjelenítése mellett döntött. Az optimális megjelenés érdekében töltsön fel egy áttetsző hátterű emblémát.<p><ul><li>Maximális Képméret: 400px x 400px</li><li>Maximális fájlméret: 750KB</li><li>Fájltípus: PNG, JPG vagy JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Márkakép a Céges portálhoz

Márkakép feltöltése, amely tükrözi a vállalati márkát. A módosítások mentése után az Intune-webportálon a panel tetején található **Beállítások előnézetének megtekintése** lehetőséget választva megtekintheti, hogyan fog kinézni a konfigurációja. Vegye figyelembe, hogy a márkakép előnézetét csak egy iOS-eszközön lehet megtekinteni, az Intune webes portálján nem. 

|Mező neve|További információ|
|---|---|
|**Márkakép feltöltése**| Ezt a beállítás rendelkezésre áll háttérkép megjelenítéséhez a Céges portál alkalmazás felhasználói profil oldalán.<p>*Megjegyzés*: A kép a különböző platformok módon jelenhetnek meg.<p><ul><li>Kép szélessége ajánlott: Kisebb, mint 1125px, de nem kisebb, mint 640 képpont</li><li>Maximális Képméret: 1.3 MB</li><li>Fájltípus: PNG, JPG vagy JPEG</li></ul>|

A megfelelő márkakép javíthatja a felhasználó Céges portálba vetett bizalmát a cég márkájának hangsúlyozásával. Íme néhány tipp, amelyet érdemes figyelembe venni a kép Céges portálhoz történő beszerzésekor, kiválasztásakor és optimalizálásakor. 

- Vegye fel a kapcsolatot az értékesítési vagy művészeti osztállyal. Előfordulhat, hogy már van jóváhagyott márka lemezképek. Előfordulhat, hogy a képek igény szerinti optimalizálásában is tudnak segíteni. 

- Fontolja meg a fekvő és az álló tájolású kompozíciókat is. A képnek megfelelő háttérrel kell rendelkeznie, amely körülveszi a fókuszpontot. A kép eszköz mérete, a tájolást és a platform menübeállításoktól függően előfordulhat, hogy levágja. 

- Kerülje az általános, készletben elérhető képek használatát. A képnek tükröznie kell a vállalati márkát, és ismerősnek kell tűnnie a felhasználóknak. Ha még nem rendelkezik ilyen képpel, jobb ha nem használ semmilyet, mint sem hogy olyan általános képet adjon meg, ami semmit nem jelent a felhasználóknak. 

- Szükségtelen metaadatok eltávolítása. A képfájl tartalmazhat metaadatokat, például kameraprofilt, földrajzi helyet, címet, feliratot stb. Használjon képoptimalizáló eszközt ezeknek az adatoknak az eltávolításához a minőség fájlméretkorlátok betartásával történő megőrzéséhez. 

A márka lemezkép van hozzáadva, vagy módosítása után az Intune-ban a végfelhasználó előfordulhat, hogy nem jelenik meg az iOS-eszközökön a vállalati portál a Start menüben a módosítás mentése elismert, és ezután újra lett indítva a márka kép megjelenítéséhez. 

### <a name="brand-image-examples"></a>Márka kép példák

Az alábbi képen látható példában iPad védjegyzési kép:

![Védjegyzési kép például iPhone képernyőképe](media/company-portal-app/company-portal-app-03.png)

Az alábbi képen látható védjegyzési kép például iPhone-on:

![Védjegyzési kép például iPad képernyőképe](media/company-portal-app/company-portal-app-02.png)

## <a name="windows-company-portal-keyboard-shortcuts"></a>A Windows Céges portálon használható billentyűparancsok

A végfelhasználók a Windows céges portál (megoldásgyorsítók) billentyűparancsok használata a navigációs, alkalmazás és eszköz műveletek is indíthat.

A következő billentyűparancsok érhetők el a Windows Céges portál alkalmazásban.

| Terület | Leírás | Billentyűparancs |
|:------------------:|:--------------:|:-----------------:|
| Navigációs menü | Navigáció | Alt+M |
|  | Otthoni | Alt+H |
|  | Minden alkalmazás | Alt+A |
|  | Telepített alkalmazások | Alt+I |
|  | Visszajelzés küldése | Alt+F |
|  | Saját profil | Alt+U |
|  | Beállítások | Alt+T |
| Kezdőlap – Eszköz csempe | Átnevezés | F2 |
|  | Eltávolítás | Ctrl+D vagy Delete |
|  | Hozzáférés ellenőrzése | Ctrl+M vagy F9 |
| Eszközadatok | Átnevezés | F2 |
|  | Eltávolítás | Ctrl+D vagy Delete |
|  | Hozzáférés ellenőrzése | Ctrl+M vagy F9 |
| Alkalmazás részletei | Telepítés | Ctrl+I |

A végfelhasználók is elérhetik a Windows céges portál alkalmazásban elérhető parancsikonjait megtekintéséhez.

![Képernyőfelvétel a Windows vállalati portálon elérhető hivatkozása](media/company-portal-app/company-portal-app-01.png)

## <a name="next-steps"></a>További lépések

- [A Windows 10-es céges portál alkalmazás manuális hozzáadása a Microsoft Intune-nal](store-apps-company-portal-app.md)
