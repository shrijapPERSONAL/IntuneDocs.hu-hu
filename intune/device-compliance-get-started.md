---
title: Eszközmegfelelőségi szabályzatok az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Az eszközmegfelelőségi szabályzatok használatának követelményei, az állapotok és a súlyossági szintek áttekintése, a „Türelmi időszakban” állapot használata, a feltételes hozzáférés használata, a szabályzat nélküli eszközök kezelése, illetve az Azure Portal és a Microsoft Intune-beli klasszikus portál megfelelőségi lehetőségeinek különbségei.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 777cfa7d387c2bd19d529dbfc6d1aeab5dbad67e
ms.sourcegitcommit: af0cc27b05bf0743f7d0970f5f3822f0aab346af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/16/2018
---
# <a name="get-started-with-device-compliance-policies-in-intune"></a>Az Intune eszközmegfelelőségi szabályzatai – első lépések

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A megfelelőségi követelmények lényegében szabályok; ilyen lehet például a PIN-kód vagy a titkosítás megkövetelése az eszközön. Az eszközöknek az eszközmegfelelőségi szabályzatok által meghatározott szabályok és beállítások szerint kell működnie ahhoz, hogy a rendszer megfelelőnek minősítse őket. Ezek a szabályok a következők:

- Jelszó megkövetelése az eszköz eléréséhez

- Encryption

- Az, hogy az eszköz jailbreakelve vagy rootolva van-e

- Az operációs rendszer minimálisan szükséges verziója

- Az operációs rendszer szükséges maximális verziója

- Az eszköz maximálisan megengedett Mobile Threat Defense-szintjének megkövetelése

A megfelelőségi szabályzatokkal figyelheti eszközei megfelelőségi állapotát is.

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
Az eszközmegfelelőségi szabályzatok használatához az alábbi követelményeknek kell megfelelnie:

- Használja az alábbi előfizetéseket:

  - Intune
  - Azure Active Directory (AD) Premium

- Használjon támogatott platformot:

  - Android
  - iOS
  - macOS (előzetes verzió)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- A megfelelőségi állapotuk jelentéséhez az eszközöket regisztrálnia kell az Intune-ban.

- Támogatottak az egy felhasználóhoz regisztrált, illetve elsődleges felhasználóval nem rendelkező eszközök is. Több felhasználói környezet egyidejű használata nem támogatott.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Az Intune-eszközmegfelelőségi szabályzatok és az Azure AD együttműködése

Az eszközök Intune-beli regisztrálásakor elindul az Azure AD-regisztrációs folyamat, mely frissíti az eszköz attribútumait az Azure AD-ben. Az egyik legfontosabb információ az eszköz megfelelőségi állapota. Ezt a megfelelőségi állapotot használják a feltételes hozzáférési szabályzatok az e-mailekhez és más vállalati erőforrásokhoz való hozzáférés engedélyezéséhez vagy letiltásához.

Többet is megtudhat az [Azure AD-regisztrációs folyamatról](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction).

### <a name="assign-a-resulting-device-configuration-profile-status"></a>Eszközkonfigurációs profil eredményül kapott állapotának hozzárendelése

Ha egy eszköz több konfigurációs profillal rendelkezik, és az eszköz megfelelőségi állapota két vagy több hozzárendelt konfigurációs profil esetében eltérő, egyetlen eredményül kapott megfelelőségi állapotot rendel hozzá a rendszer. A hozzárendelés az egyes megfelelőségi állapotokhoz hozzárendelt fogalmi szintű súlyossági szinten alapul. Az egyes megfelelőségi állapotok a következő súlyossági szinttel rendelkeznek:

|Állapot  |Severity  |
|---------|---------|
|Függőben     |1|
|Sikerült     |2|
|Sikertelen     |3|
|Hiba     |4|

Ha egy eszköz több konfigurációs profillal rendelkezik, akkor az eszközhöz hozzárendelt összes profilé közül a legmagasabb súlyossági szintet rendeli hozzá a rendszer az eszközhöz.

Tegyük fel például, hogy egy eszközhöz három profil van hozzárendelve: egy Függőben állapotú (súlyosság = 1), egy Sikerült állapotú (súlyosság = 2), és egy Hiba állapotú (súlyosság = 4). A Hiba állapot súlyossági szintje a legmagasabb, így a rendszer mindhárom profilhoz a Hiba megfelelőségi állapotot rendeli hozzá.

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
Eszközmegfelelőségi szabályzatokat a feltételes hozzáférés nélkül is használhat. A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Jelentést kérhet például arról, hogy hány eszköz nincs titkosítva, vagy mely eszközök vannak jailbreakelve vagy rootolva. Ha a megfelelőségi szabályzatokat feltételes hozzáférés nélkül használja, akkor nem korlátozza a rendszer a vállalati erőforrások elérését.

## <a name="ways-to-deploy-device-compliance-policies"></a>Az eszközmegfelelőségi szabályzatok üzembe helyezésének módjai
Az eszközmegfelelőségi szabályzatokat felhasználói csoportokban lévő felhasználók, illetve eszközcsoportokban lévő eszközök számára helyezheti üzembe. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer az összes felhasználói eszköz megfelelőségét ellenőrzi.

A **Megfelelőségi szabályzat beállításai** lap (Azure Portal > Eszközmegfelelőség) az alábbi beállításokat tartalmazza:

- **Hozzárendelt megfelelőségi szabályzattal nem rendelkező eszköz megjelölése mint**: Ehhez a tulajdonsághoz két érték tartozik:

  - **Megfelelő**: biztonsági szolgáltatás kikapcsolva
  - **Nem megfelelő** (alapértelmezés): biztonsági szolgáltatás bekapcsolva

  Ha egy eszköz nem rendelkezik hozzárendelt megfelelőségi szabályzattal, akkor az eszközt nem megfelelőként minősíti a rendszer. Az eszközök állapota alapértelmezés szerint **Megfelelő**. Ha feltételes hozzáférést használ, javasoljuk, hogy módosítsa a beállítást **Nem megfelelő** értékre. Ha egy végfelhasználó nem felel meg, mert nincs szabályzat hozzárendelve, akkor a Céges portál a következőt jeleníti meg: `No compliance policies have been assigned`.

- **Függetlenítés (jailbreakelés) bővített észlelése**: E tulajdonság engedélyezése esetén az iOS-eszközök gyakrabban jelentkeznek be. A tulajdonság engedélyezésekor a rendszer igénybe veszi az eszköz helyalapú szolgáltatásait, mely hatással van az akkumulátorhasználatra. A felhasználó tartózkodási helyét az Intune nem tárolja.

  Ennek a beállításnak az engedélyezésekor az eszközöknek meg kell felelnie a következőknek:
  - Engedélyezett helyalapú szolgáltatások az operációs rendszer szintjén
  - Helyalapú szolgáltatások használatának engedélyezése a Céges portál számára
  - Jailbreakelés állapotának kiértékelése és jelentése az Intune-nak legalább 72 óránként. Máskülönben az eszköz „nem megfelelő” állapotúként lesz megjelölve.

- **Megfelelőségi állapot érvényességi időtartama (nap)**: Adja meg azt az időszakot, amelyben az eszközöknek jelenteniük kell az állapotukat minden fogadott megfelelőségi szabályzat vonatkozásában. A rendszer nem megfelelőként kezeli azokat az eszközöket, melyek ebben az időszakban nem adják vissza állapotukat. Az alapértelmezett érték 30 nap.

Minden eszköz rendelkezik egy **Alapértelmezett eszközmegfelelőségi szabályzattal** (Azure Portal > Eszközmegfelelőség). Használja ezt az alapértelmezett szabályzatot ezeknek a beállításoknak a figyeléséhez.

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
  - [Android for work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Az Intune-adattárház szabályzat típusú entitásaival kapcsolatos információkért lásd: [Szabályzat típusú entitások referenciája](reports-ref-policy.md).
