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
ms.openlocfilehash: da0aa98774f25bf290391225c6ccae56a3859c22
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59425333"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Megfelelőségi szabályzat létrehozása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az eszközmegfelelőségi szabályzatok használata kiemelten fontos, ha az Intune-t a vállalat erőforrásainak védelmére kívánja használni. Az Intune-ban létrehozhat szabályokat és beállításokat a-eszközök megfelelőségéhez, mint a minimális operációsrendszer-verzió. Ha egy eszköz nem megfelelő, a [feltételes hozzáférés](conditional-access.md) segítségével blokkolhatja a hozzáférést az adatokhoz és erőforrásokhoz.

A műveleteket meg nem felelés esetén, például az e-mailben értesítést küld a felhasználónak. Megfelelőségi szabályzatok mire, és a használatuk áttekintését lásd: [eszközmegfelelőség használatának első lépései](device-compliance-get-started.md).

Ez a cikk:

- Az előfeltételeket és a egy előírásainak való megfelelést szabályzat létrehozásának lépéseit sorolja fel.
- Bemutatja, hogyan a szabályzat hozzárendelése a felhasználói és eszközcsoportok.
- További funkciókat, például a "szűréséhez" a házirendek és a lépéseket, amelyeket nem megfelelő eszközökön hatókörcímkék ismerteti.
- A bejelentkezési frissítési ciklusok idejét, amikor az eszköz megkapja a házirend-frissítések listája.

## <a name="before-you-begin"></a>Előkészületek

Az eszközmegfelelőségi szabályzatok használatához győződjön meg:

- Használja az alábbi előfizetéseket:

  - Intune
  - Ha feltételes hozzáférést használ, akkor szüksége az Azure Active Directory (AD) Premium edition. [Az Azure Active Directory díjszabása](https://azure.microsoft.com/pricing/details/active-directory/) sorolja fel, hogy mit kap különböző kiadásait. Az Intune megfelelőségi nincs szükség Azure ad-ben.

- Használjon támogatott platformot:

  - Android
  - Vállalati Android
  - iOS
  - macOS (előzetes verzió)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Eszközök regisztrálása az Intune-ban (a megfelelőségi állapot megtekintéséhez szükséges)

- Eszközök regisztrációja az egy felhasználó, vagy regisztráció nélkül elsődleges felhasználói. Több felhasználó számára regisztrált eszközök nem támogatottak.

## <a name="create-the-policy"></a>A szabályzat létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközmegfelelőség** elemet. A következő lehetőségek állnak rendelkezésére:

    - **Áttekintés**: Megjeleníti a összefoglalását és megfelelő eszközök, nem értékeli ki, hány és így tovább. A házirendek és a szabályzatok egyes beállításainak is megjeleníti. [Az Intune eszközmegfelelőségi szabályzatok figyeléséhez](compliance-policy-monitor.md) néhány hasznos információkat nyújt.
    - **Kezelése**: Szabályzatok létrehozása, küldése [értesítések](quickstart-send-notification.md) és a nem megfelelő eszközök engedélyezése [szintaxiskiemeléshez hálózati](use-network-locations.md).
    - **A figyelő**: Az eszközök, valamint a beállítás, és a házirend szintjén megfelelőségi állapotának ellenőrzéséhez. [Az Intune eszközmegfelelőségi szabályzatok figyeléséhez](compliance-policy-monitor.md) akkor a leghasznosabb. Megtekintheti a naplókat és az eszközök fenyegetések ügynök állapotának ellenőrzéséhez.
    - **A telepítő**: Használja a [beépített szabályzatok](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), engedélyezése [a Windows Defender komplex veszélyforrások elleni védelem (ATP)](advanced-threat-protection.md), adjon hozzá egy [mobile threat defense-összekötő](mobile-threat-defense.md), ,és[Jamf](conditional-access-integrate-jamf.md).

3. Válassza a **Szabályzatok** > **Szabályzat létrehozása** lehetőséget. Adja meg a következő tulajdonságokat:

    - **Név**: Adjon meg egy leíró nevet a szabályzathoz. Adjon nevet a szabályzatok, így könnyen azonosíthatja azokat később. Például egy jó házirendnév van **megjelölése iOS feltört eszközök nem megfelelőként**.
    - **Description** (Leírás): Adja meg a házirend leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki a platform az eszközök. A választható lehetőségek:  

       - **Android**
       - **Vállalati Android**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 és újabb**
       - **Windows 10 és újabb**

    - **Beállítások**: A következő cikkek listája, és az egyes platformokra vonatkozó beállításait ismertetik:

        - [Android](compliance-policy-create-android.md)
        - [Android Enterprise](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 és újabb verziók](compliance-policy-create-windows-8-1.md)
        - [Windows 10 és újabb](compliance-policy-create-windows.md)

4. Amikor végzett, válassza ki a **OK** > **létrehozás** a módosítások mentéséhez. A házirend létrehozása, és látható a listában. Ezután a szabályzat hozzárendelése a csoportokhoz.

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

Szabályzat létrehozása után a következő lépés a szabályzat hozzárendelése a csoportokhoz:

1. Válassza ki a létrehozott szabályzatot. A meglévő szabályzatok az **Eszközmegfelelőség** > **Szabályzatok** alatt találhatók.
2. Válassza ki a szabályzatot > **hozzárendelések**. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
3. Azure AD-biztonsági csoportjait a **Kijelölt csoportok** lehetőséget választva tekintheti meg. Válassza ki a felhasználói csoportokat, a szabályzatot alkalmazni szeretné > Válasszon **mentése** a házirend telepítése a felhasználók számára.

Felhasználóra vonatkozik a szabályzat. A rendszer ekkor kiértékeli a szabályzat hatókörébe tartozó felhasználók által használt eszközök megfelelőségét.

### <a name="evaluate-how-many-users-are-targeted"></a>Kiértékelheti, hogy hány felhasználóra vonatkozik

A szabályzat hozzárendelésekor is **Evaluate** hány felhasználó érintett. Ez a funkció számítja ki a felhasználók; eszköz nem számítja ki.

1. Válassza ki az Intune-ban **eszközmegfelelőség** > **házirendek**.
2. Válasszon ki egy szabályzatot > **hozzárendelések** > **Evaluate**. Megjelenik egy üzenet, hogy hány felhasználóra vonatkozik a szabályzat.

Ha a **Evaluate** gomb szürkén jelenik meg, ellenőrizze, hogy a szabályzat hozzá van rendelve egy vagy több csoportot.

## <a name="actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek

Olyan eszközökhöz, amelyek nem felelnek meg a megfelelőségi szabályzatok automatikusan a alkalmazni egy műveletsorozatot is hozzáadhat. Módosíthatja az eszköz nem megfelelőként való megjelölésének ütemezését, megadhatja például, hogy egy nap elteltével jelölje a rendszer nem megfelelőnek az eszközt. Hozzáadhat egy második műveletet is, amely e-mailt küld a felhasználónak, ha az eszköz nem megfelelő.

A [Műveletek hozzáadása nem megfelelő eszközökhöz](actions-for-noncompliance.md) további információval szolgál, többek között értesítési e-mailt hozhat létre a felhasználók számára.

Például, a Helyek funkciót használja, és hozzáad egy helyet egy megfelelőségi szabályzatban. Az alapértelmezett meg nem felelési művelet alkalmazandó, ha kiválaszt legalább egy helyet. Ha az eszköz nem csatlakozik a megadott helyekhez, akkor azonnal nem megfelelőnek számít. Biztosíthat a felhasználóknak egy türelmi időszakot, például egy napot.

## <a name="scope-tags"></a>Hatókörcímkék

Hatókörcímkék nagyszerű módját hozzárendelése és szűrheti a házirendek adott csoportokra, például a Sales, HR, az összes USA-NC-alkalmazottak számára, és így tovább. Miután hozzáadta a beállításokat, a megfelelőségi házirendeket is hatókörcímke is hozzáadhat. [Használja a szűrő házirendek hatókörcímkék](scope-tags.md) akkor a leghasznosabb.

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
| macOS | 6 órán át 15 perceként, majd 6 óránként | 
| Android | 15 percen át 3 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Eszközként regisztrált Windows 10 számítógépek | 30 percen át 3 percenként, majd 8 óránként | 
| Windows Phone | 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Windows 8.1 | 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 

Bármikor a felhasználók nyissa meg a céges portál alkalmazást, és az eszköz szinkronizálása érdekében bármikor jelentkezhetnek a szabályzat.

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

Például, egy eszközt, a három megfelelőségi szabályzat hozzárendelve: egy ismeretlen állapotú (súlyosság = 1), egy megfelelő állapotú (súlyosság = 3), és a egy türelmi időszakban állapotú (súlyosság = 4). A türelmi időszakban állapot súlyossági szintje a legmagasabb. Így a mindhárom szabályzathoz a türelmi időszakban állapotot nincs.

## <a name="next-steps"></a>További lépések

[A szabályzatok figyelése a](compliance-policy-monitor.md).