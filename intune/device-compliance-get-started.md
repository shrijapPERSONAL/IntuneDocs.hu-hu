---
title: Eszközmegfelelőségi szabályzatok az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Használja az eszközmegfelelőségi szabályzatok állapotát és a súlyossági szintek, a türelmi időszakban állapot, a feltételes hozzáférési szabályzat és megfelelőség az Azure Portalon a különbségeket nélküli eszközök kezelése használata használatával áttekintése – első lépések és a Microsoft Intune klasszikus portálon
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6a0cb69612e4cf0181fde957f06f490bede7200e
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392549"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Beállíthat szabályokat az erőforrásokhoz való hozzáférés engedélyezése a munkahelyi Intune-eszközök

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Számos mobileszköz-felügyelet (MDM) megoldás segítségével a szervezeti adatok védelme azzal, hogy a felhasználók és eszközök bizonyos követelmények teljesítéséhez. Az Intune-ban a szolgáltatás neve "megfelelőségi szabályzatok". Megfelelőségi szabályzatok határozzák meg, a szabályokat és beállításokat, amelyeket a felhasználók és eszközök megfelelőségéhez meg kell felelnie. Feltételes hozzáféréssel kombinálva, a rendszergazdák képes blokkolni a felhasználók és eszközök, amelyek nem felelnek meg a szabályokat. 

Ha például az Intune-rendszergazdák lehet szükség:

- A végfelhasználók jelszó segítségével elérni a szervezeti adatokat mobileszközökön
- Az eszköz nincs jailbreakelve vagy rootolással feltört
- Az eszköz egy minimális és maximális operációsrendszer-verzió
- Az eszköz, vagy az alatt a fenyegetettségi szint

Eszközök megfelelőségi állapotának figyelése a szervezet is használhatja ezt a szolgáltatást.

> [!IMPORTANT]
> Intune az eszköz bejelentkezési ütemezés az összes megfelelőségi értékelést követi az eszközön. [További információ az eszköz bejelentkezési ütemezés](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

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

## <a name="prerequisites"></a>Előfeltételek

Az eszközmegfelelőségi szabályzatok használatához győződjön meg:

- Használja az alábbi előfizetéseket:

  - Intune
  - Azure Active Directory (AD) Premium

- Használjon támogatott platformot:

  - Android
  - iOS
  - macOS (előzetes verzió)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- Eszközök regisztrálása az Intune-t, tekintse meg a megfelelőségi állapot

- Eszközök regisztrációja az egy felhasználó, vagy regisztráció nélkül elsődleges felhasználói. Több felhasználó számára regisztrált eszközök nem támogatottak.

## <a name="how-device-compliance-policies-work-with-azure-ad"></a>Az eszközmegfelelőségi szabályzatok működését az Azure ad-vel

Az eszközök Intune-beli regisztrálásakor elindul az Azure AD-regisztrációs folyamat, mely frissíti az eszköz attribútumait az Azure AD-ben. Az egyik legfontosabb információ az eszköz megfelelőségi állapota. Ezt a megfelelőségi állapotot használják a feltételes hozzáférési szabályzatok az e-mailekhez és más vállalati erőforrásokhoz való hozzáférés engedélyezéséhez vagy letiltásához.

Többet is megtudhat az [Azure AD-regisztrációs folyamatról](https://docs.microsoft.com/azure/active-directory/device-management-introduction).

## <a name="refresh-cycle-times"></a>Frissítse a ciklusok idejét

A megfelelőség ellenőrzésekor az Intune az azonos frissítési ciklus konfigurációs profilokat használja. Általában a idők a következők:

| Platform | A frissítés|
| --- | --- |
| iOS | 6 óránként |
| macOS | 6 óránként |
| Android | 8 óránként |
| Eszközként regisztrált Windows 10 számítógépek | 8 óránként |
| Windows Phone | 8 óránként |
| Windows 8.1 | 8 óránként |

Ha az eszköz nemrég lett regisztrálva, a megfelelőségi ellenőrzést a gyakrabban fusson:

| Platform | Gyakoriság |
| --- | --- |
| iOS | 6 órán át 15 perceként, majd 6 óránként |  
| Mac OS X | 6 órán át 15 perceként, majd 6 óránként | 
| Android | 15 percen át 3 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Windows Phone | 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Eszközként regisztrált Windows-számítógépek | 30 percen át 3 percenként, majd 8 óránként | 

Címen bármikor, a felhasználók nyissa meg a céges portál alkalmazást, és az eszköz szinkronizálása érdekében bármikor jelentkezhetnek a szabályzat.

### <a name="assign-an-ingraceperiod-status"></a>Türelmi időszakban állapot hozzárendelése

A megfelelőségi szabályzatok Türelmi időszakban állapota egy érték. Ezt az értéket a rendszer az adott eszköz türelmi időszaka és az eszközre érvényes megfelelőségi szabályzat tényleges állapota alapján határozza meg.

Konkrétan, ha egy eszköz Nem megfelelő állapotú egy hozzárendelt megfelelőségi szabályzatra vonatkozóan, illetve:

- az eszközhöz nincs hozzárendelve türelmi időszak, akkor a megfelelőségi szabályzathoz a Nem megfelelő érték lesz hozzárendelve
- az eszközhöz lejárt türelmi időszak van hozzárendelve, akkor a megfelelőségi szabályzathoz a Nem megfelelő érték lesz hozzárendelve
- az eszköz jövőbeli türelmi időszakkal rendelkezik, akkor a megfelelőségi szabályzathoz a Türelmi időszakban érték lesz hozzárendelve

Az alábbi táblázat összefoglalja ezt részletesen:

|Aktuális megfelelőségi állapot|A hozzárendelt türelmi időszak értéke|Tényleges megfelelőségi állapot|
|---------|---------|---------|
|Nem megfelelő |Nincs hozzárendelve türelmi időszak |Nem megfelelő |
|Nem megfelelő |Tegnapi dátum|Nem megfelelő|
|Nem megfelelő |Holnapi dátum|Türelmi időszakban|

Az eszközmegfelelőségi szabályzatok figyelésével kapcsolatos további információkért lásd: [Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Megfelelőségi szabályzat eredményül kapott állapotának hozzárendelése

Ha egy eszközhöz több megfelelőségi szabályzat tartozik, és az eszköz megfelelőségi állapota két vagy több hozzárendelt megfelelőségi szabályzat esetében eltérő, akkor egyetlen eredményül kapott megfelelőségi állapot lesz hozzárendelve. A hozzárendelés az egyes megfelelőségi állapotokhoz hozzárendelt fogalmi szintű súlyossági szinten alapul. Az egyes megfelelőségi állapotok a következő súlyossági szinttel rendelkeznek:

|Állapot  |Severity  |
|---------|---------|
|Ismeretlen     |1|
|Nem alkalmazható     |2|
|Compliant (Megfelelő)|3|
|Türelmi időszakban|4|
|Nem megfelelő|5|
|Hiba|6|

Ha egy eszköz több megfelelőségi szabályzattal rendelkezik, akkor az eszközhöz hozzárendelt összes szabályzaté közül a legmagasabb súlyossági szintet rendeli hozzá a rendszer az eszközhöz.

Tegyük fel például, hogy egy eszközhöz három megfelelőségi szabályzat van hozzárendelve: egy Ismeretlen állapotú (súlyosság = 1), egy Megfelelő állapotú (súlyosság = 3) és egy Türelmi időszakban állapotú (súlyosság = 4). A Türelmi időszakban állapot súlyossági szintje a legmagasabb, így a rendszer mindhárom szabályzathoz a Türelmi időszakban állapotot rendeli hozzá.

## <a name="ways-to-use-device-compliance-policies"></a>Eszközmegfelelőségi szabályzatok használatának módjai

#### <a name="with-conditional-access"></a>Feltételes hozzáféréssel
A szabályzat szabályainak megfelelő eszközök hozzáférést kapnak az e-mailekhez és más vállalati erőforrásokhoz. Ha egy eszköz nem felel meg a szabályzat szabályainak, akkor nem kap hozzáférést a vállalati erőforrásokhoz. Ez a feltételes hozzáférés.

#### <a name="without-conditional-access"></a>Feltételes hozzáférés nélkül
Eszközmegfelelőségi szabályzatokat a feltételes hozzáférés nélkül is használhat. A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Például hogy hány eszköz nincs titkosítva, vagy mely eszközök jailbreakelve vagy rootolással feltört jelentést kérhet. Megfelelőségi szabályzatokat feltételes hozzáférés nélkül használja, ha nincsenek hozzáférési korlátozások a munkahelyi erőforrásokhoz.

## <a name="ways-to-deploy-device-compliance-policies"></a>Az eszközmegfelelőségi szabályzatok üzembe helyezésének módjai
Az eszközmegfelelőségi szabályzatokat felhasználói csoportokban lévő felhasználók, illetve eszközcsoportokban lévő eszközök számára helyezheti üzembe. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer az összes felhasználói eszköz megfelelőségét ellenőrzi. A Windows 10 1803-as vagy újabb verziójával rendelkező eszközökön javasolt az eszközcsoportokba történő üzembe helyezés, *ha* az elsődleges felhasználó nem regisztrálta az eszközt. Ebben a forgatókönyvben az eszközcsoportok használata segít a megfelelőségi jelentések elkészítésében.

Beépített megfelelőségiszabályzat-beállítások készletét (**Intune** > **eszközmegfelelőség**) lekérdezi értékeli ki az összes Intune-ban regisztrált eszközökön. Ezek a következők:

- **Eszköz megjelölése mint hozzárendelt megfelelőségi szabályzattal nem rendelkező**: Ez a tulajdonság két értéke van:

  - **Megfelelő**: biztonsági szolgáltatás kikapcsolva
  - **Nem megfelelő** (alapértelmezés): biztonsági szolgáltatás bekapcsolva

  Ha egy eszköz nem rendelkezik hozzárendelt megfelelőségi szabályzattal, akkor az eszközt nem megfelelőként minősíti a rendszer. Az eszközök állapota alapértelmezés szerint **Nem megfelelő**. Ha feltételes hozzáférést használ, javasoljuk, állítsa a beállítást **nem megfelelő**. Ha a felhasználó nem megfelelő, mert nincs szabályzat hozzárendelve, vállalati portál megjeleníti a `No compliance policies have been assigned`.

- **Továbbfejlesztett függetlenítésészlelés**: Ha engedélyezve van, ez a beállítás hatására a iOS-eszközök gyakrabban jelentkeznek be az Intune-ban. A tulajdonság engedélyezésekor a rendszer igénybe veszi az eszköz helyalapú szolgáltatásait, mely hatással van az akkumulátorhasználatra. A felhasználó tartózkodási helyét az Intune nem tárolja.

  Ennek a beállításnak az engedélyezésekor az eszközöknek meg kell felelnie a következőknek:
  - Engedélyezett helyalapú szolgáltatások az operációs rendszer szintjén
  - Helyalapú szolgáltatások használatának engedélyezése a Céges portál számára
  - Jailbreakelés állapotának kiértékelése és jelentése az Intune-nak legalább 72 óránként. Máskülönben az eszköz „nem megfelelő” állapotúként lesz megjelölve. Az értékelés akkor indul el, ha megnyitja a Céges portál alkalmazást, vagy legalább 500 méterrel fizikailag áthelyezi az eszközt. Ha az eszköz nem helyezi át 500 mérőszámok 72 órán belüli, a felhasználónak kell nyissa meg a céges portál alkalmazást továbbfejlesztett egyes break értékeléshez.

- **Megfelelőségi állapot érvényességi időtartama (nap)**: Adja meg az időtartamot, hogy eszközök jelenteniük kell az állapotukat minden fogadott megfelelőségi szabályzat. A rendszer nem megfelelőként kezeli azokat az eszközöket, melyek ebben az időszakban nem adják vissza állapotukat. Az alapértelmezett érték 30 nap.

Minden eszköz rendelkezik egy **Beépített eszközmegfelelőségi szabályzattal** (Azure Portal > Eszközmegfelelőség). Használja ezt a beépített szabályzatot ezeknek a beállításoknak a figyeléséhez.

Arról, hogy mennyi idővel a szabályzat életbe léptetése után kapják meg a mobileszközök a szabályzatot, az [Eszközprofilok hibaelhárítása](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned) című cikk nyújt tájékoztatást.

A megfelelőségi jelentések praktikus módot nyújtanak az eszközök állapotának ellenőrzésére. Útmutatásért lásd: [Megfelelőségi szabályzatok figyelése](compliance-policy-monitor.md).

### <a name="actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek
Konfigurálhat egy olyan műveletsorozatot, amelyet a rendszer a megfelelőségi szabályzat követelményeit nem teljesítő eszközökre alkalmaz. Ezeket a meg nem felelő eszközökön végrehajtott műveleteket automatizálhatja is, a [Meg nem felelés esetén végrehajtandó műveletek automatizálása](actions-for-noncompliance.md) című cikk útmutatását követve.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasszikus Azure-portál és Azure Portal

Az eszközmegfelelőségi szabályzatok Azure Portalon való használatának fő különbsége:

- Az Azure Portalon a megfelelőségi szabályzatokat minden támogatott platformhoz külön kell létrehozni
- A klasszikus Azure-portálon minden támogatott platformra ugyanaz az eszközmegfelelőségi szabályzat érvényes

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Eszközmegfelelőségi szabályzatok a klasszikus portálon és az Azure Portalon

A [klasszikus portálon](https://manage.microsoft.com) létrehozott eszközmegfelelőségi szabályzatok nem jelennek meg az [Azure Portalon](https://portal.azure.com). Továbbra is alkalmazva vannak azonban a felhasználókra, és kezelhetők a klasszikus portálon keresztül.

Az Azure Portal eszközmegfelelőséggel kapcsolatos funkcióinak használatához új eszközmegfelelőségi szabályzatokat kell létrehoznia az Azure Portalon. Ha az Azure Portalon eszközmegfelelőségi szabályzatot rendel egy olyan felhasználóhoz, akihez már a klasszikus portálon is hozzá van rendelve egy másik eszközmegfelelőségi szabályzat, akkor az Azure Portal szabályzata elsőbbséggel bír a klasszikus portálon létrehozott szabályzattal szemben.

## <a name="next-steps"></a>További lépések

- Eszközmegfelelőségi szabályzat létrehozása az alábbi platformokhoz:

  - [Android](compliance-policy-create-android.md)
  - [Androidos munkahelyi profil](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Az Intune-adattárház szabályzat típusú entitásaival kapcsolatos információkért lásd: [Szabályzat típusú entitások referenciája](reports-ref-policy.md).
