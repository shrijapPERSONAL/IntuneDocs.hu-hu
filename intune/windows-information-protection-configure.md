---
title: Windows információvédelem beállításai a Microsoft Intune-ban |} A Microsoft Intune-ban
description: A Windows Információvédelem kezelésére használható Microsoft Intune-beállítások.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4de47ace4c648a2469ff9d1144f694cc86a95bf
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57395800"
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>A Windows Információvédelem konfigurálása a Microsoft Intune-ban

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ahogy a vállalaton belül egyre nő az alkalmazottak tulajdonában álló eszközök száma, úgy nő az adatok véletlen kiszivárgásának kockázata is az olyan alkalmazásokon és szolgáltatásokon keresztül, mint az e-mail, a közösségi média és a nyilvános felhő, amelyek fölött a vállalatnak nincs irányítási lehetősége. Olyan esetekről van szó, mint például amikor egy alkalmazott egy személyes e-mail-fiókból küldi el a legújabb tervrajzokat, termékadatokat másol és illeszt be egy tweetbe, vagy nyilvános felhőben található tárhelyre ment egy aktuális értékesítési jelentést.

A **Windows Információvédelem** úgy segít védekezni az ezekhez hasonló esetleges adatszivárgások ellen, hogy mindeközben más módon nem avatkozik bele az alkalmazott munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által munkába hozott személyes eszközökön véletlenül kiszivárogjanak, ehhez pedig nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.

Ez az Intune-szabályzat látja el a Windows Information Protection által védett alkalmazások, a vállalati hálózati helyek, a védelmi szintek és a titkosítási beállítások kezelését.

>[!NOTE]
> A Windows 10-es Céges portál alkalmazás Windows Információvédelemmel való használatához a Céges portál alkalmazást fel kell vennie a Windows Információvédelem **Kivételek** listájára. 

## <a name="next-steps"></a>További lépések
További információkért lásd:
-  [Vállalati adatok védelme a Windows információvédelemmel](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
- [Windows információvédelmi (WIP-) szabályzat létrehozása a hagyományos Microsoft Intune-konzollal](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [MDM-mel ellátott Windows információvédelmi (WIP-) szabályzat létrehozása a Microsoft Intune Azure Portaljával](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [MDM-mel ellátott Windows információvédelmi (WIP-) szabályzat létrehozása a Microsoft Intune Azure Portaljával](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
