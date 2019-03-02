---
title: Apple MDM Push-tanúsítvány beszerzése az Intune-hoz
titlesuffix: ''
description: Apple MDM Push-tanúsítvány kezelése az Intune-nal iOS-eszközök beszerzése.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5719d1f662cc644377057b07dd632288a5c16552
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238013"
---
# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM push-tanúsítvány beszerzése

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune-nak Apple MDM Push-tanúsítványra van szüksége ahhoz, hogy felügyelni tudja az iOS- és macOS-eszközöket. Miután hozzáadta a tanúsítványt az Intune-hoz, felhasználói a következő segítségével regisztrálhatják az eszközeiket:

- A Céges portál alkalmazás.

- Az Apple tömeges regisztrálási módjai, mint a Készülékregisztrációs program, az Apple School Manager vagy az Apple Configurator.

A regisztrálási lehetőségekről további információt talál a [iOS-eszközök regisztrálásának módjai](enrollment-method-choose-ios.md) című témakörben.

Amikor a leküldéses tanúsítvány lejár, meg kell újítani. Megújításkor győződjön meg róla, hogy ugyanazt az Apple ID-t használja, mint a leküldéses tanúsítvány létrehozásakor.


## <a name="steps-to-get-your-certificate"></a>A tanúsítvány beszerzésének lépései
Az [Azure Portalon](https://portal.azure.com) válassza az **Eszközök regisztrálása** > **Apple-regisztráció** > **Apple MDM Push-tanúsítvány** elemet, majd kövesse az [Azure Portalon](https://portal.azure.com) a következő lépéseket.

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>1. lépés Engedélyezze a Microsoftnak a felhasználó- és eszközadatok Apple-nek való elküldését
Válassza az **Elfogadom.** lehetőséget az engedély megadásához.

![Az MDM Push-tanúsítvány konfigurálása képernyő az MDM Push beállítását megelőzően.](./media/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>2. lépés Töltse le az Apple MDM push-tanúsítvány létrehozásához szükséges Intune tanúsítvány-aláírási kérelmet
Válassza a **CSR letöltése** lehetőséget a kérelemfájl letöltéséhez és helyi mentéséhez. A fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.

  ### <a name="step-3-create-an-apple-mdm-push-certificate"></a>3. lépés. Apple MDM push-tanúsítvány létrehozása
Válassza az **MDM push-tanúsítvány létrehozása** lehetőséget az Apple Push Certificates Portal webhely megnyitásához. A céges Apple-azonosítójával való bejelentkezés után kattintson a **Tanúsítvány létrehozása** lehetőségre. Válassza a **Fájl kiválasztása** elemet, keresse meg a tanúsítvány-aláírási kérelem fájlját, majd válassza a **Feltöltés** lehetőséget. A tanúsítvány .pem kiterjesztésű fájljának letöltéséhez a megerősítés lapon válassza a **Letöltés** elemet, és mentse a fájlt helyileg.

> [!NOTE]
> A tanúsítványt a rendszer ahhoz az Apple-azonosítóhoz társítja, amely létrehozta azt. Ajánlott eljárásként használjon céges Apple ID-t kezelési feladatokhoz, és ügyeljen rá, hogy a postafiókot egy terjesztési listához hasonlóan többen figyelik. Soha ne használjon személyes Apple-azonosítót.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>4. lépés. Adja meg az Apple MDM Push-tanúsítvány létrehozásához használt Apple ID azonosítót
Jegyezze fel az azonosítót, hogy ne feledje a tanúsítványt időben megújítani.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>5. lépés. Tallózással keresse meg a fájlt az Apple MDM push-tanúsítvány feltöltéséhez
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az Apple-eszközöket.

## <a name="renew-apple-mdm-push-certificate"></a>Apple MDM push-tanúsítvány megújítása
Az Apple MDM push-tanúsítvány egy évig érvényes, és az iOS és macOS eszközkezelés karbantartásához évente meg kell újítani. Ha a tanúsítvány lejár, a regisztrált Apple-eszközöket nem lehet elérni.

A tanúsítványt a rendszer ahhoz az Apple-azonosítóhoz társítja, amely létrehozta azt. Az MDM push-tanúsítványt ugyanazzal az Apple-azonosítóval kell megújítani, amellyel létrehozták.

1. Az [Azure Portalon](https://portal.azure.com) válassza az **Eszközök regisztrálása** > **Apple-regisztráció**, majd az **Apple MDM Push-tanúsítvány** lehetőséget a Részletek területen.
2. Válassza a **CSR letöltése** lehetőséget a kérelemfájl letöltéséhez és helyi mentéséhez. A fájl a megbízhatósági kapcsolat tanúsítványának Apple Push Certificates portálról való beszerzésére szolgál.
3. Válassza az **MDM push-tanúsítvány létrehozása** lehetőséget az Apple Push Certificates Portal webhely megnyitásához. Keresse meg a megújítani kívánt tanúsítványt, és kattintson a **Megújítás** elemre.
4. A **Push-tanúsítvány megújítása** képernyőn adjon meg jegyzeteket a tanúsítvány későbbi azonosításának megkönnyítése érdekében, majd a **Fájl kiválasztása** elemet választva keresse meg a letöltött új kérelemfájlt, és válassza a **Feltöltés** lehetőséget.
   > [!TIP]
   > A tanúsítványok a felhasználóazonosító alapján azonosíthatók. A felhasználóazonosító GUID részének azonosításához tekintse meg a **Tulajdonos azonosítóját** a tanúsítvány részletei között. Vagy egy regisztrált iOS-eszközön lépjen a **Beállítások** > **Általános** > **Eszköz** **Felügyelet** > **Felügyeleti profil** > **További részletek** > **Felügyeleti profil** részre. A **Téma** elnevezésű második sori elem tartalmazza az egyedi GUID azonosítót, amelyet megfeleltethet az Apple Push Certificates portál tanúsítványának.
 
6. A **Megerősítés** képernyőn kattintson a **Letöltés** elemre, majd mentse helyileg a .pem fájlt.
7. Az [Azure Portalon](https://portal.azure.com) válassza az **Apple MDM Push-tanúsítvány** böngészőikont, válassza ki az Apple portáljáról letöltött .pem-fájlt, majd válassza a **Feltöltés** lehetőséget.

Az Apple MDM push-tanúsítvány ekkor **Aktív** állapotba kerül, és 365 napig érvényben marad.
