---
title: Az Active Directory az Intune-összekötő proxybeállításainak konfigurálása
description: Ismerteti az Active Directory meglévő helyszíni proxykiszolgálók használata az Intune-összekötő konfigurálása.
keywords: ''
author: master11218
ms.author: tanvira
manager: smantri
ms.date: 4/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c47a7413d98467fffc26dee098a64cfeac770e4
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043551"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Meglévő helyszíni proxykiszolgálók használata

Ez a cikk ismerteti az Intune-összekötő kimenő proxy kiszolgálók használata az Active Directory konfigurálása. Az ügyfelek számára hálózati környezetekben, ahol a meglévő proxyk szolgál.

Összekötők működése kapcsolatos további információkért lásd: [megismerheti az Azure AD-alkalmazásproxy összekötőit](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors).

## <a name="bypass-outbound-proxies"></a>Kimenő Proxy megkerülése

Összekötők alapjául szolgáló operációs rendszer összetevőket kimenő kérelmek rendelkezik. Ezeket az összetevőket automatikusan megpróbálja megkeresni egy proxykiszolgálót a hálózati Proxy automatikus felderítési WPAD (Web) használatával.

Az operációs rendszer összetevők megpróbálja megkeresni a proxykiszolgálót egy DNS-címkeresése wpad.domainsuffix elvégzésével. Ha a keresési DNS-ben, egy HTTP-kérelem majd kérés érkezett wpad.dat IP-címét. A kérelem válik a proxy konfigurációs parancsprogramja a környezetben. Az összekötő válassza ki a kívánt kimenő proxykiszolgáló használja ezt a szkriptet. Azonban összekötő forgalom előfordulhat, hogy továbbra is halad át, a proxy szükség további konfigurációs beállítások miatt.

Beállíthatja, hogy az összekötő, győződjön meg arról, hogy az Azure-szolgáltatásokhoz való közvetlen kapcsolódás használ a helyszíni proxy megkerülése. Javasoljuk, hogy ez a megközelítés mindaddig, amíg a hálózati házirend lehetővé teszi, hogy, mert azt jelenti, hogy egy kisebb konfigurációs fenntartásához.

Kimenő proxy használatát az összekötő letiltásához módosítsa a: \Program Files\Microsoft Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config fájlt, és a proxykiszolgáló címét és a proxy portja a szakasz ebben a kódmintában látható:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
            <dependentAssembly>
                <assemblyIdentity name="mscorlib" publicKeyToken="b77a5c561934e089" culture="neutral"/>
                <bindingRedirect oldVersion="0.0.0.0-2.0.0.0" newVersion="4.6.0.0" />
            </dependentAssembly>
        </assemblyBinding>
    </runtime>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="SignInURL" value="https://portal.manage.microsoft.com/Home/ClientLogon"/>
        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
    </appSettings>
</configuration>
```
Győződjön meg arról, hogy az összekötő frissítési szolgáltatást is megkerüli a proxy, egy hasonló módosítást a C:\Program Files\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="BaseServiceAddress" value="https://manage.microsoft.com/" />
    </appSettings>
</configuration>
```

Ügyeljen arra, hogy az eredeti fájlok másolatait abban az esetben meg kell visszaállítania az alapértelmezett .config fájl.

Miután a konfigurációs fájlok módosítva lett, szüksége lesz az Intune-összekötő szolgáltatás újraindításához. 

1. Nyissa meg **services.msc**.
2. Keresse meg és válassza a **az Intune-hoz készült Service**.
3. Válassza ki **indítsa újra a**.

![Képernyőkép a szolgáltatás újraindítása](media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>További lépések

[Az eszközök kezeléséhez](device-management.md)