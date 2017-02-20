---
title: "Az Intune egyéni eszközbeállításainak konfigurálása | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: További információ arról, hogyan használható az Intune az egyéni beállítások a felügyelt eszközökön való konfigurálásához."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: b404df57e94afe7b80dd39163ed72a24d8b05508


---

# <a name="how-to-configure-custom-device-settings"></a>Az egyéni eszközbeállítások konfigurálása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="when-to-use-custom-settings"></a>Mikor kell egyéni beállításokat használni?

Az egyéni eszközbeállítások akkor lehetnek hasznosak, ha az Intune nem rendelkezik a kívánt beépített beállítással, vagy ha azok nem érhetőek el más eszközprofilokból.
Az egyéni beállításokat minden platformra külön-külön kell konfigurálni. Például Android és Windows rendszerű eszközökre megadhat OMA-URI (Open Mobile Alliance Uniform Resource Identifier) értékeket az eszköz funkcióinak vezérléséhez. Apple-eszközök esetében importálhatja az [Apple Configuratorral](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) létrehozott fájlokat.

A témakörben található információk alapján megismerheti az egyéni beállításokkal rendelkező profilok konfigurálásának alapjait, és az egyes platformokra vonatkozó további témakörökben bővebben is olvashat az eszközök tulajdonságairól.

## <a name="create-a-device-profile-containing-custom-settings"></a>Az egyéni beállításokat tartalmazó eszközprofil létrehozása

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget.
2. Az **Eszközök konfigurálása** panelen válassza a **Kezelés** > **Profilok** lehetőséget.
3. A profilok paneljén válassza a **Profil létrehozása** lehetőséget.
4. A **Profil létrehozása** panelen írja be az egyéni profilra vonatkozó **Név** és **Leírás** szövegét.
5. A **Platform** legördülő listából válassza ki azt az eszközplatformot, amelyre egyéni beállításokat szeretne alkalmazni. Jelenleg az alábbi platformokra vonatkozóan lehet egyéni eszközbeállításokat megadni:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 és újabb**
6. A **Profil** típusa legördülő listában válassza az **Egyéni** lehetőséget.
7. A kiválasztott platformtól függően a konfigurálható beállítások eltérőek. Az egyes platformokra vonatkozóan az alábbi témakörökben találja a beállítások részletes ismertetését:
    - [Android-beállítások](custom-for-android.md)
    - [iOS-beállítások](custom-for-ios.md)
    - [macOS-beállítások](custom-for-macos.md)
    - [Windows Phone 8.1-beállítások](custom-for-windows-phone-8-1.md)
    - [Windows 10-beállítások](custom-for-windows-10.md)
8. Ha elkészült, lépjen vissza a **Profil létrehozása** panelre, és válassza a **Létrehozás** elemet.

Ekkor létrejön a profil, és megjelenik a profilok listáját tartalmazó panelen.
Ha a profilt csoportokhoz szeretné hozzárendelni, erről az [eszközprofilok hozzárendelését](how-to-assign-device-profiles.md) ismertető cikk nyújt tájékoztatást.




<!--HONumber=Feb17_HO1-->

