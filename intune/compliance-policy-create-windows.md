---
title: "Megfelelőségi szabályzat létrehozása Windows rendszerhez"
titleSuffix: Azure portal
description: "A cikk azt ismerteti, hogyan lehet megfelelőségi szabályzatokat létrehozni Windows-eszközökhöz.”"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 13fc7783-d4de-47d0-b1b8-4c8710a9e6ab
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 76d1bb091553fbe5a1220c818289f59f4ef4100b
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune"></a>Windowsos eszközök megfelelőségi szabályzatainak létrehozása az Intune-ban


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A megfelelőségi szabályzatok az egyes platformhoz hozhatók létre.  Megfelelőségi szabályzatok az Azure Portal webhelyen hozhatók létre. A megfelelőségi szabályzatokról a [What is a device compliance](device-compliance.md) (Mi az eszközmegfelelőség?) című témakörben találhat további információt. A megfelelőségi szabályzatok létrehozása előtt teljesítendő előfeltételekről a [Get started with device compliance](device-compliance-get-started.md) (Az eszközmegfelelőség használatának első lépései) című témakörben találhat további információt.

Az alábbi táblázat ismerteti, hogyan történik a nem megfelelő beállítások kezelése, ha a megfelelőségi szabályzatot feltételes hozzáférési szabályzattal együtt használják.

---------------------------

| **Szabályzat-beállítás** | **Windows 8.1 és újabb verziók** | **Windows Phone 8.1 és újabb verziók** |
|----| ----| --- |
| **PIN-kód vagy jelszó konfigurálása** | Kijavítva | Kijavítva |   
| **Eszköztitkosítás** | Nem alkalmazható | Kijavítva |   
| **Jailbreakelt vagy rootolt eszköz** | Nem alkalmazható | Nem alkalmazható |  
| **E-mail profil** | Nem alkalmazható | Nem alkalmazható |   
| **Operációs rendszer minimális verziója** | Karanténba helyezve | Karanténba helyezve |   
| **Operációs rendszer maximális verziója** | Karanténba helyezve | Karanténba helyezve |   
| **Windows-állapotigazolás** | Karanténba helyezve: Windows 10 és Windows 10 Mobile|Nem alkalmazható: Windows 8.1 |

-------------------------------

**Javítva** = Az eszköz operációs rendszere megköveteli a megfelelést. (Például a felhasználónak kötelező PIN-kódot beállítani.)+

**Karanténba helyezve** = Az eszköz operációs rendszere nem követeli meg a megfelelést. (Az Android-eszközök például nem követelik meg a felhasználótól az eszköz titkosítását.) A rendszer a következő műveleteket hajtja végre, ha az eszköz nem megfelelő:+

- A rendszer letiltja az eszközt, ha a felhasználóra feltételes hozzáférési szabályzat vonatkozik.
- A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Megfelelőségi szabályzat létrehozása az Azure Portal webhelyen

1. Az **Intune** panelen válassza az **Eszközmegfelelőség beállítása** lehetőséget. A **Kezelés** alatt válassza az **Összes eszközmegfelelőségi szabályzat**, majd a **Létrehozás** lehetőséget.
2. Adja meg a szabályzat nevét és leírását, majd válassza ki a platformot, amelyre alkalmazni szeretné.
3. Válassza a **Megfelelőségi követelmények** lehetőséget a megfelelőségi követelmények paneljének megnyitásához.  Itt megadhatja a **Biztonság**, az **Eszközállapot** és az **Eszköztulajdonság** beállítást. Miután elkészült, kattintson az **Ok** gombra.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
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

- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához:** Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget.
- **Egyszerű jelszavak engedélyezése:** Ha engedélyezni szeretné, hogy a felhasználók használhassanak olyan egyszerű jelszavakat, mint az **1234** vagy az **1111** válassza az **Igen** lehetőséget.
- **Jelszó minimális hossza:** Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.
- **Megkövetelt jelszótípus:** Meghatározza, hogy a felhasználóknak **alfanumerikus** vagy **numerikus** jelszót kell-e létrehozniuk.

A Windows rendszerű és Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha a jelszó minimális hossza hosszabb nyolc karakternél, vagy ha a karakterkészletek minimális száma meghaladja a kettőt.

- **Karakterkészletek minimális száma:** Ha a **Megkövetelt jelszótípus** **alfanumerikus**, ez a beállítás határozza meg a jelszóban használandó karakterkészletek minimális számát. A négy karakterkészlet a következő:
  - Kisbetűk
  - Nagybetűk
  - Szimbólumok
  - Számok

Ha nagyobb értékre állítja ezt a beállítást, a felhasználóknak összetettebb jelszavakat kell létrehozniuk. A Windows rendszerű és Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha a jelszó minimális hossza hosszabb nyolc karakternél, vagy ha a karakterkészletek minimális száma meghaladja a kettőt.

- **Jelszó kérése ennyi perc inaktivitás után:** Azt a tétlenségi időt határozza meg, amely eltelte után a felhasználónak újra be kell írnia a jelszavát.
- **Jelszó érvényessége (napokban)**: Válassza ki, hogy hány nap elteltével járjon le a felhasználó jelszava, ami után újat kell létrehoznia.
- **Korábbi jelszavak megjegyzése:** Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban már használt jelszavakat hozzon létre.
- **Korábbi jelszavak újbóli használatának tiltása:** Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.
- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból:** Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt kell használni. A rendszer megkéri a végfelhasználót egy jelszó beírására a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz eléréséhez.

**Ez a beállítás csak Windows 10 Mobile-eszközökre vonatkozik.**

### <a name="encryption"></a>Titkosítás

- **Titkosítás megkövetelése mobileszközön:** Állítsa ezt a beállítást **Igen** értékre, ha szeretné előírni, hogy az eszközök csak titkosítás használata esetén csatlakozhassanak az erőforrásokhoz.



## <a name="device-health-settings"></a>Eszközállapot-beállítások

- **Eszközök kifogástalanként való jelentésének megkövetelése:** Megadhat egy szabályt, amely szerint a **Windows 10 Mobile**-eszközöket kifogástalan állapotúként kell jelenteni az új vagy meglévő megfelelőségi házirendekben. Ha ez a beállítás engedélyezett, a Windows 10-es eszközöket az állapotigazolási szolgáltatás (HAS) értékeli ki a következő adatpontokhoz:
  - **BitLocker engedélyezve:** Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni az eszközön tárolt adatokat a jogosulatlan hozzáféréstől, amikor a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker-meghajtótitkosítás titkosítja a Windows operációs rendszer kötetén tárolt összes adatot. A BitLocker a TPM-mel segít megvédeni a Windows operációs rendszer és a felhasználó adatait és segít biztosítani, hogy a számítógéphez ne férjenek hozzá jogosulatlanul akkor sem, ha felügyelet nélkül hagyják, elveszik vagy ellopják. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM-mel zárolja az adatokat védő titkosítási kulcsokat. Ennek eredményeképpen a kulcsok nem érhetők el, amíg a TPM nem ellenőrizte a számítógép állapotát.
  - **Kódintegritás engedélyezve:** A kódintegritás olyan szolgáltatás, amely ellenőrzi az illesztők vagy rendszerfájlok integritását, amikor azokat betölti a memóriába. A kódintegritás észleli, ha aláíratlan illesztőt vagy rendszerfájlt töltenek be a kernelbe, vagy ha egy rendszerfájlt rendszergazdai jogosultságokkal rendelkező felhasználói fiók által futtatott rosszindulatú szoftver módosított.
  - **Biztonságos rendszerindítás engedélyezve:** Amikor a biztonságos rendszerindítás engedélyezett, az a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül amikor a biztonságos rendszerindítás engedélyezett, a gép rendszerindításához használt fő összetevőknek a megfelelő titkosított aláírásokra van szükségük, amelyekben az eszközt gyártó szervezet megbízik. Az UEFI belső vezérlőprogram ellenőrzi ezt, mielőtt engedélyezi a számítógép elindítását. Ha bármelyik megfigyelt fájlt illetéktelen módosítás ért az aláírás feltörésével, a rendszer nem indul el.

A HAS szolgáltatás működésével kapcsolatos információért lásd: [Állapotigazolási CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Az operációs rendszer szükséges minimális verziója:** Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.
- **Maximálisan engedélyezett operációsrendszer-verzió:** Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai

### <a name="password"></a>Jelszó

- **Jelszó minimális hossza:** – Windows 8.1 rendszeren támogatott.

Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

A Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha **A jelszó minimális hossza** több mint 8 karakter, vagy ha a **Karakterkészletek minimális száma** meghaladja a kettőt.

- **Kötelező jelszótípus:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott

Meghatározza, hogy a felhasználóknak **alfanumerikus** vagy **numerikus** jelszót kell-e létrehozniuk.

- **Karakterkészletek minimális száma:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott. Ha a **Kötelező jelszótípus** **Alfanumerikus**, ez a beállítás határozza meg a jelszóban szereplő karakterkészletek minimális számát. A négy karakterkészlet a következő:
  - Kisbetűk
  - Nagybetűk
  - Szimbólumok
  - Számok: Ha nagyobb értékre állítja ezt a beállítást, a felhasználóknak összetettebb jelszavakat kell létrehozniuk.

A Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha **A jelszó minimális hossza** több mint 8 karakter, vagy ha a **Karakterkészletek minimális száma** meghaladja a kettőt.

- **Jelszó kérése ennyi perc inaktivitás után:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

Azt a tétlenségi időt határozza meg, amely eltelte után a felhasználónak újra be kell írnia a jelszavát.

- **Jelszó érvényessége (napokban):** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

Válassza ki, hogy hány nap elteltével járjon le a felhasználó jelszava, ami után újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

Ha a **Korábbi jelszavak megjegyzése** be van jelölve, adja meg azon korábban használt jelszavak számát, amelyeket nem lehet ismét használni.


## <a name="device-health-settings"></a>Eszközállapot-beállítások

- **Eszközök kifogástalanként való jelentésének megkövetelése:** – Windows 10-es eszközökön támogatott. Megadhat egy szabályt, amely szerint a Windows 10-es eszközöket kifogástalan állapotúként kell jelenteni az új vagy meglévő megfelelőségi házirendekben. Ha ez a beállítás engedélyezett, a Windows 10-es eszközöket az állapotigazolási szolgáltatás (HAS) értékeli ki a következő adatpontokhoz:
  - **BitLocker engedélyezve:** Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni az eszközön tárolt adatokat a jogosulatlan hozzáféréstől, amikor a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker-meghajtótitkosítás titkosítja a Windows operációs rendszer kötetén tárolt összes adatot. A BitLocker a TPM-mel segít megvédeni a Windows operációs rendszer és a felhasználó adatait és segít biztosítani, hogy a számítógéphez ne férjenek hozzá jogosulatlanul akkor sem, ha felügyelet nélkül hagyják, elveszik vagy ellopják. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM-mel zárolja az adatokat védő titkosítási kulcsokat. Ennek eredményeképpen a kulcsok nem érhetők el, amíg a TPM nem ellenőrizte a számítógép állapotát.
  - **Kódintegritás engedélyezve:** A kódintegritás olyan szolgáltatás, amely ellenőrzi az illesztők vagy rendszerfájlok integritását, amikor azokat betölti a memóriába. A kódintegritás észleli, ha aláíratlan illesztőt vagy rendszerfájlt töltenek be a kernelbe, vagy ha egy rendszerfájlt rendszergazdai jogosultságokkal rendelkező felhasználói fiók által futtatott rosszindulatú szoftver módosított.
  - **Biztonságos rendszerindítás engedélyezve:** Amikor a biztonságos rendszerindítás engedélyezett, az a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül amikor a biztonságos rendszerindítás engedélyezett, a gép rendszerindításához használt fő összetevőknek a megfelelő titkosított aláírásokra van szükségük, amelyekben az eszközt gyártó szervezet megbízik. Az UEFI belső vezérlőprogram ellenőrzi ezt, mielőtt engedélyezi a számítógép elindítását. Ha bármelyik megfigyelt fájlt illetéktelen módosítás ért az aláírás feltörésével, a rendszer nem indul el.
  - **Korai indítású kártevőirtó:** A korai indítású kártevőirtó (ELAM) védelmet nyújt a hálózaton lévő számítógépek számára az indításkor és a külső illesztők inicializálása előtt.

A HAS szolgáltatás működésével kapcsolatos információért lásd: [Állapotigazolási CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Eszköztulajdonság-beállítások

- **Az operációs rendszer szükséges minimális verziója:** – Windows 8.1 és Windows 10 rendszeren támogatott.

Az értéket „főverzió.alverzió.build” formában adja meg. A verziószámnak meg kell egyeznie a ```winver``` parancs által visszaadott verzióval.

Ha egy eszköz a megadott verziónál korábbi operációs rendszerrel rendelkezik, azt a rendszer nem megfelelőként fogja jelenteni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Operációs rendszer maximálisan engedélyezett verziója:** – Windows 8.1 és Windows 10 rendszeren támogatott.

Ha egy eszközön a szabályban megadott operációsrendszer-verziótól újabb fut, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

**Az operációs rendszer szükséges minimális verziója** és az **Operációs rendszer maximálisan engedélyezett verziója** beállításhoz használandó verziószám megállapításához futtassa a **winver** parancsot a parancssorból. A winver parancs visszaadja az operációs rendszer jelentett verzióját.+

- Windows 8.1-es számítógépek esetén például a visszaadott verzió a **3**-as. Ha az operációs rendszer verziószabálya Windows 8.1-re van megadva a Windows esetén, az eszköz akkor is nem megfelelőként jelenik meg, ha Windows 8.1 operációs rendszer fut rajta.
- Windows 10-es számítógépeken a verziót a következőképpen kell beállítani: &quot;10.0&quot; + a winver parancs által visszaadott operációs rendszer buildszáma.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
