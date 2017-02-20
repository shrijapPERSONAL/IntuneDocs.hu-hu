---
title: "iOS-eszközök Intune-ban való regisztrálási módjának kiválasztása |Azure-beli Intune – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: Útmutató iOS-eszközök Microsoft Intune-ban való regisztrációjának beállításához"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: c228601451b33238d0f6929987dcdec3a5e56e8d


---

# <a name="choose-how-to-enroll-ios-devices"></a>iOS-eszközök regisztrálási módjának kiválasztása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ez a témakör bemutatja az iOS-eszközök regisztrálására használható módszereket és a regisztráció előfeltételeit.

Az alábbi információk alapján döntheti el, hogy milyen módszerrel regisztrálja az iOS-eszközöket. A következő eljárások a BYOD kivételével mind a vállalati tulajdonban lévő eszközök regisztrálására szolgálnak.

**Előfeltétel:** [Egy Apple Push Notification szolgáltatásbeli tanúsítvány](get-an-apple-mdm-push-certificate.md).

## <a name="user-owned-ios-devices-byod"></a>A felhasználó tulajdonában lévő iOS-eszközök (BYOD)

Ha a felhasználók saját eszközeiket szeretnék használni (BYOD), számukra az a regisztrálás egyetlen módja, hogy letöltik az iOS Céges portál alkalmazást az Alkalmazás-áruházból, majd követik az alkalmazástól kapott utasításokat. A regisztrációt követően a felhasználók kapcsolódhatnak a vállalat hálózatához, csatlakozhatnak a tartományhoz vagy az Azure Active Directoryhoz, és hozzáférnek a vállalati erőforrásokhoz.

## <a name="apple-configurator"></a>Apple Configurator

Az iOS-eszközök egy vállalati regisztrációs profil exportálásával, majd a mobileszközöknek egy [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) eszközt futtató Mac számítógéphez való csatlakoztatásával regisztrálhatók. Az Apple Configurator a regisztráció két formáját támogatja:

- **Regisztrálás a Beállítási asszisztenssel**: Gyári alaphelyzetbe állítja az eszközt, és felkészíti a beállításhoz az új felhasználó számára. Ennél a módszernél a rendszergazdának a regisztráció előkonfigurálásához csatlakoztatnia kell az iOS-eszközt USB-kapcsolaton keresztül egy Apple Configuratort futtató Mac számítógéphez. Az eszközöket ekkor el kell juttatni a felhasználókhoz, akik elindítják a Beállítási asszisztenst. A folyamat konfigurálja az eszközt a felhasználók munkahelyi vagy iskolai azonosítójával, és elvégzi a regisztrációt. További információt az [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md) című témakörben találhat.

- **Közvetlen regisztrálás**: Létrejön egy Apple Configurator-kompatibilis fájl, amely az eszköz előkészítésez szükséges. A regisztrált eszköz nincs gyári alaphelyzetbe állítva, és egyetlen felhasználóhoz sem kapcsolódik. Az eszközök regisztrálásához a rendszergazdának csatlakoztatnia kell az iOS-eszközt USB-kapcsolaton keresztül egy Apple Configuratort futtató Mac számítógéphez. További információt az [iOS-eszközök közvetlen regisztrálása az Apple Configurator használatával](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md) című témakörben találhat.

## <a name="use-the-device-enrollment-program-dep"></a>A Device Enrollment Program (DEP) használata

A DEP a DEP-en keresztül megvásárolt eszközökre egy regisztrációs profilt telepít. Amikor a felhasználó a Beállítási asszisztenst futtatja az eszközön, az eszköz regisztrációja az Intune-ban rögzül. A DEP programon keresztül regisztrált eszközök regisztrációját a felhasználók nem törölhetik. További információt az [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](enroll-ios-devices-using-device-enrollment-program.md) című témakörben találhat.

## <a name="use-the-device-enrollment-manager-dem"></a>A készülékregisztráció-kezelő (DEM) használata
A készülékregisztráció-kezelő egyfajta felhasználói fiók, amely legfeljebb 1000 eszközt regisztrálhat és kezelhet. Ezt a lehetőséget a DEM-fiókba való felvételükkel adhatja meg a meglévő felhasználóknak. A DEM-felhasználó által regisztrált valamennyi eszköz egyetlen Intune-licencet használ. További információt az [Eszközök regisztrálása a készülékregisztrációs program segítségével](enroll-devices-using-device-enrollment-manager.md) című témakörben találhat.



<!--HONumber=Feb17_HO1-->


