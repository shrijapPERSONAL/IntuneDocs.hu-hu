---
title: A Windows Információvédelem beállításai a Microsoft Intune-ban
titleSuffix: ''
description: A Windows Információvédelem kezelésére használható Microsoft Intune-beállítások.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1ec649134d4c3d28c99863aa3f04d2a89d4e029f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31033130"
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>A Windows Információvédelem konfigurálása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ahogy a vállalaton belül egyre nő az alkalmazottak tulajdonában álló eszközök száma, úgy nő az adatok véletlen kiszivárgásának kockázata is az olyan alkalmazásokon és szolgáltatásokon keresztül, mint az e-mail, a közösségi média és a nyilvános felhő, amelyek fölött a vállalatnak nincs irányítási lehetősége. Olyan esetekről van szó, mint például amikor egy alkalmazott egy személyes e-mail-fiókból küldi el a legújabb tervrajzokat, termékadatokat másol és illeszt be egy tweetbe, vagy nyilvános felhőben található tárhelyre ment egy aktuális értékesítési jelentést.

A **Windows Információvédelem** úgy segít védekezni az ezekhez hasonló esetleges adatszivárgások ellen, hogy mindeközben más módon nem avatkozik bele az alkalmazott munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által munkába hozott személyes eszközökön véletlenül kiszivárogjanak, ehhez pedig nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.

Ez az Intune-szabályzat látja el a Windows Information Protection által védett alkalmazások, a vállalati hálózati helyek, a védelmi szintek és a titkosítási beállítások kezelését.

>[!NOTE]
> A Windows 10-es Céges portál alkalmazás Windows Információvédelemmel való használatához a Céges portál alkalmazást fel kell vennie a Windows Információvédelem **Kivételek** listájára. 

### <a name="next-steps"></a>További lépések
További információkért lásd:
-  [Vállalati adatok védelme a Windows információvédelemmel](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
- [Windows információvédelmi (WIP-) szabályzat létrehozása a hagyományos Microsoft Intune-konzollal](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [MDM-mel ellátott Windows információvédelmi (WIP-) szabályzat létrehozása a Microsoft Intune Azure Portaljával](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [MDM-mel ellátott Windows információvédelmi (WIP-) szabályzat létrehozása a Microsoft Intune Azure Portaljával](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
