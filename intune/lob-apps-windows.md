---
title: Üzletági Windows-alkalmazás hozzáadása a Microsoft Intune-hoz
titleSuffix: ''
description: Ismerje meg, hogyan adhat hozzá egy Windows üzletági (LOB) alkalmazások Microsoft Intune-nal.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 05d0841a8d358ac691cbd2293e95e2f2aa8a3f23
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799149"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Üzletági Windows-alkalmazás hozzáadása a Microsoft Intune-hoz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az üzletági (LOB) alkalmazásokat egy alkalmazástelepítő fájlból adja hozzá. Az ilyen alkalmazásokat általában házon belül írják. Az alábbi lépések nyújtanak útmutatást az üzletági Windows-alkalmazások a Microsoft Intune-hoz való hozzáadásához.

## <a name="step-1-specify-the-software-setup-file"></a>1. lépés: A szoftvertelepítő fájl megadása

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget.

## <a name="step-2-configure-the-app-package-file"></a>2. lépés: Az alkalmazáscsomag-fájl konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazáscsomag-fájl** lehetőséget.
2. Az **Alkalmazáscsomag-fájl** panelen válassza a tallózás gombot. Ez után jelölje ki az **.msi**, **.appx** vagy **.appxbundle** kiterjesztésű telepítőfájlt.

    > [!NOTE]
    > A windowsos alkalmazások fájlnévkiterjesztései közé tartozik az **.msi**, az **.appx**, az **.appxbundle**, az **.msix** és az **.msixbundle** is.  

1. Amikor végzett, válassza az **OK** gombot.


## <a name="step-3-configure-app-information"></a>3. lépés: Az alkalmazásadatok konfigurálása

1. Az **Alkalmazás hozzáadása** panelen válassza az **Alkalmazásadatok** lehetőséget.
2. Az **Alkalmazás adatai** panelen konfigurálja az alábbi információkat. Lehetséges, hogy ezen a panelen néhány érték automatikusan ki lesz töltve.
    - **Név**: Adja meg az alkalmazás nevét, a vállalati portálon megjelenő. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a Céges portálon.
    - **Description** (Leírás): Adja meg az alkalmazás leírását. A leírás megjelenik a Céges portálon.
    - **Közzétevő**: Itt adhatja meg az alkalmazás kiadójának nevét.
    - **Alkalmazásverzió figyelmen kívül hagyása**: Állítsa be **Igen** , ha az alkalmazást automatikusan frissíti annak fejlesztője az alkalmazás. Ez a beállítás csak mobil .msi alkalmazásokra vonatkozik.
    - **Kategória**: Válasszon ki egyet vagy többet a beépített Alkalmazáskategóriák közül, vagy válasszon egy kategóriát, amelyet Ön hozott létre. A kategóriákkal megkönnyítheti a felhasználók számára az alkalmazás megkeresését a Céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a céges portálon**: Az alkalmazás jól észrevehető módon való megjelenítése a vállalati portál fő lapján, amikor a felhasználók tallózással alkalmazásokat keresnek.
    - **Információs URL-cím**: Igény esetén megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-CÍMÉT. Az URL-cím megjelenik a Céges portálon.
    - **Adatvédelmi URL-címe**: Igény esetén megadhatja az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-CÍMÉT. Az URL-cím megjelenik a Céges portálon.
    - **Parancssori argumentumok**: Megadhatja, hogy a alkalmazni az .msi fájl futtatásakor kívánt parancssori argumentumokat. Például: **/q**.
    - **Fejlesztői**: Megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Szükség esetén adja meg az alkalmazás tulajdonosának nevét. Például **HR részleg**.
    - **Megjegyzések**: Adja meg az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Embléma**: Töltse fel az alkalmazáshoz társított ikont. Ez az ikon jelenik meg az alkalmazásnál a Céges portálon böngésző felhasználók számára.
3. Amikor végzett, válassza az **OK** gombot.

## <a name="step-4-finish-up"></a>4. lépés: Befejezés

1. Az **Alkalmazás hozzáadása** panelen ellenőrizze, hogy helyesen konfigurálta-e az alkalmazásadatokat.
2. Az alkalmazást a **Hozzáadás** elem kiválasztásával töltheti fel az Intune-ba.

## <a name="step-5-update-a-line-of-business-app"></a>5. lépés: Az üzletági alkalmazás frissítése

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Önfrissítő MSI-mobilalkalmazások konfigurálása a verzióellenőrzési folyamat figyelmen kívül hagyására

Az ismert önfrissítő MSI-mobilalkalmazásokat konfigurálhatja úgy, hogy figyelmen kívül hagyják a verzióellenőrzési folyamatot. 

Egyes MSI-telepítőalapú alkalmazásokat automatikusan frissít az adott alkalmazás fejlesztője. Az ilyen automatikusan frissített MSI-alkalmazások esetében konfigurálhatja az **Alkalmazásverzió figyelmen kívül hagyása** beállítást az **Alkalmazásadatok** panelen. Ha ezt a beállítást átállítja az **Igen** értékre, a Microsoft Intune nem kényszeríti a Windows-ügyfélen telepített alkalmazásverzió használatát. 

Ez a funkció akkor hasznos, ha nem szeretne versenyhelyzetbe kerülni. Konfliktus alakulhat ki például akkor, amikor az alkalmazást automatikusan frissíti annak fejlesztője, ugyanakkor az Intune is frissíti. Mindkettő megpróbálhatja kikényszeríteni az alkalmazás egy verziójának használatát a Windows-ügyfélen, ami ütközést eredményezhet.

## <a name="next-steps"></a>További lépések

- A létrehozott alkalmazás megjelenik az alkalmazások listájában. Mostantól hozzárendelheti az Ön által választott csoportokhoz. További segítségért lásd: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).

- További tájékoztató az alkalmazás jellemzőinek és hozzárendelési állapotának figyeléséről. Lásd: [Alkalmazásadatok és -hozzárendelések figyelése](apps-monitor.md).

- További tudnivalók az Intune-beli alkalmazás környezetéről. Lásd: [Az eszközök és alkalmazások életciklusának áttekintése](introduction-device-app-lifecycles.md).
