---
title: "Telepítési célok, célkitűzések és kihívások meghatározása | Microsoft Docs"
description: "Ez a cikk segítséget nyújt a Microsoft Intune csak felhőalapú megvalósításához kapcsolódó telepítési célok, célkitűzések és kihívások meghatározásában."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d10906ee3fb69458738b31bb1d4252d632a9a0cf
ms.openlocfilehash: 6014527422ea3dae4d1333965ccd9e48e8216afb
ms.lasthandoff: 04/08/2017


---

# <a name="determine-intune-deployment-goals-objectives-and-challenges"></a>Telepítési célok, célkitűzések és kihívások meghatározása

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A jó telepítési tervhez legelőször is meg kell határozni munkahelye telepítési céljait, célkitűzéseit, valamint a lehetséges kihívásokat. Minden munkahely egyedi, saját célokkal, célkitűzésekkel és kihívásokkal. Az alábbiakban mindegyik kérdést részletesen is megtárgyaljuk.

## <a name="deployment-goals"></a>Üzembe helyezés céljai

Telepítési céloknak a Microsoft Intune vállalaton belüli alkalmazásával megvalósuló hosszú távú eredmények tekintendők. Az alábbiakban egy munkahely Intune-telepítési céljait, valamint azok leírását és üzleti értékét bemutató példák találhatók.

-   **Integráció az Office 365-tel és az Office-mobilalkalmazások támogatása**

    -   **Leírás:** Szoros integráció biztosítása az Office 365-tel, valamint az Office-mobilalkalmazások alkalmazásvédelemmel történő használata.

    -   **Üzleti érték:** Biztonságos és fokozott felhasználói élmény azáltal, hogy a felhasználók az számukra ismerős és kedvelt alkalmazásokat használhatnak.

-   **Belső céges szolgáltatásokhoz való hozzáférés engedélyezése mobileszközökön**

    -   **Leírás:** A munkahely stratégiai célkitűzései közé tartozik, hogy a munkavállalók bárhonnan, a számukra leginkább megfelelő eszközökön hatékonyan végezzék a munkát. Ez magába foglalja a mobileszközökről végzett hatékony munkát, valamint a céges adatokhoz való biztonságos hozzáférést.

    -   **Üzleti érték:** Ha a munkavállalók agilisak lehetnek és bárhonnan tudnak dolgozni, a vállalkozás versenyképesebbé, a munkakörnyezet pedig jobbá válik.

-   **Adatvédelem biztosítása a mobileszközökön**

    -   **Leírás**: Ahol az adatokat mobileszközökön tárolják, ott meg kell védeni azokat a rosszindulatú vagy véletlenszerű elvesztésektől vagy megosztásoktól.

    -   **Üzleti érték:** Az adatvédelem életbevágóan fontos, hogy versenyképesek maradjunk, valamint hogy saját és ügyfeleink adatait a lehető legkörültekintőbben kezeljük.

-   **Költségcsökkentés**

    -   **Leírás:** A projekt lehetőség szerint csökkenti a telepítési és működtetési költségeket.

    -    **Üzleti érték:** Az erőforrások hatékony felhasználásával a vállalkozás más területeken is befektethet, hatékonyabban versenyezhet, valamint jobb szolgáltatásokat nyújthat ügyfeleinek.

## <a name="deployment-objectives"></a>Üzembe helyezés feladatai

A telepítés célkitűzései olyan műveletek, amelyekkel az adott munkahely elérheti a Microsoft Intune telepítésének céljait. Az alábbiakban egy munkahely telepítési célkitűzéseire, valamint azok megvalósítására talál példákat.

-   **Az eszközkezelési megoldások számának csökkentése**
<br>
    -   **Végrehajtás:** Alkalmazásai és eszközei védelméhez szorítkozzon egyetlen mobileszköz-felügyeleti megoldásra, mégpedig a Microsoft Intune-ra.
<br></br>
-   **Biztosítson az Exchange-hez és a SharePoint Online-hoz biztonságos hozzáférést**
<br>
    -   **Végrehajtás:** Hajtsa végre az Exchange és a SharePoint Online megoldásokra vonatkozó Microsoft Intune-beli feltételes hozzáférést.
<br></br>
-   **Ne engedje, hogy a céges adatok a mobileszköz nem céges szolgáltatásain kerüljenek tárolásra vagy továbbításra**
<br>
    -   **Végrehajtás:** Hajtsa végre a Microsoft Office- és az üzletági alkalmazásokra vonatkozó Microsoft Intune alkalmazásvédelmi szabályzatokat.
<br></br>
-   **Biztosítsa a céges adatok törlésének képességét az eszközről**
<br>
    -   **Végrehajtás:** Regisztrálja és felügyelje az eszközöket Microsoft Intune-ban, így alkalomadtán távolról is törölheti a vállalati adatokat és erőforrásokat.

## <a name="deployment-challenges"></a>Üzembe helyezés kihívásai

A telepítés kihívásai kiemelt fontossággal bírnak a cégek életében, és előfordulhat, hogy negatív hatást gyakorolhatnak magára a telepítésre. Olykor ezek régi projekteknél fellépő múltbéli problémákkal kapcsolatosak, most pedig szeretné megelőzni a jelenlegi telepítéskor esetlegesen felmerülő újakat. Az alábbiakban az egyes munkahelyek Microsoft Intune-telepítési kihívásai és azok lehetséges megoldásai találhatók.

-   A kezdeti projekt nem terjed ki a támogatásra és a végfelhasználói élményre.  Ez gyenge végfelhasználói átállást eredményez, és kihívást jelent a megoldás támogatásánál.
<br>
    -   **Megoldás:** A telepítési tervbe vegye bele a támogatási képzéseket, valamint a végfelhasználói élmény sikerkritériumokkal történő ellenőrzését.
<br></br>
-   Az egyértelműen meghatározott célok és sikerkritériumok hiánya miatt nincsenek kézzel fogható eredmények, a problémákat pedig reaktívan kezelik.
<br>
    -   **Megoldás:** A célokat és a siker kritériumait már a projekthatókör meghatározásának korai szakaszában definiálja, és ezeket az adatokat vegye alapul a bevezetés további fázisainak tervezéséhez. A célokat úgy tűzze ki, hogy konkrétak, mérhetők, teljesíthetők, reálisak és időszerűek legyenek, és tervezzen be felmérési pontokat is mindegyik fázisban, amelyek segítségével megállapíthatja, hol tart a cél és egyúttal a bevezetési projekt megvalósításában.
<br></br>
-   A szervezet érdeklődését felkeltő és világos felkínált érték megteremtésének, ellenőrzésének és agresszív megosztásának mellőzése gyakran kisebb mértékű átálláshoz és a megtérülés elmaradásához vezet.
<br>
    -   **Megoldás:** Bár bizonyára izgatottan várja, hogy belevágjon a projektbe, gondoskodjon arról, hogy pontosan meghatározza a céljait és törekvéseit. Ezeket foglalja bele valamennyi tájékoztatási és képzési tevékenységbe, hogy a felhasználók tisztában legyenek azzal, miért választotta a szervezet az Intune-t.

## <a name="next-steps"></a>További lépések

Most, hogy már meghatározta a telepítési célokat, célkitűzéseket és a lehetséges kihívásokat, áttérhet a következő szakaszra: [Tipikus használatieset-forgatókönyvek](section-2-identify-use-case-scenarios.md).

