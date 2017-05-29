---
title: "Megfelelőségi szabályzat létrehozása iOS rendszerhez"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Útmutató az iOS-es eszközök megfelelőségi szabályzatainak létrehozásához."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 423c6058c8a2803e62a90f309f4b9c9ad62f9ede
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune-azure-preview"></a>iOS-es eszközök megfelelőségi szabályzatainak létrehozása az Azure-beli Intune előzetesében


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A megfelelőségi szabályzatok az egyes platformokhoz jönnek létre.  Megfelelőségi szabályzatokat az Azure Portalon hozhat létre. A megfelelőségi szabályzatokról a [Mi az eszközmegfelelőség?](device-compliance.md) című témakörben találhat további információt. A megfelelőségi szabályzatok létrehozása előtt teljesítendő előfeltételekről [Az eszközmegfelelőség használatának első lépései](device-compliance-get-started.md) című témakörben találhat további információt.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

-------------------------------


| **Szabályzat-beállítás** | **iOS 8.0 vagy újabb** |
| --- | --- |
| **PIN-kód vagy jelszó konfigurálása** | Kijavítva |   
| **Eszköztitkosítás** | Kijavítva (PIN-kód beállításával) |
| **Jailbreakelt vagy rootolt eszköz** | Karanténba helyezve (nem beállítás)
| **E-mail profil** | Karanténba helyezve |
|**Operációs rendszer minimális verziója** | Karanténba helyezve |
| **Operációs rendszer maximális verziója** | Karanténba helyezve |  
| **Windows-állapotigazolás** | Nem alkalmazható |  
----------------------------


**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználó kénytelen lesz PIN-kódot beállítani.)

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Megfelelőségi szabályzat létrehozása az Azure Portal webhelyen

1. Az **Intune** panelen válassza az **Eszközmegfelelőség beállítása** lehetőséget. A **Kezelés** alatt válassza az **Összes eszközmegfelelőségi szabályzat**, majd a **Létrehozás** lehetőséget.
2. Írjon be egy nevet és egy leírást, és válassza ki azt a platformot, amelyre ez a szabályzat vonatkozik.
3. A **Megfelelőségi követelmények** területen megadhatja a **Biztonság**, az **Eszközállapot** és az **Eszköztulajdonság** beállításait. Ha elkészült, válassza az **OK** lehetőséget.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Felhasználói csoportok hozzárendelése

A megfelelőségi szabályzatok felhasználókhoz való hozzárendeléséhez válasszon egy már konfigurált szabályzatot. A meglévő szabályzatok a **Megfelelőségi szabályzatok** panelen találhatók.

1. Válassza ki azt a szabályzatot, amelyet szeretne hozzárendelni felhasználókhoz, majd válassza a **Hozzárendelések** lehetőséget. Ekkor megnyílik a panel, amelyen kiválaszthatja a kívánt **Azure Active Directory-beli biztonsági csoportokat**, és hozzárendelheti őket a szabályzathoz.
2. Válassza a **Csoportok kiválasztása** lehetőséget az Azure AD biztonsági csoportjait megjelenítő panel megnyitásához.  A **Kiválasztás** elemre kattintva telepítheti a szabályzatot a felhasználók számára.

Ezzel érvénybe léptette a szabályzatot a felhasználók számára.  A szabályzattal megcélzott felhasználók által használt eszközök megfelelőségét értékelni fogja a rendszer.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget. A jelszót használó iOS-eszközöket titkosítja a rendszer.
- **Egyszerű jelszavak engedélyezése:** Ha engedélyezni szeretné, hogy a felhasználók használhassanak olyan egyszerű jelszavakat, mint az **1234** vagy az **1111**, válassza az **Igen** lehetőséget.
- **Jelszó minimális hossza:** meghatározza a jelszóban szereplő számjegyek vagy karakterek minimális számát.
- **Megkövetelt jelszótípus:** Meghatározza, hogy a felhasználóknak **alfanumerikus** jelszót vagy **numerikus** jelszót kell-e létrehozniuk.
- **Karakterkészletek minimális száma:** Ha a **Megkövetelt jelszótípus** **Alfanumerikus**, ez a beállítás határozza meg a jelszóban használandó karakterkészletek minimális számát. A négy karakterkészlet a következő:
  - Kisbetűk
  - Nagybetűk
  - Szimbólumok
  - Számok

Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

Az iOS-eszközök esetében ez a beállítás a speciális karakterek minimális számára utal, például: **!** **#** , **&amp;**), amelynek szerepelnie kell a jelszóban.

- **Jelszó kérése ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a jelszó, ami után újat kell létrehoznia.
- **Korábbi jelszavak megjegyzése:** Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban már használt jelszavakat hozzon létre.
- **Korábbi jelszavak újbóli használatának tiltása**: Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.
- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**: Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt használhatja. A rendszer megkéri a felhasználót egy jelszó beírására a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz elérésekor.

### <a name="email-profile"></a>E-mail profil

- **Csak az Intune által felügyelt e-mail fiók használható:** Ha **Igen** értékre állítja a beállítást, az eszköznek az eszközre telepített e-mail-fiókot kell használnia. Az eszköz a következő esetekben számít nem megfelelőnek:
  - Az e-mail-profil nem a megfelelőségi szabályzat által célzott felhasználócsoporttól különböző felhasználócsoportnál van telepítve.
  - A felhasználó már beállított egy, az eszközre telepített Intune levelezési profillal egyező e-mail-fiókot az eszközön. Az Intune nem írhatja felül a felhasználó által létesített profilt, így nem kezelheti. A megfelelőség biztosítása érdekében a felhasználónak törölnie kell a meglévő e-mail-beállításokat. Ezt követően az Intune képes lesz a felügyelt e-mail-profil telepítésére.
- **Az Intune-ban felügyelni kívánt levelezési profil:** Ha a **Csak az Intune által felügyelt e-mail fiók használható** beállítás be van jelölve, kattintson a **Kiválasztás** elemre az Intune levelezési profil kiválasztásához. A levelezési profilnak megtalálhatónak kell lennie az eszközön.

Az e-mail-profilról a [Vállalati levelezéshez való hozzáférés konfigurálása e-mail-profilokkal a Microsoft Intune-ban](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) című témakörben talál további információt.

## <a name="device-health-settings"></a>Eszközállapot-beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz:** Ha bekapcsolja ezt a beállítást, a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.

## <a name="device-properties"></a>Eszköztulajdonságok

- **Az operációs rendszer szükséges minimális verziója:** Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó választhatja az eszköz frissítését. Azt követően hozzáférhet a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió:** Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->

