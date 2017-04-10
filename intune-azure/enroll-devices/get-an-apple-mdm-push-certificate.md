---
title: "Apple MDM push-tanúsítvány beszerzése"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Az Apple MDM Push-tanúsítvány beszerzéséhez szükséges lépések ismertetése az iOS-eszközök Intune-os felügyeletéhez."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 82585886bb053d5b6b5981f61d0337fc6feffea4
ms.openlocfilehash: b26d66d557e084b5b328aec2222c50c2db254bf7
ms.lasthandoff: 03/14/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM push-tanúsítvány beszerzése

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune lehetőséget nyújt az iPadek, iPhone-ok és Mac számítógépek mobileszköz-felügyeletére (MDM), és hozzáférést biztosít a felhasználóknak a vállalati e-mailjeikhez és alkalmazásaikhoz. Az Intune-nak MDM Push-tanúsítványra van szüksége ahhoz, hogy felügyelni tudja az iOS-es és Mac eszközöket. Miután hozzáadta a tanúsítványt az Intune-hoz, felhasználói telepíthetik a Céges portál alkalmazást az eszközeik regisztrálásához. Az Apple Device Enrollment Programmal a vállalati tulajdonú iOS-eszközökre is beállíthat eszközfelügyeletet, vagy többek között az Apple Configurator használatával is regisztrálhatja az eszközöket. A regisztrálási lehetőségekről további információt talál a [iOS-eszközök regisztrálásának módjai](https://docs.microsoft.com/intune-azure/enroll-devices/choose-ios-enrollment-method) című témakörben.

## <a name="steps-to-get-your-certificate"></a>A tanúsítvány beszerzésének lépései
Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Válassza az Intune panelen az **Eszközök regisztrálása** > **Apple-regisztráció** **Apple MDM Push-tanúsítvány** elemet, majd kövesse az Azure Portal számozott lépéseit (alább láthatók).

**1. lépés Töltse le az Apple MDM push-tanúsítvány létrehozásához szükséges Intune tanúsítvány-aláírási kérelmet.**<br>
Válassza a **CSR letöltése** lehetőséget a .CSR kiterjesztésű fájl letöltéséhez és helyi mentéséhez. A .csr fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.

**2. lépés Apple MDM push-tanúsítvány létrehozása**<br>
Válassza az **MDM push-tanúsítvány létrehozása** lehetőséget az Apple Push Certificates Portal webhely megnyitásához. A céges Apple-azonosítójával való bejelentkezés után hozhatja létre a leküldéses tanúsítványt a .csr kiterjesztésű fájllal. Az Apple Push Certificates portál **Upload** (Feltöltés) gombjára való kattintás után egy .json kiterjesztésű fájlt fog kapni. Használja ezt a fájlt a leküldéses tanúsítványhoz. Fejezze be a letöltést, térjen vissza az Apple Push Certificates portálra a Certificates for Third-Party Servers (Tanúsítványok külső kiszolgálóknak) lapra, majd kattintson a **Download** (Letöltés) elemre. Töltse le a leküldéses tanúsítványt (.pem-fájlt), és mentse helyileg a fájlt.
Megjegyzés

**3. lépés Adja meg az Apple MDM Push-tanúsítvány létrehozásához használt Apple ID azonosítót.**

**4. lépés Tallózással keresse meg a fájlt az Apple MDM push-tanúsítvány feltöltéséhez.**<br>
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével.

