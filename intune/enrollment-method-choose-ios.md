---
title: "Az iOS-eszközök regisztrálási módjának kiválasztása az Intune-ban"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Útmutató iOS-eszközök Microsoft Intune-ban való regisztrációjának beállításához"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ee0ecf26a333ec441eb95e79473a9bf405e4120c
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="choose-how-to-enroll-ios-devices"></a>iOS-eszközök regisztrálási módjának kiválasztása

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ez a témakör bemutatja az iOS-eszközök regisztrálására használható módszereket és a regisztráció előfeltételeit.

Az alábbi információk alapján döntheti el, hogy milyen módszerrel regisztrálja az iOS-eszközöket. A következő eljárások a BYOD kivételével mind a vállalati tulajdonban lévő eszközök regisztrálására szolgálnak.

**Előfeltétel:** [Egy Apple Push Notification szolgáltatásbeli tanúsítvány](apple-mdm-push-certificate-get.md).

## <a name="user-owned-ios-devices-byod"></a>A felhasználó tulajdonában lévő iOS-eszközök (BYOD)

Ha a felhasználók saját eszközeiket szeretnék használni (BYOD), számukra az a regisztrálás egyetlen módja, hogy letöltik az iOS Céges portál alkalmazást az Alkalmazás-áruházból, majd követik az alkalmazástól kapott utasításokat. A regisztrációt követően a felhasználók kapcsolódhatnak a vállalat hálózatához, csatlakozhatnak a tartományhoz vagy az Azure Active Directoryhoz, és hozzáférnek a vállalati erőforrásokhoz. Letilthatja a személyes tulajdonban lévő iOS-es eszközök regisztrálását. Útmutatót a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md#set-device-type-restrictions) című cikkben talál.

## <a name="apple-configurator"></a>Apple Configurator

Az iOS-eszközök egy vállalati regisztrációs profil exportálásával, majd a mobileszközöknek egy [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) eszközt futtató Mac számítógéphez való csatlakoztatásával regisztrálhatók. Az Apple Configurator a regisztráció két formáját támogatja:

- **Regisztrálás a Beállítási asszisztenssel**: Gyári alaphelyzetbe állítja az eszközt, és felkészíti a beállításhoz az új felhasználó számára. Ennél a módszernél a rendszergazdának a regisztráció előkonfigurálásához csatlakoztatnia kell az iOS-eszközt USB-kapcsolaton keresztül egy Apple Configuratort futtató Mac számítógéphez. Az eszközöket ekkor el kell juttatni a felhasználókhoz, akik elindítják a Beállítási asszisztenst. A folyamat konfigurálja az eszközt a felhasználók munkahelyi vagy iskolai azonosítójával, és elvégzi a regisztrációt. További információt az [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével](apple-configurator-setup-assistant-enroll-ios.md) című témakörben találhat.

- **Közvetlen regisztrálás**: Létrejön egy Apple Configurator-kompatibilis fájl, amely az eszköz előkészítésez szükséges. A regisztrált eszköz nincs gyári alaphelyzetbe állítva, és egyetlen felhasználóhoz sem kapcsolódik. Az eszközök regisztrálásához a rendszergazdának csatlakoztatnia kell az iOS-eszközt USB-kapcsolaton keresztül egy Apple Configuratort futtató Mac számítógéphez. További információt az [iOS-eszközök közvetlen regisztrálása az Apple Configurator használatával](apple-configurator-direct-enroll-ios.md) című témakörben találhat.

## <a name="use-the-device-enrollment-program-dep"></a>A Device Enrollment Program (DEP) használata

A DEP a DEP-en keresztül megvásárolt eszközökre egy regisztrációs profilt telepít. Amikor a felhasználó a Beállítási asszisztenst futtatja az eszközön, az eszköz regisztrációja az Intune-ban rögzül. A DEP programon keresztül regisztrált eszközök regisztrációját a felhasználók nem törölhetik. További információt az [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](device-enrollment-program-enroll-ios.md) című témakörben találhat.

## <a name="use-the-device-enrollment-manager-dem"></a>A készülékregisztráció-kezelő (DEM) használata
A készülékregisztráció-kezelő egyfajta felhasználói fiók, amely legfeljebb 1000 eszközt regisztrálhat és kezelhet. Ezt a lehetőséget a DEM-fiókba való felvételükkel adhatja meg a meglévő felhasználóknak. A DEM-felhasználó által regisztrált valamennyi eszköz egyetlen Intune-licencet használ. További információt az [Eszközök regisztrálása a készülékregisztrációs program segítségével](device-enrollment-manager-enroll.md) című témakörben találhat.

