---
# required metadata

title: Megfelelőségi szabályzat beállításai iOS-eszközökhöz | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Megfelelőségi szabályzat beállításai iOS-eszközökhöz a Microsoft Intune-ban

A jelen témakörben leírt szabályzati beállítások  iOS 6 vagy újabb verziójú futó eszközökre vonatkoznak.

Ha más platformokra vonatkozó információkat keres, válassza az alábbiak egyikét:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai Android-eszközökhöz](android-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Windows-eszközökhöz](windows-compliance-policy-settings-in-microsoft-intune.md)

## A rendszer biztonsági beállításai
### Jelszó
- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához:** ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen**
  lehetőséget. A jelszót használó iOS-eszközöket titkosítja a rendszer.

- **Egyszerű jelszavak engedélyezése:** állítsa
   **Igen** értékre ezt a beállítást, ha engedélyezni szeretné, hogy a felhasználók
   egyszerű jelszavakat (például **1234** vagy **1111**) hozzanak létre.

-  **Jelszó minimális hossza:**
  meghatározza a felhasználók jelszavában szereplő
  számjegyek vagy karakterek minimális számát.
- **Kötelező jelszótípus:** meghatározza, hogy a felhasználók kötelesek-e
**Alfanumerikus** vagy **Numerikus** jelszót beállítani.

- **Karakterkészletek minimális száma:** Ha a **Kötelező jelszótípus** beállítást
**Alfanumerikus** értékre állítja, ezzel a beállítással határozhatja meg, hogy legalább
hány karakterkészletet kell tartalmaznia a jelszónak. A négy karakterkészlet a következő:
  -   Kisbetűk
  -   Nagybetűk
  -   Szimbólumok
  -   Számok

  Ha nagyobb értékre állítja ezt a beállítást, a felhasználóknak összetettebb jelszavakat kell létrehozniuk.

  Az iOS-eszközök esetében ez a beállítás a jelszóban szereplő speciális karakterek (például: **!**, **#**, **&amp;**) minimális számára utal.
- **Jelszó kérése ennyi perc inaktivitás után**: arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban):** adja meg, hogy a felhasználó jelszava hány nap elteltével járjon le.
A megadott időtartam elteltével a felhasználónak új jelszót kell létrehoznia.

- **Korábbi jelszavak tárolása:** ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással együtt használva korlátozhatja,
hogy a felhasználó korábban már használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** ha bekapcsolta a **Korábbi jelszavak tárolása** funkciót, adja meg
hány jelszóra visszamenőleg nem használható egy már korábban használt jelszó.

- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból:**
Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt kell használni. A rendszer megkéri a végfelhasználót a jelszó megadására, amennyiben a kérdéses eszköz a
**Jelszó kérése ennyi perc inaktivitás után** beállításban megadott időtartamon át inaktív volt.

### E-mail profil
- **Csak az Intune által felügyelt e-mail fiók használható:** ha **Igen** értékre állítja a beállítást, az eszköznek az eszközre telepített megfelelő e-mail-fiókot kell használnia. Az eszköz a következő esetekben számít nem megfelelőnek:
  - Az e-mail-profilt ugyanarra a felhasználói csoportra kell telepíteni, amelyet a megfelelőségi szabályzat is céloz, ellenkező esetben a felhasználó eszköze nem megfelelőnek fog számítani.
  - Ha a felhasználó olyan e-mail-fiókot állított be az eszközön, amely egyezik az eszközre telepített Intune-e-mail-fiókkal, a rendszer nem megfelelőként jelenti az eszközt. Az Intune nem írhatja felül a felhasználó által kiépített profilt, így
  nem is képes annak kezelésére. A megfelelőség biztosítása érdekében a felhasználónak törölnie kell
  a meglévő e-mail-beállításokat. Ezt követően az Intune képes lesz
  az e-mail-profil kezelésére.


- **Az Intune-ban felügyelni kívánt e-mail-profil kiválasztása:**
     Ha bekapcsolta a **Csak az Intune által felügyelt e-mail fiók használható** beállítást,
     az Intune e-mail-profil megadásához válassza a **Kiválasztás** lehetőséget. A levelezési profilnak megtalálhatónak kell lennie az eszközön.

     Az e-mail-profilokkal kapcsolatos további információért lásd: [Vállalati levelezéshez
     való hozzáférés engedélyezése a Microsoft Intune e-mail profiljaival](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## Eszközállapot-beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz:** ha bekapcsolja ezt a beállítást,
a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.

##  Eszköztulajdonságok
- **Minimum OS required** (Az operációs rendszer szükséges minimális verziója): ha egy eszköz nem teljesíti a minimális operációsrendszer-verzióra
vonatkozó követelményeket, a rendszer nem megfelelőként fogja értékelni.
Megjelenik egy, a verziófrissítésre vonatkozó információkra mutató hivatkozás. A végfelhasználó frissítheti az eszközt, ezt követően pedig hozzáférhet a vállalati erőforrásokhoz.

- **Maximum OS version allowed:** (Maximálisan engedélyezett operációsrendszer-verzió) ha a rendszer az itt meghatározottnál
újabb operációsrendszer-verziót használ, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie a rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.


<!--HONumber=May16_HO1-->


