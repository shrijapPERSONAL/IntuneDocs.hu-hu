---
title: "Az Intune használatieset-forgatókönyvének követelményei | Microsoft Docs"
description: "Ez a cikk segít az Intune használatieset- valamint alhasználatieset-forgatókönyv követelményeinek meghatározásában a Microsoft Intune felhőalapú megvalósítás esetében."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 91b25fe35c6a1f8a554d543ca005cc3b482f22d7
ms.lasthandoff: 12/30/2016


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Intune használatieset-forgatókönyvek követelményeinek meghatározása

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Ebben a szakaszban meghatározza az összes használatieset-forgatókönyv minden egyes munkahelyi csoportjára vonatkozó követelményeket. A folyamat végrehajtása segít abban, hogy jobban felkészülhessen az Intune telepítésével kapcsolatos más területeken, például az architektúra és tervezés, az előkészítés és bevezetés terén. Mindemellett az Intune telepítési projektjével kapcsolatos lehetséges hiányosságokat és kihívásokat is segít azonosítani.

Előfordulhat, hogy egyes használatieset/alhasználatieset-forgatókönyvekre vonatkozóan más követelmények, társított munkahelyi csoportok és mobileszköz-platformok léteznek. Például a céges használatieset-forgatókönyv követelményei szerint szigorúbb eszközbeállítások alapján (például 6 karakter hosszúságú PIN-kód, a felhő alapú mentés letiltása) kell regisztrálni az eszközöket Intune-ban, mint a „Saját eszközök használata” (BYOD) használatieset-forgatókönyvek követelményei szerint (ahol például elegendő a 4 karakter hosszúságú PIN-kód, a felhő alapú mentés engedélyezett).

Az is elképzelhető, hogy a céges használatieset-forgatókönyvekre olyan munkahelyi csoportokkal rendelkezik, amelyekre eltérő követelmények vonatkoznak (például a PIN-kód beállításait, Wi-Fi vagy VPN-profilt, az alkalmazásokat illetően). Továbbá az is elképzelhető, hogy a követelményeket a mobileszköz-platform képességei határozzák meg (például ujjlenyomat-olvasó, e-mail profil).

Itt található néhány példa a munkahelyi használatieset-forgatókönyvek követelményeire, amelyekben az egyes használatieset/alhasználatieset-forgatókönyvekre, munkahelyi csoportra és mobileszköz-platformra különböző követelmények vonatkoznak. Az alábbi táblázatot is felhasználhatja a munkahelye használatieset-követelményeinek megadásához:

| **Használati esetek** | **Alhasználati esetek** | **Csoportok** | **Az eszköz operációs rendszerének platformja** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Vállalat | Infómunkás | HR, Pénzügy | iOS | Biztonságos e-mail, eszközbeállítások, profilok, alkalmazások |                                                          
| Vállalat | Vezetők | HR, Pénzügy | iOS | Biztonságos e-mail, eszközbeállítások, profilok, alkalmazások |                                                         
| Vállalat | Kioszkmód | Kereskedelem | Android | Eszközbeállítások, profilok, alkalmazások |
| BYOD | Infómunkás | Marketing, értékesítés | iOS | Biztonságos e-mail, eszközbeállítások, profilok, alkalmazások |                                                         
| BYOD | Vezetők | Marketing, értékesítés | iOS | Biztonságos e-mail, eszközbeállítások, profilok, alkalmazások |

## <a name="examples-of-requirements"></a>Példák a követelményekre

Itt található további néhány példa, amelyek a fenti táblázat „Requirements” oszlopában használhatók:

- **Biztonságos e-mail**
    - Feltételes hozzáférési folyamat online / helyszíni Exchange esetén
    - Az Outlook alkalmazás adatvédelmi szabályzatai
<br></br>
- **Eszközbeállítások**
    - PIN-kód beállítása 4 vagy 6 karakterrel
    - Felhőbeli biztonsági mentés korlátozása
<br></br>
- **Profilok**
    - Wi-Fi
    - VPN
    - E-mail (Windows 10 mobil verzió)
<br></br>
- **Alkalmazások**
    - Az Office 365 és az alkalmazás adatvédelmi szabályzatai
    - Üzletági (LOB) alkalmazásvédelmi szabályzatok

## <a name="next-section"></a>Következő szakasz

A következő szakaszban az [Intune bevezetési tervének összeállításáról](section-4-develop-a-rollout-plan.md) található információ.

