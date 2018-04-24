---
title: A Windows kiadásfrissítési szabályzatának beállításai
description: Ismerje meg, hogyan frissíthet automatikusan Windows 10-eszközt más verzióra az Intune segítségével.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 04/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99c0ef47ad8f143ef9bd1d6dbfff9c94fb154007
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>A Windows kiadásfrissítési házirendjének beállításai a Microsoft Intune-ban

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

A Microsoft Intune **kiadásfrissítési házirendje** lehetővé teszi az alábbi Windows 10-verziók valamelyikét futtató eszközök más verzióra történő automatikus frissítését:
* Windows 10 asztali verzió
* Windows 10 Holographic
* Windows 10 mobil verzió

Az alábbi verziófrissítési útvonalak támogatottak:
- Windows 10 Próról Windows 10 Enterprise-ra
- Windows 10 Home-ról Windows 10 Educationre
- Windows 10 Mobile-ról Windows 10 Mobile Enterprise-ra
- Windows 10 Holographic Próról Windows 10 Holographic Enterprise-ra

## <a name="before-you-start"></a>Előkészületek
Az eszközök legújabb verzióra történő frissítésének megkezdése előtt szüksége lesz a következők valamelyikére:
* Termékkulcsra, amely érvényes a Windows új verziójának – a házirend céljaként meghatározott összes eszközre történő – telepítéséhez (a Windows 10 asztali verziója esetén). Többször használható aktiválási kulcsokat (MAK) vagy kulcskezelő kiszolgálói (KMS) kulcsokat használhat.
**vagy** A Microsoft által kiadott licencfájlra, amely a Windows új verziójának – a szabályzat céljaként meghatározott összes eszközön történő – telepítéséhez szükséges licencelési adatokat tartalmazza (a Windows 10 Mobile és a Windows 10 Holographic verzió esetén).
* A célként meghatározott Windows 10 rendszerű eszközöket regisztrálni kell a Microsoft Intune-ban. A kiadásfrissítési szabályzat nem használható az Intune PC-ügyfélszoftvert futtató számítógépekkel.

## <a name="edition-upgrade-policy-settings"></a>Kiadásfrissítési házirend beállításai

|Beállítás neve|Részletek|
|-|-|
|**Név**|Adja meg a kiadásfrissítési házirend nevét.|
|**Leírás**|Megadhatja a házirend leírását, hogy könnyebb legyen azonosítani az Intune-konzolon (nem kötelező).
|**Frissítés erre a kiadásra**|A legördülő listából válassza ki a Windows 10 asztali verziónak, a Windows 10 Holographic vagy a Windows 10 Mobile rendszernek azt a verzióját, amelyre a megcélzott eszközöket frissíteni szeretné.
|**Termékkulcs**|Adja meg a Microsofttól kapott, minden megcélzott Windows 10 asztali eszköz frissítéséhez használható termékkulcsot.<br>Miután létrehozta a termékkulcsot tartalmazó házirendet, a termékkulcsot már nem szerkesztheti. Ennek oka a kulcs biztonsági okokból történő elrejtése. Ha módosítani szeretné a termékkulcsot, a teljes kulcsot újra meg kell adnia.
|**Licencfájl**|Válassza a **Tallózás** elemet, és jelölje ki a Microsofttól kapott, a Windows Holographic vagy Windows 10 Mobile azon kiadásának licencadatait tartalmazó licencfájlt, amelyre a célzott eszközöket frissíteni szeretné.

### <a name="see-also"></a>Lásd még:
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
