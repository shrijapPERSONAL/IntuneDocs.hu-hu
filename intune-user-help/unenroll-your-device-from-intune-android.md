---
title: Android-eszköz regisztrációjának törlése az Intune-ból | Microsoft Docs
description: Egy Android-eszköz regisztrációjának törlését mutatja be az Intune-ból
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
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
ms.openlocfilehash: 683b5ec7b07d7c270ea30ac438e7fc839b13d5fc
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43150344"
---
# <a name="how-to-remove-your-android-device-from-intune"></a>Android-eszköz regisztrációjának törlése az Intune-ból

Ha törli androidos eszköze regisztrációját az Intune-ból, az eszköz többé nem fog tudni hozzáférni a munkahelyi erőforrásokhoz.  Az eszköz felügyelet alóli kivonásának további következményeiről további információkért lásd: [Mi történik, ha törli az eszköz regisztrációját az Intune-ból?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

## <a name="removing-the-device-from-the-company-portal-app"></a>Az eszköz eltávolítása a Céges portál alkalmazásból

Ha törölni szeretné az eszköz regisztrációját az Intune-ból és a Céges portál alkalmazást, kövesse az alábbi lépéseket:

1. A Céges portál alkalmazás jobb felső sarkában található három pontra kattintva nyissa meg a **műveletmenüt**.

   ![Az androidos Céges portál alkalmazás képe, a jobb felső sarokban a megnyitott műveletmenüvel. A „Saját profil” és a „beállítások” lehetőség alatt harmadikként megjelenik az új „céges portál eltávolítása” lehetőség is, alatta a „használati feltételek”, a „súgó és visszajelzés” és végül a „névjegy”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Koppintson a **Céges portál eltávolítása** elemre.

3. Egy üzenet jelenik meg, amely arra kéri, erősítse meg, hogy valóban el akarja-e távolítani a Céges portált. Az üzenet röviden tájékoztatja arról, mi történik az eszköz regisztrációjának törlése után. Ha elolvasta az üzenetet, az eltávolításhoz koppintson az **OK** gombra.

   ![A megerősítést kérő párbeszédpanel képe, amely az új „céges portál eltávolítása” lehetőség kiválasztása után jelenik meg. A párbeszédpanel tájékoztatja a felhasználót, hogy „a céges portál eltávolítása után az eszközt nem fogja felügyelni a cég informatikai támogató szolgálata, és megszűnhet a hozzáférés a céges adatokhoz, a céges alkalmazásokhoz és a céges e-mailekhez.” Megkérdezi a felhasználót, biztosan el akarja-e távolítani a Céges portál alkalmazást, mely esetben az „Igen” lehetőséget választhatja.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>A Céges portál alkalmazás által gyűjtött adatok eltávolítása

Az Android-eszközhöz készült Céges portál alkalmazás által az eszközön tárolt adatok törlésének módja a következő:

-   Törölje az alkalmazás adatait az Alkalmazások -> kattintás az alkalmazáson -> "Adatok törlése" gomb lépésekkel.
-   Törölje a '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal' mappát.

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).
