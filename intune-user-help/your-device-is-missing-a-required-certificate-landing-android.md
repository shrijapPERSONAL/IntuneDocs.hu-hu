---
title: Az eszközhöz hiányzik egy szükséges tanúsítvány | Microsoft Docs
titlesuffix: Microsoft Intune
description: Mi a teendő, ha az eszközhöz hiányzik egy szükséges tanúsítvány.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 150dceebd26430e82845eef6480b87c70d00a1f0
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61500685"
---
# <a name="your-device-is-missing-a-required-certificate"></a>Az eszközhöz hiányzik egy szükséges tanúsítvány

## <a name="whats-a-certificate"></a>Mi az a tanúsítvány?

A [kriptográfia](https://technet.microsoft.com/library/cc962030.aspx) az információ biztonságossá tételének tudománya. A kriptográfiát hagyományosan kódolt üzenetek váltására alkalmazták, hogy a [kommunikáció titokban maradjon](https://technet.microsoft.com/library/cc962019.aspx). A simplist formájában titkosítás vagy transzponálásával betűk helyettesítésével olvashatatlan, titkosított vagy rejtett üzenetbe. Csak a visszafejtési kulccsal vagy _tanúsítvánnyal_ rendelkezők alakíthatják vissza a kódolt üzenetet az eredeti, olvasható formájukba. Az androidos eszköze tanúsítványokat használ az Intune-nal, hogy az eszköze és a munkahelyi erőforrások közötti kommunikáció, például az üzenetek vagy a dokumentumok az elejétől a végéig biztonságosak legyenek.

## <a name="fixing-certificate-issues"></a>Tanúsítványproblémák elhárítása

Ha az androidos eszköz nincs regisztrálva az Intune-ban, és hiányzik róla egy, a cég informatikai támogatási szolgálata által kért tanúsítvány, nem fog tudni bejelentkezni a céges portál alkalmazásba. Amikor megpróbál bejelentkezni, a következő üzenet jelenik meg:

![képernyőfelvétel-hibaüzenet-hiányzó-tanúsítványról](./media/andr-cert_install-1-cert_missing.png)

Az első lépésként ellenőrizze, hogy eszközén [hiányzik-e egy olyan tanúsítvány, amely rendszerint előre telepített](your-device-is-missing-a-preinstalled-certificate-android.md).

Tanúsítványproblémák elhárítása nem működik, ha a cég informatikai támogatási szolgálata [kell biztonság további erősítése érdekében második tanúsítvány telepítésre](your-device-is-missing-an-IT-required-certificate-android.md).

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).

## <a name="next-steps"></a>További lépések  
További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).  

