---
title: "Az eszközhöz hiányzik egy szükséges tanúsítvány | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 910fe2bc4e616c3b60d351efaffe173f58c04bc6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="your-device-is-missing-a-required-certificate"></a>Az eszközhöz hiányzik egy szükséges tanúsítvány

## <a name="whats-a-certificate"></a>Mi az a tanúsítvány?

A [kriptográfia](https://technet.microsoft.com/library/cc962030.aspx) az információ biztonságossá tételének tudománya. A kriptográfiát hagyományosan kódolt üzenetek váltására alkalmazták, hogy a [kommunikáció titokban maradjon](https://technet.microsoft.com/library/cc962019.aspx). A kriptográfia legegyszerűbb formájában betűk helyettesítésével vagy transzponálásával olvashatatlan, titkosított vagy rejtett kódolt üzenetek készítését jelenti. Csak a visszafejtési kulccsal vagy _tanúsítvánnyal_ rendelkezők alakíthatják vissza a kódolt üzenetet az eredeti, olvasható formájukba. Az androidos eszköze tanúsítványokat használ az Intune-nal, hogy az eszköze és a munkahelyi erőforrások közötti kommunikáció, például az üzenetek vagy a dokumentumok az elejétől a végéig biztonságosak legyenek.

## <a name="fixing-certificate-issues"></a>Tanúsítványproblémák elhárítása

Ha az androidos eszköz nincs regisztrálva az Intune-ban, és hiányzik róla egy, a rendszergazda által kért tanúsítvány, nem fog tudni bejelentkezni a Munkahelyi portál alkalmazásba. Amikor megpróbál bejelentkezni, a következő üzenet jelenik meg:

![képernyőfelvétel-hibaüzenet-hiányzó-tanúsítványról](./media/andr-cert_install-1-cert_missing.png)

Az első lépésként ellenőrizze, hogy eszközén [hiányzik-e egy olyan tanúsítvány, amely rendszerint előre telepített](your-device-is-missing-a-preinstalled-certificate-android.md).

Ha ez nem hoz eredményt, a rendszergazda [a fokozott biztonság érdekében második tanúsítvány telepítésre kötelezheti](your-device-is-missing-an-IT-required-certificate-android.md).

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).
