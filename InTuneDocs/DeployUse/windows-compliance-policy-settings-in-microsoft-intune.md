---
# required metadata

title: Megfelelőségi szabályzat beállításai Windows-eszközökhöz | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Megfelelőségi szabályzat beállításai Windows-eszközökhöz a Microsoft Intune-ban

A jelen témakörben leírt házirend-beállítások a Windows operációs rendszerrel működő eszközökre vonatkoznak. A támogatott Windows-verziót feltüntettük az alábbi szakaszokban.

Ha más platformokra vonatkozó információkat keres, válasszon az alábbi lehetőségek közül:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai iOS-eszközökhöz](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Android-eszközökhöz](android-compliance-policy-settings-in-microsoft-intune.md)

## Megfelelőségi szabályzat beállításai Windows Phone-eszközökhöz
A jelen szakaszban felsorolt beállítások támogatottak a Windows Phone 8.1 és újabb verziók.

## A rendszer biztonsági beállításai
### Jelszó
- **A mobileszközök zárolásának feloldásához jelszó szükséges:** Ha szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassz az **Igen**
  lehetőséget.

- **Egyszerű jelszavak engedélyezése:** Állítsa
   **Igen** értékre ezt a beállítást, ha szeretné engedélyezni, hogy a felhasználók egyszerű jelszavakat hozhassanak létre
   (például **1234** vagy **1111**).

-  **Jelszó minimális hossza:**
  meghatározza a felhasználók jelszavában szereplő
  számjegyek vagy karakterek minimális számát.
- **Kötelező jelszótípus:** meghatározza, hogy a felhasználók kötelesek-e
**Alfanumerikus** vagy **Numerikus** jelszót beállítani.

  A Windows rendszerű és Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha a jelszó minimális hossza hosszabb nyolc karakternél, vagy ha a karakterkészletek minimális száma meghaladja a kettőt.

- **Karakterkészletek minimális száma:** Ha a **Kötelező jelszótípus** beállítást
**Alfanumerikus** értékre állítja, akkor ez a beállítás határozza meg, hogy legalább
hány karakterkészletet kell tartalmaznia a jelszónak. A négy karakterkészlet a következő:
  -   Kisbetűk
  -   Nagybetűk
  -   Szimbólumok
  -   Számok

  Ha nagyobb értékre állítja ezt a beállítást, a felhasználóknak összetettebb jelszavakat kell létrehozniuk. A Windows rendszerű és Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha a jelszó minimális hossza hosszabb nyolc karakternél, vagy ha a karakterkészletek minimális száma meghaladja a kettőt.
- **Jelszó kérése ennyi perc inaktivitás után:** arra a tétlenségi időre vonatkozik, amin belül a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban):** Adja meg, hogy a felhasználó jelszava hány nap elteltével járjon le.
  A megadott időtartam elteltével a felhasználónak új jelszót kell létrehoznia.

- **Korábbi jelszavak tárolása:** ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással együtt használva korlátozhatja,
  hogy a felhasználó korábban már használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** ha bekapcsolta a **Korábbi jelszavak tárolása** funkciót, adja meg
  a korábban már használt, újból nem használható jelszavak számát.
- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból:** Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt kell használni. A rendszer megkéri a végfelhasználót egy jelszó beírására a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz eléréséhez.

  **Ez a beállítás csak Windows 10 Mobile-eszközökre vonatkozik.**
### Titkosítás
- **Titkosítás megkövetelése mobileszközön:** állítsa **Igen** értékre ezt a beállítást, ha szeretné előírni, hogy az
  eszközök csak titkosítás használata esetén csatlakozhassanak az erőforrásokhoz.

## Eszközállapot-beállítások
- **Eszközök kifogástalanként való jelentésének megkövetelése:** Megadhat egy szabályt, amely szerint a **Windows 10 Mobile**-eszközöket kifogástalan állapotúként kell jelenteni az új vagy meglévő megfelelőségi házirendekben.  Ha ez a beállítás engedélyezett, a Windows 10-es eszközöket a rendszer az eszközállapot-igazolási szolgáltatáson (HAS) keresztül értékeli ki a következő adatpontokhoz:
  -  **BitLocker engedélyezve:** Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni az eszközön tárolt adatokat a jogosulatlan hozzáféréstől, amikor a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker-meghajtótitkosítás titkosítja a Windows operációs rendszer kötetén tárolt összes adatot. A BitLocker a TPM-mel segít megvédeni a Windows operációs rendszer és a felhasználó adatait és segít biztosítani, hogy a számítógéphez ne férjenek hozzá jogosulatlanul akkor sem, ha felügyelet nélkül hagyják, elveszik vagy ellopják. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM-mel zárolja az adatokat védő titkosítási kulcsokat. Ennek eredményeképpen a kulcsok nem érhetők el, amíg a TPM nem ellenőrizte a számítógép állapotát.
  -  **Kódintegritás engedélyezve:** A kódintegritás olyan szolgáltatás, amely ellenőrzi az illesztők vagy rendszerfájlok integritását, amikor azokat betölti a memóriába. A kódintegritás észleli, ha aláíratlan illesztőt vagy rendszerfájlt töltenek be a kernelbe, vagy ha egy rendszerfájlt rendszergazdai jogosultságokkal rendelkező felhasználói fiók által futtatott rosszindulatú szoftver módosított.
  - **Biztonságos rendszerindítás engedélyezve:** Amikor a biztonságos rendszerindítás engedélyezett, az a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül amikor a biztonságos rendszerindítás engedélyezett, a gép rendszerindításához használt fő összetevőknek a megfelelő titkosított aláírásokra van szükségük, amelyekben az eszközt gyártó szervezet megbízik. Az UEFI belső vezérlőprogram ezt a gép elindításának engedélyezése előtt ellenőrzi. Ha bármelyik megfigyelt fájlt illetéktelen módosítás ért az aláírás feltörésével, a rendszer nem indul el.

  A HAS szolgáltatás működésével kapcsolatos információért lásd: [Állapotigazolási CSP](https://msdn.microsoft.com/library/dn934876.aspx)..
##  Eszköztulajdonság-beállítások
- **Az operációs rendszer szükséges minimális verziója:** ha egy eszköz nem teljesíti a minimális operációsrendszer-verzióra
    vonatkozó követelményeket, a rendszer nem megfelelőként fogja értékelni.
    Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Maximálisan engedélyezett operációsrendszer-verzió:** ha egy eszközön
    a szabályban megadottnál újabb operációs rendszer fut, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.


## Megfelelőségi szabályzat beállításai windowsos számítógépekhez
A jelen szakaszban felsorolt beállítások Windows rendszerű számítógépek támogatottak.
## A rendszer biztonsági beállításai
### Jelszó
- **Jelszó minimális hossza:** – Windows 8.1 rendszeren támogatott.

  Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

  A Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha **A jelszó minimális hossza** több mint 8 karakter, vagy ha a **Karakterkészletek minimális száma** meghaladja a kettőt.

- **Kötelező jelszótípus:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Meghatározza, hogy a felhasználóknak **alfanumerikus** vagy **numerikus** jelszót kell-e létrehozniuk.

- **Karakterkészletek minimális száma:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott. Ha a **Jelszó kötelező** típusa **Alfanumerikus**, ez a beállítás határozza meg a jelszóban szereplő karakterkészletek minimális számát. A négy karakterkészlet a következő:
  -   Kisbetűk
  -   Nagybetűk
  -   Szimbólumok
  -   Számok:     Ha nagyobb értékre állítja ezt a beállítást, a felhasználóknak összetettebb jelszavakat kell létrehozniuk.

  A Microsoft-fiókkal elért eszközök esetén a megfelelőségi házirend kiértékelése helytelen, ha **A jelszó minimális hossza** több mint 8 karakter, vagy ha a **Karakterkészletek minimális száma** meghaladja a kettőt.
- **Jelszó kérése ennyi perc inaktivitás után:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Azt a tétlenségi időt határozza meg, amely eltelte után a felhasználónak újra be kell írnia a jelszavát.

- **Jelszó érvényessége (napokban):** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Válassza ki azon napok számát, amelyek eltelte után a felhasználó jelszava lejár, és újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban használt jelszavakat hozzon létre.
- **Korábbi jelszavak újbóli használatának tiltása:** – Windows RT, Windows RT 8.1 és Windows 8.1 rendszeren támogatott.

  Ha a **Korábbi jelszavak megjegyzése** be van jelölve, adja meg azon korábban használt jelszavak számát, amelyeket nem lehet ismét használni.

## Eszközállapot-beállítások
- **Eszközök kifogástalanként való jelentésének megkövetelése:** – Windows 10-es eszközökön támogatott.
Megadhat egy szabályt, amely szerint a Windows 10-es eszközöket kifogástalan állapotúként kell jelenteni az új vagy meglévő megfelelőségi házirendekben.  Ha ez a beállítás engedélyezett, a Windows 10-es eszközöket a rendszer az eszközállapot-igazolási szolgáltatáson (HAS) keresztül értékeli ki a következő adatpontokhoz:
  -  **BitLocker engedélyezve:** Ha a BitLocker be van kapcsolva, az eszköz meg tudja védeni az eszközön tárolt adatokat a jogosulatlan hozzáféréstől, amikor a rendszer ki van kapcsolva vagy hibernálva van. A Windows BitLocker-meghajtótitkosítás titkosítja a Windows operációs rendszer kötetén tárolt összes adatot. A BitLocker a TPM-mel segít megvédeni a Windows operációs rendszer és a felhasználó adatait és segít biztosítani, hogy a számítógéphez ne férjenek hozzá jogosulatlanul akkor sem, ha felügyelet nélkül hagyják, elveszik vagy ellopják. Ha a számítógépen kompatibilis TPM található, a BitLocker a TPM-mel zárolja az adatokat védő titkosítási kulcsokat. Ennek eredményeképpen a kulcsok nem érhetők el, amíg a TPM nem ellenőrizte a számítógép állapotát.
  -  **Kódintegritás engedélyezve:** A kódintegritás olyan szolgáltatás, amely ellenőrzi az illesztők vagy rendszerfájlok integritását, amikor azokat betölti a memóriába. A kódintegritás észleli, ha aláíratlan illesztőt vagy rendszerfájlt töltenek be a kernelbe, vagy ha egy rendszerfájlt rendszergazdai jogosultságokkal rendelkező felhasználói fiók által futtatott rosszindulatú szoftver módosított.
  - **Biztonságos rendszerindítás engedélyezve:** Amikor a biztonságos rendszerindítás engedélyezett, az a rendszert gyárilag megbízható állapotban végzett rendszerindításra kényszeríti. Ezenkívül amikor a biztonságos rendszerindítás engedélyezett, a gép rendszerindításához használt fő összetevőknek a megfelelő titkosított aláírásokra van szükségük, amelyekben az eszközt gyártó szervezet megbízik. Az UEFI belső vezérlőprogram ezt a gép elindításának engedélyezése előtt ellenőrzi. Ha bármelyik megfigyelt fájlt illetéktelen módosítás ért az aláírás feltörésével, a rendszer nem indul el.
  - **Korai indítású kártevőirtó:** A korai indítású kártevőirtó (ELAM) védelmet nyújt a hálózaton lévő számítógépek számára az indításkor és a külső illesztők inicializálása előtt.

  A HAS szolgáltatás működésével kapcsolatos információért lásd: [Állapotigazolási CSP](https://msdn.microsoft.com/library/dn934876.aspx)..

## Eszköztulajdonság-beállítások
- **Az operációs rendszer szükséges minimális verziója:** – Windows 8.1 és Windows 10 rendszeren támogatott.

  Az értéket „főverzió.alverzió.build” formában adja meg. A verziószámnak meg kell egyeznie a winver parancs által visszaadott verzióval.

  Ha egy eszköz a megadott verziónál korábbi operációs rendszerrel rendelkezik, azt a rendszer nem megfelelőként fogja jelenteni. Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A végfelhasználó frissítheti az eszközt, és utána hozzáférhet a vállalati erőforrásokhoz.

- **Operációs rendszer maximálisan engedélyezett verziója:** – Windows 8.1 és Windows 10 rendszeren támogatott.

  Ha egy eszközön a szabályban megadott operációsrendszer-verziótól újabb fut, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie az informatikai rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.

**Az operációs rendszer szükséges minimális verziója** és az **Operációs rendszer maximálisan engedélyezett verziója** beállításokhoz használandó verziószám megállapításához futtassa a **winver** parancsot a parancssorból. A winver parancs visszaadja az operációs rendszer jelentett verzióját.
- Windows 8.1-es számítógépek esetén például a visszaadott verzió a **6.3**-as.    Ha az operációs rendszer verziószabálya Windows 8.1-re van megadva a Windows esetén, az eszköz akkor is nem megfelelőként jelenik meg, ha Windows 8.1 operációs rendszer fut rajta.
- Windows 10-es számítógépeken a verziót a következőképpen kell beállítani: „10.0” + a winver parancs által visszaadott operációs rendszer buildszáma. Például: 10.0.10586.
> ![CA_Win10OSVersion](./media/ca_win10-os-version.png)


<!--HONumber=May16_HO1-->


