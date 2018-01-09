---
title: "Apple MDM push-tanúsítvány beszerzése"
titlesuffix: Azure portal
description: "Az Apple MDM Push-tanúsítvány beszerzéséhez szükséges lépések ismertetése az iOS-eszközök Intune-os felügyeletéhez."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b67c2cb238d354ccd9801ec0b5c9f8ccb49c6715
ms.sourcegitcommit: 9fabf1a8db53842f7b00762374de5b137158ee25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/22/2017
---
# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM push-tanúsítvány beszerzése

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune lehetőséget nyújt az iPadek, iPhone-ok és Mac számítógépek mobileszköz-felügyeletére (MDM), és hozzáférést biztosít a felhasználóknak a vállalati e-mailjeikhez és alkalmazásaikhoz. Az Intune-nak MDM Push-tanúsítványra van szüksége ahhoz, hogy felügyelni tudja az iOS-es és Mac eszközöket. Miután hozzáadta a tanúsítványt az Intune-hoz, felhasználói telepíthetik a Céges portál alkalmazást az eszközeik regisztrálásához. Az Apple Device Enrollment Programmal a vállalati tulajdonú iOS-eszközökre is beállíthat eszközfelügyeletet, vagy többek között az Apple Configurator használatával is regisztrálhatja az eszközöket. A regisztrálási lehetőségekről további információt talál a [iOS-eszközök regisztrálásának módjai](enrollment-method-choose-ios.md) című témakörben.

## <a name="steps-to-get-your-certificate"></a>A tanúsítvány beszerzésének lépései
Az Azure Portalon válassza az **Eszközök regisztrálása** > **Apple-regisztráció** **Apple MDM Push-tanúsítvány** elemet, majd kövesse az Azure Portalon a következő lépéseket.

**1. lépés Töltse le az Apple MDM push-tanúsítvány létrehozásához szükséges Intune tanúsítvány-aláírási kérelmet.**<br>
Válassza a **CSR letöltése** lehetőséget a kérelemfájl letöltéséhez és helyi mentéséhez. A fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.

  ![Képernyőfelvétel, amely az MDM push-tanúsítvány konfigurálása képernyőt ábrázolja az MDM-push beállítását megelőzően.](./media/create-mdm-push-certificate.png)

**2. lépés Apple MDM push-tanúsítvány létrehozása**<br>
Válassza az **MDM push-tanúsítvány létrehozása** lehetőséget az Apple Push Certificates Portal webhely megnyitásához. A céges Apple-azonosítójával való bejelentkezés után kattintson a **Tanúsítvány létrehozása** lehetőségre. Válassza a **Fájl kiválasztása** elemet, keresse meg a tanúsítvány-aláírási kérelem fájlját, majd válassza a **Feltöltés** lehetőséget. A tanúsítvány .pem kiterjesztésű fájljának letöltéséhez a megerősítés lapon válassza a **Letöltés** elemet, és mentse a fájlt helyileg.

> [!NOTE]
> A tanúsítványt a rendszer ahhoz az Apple-azonosítóhoz társítja, amely létrehozta azt. Az ajánlott eljárás szerint a felügyeleti feladatokhoz vállalati Apple-azonosítót használjon. Soha ne használjon személyes Apple-azonosítót.

**3. lépés Adja meg az Apple MDM Push-tanúsítvány létrehozásához használt Apple ID azonosítót.**<br>
Jegyezze fel az azonosítót, hogy ne feledje a tanúsítványt időben megújítani.

**4. lépés Tallózással keresse meg a fájlt az Apple MDM push-tanúsítvány feltöltéséhez.**<br>
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az Apple-eszközöket.

## <a name="renew-apple-mdm-push-certificate"></a>Apple MDM push-tanúsítvány megújítása
Az Apple MDM push-tanúsítvány egy évig érvényes, és az iOS és macOS eszközkezelés karbantartásához évente meg kell újítani. Ha a tanúsítvány lejár, a regisztrált Apple-eszközöket nem lehet elérni.

A tanúsítványt a rendszer ahhoz az Apple-azonosítóhoz társítja, amely létrehozta azt. Az MDM push-tanúsítványt ugyanazzal az Apple-azonosítóval kell megújítani, amellyel létrehozták.

1. Az Azure Portalon válassza az **Eszközök regisztrálása** > **Apple-regisztráció**, majd az **Apple MDM Push-tanúsítvány** elemet.
2. Válassza a **CSR letöltése** lehetőséget a kérelemfájl letöltéséhez és helyi mentéséhez. A fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.
3. Keresse meg a megújítani kívánt tanúsítványt, és kattintson a **Megújítás** elemre.
4. A**push-tanúsítvány megújítása** képernyőn adjon meg jegyzeteket a tanúsítvány későbbi azonosításának megkönnyítése érdekében, majd a **Fájl kiválasztása** elemre kattintva keresse meg a letöltött új kérelemfájlt, és kattintson a **Feltöltés** elemre.
5. A **Megerősítés** képernyőn kattintson a **Letöltés** elemre, majd mentse helyileg a .pem fájlt.
6. Az Azure Portalon kattintson az **Apple MDM push-tanúsítvány** böngészőikonra, válassza ki az Apple portáljáról letöltött .pem-fájlt, majd válassza a **Feltöltés** lehetőséget.

Az Apple MDM push-tanúsítvány ekkor **Aktív** állapotba kerül, és 365 napig érvényben marad.
