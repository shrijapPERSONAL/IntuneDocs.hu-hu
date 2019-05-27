---
title: Eszközkezelés a Microsoft 365-ben
description: A Microsoft 365 Nagyvállalati verzió tartalmazza a Microsoft Intune-t. Tekintse meg, hogyan nyújt az Intune a mobileszköz-kezelés és a mobilalkalmazás-kezelés a szervezet számára. Olvassa el a gyakori forgatókönyvek és a Microsoft 365 környezetbe telepítése az Intune-nal.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/29/2019
ms.topic: conceptual
audience: ITPro
ms.service: ''
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 452cb8e4163b82d699347a33fd8dfda9c792b6fc
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050276"
---
# <a name="what-is-device-management"></a>Mi az eszközkezelés? 

Minden rendszergazda egyik fő feladata a vállalati erőforrások és adatok biztonságba helyezése és védelme. Ez a feladat *Eszközkezelés*. Felhasználók rendelkeznek számos eszközről, ahol fognak és személyes fájlok megosztása, látogasson el a websites, és telepítse az alkalmazásokat és játékokat. Ugyanazokat a felhasználókat is, az alkalmazottak, mind a tanulói. Szeretnének hozzáférni a munkahelyi és iskolai erőforrásokhoz, például az e-mailek és a OneNote eszközeiket használják. Kezelés lehetővé teszi a szervezetek számára, hogy védelmében, az erőforrások és az adatokat. 

Egy eszköz-felügyeleti szolgáltatót használ, szervezete meggyőződhet arról, hogy csak a jogosult személyek és eszközök eléréséhez szellemi tulajdont képező adatokat. Ehhez hasonlóan eszköz felhasználók is telefont, a munkahelyi adatok elérése könnyű, a úgy is, mivel azokat, hogy az eszközt a szervezeti biztonsági követelmények teljesítéséhez. Minden vállalatnál felmerülhet a kérdés: **Mit használhatnánk erőforrásaink védelme érdekében?**

A válasz [a Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune). Az Intune mobileszköz-kezelést (MDM) és mobilalkalmazás-kezelést (MAM) is kínál. Minden MDM- és MAM-megoldás fő feladatai közé tartoznak a következők:

- A különböző mobil környezet támogatja, és biztonságosan iOS, Android, Windows és MacOS rendszerű eszközök kezelése.
- Győződjön meg arról, hogy az eszközök és alkalmazások megfeleljenek a szervezet biztonsági követelményeinek.
- A szervezeti adatok biztonságban vállalati és személyes eszközök olyan házirendeket készíthetnek.
- Az ezeket a szabályzatokat érvényesítő egyetlen, egységes mobilmegoldás használata, valamint az eszközök, alkalmazások, felhasználók és csoportok kezelésének támogatása.

Az Intune a Microsoft 365 része, és integrálva van az Azure Active Directoryval (Azure AD). Az Azure AD segít szabályozni, hogy ki, mihez fér hozzá.

## <a name="hello-intune"></a>Hello, Intune!
Számos vállalat, köztük a Microsoft is az Intune használatával védi a felhasználók által vállalati vagy saját tulajdonban lévő mobileszközökön hozzáférhető, szellemi tulajdont képező adatok védelmére. Az Intune eszköz- és konfigurációs szabályzatok, a szoftverfrissítési szabályzatok és a telepítési állapotot (diagramok, táblák és jelentések) segítségével biztonságos és az adatelérés figyelésére tartalmaz.

Sokan rendelkeznek több, különböző platformokat használó eszközzel. Egy alkalmazott használhat például Surface Pro-t a munkájához, és egy Androidos mobileszközt magáncélokra. Az is gyakori, hogy az illető ezekről az eszközökről egyaránt használja az olyan vállalati erőforrásokat, amilyen az Outlook és a SharePoint.

Az Intune-nal személyenként több eszköz, és az egyes eszközökön futó több platform, például iOS, macOS, Android és Windows is kezelhető. Az Intune eszközplatform szerint elválasztja a szabályzatokat és beállításokat. Így egyszerűen, kezelése és az adott platformhoz az eszközök.

A **[Gyakori helyzetek](https://docs.microsoft.com/intune/common-scenarios)** kitűnő forrás, amelyből megtudhatja, hogyan válaszolja meg az Intune a mobileszközökkel végzett munka során gyakran felmerülő kérdéseket. Megtalálhatja a következő helyzetek ismertetését:  
- Levelezés védelme helyszíni Exchange használatával
- Az Office 365 biztonságos elérése
- Vállalati erőforrások elérése személyes eszközökkel

## <a name="integration-with-secure-and-protect-services"></a>Integráció biztonsági és védelmi szolgáltatásokkal
Minden eszközkezelési megoldás fő feladata a biztonság és a védelem. Az Intune erőssége a más szolgáltatásokkal való integráció, ennek a feladatnak a szolgálatában. Példa:

- A **Microsoft 365** kulcsszerepet játszik a gyakori informatikai feladatok egyszerűsítésében. A Microsoft 365 felügyeleti központban, felhasználók, csoportok létrehozásához és kezeléséhez. Hogy is elérheti a más szolgáltatások, például az Intune, Azure AD-ben stb. 

  Például hozzon létre egy iOS-eszközök csoportjának a Microsoft 365-ben. Az Intune ez után olyan iOS-funkciókkal kapcsolatos szabályzatokat küld le az iOS-eszközök csoportjának, mint az App Store-hozzáférés, az AirDrop használata, biztonsági másolatot készítése az iCloudban, az Apple webes szűrőjének használata és sok egyéb.

- A **Windows Defender** a Windows 10-es eszközök védelmében közreműködő számos biztonsági funkciót tartalmaz. Az Intune és a Windows Defender együttes használatával megteheti például a következőket: 

    - Engedélyezheti a [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10) megoldást, amely gyanús tevékenységeket keres mobileszközökön, fájlokban és alkalmazásokban. 
    - Használat [Windows Defender komplex veszélyforrások elleni védelem (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) a mobileszközök biztonsági problémák megelőzése érdekében. És, korlátozhatják a biztonsági incidensek blokkolja a felhasználó a céges erőforrásokhoz.

- A **Feltételes hozzáférés** az Azure Active Directory funkciója, amely jól integrálható az Intune-nal. Használatával [feltételes hozzáférési](https://docs.microsoft.com/intune/conditional-access), győződjön meg arról, hogy csak megfelelő eszközök férhessenek hozzá az e-mailt, a SharePoint és egyéb alkalmazásokhoz. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Az Önnek megfelelő eszközkezelési megoldás kiválasztása

Az eszközkezelés több módon is megközelíthető. Először az eszközök Intune-bA beépített funkciót különböző aspektusait is kezelheti. Ezt a módszert nevezik **mobileszköz-felügyelet (MDM)**. Felhasználók "igénylési" eszközeiket, és tanúsítványok használatával kommunikáljon az Intune-ban. Alkalmazások küldése informatikai rendszergazdaként az eszközökön, korlátozza az adott operációs rendszerrel, a személyes eszközök, és egyéb eszközök. Ha egy eszköz elveszett vagy ellopták, akkor eltávolíthatják az eszközről az összes adatot. 

A második megközelítés szerint az eszközökön lévő alkalmazások lesznek kezelve. Ezt a módszert nevezik **mobilalkalmazás-kezelés (MAM)**. Felhasználók személyes eszközeiket használhatják a céges erőforrások elérésére. Egy alkalmazás, például e-mail vagy a SharePoint megnyitásakor a rendszer további hitelesítést kér a felhasználótól. Ha egy eszköz elveszett vagy ellopták, akkor az eszközről az összes vállalati adat eltávolítható. 

Az [MDM és az MAM](https://docs.microsoft.com/intune/byod-technology-decisions) együtt is használható.

Az Intune beállításakor azt is kiválaszthatja, hogy csak az Azure Portalon, vagy az Intune és a Microsoft 365 együttes használatával kívánja kezelni az eszközöket. [Az Azure Portalon áttelepítése mobileszköz-felügyelet az Intune-bA](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) van a Microsoft IT esettanulmány. Ebben az esetben tanulmányi, megtudhatja, hogyan a Microsoft IT egy modern eszközfelügyeleti módszer választotta, és olvassa el, a tapasztalatok.

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
Amikor készen áll az MDM és MAM-megoldás használatának első lépései, különböző való beállítása az Intune-ban, az eszközök beléptetéséhez és a szabályzatok létrehozásának első lépéseiről. [A Microsoft 365-höz készült mobileszköz-kezelés](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) van is egy nagyszerű forrás.
