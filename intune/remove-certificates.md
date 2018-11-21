---
title: SCEP- vagy PKCS-tanúsítványok eltávolítása a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: A rendszergazdák az összes adat törlésével, illetve kivonással távolíthatnak el tanúsítványokat a Microsoft Intune-ból. Vannak olyan forgatókönyvek, amelyek során a tanúsítványokat a rendszer automatikusan eltávolítja, például egy eszköz regisztrációjának törlésekor vagy egy megfelelőségi szabályzat eltávolításakor. Olyan forgatókönyvek is vannak, amelyek során a tanúsítványok automatikusan az eszközön maradnak, például az Intune-licenc elvesztésekor vagy eltávolításakor. Lásd az Android, az Android Enterprise, az iOS, a macOS és a Windows rendszerű eszközökre vonatkozó különféle módszereket.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: dabd5b6ca2f8bb01421c24cb7c16ab57cf59ef56
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180986"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>SCEP- vagy PKCS-tanúsítványok eltávolítása a Microsoft Intune-ban

A Microsoft Intune-ban SCEP- vagy PKCS-tanúsítványokat adhat hozzá az eszközökhöz. Ezek a tanúsítványok az eszköz [tartalmának törlése](devices-wipe.md#wipe) vagy az eszköz [kivonása](devices-wipe.md#retire) során is el is távolíthatók. Vannak olyan forgatókönyvek, amelyek során a rendszer automatikusan eltávolítja a tanúsítványokat, és olyanok is, amelyekben a tanúsítványok az eszközön maradnak.

Ez a cikk néhány gyakori forgatókönyvet és azok PKCS- és SCEP-tanúsítványokra gyakorolt hatását mutatja be.

> [!NOTE]
> Ha szeretné eltávolítani vagy megvonni a tanúsítványokat egy olyan felhasználótól, akit eltávolít az Active Directoryból (AD) vagy az Azure AD-ból, mindig tartsa be az alábbi sorrendet:
>
>    1. Először vonja ki a felhasználó eszközét vagy törölje annak teljes tartalmát.
>    2. Csak ezután távolítsa el a felhasználót az AD-ból vagy az Azure AD-ból.

## <a name="windows-devices"></a>Windows-eszközök

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

- Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet
  - Az eszközt eltávolítják az Azure Active Directory- (AD-) csoportból
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből
  - A konfigurációs profilt eltávolítják a csoport-hozzárendelésből

- Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
  - A rendszergazda módosítja vagy frissíti az SCEP-profilt

- A főtanúsítvány eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből

- Az SCEP-tanúsítványok az eszközön **maradnak** (a tanúsítványok nem lesznek visszavonva vagy eltávolítva), ha:
  - A végfelhasználó elveszíti az Intune-licencét
  - Egy rendszergazda visszavonja az Intune-licencet
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure AD-ból

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

- A PKCS-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet

- A főtanúsítvány eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet

- A PKCS-tanúsítványok az eszközön **maradnak** (a tanúsítványok nem lesznek visszavonva vagy eltávolítva), ha:
  - A végfelhasználó elveszíti az Intune-licencét
  - Egy rendszergazda visszavonja az Intune-licencet
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure AD-ból
  - A rendszergazda módosítja vagy frissíti a PKCS-profilt
  - A konfigurációs profilt eltávolítják a csoport-hozzárendelésből
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből 


## <a name="ios-devices"></a>iOS-eszközök

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

- Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet
  - Az eszközt eltávolítják az Azure Active Directory- (AD-) csoportból
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből
  - A konfigurációs profilt eltávolítják a csoport-hozzárendelésből

- Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
  - A rendszergazda módosítja vagy frissíti az SCEP-profilt

- A főtanúsítvány eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből

- Az SCEP-tanúsítványok az eszközön **maradnak** (a tanúsítványok nem lesznek visszavonva vagy eltávolítva), ha:
  - A végfelhasználó elveszíti az Intune-licencét
  - Egy rendszergazda visszavonja az Intune-licencet
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure AD-ból

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

- A PKCS-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet

- A PKCS-tanúsítvány eltávolítására a következő esetekben kerül sor:
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből
  - A konfigurációs profilt eltávolítják a csoport-hozzárendelésből
  
- A főtanúsítvány eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet

- A PKCS-tanúsítványok az eszközön **maradnak** (a tanúsítványok nem lesznek visszavonva vagy eltávolítva), ha:
  - A végfelhasználó elveszíti az Intune-licencét
  - Egy rendszergazda visszavonja az Intune-licencet
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure AD-ból
  - A rendszergazda módosítja vagy frissíti a PKCS-profilt

## <a name="android-knox-devices"></a>Android Knox-eszközök

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

- Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet

- Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet
  - Az eszközt eltávolítják az Azure Active Directory- (AD-) csoportból
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből
  - A konfigurációs profilt eltávolítják a csoport-hozzárendelésből
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure Active Directoryból (AD-ból)
  - A rendszergazda módosítja vagy frissíti az SCEP-profilt

- A főtanúsítvány eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet

- Az SCEP-tanúsítványok az eszközön **maradnak** (a tanúsítványok nem lesznek visszavonva vagy eltávolítva), ha:
  - A végfelhasználó elveszíti az Intune-licencét
  - Egy rendszergazda visszavonja az Intune-licencet
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure AD-ból

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

- A PKCS-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:

  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet

- A főtanúsítvány eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja az [összes adatot törlő](devices-wipe.md#wipe) műveletet
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet

- A PKCS-tanúsítványok az eszközön **maradnak** (a tanúsítványok nem lesznek visszavonva vagy eltávolítva), ha:
  - A végfelhasználó elveszíti az Intune-licencét
  - Egy rendszergazda visszavonja az Intune-licencet
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure AD-ból
  - A rendszergazda módosítja vagy frissíti a PKCS-profilt
  - A konfigurációs profilt eltávolítják a csoport-hozzárendelésből
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből 
  
  
> [!NOTE]
> Az Android for Work-eszközök nincsenek ellenőrizve a fenti forgatókönyvekhez. Az örökölt Android-eszközök (nem Samsung márkájú, nem munkahelyi profillal rendelkező eszközök) esetén nem távolítható el a tanúsítvány. 

## <a name="macos-certificates"></a>macOS-tanúsítványok

#### <a name="scep-certificates"></a>SCEP-tanúsítványok

- Az SCEP-tanúsítvány visszavonására *és* eltávolítására a következő esetekben kerül sor:
  - Egy végfelhasználó törli a regisztrációját
  - Egy rendszergazda futtatja a [kivonási](devices-wipe.md#retire) műveletet
  - Az eszközt eltávolítják az Azure Active Directory- (AD-) csoportból
  - A megfelelőségi szabályzatot eltávolítják a csoport-hozzárendelésből
  - A konfigurációs profilt eltávolítják a csoport-hozzárendelésből

- Az SCEP-tanúsítvány visszavonására a következő esetekben kerül sor:
  - A rendszergazda módosítja vagy frissíti az SCEP-profilt

- Az SCEP-tanúsítványok az eszközön **maradnak** (a tanúsítványok nem lesznek visszavonva vagy eltávolítva), ha:
  - A végfelhasználó elveszíti az Intune-licencét
  - Egy rendszergazda visszavonja az Intune-licencet
  - Egy rendszergazda eltávolítja a felhasználót vagy csoportot az Azure AD-ból

> [!NOTE]
> Az [összes adatot törlő](devices-wipe.md#wipe) műveletet nem lehet használni a macOS-eszközök gyári beállításainak visszaállításához.

#### <a name="pkcs-certificates"></a>PKCS-tanúsítványok

A macOS nem támogatja a PKCS-tanúsítványokat.

