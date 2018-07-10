---
title: A Céges portál alkalmazás konfigurálása
titleSuffix: Microsoft Intune
description: További információ a vállalatspecifikus védjegyezés az Intune Céges portál alkalmazásban való alkalmazásáról.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4535bdfa9b801c605c70c0a9dad900d76044eab4
ms.sourcegitcommit: c78923b0d5b320322c828b1bbea2deb9062e30d2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37844980"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>A Microsoft Intune Céges portál alkalmazásának konfigurálása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A felhasználók a Microsoft Intune Céges portálon férhetnek hozzá a vállalati adatokhoz, és olyan gyakori feladatokat hajthatnak végre, mint például az eszközök regisztrálása, az alkalmazások telepítése és az informatikai támogatási információk megtekintése.        

> [!Tip]        
> A vállalati portál testreszabása a vállalati portál webhelyére és a vállalati portál alkalmazásaira egyaránt hatással van.       

A vállalati portál testreszabásával ismerős és könnyen használható környezetet teremthet felhasználóinak. Ennek végrehajtásához válassza a **Mobilalkalmazások** területen a **Beállítás** > **Company Portal Branding** (Céges portál védjegyezése) lehetőséget, majd konfigurálja a szükséges beállításokat.  

> [!Note]       
> A Windows 10 Céges portál mostantól alkalmazáshasználati naplókat küld közvetlenül a Microsoftnak, ha egy felhasználó segítséget kér egy problémához. Így könnyebben háríthatók el és oldhatók meg a Microsoftnak továbbított problémák.  

## <a name="company-information-and-privacy-statement"></a>A vállalat adatai és adatvédelmi nyilatkozata        
A vállalat neve a Vállalati portál címeként jelenik meg. Az adatvédelmi nyilatkozat az Adatvédelem hivatkozásra kattintva jeleníthető meg.

A csillaggal (*) jelölt mezők kitöltése kötelező.       


| Mező neve | Maximális hossz | További információ |
|---|---|---|
|**Vállalat neve**| 40 | Ez a név a Céges portál címeként jelenik meg, és az Intune használata alatt végig szöveges formában olvasható. |
| **Az adatvédelmi nyilatkozat URL-címe** |     79     | Itt adhatja meg vállalatának adatvédelmi nyilatkozatát, amely akkor jelenik meg, ha a felhasználó a Vállalati portál adatvédelmi hivatkozásaira kattint. Érvényes URL-címet kell megadnia, a következő formátumban: `<https://www.contoso.com>`. |

## <a name="support-information"></a>Támogatási információk      
Ahhoz, hogy munkatársainak megadhassa az Intune-nal kapcsolatos kérdések esetén használható kapcsolattartási adatokat, írja be a céges támogatási információkat.       

|Mező neve|Maximális hossz|További információ|
|---|---|---|
|**Kapcsolattartó neve** | 40 | Ez a név az **IT-csoport elérhetősége** lapon jelenik meg. |
|**Telefonszám** | 20 | A kapcsolattartási szám megjelenik az **IT-csoport elérhetősége** lapon, és lehetővé teszi munkatársai számára a támogatáskérést. |
|**E-mail cím**| 40 | Ez a cím az **IT-csoport elérhetősége** lapon jelenik meg. Meg kell adnia egy érvényes e-mail-címet a következő formátumban: `alias@domainname.com`. |
|**Webhely neve**| 40 | Ez a név a támogatási webhely URL-címének rövid neveként jelenik meg. Ha a támogatási webhelyhez csak URL-címet ad meg, de rövid nevet nem, akkor Az IT-csoport weboldalának megnyitása felirat jelenik meg a Céges portál **IT-csoport elérhetősége** lapján. |
|**Webhely URL-címe**| 150 | Ha rendelkezik saját felhasználóinak szánt támogatási webhellyel, ide írja be az URL-címét. Az URL-cím formátumának a következőnek kell lennie: `https://www.contoso.com`. Ha nem ad meg URL-címet, semmi sem jelenik meg a támogatási webhelyről a Vállalati portál **IT-csoport elérhetősége** lapján. |
| **További információ**| 120 | Az **IT-csoport elérhetősége** lapon jelenik meg. |


## <a name="company-branding-customization"></a>Vállalati arculat szerinti testreszabás       
A Vállalati portál testre szabható a vállalat emblémájának és nevének, valamint a téma színének és a háttérnek a megadásával.     

### <a name="theme-color"></a>Téma színe
Témaszínt alkalmazhat a Céges portálon. Jelöljön ki egy szabványos színt, vagy adjon meg egy hexadecimális hatjegyű kódot az egyéni színhez.

|Mező neve|További információ|
|---|---|
|**Színtípus**| A Vállalati portálra alkalmazni kívánt témaszín kiválasztása. Választhat a színválasztóból, vagy megadhat egy hexadecimális kódot. |
|**Szín választása** vagy **Hexadecimális színkód**| A Vállalati portálra alkalmazni kívánt témaszín kiválasztása. Választhat a színválasztóból, vagy megadhat egy hexadecimális kódot. Ezek a lehetőségek az Ön által megadott **Színtípus** alapján érhetők el.  |

### <a name="company-logo"></a>Céges embléma
Feltöltheti cége emblémáját, és láthatóvá teheti végig az Intune használata során.

|Mező neve|További információ|
|---|---|
|**Cég emblémájának megjelenítése**|Ha engedélyezi ezt a beállítást, feltöltheti a Vállalati portálon megjeleníteni kívánt vállalati emblémát. Két emblémát tölthet fel: az egyik akkor jelenik meg, ha a Vállalati portál háttérszíne fehér, a másik pedig akkor, ha a Vállalati portál a témának megfelelő háttérszínnel jelenik meg. |
|**Embléma feltöltése témaszínnel ellátott háttér elé**| Ez a lehetőség akkor érhető el, ha a céges embléma megjelenítése mellett döntött. Az emblémának legfeljebb 400 x 400 képpont felbontású, legfeljebb 750 KB méretű .png vagy .jpg formátumú fájlnak kell lennie. |
|**Embléma feltöltése világos háttér elé**| Ez a lehetőség akkor érhető el, ha a céges embléma megjelenítése mellett döntött. Az emblémának legfeljebb 400 x 400 képpont felbontású, legfeljebb 750 KB méretű .png vagy .jpg formátumú fájlnak kell lennie. |
|**Cégnév feltüntetése az embléma mellett**| Válassza ezt a lehetőséget, ha a megadott cégnevet meg szeretné jeleníteni a feltöltött embléma mellett. |

A módosítások mentése után a panel tetején látható **Preview your settings in the Intune Web Portal** (A beállítások előnézetének megtekintése az Intune webportálon) lehetőségre kattintva tekintheti meg előre a konfigurációk megjelenítését.
