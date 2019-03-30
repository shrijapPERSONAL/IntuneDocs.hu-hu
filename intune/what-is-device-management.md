---
title: Eszközkezelés a Microsoft 365-ben
description: A Microsoft 365 Nagyvállalati verzió tartalmazza a Microsoft Intune-t. Az Intune által a vállalata számára kínált mobileszköz-kezelés és mobilalkalmazás-kezelés ismertetése gyakori felhasználási helyzetek leírásával. A Microsoft 365 saját környezetében, az Intune használatával végzett telepítésének ismertetése.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/29/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea24101600c7a0e485440f50fc043c14bd840968
ms.sourcegitcommit: 8e6f4acb592dbe5de63aa7642ee9487288740714
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58646488"
---
# <a name="what-is-device-management"></a>Mi az eszközkezelés? 

Minden rendszergazda egyik fő feladata a vállalati erőforrások és adatok biztonságba helyezése és védelme. Ez a feladat *Eszközkezelés*. A felhasználók számos eszközzel rendelkeznek, amelyeken személyes fájlokat nyitnak és osztanak meg, webhelyeket keresnek fel, alkalmazásokat és játékokat telepítenek. Ezek a felhasználók egyben alkalmazottak és tanulók is, akik olyan munkahelyi és iskolai erőforrásokhoz akarnak hozzáférni eszközeikkel, mint a levelezés és a OneNote. Kezelés lehetővé teszi a szervezetek számára, hogy védelmében, az erőforrások és az adatokat. 

Eszközkezelési szolgáltató igénybe vételével a vállalatok biztosítani tudják, hogy csak az arra felhatalmazott egyének és eszközök férjenek hozzá a szellemi tulajdont képező információkhoz. Ezzel együtt az eszközök felhasználói is nyugodtan férhetnek hozzá telefonjaikon a munkahelyi adatokhoz annak tudatában, hogy eszközük eleget tesz vállalatuk biztonsági követelményeinek. Minden vállalatnál felmerülhet a kérdés: **Mit használhatnánk erőforrásaink védelme érdekében?**

Ekkor lép be a képbe a [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune). Az Intune mobileszköz-kezelést (MDM) és mobilalkalmazás-kezelést (MAM) is kínál. Minden MDM- és MAM-megoldás fő feladatai közé tartoznak a következők:

- Szerteágazó mobil környezet támogatása &mdash; iOS-, Android-, Windows- és macOS-eszközök biztonságos kezelése
- Annak biztosítása, hogy az eszközök és az alkalmazások megfeleljenek a vállalat biztonsági követelményeinek
- A vállalati adatok védelmét a vállalati tulajdonban lévő és személyes eszközökön is elősegítő szabályzatok létrehozása
- Az ezeket a szabályzatokat érvényesítő egyetlen, egységes mobilmegoldás használata, valamint az eszközök, alkalmazások, felhasználók és csoportok kezelésének támogatása.

Az Intune a Microsoft 365 része, és integrálva van az Azure Active Directoryval (Azure AD). Az Azure AD segít szabályozni, hogy ki, mihez fér hozzá.

## <a name="hello-intune"></a>Hello, Intune!
Számos vállalat, köztük a Microsoft is az Intune használatával védi a felhasználók által vállalati vagy saját tulajdonban lévő mobileszközökön hozzáférhető, szellemi tulajdont képező adatok védelmére. Az Intune olyan funkciókkal szolgálja az adatokhoz való hozzáférés biztonságát és figyelését, mint az eszköz- és alkalmazáskonfigurációs szabályzatok, szoftverfrissítési szabályzatok és telepítési állapotok (valamint diagramok, táblázatok és jelentések).

Sokan rendelkeznek több, különböző platformokat használó eszközzel. Egy alkalmazott használhat például Surface Pro-t a munkájához, és egy Androidos mobileszközt magáncélokra. Az is gyakori, hogy az illető ezekről az eszközökről egyaránt használja az olyan vállalati erőforrásokat, amilyen az Outlook és a SharePoint.

Az Intune-nal személyenként több eszköz, és az egyes eszközökön futó több platform, például iOS, macOS, Android és Windows is kezelhető. Az Intune eszközplatformonként különíti el a szabályzatokat és beállításokat, így az egy adott platformhoz tartozó eszközök egyszerűen kezelhetők és megtekinthetők.

A **[Gyakori helyzetek](https://docs.microsoft.com/intune/common-scenarios)** kitűnő forrás, amelyből megtudhatja, hogyan válaszolja meg az Intune a mobileszközökkel végzett munka során gyakran felmerülő kérdéseket. Megtalálhatja a következő helyzetek ismertetését:  
- Levelezés védelme helyszíni Exchange használatával
- Az Office 365 biztonságos elérése
- Vállalati erőforrások elérése személyes eszközökkel

## <a name="integration-with-secure-and-protect-services"></a>Integráció biztonsági és védelmi szolgáltatásokkal
Minden eszközkezelési megoldás fő feladata a biztonság és a védelem. Az Intune erőssége a más szolgáltatásokkal való integráció, ennek a feladatnak a szolgálatában. Példa:

- A **Microsoft 365** kulcsszerepet játszik a gyakori informatikai feladatok egyszerűsítésében. A Microsoft 365 felügyeleti központjával felhasználókat hozhat létre, kezelhet csoportokat, és hozzáférhet olyan további szolgáltatásokhoz, mint az Intune, az Azure Active Directory és sok más. A Microsoft 365-ben létrehozhatja például iOS-eszközök csoportját. Az Intune ez után olyan iOS-funkciókkal kapcsolatos szabályzatokat küld le az iOS-eszközök csoportjának, mint az App Store-hozzáférés, az AirDrop használata, biztonsági másolatot készítése az iCloudban, az Apple webes szűrőjének használata és sok egyéb.

- A **Windows Defender** a Windows 10-es eszközök védelmében közreműködő számos biztonsági funkciót tartalmaz. Az Intune és a Windows Defender együttes használatával megteheti például a következőket: 

    - Engedélyezheti a [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10) megoldást, amely gyanús tevékenységeket keres mobileszközökön, fájlokban és alkalmazásokban. 
    - A [Windows Defender Komplex veszélyforrások elleni védelem (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) használatával segíthet megelőzni a mobileszközökön történő biztonsági incidenseket, és korlátozni az incidensek következményeit azáltal, hogy letiltja a felhasználó hozzáférését a vállalati erőforrásokhoz.

- A **Feltételes hozzáférés** az Azure Active Directory funkciója, amely jól integrálható az Intune-nal. [Feltételes hozzáférés](https://docs.microsoft.com/intune/conditional-access) használatával gondoskodhat arról, hogy csak megfelelő eszközöknek engedélyezze a levelezéshez, a SharePointhoz és más alkalmazásokhoz való hozzáférést. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Az Önnek megfelelő eszközkezelési megoldás kiválasztása

Az eszközkezelés több módon is megközelíthető. Először is az eszközök minden jellemzőjét kezelni tudja az Intune összes beépített funkciójával. Ezt nevezzük **mobileszköz-kezelésnek (MDM)**. Ennél a megközelítési módnál a felhasználók „regisztrálják” eszközeiket, és tanúsítványok használatával kommunikálnak az Intune-nal. Az informatikai rendszergazdák sok más lehetőség mellett alkalmazásokat küldhetnek le az eszközökre, megkövetelhetnek egy adott operációs rendszert az eszközökön, és letilthatják a személyes eszközöket. Ha egy eszköz elveszett vagy ellopták, akkor eltávolíthatják az eszközről az összes adatot. 

A második megközelítés szerint az eszközökön lévő alkalmazások lesznek kezelve. Ezt nevezzük **mobilalkalmazás-kezelésnek (MAM)**. Ezen a módon a felhasználók saját eszközeikkel férhetnek hozzá a vállalati erőforrásokhoz. Egy alkalmazás, például e-mail vagy a SharePoint megnyitásakor a rendszer további hitelesítést kér a felhasználótól. Ha egy eszköz elveszett vagy ellopták, akkor az eszközről az összes vállalati adat eltávolítható. 

Az [MDM és az MAM](https://docs.microsoft.com/intune/byod-technology-decisions) együtt is használható.

Az Intune beállításakor azt is kiválaszthatja, hogy csak az Azure Portalon, vagy az Intune és a Microsoft 365 együttes használatával kívánja kezelni az eszközöket. A Microsoft [Mobileszköz-kezelés Intune-ba migrálása az Azure Portalon](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) című esettanulmányából megtudhatja, hogyan választott a Microsoft informatikai részlege korszerű eszközkezelési módszert, és milyen tapasztalatokat szerzett. 

## <a name="simplify-it-tasks-using-the-device-management-dashboard"></a>Informatikai feladatok egyszerűsítése a Eszközkezelés irányítópulttal

Az [Eszközkezelés irányítópulton](https://devicemanagement.portal.azure.com/) egy helyen kezelheti mobileszközeit, és végezhet rajtuk feladatokat. Az irányítópult magában foglalja az eszközkezeléshez használt szolgáltatásokat, köztük az Intune-t és az Azure Active Directoryt, és az ügyfélalkalmazások kezelésére is alkalmas. 

Az Eszközkezelés irányítópulton a következőket hajthatja végre:

- [Eszközök regisztrálása](https://docs.microsoft.com/intune/device-enrollment)
- [Eszközmegfelelőség beállítása](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Eszközök kezelése](https://docs.microsoft.com/intune/device-management)
- [Alkalmazások kezelése](https://docs.microsoft.com/intune/app-management)  
- [iOS-es e-könyvek](https://docs.microsoft.com/intune/vpp-ebooks-ios)  
- [A helyszíni Exchange-összekötő telepítése](https://docs.microsoft.com/intune/exchange-connector-install)  
- [Szerepkörök kezelése](https://docs.microsoft.com/intune/role-based-access-control)  
- Szoftverfrissítések kezelése
  - [Windows 10-frissítések kezelése](https://docs.microsoft.com/intune/windows-update-for-business-configure)  
  - [iOS-frissítések kezelése](https://docs.microsoft.com/intune/software-updates-ios)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Felhasználók kezelése](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Csoportok és tagok kezelése](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Hibaelhárítás](https://docs.microsoft.com/intune/help-desk-operators)

## <a name="next-step"></a>Következő lépés
Ha készen áll egy MDM- vagy MAM-megoldás bevezetésére, olvassa el az Intune telepítési lépéseinek végrehajtását, az eszközök regisztrálását és az első szabályzatok létrehozását ismertető, [Mobileszköz-kezelés a Microsoft 365-ben](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) című cikket. 
