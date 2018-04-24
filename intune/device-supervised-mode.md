---
title: iOS-es felügyelt mód a Microsoft Intune-nal
titleSuffix: ''
description: Információ az iOS-es felügyelt mód bekapcsolásáról az Intune-ban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09b94ad2109c41ad02e8da7267690c31ba296bae
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="turn-on-ios-supervised-mode"></a>iOS-es felügyelt mód bekapcsolása


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Apple iOS-es felügyelt mód több lehetőséget biztosít a rendszergazdáknak Apple-eszközök kezelésénél, ami különösen a nagy méretekben üzembe helyezett vállalati tulajdonban lévő eszközök esetén hasznos. Például korlátozhatja az AirDropot, vagy letilthatja a felhasználók számára az eszköz nevének módosítását. A felügyelt módot megkövetelő beállítások listáját az [iOS-es eszközkorlátozási beállítások az Intune-ban](device-restrictions-ios.md) című témakörben találja.

Az Intune az Apple [készülékregisztrációs program (DEP)](device-enrollment-program-enroll-ios.md) keretében biztosít lehetőséget az eszközök felügyelt módú üzemeltetéséhez.

Az Apple [Adattartalom-beállítási referencia](http://help.apple.com/configurator/mac/2.4/#/cad5370d089) című cikkében megtalálja azoknak az Apple-vezérlőknek a listáját, amelyekhez felügyelt mód szükséges.

## <a name="turn-on-supervised-mode-during-enrollment"></a>Felügyelt mód bekapcsolása regisztrálás során

Az Intune-ban bekapcsolható az eszközökhöz felügyelt mód, amikor [Apple-regisztrációs profilokat hoz létre a DEP-beb](https://docs.microsoft.com/en-us/intune/device-enrollment-program-enroll-ios#create-an-apple-enrollment-profile). Ehhez az **Eszközfelügyeleti beállítások** területen jelölje be a **Felügyelt** jelölőnégyzetet.

## <a name="turn-on-supervised-mode-after-enrollment"></a>Felügyelt mód bekapcsolása regisztrálás után

Ha a regisztráció már megtörtént, az iOS-eszközt össze kell kötni egy Mac számítógéppel, és az [Apple Configuratort használva](apple-configurator-enroll-ios.md) engedélyezni kell rajta a felügyelt módot (ami alaphelyzetbe állítja az eszközt). Regisztráció után az Intune-ban nem lehetséges az eszközt felügyelt módra konfigurálni.

## <a name="identify-a-supervised-device"></a>Felügyelt eszköz azonosítása

Ha azt szeretné ellenőrizni, hogy felügyelt-e egy eszköz, nézze meg a zárolási képernyőt vagy a **Névjegy** oldalt:
- Az eszköz zárolási képernyőjén ez látható: **Ezt az iPhone-t a „Cég neve” felügyeli.**
- Az eszköz **Névjegy** oldalán pedig ez látható: **Ez egy felügyelt eszköz. A Cégnév figyelheti az internetes forgalmat és megállapíthatja a készülék helyét.**

## <a name="next-steps"></a>További lépések

További eszközfelügyeleti beállításokért lásd: [A Microsoft Intune-eszközfelügyelet ismertetése](device-management.md).
