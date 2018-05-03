---
title: Meg nem felelés esetén használható üzenetek és műveletek az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Értesítési e-mailt hozhat létre, és elküldheti azt a nem megfelelő eszközökre. Miután az eszköz nem megfelelőként lett megjelölve, hozzáadhat olyan műveleteket, mint a türelmi időszak kijelölése a megfelelőség teljesítéséig, vagy egy ütemterv, amely az eszköz megfelelővé válásáig letiltja a hozzáférést. Mindezt megteheti az Azure-beli Microsoft Intune használatával.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e8603ca59b46937b1529e710a8bc83aec5dd4d6
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2018
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Automatizált e-mailek és műveletek hozzáadása a nem megfelelő eszközökhöz – Intune

A **Meg nem felelés esetén végrehajtandó műveletek** funkció egy időbe rendezett műveletsort állít össze. A műveletek azokra az eszközökre vonatkoznak, amelyek nem teljesítik a megfelelőségi szabályzat követelményeit. 

## <a name="overview"></a>Áttekintés
Alapértelmezés szerint az Intune a nem megfelelő eszköz észlelése után azonnal nem megfelelőként jelöli meg azt. Ekkor az Azure Active Directory (AD) [feltételes hozzáférés](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) funkciója letiltja az eszközt. A **Meg nem felelés esetén végrehajtandó műveletek** funkció rugalmas döntésekre is lehetőséget ad, ha egy eszköz nem megfelelő. Például nem kell azonnal letiltani az eszközt, hanem türelmi időszakot is meghatározhat az eszköz megfelelőségének visszaállításáig.

Kétféle művelet használható:

- **Végfelhasználók értesítése e-mailben**: Testre szabhatja az értesítő e-mailt, mielőtt elküldené a végfelhasználónak. Testre szabhatja az e-mail címzettjeit és tárgyát, az üzenet szövegét, a céges emblémát és a kapcsolattartási adatokat.

    Az Intune a nem megfelelő eszköz adatait is szerepelteti az értesítésben.

- **Eszköz megjelölése nem megfelelőként**: Megadhatja, hogy hány napon belül legyen nem megfelelőként megjelölve az eszköz. A műveletet konfigurálhatja azonnali kezdettel, de meghatározhat egy türelmi időszakot is a megfelelőséghez.

## <a name="before-you-begin"></a>Előkészületek

- A meg nem felelés esetén végrehajtandó műveletek beállításához legalább egy eszközmegfelelőségi szabályzatra van szükség. Eszközmegfelelőségi szabályzat létrehozásához tekintse meg a következő platformokat:

  - [Android](compliance-policy-create-android.md)
  - [Android for Work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Ha az eszközmegfelelőségi szabályzatot az eszközök céges erőforrásokhoz való hozzáférésének letiltásához használja, az Azure AD feltételes hozzáférést is be kell állítania. Ehhez a [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) című témakör nyújt útmutatást.

- Létre kell hozni egy értesítési üzenetsablont. A felhasználóknak szóló e-mail kiküldéséhez ez a sablon hozza létre a nem megfelelés esetén végrehajtandó műveleteket.

## <a name="create-a-notification-message-template"></a>Értesítési üzenetsablon létrehozása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com) az Intune-os hitelesítő adataival. 
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Kattintson az **Eszközmegfelelőség**, majd az **Értesítések** elemre. 
4. Válassza az **Értesítés létrehozása** lehetőséget, majd adja meg az alábbi adatokat:

   - Név
   - Tárgy
   - Üzenet
   - E-mail fejléce – a cég emblémájának megjelenítése
   - E-mail lábléce – a cég emblémájának megjelenítése
   - E-mail lábléce – a kapcsolatfelvételi adatok megjelenítése

   ![Megfelelőségről szóló értesítési üzenetminta az Intune-ban](./media/actionsfornoncompliance-1.PNG)

Ha megadta a szükséges információkat, válassza a **Létrehozás** elemet. Az értesítési üzenet sablonja mostantól használható.

> [!NOTE]
> A korábban létrehozott értesítési sablonokat szerkesztheti is.

## <a name="add-actions-for-noncompliance"></a>Meg nem felelés esetén végrehajtandó műveletek hozzáadása

Alapértelmezés szerint az Intune automatikusan létrehoz egy meg nem felelés esetén végrehajtandó műveletet. Ha egy eszköz nem teljesíti a megfelelőségi szabályzat követelményeit, ez a művelet nem megfelelőként jelöli meg az eszközt. Testre szabhatja, hogy az eszköz meddig maradjon nem megfelelőként megjelölve. Ezt a műveletet nem lehet eltávolítani.

További műveletet akkor vehet fel, ha új megfelelőségi szabályzatot hoz létre, vagy frissíti a meglévő megfelelőségi szabályzatot. 

1. Az [Azure Portalon](https://portal.azure.com) nyissa meg a **Microsoft Intune** lapot, és kattintson az **Eszközmegfelelőség** elemre.
2. Kattintson a **Szabályzatok** elemre, válassza ki az egyik szabályzatot, majd kattintson a **Tulajdonságok** elemre. 

  Még nincs szabályzata? Létrehozhat egy új szabályzatot [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md), vagy más platformokon.
  
  > [!NOTE]
  > A JAMF-eszközök és az eszközcsoportok segítségével megcélzott eszközök jelenleg nem képesek megfelelőségi műveleteket fogadni.

3. Válassza a **Meg nem felelőség esetén végrehajtandó műveletek** lehetőséget, és kattintson a **Hozzáadás** elemre a művelet paramétereinek megadásához. Választhatja a korábban már létrehozott üzenetsablont, hozzáadhat új címzetteket, és frissítheti a türelmi időszak ütemezését. Az ütemezésben megadhatja a napok számát (0 és 365 között), majd kötelezővé teheti a feltételes hozzáférési szabályzatok érvénybe léptetését. Ha **0** napot adott meg, a feltételes hozzáférés **azonnal** letiltja a céges erőforrásokhoz való hozzáférést.

4. Ha elkészült, kattintson a **Hozzáadás** > **OK** elemre a módosítások mentéséhez.

## <a name="next-steps"></a>További lépések
Az eszköz megfelelőségi tevékenységét a jelentések futtatásával figyelheti. Ehhez [Az eszközmegfelelőség figyelése az Intune-ban](device-compliance-monitor.md) című témakörben talál útmutatást.
