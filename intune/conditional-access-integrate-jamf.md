---
title: A Jamf Pro integrálása a Microsoft Intune-nal a megfelelőség érdekében
titlesuffix: ''
description: A Microsoft Intune megfelelőségi szabályzatait az Azure Active Directory feltételes hozzáférésével használva biztonságossá teheti a Jamf által kezelt eszközöket.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 01/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cdeb3a21af2b4cf020d3e5029eeb5b0bc31db062
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>A Jamf Pro integrálása az Intune-nal a megfelelőség érdekében

|A következőkre vonatkozik: Intune az Azure Portalon |
|--|
|A klasszikus portálbeli Intune-ról keres dokumentációt? [Lépjen tovább ide](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

Ha a szervezet a [Jamf Pro](https://www.jamf.com) segítségével felügyeli a végfelhasználók Mac-alapú számítógépeit, lehetősége van a Microsoft Intune megfelelőségi szabályzataival és az Azure Active Directory-alapú feltételes hozzáféréssel biztosítani az eszközmegfelelőséget a szervezetben.

## <a name="prerequisites"></a>Előfeltételek

A Jamf Pro használatával történő feltételes hozzáférés konfigurálásához a következőkre van szüksége:

- A Jamf Pro 10.1.0-ás vagy későbbi verziója
- [macOS-hez készült Céges portál alkalmazás](https://aka.ms/macoscompanyportal)
- OS X 10.11-es vagy későbbi Yosemite verzióval rendelkező macOS-alapú eszközök

## <a name="connecting-intune-to-jamf-pro"></a>Az Intune csatlakoztatása a Jamf Pro-hoz

Az Intune és a Jamf Pro csatlakoztatásához a következők szükségesek:

1. Új alkalmazás létrehozása az Azure-ban
2. Az Intune engedélyezése a Jamf Pro-val történő integrációra
3. Feltételes hozzáférés konfigurálása a Jamf Pro szolgáltatásban

## <a name="create-a-new-application-in-azure-active-directory"></a>Új alkalmazás létrehozása az Azure Active Directoryban

1. Nyissa meg az **Azure Active Directory** > **Alkalmazásregisztrációk** lapot.
2. Kattintson az **+Új alkalmazás létrehozása** elemre.
3. Adjon meg egy **megjelenítendő nevet**, például **Jamf feltételes hozzáférés**.
4. Kattintson a **Webalkalmazás / API** elemre.
5. Adja meg a **Bejelentkezési URL-címet** a Jamf Pro-példány URL-címe alapján.
6. Kattintson az **Alkalmazás létrehozása** lehetőségre.
7. Mentse az újonnan létrehozott **Alkalmazásazonosítót**, majd válassza a **Beállítások** lehetőséget, és navigáljon az **API-hozzáférés** > **Kulcsok** lapra az új alkalmazáskulcs létrehozásához. Adja meg a kívánt leírást a **Leírás** oszlopban, adja meg a lejárat időtartamát a **Lejárat** oszlopban, majd mentse az alkalmazáskulcsot.

   > [!IMPORTANT]
   > Az alkalmazáskulcs csak egyszer jelenik meg a folyamat során. Mindenképpen olyan helyre mentse, ahol később könnyen hozzáférhet.

8. Nyissa meg a **Beállítások** lapot, navigáljon az **API-hozzáférés** > **Szükséges engedélyek** lapra, és törölje az összes engedélyt.

   > [!NOTE]
   > Adjon hozzá egy új szükséges engedélyt. Az alkalmazás csak akkor működik megfelelően, ha egyetlen szükséges engedéllyel rendelkezik.

9. Válassza ki a **Microsoft Intune API** lehetőséget, majd kattintson a **Kiválaszt** elemre.
10. Válassza ki a **Eszközattribútumok küldése a Microsoft Intune-ba** lehetőséget, majd kattintson a **Kiválaszt** elemre.
11. Miután mentette az alkalmazáshoz szükséges engedélyeket, kattintson az **Engedélyek megadása** gombra.

    > [!NOTE]
    > Az alkalmazáskulcs lejártakor új alkalmazáskulcsot kell létrehoznia a Microsoft Azure-ban, majd frissítenie kell a feltételes hozzáférési adatokat a Jamf Pro-ban. A szolgáltatás megszakításmentes végrehajtása érdekében az Azure lehetővé teszi, hogy a régi és az új kulcs egyidejűleg aktív legyen.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Az Intune engedélyezése a Jamf Pro-val történő integrációra

1. A Microsoft Azure Portalon nyissa meg a **Microsoft Intune** > **Eszköz megfelelősége** > **Partnereszköz kezelése** lapot.
2. Illessze be az alkalmazásazonosítót a **Jamf Azure Active Directory alkalmazásazonosító** mezőbe, és ezzel engedélyezze a megfelelőségi összekötőt.
3. Kattintson a **Mentés**gombra.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>A Microsoft Intune-integráció konfigurálása a Jamf Pro szolgáltatásban

1. A Jamf Pro oldalán nyissa meg a **Globális felügyelet** > **Feltételes hozzáférés** lehetőséget. Kattintson a **Microsoft Intune-integráció** lapon található **Szerkesztés** gombra.
2. Jelölje be a **Microsoft Intune-integráció engedélyezése** jelölőnégyzetet.
3. Adja meg az Azure-bérlőre vonatkozó szükséges adatokat, köztük a **Helyet**, a **Tartománynevet**, és az előző lépésekben mentett **Alkalmazásazonosítót** és **Alkalmazáskulcsot**.
4. Kattintson a **Mentés**gombra. A Jamf Pro ellenőrzi a beállításokat és a sikeres végrehajtást.

## <a name="set-up-compliance-policies-and-register-devices"></a>Megfelelőségi szabályzatok beállítása és eszközök regisztrálása

Miután végzett az Intune és a Jamf közötti integráció konfigurálásával, [megfelelőségi szabályzatokat kell alkalmaznia a Jamf által kezelt eszközökre](conditional-access-assign-jamf.md).

## <a name="information-shared-from-jamf-pro-to-intune"></a>A Jamf Pro információmegosztása az Intune-nal

A Jamf Pro rögzíti a felügyelt macOS-alapú eszközök eszközkészletadatait. A Jamf Pro a következő információkat továbbítja az Intune-nak:

* Azure AD-eszközazonosító
* JAMF eszközkészlet-állapot (a Jamf Pro szolgáltatásba az elmúlt 24 órán belül bejelentkezett számítógép eszközkészlet-állapota)
* Operációs rendszer verziója
* Azure AD-felhasználói azonosító
* Titkosított (FileVault 2)
* Forgalomirányító állapota
* Jelszó: Karakterkészletek minimális száma
* Jelszó lejárata (nap)
* Jelszó típusa – egyszerű, alfanumerikus, vagy ismeretlen
* Automatikus bejelentkezés tiltása
* PIN-kód minimális hossza
* Jelszó: az újrafelhasználásból kizárt korábbi jelszavak száma
* Rendszer sértetlenségének védelme
* Legutóbbi bejelentkezés
* Architektúra típusa
* Rendelkezésre álló RAM-tárhelyek
* Akkumulátor kapacitása
* Rendszerindító ROM
* Busz sebessége
* Gyorsítótár mérete
* Eszköz neve
* Csatlakozás tartományhoz
* Jamf-azonosító
* MAC-cím
* Gyártmány
* Modell
* Modellazonosító
* Hálózati adapter sebessége
* Magok száma
* Processzorok száma
* Operációs rendszer
* Platform
* Processzor sebessége
* Processzor típusa
* Másodlagos MAC-cím
* Sorozatszám
* SMC verziója
* RAM mérete összesen
* UDID
* Felhasználó e-mail-címe

## <a name="next-steps"></a>További lépések

- [Megfelelőségi szabályzatok alkalmazása Jamf által felügyelt eszközökön](conditional-access-assign-jamf.md)
