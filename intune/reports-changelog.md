---
title: "Intune-adattárház – módosítási napló | Microsoft Docs"
description: "Az Intune-adattárház API módosításai."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7269d0552a0c01e4702eaae861d6c24f3f4f6f02
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Az Intune-adattárház API módosítási naplója

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Maradjon naprakész az Intune-adattárház frissítéseivel kapcsolatban.

## <a name="1710"></a>1710
_Kiadás dátuma: 2017. november_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Az Aktuális felhasználó nevű új entitásgyűjtemény a jelenleg aktív felhasználói adatokra korlátozódik <!-- 1544273 -->

A **Felhasználók** entitásgyűjtemény az utolsó egy hónapról tartalmaz adatokat. A rekordok között akkor is ott vannak az adatgyűjtési időszakon belüli felhasználói állapotok, ha a felhasználót azóta eltávolították. Például az elmúlt egy hónap során hozzáadhattak az Intune-hoz egy felhasználót, majd el is távolíthatták onnan. A felhasználó a jelentés időpontjában nincs jelen, de az adatok tartalmazzák a felhasználót és állapotát. Ekkor létrehozhat egy olyan jelentést, amely megjeleníti a felhasználó korábbi jelenlétének időtartamát az adatokban.

Ezzel szemben az új **Aktuális felhasználó** entitásgyűjtemény csak azokat a felhasználókat tartalmazza, akiket nem távolítottak el. Az **Aktuális felhasználó** entitásgyűjtemény csak a jelenleg aktív felhasználókat tartalmazza. Az **Aktuális felhasználó** entitásgyűjteménnyel kapcsolatban az [Aktuális felhasználó típusú entitás referenciája](reports-ref-current-user.md) oldalon talál további információkat.

## <a name="1709"></a>1709
_Kiadás dátuma: 2017. október_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Felhasználók és eszközök társítási entitásgyűjteménye jelenik meg az Intune-adattárház adatmodelljében <!-- 1187917 -->

A felhasználók és eszközök gyűjteményének társítását végző felhasználói eszköztársítási információ használatával jelentéseket és adatvizualizációkat hozhat létre. Az adatmodell a Power BI-fájlon (PBIX) keresztül érhető el az adattárház Intune-oldaláról az OData-végpont használatával vagy egyéni ügyfél létrehozásával. További információkért lásd: [Felhasználók és eszközök társítása](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Új entitások az adattárház adatmodelljében <!-- 1479526 --><!-- -->

 - Új entitás: [**UserDeviceAssociation**](reports-ref-user-device.md). A **UserDeviceAssociation** tartalmazza a szervezet felhasználói hozzárendeléseit. A felhasználók és eszközök gyűjteményének társítását végző felhasználói eszköztársítási információ használatával jelentéseket és adatvizualizációkat hozhat létre.  
 - Megjelent az [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) entitás. Az **IntuneManagementExtension** mobileszközökhöz készült entitásokat tartalmaz, amelyek többek között a verziószámot és a telepítési állapotot követik nyomon.

## <a name="next-steps"></a>További lépések
 - Heti összesítésben [olvashat az Intune újdonságairól](whats-new.md). Emellett tájékozódhat a jövőbeni változtatásokról, a szolgáltatással kapcsolatos fontos bejelentésekről és a korábbi verziókról is. 
 - Tekintse meg [a Microsoft Intune blogját](http://go.microsoft.com/fwlink/?LinkID=273882).