---
title: Megfelelőségi szabályzat beállításai iOS-es eszközökhöz
description: Ez a témakör azokat a szabályokat és beállításokat ismerteti, amelyeket az iOS-eszközök megfelelőségi szabályzatában adhat meg.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7973dd757c69bc0a63f1ff5d24973acb6086d8a4
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2018
---
# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a>Megfelelőségi szabályzat beállításai iOS-eszközökhöz a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Az ebben a témakörben leírt szabályzatbeállítások az iOS 8.0 vagy újabb verziójú operációs rendszert futtató eszközökre vonatkoznak.

Ha más platformokra vonatkozó információkat keres, válassza az alábbiak egyikét:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai Android-eszközökhöz](android-compliance-policy-settings-in-microsoft-intune.md)
- [Az Android for Work megfelelőségi szabályzatainak beállításai](afw-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Windows-eszközökhöz](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>A rendszer biztonsági beállításai
### <a name="password"></a>Jelszó
- **Jelszó megkövetelése a mobileszköz-zárolás feloldásához**: Ha azt szeretné, hogy a felhasználók kötelesek legyenek jelszót megadni az eszköz eléréséhez, válassza az **Igen** lehetőséget. A jelszót használó iOS-eszközöket titkosítja a rendszer.

- **Egyszerű jelszavak engedélyezése:** Ha engedélyezni szeretné, hogy a felhasználók használhassanak olyan egyszerű jelszavakat, mint az **1234** vagy az **1111**, válassza az **Igen** lehetőséget.

-  **Jelszó minimális hossza**: Meghatározza a felhasználók jelszavában szereplő számjegyek vagy karakterek minimális számát.

- **Megkövetelt jelszótípus:** Meghatározza, hogy a felhasználóknak **alfanumerikus** jelszót vagy **numerikus** jelszót kell-e létrehozniuk.

- **Karakterkészletek minimális száma:** Ha a **Megkövetelt jelszótípus** **Alfanumerikus**, ez a beállítás határozza meg a jelszóban használandó karakterkészletek minimális számát. A négy karakterkészlet a következő:
  -   Kisbetűk
  -   Nagybetűk
  -   Szimbólumok
  -   Számok

  Ha nagyobb értékre állítja, a felhasználóknak összetettebb jelszót kell létrehozniuk.

  Az iOS-eszközök esetében ez a beállítás a jelszóban használandó különleges karakterek (például: **!**, **#**, **&amp;**) minimális számára utal.

- **Jelszó kérése ennyi perc inaktivitás után**: Arra a tétlenségi időre vonatkozik, amelynek elteltével a felhasználónak újra meg kell adnia a jelszavát.

- **Jelszó érvényessége (napokban)**: Válassza ki, hány nap elteltével járjon le a felhasználó jelszava, ami után újat kell létrehoznia.

- **Korábbi jelszavak megjegyzése:** Ezt a beállítást a **Korábbi jelszavak újbóli használatának tiltása** beállítással használva korlátozhatja, hogy a felhasználó korábban már használt jelszavakat hozzon létre.

- **Korábbi jelszavak újbóli használatának tiltása**: Ha a **Korábbi jelszavak megjegyzése** beállítás be van jelölve, adja meg, hogy az utolsó hány korábbi jelszót ne lehessen ismét használni.

- **Jelszó kérése, amikor az eszköz visszatér inaktív állapotból**: Ezt a beállítást a **Jelszó kérése ennyi perc inaktivitás után** beállítással együtt használhatja. A rendszer megkéri a felhasználót egy jelszó beírására a **Jelszó kérése ennyi perc inaktivitás után** beállításban megadott ideig inaktív eszköz elérésekor.

### <a name="email-profile"></a>E-mail-profil
- **Csak az Intune által felügyelt e-mail fiók használható:** Ha **Igen** értékre állítja a beállítást, az eszköznek az eszközre telepített e-mail-fiókot kell használnia. Az eszköz a következő esetekben számít nem megfelelőnek:
  - Az e-mail-profil nem a megfelelőségi szabályzat által célzott felhasználócsoporttól különböző felhasználócsoportnál van telepítve.
  - A felhasználó már beállított egy, az eszközre telepített Intune levelezési profillal egyező e-mail-fiókot az eszközön. Az Intune nem írhatja felül a felhasználó által létesített profilt, így nem kezelheti. A megfelelőség biztosítása érdekében a felhasználónak törölnie kell a meglévő e-mail-beállításokat. Ezt követően az Intune képes lesz a felügyelt e-mail-profil telepítésére.

- **Az Intune-ban felügyelni kívánt levelezési profil:** Ha a **Csak az Intune által felügyelt e-mail fiók használható** beállítás be van jelölve, kattintson a **Kiválasztás** elemre az Intune levelezési profil kiválasztásához. A levelezési profilnak megtalálhatónak kell lennie az eszközön.

     A levelezési profilokról a [Vállalati levelezéshez való hozzáférés konfigurálása e-mail-profilokkal a Microsoft Intune-ban](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) című témakörben talál további információt.

## <a name="device-health-settings"></a>Eszközállapot-beállítások

- **Az eszköz nem lehet függetlenített vagy feltört eszköz:** Ha bekapcsolja ezt a beállítást, a rendszer nem megfelelőként fogja értékelni a feltört eszközöket.

##  <a name="device-properties"></a>Eszköztulajdonságok
- **Az operációs rendszer szükséges minimális verziója**: Ha egy eszköz nem teljesíti az operációs rendszer szükséges minimális verziójára vonatkozó követelményt, nem megfelelőként fog szerepelni.
Megjelenik egy hivatkozás, amelyen a verziófrissítésre vonatkozó információk érhetők el. A felhasználó választhatja az eszköz frissítését. Azt követően hozzáférhet a vállalati erőforrásokhoz.

- **Maximálisan engedélyezett operációsrendszer-verzió**: Ha egy eszközön a szabályban megadott operációsrendszer-verziónál újabb fut, a vállalati erőforrásokhoz való hozzáférés le lesz tiltva, és a felhasználónak kapcsolatba kell lépnie a rendszergazdával. Az eszköz csak akkor használható a vállalati erőforrások eléréséhez, ha a szabályt úgy módosítják, hogy engedélyezze az operációs rendszer verzióját.
