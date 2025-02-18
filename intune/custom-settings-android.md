---
title: Egyéni beállítások hozzáadása Android-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Egyéni profilok Android-eszközökhöz való hozzáadásával vagy létrehozásával előmegosztott kulccsal rendelkező Wi-Fi-profilt és alkalmazásonkénti VPN-profilt hozhat létre, vagy engedélyezheti és letilthatja a Samsung Knox Standard-eszközök alkalmazásait a Microsoft Intune-ban
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 39aba38d808a770ee04f5d165ca8037b43576812
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374016"
---
# <a name="use-custom-settings-for-android-devices-in-microsoft-intune"></a>Egyéni beállítások használata Android-eszközökhöz a Microsoft Intune-ban

A Microsoft Intune-nal egyéni beállításokat adhat hozzá vagy hozhat létre az Android-eszközökhöz „egyéni profilok” használatával. Az egyéni profilok az Intune részét képezik. Akkor hasznosak, ha olyan eszközbeállításokat és funkciókat szeretne használni, amelyek nem érhetők el beépítetten az Intune-ban.

Az Android rendszer egyéni profiljai az Open Mobile Alliance Uniform Resource Identifier (OMA-URI) beállításokat használják a különböző funkciók konfigurálásához Android-eszközökön. Ezekkel a beállításokkal általában a mobileszközgyártók vezérlik ezeket a funkciókat.

Egyéni profillal a következő Android-beállításokat konfigurálhatja és rendelheti hozzá. A következő beállítások nem érhetők el beépítetten az Intune-ban:

- [Wi-Fi-profil létrehozása előmegosztott kulccsal](/intune/wi-fi-profile-shared-key)
- [Alkalmazásonkénti VPN-profil létrehozása](/intune/android-pulse-secure-per-app-vpn)
- [Alkalmazások engedélyezése és letiltása Samsung Knox Standard-eszközökön](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Az egyéni profilokban csak a felsorolt beállítások konfigurálhatók. Az Android-eszközök nem teszik elérhetővé a konfigurálható OMA-URI-beállítások teljes listáját. Ha több beállítást szeretne látni, szavazzon rájuk az [Intune Uservoice webhelyén](https://microsoftintune.uservoice.com/forums/291681-ideas).

Ebből a cikkből megtudhatja, hogyan hozhat létre egyéni profilt az Android-eszközök számára.

## <a name="create-the-profile"></a>A profil létrehozása

1. Jelentkezzen be a [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő beállításokat:

    - **Név**: Adja meg egy nevet a profilnak, például `android custom profile`.
    - **Description** (Leírás): Adja meg a profil leírását.
    - **Platform**: Válasszon **Android**.
    - **Profil típusa**: Válasszon **egyéni**.

4. Az **Egyéni OMA-URI-beállítások** menüben válassza a **Hozzáadás** lehetőséget. Adja meg a következő beállításokat:

    - **Név**: Adja meg egy egyedi nevet az OMA-URI beállítás számára, hogy könnyen megtalálhassa.
    - **Description** (Leírás): Adjon meg egy leírást, amely áttekintést ad a beállítást, és bármilyen egyéb fontos részleteket.
    - **OMA-URI**: Adja meg az OMA-URI beállításai használni kívánt.
    - **Adattípus**: Válassza ki az adatokat fogja használni az OMA-URI-beállítás. A választható lehetőségek:

      - Sztring
      - Sztring (XML-fájl)
      - Dátum és időpont
      - Egész szám
      - Lebegőpontos szám
      - Logikai
      - Base64 (fájl)

    - **Érték**: A megadott OMA-URI társítani kívánt adatok értéket adjon meg. Az érték a választott adattípustól függ. A **Dátum és idő** típus esetén például a dátumválasztóból választhat értéket.

    Néhány beállítás megadása után válassza az **Exportálás** lehetőséget. Az **Exportálás** a hozzáadott értékek listáját hozza létre egy vesszővel tagolt (.csv) fájlban.

5. Válassza ki **OK** a módosítások mentéséhez. Szükség szerint adjon hozzá további beállításokat. 
6. Ha elkészült, az Intune-profil létrehozásához kattintson az **OK** > **Létrehozás** lehetőségre. Ha a profil elkészült, megjelenik az **Eszközkonfiguráció – Profilok** listában.

## <a name="next-steps"></a>További lépések

A profil létrejött, de egyelőre nem csinál semmit. Következő lépésként [végezze el a profil hozzárendelését](device-profile-assign.md).

Tekintse meg, hogyan [hozhat létre profilokat Android Enterprise-eszközökön](custom-settings-android-for-work.md).
