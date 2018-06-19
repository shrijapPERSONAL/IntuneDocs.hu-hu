---
title: Egyéni beállítások hozzáadása Android-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Egyéni profilok Android-eszközökhöz való hozzáadásával vagy létrehozásával előmegosztott kulccsal rendelkező Wi-Fi-profilt és alkalmazásonkénti VPN-profilt hozhat létre, vagy engedélyezheti és letilthatja a Samsung Knox Standard-eszközök alkalmazásait a Microsoft Intune-ban
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0195e138b59fae019fa2bc02aadf211257a65cac
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022050"
---
# <a name="custom-settings-for-android-devices---intune"></a>Android-eszközök egyéni beállításai – Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az egyéni profilok Open Mobile Alliance Uniform Resource Identifier (OMA-URI) beállítások segítségével konfigurálják az Android-eszközök különböző beállításait és a szolgáltatásait. Ezekkel a beállításokkal általában a mobileszközgyártók vezérlik az eszközök funkcióit.

Egyéni profillal a következő Android-beállításokat konfigurálhatja és rendelheti hozzá. Ezek a beállítások nem beépített részei az Intune-szabályzatoknak:

- [Wi-Fi-profil létrehozása előmegosztott kulccsal](/intune/wi-fi-profile-shared-key)
- [Alkalmazásonkénti VPN-profil létrehozása](/intune/android-pulse-secure-per-app-vpn)
- [Alkalmazások engedélyezése és letiltása Samsung Knox Standard-eszközökön](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Ezzel a profiltípussal csak a felsorolt beállítások konfigurálhatók. Az Android-eszközök nem teszik elérhetővé a konfigurálható OMA-URI-beállítások teljes listáját. Ha több beállítást szeretne látni, szavazzon rájuk az [Intune Uservoice webhelyén](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Egyéni profilbeállítások Android rendszerű eszközökhöz

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com). 
2. Kattintson a **Minden szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a  **Microsoft Intune** elemet.
3. Hozzon létre egy egyéni profilt az Android-platformmal. A folyamat lépéseit az [Egyéni eszközbeállítások konfigurálása a Microsoft Intune-ban](custom-settings-configure.md) című cikk ismerteti.
4. Az **Egyéni OMA-URI beállítások** területen válassza a **Hozzáadás**, majd a **Sor hozzáadása** lehetőséget.
5. Adja meg a következő tulajdonságokat:

   - **Név** – Adjon meg egy egyéni nevet az OMA-URI beállításnak, hogy később könnyebben megtalálja.
   - **Leírás** – Adjon meg egy olyan leírást, amely ismerteti a beállítást, valamint írjon be egyéb fontos részleteket.
   - **Adattípus** – Adja meg az OMA-URI beállításhoz használt adattípust. A **Karakterlánc**, **Karakterlánc (XML)**, **Dátum és idő**, **Egész szám**, **Lebegőpontos szám** vagy **Logikai** lehetőségek közül választhat.
   - **OMA-URI** – Adja meg a kívánt OMA-URI-t.
   - **Érték** – Adja meg a megadott OMA-URI azonosítóhoz társítandó értéket.

6. A módosítások mentéséhez válassza az **OK** gombot. Szükség szerint adjon hozzá további beállításokat.

## <a name="next-steps"></a>További lépések

A beállítások befejezését követően létrejön a profil, és megjelenik a listában. Ha a profilt csoportokhoz szeretné rendelni, erről az [eszközprofilok hozzárendelését](device-profile-assign.md) ismertető cikk nyújt tájékoztatást.
