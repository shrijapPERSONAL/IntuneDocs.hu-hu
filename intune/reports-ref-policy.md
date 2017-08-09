---
title: "Szabályzat | Microsoft Docs"
description: "Az Intune-adattárház API-ban található entitásgyűjtemények szabályzatkategóriájára vonatkozó referencia-témakör."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6af0ff1f463c153e62f6df63ce811076c5f692f2
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-policy-entities"></a>Szabályzat típusú entitások referenciája

A **Szabályzat**kategória mobileszközökhöz tartozó entitásokat tartalmaz, amelyek információt gyűjtenek, például:

  -  Az eszköz- és alkalmazáskonfigurációs profilok, valamint a megfelelőségi szabályzatok készlete  
  -  A sikeres, függő, sikertelen vagy hibás állapotú eszközök száma naponta  
  -  A sikeres, függő, sikertelen vagy hibás állapotú felhasználók száma naponta  
  -  A sikeres, függő, sikertelen vagy hibás állapotú eszközök száma összesen  

## <a name="policy"></a>Házirend

A **Szabályzat** entitás eszköz- és alkalmazáskonfigurációs profilokat, valamint megfelelőségi szabályzatokat tartalmaz. A szabályzatokat a Mobileszköz-kezelési (MDM) megoldás segítségével rendelheti hozzá a vállalat valamely csoportjához.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| PolicyKey |A szabályzat adattárházban való jelölésére szolgáló egyedi kulcs |123 |
| PolicyId |A szabályzat egyedi azonosítója az adattárházban |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |A szabályzat neve |„Windows 10 Baseline” |
| PolicyVersion |A szabályzat verziója. A szabályzat szerkesztésekor vagy módosításakor új verzió jön létre. |1, 2, 3 |
| IsDeleted |Jelzi, hogy frissítve lett-e a szabályzatrekord.  Igaz – a szabályzat új, frissített mezőkkel ellátott rekorddal rendelkezik. Hamis – a szabályzat legújabb rekordja. |Igaz/hamis |
| StartDateInclusiveUTC |A szabályzat adattárházban történt létrehozásának dátuma és időpontja (UTC) |2016.11.23. 12:00:00 |
| DeletedDateUTC |Az IsDeleted paraméter igaz értékre történt módosulásának dátuma és időpontja (UTC) |2016.11.23. 12:00:00 |
| RowLastModifiedDateTimeUTC |A szabályzat adattárházban történt utolsó módosításának dátuma és időpontja (UTC). |2016.11.23. 12:00:00 |

## <a name="policytype"></a>PolicyType

A **PolicyType** entitás az eszköz- és alkalmazáskonfigurációs profilok, valamint a megfelelőségi szabályzatok típusait tartalmazza. A szabályzatokat a Mobileszköz-kezelési (MDM) megoldás segítségével rendelheti hozzá a vállalat valamely csoportjához.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| PolicyTypeId |A szabályzat egyedi azonosítója a forrásrendszerben |123 |
| PolicyTypeId |A szabályzat egyedi azonosítója az adattárházban |1 |
| PolicyTypeName |A szabályzattípus neve. |A Windows 10-re vonatkozó megfelelőségi szabályzat |

## <a name="deviceconfiguration"></a>DeviceConfiguration

A **DeviceConfigurationProfileDeviceActivity** entitás a napi sikeres, függő, sikertelen vagy hibás állapotú eszközök számát sorolja fel. A szám az entitáshoz rendelt eszközkonfigurációs profilokat jelöli. Ha például az adott eszköz valamennyi hozzárendelt szabályzata tekintetében sikeres állapotú, akkor az entitás azon a napon eggyel növeli az értéket a sikeres állapotot jelző számlálón. Ha az adott eszköz két hozzárendelt profillal rendelkezik, amelyek közül az egyik sikeres, míg a másik hibás állapotú, akkor az entitás növeli az értéket a sikeres állapotot jelző számlálón, és hibás állapotba helyezi az eszközt. Az entitás azt sorolja fel, hogy hány eszköz van az egyes állapotokban az elmúlt 30 napon belüli adott napon.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| DateKey |A Date Key azt jelöli, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése |20160703 |
| Függőben |A függő állapotú egyedi eszközök száma |123 |
| Sikerült |A sikeres állapotú egyedi eszközök száma |12 |
| Hiba |A hibás állapotú egyedi eszközök száma |10 |
| Sikertelen |A sikertelen állapotú lévő egyedi eszközök száma |2 |

## <a name="userconfiguration"></a>UserConfiguration

A **UserConfigurationProfileDeviceActivity** entitás a napi sikeres, függő, sikertelen vagy hibás állapotú felhasználók számát sorolja fel. A szám az entitáshoz rendelt eszközkonfigurációs profilokat jelöli. Ha például az egyik felhasználó valamennyi hozzárendelt szabályzata tekintetében sikeres állapotú, akkor az entitás azon a napon eggyel növeli az értéket a sikeres állapotot jelző számlálón. Ha az adott felhasználó két hozzárendelt profillal rendelkezik, amelyek közül az egyik sikeres, míg a másik hibás állapotú, akkor a felhasználót hibás állapotúnak számítjuk.  A **UserConfigurationProfileDeviceActivity** entitás azt sorolja fel, hogy hány felhasználó van az egyes állapotokban az elmúlt 30 napon belüli adott napon.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| DateKey |A Date Key azt jelöli, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése |20160703 |
| Függőben |A függő állapotú egyedi felhasználók száma |123 |
| Sikerült |A sikeres állapotú egyedi felhasználók száma |12 |
| Hiba |A hibás állapotú egyedi felhasználók száma |10 |
| Sikertelen |A sikertelen állapotú egyedi felhasználók száma |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

A **PolicyTypeActivity** entitás a sikeres, függő, sikertelen vagy hibás állapotú eszközök számát sorolja fel összesítve. Ezeket az állapotokat az adott eszköz-, illetve alkalmazáskonfigurációs profilra, valamint megfelelőségi szabályzatra vonatkozóan ismerteti.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| DateKey |A dátumkulcs azt jelzi, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése |20160703 |
| PolicyKey |Szabályzatkulcs, amely összekapcsolható a szabályzattal a policyName paraméter lekérése érdekében |Windows 10 baseline |
| PolicyTypeKey |Szabályzatkulcs típusa, amely összekapcsolható a szabályzattípussal a szabályzattípus nevének lekérése érdekében |Windows10megfelelőségiSzabályzat |
| Függőben |A függő állapotú egyedi eszközök száma |123 |
| Sikerült |A sikeres állapotú egyedi eszközök száma |12 |
| Hiba |A hibás állapotú egyedi eszközök száma |10 |
| Sikertelen- |A sikertelen állapotú egyedi eszközök száma |2 |