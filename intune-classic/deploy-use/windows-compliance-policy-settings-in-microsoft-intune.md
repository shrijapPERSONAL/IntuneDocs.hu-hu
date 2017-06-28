---
title: "Megfelelőségi szabályzat beállításai Windows-eszközökhöz"
description: "Ez a témakör a Windows-eszközök megfelelőségi szabályzatában konfigurálható szabályokat és beállításokat ismerteti."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 67810c51c7a7b2ec1e1ff33c11a27a8757b2bcbd
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---

# <a name="compliance-policy-settings-for-windows-devices-in-microsoft-intune"></a>Megfelelőségi szabályzat beállításai Windows-eszközökhöz a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az ebben a témakörben leírt szabályzatbeállítások a Windows operációs rendszerrel működő eszközökre vonatkoznak. A következő szakaszok a támogatott Windows-verziókat ismertetik.

Ha más platformokra vonatkozó információkat keres, válasszon a következők közül:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai iOS-eszközökhöz](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Android-eszközökhöz](android-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai az Android for Workhöz](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="compliance-policy-settings-for-windows-phone-devices"></a>Megfelelőségi szabályzat beállításai Windows Phone-eszközökhöz
A jelen szakaszban felsorolt beállítások támogatottak a Windows Phone 8.1 és újabb verziók.

### <a name="system-security-settings"></a>A rendszer biztonsági beállításai
#### <a name="password"></a>Jelszó
- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget.

- **Egyszerű jelszavak engedélyezése:** Ha engedélyezni szeretné, hogy a felhasználók használhassanak olyan egyszerű jelszavakat, mint az **1234** vagy az **1111**, válassza az **Igen** lehetőséget.

-  **Jelszó minimális hossza**: Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.
- **Megkövetelt jelszótípus:** Meghatározza, hogy a felhasználóknak **alfanumerikus** jelszót vagy **numerikus** jelszót kell-e létrehozniuk.

  A Windows rendszerű és Microsoft-fiókkal elért eszközök esetében a megfelelőségi szabályzat kiértékelése helytelen, ha a jelszó minimális hossza hosszabb nyolc karakternél, vagy ha a karakterkészletek minimális száma meghaladja a kettőt.

- **Karakterkészletek minimális száma:** Ha a **Megkövetelt jelszótípus** **alfanumerikus**, ez a beállítás határozza meg a jelszóban használandó karakterkészletek minimális számát. A négy karakterkészlet a következő:
  -   Kisbetűk
  -   Nagybetűk
  -   Szimbólumok
  -   Számok

  Ha nagyobb értékre állítja ezt a beállítást, a felhasználóknak összetettebb jelszót kell létrehozniuk. A Windows rendszerű és Microsoft-fiókkal elért eszközök esetében a megfelelőségi szabályzat kiértékelése helytelen, ha a jelszó minimális hossza hosszabb nyolc karakternél, vagy ha a karakterkészletek minimális száma meghaladja a kettőt.

- A **Jelszó kérése ennyi perc inaktivitás után:** Ez a beállítás azt adja meg, hogy mennyi ideig tartó tétlenség után kell a felhasználónak újra megadnia a jelszavát.

- **Jelszó érvényessége (napokban)**: Válassza ki, hogy hány nap elteltével járjon le a felhasználó jelszava, ami után újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése:** Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban már használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.
- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**: Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt használhatja. A rendszer megkéri a felhasználót egy jelszó beírására a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz elérésekor.

  > [!NOTE]
  > Ez a beállítás csak Windows 10 Mobile-eszközökre vonatkozik.

#### <a name="encryption"></a>Encryption
- **Titkosítás megkövetelése mobileszközön:** Állítsa ezt a beállítást **Igen** értékre, ha elő szeretné írni, hogy az eszközök csak titkosítás használata esetén csatlakozhassanak az erőforrásokhoz.

### <a name="device-health-settings"></a>Eszközállapot-beállítások
- **Eszközök kifogástalanként való jelentésének megkövetelése:** Megadhat egy szabályt, amely szerint a **Windows 10 Mobile**-eszközöket kifogástalan állapotúként kell jelenteni az új vagy meglévő megfelelőségi szabályzatokban.  Ha ez a beállítás engedélyezve van, a Windows 10-es eszközöket a rendszer az eszközállapot-igazolási szolgáltatással (HAS) értékeli ki a következő szempontok alapján:
  -  **BitLocker engedélyezve:** Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni az eszközön tárolt adatokat a jogosulatlan hozzáféréstől, amikor a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker meghajtótitkosítás a Windows operációs rendszer kötetén tárolt összes adatot titkosítja. A BitLocker a TPM-mel segíti elő a Windows operációs rendszer és a felhasználói adatok védelmét. A BitLocker segít továbbá abban, hogy ne lehessen illetéktelenül hozzáférni a számítógéphez akkor sem, ha az felügyelet nélkül van, elveszett vagy ellopták. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM használatával zárolja az adatok védelmét segítő a titkosítási kulcsokat. Ezért a kulcsok nem érhetők el addig, amíg a TPM nem ellenőrizte a számítógép állapotát.
  -  **Kódintegritás engedélyezve:** A kódintegritás olyan szolgáltatás, amely ellenőrzi az illesztőprogramok és a rendszerfájlok integritását, amikor betölti őket a memóriába. A kódintegritás észleli, ha aláíratlan illesztőprogramot vagy rendszerfájlt töltenek be a kernelbe. Azt is észleli, ha egy rendszerfájlt módosít egy olyan kártevő szoftver, amelyet rendszergazdai jogosultságokkal rendelkező felhasználói fiókkal futtatnak.
  - **Biztonságos rendszerindítás engedélyezve:** Ha a biztonságos rendszerindítás engedélyezve van, a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül a biztonságos rendszerindítás engedélyezése esetén a számítógép elindításához használt alapvető összetevőknek olyan megfelelő titkosítási aláírásokkal kell rendelkezniük, amelyeket az eszközt gyártó szervezet megbízhatónak tekint. Az UEFI belső vezérlőprogram ellenőrzi ezt, mielőtt engedélyezi a számítógép elindítását. Ha bármelyik megfigyelt fájlt illetéktelen módosítás ért az aláírás feltörésével, a rendszer nem indul el.

  > [!IMPORTANT]
  > A Windows-eszközök nem támogatják az eszközállapot-igazolás részeként telepített külső **korai indítású kártevőirtó illesztőprogramokat** (ELAM).

  A HAS szolgáltatás működésével kapcsolatos információért lásd: [Állapotigazolási CSP](https://msdn.microsoft.com/library/dn934876.aspx).
###  <a name="device-property-settings"></a>Eszköztulajdonság-beállítások
- **Az operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni.
    Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie a rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.


## <a name="compliance-policy-settings-for-windows-pcs"></a>Megfelelőségi szabályzat beállításai windowsos számítógépekhez
A jelen szakaszban felsorolt beállítások Windows rendszerű számítógépek támogatottak.
### <a name="system-security-settings"></a>A rendszer biztonsági beállításai
#### <a name="password"></a>Jelszó
- **Jelszó minimális hossza:** Windows 8.1 rendszeren támogatott.

  Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

  A Microsoft-fiókkal elért eszközök esetében a megfelelőségi házirend kiértékelése helytelen, ha **A jelszó minimális hossza** több mint 8 karakter, vagy ha a **Karakterkészletek minimális száma** meghaladja a kettőt.

- **Jelszó kötelező típusa:** Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Meghatározza, hogy a felhasználóknak **alfanumerikus** jelszót vagy **numerikus** jelszót kell-e létrehozniuk.

- **Karakterkészletek minimális száma:** Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Ha a **Jelszó kötelező típusa** **Alfanumerikus**, ez a beállítás határozza meg a jelszóban szereplő karakterkészletek minimális számát. A négy karakterkészlet a következő:
  -   Kisbetűk
  -   Nagybetűk
  -   Szimbólumok
  -   Számok     

  Ha nagyobb értékre állítja ezt a beállítást, a felhasználóknak összetettebb jelszót kell létrehozniuk. A Microsoft-fiókkal elért eszközök esetében a megfelelőségi házirend kiértékelése helytelen, ha **A jelszó minimális hossza** több mint 8 karakter, vagy ha a **Karakterkészletek minimális száma** meghaladja a kettőt.

- **Jelszó kérése ennyi perc inaktivitás után:** Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Azt a tétlenségi időt határozza meg, amelynek eltelte után a felhasználónak újra be kell írnia a jelszavát.

- **Jelszó érvényessége (napokban):** Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Válassza ki, hogy hány nap elteltével jár le a felhasználó jelszava, és ezért a felhasználónak újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése:** Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Ha a **Korábbi jelszavak megjegyzése** be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.

### <a name="device-health-settings"></a>Eszközállapot-beállítások
- **Eszközök kifogástalanként való jelentésének megkövetelése:** Windows 10-es eszközökön támogatott.
Beállíthat olyan szabályt, amely előírja, hogy a Windows 10-eszközöknek kifogástalan állapotban kell szerepelniük az új vagy meglévő megfelelőségi szabályzatokban. Ha ez a beállítás engedélyezve van, a Windows 10-es eszközöket a rendszer az eszközállapot-igazolási szolgáltatással (HAS) értékeli ki a következő szempontok alapján:
  -  **BitLocker engedélyezve:** Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni az eszközön tárolt adatokat a jogosulatlan hozzáféréstől, amikor a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker meghajtótitkosítás a Windows operációs rendszer kötetén tárolt összes adatot titkosítja. A BitLocker a TPM-mel segíti elő a Windows operációs rendszer és a felhasználói adatok védelmét. A BitLocker segít továbbá abban, hogy ne lehessen illetéktelenül hozzáférni a számítógéphez akkor sem, ha az felügyelet nélkül van, elveszett vagy ellopták. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM használatával zárolja az adatok védelmét segítő a titkosítási kulcsokat. Ezért a kulcsok nem érhetők el addig, amíg a TPM nem ellenőrizte a számítógép állapotát.
  -  **Kódintegritás engedélyezve:** A kódintegritás olyan szolgáltatás, amely ellenőrzi az illesztőprogramok és a rendszerfájlok integritását, amikor betölti őket a memóriába. A kódintegritás észleli, ha aláíratlan illesztőprogramot vagy rendszerfájlt töltenek be a kernelbe. Azt is észleli, ha egy rendszerfájlt módosít egy olyan kártevő szoftver, amelyet rendszergazdai jogosultságokkal rendelkező felhasználói fiókkal futtatnak.
  - **Biztonságos rendszerindítás engedélyezve:** Ha a biztonságos rendszerindítás engedélyezve van, a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül a biztonságos rendszerindítás engedélyezése esetén a számítógép elindításához használt alapvető összetevőknek olyan megfelelő titkosítási aláírásokkal kell rendelkezniük, amelyeket az eszközt gyártó szervezet megbízhatónak tekint. Az UEFI belső vezérlőprogram ellenőrzi ezt, mielőtt engedélyezi a számítógép elindítását. Ha azt észleli, hogy valamelyik fájl módosult, és érvénytelenné vált az aláírása, akkor a rendszer nem indul el.
  - **Korai indítású kártevőirtó:** A korai indítású kártevőirtó (ELAM) védelmet nyújt a hálózaton lévő számítógépek számára az indításkor és a külső illesztőprogramok inicializálása előtt.

  A HAS szolgáltatás működésével kapcsolatos információért lásd: [Állapotigazolási CSP](https://msdn.microsoft.com/library/dn934876.aspx).

### <a name="device-property-settings"></a>Eszköztulajdonság-beállítások
- **Az operációs rendszer szükséges minimális verziója:** Windows 8.1 és Windows 10 rendszeren támogatott.

  Az értéket „főverzió.alverzió.build” formában adja meg. A verziószámnak meg kell egyeznie a **winver** parancs által visszaadott verzióval.

  Ha egy eszköznek a megadott verziónál korábbi az operációs rendszere, azt a rendszer nem megfelelőként fogja jelenteni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Operációs rendszer maximálisan engedélyezett verziója:** Windows 8.1 és Windows 10 rendszeren támogatott.

  Ha egy eszközön a szabályban megadott operációsrendszer-verziótól újabb fut, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

**Az operációs rendszer szükséges minimális verziója** és az **Operációs rendszer maximálisan engedélyezett verziója** beállításhoz használandó verziószám megállapításához futtassa a **winver** parancsot a parancssorból. A **winver** parancs visszaadja az operációs rendszer jelentett verzióját.

- Windows 8.1-es számítógépek esetén például a visszaadott verzió a **6.3**-as. Ha az operációs rendszer verziószabálya Windows 8.1-re van megadva a Windows esetén, az eszköz akkor is nem megfelelőként jelenik meg, ha Windows 8.1 operációs rendszer fut rajta.

- Windows 10-es számítógépeken a verziót a következőképpen kell beállítani: **10.0** + az operációs rendszernek a **winver** parancs által visszaadott buildszáma. Például: 10.0.10586.
> ![Az operációs verzió buildszáma kiemelve „A Windows névjegye” párbeszédpanelen](./media/ca_win10-os-version.png)

