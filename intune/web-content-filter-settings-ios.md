---
title: A Microsoft Intune webtartalomszűrő-beállításai iOS-eszközökhöz
titlesuffix: ''
description: Ismerkedjen meg az iOS-es eszközök webhelyhozzáférésének engedélyezésére és letiltására szolgáló Microsoft Intune-beállításokkal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1c8eb121b3db52f0fdfc30d7d8dff7ef0f7bf97b
ms.sourcegitcommit: f21287c66dd5559688f08bd98b6c976a0dea055d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/31/2018
ms.locfileid: "34456350"
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Webtartalomszűrő-beállítások iOS-eszközökhöz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ez a cikk bemutatja az iOS-eszközök böngészőinek URL-cím-hozzáférését vezérlő Microsoft Intune-beállításokat.

Az URL-címeket kétféleképpen konfigurálhatja:

- **URL-címek konfigurálása** – használja az Apple felnőtt kulcsszavakat, például trágár vagy nyíltan szexuális tartalmú kifejezéseket kereső beépített webszűrőjét. Ez a funkció betöltéskor vizsgálja meg a weblapokat, így próbálja felismerni és blokkolni a nem megfelelő tartalmat. A szűrő által nem ellenőrzött URL-eket is konfigurálhat, valamint a szűrő beállításaitól függetlenül letiltott URL-eket.

- **Csak meghatározott webhelyek** (csak a Safari böngészőben) – ezek az URL-ek a Safari könyvjelzői közé kerülnek. A felhasználó **kizárólag** ezeket a webhelyeket nyithatja meg, az összes többi le lesz tiltva. Akkor célszerű ezt a lehetőséget választani, ha a felhasználók által elérhető URL-ek listája pontosan ismert.
Ha nincs megadva semmilyen URL, akkor a felhasználók mindössze a microsoft.com, a microsoft.net és az apple.com webhelyekhez férnek hozzá.

## <a name="get-started"></a>Első lépések

1. Az Eszközfunkciók panelen válassza a **Webes tartalomszűrés (csak felügyelt)** lehetőséget.
2. A **Webes tartalomszűrés** panelen az alábbiak közül válassza ki a konfigurálni kívánt **Szűrőtípust**:
    - **Nincs beállítva** – a szűrés ki lesz kapcsolva.
    - **URL-címek konfigurálása**
    - **Csak meghatározott webhelyek**
3. Következőként a használt szűrő típusától függően használja a következő eljárások egyikét:


## <a name="configure-urls"></a>URL-címek konfigurálása

1. A **Webes tartalomszűrés** panelen szükség esetén válasszon az alábbi beállítások közül:
   - **Engedélyezett URL-címek** – az **Engedélyezett URL-címek** panelen írja be az engedélyezni (az Apple webszűrőjén átengedni) kívánt URL-címeket, és mindegyik után nyomja meg az Entert.
     > [!NOTE]
     > Az itt megadott URL-címekre nem vonatkozik az Apple webszűrője. Ezek az URL-címek nem a kizárólagosan engedélyezett webhelyeket képviselik. Ha ilyet szeretne beállítani, használja a **Csak meghatározott webhelyek** lehetőséget.

   - **Blokkolt URL-címek** – a **Blokkolt URL-címek** panelen írja be a(z Apple webszűrőjének beállításaitól függetlenül) blokkolni kívánt URL-címeket, és mindegyik után nyomja meg az Entert.
2. Amikor végzett, kattintson az **OK**gombra.


## <a name="specific-websites-only"></a>Csak meghatározott webhelyek

1. A **Webes tartalomszűrés** panelen minden engedélyezni kívánt webhelyhez konfigurálja az alábbi beállításokat:
    - **URL** – írja be az engedélyezni kívánt webhely URL-címét (például **http://www.contoso.com**).
    - **Elérési út felvétele a könyvjelzők közé** – Adja meg a könyvjelző kívánt tárolási helyét (például **/Contoso/Business Apps**). Ha nem adja meg az elérési utat, a könyvjelző az eszköz alapértelmezett könyvjelzőmappájába kerül.
    - **Cím** – Adjon jellemző címet a könyvjelzőnek.
2. Az egyes webhelyek adatainak kitöltése után mindig kattintson a **Hozzáadás** gombra.
3. Amikor végzett, kattintson az **OK**gombra.

> [!IMPORTANT]
> Az Intune a következő URL-eket engedélyezi automatikusan.
> - <www.microsoft.com>
> - <www.microsoft.net>
> - <www.apple.com>

## <a name="finish-up"></a>Befejezés

Az **OK** gombra kattintva térjen vissza a **Profil létrehozása** panelre, majd válassza a **Létrehozás** elemet.

## <a name="next-steps"></a>További lépések

Most hozzárendelheti az eszközprofilt a kiválasztott csoportokhoz. A részletekért lásd: [Eszközprofilok hozzárendelése](device-profile-assign.md).
