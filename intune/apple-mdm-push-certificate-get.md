---
title: "Apple MDM push-tanúsítvány beszerzése"
titleSuffix: Intune on Azure
description: "Az Apple MDM Push-tanúsítvány beszerzéséhez szükséges lépések ismertetése az iOS-eszközök Intune-os felügyeletéhez."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 915b432ed32565e820e16a65932fcdeac00d9bc3
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2017
---
# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM push-tanúsítvány beszerzése

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune lehetőséget nyújt az iPadek, iPhone-ok és Mac számítógépek mobileszköz-felügyeletére (MDM), és hozzáférést biztosít a felhasználóknak a vállalati e-mailjeikhez és alkalmazásaikhoz. Az Intune-nak MDM Push-tanúsítványra van szüksége ahhoz, hogy felügyelni tudja az iOS-es és Mac eszközöket. Miután hozzáadta a tanúsítványt az Intune-hoz, felhasználói telepíthetik a Céges portál alkalmazást az eszközeik regisztrálásához. Az Apple Device Enrollment Programmal a vállalati tulajdonú iOS-eszközökre is beállíthat eszközfelügyeletet, vagy többek között az Apple Configurator használatával is regisztrálhatja az eszközöket. A regisztrálási lehetőségekről további információt talál a [iOS-eszközök regisztrálásának módjai](enrollment-method-choose-ios.md) című témakörben.

## <a name="steps-to-get-your-certificate"></a>A tanúsítvány beszerzésének lépései
Az Intune-portálon válassza az **Eszközök regisztrálása** > **Apple-regisztráció** **Apple MDM Push-tanúsítvány** elemet, majd kövesse az Azure Portalon a következő lépéseket.

**1. lépés Töltse le az Apple MDM push-tanúsítvány létrehozásához szükséges Intune tanúsítvány-aláírási kérelmet.**<br>
Válassza a **CSR letöltése** lehetőséget a kérelemfájl letöltéséhez és helyi mentéséhez. A fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.

  ![Képernyőfelvétel, amely az MDM push-tanúsítvány konfigurálása képernyőt ábrázolja az MDM-push beállítását megelőzően.](./media/create-mdm-push-certificate.png)

**2. lépés Apple MDM push-tanúsítvány létrehozása**<br>
Válassza az **MDM push-tanúsítvány létrehozása** lehetőséget az Apple Push Certificates Portal webhely megnyitásához. A céges Apple-azonosítójával való bejelentkezés után a kérelemfájllal hozhatja létre a leküldéses tanúsítványt. Az Apple Push Certificates portál **Upload** (Feltöltés) gombjára való kattintás után egy .json kiterjesztésű fájlt fog kapni. Használja ezt a fájlt a leküldéses tanúsítványhoz. Fejezze be a letöltést, térjen vissza az Apple Push Certificates portálra a Certificates for Third-Party Servers (Tanúsítványok külső kiszolgálóknak) lapra, majd kattintson a **Download** (Letöltés) elemre. Töltse le a leküldéses tanúsítványt (.pem-fájlt), és mentse helyileg a fájlt.

> [!NOTE]
> A tanúsítványt a rendszer ahhoz az Apple-azonosítóhoz társítja, amely létrehozta azt. Az ajánlott eljárás szerint a felügyeleti feladatokhoz vállalati Apple-azonosítót használjon. Soha ne használjon személyes Apple-azonosítót.

**3. lépés Adja meg az Apple MDM Push-tanúsítvány létrehozásához használt Apple ID azonosítót.**

**4. lépés Tallózással keresse meg a fájlt az Apple MDM push-tanúsítvány feltöltéséhez.**<br>
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével.

## <a name="renew-apple-mdm-push-certificate"></a>Apple MDM push-tanúsítvány megújítása
Az Apple MDM push-tanúsítvány egy évig érvényes, és az iOS és macOS eszközkezelés karbantartásához évente meg kell újítani. Ha a tanúsítvány lejár, a regisztrált Apple-eszközöket nem lehet elérni.

A tanúsítványt a rendszer ahhoz az Apple-azonosítóhoz társítja, amely létrehozta azt. Az MDM push-tanúsítványt ugyanazzal az Apple-azonosítóval kell megújítani, amellyel létrehozták.

> [!NOTE]
> A tanúsítványt a rendszer ahhoz az Apple-azonosítóhoz társítja, amely létrehozta azt. Az ajánlott eljárás szerint a felügyeleti feladatokhoz vállalati Apple-azonosítót használjon. Soha ne használjon személyes Apple-azonosítót.

1. Az Intune-portálon válassza az **Eszközök regisztrálása** > **Apple-regisztráció**, majd az **Apple MDM push-tanúsítvány** elemet.
2. Válassza a **CSR letöltése** lehetőséget a kérelemfájl letöltéséhez és helyi mentéséhez. A fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.
3. Keresse meg a megújítani kívánt tanúsítványt, és kattintson a **Megújítás** elemre.
4. A**push-tanúsítvány megújítása** képernyőn adjon meg jegyzeteket a tanúsítvány későbbi azonosításának megkönnyítése érdekében, majd a **Fájl kiválasztása** elemre kattintva keresse meg a letöltött új kérelemfájlt, és kattintson a **Feltöltés** elemre.
5. A **Megerősítés** képernyőn kattintson a **Letöltés** elemre, majd mentse helyileg a .pem fájlt.
6. Az Azure Intune portálon kattintson az **Apple MDM push-tanúsítvány** böngészőikonra, válassza ki az Apple portáljáról letöltött .pem fájlt, majd kattintson a **Feltöltés** elemre.

Az Apple MDM push-tanúsítvány ekkor **Aktív** állapotba kerül, és 365 napig érvényben marad.
