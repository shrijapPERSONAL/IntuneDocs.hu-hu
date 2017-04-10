---
title: "Szabályzatok érvénybe léptetése és alkalmazások telepítése | Microsoft Docs"
description: "Engedélyezheti a szabályzatok beállításait, és telepíthet olyan alkalmazásokat, amelyek azonnal rákerülnek az eszközökre, amint regisztrálják őket felügyeletre."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: 4093497553ccb7cc5f5c949f2ff0004697beb42a


---

# <a name="create-policies-and-publish-apps"></a>Szabályzatok létrehozása és alkalmazások közzététele

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör azt ismerteti az Intune-rendszergazdák számára, hogy miképpen hozhatnak létre szabályzatokat, illetve tehetnek közzé alkalmazásokat, amelyeket telepíthetnek a felügyelt eszközökre.

Mielőtt elkezd alkalmazásokat regisztrálni az Intune-ban, engedélyezhet szabályzatbeállításokat és alkalmazásokat. Ezek azonnal érvénybe lépnek és települnek, amint az eszközök felügyelet alá kerülnek. Az Intune-szabályzatok lehetőséget biztosítanak a mobileszközök biztonsági beállításainak kezelésére, a Windows tűzfal és az Endpoint Protection szolgáltatás számítógépeken alkalmazott beállításainak karbantartására, illetve alkalmazások telepítésére. Konfigurálhat szabályzatokat, felvehet alkalmazásokat, és telepítheti őket, hogy az eszközök azonnal megkapják ezeket a beállításokat és alkalmazásokat, amint regisztrálnak az Intune-ban.

A szabályzatok és az alkalmazások platformfüggőek.

## <a name="manage-device-settings"></a>Az eszközbeállítások kezelése

 Az eszközszabályzatok beállításainak konfigurálása és kezelése platformonként történik. A következő hivatkozásokkal elérhetők a különféle platformokban használható beállítások:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android és Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (asztali és mobilverzió)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Team](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

A következő cikk további tájékoztatást nyújt: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Alkalmazások felvétele és telepítése

Kétféleképpen vehet fel alkalmazásokat az Intune-ba, illetve telepítheti őket a felügyelt eszközökre:
- **Kötelező telepítés** – Az alkalmazás automatikusan települ a felügyelt eszközökre.
- **Elérhető telepítés** – Az alkalmazások megjelennek az Intune Munkahelyi portáljában, hogy a felhasználók eldönthessék, telepítik-e őket az eszközükre.

### <a name="add-apps"></a>Alkalmazások hozzáadása

Először elérhetővé kell tennie az alkalmazásokat az Intune-ban a következő módszerek valamelyikével:
- [Alkalmazások hozzáadása regisztrált eszközökhöz](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Alkalmazások hozzáadása az Intune ügyfélszoftvert tartalmazó gépekhez](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Alkalmazások telepítése

Az alkalmazás ekkor elérhetővé válik az Intune-ban, tehát telepíthető a felügyelt eszközökre:
- [Alkalmazások telepítése eszközökre](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Mennyiségi programban vásárolt alkalmazások telepítése:
    - [iOS – Volume Purchase Program](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Vállalati Windows Áruház](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    Azt követően, hogy konfigurálta az alkalmazásokat telepítésre, [konfigurálhatja az alkalmazásokat](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune), és [figyelheti az alkalmazásokat](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Felhasználók és eszközök rendszerezése**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**A Vállalati portál testreszabása** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Feb17_HO3-->


