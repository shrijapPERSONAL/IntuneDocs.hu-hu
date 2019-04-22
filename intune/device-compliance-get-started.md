---
title: Eszközmegfelelőségi szabályzatok az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Használja az eszközmegfelelőségi szabályzatok állapotát és a súlyossági szintek, a türelmi időszakban állapot, a feltételes hozzáférési szabályzat és megfelelőség az Azure Portalon a különbségeket nélküli eszközök kezelése használata használatával áttekintése – első lépések és a Microsoft Intune klasszikus portálon
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
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
ms.openlocfilehash: fbed6185abe7656c3269805d1d5ed09eccbaf05e
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897017"
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
> Intune az eszköz bejelentkezési ütemezés az összes megfelelőségi értékelést követi az eszközön. [További információ az eszköz bejelentkezési ütemezés](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

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

## <a name="device-compliance-policies-work-with-azure-ad"></a>Az eszközmegfelelőségi szabályzatok használata az Azure ad-vel

Intune az Azure Active Directory (AD) használja [feltételes hozzáférési](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) (megnyílik egy másik docs-webhely) érdekében, hogy kényszerítse a megfelelőséget. Ha eszközt regisztrálják az Intune-ban, az Azure AD-regisztrációs folyamat elindul, és eszközadatokat frissül az Azure ad-ben. Az egyik legfontosabb információ az eszköz megfelelőségi állapota. Ezt a megfelelőségi állapotot használják e-mailekhez való hozzáférést engedélyező vagy blokkoló feltételes hozzáférési szabályzatokkal és egyéb munkahelyi erőforrásokhoz.

- [Az Azure Active Directory-Eszközfelügyelet](https://docs.microsoft.com/azure/active-directory/device-management-introduction) van egy nagyszerű erőforrás miért és hogyan az Azure ad-ben regisztrált eszközök.

- [Feltételes hozzáférés](conditional-access.md) és [feltételes hozzáférés használatának szokásos módjai](conditional-access-intune-common-ways-use.md) ismertetik ezt a szolgáltatást, az Intune-ra vonatkozik.

## <a name="ways-to-use-device-compliance-policies"></a>Eszközmegfelelőségi szabályzatok használatának módjai

#### <a name="with-conditional-access"></a>Feltételes hozzáféréssel

A szabályzat szabályainak megfelelő eszközök esetén eszközök hozzáférést adhat e-mailek és az egyéb munkahelyi erőforrásokhoz. Ha az eszköz nem felel meg a szabályzat szabályainak, akkor nem kap hozzáférést a munkahelyi erőforrásokhoz. Ez a feltételes hozzáférés.

#### <a name="without-conditional-access"></a>Feltételes hozzáférés nélkül

Eszközmegfelelőségi szabályzatokat a feltételes hozzáférés nélkül is használhat. A megfelelőségi szabályzatok önálló használata esetén a megcélzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Például hogy hány eszköz nincs titkosítva, vagy mely eszközök jailbreakelve vagy rootolással feltört jelentést kérhet. Megfelelőségi szabályzatokat feltételes hozzáférés nélkül használja, ha nincsenek hozzáférési korlátozások a munkahelyi erőforrásokhoz.

## <a name="ways-to-deploy-device-compliance-policies"></a>Az eszközmegfelelőségi szabályzatok üzembe helyezésének módjai

Az eszközmegfelelőségi szabályzatokat felhasználói csoportokban lévő felhasználók, illetve eszközcsoportokban lévő eszközök számára helyezheti üzembe. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer az összes felhasználói eszköz megfelelőségét ellenőrzi. A Windows 10 1803-as vagy újabb verziójával rendelkező eszközökön javasolt az eszközcsoportokba történő üzembe helyezés, *ha* az elsődleges felhasználó nem regisztrálta az eszközt. Ebben a forgatókönyvben az eszközcsoportok használata segít a megfelelőségi jelentések elkészítésében.

Intune-ban is tartalmaz egy beépített megfelelőségi szabályzat beállításai. A következő beépített szabályzatok lekérése értékeli ki az összes, az Intune-ban regisztrált eszközökön:

- **Eszköz megjelölése mint hozzárendelt megfelelőségi szabályzattal nem rendelkező**: Ez a tulajdonság két értéke van:

  - **Megfelelő**: biztonsági szolgáltatás kikapcsolva
  - **Nem megfelelő** (alapértelmezés): biztonsági szolgáltatás bekapcsolva

  Ha egy eszköz nem rendelkezik hozzárendelt megfelelőségi szabályzattal, akkor az eszközt nem megfelelőként minősíti a rendszer. Az eszközök állapota alapértelmezés szerint **Nem megfelelő**. Ha feltételes hozzáférést használ, javasoljuk, állítsa a beállítást **nem megfelelő**. Ha a felhasználó nem megfelelő, mert nincs szabályzat hozzárendelve, akkor a [céges portál alkalmazás](company-portal-app.md) látható `No compliance policies have been assigned`.

- **Továbbfejlesztett függetlenítésészlelés**: Ha engedélyezve van, ez a beállítás hatására a iOS-eszközök gyakrabban jelentkeznek be az Intune-ban. A tulajdonság engedélyezésekor a rendszer igénybe veszi az eszköz helyalapú szolgáltatásait, mely hatással van az akkumulátorhasználatra. A felhasználó tartózkodási az Intune nem tárolja.

  Ennek a beállításnak az engedélyezésekor az eszközöknek meg kell felelnie a következőknek:
  - Engedélyezze a helyalapú szolgáltatások az operációs rendszer szintjén.
  - A céges portálnak a helyalapú szolgáltatások használatának engedélyezése.
  - Jailbreakelés állapotának kiértékelése és jelentése az Intune-nak legalább 72 óránként. Máskülönben az eszköz „nem megfelelő” állapotúként lesz megjelölve. Értékelés akkor aktiválódik, a vállalati portál alkalmazás megnyitásával, vagy az eszköz 500 fogyasztásmérőit, vagy további fizikai áthelyezésével. Ha az eszköz nem helyezi át 500 mérőszámok 72 órán belüli, a felhasználónak kell nyissa meg a céges portál alkalmazást továbbfejlesztett egyes break értékeléshez.

- **Megfelelőségi állapot érvényességi időtartama (nap)**: Adja meg az időtartamot, hogy eszközök jelenteniük kell az állapotukat minden fogadott megfelelőségi szabályzat. A rendszer nem megfelelőként kezeli azokat az eszközöket, melyek ebben az időszakban nem adják vissza állapotukat. Az alapértelmezett érték 30 nap.

Ezek a beépített szabályzatok használatával figyelheti meg ezeket a beállításokat. Intune-ban is [frissíti vagy keres frissítéseket](create-compliance-policy.md#refresh-cycle-times) különböző időközönként, az eszköz platformjától függően. [Gyakori kérdések, problémák és megoldások a szabályzatok és profilok a Microsoft Intune-ban](device-profile-troubleshoot.md) akkor a leghasznosabb.

A megfelelőségi jelentések praktikus módot nyújtanak az eszközök állapotának ellenőrzésére. [Eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md) útmutatást tartalmaz.

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Meg nem felelési és a feltételes hozzáférés a különböző platformokon

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

---------------------------

|**Szabályzat-beállítás**| **Platform** |
| --- | ----|
| **PIN-kód vagy jelszó konfigurálása** | - **Android 4.0-s és újabb verziók**: Karanténba helyezve</br>- **Samsung Knox Standard 4.0 és újabb verziók**: Karanténba helyezve</br>- **Android Enterprise**: Karanténba helyezve</br></br>- **iOS 8.0 és újabb**: Kijavítva</br>- **macOS 10.11 és újabb verziók**: Kijavítva</br></br>- **Windows 8.1 és újabb verziók**: Kijavítva</br>- **Windows Phone 8.1 és újabb verziók**: Kijavítva|
| **Eszköztitkosítás** | - **Android 4.0-s és újabb verziók**: Karanténba helyezve</br>- **Samsung Knox Standard 4.0 és újabb verziók**: Karanténba helyezve</br>- **Android Enterprise**: Karanténba helyezve</br></br>- **iOS 8.0 és újabb**: Kijavítva (PIN-kód beállításával)</br>- **macOS 10.11 és újabb verziók**: Kijavítva (PIN-kód beállításával)</br></br>- **Windows 8.1 és újabb verziók**: Nem alkalmazható</br>- **Windows Phone 8.1 és újabb verziók**: Kijavítva |
| **Jailbreakelt vagy rootolt eszköz** | - **Android 4.0-s és újabb verziók**: Karanténba helyezve (nem beállítás)</br>- **Samsung Knox Standard 4.0 és újabb verziók**: Karanténba helyezve (nem beállítás)</br>- **Android Enterprise**: Karanténba helyezve (nem beállítás)</br></br>- **iOS 8.0 és újabb**: Karanténba helyezve (nem beállítás)</br>- **macOS 10.11 és újabb verziók**: Nem alkalmazható</br></br>- **Windows 8.1 és újabb verziók**: Nem alkalmazható</br>- **Windows Phone 8.1 és újabb verziók**: Nem alkalmazható |
| **E-mail profil** | - **Android 4.0-s és újabb verziók**: Nem alkalmazható</br>- **Samsung Knox Standard 4.0 és újabb verziók**: Nem alkalmazható</br>- **Android Enterprise**: Nem alkalmazható</br></br>- **iOS 8.0 és újabb**: Karanténba helyezve</br>- **macOS 10.11 és újabb verziók**: Karanténba helyezve</br></br>- **Windows 8.1 és újabb verziók**: Nem alkalmazható</br>- **Windows Phone 8.1 és újabb verziók**: Nem alkalmazható |
| **Operációs rendszer minimális verziója** | - **Android 4.0-s és újabb verziók**: Karanténba helyezve</br>- **Samsung Knox Standard 4.0 és újabb verziók**: Karanténba helyezve</br>- **Android Enterprise**: Karanténba helyezve</br></br>- **iOS 8.0 és újabb**: Karanténba helyezve</br>- **macOS 10.11 és újabb verziók**: Karanténba helyezve</br></br>- **Windows 8.1 és újabb verziók**: Karanténba helyezve</br>- **Windows Phone 8.1 és újabb verziók**: Karanténba helyezve |
| **Operációs rendszer maximális verziója** | - **Android 4.0-s és újabb verziók**: Karanténba helyezve</br>- **Samsung Knox Standard 4.0 és újabb verziók**: Karanténba helyezve</br>- **Android Enterprise**: Karanténba helyezve</br></br>- **iOS 8.0 és újabb**: Karanténba helyezve</br>- **macOS 10.11 és újabb verziók**: Karanténba helyezve</br></br>- **Windows 8.1 és újabb verziók**: Karanténba helyezve</br>- **Windows Phone 8.1 és újabb verziók**: Karanténba helyezve |
| **Windows-állapotigazolás** | - **Android 4.0-s és újabb verziók**: Nem alkalmazható</br>- **Samsung Knox Standard 4.0 és újabb verziók**: Nem alkalmazható</br>- **Android Enterprise**: Nem alkalmazható</br></br>- **iOS 8.0 és újabb**: Nem alkalmazható</br>- **macOS 10.11 és újabb verziók**: Nem alkalmazható</br></br>- **Windows 10 és Windows 10 Mobile**: Karanténba helyezve</br>- **Windows 8.1 és újabb verziók**: Karanténba helyezve</br>- **Windows Phone 8.1 és újabb verziók**: Nem alkalmazható |

---------------------------

**Szervizelt**: Az eszköz operációs rendszere megköveteli a megfelelést. Például a felhasználó köteles lesz PIN-kódot beállítani.

**Karanténba helyezve**: Az eszköz operációs rendszere nem kényszeríti ki a megfelelőséget. Android és Android Enterprise-eszközök például nem kényszerítik a felhasználót az eszköz titkosítását. Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

  - Ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik, a rendszer letiltja az eszközt.
  - A vállalati portál alkalmazás értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasszikus Azure-portál és Azure Portal

Az eszközmegfelelőségi szabályzatok Azure Portalon való használatának fő különbsége:

- Az Azure Portalon a megfelelőségi szabályzatokat minden támogatott platformhoz külön kell létrehozni
- A klasszikus Azure-portálon minden támogatott platformra ugyanaz az eszközmegfelelőségi szabályzat érvényes

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are initiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

A [klasszikus portálon](https://manage.microsoft.com) létrehozott eszközmegfelelőségi szabályzatok nem jelennek meg az [Azure Portalon](https://portal.azure.com). Továbbra is alkalmazva vannak azonban a felhasználókra, és kezelhetők a klasszikus portálon keresztül.

Az Azure Portal eszközmegfelelőséggel kapcsolatos funkcióinak használatához új eszközmegfelelőségi szabályzatokat kell létrehoznia az Azure Portalon. Ha az Azure Portalon eszközmegfelelőségi szabályzatot rendel egy olyan felhasználóhoz, akihez már a klasszikus portálon is hozzá van rendelve egy másik eszközmegfelelőségi szabályzat, akkor az Azure Portal szabályzata elsőbbséggel bír a klasszikus portálon létrehozott szabályzattal szemben.

## <a name="next-steps"></a>További lépések

- [Hozzon létre egy házirendet](create-compliance-policy.md) , és megtekintheti az előfeltételeket.
- Tekintse meg a megfelelőségi beállítások a különböző platformokhoz:

  - [Android](compliance-policy-create-android.md)
  - [Android Enterprise](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows 10 és újabb](compliance-policy-create-windows.md)
  - [Windows 8.1 és Windows Phone 8.1](compliance-policy-create-windows-8-1.md)

- [Szabályzat típusú entitások referenciája](reports-ref-policy.md) az Intune-adattárház szabályzat típusú entitásaival kapcsolatos információkat tartalmaz.