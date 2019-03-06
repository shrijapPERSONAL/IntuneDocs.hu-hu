---
title: Aláírása és titkosítása e-mailt az S/MIME - a Microsoft Intune – Azure |} Micrososft Docs
description: Útmutató az e-mail digitális tanúsítványokat a Microsoft Intune-ban és e-mailek eszközökön titkosítására. Ezek a tanúsítványok S/MIME nevezik, és eszközkonfigurációs profilok használatával konfigurálhatók. Aláírás és titkosítás tanúsítványok PKCS, vagy privát tanúsítványok, és a tanúsítványok importálása egy összekötő használatával.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e288cdf426f2fda2638e49350515182107d9bba
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389592"
---
# <a name="smime-overview-to-sign-and-encrypt-email-in-intune"></a>S/MIME áttekintése és titkosítására e-mailt az Intune-ban

E-mail-tanúsítványok, más néven az S/MIME-tanúsítvány, adja meg az extra biztonsági az e-mail-üzeneteket, a titkosítás és visszafejtés. A Microsoft Intune S/MIME-tanúsítványok használatával aláírása és titkosítása e-mailt a következő platformot futtató mobileszközökre:

- Android
- iOS
- macOS
- Windows 10 és újabb
- Windows Phone

iOS-eszközökön létrehozható egy Intune által felügyelt e-mail-profil, amely S/MIME és tanúsítványok használatával írja alá és titkosítja a bejövő és kimenő e-maileket. Más platformokon az S/MIME lehet támogatott vagy nem támogatott. Támogatott, ha telepíti az S/MIME-aláírásra és titkosításra használt tanúsítványok. Ezután a végfelhasználó lehetővé teszi az e-mail alkalmazás S/MIME.

S/MIME e-mail aláírási és titkosítási az Exchange kiszolgálóval kapcsolatos további információkért lásd: [S/MIME-üzenet aláíráshoz és titkosításhoz](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

Ez a cikk áttekintést és e-mailek, az eszközök titkosítására S/MIME-tanúsítványok használatával.

## <a name="signing-certificates"></a>Aláíró tanúsítványok

Az aláíráshoz használt tanúsítványok lehetővé teszik, hogy az ügyfél e-mail-alkalmazás biztonságosan kommunikáljon a levelezési kiszolgálóval.

Aláíró tanúsítványok használatához hozzon létre egy sablont a a hitelesítésszolgáltató (CA), amely aláírási összpontosít. A Microsoft Active Directory hitelesítésszolgáltatóhoz [A kiszolgálói tanúsítvány-sablon konfigurálása](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) című cikk ismerteti a tanúsítványsablonok létrehozásának lépéseit.

Az Intune-beli aláíró tanúsítványok PKCS-tanúsítványokat használnak. A [PKCS-tanúsítványok konfigurálása és használata](certficates-pfx-configure.md) című cikk leírja, hogyan telepíthet és használhat PKCS-tanúsítványokat Intune-környezetében. Ezek a lépések az alábbiak:

- A PKCS-tanúsítványkérelmek támogatásához töltse le és telepítse a Microsoft Intune Tanúsítvány-összekötőt.
- Hozzon létre egy megbízható főtanúsítvány-profilt eszközeihez. E lépés során megbízható főtanúsítványokat és köztes tanúsítványokat is használni kell a hitelesítésszolgáltatónál, majd üzembe kell helyezni a profilt az eszközökön.
- Hozzon létre egy PKCS-tanúsítványprofilt az elkészült tanúsítványsablon használatával. Ez a profil adja ki az aláíró tanúsítványokat az eszközöknek, és helyezi üzembe a PKCS-tanúsítványprofilt az eszközökön.

Aláíró tanúsítvány egy adott felhasználó számára is importálható. Az aláíró tanúsítvány van üzembe helyezve, bármilyen eszközön, amely a felhasználó regisztrál. A tanúsítványok Intune-ba való importálásához használja [a GitHubon elérhető PowerShell-parancsmagokat](https://github.com/Microsoft/Intune-Resource-Access). Az Intune-ba importált PKCS-tanúsítványok e-mail-aláíráshoz való üzembe helyezéséhez kövesse a [PKCS-tanúsítványok konfigurálása és használata az Intune-nal](certficates-pfx-configure.md) című témakörben leírt lépéseket. Ezek a lépések az alábbiak:

- Töltse le és telepítse a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőt. Ez az összekötő juttatja el az importált PKCS-tanúsítványokat az eszközökre.
- Importáljon S/MIME e-mail-aláíró tanúsítványokat az Intune-ba.
- Hozzon létre egy importált PKCS-tanúsítványprofilt. Ez a profil juttatja el az importált PKCS-tanúsítványokat a megfelelő felhasználók eszközeire.

## <a name="encryption-certificates"></a>Titkosítási tanúsítványok

A titkosításhoz használt tanúsítványok biztosítják, hogy a titkosított e-mailt csak az a címzett tudja visszafejteni, akinek szánták. A S/MIME-titkosítás az e-mail-kommunikációban használható újabb biztonsági réteg.

Amikor titkosított e-mailt küld egy másik felhasználónak, beszerzi a címzett titkosítási tanúsítványának nyilvános kulcsát, és titkosítja a küldeni kívánt e-mailt. A címzett a titkos kulcsával oldja fel az e-mail titkosítását az eszközén. A felhasználók az e-mailek titkosításához használt korábbi tanúsítványokkal is rendelkezhetnek. Az e-mailek sikeres visszafejtéséhez minden ilyen tanúsítványnak telepítve kell lennie az adott felhasználó összes eszközén.

Az e-mail-titkosítási tanúsítványokat ajánlott nem az Intune-ban létrehozni. Bár az Intune támogatja titkosítást támogató PKCS-tanúsítványok kiállítását, az Intune eszközönként egyedi tanúsítványokat hoz létre. Az eszközönként egyedi tanúsítvány nem ideális S/MIME-titkosítás esetén, amikor a titkosítási tanúsítványnak a felhasználó minden eszközén meg kellene lennie.

S/MIME-tanúsítványok Intune-nal való üzembe helyezéséhez egy felhasználó összes titkosítási tanúsítványát importálnia kell az Intune-ba. Az Intune majd helyezünk üzembe minden tanúsítványok minden olyan felhasználó által regisztrált eszköz. A tanúsítványok Intune-ba való importálásához használja [a GitHubon elérhető PowerShell-parancsmagokat](https://github.com/Microsoft/Intune-Resource-Access).

Az Intune-ba importált PKCS-tanúsítványok e-mail-titkosításhoz való üzembe helyezéséhez kövesse a [PKCS-tanúsítványok konfigurálása és használata az Intune-nal](certficates-pfx-configure.md) című témakörben leírt lépéseket. Ezek a lépések az alábbiak:

- Töltse le és telepítse a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőt. Ez az összekötő juttatja el az importált PKCS-tanúsítványokat az eszközökre.
- Importáljon S/MIME e-mail-titkosítási tanúsítványokat az Intune-ba.
- Hozzon létre egy importált PKCS-tanúsítványprofilt. Ez a profil juttatja el az importált PKCS-tanúsítványokat a megfelelő felhasználók eszközeire.

 > [!NOTE]
 > Az importált S/MIME titkosítási tanúsítványok el lesznek távolítva az Intune-ból, ha törlik a céges adatokat, vagy ha a felhasználók regisztrációját törlik a felügyeleti rendszerben. A tanúsítványok azonban nem lesznek visszavonva a hitelesítésszolgáltatónál.

## <a name="smime-email-profiles"></a>S/MIME e-mail-profilok

S/MIME aláíró és titkosítási tanúsítványprofilok létrehozása után [engedélyezheti az S/MIME használatát az iOS-natív levelezéshez](email-settings-ios.md).

## <a name="next-steps"></a>További lépések

- [SCEP-tanúsítványok használata](certificates-scep-configure.md)
- [PKCS-tanúsítványok használata](certficates-pfx-configure.md)
- [A partner hitelesítésszolgáltató használata](certificate-authority-add-scep-overview.md)
- [Adja ki a PKCS-tanúsítványok Symantec PKI manager webszolgáltatás](certificates-symantec-configure.md)
