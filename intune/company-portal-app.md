---
title: "A Céges portál alkalmazás konfigurálása"
titleSuffix: Azure portal
description: "További információ a vállalatspecifikus védjegyezés az Intune Céges portál alkalmazásban való alkalmazásáról. \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 303d4a4cbce9d63abc0809a27ae1e22dcd1e195b
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>A Microsoft Intune Céges portál alkalmazásának konfigurálása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A felhasználók a Microsoft Intune Céges portálon férhetnek hozzá a vállalati adatokhoz, és olyan gyakori feladatokat hajthatnak végre, mint például az eszközök regisztrálása, az alkalmazások telepítése és az informatikai támogatási információk megtekintése.        

> [!Tip]        
> A vállalati portál testreszabása a vállalati portál webhelyére és a vállalati portál alkalmazásaira egyaránt hatással van.       

A vállalati portál testreszabásával ismerős és könnyen használható környezetet teremthet felhasználóinak. Ennek végrehajtásához válassza a **Mobilalkalmazások** területen a **Beállítás** > **Company Portal Branding** (Céges portál védjegyezése) lehetőséget, majd konfigurálja a szükséges beállításokat.      

## <a name="company-contact-information-and-privacy-statement"></a>Vállalat kapcsolattartási adatai és adatvédelmi nyilatkozata        
A vállalat neve a Vállalati portál címeként jelenik meg. A kapcsolattartási adatokat és részleteket a felhasználók a Céges portál **IT-csoport elérhetősége** képernyőjén tekinthetik meg. Az adatvédelmi nyilatkozat az Adatvédelem hivatkozásra kattintva jeleníthető meg.        


|Mező neve|Maximális hossz|További információ|        
|-|-|-|     
|**Vállalat neve**|40|Ez a név a Vállalati portál címeként jelenik meg.|        
|**IT-részleg kapcsolattartójának a neve**|40|Ez a név az **IT-csoport elérhetősége** lapon jelenik meg.|      
|**IT-részleg telefonszáma**|20|Ez a telefonszám az **IT-csoport elérhetősége** lapon jelenik meg.|        
|IT-részleg e-mail címe|40|Ez a cím az **IT-csoport elérhetősége** lapon jelenik meg. Meg kell adnia egy érvényes e-mail címet a következő formátumban: **alias@domainname.com**.|     
|**További információ**|120|Az **IT-csoport elérhetősége** lapon jelenik meg.|      
|**Vállalat adatvédelmi nyilatkozatának URL-címe**|79|Itt adhatja meg vállalatának adatvédelmi nyilatkozatát, amely akkor jelenik meg, ha a felhasználó a Vállalati portál adatvédelmi hivatkozásaira kattint. Érvényes URL-címet kell megadnia, a következő formátumban: **https://www.contoso.com**.|        

## <a name="support-contacts"></a>Támogatási kapcsolattartók     
A támogatási webhely a Vállalati portálon jelenik meg, és lehetővé teszi a felhasználók számára az online támogatás elérését.        



|Mező neve|Maximális hossz|További információ|        
|-|-|-|     
|**Támogatási webhely URL-címe**|150|Ha rendelkezik saját felhasználóinak szánt támogatási webhellyel, ide írja be az URL-címét. Az URL-címet **https://www.contoso.com** formátumban kell megadni. Ha nem ad meg URL-címet, semmi sem jelenik meg a támogatási webhelyről a Vállalati portál **IT-csoport elérhetősége** lapján.|        
|**Támogatási webhely neve**|40|Ez a név a támogatási webhely URL-címének rövid neveként jelenik meg. Ha a támogatási webhelyhez csak URL-címet ad meg, de rövid nevet nem, akkor Az IT-csoport weboldalának megnyitása felirat jelenik meg a Céges portál **IT-csoport elérhetősége** lapján.       

## <a name="company-branding-customization"></a>Vállalati arculat szerinti testreszabás       
A Vállalati portál testre szabható a vállalat emblémájának és nevének, valamint a téma színének és a háttérnek a megadásával.     



|Mező neve|További információ|       
|-|-|       
|**Téma színe**|A Vállalati portálra alkalmazni kívánt témaszín kiválasztása.|      
|**Cég emblémájának megjelenítése**|Ha engedélyezi ezt a beállítást, feltöltheti a Vállalati portálon megjeleníteni kívánt vállalati emblémát. Két emblémát tölthet fel: az egyik akkor jelenik meg, ha a Vállalati portál háttérszíne fehér, a másik pedig akkor, ha a Vállalati portál a témának megfelelő háttérszínnel jelenik meg. Mindkét emblémának egy .png vagy .jpg formátumú fájlnak kell lennie, melyek felbontása legfeljebb 400 x 100 képpont, mérete pedig legfeljebb 750 KB lehet.<br>A megadott vállalatnevet a feltöltött embléma mellett is megjelenítheti.|      

A módosítások mentése után **Preview your settings in the Intune Web Portal** (A beállítások előnézetének megtekintése az Intune webportálon) lehetőséget választva tekintheti meg, hogyan fognak megjelenni a konfigurációk.
