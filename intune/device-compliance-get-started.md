---
title: "Intune-eszközmegfelelőségi szabályzatok"
titleSuffix: Intune on Azure
description: "Ebből a témakörből megtudhatja, mit jelent az eszközmegfelelőség fogalma a Microsoft Intune-ban"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9723e5a8b001068e8b7c9994723e6c7111e7a80d
ms.sourcegitcommit: abd8f9f62751e098f3f16b5b7de7eb006b7510e4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/20/2017
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Az Intune eszközmegfelelőségi szabályzatai – első lépések

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Eszközmegfelelőség az Intune-ban

Az eszközöknek az Intune eszközmegfelelőségi szabályzatai által meghatározott szabályok és beállítások szerint kell működnie, hogy megfeleljen az Intune előírásainak.

Ezek a szabályok a következők:

- Jelszó megkövetelése az eszköz eléréséhez

- Titkosítás

- Az, hogy az eszköz jailbreakelve vagy rootolva van-e

- Az operációs rendszer minimálisan szükséges verziója

- Az operációs rendszer szükséges maximális verziója

- Az eszköz maximálisan megengedett Mobile Threat Defense-szintjének megkövetelése

A megfelelőségi szabályzatokkal figyelheti eszközei megfelelőségi állapotát is.

### <a name="device-compliance-requirements"></a>Eszközmegfelelőségi követelmények

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

##  <a name="pre-requisites"></a>Előfeltételek

Az alábbi előfizetésekkel kell rendelkeznie az Intune eszközmegfelelőségi szabályzatainak használatához:

- Intune EMS

- Prémium szintű Azure AD

###  <a name="supported-platforms"></a>Támogatott platformok:

-   Android

-   iOS

-   macOS (előzetes verzió)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Az eszközök csak akkor jelenthetik megfelelőségi állapotaikat, ha regisztrálva vannak az Intune-ban.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Az Intune-eszközmegfelelőségi szabályzatok és az Azure AD együttműködése

Az eszközök Intune-beli regisztrálásakor megtörténik az Azure AD-regisztrációs folyamat, amely további információval frissíti az eszköz attribútumait az Azure AD-ben. A kulcs-eszközadatok egyike az e-mailekhez és más vállalati erőforrásokhoz való hozzáférést engedélyező vagy blokkoló feltételes hozzáférési szabályzatok által használt eszközmegfelelőségi állapot.

- Tudjon meg többet az [Azure AD-regisztrációs folyamatról](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  <a name="ways-to-use-device-compliance-policies"></a>Eszközmegfelelőségi szabályzatok használatának módjai

### <a name="with-conditional-access"></a>Feltételes hozzáféréssel
A megfelelőségi szabályzatokhoz feltételes hozzáférési szabályzatokat társíthat. Ilyenkor kizárólag azok az eszközök férhetnek hozzá az e-mailekhez és más vállalati erőforrásokhoz, amelyek eleget tesznek egy vagy több megfelelőségi szabályzatnak.

### <a name="without-conditional-access"></a>Feltételes hozzáférés nélkül
Eszközmegfelelőségi szabályzatokat a feltételes hozzáféréstől függetlenül is használhat. A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Jelentést kérhet például arról, hogy hány eszköz nincs titkosítva, vagy mely eszközök vannak jailbreakelve vagy rootolva. De ha önállóan alkalmazza a megfelelőségi szabályzatokat, akkor nem korlátozza a rendszer a vállalati erőforrásokhoz való hozzáférést.

A megfelelőségi szabályzatokat felhasználókra lehet alkalmazni. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer a felhasználói eszközök megfelelőségét ellenőrzi. Az eszközök beállításainak és funkcióinak kezelése című cikkben olvashat arról, hogy mennyi idővel a szabályzat életbe léptetése után kapják meg a mobileszközök a szabályzatot.

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Az eszközmegfelelőségi szabályzatok használata az Intune-ban – klasszikus portál és Azure Portal

Mint láthatja, a fő eltérések az új eszközmegfelelőségiszabályzat-munkafolyamatra való áttérést segítik az Azure Portal webhelyen.

- Az Azure Portalon a megfelelőségi szabályzatokat minden támogatott platformhoz külön kell létrehozni.
- A klasszikus portálon minden támogatott platformra ugyanaz az eszközmegfelelőségi szabályzat volt érvényes.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Eszközmegfelelőségi szabályzatok migrálása a klasszikus Intune-portálról az Azure Portal webhelyre

A [klasszikus Intune-portálon](https://manage.microsoft.com) létrehozott eszközmegfelelőségi szabályzatok nem jelennek meg az új [Azure-beli Intune-portálon](https://portal.azure.com), de továbbra is érintik a felhasználókat, és kezelhetők a klasszikus Intune-portálon.

Ha szeretné kihasználni az Azure-portál eszközmegfelelőséggel kapcsolatos új funkcióit, akkor az Azure Portal webhelyen kell új eszközmegfelelőségi szabályzatokat létrehoznia. Ha az Azure Portal webhelyen új eszközmegfelelőségi szabályzatot rendel egy olyan felhasználóhoz, akihez már a klasszikus Intune-portálon is hozzá van rendelve egy másik eszközmegfelelőségi szabályzat, akkor az Azure-beli Intune-portál szabályzata elsőbbséggel bír a klasszikus Intune-portálon létrehozottal szemben.

##  <a name="next-steps"></a>További lépések

Eszközmegfelelőségi szabályzat létrehozása az alábbi platformokhoz:

- [Android](compliance-policy-create-android.md)
- [Android for work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
