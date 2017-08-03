---
title: "Az Intune beállítása"
description: "Az Intune-előfizetés használatának megkezdéséhez szükséges követelmények és előfeltételek"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 966183f0da7a48148a193a1823f74b9e416f4004
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2017
---
# <a name="set-up-intune"></a>Az Intune beállítása

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

A beállítási lépések előkészítik a környezetét a mobileszköz-kezelésre.  

Ha jelenleg a Microsoft System Center Configuration Managerrel felügyeli a számítógépeket és a kiszolgálókat, [kiterjesztheti a Configuration Manager hatáskörét, hogy a mobileszközöket is felügyelje](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

>[!TIP]
>Ha egy erre jogosult csomagban megvásárol legalább 150 Intune-licencet, akkor használhatja a *FastTrack Center értékcsomagot*. Ennek a szolgáltatásnak a keretében a Microsoft szakemberei együttműködnek Önnel a környezete Intune-hoz való előkészítése érdekében. Lásd: [FastTrack Center juttatás az Enterprise Mobility + Securityhez (EMS)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).

| Lépések | Állapot  |
| ------------- |-------------|
| 1  | [Előfeltételek](supported-devices-browsers.md) – Tudnivalók a kezdés előtt|
| 2 |  [Bejelentkezés az Intune-ba](account-sign-up.md) – Jelentkezzen be a próba-előfizetésbe, vagy hozzon létre egy újat |  
| 3 | [Tartománynév konfigurálása](custom-domain-name-configure.md) – DNS-regisztráció beállítása a vállalat tartománynevének Intune-nal való összekapcsolásához  |
| 4 | [Felhasználók hozzáadása](users-add.md) – Felhasználók manuális hozzáadása, vagy kapcsolódás az Active Directoryhoz a felhasználók és az Intune szinkronizálásához  |
| 5 | [Licencek kiosztása](licenses-assign.md) – Engedélyezheti az Intune használatát a felhasználók számára|
| 6 |  [Csoportok hozzáadása](groups-add.md) – Felhasználói és eszközcsoportok használata a kezelési feladatok egyszerűsítéséhez |
| 7 | [Alkalmazások felvétele](apps-add.md) – A felhasználók számára üzembe helyezhető alkalmazások és beállítások engedélyezése |
| 8 | [Eszközök konfigurálása](device-profiles.md) – Az eszközöket és a vállalati erőforrásokhoz való hozzáférést kezelő profilok beállítása |
| 9 | [Céges portál testreszabása](company-portal-app.md) – Az Intune céges portáljának testreszabása   |
| 10 | [Eszközregisztráció engedélyezése](mdm-authority-set.md) – Engedélyezheti iOS-, Windows-, Android- és Mac-eszközök Intune általi felügyeletét |
