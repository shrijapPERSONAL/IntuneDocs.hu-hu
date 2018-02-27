---
title: "Intune-eszközmegfelelőségi szabályzatok"
titleSuffix: Azure portal
description: "Ebből a témakörből megtudhatja, mit jelent az eszközmegfelelőség fogalma a Microsoft Intune-ban"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 2/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98a9a93efb93697b454cb9bc06d1ac268ebaf9d8
ms.sourcegitcommit: cccbb6730a8c84dc3a62093b8910305081ac9d24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2018
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Az Intune eszközmegfelelőségi szabályzatai – első lépések

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Eszközmegfelelőség az Intune-ban

Az eszközöknek az Intune eszközmegfelelőségi szabályzatai által meghatározott szabályok és beállítások szerint kell működnie, hogy megfeleljen az Intune előírásainak.

Ezek a szabályok a következők:

- Jelszó megkövetelése az eszköz eléréséhez

- Encryption

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

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

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

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Az eszközök csak akkor jelenthetik megfelelőségi állapotaikat, ha regisztrálva vannak az Intune-ban.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Az Intune-eszközmegfelelőségi szabályzatok és az Azure AD együttműködése

Az eszközök Intune-beli regisztrálásakor megtörténik az Azure AD-regisztrációs folyamat, amely további információval frissíti az eszköz attribútumait az Azure AD-ben. A kulcs-eszközadatok egyike az e-mailekhez és más vállalati erőforrásokhoz való hozzáférést engedélyező vagy blokkoló feltételes hozzáférési szabályzatok által használt eszközmegfelelőségi állapot.

- Tudjon meg többet az [Azure AD-regisztrációs folyamatról](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction).

### <a name="assigning-a-resulting-device-configuration-profile-status"></a>Eszközkonfigurációs profil eredményül kapott állapotának hozzárendelése

Ha egy eszközhöz több konfigurációs profil is hozzá van rendelve, és az eszköz megfelelőségi állapota két vagy több hozzárendelt konfigurációs profil esetében eltérő, egyetlen eredményül kapott megfelelőségi állapotot kell hozzárendelni. A hozzárendelés az egyes megfelelőségi állapotokhoz hozzárendelt fogalmi szintű súlyossági szinten alapul. Az egyes megfelelőségi állapotok a következő súlyossági szinttel rendelkeznek:


|Állapot  |Severity  |
|---------|---------|
|Függőben     |1|
|Sikerült     |2|
|Sikertelen     |3|
|Hiba     |4|

Ezután a rendszer a két vagy több konfigurációs profilból eredményül kapott állapotot rendeli hozzá az eszközhöz hozzárendelt összes profilé közül a legmagasabb súlyossági szint kiválasztásával.

Tegyük fel például, hogy egy eszközhöz három profil van hozzárendelve: egy Függőben állapotú (súlyosság = 1), egy Sikerült állapotú (súlyosság = 2), és egy Hiba állapotú (súlyosság = 4). A Hiba állapot súlyossági szintje a legmagasabb, így a rendszer mindhárom profilhoz ezt rendeli hozzá eredményül kapott megfelelőségi állapotként.

### <a name="assigning-an-ingraceperiod-status-for-an-assigned-compliance-policy"></a>Türelmi időszakban állapot hozzárendelése hozzárendelt megfelelőségi szabályzatokhoz

A megfelelőségi szabályzatok Türelmi időszakban állapotértéket az adott eszköz türelmi időszaka és az eszköz a hozzárendelt megfelelőségi szabályzatra vonatkozó tényleges állapota kombinációjának figyelembe vételével határozza meg a rendszer. 

Konkrétan, ha egy eszköz Nem megfelelő állapotú egy hozzárendelt megfelelőségi szabályzatra vonatkozóan, illetve:

- az eszközhöz nincs hozzárendelve türelmi időszak, akkor a megfelelőségi szabályzathoz a Nem megfelelő érték lesz hozzárendelve.
- az eszközhöz lejárt türelmi időszak van hozzárendelve, akkor a megfelelőségi szabályzathoz a Nem megfelelő érték lesz hozzárendelve.
- az eszköz jövőbeli türelmi időszakkal rendelkezik, akkor a megfelelőségi szabályzathoz a Türelmi időszakban érték lesz hozzárendelve.

A fentebbieket az alábbi táblázat foglalja össze:


|Aktuális megfelelőségi állapot|A hozzárendelt türelmi időszak értéke|Tényleges megfelelőségi állapot|
|---------|---------|---------|
|Nem megfelelő |Nincs hozzárendelve türelmi időszak |Nem megfelelő |
|Nem megfelelő |Tegnapi dátum|Nem megfelelő|
|Nem megfelelő |Holnapi dátum|Türelmi időszakban|

Az eszközmegfelelőségi szabályzatok figyelésével kapcsolatos további információkért lásd: [Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).

### <a name="assigning-a-resulting-compliance-policy-status"></a>Megfelelőségi szabályzat eredményül kapott állapotának hozzárendelése

Ha egy eszközhöz több megfelelőségi szabályzat is hozzá van rendelve, és az eszköz megfelelőségi állapota két vagy több hozzárendelt megfelelőségi szabályzat esetében eltérő, egyetlen eredményül kapott megfelelőségi állapotot kell hozzárendelni. A hozzárendelés az egyes megfelelőségi állapotokhoz hozzárendelt fogalmi szintű súlyossági szinten alapul. Az egyes megfelelőségi állapotok a következő súlyossági szinttel rendelkeznek: 

|Állapot  |Severity  |
|---------|---------|
|Ismeretlen     |1|
|Nem alkalmazható     |2|
|Compliant (Megfelelő)|3|
|Türelmi időszakban|4|
|Nem megfelelő|5|
|Hiba|6|

Ezután a rendszer meghatározza a két vagy több megfelelőségi szabályzatból eredményül kapott állapotot az eszközhöz hozzárendelt összes szabályzaté közül a legmagasabb súlyossági szint kiválasztásával.
 
Tegyük fel például, hogy egy eszközhöz három megfelelőségi szabályzat van hozzárendelve: egy Ismeretlen állapotú (súlyosság = 1), egy Megfelelő állapotú (súlyosság = 3) és egy Türelmi időszakban állapotú (súlyosság = 4). A Türelmi időszakban állapot súlyossági szintje a legmagasabb, így a rendszer mindhárom profilhoz ezt rendeli hozzá eredményül kapott megfelelőségi állapotként.  

##  <a name="ways-to-use-device-compliance-policies"></a>Eszközmegfelelőségi szabályzatok használatának módjai

### <a name="with-conditional-access"></a>Feltételes hozzáféréssel
A megfelelőségi szabályzatokhoz feltételes hozzáférési szabályzatokat társíthat. Ilyenkor kizárólag azok az eszközök férhetnek hozzá az e-mailekhez és más vállalati erőforrásokhoz, amelyek eleget tesznek egy vagy több megfelelőségi szabályzatnak.

### <a name="without-conditional-access"></a>Feltételes hozzáférés nélkül
Eszközmegfelelőségi szabályzatokat a feltételes hozzáféréstől függetlenül is használhat. A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Jelentést kérhet például arról, hogy hány eszköz nincs titkosítva, vagy mely eszközök vannak jailbreakelve vagy rootolva. De ha önállóan alkalmazza a megfelelőségi szabályzatokat, akkor nem korlátozza a rendszer a vállalati erőforrásokhoz való hozzáférést.

A megfelelőségi szabályzatokat felhasználókra lehet alkalmazni. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer a felhasználói eszközök megfelelőségét ellenőrzi. Arról, hogy mennyi idővel a szabályzat életbe léptetése után kapják meg a mobileszközök a szabályzatot, [Eszközprofilok hibaelhárítása a Microsoft Intune-ban](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned) című cikk nyújt tájékoztatást.

#### <a name="actions-for-non-compliance"></a>Meg nem felelés esetén végrehajtandó műveletek

A Meg nem felelés esetén végrehajtandó műveletekkel időrendbe állított műveleteket alkalmazhat a megfelelőségi szabályzat követelményeit nem teljesítő eszközökre. További információért lásd: [Meg nem felelés esetén végrehajtandó műveletek automatizálása](actions-for-noncompliance.md).

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

- Eszközmegfelelőségi szabályzat létrehozása az alábbi platformokhoz:

   - [Android](compliance-policy-create-android.md)
   - [Android for work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- Az Intune-adattárház szabályzat típusú entitásaival kapcsolatos információkért lásd: [Szabályzat típusú entitások referenciája](reports-ref-policy.md).
