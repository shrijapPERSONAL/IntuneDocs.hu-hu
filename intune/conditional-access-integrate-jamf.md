---
title: "A Jamf Pro integrálása az Intune-nal a megfelelőség érdekében"
titlesuffix: Azure portal
description: "A megfelelőség alkalmazásával biztonságosabbá teheti a Jamf által felügyelt eszközöket."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b37ffd23f8cf8764ba457b0803dfc308cf1c071
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>A Jamf Pro integrálása az Intune-nal a megfelelőség érdekében

|A következőkre vonatkozik: Intune az Azure Portalon |
|--|
|A klasszikus portálbeli Intune-ról keres dokumentációt? [Lépjen tovább ide](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Jelenleg Private Preview verzióban|
|--|
|A jelen témakörben leírt funkciók jelenleg csak Private Preview verzióban elérhetők az ügyfelek számára. Miután a verzió minden felhasználó számára elérhetővé vált, eltávolítjuk ezt a megjegyzést.|
| |

Ha a szervezet a [Jamf Pro](https://www.jamf.com) segítségével felügyeli a végfelhasználók Mac-alapú számítógépeit, lehetősége van a Microsoft Intune megfelelőségi szabályzataival és az Azure Active Directory-alapú feltételes hozzáféréssel biztosítani az eszközmegfelelőséget a szervezetben.

## <a name="prerequisites"></a>Előfeltételek

A Jamf Pro használatával történő feltételes hozzáférés konfigurálásához a következőkre van szüksége:

- Hozzáférés a macOS feltételes hozzáférést biztosító Intune Private Preview verzióhoz
- A Jamf Pro 10.1.0-ás vagy későbbi verziója
- [macOS-hez készült Céges portál alkalmazás](https://aka.ms/macoscompanyportal)
- OS X 10.11-es vagy későbbi Yosemite verzióval rendelkező macOS-alapú eszközök

## <a name="connecting-intune-to-jamf-pro"></a>Az Intune csatlakoztatása a Jamf Pro-hoz

Az Intune és a Jamf Pro csatlakoztatásához a következők szükségesek:

1. Új alkalmazás létrehozása az Azure-ban
2. Az Intune engedélyezése a Jamf Pro-val történő integrációra
3. Feltételes hozzáférés konfigurálása a Jamf Pro szolgáltatásban

## <a name="create-a-new-application-in-azure-active-directory"></a>Új alkalmazás létrehozása az Azure Active Directoryban

1. Nyissa meg az **Azure Active Directory** > **Alkalmazásregisztráció** oldalt.
2. Kattintson az **+Új alkalmazás létrehozása** elemre.
3. Adjon meg egy **megjelenítendő nevet**, például **Jamf feltételes hozzáférés**.
4. Kattintson a **Webalkalmazás / API** elemre.
5. Adja meg a **Bejelentkezési URL-címet** a Jamf Pro számára.
6. Kattintson az **Alkalmazás létrehozása** lehetőségre.
7. Mentse az újonnan létrehozott **Alkalmazásazonosítót**, majd nyissa meg az **Összes beállítás** > **Kulcsok** oldalt az új alkalmazáskulcs létrehozásához. Mentse az alkalmazáskulcsot.

  > [!NOTE]
  > Az alkalmazáskulcs csak egyszer jelenik meg a folyamat során. Mindenképpen olyan helyre mentse, ahol később könnyen hozzáférhet.

8. Nyissa meg az **Összes beállítás** > **API-hozzáférés**  > **Szükséges engedélyek** oldalt, és törölje az összes engedélyt.

  > [!NOTE]
  > Adjon hozzá egy új szükséges engedélyt. Az alkalmazás csak akkor működik megfelelően, ha egyetlen szükséges engedéllyel rendelkezik.

9.  Válassza ki a **Microsoft Intune API** lehetőséget, majd kattintson a **Kiválaszt** elemre.
10. Válassza ki a **Eszközattribútumok küldése a Microsoft Intune-ba** lehetőséget, majd kattintson a **Kiválaszt** elemre.
11. Miután mentette az alkalmazáshoz szükséges engedélyeket, kattintson az **Engedélyek megadása** gombra.

  > [!NOTE]
  > Az alkalmazáskulcs lejártakor új alkalmazáskulcsot kell létrehoznia a Microsoft Azure-ban, majd frissítenie kell a feltételes hozzáférési adatokat a Jamf Pro-ban. A szolgáltatás megszakításmentes végrehajtása érdekében az Azure lehetővé teszi, hogy a régi és az új kulcs egyidejűleg aktív legyen.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Az Intune engedélyezése a Jamf Pro-val történő integrációra

1. A Microsoft Azure Portalon nyissa meg a **Microsoft Intune** > **Eszközmegfelelőség** > **Jamf megfelelőségi összekötő** oldalt.
2. Illessze be az alkalmazásazonosítót a **Jamf Azure Active Directory alkalmazásazonosító** mezőbe, és ezzel engedélyezze a megfelelőségi összekötőt.
3. Kattintson a **Mentés**gombra.

## <a name="configure-conditional-access-in-jamf-pro"></a>Feltételes hozzáférés konfigurálása a Jamf Pro szolgáltatásban

1. A Jamf Pro oldalán nyissa meg a **Globális felügyelet** > **Feltételes hozzáférés** lehetőséget. Kattintson a **Microsoft** lapon található **Szerkesztés** gombra.
2. Jelölje be a **Feltételes hozzáférés engedélyezése a Microsofttal** feliratú jelölőnégyzetet.
3. Adja meg az Azure-bérlőre vonatkozó szükséges adatokat, köztük a **Helyet**, a **Tartománynevet**, és az előző lépésekben mentett **Alkalmazásazonosítót** és **Alkalmazáskulcsot**.
4. Kattintson a **Mentés**gombra. A Jamf Pro ellenőrzi a beállításokat és a sikeres végrehajtást.

## <a name="information-shared-from-jamf-pro-to-intune"></a>A Jamf Pro információmegosztása az Intune-nal

A Jamf Pro rögzíti a felügyelt macOS-alapú eszközök eszközkészletadatait. A Jamf Pro a következő információkat továbbítja az Intune-nak:

* Azure AD-eszközazonosító
* JAMF eszközkészlet-állapot (a Jamf Pro szolgáltatásba az elmúlt 24 órán belül bejelentkezett számítógép eszközkészlet-állapota)
* Operációs rendszer verziója
* Azure AD-felhasználói azonosító
* Titkosított (FileVault 2)
* Forgalomirányító állapota
* Jelszó: Karakterkészletek minimális száma
* Jelszó lejárta (napokban)
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