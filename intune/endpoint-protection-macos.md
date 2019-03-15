---
title: Végpontvédelem hozzáadása macOS rendszeren az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: macOS rendszerű eszközökön használjon forgalomirányítót annak meghatározására, hogy honnan lehet alkalmazásokat telepíteni, beleértve a Mac App Store áruházat is. Engedélyezzen vagy konfiguráljon tűzfalat is egyes alkalmazások engedélyezésére, alkalmazások tiltására, rejtett üzemmód használatára vagy akár bizonyos bejövő kapcsolattípusok tiltására a Microsoft Intune használatával.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c2c3a33b996a68263550fc05d3af853c263c930a
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565936"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>macOS végpontvédelem-beállítások az Intune-ban

A cikk a macOS rendszerű eszközökhöz konfigurálható, végpontvédelemre vonatkozó beállításokat mutatja be. Ezek a beállítások az eszközök forgalomirányító- és tűzfal-beállításait is tartalmazzák és eszközprofil használatával konfigurálhatók a Microsoft Intune-ban.

## <a name="gatekeeper"></a>Forgalomirányító

- **Alkalmazások ezen helyekről való letöltésének engedélyezése**: Korlátozza az alkalmazásokat attól függően, ahol a töltik le azokat. Rendeltetése az eszközök védelme a rosszindulatú szoftverekkel szemben. Csak olyan forrásokból származó alkalmazásokat engedélyezzen, amelyekben megbízik. Az engedélyezhető lehetőségek: 
  - **Mac App Store**
  - **Mac App Store és ismert fejlesztők**
  - **Bárhonnan**

- **Felhasználó felülbírálhatja a forgalomirányítót**: Megakadályozza, hogy a felhasználók felülbírálják a forgalomirányító beállítást, és megakadályozza, hogy a felhasználók kattintással telepíthet egy alkalmazást. Ha engedélyezve van, akkor a felhasználók bármilyen alkalmazást telepíteni tudnak, ha a Ctrl billentyűt lenyomva rákattintanak.

## <a name="firewall"></a>Firewall

A tűzfalat inkább a kapcsolatok alkalmazásonkénti, nem pedig portonkénti korlátozására használja. Az alkalmazásonkénti beállítások használatával könnyebben kihasználhatók a tűzfal védelmének előnyei. Segít annak megelőzésében is, hogy nem kívánt alkalmazások átvegyék a megbízható alkalmazások számára nyitott portok irányítását.

- **Használja a tűzfalat az eszközök nem engedélyezett hálózati hozzáférésének megakadályozására a kapcsolatok alkalmazásonkénti szabályozásával.**
  - **Tűzfal**: Tűzfal engedélyezése annak konfigurálásához, hogy a bejövő kapcsolatok kezelése a környezetben.
  - **A bejövő kapcsolatok**: Olyan alapvető Internet-szolgáltatások, például a DHCP, Bonjour és az IPSec kivételével minden bejövő kapcsolat blokkolása. Ez a funkció a megosztási szolgáltatásokat, például a fájlmegosztást és a képernyőmegosztást is letiltja. Ha megosztási szolgáltatásokat használ, hagyja ezt a beállítást a **Nincs konfigurálva** értéken.

- **Adott alkalmazás bejövő kapcsolatainak engedélyezése vagy tiltása**
  - **Engedélyezett alkalmazások**: Válassza ki az alkalmazásokat, amelyek számára kifejezetten engedélyezett fogadhatnak bejövő kapcsolatokat.
  - **Letiltott alkalmazások**: Válassza ki az alkalmazásokat, amelyeknek blokkolniuk kell a bejövő kapcsolatok.
  - **Rejtett üzemmód**: A rejtett üzemmód engedélyezésével megakadályozhatja a számítógép az ellenőrzési kérelmekre válaszol, a. Az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre. Az olyan váratlan kérelmeket, mint az ICMP (ping), a rendszer figyelmen kívül hagyja.
