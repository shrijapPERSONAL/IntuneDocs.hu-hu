---
title: Az energiaoptimalizálás akadályozza az e-mail-hozzáférést | Microsoft Docs
description: Az alábbi cikkből megtudhatja, hogyan kapcsolhatja ki az androidos energiaoptimalizálást, hogy biztosan hozzáférhessen a levelezéséhez.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/07/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 33b6199c25e9e36b65dfe2ca819640fa614e68b6
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43148223"
---
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a>Az Outlook nem szinkronizálja a felügyelt e-maileket, ha az androidos akkumulátor-optimalizálás be van kapcsolva

> [!IMPORTANT]
> A problémát azért itt dokumentáljuk, mert az elmúlt időben nagy mennyiségű felhasználói visszajelzést kaptunk vele kapcsolatban. Ha a probléma az alábbi lépések elvégzése után is fennáll, további segítségért lépjen kapcsolatba a [cég informatikai támogatási szolgálatával](https://go.microsoft.com/fwlink/?linkid=2010980).

Az eszköz Intune-regisztrációjával hozzáférhet a céges erőforrásokhoz. A leggyakrabban használt erőforrások egyike az e-mail-hozzáférés. Az Android-eszközök esetében az Outlook-levelezés hozzáférésével kapcsolatos hibák egyike az akkumulátor-optimalizálás bekapcsolása során jelentkezett. Az akkumulátor-optimalizálás automatikusan bekapcsolhat az eszköz üzemidejének meghosszabbítása érdekében. Az akkumulátor-optimalizálás az automatikus e-mail-letöltés leállításával részben segít megőrizni az eszköz töltöttségét.

A Microsoft Intune csapata aktívan dolgozik a probléma megoldásán. Ha nem szeretné, hogy az eszköz alacsony töltöttségű módban üzemeljen, tartsa az akkumulátor töltöttségét 30% felett. Ha nem szeretné, hogy a probléma továbbra is fennálljon az alacsony töltöttségű módban, távolítsa el a Céges portált és az Outlookot az akkumulátor-optimalizálás és az energiatakarékos használati beállítások alkalmazáslistájából.

Számos gyártó megannyi Android-eszközzel szolgál, így nem tudunk minden eszközhöz pontos útmutatást nyújtani. Előfordulhat, hogy a szükséges műveleteket elég a rendszerbeállításokban elvégeznie, azonban az is, hogy a gyártóspecifikus beállításokat is módosítania kell. Az alábbiakban gyakori példákat láthat a probléma megoldási módjaira Android-eszközökön.

## <a name="unmodified-android-devices"></a>Módosítás nélküli Android-eszközök

Számos gyártó módosításokkal látja el az Android-eszközöket. Ezek függvényében változhat az, hogy Ön hogyan használja az eszközt, például változhatnak a témák és az értesítések. A Google általában nem alkalmaz módosításokat a telefonjain. Az Android 7.0 vagy újabb verziójú Google Pixel telefonokon például az alábbi lépéseket kell követnie az alkalmazások az akkumulátor-optimalizálás hatóköre alól való eltávolításához:

1. Nyissa meg a **Beállításokat**.
2. Koppintson az **Akkumulátor** > **Egyéb** > **Akkumulátor-optimalizálás** lehetőségre.
3. Koppintson a lefelé mutató nyílra, majd a **Nincs optimalizálva** lehetőségre.
4. Válassza ki a Céges portál és az Outlook alkalmazást, és kapcsolja ki az akkumulátor-optimalizálást.

## <a name="samsung-devices"></a>Samsung-eszközök

Egyéb típusú Android-eszközök, például Android 7.0 vagy újabb verziójú Samsung-eszközök esetében eltérő lépésekkel távolíthatja el az Outlookot és a Céges portált az akkumulátor-optimalizálás hatóköre alól.

1. Nyissa meg a **Beállításokat**.
2. Koppintson a **Menü (...)**  > **Különleges hozzáférés** > **Akkumulátorhasználat optimalizálása** lehetőségre.
3. Válassza a **Minden alkalmazás** lehetőséget a legördülő listából.
4. Az akkumulátor-optimalizálást kikapcsolásához a Céges portál és az Outlook alkalmazás mellett kapcsolja **ki** a gombot.

Emellett ha egy, az Android korábbi verziójával rendelkező Samsung-eszközt használ, az alábbi lépéseket kell követnie az alkalmazások az energiatakarékos mód hatóköréből való eltávolításához.

1. Nyissa meg a **Beállításokat**.
2. Koppintson az **Eszközkarbantartás** > **Akkumulátor** > **Nem figyelt alkalmazások** lehetőségre.
3. Koppintson az **Alkalmazások hozzáadása** lehetőségre.
4. Válassza ki a Céges portál és az Outlook alkalmazást, majd koppintson a **Kész** elemre.

## <a name="oneplus-devices"></a>OnePlus-eszközök

A szükséges beállításokat emellett a rendszerbeállítások között is megkeresheti. Például egy Android 7.1.1 rendszerű OnePlus 3-eszközön az alábbi lépéseket kell követnie: 

1. Nyissa meg a **Rendszerbeállítások** menüt. 
2. Koppintson a **Keresés** gombra. Ez a képernyő tetején, egy nagyítóikonként jelenik meg. 
3. Írja be az **akkumulátor-optimalizálás** kifejezést a keresőmezőbe, majd válassza az **Akkumulátor-optimalizálás** lehetőséget a megjelenő **Beállítások** képernyőn. 
4. Koppintson az **Akkumulátor** > **Akkumulátor-optimalizálás** lehetőségre.
5. Válassza ki a Céges portál és az Outlook alkalmazást, majd koppintson a **Ne optimalizálja** elemre. Koppintson a **Kész** gombra.

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

További segítségre van szüksége? Forduljon a cég informatikai támogatásához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](https://go.microsoft.com/fwlink/?linkid=2010980).
