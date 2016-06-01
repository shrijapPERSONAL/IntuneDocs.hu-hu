---
# required metadata

title: Megfelelőségi szabályzat beállításai Android-eszközökhöz | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Megfelelőségi szabályzat beállításai Android-eszközökhöz a Microsoft Intune-ban

A jelen témakörben leírt szabályzati beállítások az Android 4.0-s és újabb verzióival, illetve a Samsung KNOX 4.0-s és újabb verzióival futó eszközökre vonatkoznak.

Ha más platformokra vonatkozó információkat keres, válassza az alábbiak egyikét:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai iOS-eszközökhöz](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Windows-eszközökhöz](windows-compliance-policy-settings-in-microsoft-intune.md)

## A rendszer biztonsági beállításai
### Jelszó
- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához:** ha szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen**
  lehetőséget.

-  **Jelszó minimális hossza:** meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

- **Jelszó erőssége:** a beállítás bekapcsolása esetén konfigurálhatja az Android-eszközök jelszókövetelményeit. A következő lehetőségek közül választhat:
  -   **Alacsony biztonságú biometrikus**
  - **Kötelező**
  -   **Legalább számok**
  -   **Legalább betűk**
  -   **Legalább alfanumerikus karakterek**
  -   **Alfanumerikus karakterek és szimbólumok**

- **Jelszó kérése ennyi perc inaktivitás után**: arra a tétlenségi időre vonatkozik, amelyen belül a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban):** adja meg, hogy a felhasználó jelszava hány nap elteltével járjon le.
  A megadott időtartam elteltével a felhasználónak új jelszót kell létrehoznia.

- **Korábbi jelszavak tárolása:** ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással együtt használva korlátozhatja,
  hogy a felhasználó korábban már használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása:** ha bekapcsolta a **Korábbi jelszavak tárolása** funkciót, adja meg,
  hány jelszóra visszamenőleg nem használható egy már korábban használt jelszó.

- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból:**
  Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt kell használni. A rendszer megkéri a végfelhasználót a jelszó megadására, amennyiben a kérdéses eszköz a
  **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott időtartamon át inaktív volt.

### Titkosítás
- **Titkosítás megkövetelése mobileszközökön:** állítsa **Igen** értékre ezt a beállítást, ha szeretné megkövetelni, hogy az
  eszközök csak titkosítás használata esetén csatlakozhassanak az erőforrásokhoz. A rendszer titkosítja az eszközöket,
  amennyiben a felhasználó elvégzi a **Jelszó megkövetelése
  a mobileszköz-zárolás feloldásához** beállítás konfigurálását.

## Eszközállapot-beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz:** ha bekapcsolja ezt a beállítást,
  a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.

## Eszköztulajdonság-beállítások
- **Az operációs rendszer szükséges minimális verziója:** ha egy eszköz nem teljesíti a minimális operációsrendszer-verzióra
  vonatkozó követelményeket, a rendszer nem megfelelőnek fogja minősíteni.
  Megjelenik egy, a verziófrissítésre vonatkozó információkra mutató hivatkozás. A végfelhasználó frissítheti az eszközt, ezt követően pedig hozzáférhet a vállalati erőforrásokhoz.

- **Maximum OS version allowed** (Maximálisan engedélyezett operációsrendszer-verzió): ha a rendszer az itt meghatározottnál
  újabb operációsrendszer-verziót használ, a vállalati erőforrásokhoz való hozzáférés le van tiltva, és a felhasználónak kapcsolatba kell lépnie a rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.


<!--HONumber=May16_HO1-->


