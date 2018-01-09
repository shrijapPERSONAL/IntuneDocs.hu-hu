---
title: "Az Intune webtartalomszűrő-beállításai iOS-eszközökhöz"
titlesuffix: Azure portal
description: "Ismerkedjen meg az iOS-es eszközök webhelyhozzáférésének engedélyezésére és letiltására szolgáló beállításokkal."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d0d8a6e198a58fc513645db68ae3a3ef84a3653
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/30/2017
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Webtartalomszűrő-beállítások iOS-eszközökhöz

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ezekkel a beállításokkal konfigurálhatja, hogy az iOS-es eszközök böngészőinek végfelhasználói mely URL-eket érhetik el, és melyeket nem. Az URL-címeket kétféleképpen konfigurálhatja:

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
    - **Blokkolt URL-címek** – a **Blokkolt URL-címek** panelen írja be a(z Apple webszűrőjének beállításaitól függetlenül) blokkolni kívánt URL-címeket, és mindegyik után nyomja meg az Entert.
2. Amikor végzett, kattintson az **OK**gombra.


## <a name="specific-websites-only"></a>Csak meghatározott webhelyek

1. A **Webes tartalomszűrés** panelen minden engedélyezni kívánt webhelyhez konfigurálja az alábbi beállításokat:
    - **URL** – írja be az engedélyezni kívánt webhely URL-jét (például **http://www.contoso.com**).
    - **Elérési út felvétele a könyvjelzők közé** – Adja meg a könyvjelző kívánt tárolási helyét (például **/Contoso/Business Apps**). Ha nem adja meg az elérési utat, a könyvjelző az eszköz alapértelmezett könyvjelzőmappájába kerül.
    - **Cím** – Adjon jellemző címet a könyvjelzőnek.
2. Az egyes webhelyek adatainak kitöltése után mindig kattintson a **Hozzáadás** gombra.
3. Amikor végzett, kattintson az **OK**gombra.

>[!IMPORTANT] 
> Az Intune a következő URL-eket engedélyezi automatikusan:
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## <a name="finish-up"></a>Befejezés

Az **OK** gombra kattintva térjen vissza a **Profil létrehozása** panelre, majd válassza a **Létrehozás** elemet.

## <a name="next-steps"></a>További lépések

Most hozzárendelheti az eszközprofilt a kiválasztott csoportokhoz. A részletekért lásd: [Eszközprofilok hozzárendelése](device-profile-assign.md).
