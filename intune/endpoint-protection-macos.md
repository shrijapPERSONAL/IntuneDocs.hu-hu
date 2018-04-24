---
title: Végpontvédelem hozzáadása macOS rendszeren az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: macOS rendszerű eszközökön használjon forgalomirányítót annak meghatározására, hogy honnan lehet alkalmazásokat telepíteni, beleértve a Mac App Store áruházat is. Engedélyezzen vagy konfiguráljon tűzfalat is egyes alkalmazások engedélyezésére, alkalmazások tiltására, rejtett üzemmód használatára vagy akár bizonyos bejövő kapcsolattípusok tiltására a Microsoft Intune használatával.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 49194d49658042802cbc1148276445008ee1b09f
ms.sourcegitcommit: c3ae3c3dc46b62d9191813d25a196874ba4927be
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/28/2018
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>macOS végpontvédelem-beállítások az Intune-ban

A cikk a macOS rendszerű eszközökhöz konfigurálható, végpontvédelemre vonatkozó beállításokat mutatja be. Ezek a beállítások az eszközök forgalomirányító- és tűzfal-beállításait is tartalmazzák és eszközprofil használatával konfigurálhatók a Microsoft Intune-ban.

## <a name="gatekeeper"></a>Forgalomirányító

- **Alkalmazások letöltésének engedélyezése ezekről a helyekről**: Korlátozza az alkalmazásokat attól függően, hogy honnan töltik le azokat. Rendeltetése az eszközök védelme a rosszindulatú szoftverekkel szemben. Csak olyan forrásokból származó alkalmazásokat engedélyezzen, amelyekben megbízik. Az engedélyezhető lehetőségek: 
  - **Mac App Store**
  - **Mac App Store és ismert fejlesztők**
  - **Bárhonnan**

- **A felhasználó felülbírálhatja a forgalomirányítót**: Megakadályozza, hogy a felhasználók felülbírálják a forgalomirányító beállításait és hogy a felhasználók Ctrl+kattintással alkalmazást telepítsenek. Ha engedélyezve van, akkor a felhasználók bármilyen alkalmazást telepíteni tudnak, ha a Ctrl billentyűt lenyomva rákattintanak.

## <a name="firewall"></a>Tűzfal

A tűzfalat inkább a kapcsolatok alkalmazásonkénti, nem pedig portonkénti korlátozására használja. Az alkalmazásonkénti beállítások használatával könnyebben kihasználhatók a tűzfal védelmének előnyei. Segít annak megelőzésében is, hogy nem kívánt alkalmazások átvegyék a megbízható alkalmazások számára nyitott portok irányítását.

- **Használja a tűzfalat az eszközök nem engedélyezett hálózati hozzáférésének megakadályozására a kapcsolatok alkalmazásonkénti szabályozásával.**
  - **Tűzfal**: A tűzfal engedélyezésével konfigurálható, hogy hogyan legyenek kezelve a bejövő kapcsolatok a környezetében.
  - **Bejövő kapcsolatok**: Tiltson minden kapcsolatot az olyan alapvető Internet-szolgáltatások kivételével, mint a DHCP, Bonjour és az IPSec. Ez a funkció a megosztási szolgáltatásokat, például a fájlmegosztást és a képernyőmegosztást is letiltja. Ha megosztási szolgáltatásokat használ, hagyja ezt a beállítást a **Nincs konfigurálva** értéken.

- **Adott alkalmazás bejövő kapcsolatainak engedélyezése vagy tiltása**
  - **Engedélyezett alkalmazások**: Jelölje ki azokat az alkalmazásokat, amelyek fogadhatnak bejövő kapcsolatokat.
  - **Tiltott alkalmazások**: Jelölje ki azokat az alkalmazásokat, amelyeknek el kell utasítaniuk a bejövő kapcsolatokat.
  - **Rejtett üzemmód**: A rejtett üzemmód engedélyezésével megakadályozhatja, hogy a számítógép válaszoljon a bejövő kérelmekre. Az eszköz továbbra is válaszol az engedélyezett alkalmazásoktól érkező kérelmekre. Az olyan váratlan kérelmeket, mint az ICMP (ping), a rendszer figyelmen kívül hagyja.
