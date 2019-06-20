---
title: A Jamf Pro integrálása a Microsoft Intune-nal a megfelelőség érdekében
titleSuffix: Microsoft Intune
description: Az Azure Active Directory feltételes hozzáférés a Microsoft Intune megfelelőségi szabályzatok használatával segítheti a biztonságos Jamf által felügyelt eszközökön.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d25012790322491a9038f0bcf9349434d5a45b8d
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251086"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>A Jamf Pro integrálása az Intune-nal a megfelelőség érdekében

Érintett kiadások: Intune az Azure Portalon

Ha a szervezet használja [a Jamf Pro](https://www.jamf.com) kezelheti a végfelhasználók Mac számítógépeken, használhatja a Microsoft Intune megfelelőségi szabályzatok az Azure Active Directory feltételes hozzáférés, győződjön meg arról, hogy megfelelnek-e a szervezetben lévő eszközök.

## <a name="prerequisites"></a>Előfeltételek

Feltételes hozzáférés konfigurálása a Jamf Pro a következőkre lesz szüksége:

- A Jamf Pro 10.1.0-ás vagy későbbi verziója
- [macOS-hez készült Céges portál alkalmazás](https://aka.ms/macoscompanyportal)
- OS X 10.11-es vagy későbbi Yosemite verzióval rendelkező macOS-alapú eszközök

## <a name="connecting-intune-to-jamf-pro"></a>Az Intune csatlakoztatása a Jamf Pro-hoz

Az Intune csatlakoztatása a Jamf Pro meg:

1. Új alkalmazás létrehozása az Azure-ban
2. Az Intune engedélyezése a Jamf Pro-val történő integrációra
3. Feltételes hozzáférés konfigurálása a Jamf Pro szolgáltatásban

## <a name="create-an-application-in-azure-active-directory"></a>Alkalmazás létrehozása az Azure Active Directoryban

1. Az a [az Azure portal](https://portal.azure.com), lépjen a **Azure Active Directory** > **Alkalmazásregisztrációk**, majd válassza ki **új regisztrációs**. 

2. Az a **alkalmazás regisztrálása** csoportjában adja meg a következő adatokat:
   - Az a **neve** területén adja meg egy kifejező alkalmazás nevét, például **Jamf feltételes hozzáférés**.
   - Az a **támogatott fióktípusok** szakaszban jelölje be **bármely szervezeti directory fiókok**. 
   - A **átirányítási URI-t**, hagyja meg az alapértelmezett webes, és adja meg a Jamf Pro-példány URL-CÍMÉT.  

3. Válassza ki **regisztrálása** hozhat létre az alkalmazást, és az új alkalmazáshoz – Áttekintés lap megnyitásához.  

4. Az alkalmazás **áttekintése** lapon, másolja a **Alkalmazásazonosítót (ügyfél)** értékét, és jegyezze fel későbbi használat céljából. Ez az érték későbbi eljárásokban szüksége.  

5. Válassza ki **tanúsítványok és titkos kulcsok** alatt **kezelés**. Válassza ki a **új titkos ügyfélkulcsot** gombra. Adjon meg egy értéket a **leírás**, az egyik lehetőséget sem **lejárat** válassza **Hozzáadás**.

   > [!IMPORTANT]  
   > Mielőtt elhagyja az oldalt, másolja az értéket a titkos ügyfélkulcsot, és jegyezze fel későbbi használat céljából. Ez az érték későbbi eljárásokban szüksége lesz. Ez az érték nem érhető el, az alkalmazás regisztrációját újbóli létrehozása nélkül.  

6. Válassza ki **API-engedélyek** felügyelet alatt.  Válassza ki a meglévő engedélyeket, majd **engedély eltávolítása** törli ezeket az engedélyeket. Eltávolítása minden meglévő engedélyre szükség, mivel egy új engedélyt adhat meg, és az alkalmazás csak akkor működik, ha egyetlen szükséges engedéllyel rendelkezik.  

7. Új rendeléséhez jelölje **adjon hozzá egy engedélyt**. Az a **kérelem API-engedélyek** lapon jelölje be **Intune**, majd válassza ki **Alkalmazásengedélyek**. Csak tartozó jelölőnégyzet bejelölésével **update_device_attributes**.  

   Válassza ki **adjon hozzá engedélyt** a konfiguráció mentéséhez.  

8. Az a **API-engedélyek** lapon jelölje be **adja meg a Microsoft a rendszergazdai jóváhagyás**, majd válassza az Igen gombra.  

   Az Azure ad-ben az alkalmazás regisztrációs folyamat befejeződött.


    > [!NOTE]
    > Ha a titkos ügyfélkulcsot lejár, kell az Azure-ban hozzon létre egy új titkos ügyfélkulcsot és frissítse a feltételes hozzáférési adatokat a Jamf Pro szolgáltatásban. Azure lehetővé teszi, hogy mindkét a régi titkos és az új kulcs egyidejűleg aktív szolgáltatás megszakításmentes végrehajtása érdekében.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Az Intune engedélyezése a Jamf Pro-val történő integrációra

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), és nyissa meg **a Microsoft Intune** > **Eszközmegfelelőség** > **Partnereszköz kezelése**.

2. Engedélyezze a megfelelőségi összekötőt jamf illessze be az előző eljárás során mentett az Alkalmazásazonosítót a **Jamf Azure Active Directory Alkalmazásazonosító** mező.

3. Kattintson a **Mentés** gombra.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>A Microsoft Intune-integráció konfigurálása a Jamf Pro szolgáltatásban

1. A Jamf Pro oldalán nyissa meg a **Globális felügyelet** > **Feltételes hozzáférés** lehetőséget. Kattintson a **Microsoft Intune-integráció** lapon található **Szerkesztés** gombra.

2. Jelölje be a **Microsoft Intune-integráció engedélyezése** jelölőnégyzetet.

3. Az Azure-bérlőhöz, beleértve a szükséges információt nyújtanak az **hely**, **tartománynév**, a **Alkalmazásazonosító**, és az értéke a *ügyfél titkos kulcs* , hogy mentette az alkalmazást az Azure ad-ben való létrehozásakor.  

4. Kattintson a **Mentés** gombra. A Jamf Pro ellenőrzi a beállításokat, és ellenőrzi a sikeres.

## <a name="set-up-compliance-policies-and-register-devices"></a>Megfelelőségi szabályzatok beállítása és eszközök regisztrálása

Miután az Intune és a Jamf közötti integráció konfigurálásához kell [megfelelőségi szabályzatok alkalmazása Jamf által felügyelt eszközökön](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>További lépések

- [Megfelelőségi szabályzatok alkalmazása Jamf által felügyelt eszközökön](conditional-access-assign-jamf.md)
- [Az Intune-nak küld adatokat a Jamf](data-jamf-sends-to-intune.md)
