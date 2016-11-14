---
title: "Az Exchange Connector hibaelhárítása | Microsoft Intune"
description: "Az Intune Exchange Connectorral kapcsolatos problémák elhárítása."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: f6b673d05e385ddfe6ef3d3e63cf857439b164de


---

# Az Exchange Connector hibaelhárítása
Ez a témakör az Intune Exchange Connectorral kapcsolatos problémák elhárításáról szól.

## Lépések a Connector konfigurációjának ellenőrzéséhez 

Tekintse át az Exchange Connector konfigurációját, és ellenőrizze, megoldódott-e a probléma.

- Az Exchange Connector kezdeti beállításánál adjon meg egy értesítési fiókot.
- Az Exchange Connector-szolgáltatásfióknak a megfelelő engedélyekkel kell rendelkeznie, hogy az Exchange Connector által használt PowerShell-parancsmagokat végrehajthassa.
- Az Exchange Connector konfigurálásakor adjon meg egy olyan ügyfélelérési kiszolgálót (CAS-t), amely a lehető legközelebb van Exchange Connectort futtató kiszolgálóhoz. A CAS és az Exchange Connector közötti kommunikációs késés eszközfelderítési késést okozhat, különösen az O365 dedikált verziójának használatakor.
- Vegye figyelembe, hogy az Exchange Connector és az Exchange-es CAS közötti szinkronizálás időbeli késéssel jár. A teljes szinkronizálás naponta egyszer, az eltérések szinkronizálása (gyors szinkronizálás) pedig kétóránként történik meg. Elképzelhető, hogy az újonnan regisztrált eszközökkel késés tapasztalható a hozzáféréskor.
- 
## Az Exchange ActiveSync-eszköz nem deríthető fel az Exchange-ből
Ellenőrizze, hogy az Exchange Connector szinkronizál-e az Exchange-kiszolgálóval. Ezt a teljes szinkronizálás vagy az eltérések szinkronizálásának naplófájljaiból állapíthatja meg. Lásd: Az Exchange Connector naplófájljai. Ha az eszköz csatlakoztatását követően sikeresen megtörtént a teljes szinkronizálás vagy az eltérések szinkronizálása, biztosan nem ez a probléma forrása. Ha nem került sor a szinkronizálásra, gyűjtse össze a szinkronizálási naplókat, és csatolja őket a támogatási kérelméhez.

- Ha egy felhasználó nem rendelkezik Intune-licenccel, az Exchange Connector nem észleli az eszközeit.
- Ha egy felhasználó elsődleges SMTP-címe különbözik az AAD-ben szereplő egyszerű felhasználónevétől, az Exchange Connector nem észleli az adott Intune/AAD-felhasználó eszközeit. Javítsa az elsődleges SMTP-címet.
- Ha az a CAS, amellyel egy felderítési ciklus alatt az Exchange Communicator kommunikál, egy Exchange 2010-es CAS, és Ön egyaránt rendelkezik Exchange 2010-es és 2013-as postaláda-kiszolgálókkal, az Exchange Connector nem észleli az Exchange 2013-as felhasználók eszközeit. A probléma megoldásához konfigurálja az Exchange Connectort, hogy egy Exchange 2013-as CAS-ra mutasson.  Noha a probléma főként az O365 dedikált verziójának topológiáit érinti, mégis azt javasoljuk ajánlott eljárásként, hogy más topológiáknál is Exchange 2013-as CAS-ra mutasson.
- Az Exchange dedikált verzióján (O365 dedikált verzióján) alapuló környezetben a kezdeti beállítás során az Exchange Connectornak egy Exchange 2013-as (és nem 2010-es) CAS felé kell mutatnia, ugyanis csak ezzel a CAS-szal kommunikál a PowerShell-parancsmagok végrehajtásakor.


## További adatok gyűjtése az Exchange Connectorral kapcsolatos problémákról a PowerShell segítségével
- Az adott postaládához tartozó mobileszközök listáját ezzel a paranccsal jelenítheti meg: Get-ActiveSyncDeviceStatistics -mailbox mbx
- A postaládához tartozó SMTP-címek listájához használja ezt a parancsot: Get-Mailbox -Identity user | select emailaddresses | fl.
- Az eszköz hozzáférési állapotáról részletes információt a következő paranccsal jeleníthet meg: Get-CASMailbox <upn> | fl

### További lépések
Ha ezek a hibaelhárítási információk nem oldották meg a problémát, forduljon a Microsoft támogatási szolgálatához a [Hogyan kérhet támogatást a Microsoft Intune-hoz](how-to-get-support-for-microsoft-intune.md) című témakörben leírtak szerint.



<!--HONumber=Oct16_HO4-->


