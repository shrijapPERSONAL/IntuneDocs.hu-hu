---
title: A fejlesztés – Microsoft Intune
titlesuffix: ''
description: Fejlesztés a Microsoft Intune-funkciók
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5612ae0ea6c1495fdf12e85bbed80e54bc3f287f
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394643"
---
# <a name="in-development-for-microsoft-intune---march-2019"></a>A Microsoft Intune-hoz – március 2019 fejlesztés alatt

Segítség a készültségi és tervezési, ezen a lapon listák Intune felhasználói felület frissíti, és a szolgáltatásokat, fejlesztés alatt állnak, de még nem elérhető. Továbbá:

- Ha várhatóan tovább fogjuk, hogy intézkedjen módosítása előtt kell, tesszük közzé egy ingyenes Office-Üzenetközpontban post.
- Ha egy szolgáltatás vagy előzetes elindul, éles környezetben, vagy általánosan elérhető, a szolgáltatás leírása áthelyezi ezt oldal ki, majd onnan az [Újdonságok oldalát](whats-new.md).
- Ezen a lapon, és a [Újdonságok oldalát](whats-new.md) rendszeresen frissül. További hírekért látogasson vissza.
- Tekintse meg a [M365 ütemterv](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) stratégiai le és ütemterveket.

> [!Note]
> Ezek az elemek tükrözik a Microsoft jelenlegi verziójával kapcsolatos elvárások hamarosan egy későbbi kiadásban az Intune funkcióival kapcsolatos. Dátumok és az egyes szolgáltatások változhatnak. Nem minden eleme fejlesztési rendelkeznie a szolgáltatás ezen az oldalon.

**RSS-hírcsatorna**: Értesítés küldése, amikor ezen a lapon frissül, másolása és beillesztése a következő URL-címet a hírcsatorna olvasóba szerint: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`


<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune az Azure Portalon


<!-- 1903 start-->

### <a name="scope-tags-for-app-configuration-policies---2371891---"></a>Hatókörcímkék az alkalmazáskonfigurációs szabályzatok <!--2371891 -->
Láthatja, hogy egy hatókörcímkét hozzá alkalmazás-konfigurációs házirend, így csak is az adott hatókörcímke hozzárendelt szerepkörrel rendelkező személyek hozzáférhetnek az alkalmazáskonfigurációs szabályzat. Az alkalmazáskonfigurációs szabályzat csak a megcélzott vagy az azonos hatókörcímke hozzárendelt alkalmazásokhoz vannak rendelve.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Az Autopilot-profilok hozzárendelése az összes virtuális eszközök csoport <!--2715522 -->
Autopilot-profilokat rendelhet hozzá a Minden eszköz virtuális csoporthoz. Ehhez válassza az **Eszközök beléptetése** > **Windows-regisztráció** > **Telepítési profilok** elemet > válasszon egy profilt > **Hozzárendelések** > a **Hozzárendelés a következőhöz** elemnél válassza a **Minden eszköz** lehetőséget. Az Autopilot-profilokról a [Windows-eszközök regisztrálása a Windows AutoPilot használatával](enrollment-autopilot.md) című cikkben tájékozódhat.

###  <a name="block-users-from-scanning-for-windows-updates-------3316758------"></a>A felhasználók a Windows-frissítések keresése    <!-- 3316758    -->
Adunk hozzá egy új Windows frissítési kör beállítás, amely használható, amely letiltja a felhasználók a Windows-frissítések keresése. Ez a beállítás nem lesz elérhető a portálon, de konfigurálható az Intune Graph API használatával.

### <a name="windows-update-notifications-----3316782---"></a>Windows-frissítési értesítések  <!-- 3316782 -->
Azt adja hozzá támogatást a Windows Update kör konfigurációk így konfigurálhatja a Windows Update-értesítések, amelyek megjelennek a felhasználók számára. Ez a beállítás nem lesz elérhető a portálon, de konfigurálható az Intune Graph API használatával.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Céges portál iOS 12-eszközök felhasználói regisztrációjának módosításai <!--3448635 -->  
IOS-hez készült céges portál fog frissülni, az alkalmazás regisztrációs képernyők és a mobileszköz-kezelési regisztrációs módosításokat jelent meg az Apple iOS 12.2 igazodva lépéseket. A frissített munkafolyamatot most fogja kérni a felhasználók számára:

- Nyissa meg a céges portál webhelyet (keresztül a Safari esetében), és a felügyeleti profil letöltéséhez a vállalati portál alkalmazásba való visszatérés előtt Safari engedélyezése. 
- Nyissa meg a beállítási alkalmazást a felügyeleti profil telepítésére az eszközükön.
- Térjen vissza a céges portál alkalmazás regisztráció elvégzését.  

Hogyan készítheti elő a módosítások kapcsolatos további információkért lásd: a [a Microsoft technikai Közösség post](https://aka.ms/CP_changes_iOS12). Addig is támogatásához új iOS-regisztrációk vállalati portálon, hogy frissítettük lépéseit [iOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/en-us/intune/ios-enroll). Doc módosítások után az Apple iOS-verziót 12.2 kiadások lesz élő. 

### <a name="create-and-use-device-configuration-profiles-on-android-zebra-devices-in-intune----3895244----"></a>Létrehozhat és használhat eszközkonfigurációs profilok Android Zebra eszközökön az Intune-ban <!-- 3895244  -->
Az Intune konfigurálása Android Zebra eszközöket támogatja. Pontosabban, képes lesz: 

- Eszközkonfigurációs profil létrehozása, és a beállítások StageNow által generált mobilitási bővítmények MX-profilok használatával Android Zebra-eszközökre vonatkoznak (**eszközkonfiguráció** > **profilok**  >  **Profil létrehozása** > **Android** tartozó platform).

A következőkre vonatkozik:  
- Android

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Online licenccel rendelkező Microsoft Store az üzleti alkalmazások telepítése <!-- 1672660  -->
Rendelje hozzá a szükséges online licenccel rendelkező Microsoft Store for Business-alkalmazások az eszköz a környezetben lehet. Központi telepítése a Microsoft Store for Business app így lehetővé teszi az alkalmazásnak, hogy az eszköz összes felhasználójához telepíthetők. Ez a tulajdonság csak a Windows 10 RS4 + asztali eszközökön alkalmazható. Az ügyfélalkalmazások hozzárendelés lapon találhat MSFB Online licencelt alkalmazások telepítésére, az eszköz a környezetben érhető el.

## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Lásd még:
A közelmúltbeli fejlesztésekkel kapcsolatban lásd: [Újdonságok a Microsoft Intune-ban](whats-new.md).
