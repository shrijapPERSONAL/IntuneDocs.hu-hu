---
title: "A Windows Információvédelem konfigurálása – Intune"
titleSuffix: Azure portal
description: "A cikk tájékoztatást nyújt a Windows Information Protection kezelésére használható Intune-beállításokról.”"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e33fa9b22687f7f8c4d301c6cd82ecd787c23246
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>A Windows Információvédelem konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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
