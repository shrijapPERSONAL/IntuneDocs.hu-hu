---
title: "A Windows rendszerű számítógép kezelésének leegyszerűsítése szabályzatok használatával"
description: "Ismerteti a Windows rendszerű számítógép-kezelési szabályzatokat és a Microsoft Intune Center beállításait."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: e14b5c56356812fdc3ea775cddde0f668b344177
ms.contentlocale: hu-hu
ms.lasthandoff: 06/08/2017


---

# <a name="use-policies-to-simplify-windows-pc-management"></a>A Windows rendszerű számítógép kezelésének leegyszerűsítése szabályzatok használatával

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ha a Windows rendszerű számítógépeket a rájuk telepített Intune szoftverügyféllel szeretné kezelni, akkor az Intune felügyeleti konzolján csak a **Számítógép-kezelés** területen lévő szabályzatokat használhatja. A felügyeleti konzolon felsorolt összes többi szabályzat csak mobileszközökön léptethető érvénybe. A **Számítógép-kezelés** szabályzatainak használatával konfigurálhatja a Microsoft Intune Center beállításait, irányíthatja a számítógépek frissítését, és konfigurálhatja a számítógépek Windows tűzfalát.

![Szabályzatsablon Windows rendszerű számítógépekhez](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>A Microsoft Intune Center felügyelete
A felhasználók számára az Intune-szoftverügyfél az **Microsoft Intune Center** formájában jelenik meg. A Microsoft Intune Center a következőket teszi lehetővé a felhasználók számára:

-   alkalmazások beszerzése a vállalati portálról;

-   frissítések keresése;

-   A Microsoft Intune Endpoint Protection felügyelete

-  távsegítség kérése.

A Microsoft Intune Center minden felügyelt számítógépre telepítve van. Az alábbi beállításokat konfigurálhatja egy Intune-szabályzatban, és ezek jelennek meg a felhasználóknak a Microsoft Intune Centerben:

|Házirend-beállítás|Részletek|
|------------------|--------------------|
|**Név**|A számítógépet felügyelő rendszergazda neve.<br />Maximális hossz: 40 karakter|
|**Telefonszám**|A számítógépet felügyelő rendszergazda telefonszáma.<br />Maximális hossz: 20 karakter|
|**E-mail cím**|A számítógépet felügyelő rendszergazda e-mail címe.<br />Maximális hossz: 40 karakter|
|**Webhely neve**|A felhasználói támogatási webhely neve.<br />>Maximális hossz: 40 karakter|
|**Webhely URL-címe**|A támogatási webhely URL-címe.<br />Maximális hossz: 150 karakter|
|**Megjegyzések**|A felhasználóknak megjelenített megjegyzés.<br />Maximális hossz: 120 karakter|

A Windows rendszerű számítógépekre vonatkozóan konfigurált szabályzatokról és beállításokról a következő információforrásokból tájékozódhat:

- [Windows rendszerű számítógépek naprakészen tartása szoftverfrissítésekkel a Microsoft Intune-ban](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) – Ezeknek a szabályzatoknak a hatására a felügyelt számítógépek megkeresik a Microsoft és a külső felek által közzétett szoftverfrissítéseket, és letöltik őket. Az ilyen frissítésekbe nem tartoznak bele az operációs rendszer verziófrissítései (például Windows 7-ről Windows 10-re való frissítés vagy a Windows 10 frissítése egy újabb verzióra).

- [Windows rendszerű számítógépek biztonságossá tétele a Microsoft Intune-hoz készült Endpoint Protection szolgáltatással](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) – Ezek a beállítások például az ellenőrzés ütemezésére és a kártevő észlelése esetén végrehajtandó műveletekre terjednek ki.

- [A Windows rendszerű számítógépek védelme Windows tűzfalházirendek használatával a Microsoft Intune-ban](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) – Ezek a szabályzatok leegyszerűsítik a Windows tűzfal beállításainak adminisztrációját a felügyelt számítógépeken.


### <a name="see-also"></a>További információ

[A Windows rendszerű számítógépek Intune-szoftverügyféllel való felügyeletének általános feladatai](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)

