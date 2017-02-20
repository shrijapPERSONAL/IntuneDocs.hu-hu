---
title: "Eszközmegfelelőség | Azure-beli Intune – előzetes | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: a4254503e4e6b86079f862966dee2727934f1ee6


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Eszközmegfelelőség az Azure-beli Intune előzetesében


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A vállalati adatok védelme érdekében gondoskodnia kell arról, hogy a vállalati alkalmazások és adatok elérésére használt eszközök megfeleljenek bizonyos szabályoknak. Ilyen szabály lehet például, hogy PIN-kódot kell használni az eszközök eléréséhez, és titkosítani kell az eszközökön tárolt adatokat. Az ilyen szabályok összességét **megfelelőségi szabályzatnak** nevezzük.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Hogyan kell használni az eszközmegfelelőségi szabályzatokat?
A megfelelőségi szabályzatokhoz feltételes hozzáférési szabályzatokat társíthat – ilyenkor kizárólag azok az eszközök férhetnek hozzá az e-mailekhez és egyéb szolgáltatásokhoz, amelyek eleget tesznek a megfelelőségi szabályzatnak.

Megfelelőségi szabályzatokat feltételes hozzáféréstől függetlenül is használhat.
A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Jelentést kérhet például arról, hogy hány eszköz nincs titkosítva, vagy mely eszközök vannak jailbreakelve vagy feltörve. De ha önállóan alkalmazza a megfelelőségi szabályzatokat, akkor nem korlátozza a rendszer a vállalati erőforrásokhoz való hozzáférést.

A megfelelőségi szabályzatokat felhasználókra lehet alkalmazni. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer a felhasználói eszközök megfelelőségét ellenőrzi. Az eszközök beállításainak és funkcióinak kezelése című cikkben olvashat arról, hogy mennyi idővel a szabályzat életbe léptetése után kapják meg a mobileszközök a szabályzatot.

##  <a name="concepts"></a>Fogalmak
Az alábbiakban néhány olyan szakkifejezést és fogalmat sorolunk fel, amelyek hasznosak a megfelelőségi szabályzatok célszerű használatának megértéséhez.

### <a name="compliance-requirements"></a>Megfelelőségi követelmények
A megfelelőségi követelmények gyakorlatilag olyan szabályok (például PIN-kódhasználat vagy titkosítás megkövetelése az eszközön), amelyeket kötelezőként vagy nem kötelezőként lehet megjelölni az egyes megfelelőségi szabályzatokban.

<!---### Actions for noncompliance

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

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>A klasszikus Intune-felügyeleti konzol és az Azure Portalon lévő Intune közötti különbségek


Ha korábban már használta a klasszikus Intune-felügyeleti konzolt, a következő különbségek figyelembe vétele megkönnyíti az átállást az Azure Portal új eszközmegfelelőségi munkafolyamatára:


-   Az Azure Portalon a megfelelőségi szabályzatokat minden támogatott platformhoz külön kell létrehozni. Az Intune felügyeleti konzolján minden támogatott platformra ugyanaz a megfelelőségi szabályzat volt érvényes.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>További lépések

[Bevezetés a megfelelőségi szabályzatokba](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO1-->


