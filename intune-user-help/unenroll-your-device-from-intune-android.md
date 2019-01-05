---
title: Android-eszköz regisztrációjának törlése az Intune-ból | Microsoft Docs
description: Androidos eszköz regisztrációjának törlése az Intune vállalati portál
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/04/2019
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
ms.openlocfilehash: 75b26e178badbaa7905199eb91490134d2b72ba9
ms.sourcegitcommit: 61ed365f7f8826451c41bcab5e19bef97b5a3c72
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/05/2019
ms.locfileid: "54057338"
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
Céges portál egy eszközfelügyeleti alkalmazáshoz. Nem lehet eltávolítani, amíg [annak felügyeleti az eszköz regisztrációjának törlése](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). Miután ezt megtette, koppintson a Céges portál alkalmazás ikonjára, és tartsa nyomva addig, amíg az **Eltávolítás** lehetőség meg nem jelenik. Koppintson az **Eltávolítás** lehetőségre az alkalmazás eszközről való eltávolításához.  

Azt is megteheti, koppintson **beállítások** > **alkalmazások** > **céges portál** > **Eltávolítás**.  

### <a name="remove-company-portal-app-as-device-administrator"></a>Eltávolítja a céges portál alkalmazás eszköz rendszergazdaként  
Végső megoldásként a eszközadminisztrátorként törlésével eltávolíthatja az alkalmazást az eszközről.  

Ha a vállalat által birtokolt eszközök, a szervezet előfordulhat, hogy követelmény, hogy vállalati portál az eszközön mindig. Ha eltávolítja, sikerült nem fér hozzá védett vállalati erőforrásokba, például e-mail, alkalmazások, Wi-Fi vagy VPN-, amíg az alkalmazás újratelepítése után. Telepítésével kapcsolatos további információkért frissítése, vagy távolítsa el a kötelező alkalmazásokat, lásd: [alkalmazások hozzáadása Microsoft Intune-bA](https://docs.microsoft.com/intune/apps-add#apps-that-are-added-automatically-by-intune).  

Tiltsa le a céges portál egy eszköz rendszergazdaként az alábbi lépéseket. Tényleges nevét, az egyes beállítások az Android-eszközön eltérő lehet.  

**Android lépéseket, 1. lehetőség**:  
1. Válassza ki **beállítások** > **biztonsági** > **további biztonsági beállítások** > **Eszközadminisztrátorok** .  
2. Törölje a **céges portál** kiválasztása.  

**Android lépéseket, 2. lehetőség**:  
1. Válassza ki **beállítások** > **zárolási képernyő és biztonság** > **további biztonsági beállítások** > **Eszközfelügyelet alkalmazások**.  
2. Törölje a **céges portál** kiválasztása.    

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980)
