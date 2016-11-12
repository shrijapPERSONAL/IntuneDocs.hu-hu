---
title: "IOS-eszköz regisztrációjának törlése az Intune-ból | Microsoft Intune"
description: "Egy iOS-eszköz regisztrációjának törlését mutatja be az Intune-ból"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28914db1-3e62-45f5-9632-b0d2a808a44d
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: 5db58b87e5c48c40794315e7781d32b02a653b2b


---


# <a name="unenroll-your-ios-device-from-intune"></a>IOS-eszköz regisztrációjának törlése az Intune-ból

Amikor törli az iOS-alapú eszköz Intune-regisztrációját, az nem fog tudni többé hozzáférni a vállalati erőforrásokhoz, és kikerül az Intune felügyelete alól.

Ha az eszköz regisztrációját törölni szeretné az Intune-ból, kövesse az alábbi lépéseket, vagy tekintse meg ezt a videót:

<iframe width="675" height="379" src="https://www.youtube.com/embed/6UFtBrBWUUI" frameborder="0" allowfullscreen></iframe>


1.  A Vállalati portál alkalmazás **Eszközök**csoportjában válassza ki azt az eszközt, amelynek a regisztrációját törölni szeretné.

2.  Koppintson az **Eltávolítás** &gt; **Eltávolítás** lehetőségre.

Az eszköz regisztrációjának Intune-ból való törlésekor a következők történnek:

-   Az eszköz többé nem jelenik meg a vállalati portálon.

-   Többé nem telepíthet alkalmazásokat a vállalati portálról.

-   Az eszközön annak regisztrálásakor módosult beállítások (például a kamera letiltása vagy meghatározott hosszúságú jelszó megkövetelése) hatályukat vesztik.

-   Előfordulhat, hogy az eszközről többé nem lehet elérni egyes vállalati erőforrásokat, például fájlmegosztásokat és belső webhelyeket.

-   Az eszközön többé nem használhatók a vállalati alkalmazások és adatok.

-   Előfordulhat, hogy Wi-Fi- vagy virtuális magánhálózati (VPN-) kapcsolaton keresztül nem tud többé a vállalati hálózathoz csatlakozni.

-   A rendszer eltávolítja a vállalati e-mail profilokat az eszközről.

-   A csak levelezéshez konfigurált eszközök nem fognak megjelenni a Vállalati portál alkalmazásban és a vállalati portál webhelyén.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO1-->


