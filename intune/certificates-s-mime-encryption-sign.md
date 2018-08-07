---
title: S/MIME e-mail-aláírás és -titkosítás – Azure | Micrososft Docs
description: S/MIME használata vagy engedélyezése e-mailek aláírásához és titkosításához a Microsoft Intune-ban
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0eac3c1d6739ca70e485b0327e3257ba8d32d2b
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321653"
---
# <a name="smime-email-signing-and-encryption-in-intune"></a>S/MIME e-mail-aláírás és -titkosítás az Intune-ban

Az S/MIME egy újabb biztonsági szintet nyújt a titkosítást és visszafejtést használó e-mail-kommunikációhoz. A Microsoft Intune iOS, Windows, Windows Phone, Android és macOS rendszerű mobileszközökön képes S/MIME használatára az e-mailek aláírásához és titkosításához.

iOS-eszközökön létrehozható egy Intune által felügyelt e-mail-profil, amely S/MIME és tanúsítványok használatával írja alá és titkosítja a bejövő és kimenő e-maileket. Más platformokon az S/MIME lehet támogatott vagy nem támogatott. Ha támogatott, akkor telepíthetők S/MIME-aláírást és -titkosítást használó tanúsítványok. Ilyenkor a végfelhasználók saját levelezőalkalmazásukban engedélyezhetik az S/MIME használatát.

Az S/MIME e-mail-aláírást és -titkosítást az [S/MIME üzenetek aláírásához és titkosításához](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) című cikk ismerteti bővebben.

## <a name="signing-certificates"></a>Aláíró tanúsítványok

Az aláíráshoz használt tanúsítványok lehetővé teszik, hogy az ügyfél e-mail-alkalmazás biztonságosan kommunikáljon a levelezési kiszolgálóval.

Aláíró tanúsítványok használatához hozzon létre egy aláírásra szolgáló sablont a hitelesítésszolgáltatónál. A Microsoft Active Directory hitelesítésszolgáltatóhoz [A kiszolgálói tanúsítvány-sablon konfigurálása](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) című cikk ismerteti a tanúsítványsablonok létrehozásának lépéseit.

Az Intune-beli aláíró tanúsítványok PKCS-tanúsítványokat használnak. A [PKCS-tanúsítványok konfigurálása és használata](certficates-pfx-configure.md) című cikk leírja, hogyan telepíthet és használhat PKCS-tanúsítványokat Intune-környezetében. Ezek a lépések az alábbiak:

- A PKCS-tanúsítványkérelmek támogatásához töltse le és telepítse a Microsoft Intune Tanúsítvány-összekötőt.
- Hozzon létre egy megbízható főtanúsítvány-profilt eszközeihez. E lépés során megbízható főtanúsítványokat és köztes tanúsítványokat is használni kell a hitelesítésszolgáltatónál, majd üzembe kell helyezni a profilt az eszközökön.
- Hozzon létre egy PKCS-tanúsítványprofilt az elkészült tanúsítványsablon használatával. Ez a profil adja ki az aláíró tanúsítványokat az eszközöknek, és helyezi üzembe a PKCS-tanúsítványprofilt az eszközökön.

Aláíró tanúsítvány egy adott felhasználó számára is importálható. Az aláíró tanúsítvány a felhasználó által regisztrált összes eszközön telepítve lesz. A tanúsítványok Intune-ba való importálásához használja [a GitHubon elérhető PowerShell-parancsmagokat](https://github.com/Microsoft/Intune-Resource-Access). Az Intune-ba importált PKCS-tanúsítványok e-mail-aláíráshoz való üzembe helyezéséhez kövesse a [PKCS-tanúsítványok konfigurálása és használata az Intune-nal](certficates-pfx-configure.md) című témakörben leírt lépéseket. Ezek a lépések az alábbiak:

- Töltse le és telepítse a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőt. Ez az összekötő juttatja el az importált PKCS-tanúsítványokat az eszközökre.
- Importáljon S/MIME e-mail-aláíró tanúsítványokat az Intune-ba.
- Hozzon létre egy importált PKCS-tanúsítványprofilt. Ez a profil juttatja el az importált PKCS-tanúsítványokat a megfelelő felhasználók eszközeire.

## <a name="encryption-certificates"></a>Titkosítási tanúsítványok

A titkosításhoz használt tanúsítványok biztosítják, hogy a titkosított e-mailt csak az a címzett tudja visszafejteni, akinek szánták. A S/MIME-titkosítás az e-mail-kommunikációban használható újabb biztonsági réteg.

Amikor titkosított e-mailt küld egy másik felhasználónak, beszerzi a címzett titkosítási tanúsítványának nyilvános kulcsát, és titkosítja a küldeni kívánt e-mailt. A címzett a titkos kulcsával oldja fel az e-mail titkosítását az eszközén. A felhasználók az e-mailek titkosításához használt korábbi tanúsítványokkal is rendelkezhetnek. Az e-mailek sikeres visszafejtéséhez minden ilyen tanúsítványnak telepítve kell lennie az adott felhasználó összes eszközén.

Az e-mail-titkosítási tanúsítványokat ajánlott nem az Intune-ban létrehozni. Bár az Intune támogatja titkosítást támogató PKCS-tanúsítványok kiállítását, az Intune eszközönként egyedi tanúsítványokat hoz létre. Az eszközönként egyedi tanúsítvány nem ideális S/MIME-titkosítás esetén, amikor a titkosítási tanúsítványnak a felhasználó minden eszközén meg kellene lennie.

S/MIME-tanúsítványok Intune-nal való üzembe helyezéséhez egy felhasználó összes titkosítási tanúsítványát importálnia kell az Intune-ba. Az Intune ezután az összes tanúsítványt üzembe helyezi a felhasználó által regisztrált összes eszközön. A tanúsítványok Intune-ba való importálásához használja [a GitHubon elérhető PowerShell-parancsmagokat](https://github.com/Microsoft/Intune-Resource-Access).

Az Intune-ba importált PKCS-tanúsítványok e-mail-titkosításhoz való üzembe helyezéséhez kövesse a [PKCS-tanúsítványok konfigurálása és használata az Intune-nal](certficates-pfx-configure.md) című témakörben leírt lépéseket. Ezek a lépések az alábbiak:

- Töltse le és telepítse a Microsoft Intune-hoz készült PFX tanúsítvány-összekötőt. Ez az összekötő juttatja el az importált PKCS-tanúsítványokat az eszközökre.
- Importáljon S/MIME e-mail-titkosítási tanúsítványokat az Intune-ba.
- Hozzon létre egy importált PKCS-tanúsítványprofilt. Ez a profil juttatja el az importált PKCS-tanúsítványokat a megfelelő felhasználók eszközeire.

 > [!NOTE]
 > Az importált S/MIME titkosítási tanúsítványok el lesznek távolítva az Intune-ból, ha törlik a céges adatokat, vagy ha a felhasználók regisztrációját törlik a felügyeleti rendszerben. A tanúsítványok azonban nem lesznek visszavonva a hitelesítésszolgáltatónál.

## <a name="smime-email-profiles"></a>S/MIME e-mail-profilok

S/MIME aláíró és titkosítási tanúsítványprofilok létrehozása után [engedélyezheti az S/MIME használatát az iOS-natív levelezéshez](email-settings-ios.md).