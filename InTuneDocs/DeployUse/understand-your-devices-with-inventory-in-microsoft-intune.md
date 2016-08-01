---
title: "A regisztrált eszközök áttekintése a leltárfunkcióval | Microsoft Intune"
description: "Az Intune használatával információkat kaphat a felügyelt eszközök hardvereire vonatkozóan."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 7d11642f13dfbe554661ecc4149c3aaf3e7448c2


---

# A regisztrált eszközök áttekintése a Microsoft Intune leltárfunkciójával
A Microsoft Intune leltárfunkcióját használva leltár készíthető a regisztrált eszközökről, illetve az Intune ügyfélszoftvert futtató Windows-számítógépekről.

## Milyen adatok gyűjthetők be a regisztrált eszközökről?
A mobileszközök által összegyűjtött leltáradatok megtekintéséhez futtassa a [Mobileszközkészlet-jelentések](understand-microsoft-intune-operations-by-using-reports.md) funkciót. Az Intune az alábbi táblázatban szereplő leltáradatokat gyűjti össze a regisztrált eszközökről:

|Tulajdonság|Gyűjtő eszköz|
|------------|-----------------------|
|**Név**|All rendszerű eszközök|
|**Operációs rendszer**|All rendszerű eszközök|
|**Gyártó**|All rendszerű eszközök|
|**Modell**|All rendszerű eszközök|
|**Kezelési csatorna**|All rendszerű eszközök|
|**Az AAD-ben regisztrált**|Mac OS X kivételével minden eszköz|
|**Compliant (Megfelelő)**|All rendszerű eszközök|
|**EAS engedélyezve**|Mac OS X kivételével minden eszköz|
|**EAS-aktiválási azonosító**|Mac OS X kivételével minden eszköz|
|**EAS-aktiválás ideje**|Mac OS X kivételével minden eszköz|
|**Kezelés állapota**|All rendszerű eszközök|
|**E-mail cím**|All rendszerű eszközök|
|**Exchange ActiveSync-azonosító**|All rendszerű eszközök|
|**Függetlenített vagy feltört**|Csak iOS- és Android-eszközök|
|**Az eszköz egyedi azonosítója**|Az Exchange ActiveSync kivételével minden eszköz|
|**Sorozatszám**|iOS-, Mac OS X-, Android-, Windows 8.1-, Windows 10-eszközök|
|**Teljes tárolóhely**|iOS-, Mac OS X-, Windows 8.1-, Windows 10-eszközök|
|**Szabad tárolóhely**|iOS-, Mac OS X-, Windows 8.1-, Windows 10-eszközök|
|**Telefonszám**<br>A vállalati eszközként besorolt telefonokat a teljes telefonszámuk jelöli (például egy mobileszközkészlet-jelentés futtatásakor). A BYOD-eszközök telefonszámai &#42; karakterekkel maszkolva, csak az utolsó 4 számjegyükkel jelennek meg.|iOS, Android és Windows Phone rendszerű eszközök|
|**IMEI**|Exchange ActiveSync-, iOS-, Android- és Windows Phone-eszközök|
|**MEID**<br>Mobilkészülék-azonosító szám|Csak iOS-eszközök|
|**Wi-Fi MAC**|Az Exchange ActiveSync kivételével minden eszköz|
|**Előfizető szolgáltatója**|Csak iOS- és Android-eszközök|
|**Mobiltechnológia**|Csak iOS- és Android-eszközök|
|**Felügyelt**|Csak iOS-eszközök|
|**Aktiválási zár állapota**|Csak iOS-eszközök|
|**A beléptetés dátuma**|All rendszerű eszközök|
|**Utolsó frissítés**|All rendszerű eszközök|
|**Ethernet MAC-cím**|Csak Mac OS X-eszközök|
|**Aktiválási zár engedélyezve**|Csak iOS-eszközök|
|**Titkosítás engedélyezve**|All rendszerű eszközök|

## Windows rendszerű számítógépekről gyűjtött adatok
> [!IMPORTANT]
> Ez a szakasz csak az Intune Windows PC-ügyfélszoftvert futtató Windows rendszerű számítógépekre vonatkozik.

A windowsos számítógépek által összegyűjtött leltáradatok megtekintéséhez futtassa a [Számítógépleltár-jelentések](understand-microsoft-intune-operations-by-using-reports.md) funkciót. Az Intune az alábbi táblázatban szereplő leltáradatokat gyűjti össze a Windows rendszerű számítógépekről:

-   **Név**

-   **Ház típusa**

-   **Gyártó**

-   **Modell**

-   **Operációs rendszer**

-   **TPM-verzió**

-   **Összesített lemezterület**

-   **Felhasznált lemezterület**

-   **Szabad lemezterület**

-   **Az operációs rendszer lemezének neve**

-   **Hely az operációs rendszer lemezén**

-   **Szabad hely az operációs rendszer lemezén**

-   **Fizikai memória**

-   **A processzor neve**

-   **Processzorarchitektúra**

-   **Processzor sebessége**

-   **IP-cím**

-   **Sorozatszám**

-   **Utolsó bejelentkező felhasználó**

-   **Hozzárendelt felhasználó**

-   **Utolsó frissítés**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->



<!--HONumber=Jul16_HO4-->


