---
title: "Mi történik a Vállalati portál alkalmazás telepítésekor és a Windows 10-eszköz Intune-beli regisztrálásakor? | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0dc35efe-4fd4-4d4a-8569-d649ea704fea
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 1f872d245144727406d926b0c9401827939470f1


---


# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-windows-10-device-in-intune"></a>Mi történik a Vállalati portál alkalmazás telepítésekor és a Windows 10-eszköz Intune-beli regisztrálásakor?

Miután telepítette a Vállalati portál alkalmazást, és annak használatával regisztrálta a Windows 10 Enterprise vagy Windows 10 Professional rendszerű eszközét az Intune-ban, a Vállalati portál alkalmazásban lehetősége nyílik a következőkre:

-   Elérheti a vállalat hálózatát, a saját levelezését és a munkájához szükséges fájlokat.

-   Letöltheti a vállalati alkalmazásokat a Vállalati portálról.

-   Automatikusan beállíthatja a vállalati e-mail-fiókját.

-   Ha elveszíti a telefonját, visszaállíthatja a gyári beállításait.

A regisztrálás lépéseiért lásd: [Windows 10 Mobile-eszköz vagy Windows 10 asztali eszköz regisztrálása az Intune-ban](enroll-your-w10-phone-or-w10-pc-windows.md). A [Milyen adatokhoz jut hozzá a rendszergazda, ha regisztrálom az eszközömet az Intune-ban?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md) című szakaszból megtudhatja, hogy a rendszergazda mit láthat az eszközén.

Számítógép hozzáadásakor:

-   Olyan szoftverek települnek a számítógépre, amelyek lehetővé teszik a rendszergazda számára a számítógép felügyeletét, Önnek pedig a különböző vállalati erőforrások, például alkalmazások és támogatási információk elérését. A rendszergazda automatikusan frissítheti ezeket a szoftvereket.

-   Lehetséges, hogy az Intune Endpoint Protection is települ a számítógépre. Ez egy vírusok és kártevő szoftverek elleni védelmi alkalmazás.

-   A rendszergazda leltárt készíthet a számítógépre telepített szoftverekről, ideértve az Ön által személyes használatra telepített szoftvereket is.

-   Elképzelhető, hogy el kell fogadnia a vonatkozó használati feltételeket.

-   A rendszergazda adatokat gyűjthet a számítógép merevlemezéről, illetve adatokat törölhet róla. A rendszergazda akár a merevlemez teljes tartalmát is törölheti.

-   A rendszergazda alkalmazásokat és frissítéseket telepíthet a számítógépre.

-   A rendszergazda szabályzatokat léptethet életbe a számítógépen. Például előfordulhat, hogy jelszót vagy PIN-kódot kell beállítania a számítógépen. A rendszergazda azt is korlátozhatja, hogy hányszor lehet helytelen jelszót megadni, és kizárhatja a felhasználót a számítógépről, vagy letörölheti a számítógép merevlemezén lévő összes adatot, ha túl sokszor próbálkozott.

Ha kérdése van, lépjen kapcsolatba a rendszergazdával. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO2-->


