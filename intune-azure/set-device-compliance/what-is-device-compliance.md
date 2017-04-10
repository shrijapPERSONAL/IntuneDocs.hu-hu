---
title: "Eszközmegfelelőség"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Ebből a témakörből megtudhatja, mit jelent az eszközmegfelelőség fogalma a Microsoft Intune-ban"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: f316b332c3f1b80b9d6af488943298fcfea13741
ms.openlocfilehash: 8cc5e12308871a3b023bed49e9647b888971f849
ms.lasthandoff: 03/30/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Eszközmegfelelőség az Azure-beli Intune előzetesében

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune eszközmegfelelőségi szabályzatai határozzák meg az eszközre vonatkozó szabályokat és beállításokat, amelyek ahhoz szükségesek, hogy az eszköz megfeleljen az Intune és az EMS feltételes hozzáférési szabályzatainak. A megfelelőségi szabályzatokkal figyelheti és javíthatja a megfelelőséggel kapcsolatos hibákat. 

Ezek a szabályok a következők:

- Jelszó megkövetelése az eszköz eléréséhez
- Titkosítás
- Az, hogy az eszköz jailbreakelve vagy rootolva van-e
- Az operációs rendszer minimálisan szükséges verziója
- Az operációs rendszer szükséges maximális verziója
- Az eszköz maximálisan megengedett Mobile Threat Defense-szintjének megkövetelése

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Hogyan kell használni az eszközmegfelelőségi szabályzatokat?

### <a name="using-ems-conditional-access"></a>EMS feltételes hozzáférés használata
A megfelelőségi szabályzatokhoz EMS feltételes hozzáférési szabályzatokat társíthat. Ilyenkor kizárólag azok az eszközök férhetnek hozzá az e-mailekhez és más vállalati erőforrásokhoz, amelyek eleget tesznek egy vagy több megfelelőségi szabályzatnak.

### <a name="not-using-ems-conditional-access"></a>EMS feltételes hozzáférés használata nélkül
Eszközmegfelelőségi szabályzatokat EMS feltételes hozzáféréstől függetlenül is használhat.
A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Jelentést kérhet például arról, hogy hány eszköz nincs titkosítva, vagy mely eszközök vannak jailbreakelve vagy rootolva. De ha önállóan alkalmazza a megfelelőségi szabályzatokat, akkor nem korlátozza a rendszer a vállalati erőforrásokhoz való hozzáférést.

A megfelelőségi szabályzatokat felhasználókra lehet alkalmazni. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer a felhasználói eszközök megfelelőségét ellenőrzi. Az eszközök beállításainak és funkcióinak kezelése című cikkben olvashat arról, hogy mennyi idővel a szabályzat életbe léptetése után kapják meg a mobileszközök a szabályzatot.

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Különbségek a klasszikus Intune-felügyeleti konzol és az Intune az Azure-on előzetes portálja között

Ha korábban már használta a klasszikus Intune-felügyeleti konzolt, a következő különbségek figyelembe vétele megkönnyíti az átállást az Azure Portal eszközmegfelelőségi szabályzatokkal kapcsolatos új munkafolyamatára:

-   Az Azure Portalon a megfelelőségi szabályzatokat minden támogatott platformhoz külön kell létrehozni. Az Intune felügyeleti konzolján minden támogatott platformra ugyanaz a megfelelőségi szabályzat volt érvényes.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-azure-preview-portal"></a>Migrálás a klasszikus Intune-konzolról az Azure-beli Intune-előzetes portáljára

A [klasszikus Intune-konzolon](https://manage.microsoft.com) létrehozott eszközmegfelelőségi szabályzatok nem jelennek meg az új [Azure-beli Intune-portálon](https://portal.azure.com), de továbbra is érintik a felhasználókat, és kezelhetők a klasszikus Intune-konzolon.

Ha szeretné kihasználni az Azure-beli Intune-portál eszközmegfelelőséggel kapcsolatos új funkcióit, akkor az Azure-beli Intune-portálon kell új eszközmegfelelőségi szabályzatokat létrehoznia. Ha az Azure-beli Intune-portálon új eszközmegfelelőségi szabályzatot rendel egy olyan felhasználóhoz, akihez már a klasszikus Intune-konzolon is hozzá van rendelve egy másik eszközmegfelelőségi szabályzat, akkor az Azure-beli Intune-portál szabályzata elsőbbséggel bír a klasszikus Intune-konzolon létrehozottal szemben.

##  <a name="next-steps"></a>További lépések

[Bevezetés az eszközmegfelelőségi szabályzatokba](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->

