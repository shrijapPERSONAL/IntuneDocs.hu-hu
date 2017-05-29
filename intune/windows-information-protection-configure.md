---
title: "A Windows Információvédelem konfigurálása – Intune"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk tájékoztatást nyújt a Windows Információvédelem kezelésére használható Intune-beállításokról."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: fc58b07fe33ff6223dfa182fb4f81f15379295fa
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>A Windows Információvédelem konfigurálása a Microsoft Intune-ban

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ahogy a vállalaton belül egyre nő az alkalmazottak tulajdonában álló eszközök száma, úgy nő az adatok véletlen kiszivárgásának kockázata is az olyan alkalmazásokon és szolgáltatásokon keresztül, mint az e-mail, a közösségi média és a nyilvános felhő, amelyek fölött a vállalatnak nincs irányítási lehetősége. Olyan esetekről van szó, mint például amikor egy alkalmazott egy személyes e-mail-fiókból küldi el a legújabb tervrajzokat, termékadatokat másol és illeszt be egy tweetbe, vagy nyilvános felhőben található tárhelyre ment egy aktuális értékesítési jelentést.

A **Windows Információvédelem** úgy segít védekezni az ezekhez hasonló esetleges adatszivárgások ellen, hogy mindeközben más módon nem avatkozik bele az alkalmazott munkavégzésébe. Emellett segít megelőzni azt, hogy a vállalati alkalmazások és adatok akár vállalati eszközökön, akár az alkalmazottak által munkába hozott személyes eszközökön véletlenül kiszivárogjanak, ehhez pedig nem igényel változtatásokat a környezetben vagy az egyéb alkalmazásokban.

Ez az Intune-szabályzat látja el a Windows Information Protection által védett alkalmazások, a vállalati hálózati helyek, a védelmi szintek és a titkosítási beállítások kezelését.

>[!NOTE]
> A Windows 10-es Céges portál alkalmazás Windows Információvédelemmel való használatához a Céges portál alkalmazást fel kell vennie a Windows Információvédelem **Kivételek** listájára. 

### <a name="next-steps"></a>További lépések
További információk: [Vállalati adatok védelme a Windows információvédelemmel](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

