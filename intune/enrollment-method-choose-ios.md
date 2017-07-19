---
title: "Az iOS-eszközök regisztrálási módjának kiválasztása az Intune-ban"
titleSuffix: Intune on Azure
description: "Útmutató iOS-eszközök Microsoft Intune-ban való regisztrációjának beállításához.”"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>Az iOS- és macOS-eszközök regisztrálási módjának kiválasztása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ez a témakör azt ismerteti, milyen módszereket használhat a rendszergazda az iOS-eszközök regisztrációjának engedélyezéséhez az Intune-ban.

Az alábbi információk alapján döntheti el, hogy milyen módszerrel regisztrálja az iOS-eszközöket. A következő eljárások a BYOD kivételével mind a vállalati tulajdonban lévő eszközök regisztrálására szolgálnak.

**Előfeltétel:** [Egy Apple Push Notification szolgáltatásbeli tanúsítvány](apple-mdm-push-certificate-get.md).

## <a name="user-owned-ios-devices-byod"></a>A felhasználó tulajdonában lévő iOS-eszközök (BYOD)

Ha a felhasználók saját eszközeiket szeretnék regisztrálni (BYOD), akkor letölthetik az iOS céges portál alkalmazást az App Store-ból, majd követniük kell az alkalmazástól kapott utasításokat. A regisztrációt követően a felhasználók kapcsolódhatnak a vállalat hálózatához, csatlakozhatnak a tartományhoz vagy az Azure Active Directoryhoz, és hozzáférnek a vállalati erőforrásokhoz. A BYOD engedélyezéséhez az egyetlen követelmény az [Apple leküldéses értesítési szolgáltatási (Apple Push Notification Service-) tanúsítvány](apple-mdm-push-certificate-get.md) megléte. Le is tilthatja a személyes tulajdonú iOS-eszközök regisztrációját. Útmutatót a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című cikkben talál.

## <a name="user-owned-macos-devices-byod"></a>A felhasználó tulajdonában macOS-eszközök (BYOD)

Engedélyezheti a macOS-eszközök regisztrációját. A macOS-regisztráció engedélyezéséhez az egyetlen követelmény az [Apple leküldéses értesítési szolgáltatási (Apple Push Notification Service-) tanúsítvány](apple-mdm-push-certificate-get.md) megléte. További információ: [macOS-eszközök regisztrálása](./macos-enroll.md)

## <a name="enrollment-program-with-apple"></a>Az Apple készülékregisztrációs program
Az Apple kínál olyan eszközvásárlási programokat, amelyek magukban foglalnak eszközregisztrációt és felügyeleti infrastruktúrát. Az ezen programok bármelyikének keretében vásárolt eszközök csoportosan regisztrálhatók „vezeték nélkül”, eszköz-sorozatszámok hozzárendelésével az Intune-felügyelethez.

- **Készülékregisztrációs program (DEP)** – Az Apple eszközregisztrációs programja cégeknek és vállalatoknak. További információt az [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](device-enrollment-program-enroll-ios.md) című témakörben találhat.
- **Apple School Manager** – Az Apple eszközregisztrációs programja iskolák részére. További információ: [iOS-eszközök regisztrációjának engedélyezése az Apple School Managerben](apple-school-manager-set-up-ios.md)

## <a name="apple-configurator"></a>Apple Configurator

Az iOS-eszközök egy Vállalati regisztrációs profil exportálásával, majd a mobileszközök egy Apple Configurator eszközt futtató Mac számítógéphez való csatlakoztatásával regisztrálhatók. Az Apple Configurator a regisztráció két formáját támogatja:

- **Regisztrálás a Beállítási asszisztenssel**: Gyári alaphelyzetbe állítja az eszközt, és felkészíti a beállításhoz az új felhasználó számára. Ennél a módszernél a rendszergazdának a regisztráció előkonfigurálásához csatlakoztatnia kell az iOS-eszközt USB-kapcsolaton keresztül egy Apple Configuratort futtató Mac számítógéphez. Az eszközöket ekkor el kell juttatni a felhasználókhoz, akik az eszköz első elindításakor elindítják a Beállítási asszisztenst. A folyamat konfigurálja az eszközt a felhasználók munkahelyi vagy iskolai azonosítójával, és elvégzi a regisztrációt. További információt az [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével](apple-configurator-setup-assistant-enroll-ios.md) című témakörben találhat.

- **Közvetlen regisztrálás**: Létrejön egy Apple Configurator-kompatibilis fájl, amely az eszköz előkészítésez szükséges. A regisztrált eszköz nincs gyári alaphelyzetbe állítva, és egyetlen felhasználóhoz sem kapcsolódik. Az eszközök regisztrálásához a rendszergazdának csatlakoztatnia kell az iOS-eszközt USB-kapcsolaton keresztül egy Apple Configuratort futtató Mac számítógéphez. További információt az [iOS-eszközök közvetlen regisztrálása az Apple Configurator használatával](apple-configurator-direct-enroll-ios.md) című témakörben találhat.

## <a name="use-the-device-enrollment-program-dep"></a>A Device Enrollment Program (DEP) használata

A DEP a DEP-en keresztül megvásárolt eszközökre egy regisztrációs profilt telepít. Amikor a felhasználó az eszköz első elindításakor a Beállítási asszisztenst futtatja az eszközön, az eszköz regisztrációja az Intune-ban rögzül. További információt az [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](device-enrollment-program-enroll-ios.md) című témakörben találhat.

## <a name="use-the-device-enrollment-manager-dem"></a>A készülékregisztráció-kezelő (DEM) használata
A készülékregisztráció-kezelő egy általános felhasználói fiók, amely legfeljebb 1000 külső eszközt regisztrálhat és kezelhet. A DEM által felügyelt eszközök nem rendelkezhetnek felhasználói affinitással, így az eszköznek soha sincs tulajdonosa. Az Intune-felhasználóknak DEM-jogosultságok megadásával biztosíthatja ezeket a lehetőségeket. A DEM-felhasználó által regisztrált valamennyi eszköz egy Intune-licencet használ. További információt az [Eszközök regisztrálása a készülékregisztrációs program segítségével](device-enrollment-manager-enroll.md) című témakörben találhat.
