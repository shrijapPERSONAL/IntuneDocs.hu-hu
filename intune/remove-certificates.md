---
title: SCEP- vagy PKCS-tanúsítványok eltávolítása a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: A rendszergazdák az összes adat törlésével, illetve kivonással távolíthatnak el tanúsítványokat a Microsoft Intune-ból. Vannak olyan forgatókönyvek, amelyek során a tanúsítványokat a rendszer automatikusan eltávolítja, például egy eszköz regisztrációjának törlésekor vagy egy megfelelőségi szabályzat eltávolításakor. Olyan forgatókönyvek is vannak, amelyek során a tanúsítványok automatikusan az eszközön maradnak, például az Intune-licenc elvesztésekor vagy eltávolításakor. Lásd az Android, az Android Enterprise, az iOS, a macOS és a Windows rendszerű eszközökre vonatkozó különféle módszereket.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e19df00a829d0cedb22210cd0ebe6b48c55229fe
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57392731"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>SCEP- vagy PKCS-tanúsítványok eltávolítása a Microsoft Intune-ban

A Microsoft Intune egyszerű tanúsítványigénylési protokoll (SCEP) és a nyilvános kulcs titkosítási szabványok (PKCS) tanúsítványokat is hozzáadhat az eszközökre. Ezek a tanúsítványok az eszköz [tartalmának törlése](devices-wipe.md#wipe) vagy az eszköz [kivonása](devices-wipe.md#retire) során is el is távolíthatók. 

Vannak olyan forgatókönyvek, amelyek során a rendszer automatikusan eltávolítja a tanúsítványokat, és olyanok is, amelyekben a tanúsítványok az eszközön maradnak. Ez a cikk néhány gyakori forgatókönyvet és azok PKCS- és SCEP-tanúsítványokra gyakorolt hatását mutatja be.

> [!NOTE]
> Távolítsa el, és a egy felhasználóhoz, aki folyamatban van, a tanúsítványok visszavonásához távolítva a helyszíni Active Directory vagy az Azure Active Directory (Azure AD), kövesse az alábbi lépéseket, sorrendben:
>
> 1. A felhasználó-eszköz kivonása vagy törlése.
> 2. Eltávolítja a felhasználót a helyszíni Active Directory vagy az Azure ad-ben.

## <a name="windows-devices"></a>Windows-eszközök

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.
- Az eszköz kikerül az Azure AD-csoportok.
- A tanúsítványprofil távolítja el a csoport-hozzárendelés.

Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
- A rendszergazda megváltozik, vagy frissíti az SCEP-profil.

Legfelső szintű tanúsítvány törlődik. Ha:
- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

SCEP-tanúsítványok *maradjon* az eszközön (tanúsítványok nem visszavont vagy eltávolítása) ha:
- A felhasználó elveszíti az Intune-licencet.
- A rendszergazda visszavonja az Intune-licencet.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

A PKCS-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

Legfelső szintű tanúsítvány törlődik. Ha:
- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

PKCS-tanúsítványok *maradjon* az eszközön (tanúsítványok nem visszavont vagy eltávolítása) ha:
- A felhasználó elveszíti az Intune-licencet.
- A rendszergazda visszavonja az Intune-licencet.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.
- A rendszergazda megváltozik, vagy a PKCS-profil frissítése.
- A tanúsítványprofil távolítja el a csoport-hozzárendelés.


## <a name="ios-devices"></a>iOS-eszközök

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.
- Az eszköz törlődik az Azure AD-csoportban.
- A tanúsítványprofil távolítja el a csoport-hozzárendelés.

Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
- A rendszergazda megváltozik, vagy frissíti az SCEP-profil.

Legfelső szintű tanúsítvány törlődik. Ha:
- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

SCEP-tanúsítványok *maradjon* az eszközön (tanúsítványok nem visszavont vagy eltávolítása) ha:
- A felhasználó elveszíti az Intune-licencet.
- A rendszergazda visszavonja az Intune-licencet.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

A PKCS-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

A PKCS-tanúsítvány eltávolítására a következő esetekben kerül sor:
- A tanúsítványprofil távolítja el a csoport-hozzárendelés.
  
Legfelső szintű tanúsítvány törlődik. Ha:
- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

PKCS-tanúsítványok *maradjon* az eszközön (tanúsítványok nem visszavont vagy eltávolítása) ha:
- A felhasználó elveszíti az Intune-licencet.
- A rendszergazda visszavonja az Intune-licencet.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.
- A rendszergazda megváltozik, vagy a PKCS-profil frissítése.

## <a name="android-knox-devices"></a>Android Knox-eszközök

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:
- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.

Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.
- Az eszköz kikerül az Azure AD-csoportok.
- A tanúsítványprofil távolítja el a csoport-hozzárendelés.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.
- A rendszergazda megváltozik, vagy frissíti az SCEP-profil.

Legfelső szintű tanúsítvány törlődik. Ha:
- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

SCEP-tanúsítványok *maradjon* az eszközön (tanúsítványok nem visszavont vagy eltávolítása) ha:
- A felhasználó elveszíti az Intune-licencet.
- A rendszergazda visszavonja az Intune-licencet.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

A PKCS-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

Legfelső szintű tanúsítvány törlődik. Ha:
- A felhasználó megszünteti.
- Egy rendszergazda a [törlési](devices-wipe.md#wipe) művelet.
- Egy rendszergazda a [kivonása](devices-wipe.md#retire) művelet.

PKCS-tanúsítványok *maradjon* az eszközön (tanúsítványok nem visszavont vagy eltávolítása) ha:
- A felhasználó elveszíti az Intune-licencet.
- A rendszergazda visszavonja az Intune-licencet.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.
- A rendszergazda megváltozik, vagy a PKCS-profil frissítése.
- A tanúsítványprofil távolítja el a csoport-hozzárendelés.
  
  
> [!NOTE]
> Az Android for Work-eszközökön a rendszer nem érvényesíti a fenti forgatókönyvek esetén. (Nem Samsung, nem munkahelyi profilos eszközök bármilyen) Android örökölt eszközök nem engedélyezettek a tanúsítvány eltávolítása. 

## <a name="macos-certificates"></a>macOS-tanúsítványok

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:
- A felhasználó megszünteti.
- Egy rendszergazda egy [kivonása](devices-wipe.md#retire) művelet.
- Az eszköz kikerül az Azure AD-csoportok.
- A tanúsítványprofil távolítja el a csoport-hozzárendelés.

Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
- A rendszergazda megváltozik, vagy frissíti az SCEP-profil.

SCEP-tanúsítványok *maradjon* az eszközön (tanúsítványok nem visszavont vagy eltávolítása) ha:
- A felhasználó elveszíti az Intune-licencet.
- A rendszergazda visszavonja az Intune-licencet.
- A rendszergazda eltávolítja a felhasználó vagy csoport az Azure ad-ből.

> [!NOTE]
> Az [összes adatot törlő](devices-wipe.md#wipe) műveletet nem lehet használni a macOS-eszközök gyári beállításainak visszaállításához.

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

A macOS nem támogatja a PKCS-tanúsítványokat.

