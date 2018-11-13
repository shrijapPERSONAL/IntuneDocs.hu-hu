---
title: Meg nem felelés esetén használható üzenetek és műveletek az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Értesítési e-mailt hozhat létre, és elküldheti azt a nem megfelelő eszközökre. Miután az eszköz nem megfelelőként lett megjelölve, hozzáadhat olyan műveleteket, mint a türelmi időszak kijelölése a megfelelőség teljesítéséig, vagy egy ütemterv, amely az eszköz megfelelővé válásáig letiltja a hozzáférést. Mindezt megteheti az Azure-beli Microsoft Intune használatával.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 953b468337d3317027344573d147b65d765e3db3
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236441"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz – Intune

A **Meg nem felelés esetén végrehajtandó műveletek** funkció egy időbe rendezett műveletsort állít össze. A műveletek azokra az eszközökre vonatkoznak, amelyek nem teljesítik a megfelelőségi szabályzat követelményeit. 

## <a name="overview"></a>Áttekintés
Alapértelmezés szerint az Intune a nem megfelelő eszköz észlelése után azonnal nem megfelelőként jelöli meg azt. Ekkor az Azure Active Directory (AD) [feltételes hozzáférés](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) funkciója letiltja az eszközt. A **Meg nem felelés esetén végrehajtandó műveletek** funkció rugalmas döntésekre is lehetőséget ad, ha egy eszköz nem megfelelő. Például nem kell azonnal letiltani az eszközt, hanem türelmi időszakot is meghatározhat az eszköz megfelelőségének visszaállításáig.

Többféle művelet használható:

- **E-mail küldése a felhasználónak**: Testreszabhatja az értesítő e-mailt, mielőtt elküldené a végfelhasználónak. Testre szabhatja az e-mail címzettjeit és tárgyát, az üzenet szövegét, a céges emblémát és a kapcsolattartási adatokat.

    Az Intune a nem megfelelő eszköz adatait is szerepelteti az értesítésben.

- **A nem megfelelő eszköz távoli zárolása**: A nem megfelelő eszközök esetén távoli zárolást rendelhet el. A felhasználótól az eszköz PIN-kódot vagy jelszót fog kérni az eszköz feloldásához. További információ a [Távoli zárolás](device-remote-lock.md) funkcióról. 

- **Eszköz megjelölése nem megfelelőként**: Megadhatja, hogy hány napon belül legyen nem megfelelőként megjelölve az eszköz. A műveletet konfigurálhatja azonnali kezdettel, de meghatározhat egy türelmi időszakot is a megfelelőséghez.

Ez a cikk a következőkhöz nyújt útmutatást:

- Üzenetalapú értesítés sablonjának létrehozása
- Művelet létrehozása nem megfelelőségi esetekhez, például e-mail küldése vagy eszköz távoli zárolása


## <a name="before-you-begin"></a>Előkészületek

- A meg nem felelés esetén végrehajtandó műveletek beállításához legalább egy eszközmegfelelőségi szabályzatra van szükség. Eszközmegfelelőségi szabályzat létrehozásához tekintse meg a következő platformokat:

  - [Android](compliance-policy-create-android.md)
  - [Androidos munkahelyi profilok](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Ha az eszközmegfelelőségi szabályzatot az eszközök céges erőforrásokhoz való hozzáférésének letiltásához használja, az Azure AD feltételes hozzáférést is be kell állítania. További útmutatást a [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) és [A feltételes hozzáférés használatának szokásos módjai az Intune-ban](conditional-access-intune-common-ways-use.md) című témakörökben találhat.

## <a name="create-a-notification-message-template"></a>Értesítési üzenetsablon létrehozása

Ha e-mailt szeretne küldeni a felhasználóknak, hozzon létre egy értesítési üzenetsablont. Ha egy eszköz nem megfelelő, a sablonban megadott adatok a felhasználóknak küldött e-mail tetején jelennek meg.

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközmegfelelőség** > **Értesítések** lehetőséget.
3. Válassza az **Értesítés létrehozása** lehetőséget. Adja meg az alábbi adatokat:

   - **Név**
   - **Tárgy**
   - **Üzenet**
   - **E-mail fejléce – a cég emblémájának megjelenítése**
   - **E-mail lábléce – a cég emblémájának megjelenítése**
   - **E-mail lábléce – a kapcsolatfelvételi adatok megjelenítése**

   ![Megfelelőségről szóló értesítési üzenetminta az Intune-ban](./media/actionsfornoncompliance-1.PNG)

4. Ha megadta a szükséges információkat, válassza a **Létrehozás** elemet. Az értesítési üzenet sablonja mostantól használható. Vegye figyelembe, hogy a Céges portál arculatának részeként feltöltött logó lesz használva az e-mail-sablonokban. A Céges portál arculatának kialakításáról a [Vállalati identitási arculat testreszabása](company-portal-app.md#company-identity-branding-customization) című cikk nyújt bővebb tájékoztatást.  

> [!NOTE]
> A korábban létrehozott értesítési sablonokat szerkesztheti is.

## <a name="add-actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek hozzáadása

Eszközmegfelelőségi szabályzat létrehozásakor az Intune automatikusan létrehoz egy meg nem felelés esetén végrehajtandó műveletet. Ha egy eszköz nem teljesíti a megfelelőségi szabályzat követelményeit, ez a művelet nem megfelelőként jelöli meg az eszközt. Testre szabhatja, hogy az eszköz meddig maradjon nem megfelelőként megjelölve. Ezt a műveletet nem lehet eltávolítani.

További műveletet akkor vehet fel, ha megfelelőségi szabályzatot hoz létre, vagy frissít egy meglévő szabályzatot. 

1. Az [Azure Portalon](https://portal.azure.com) nyissa meg a **Microsoft Intune** > **Eszközmegfelelőség** lapját.
2. Kattintson a **Szabályzatok** elemre, válassza ki az egyik szabályzatot, majd kattintson a **Tulajdonságok** elemre. 

    Még nincs szabályzata? Létrehozhat egy új szabályzatot [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md), vagy más platformokon.
  
    > [!NOTE]
    > A JAMF-eszközök és az eszközcsoportok segítségével megcélzott eszközök jelenleg nem képesek megfelelőségi műveleteket fogadni.

3. Válassza a **Meg nem felelés esetén végrehajtandó műveletek** > **Hozzáadás** lehetőséget.
4. Válassza ki a **műveletet**: 

    - **E-mail küldése a felhasználóknak**: Az eszköz meg nem felelése esetén e-mailt küldhet a felhasználónak. Ezenkívül: 
    
         - Válassza ki a korábban létrehozott **üzenetsablont**
         - Csoportok kiválasztásával adjon meg esetleges **további címzetteket**
    
    - **A nem megfelelő eszköz távoli zárolása**: Az eszköz meg nem felelése esetén zárolhatja az eszközt. Ez kényszeríti a felhasználót, hogy az eszköz feloldásához PIN-kódot vagy jelszót adjon meg. 
    
    - **Ütemezés**: Adja meg, hány nappal a meg nem felelés után aktiválódjon a művelet a felhasználók eszközein (0–365). A türelmi időszak után kényszerítheti a feltételes hozzáférési szabályzatot. Ha **0** napot adott meg, a feltételes hozzáférés **azonnal** életbe lép. Például azonnal letilthatja a vállalati erőforrásokhoz való hozzáférést egy eszköz meg nem felelése esetén.

5. Ha elkészült, kattintson a **Hozzáadás** > **OK** elemre a módosítások mentéséhez.

## <a name="next-steps"></a>További lépések
[Az eszköz megfelelőségi tevékenységének figyelése](device-compliance-monitor.md).
