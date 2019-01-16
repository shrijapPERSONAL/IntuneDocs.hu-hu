---
title: A Jamf Pro integrálása a Microsoft Intune-nal a megfelelőség |} A Microsoft Intune-ban
description: A Microsoft Intune megfelelőségi szabályzatait az Azure Active Directory feltételes hozzáférésével használva biztonságossá teheti a Jamf által kezelt eszközöket.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 971dc851714045a8a3b60dfe8ff6c6acc4419294
ms.sourcegitcommit: 7c41f42d6e398ed46aa602ec8aaa4f39aaf92772
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54325015"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>A Jamf Pro integrálása az Intune-nal a megfelelőség érdekében

A következőkre vonatkozik: Intune az Azure Portalon

Ha a szervezet használja [a Jamf Pro](https://www.jamf.com) kezelheti a végfelhasználók Mac számítógépeken, segítségével a Microsoft Intune megfelelőségi szabályzatok az Azure Active Directory feltételes hozzáférés győződjön meg arról, hogy megfelelnek-e a szervezetnél található eszközökön.

## <a name="prerequisites"></a>Előfeltételek

A Jamf Pro használatával történő feltételes hozzáférés konfigurálásához a következőkre van szüksége:

- A Jamf Pro 10.1.0-ás vagy későbbi verziója
- [macOS-hez készült Céges portál alkalmazás](https://aka.ms/macoscompanyportal)
- OS X 10.11-es vagy későbbi Yosemite verzióval rendelkező macOS-alapú eszközök

## <a name="connecting-intune-to-jamf-pro"></a>Az Intune csatlakoztatása a Jamf Pro-hoz

Az Intune csatlakoztatása a Jamf Pro meg:

1. Új alkalmazás létrehozása az Azure-ban
2. Az Intune engedélyezése a Jamf Pro-val történő integrációra
3. Feltételes hozzáférés konfigurálása a Jamf Pro szolgáltatásban

## <a name="create-an-application-in-azure-active-directory"></a>Alkalmazás létrehozása az Azure Active Directoryban

1. Az a [az Azure portal](https://portal.azure.com), lépjen a **Azure Active Directory** > **Alkalmazásregisztrációk**.
2. Válassza ki **+ új alkalmazásregisztráció**.
3. Adjon meg egy **megjelenítendő nevet**, például **Jamf feltételes hozzáférés**.
4. Válassza ki **webalkalmazás / API**.
5. Adja meg a **Bejelentkezési URL-címet** a Jamf Pro-példány URL-címe alapján.
6. Kattintson a **Létrehozás** gombra. Az alkalmazás létrejött, és a portál megjelenít az alkalmazás részletei.
7. Mentse a **Alkalmazásazonosító** az új alkalmazás. Ez az azonosító egy későbbi eljárásban adja meg. Majd **beállítások** , majd **API-hozzáférés** > **kulcsok**.
8. A a *kulcsok* panelen adja meg egy **leírása**, mennyi ideig kell várni, **lejárat**, majd válassza ki **mentése** az alkalmazás létrehozása Kulcs (érték).

   > [!IMPORTANT]
   > Az alkalmazáskulcs csak egyszer jelenik meg a folyamat során. Mindenképpen olyan helyre mentse, ahol később könnyen hozzáférhet.

8. Az a *beállítások* lépjen az alkalmazás panelen **API-hozzáférés** > **szükséges engedélyek**. Válassza ki a meglévő engedélyeit, és kattintson a **törlése** , és törölje az összes engedélyt. Meglévő engedélyeket törlése szükség, akkor adjon hozzá egy új engedélyt, és az alkalmazás csak akkor működik, ha egyetlen szükséges engedéllyel rendelkezik.  
9. Új rendeléséhez jelölje **+ Hozzáadás** > **API kiválasztása** > **a Microsoft Intune API**, és kattintson a **kiválasztása**.
10. A a *hozzáférés engedélyezése* ablaktáblán válassza **eszközattribútumok küldése a Microsoft Intune** majd **kiválasztása**, majd **kész**.
11. Az a *szükséges engedélyek* ablaktáblán válassza előbb **engedélyek megadása** , majd **Igen** a alkalmazni a szükséges engedélyeket az alkalmazás.

    > [!NOTE]
    > Az alkalmazáskulcs lejártakor új alkalmazáskulcsot kell létrehoznia a Microsoft Azure-ban, majd frissítenie kell a feltételes hozzáférési adatokat a Jamf Pro-ban. A szolgáltatás megszakításmentes végrehajtása érdekében az Azure lehetővé teszi, hogy a régi és az új kulcs egyidejűleg aktív legyen.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Az Intune engedélyezése a Jamf Pro-val történő integrációra

1. Az a [az Azure portal](https://portal.azure.com), lépjen a **a Microsoft Intune** > **Eszközmegfelelőség** > **Partnereszköz kezelése**.
2. Engedélyezze a megfelelőségi összekötőt jamf illessze be az előző eljárás során mentett az Alkalmazásazonosítót a **Jamf Azure Active Directory Alkalmazásazonosító** mező.
3. Kattintson a **Mentés** gombra.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>A Microsoft Intune-integráció konfigurálása a Jamf Pro szolgáltatásban

1. A Jamf Pro oldalán nyissa meg a **Globális felügyelet** > **Feltételes hozzáférés** lehetőséget. Kattintson a **Microsoft Intune-integráció** lapon található **Szerkesztés** gombra.
2. Jelölje be a **Microsoft Intune-integráció engedélyezése** jelölőnégyzetet.
3. Adja meg az Azure-bérlőre vonatkozó szükséges adatokat, köztük a **Helyet**, a **Tartománynevet**, és az előző lépésekben mentett **Alkalmazásazonosítót** és **Alkalmazáskulcsot**.
4. Kattintson a **Mentés** gombra. A Jamf Pro ellenőrzi a beállításokat, és a sikerességének ellenőrzéséhez.

## <a name="set-up-compliance-policies-and-register-devices"></a>Megfelelőségi szabályzatok beállítása és eszközök regisztrálása

Miután az Intune és a Jamf közötti integráció konfigurálásához kell [megfelelőségi szabályzatok alkalmazása Jamf által felügyelt eszközökön](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>További lépések

- [Megfelelőségi szabályzatok alkalmazása Jamf által felügyelt eszközökön](conditional-access-assign-jamf.md)
- [Az Intune-nak küld adatokat a Jamf](data-jamf-sends-to-intune.md)
