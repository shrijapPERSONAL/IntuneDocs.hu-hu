---
title: "Windows-számítógép felügyeleti lehetőségeinek összehasonlítása"
description: "A vállalat által birtokolt iOS-eszközök regisztrálása az Apple Device Enrollment program (DEP) vagy az Apple Configurator eszköz segítségével"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 66c528ce018b99a7263fb1e8395125f50d5670b3
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Windows-számítógépek számítógépként és mobileszközként való felügyeletének összehasonlítása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A vállalatok a Microsoft Intune-ban kezelhetik a Windows-számítógépeket mobileszközként, a mobileszköz-kezelés (MDM) vagy számítógépként az Intune szoftverügyfél használatával.  A Microsoft azt javasolja, hogy az ügyfelek lehetőség szerint az MDM-megoldást válasszák a felügyelethez. A két választási lehetőség közötti különbség jobb megértése érdekében a következő táblázat összehasonlítja a két felügyeleti megoldást.

|**Képesség/forgatókönyv** |**Windows számítógépként**<br>Intune-szoftverügyfél | **Windows mobileszközként**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Operációs rendszerek** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Intune-portál támogatása** |[Silverlight-konzol](https://manage.microsoft.com)|[Azure Portal](https://portal.azure.com) |
|**Feltételes hozzáférés**|Nem érhető el|Elérhető <br>[Mi a feltételes hozzáférés?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Tömeges beléptetés**|Nem érhető el|Elérhető <br>[Windowsos eszközök csoportos regisztrálása](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Eszközprofilok**|Nem érhető el|Elérhető <br>[Mik azok a Microsoft Intune-eszközprofilok?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Ügynök nélküli regisztráció**|Nem érhető el |Elérhető<br>[Windows-eszközök regisztrálása](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Szoftverfrissítések kezelése**| Windows-frissítések és a Microsoft-alkalmazások frissítése<br>[Windows rendszerű számítógépek naprakészen tartása szoftverfrissítésekkel](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Vállalati Microsoft Áruház a Windows 10-hez és a Microsoft-alkalmazások frissítéséhez<br> [A Vállalati Windows Update beállításainak konfigurálása](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Szoftverlicencek kezelése**|Elérhető <br>[Windows-számítógépes szoftverek licencszerződéseinek kezelése](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Vállalat Microsoft Áruház (csak .appx-alkalmazások)<br>[A Vállalati Microsoft Áruházban vásárolt alkalmazások kezelése](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Leltár**|Elérhető <br>[Hardver- és szoftverleltár megtekintése Windows rendszerű számítógépeken](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Elérhető <br>[Alkalmazás-hozzárendelések figyelése](https://docs.microsoft.com/intune/apps-monitor)<br>[Mi az eszközkezelés?](https://docs.microsoft.com/intune/device-management)|
|**Windows tűzfalszabályzat**|Elérhető <br>[A Windows rendszerű számítógépek védelme Windows tűzfalházirendek használatával](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Nem érhető el|
|**Kártevők elleni védelem**|Endpoint Protection<br>[Windows rendszerű számítógépek biztonságossá tétele az Endpoint Protection szolgáltatással](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[A Windows Defender beállításai](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Távsegítség** |TeamViewer<br>[Távsegítség kérése és nyújtása Windows rendszerű számítógépekhez](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Nem érhető el |
|**Alkalmazástelepítés** | Nem érhető el a Vállalati Microsoft Áruházhoz,<br>.exe, .appx, és csak a több fájlból álló .msi<br>[Az Intune szoftverügyfelet futtató Windows rendszerű számítógépes alkalmazások hozzáadása](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Elérhető a Microsoft Áruház alkalmazásaihoz és az üzletági alkalmazásokhoz<br>[Windows áruházbeli alkalmazások hozzáadása](https://docs.microsoft.com/intune/store-apps-windows)<br>[Windowsos üzletági (LOB) alkalmazások hozzáadása](https://docs.microsoft.com/intune/lob-apps-windows)|
|**Alkalmazásvédelem**|Nem érhető el|Elérhető <br>[Mik azok az alkalmazásvédelmi szabályzatok?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|


### <a name="advantages-of-mdm-windows-pc-management"></a>Az MDM Windows-számítógép-felügyelet előnyei
A Windows-számítógépek modern mobileszköz-felügyelettel történő kezelése a következő előnyökkel jár:
- **Méretezhetőség** – A mobileszköz-felügyelet az Intune-felhőkezeléssel együtt méretezhető. Az Intune szoftverügyfél 7000 számítógépre korlátozódik.
- **Egyszerűség** – Az operációs rendszerben foglalt modern felügyeleti képességeket használ anélkül, hogy letöltött szoftverügyfélre kellene támaszkodnia
- **Konzisztencia** – A Windows-számítógépeket ugyanúgy kezelheti, mint az összes többi mobileszközt a cégnél
<!-- - **Cloud optimization** - -->
