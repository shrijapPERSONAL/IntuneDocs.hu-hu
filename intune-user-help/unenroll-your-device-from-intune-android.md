---
title: Android-eszköz regisztrációjának törlése az Intune-ból | Microsoft Docs
description: Egy Android-eszköz regisztrációjának törlését mutatja be az Intune-ból
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d932005c955afed7f16e9766b559b77b2cd43182
ms.sourcegitcommit: 604b29c480b24270b5debc3e5f3141c8149ee6ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49959485"
---
# <a name="unenroll-your-android-device-from-management"></a>Android-eszköz regisztrációjának törlése  

Regisztrált Android-eszköz eltávolítása a szervezet által felügyelt eszközök közül. Ez a cikk azt ismerteti, hogyan távolíthatja el az eszközt a Céges portál alkalmazásból. Miután eltávolította az eszközt:  

* Az eszköz nem fogja tudni elérni a szervezet védett adatait és erőforrásait.
* Az eszköz nem fog megjelenni a Céges portálon.
* Nem telepíthet alkalmazásokat a Céges portálról.
* Az eszközön annak regisztrálásakor módosult beállítások (például a kamera letiltása vagy meghatározott hosszúságú jelszó megkövetelése) hatályukat vesztik.  

1. A Céges portálon koppintson a jobb felső sarokban található három függőleges pontra. Megnyílik a műveletmenü.

   ![Az androidos Céges portál alkalmazás képe, a jobb felső sarokban a megnyitott műveletmenüvel. A „Saját profil” és a „beállítások” lehetőség alatt harmadikként megjelenik az új „céges portál eltávolítása” lehetőség is, alatta a „használati feltételek”, a „súgó és visszajelzés” és végül a „névjegy”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Koppintson a **Céges portál eltávolítása** elemre.  

3. Megjelenik egy üzenet, amely tájékoztatja arról, mi történik, ha törli az eszköz regisztrációját. Koppintson az **OK** lehetőségre annak megerősítéséhez, hogy eltávolítja az eszközt a Céges portálról.

   ![A megerősítést kérő párbeszédpanel képe, amely az új „céges portál eltávolítása” lehetőség kiválasztása után jelenik meg. A párbeszédpanel tájékoztatja a felhasználót, hogy „a céges portál eltávolítása után az eszközt nem fogja felügyelni a cég informatikai támogató szolgálata, és megszűnhet a hozzáférés a céges adatokhoz, a céges alkalmazásokhoz és a céges e-mailekhez.” Megkérdezi a felhasználót, biztosan el akarja-e távolítani a Céges portál alkalmazást, mely esetben az „Igen” lehetőséget választhatja.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>A Céges portál alkalmazás által gyűjtött adatok eltávolítása  

Az Android-eszközhöz készült Céges portál alkalmazás által az eszközön tárolt adatok törlésének módja a következő:

-   Törölje az alkalmazás adatait az Alkalmazások -> kattintás az alkalmazáson -> "Adatok törlése" gomb lépésekkel.
-   Törölje a '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal' mappát.

## <a name="uninstall-the-company-portal-app"></a>A Céges portál alkalmazás eltávolítása  
A Céges portál egy eszközkezelési alkalmazás, ezért addig nem lehet eltávolítani, amíg [nem szünteti meg az eszköz regisztrációját a kezelt eszközök között](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). Miután ezt megtette, koppintson a Céges portál alkalmazás ikonjára, és tartsa nyomva addig, amíg az **Eltávolítás** lehetőség meg nem jelenik. Koppintson az **Eltávolítás** lehetőségre az alkalmazás eszközről való eltávolításához.  

Vagy koppintson a **Beállítások** > **Alkalmazások** > **Céges portál** > **Eltávolítás** lehetőségre.  

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980)
