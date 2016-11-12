---
title: "Az eszköz távoli zárolása a Vállalati portál webhelyéről | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: adc6af23-b22f-42e5-955a-4dffbdb8b42b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: 31b3f4c556c27de7a1793bfe84a1d3eb12302424


---


# <a name="remotely-lock-a-device-from-the-company-portal-website"></a>Az eszköz távoli zárolása a Vállalati portál webhelyéről

Ha elvesztette vagy ellopták az eszközét, a [Vállalati portál webhelyének](http://portal.manage.microsoft.com) Távoli zárolás funkciójával zárolhatja. A távoli zárolás a következő típusú eszközök esetén alkalmazható:

Platform  |Támogatás részletei  
---------|---------
Android | Támogatott       
iOS | Támogatott
Windows 10 mobil verzió | Csak beállított jelszóval rendelkező telefonok esetén támogatott     
Windows 10 asztali verzió | Nem támogatott  
Windows Phone 8.1 | Csak beállított jelszóval rendelkező telefonok esetén támogatott
PC (Windows 8.0 és korábbi verziók) | Nem támogatott       
PC (Windows 8.1) | Nem támogatott

</br>
A Távoli zárolás funkció használata az eszköz zárolásához:

1.  A [Vállalati portál webhelyen](http://portal.manage.microsoft.com) koppintson annak az eszköznek a nevére, amelyet zárolni szeretne.

2.  Koppintson a **Távoli zárolás** elemre.

    ![remote-lock-option-on-company-portal-website](./media/iwp-screen-with-all-options.png)

3.  Olvassa el a zárolásról szóló figyelmeztető üzenetet, és koppintson a **Távoli zárolás** lehetőségre, így a Vállalati portál webhelye zárolja az eszközt.

    A **Távoli zárolás** elemre való koppintás után megjelenik a „Távoli zárolás függőben” állapot.  Ha a távoli zárolás sikeres, az állapot a „Sikeres volt a távoli zárolás” állapotra változik.

    A Távoli zárolás állapota három helyen jelenik meg:

    * A webhely értesítési területén.
    * Az eszköz Részletek lapján.
    * Az oldal Eszközeim területén, az eszköz nevét megjelenítő csempén.

    Ha a „Sikertelen volt a távoli zárolás” értesítés jelenik meg, néhány perc várakozás után próbálkozzon újra az eszköz zárolásával. Amikor újra próbálkozik, az állapot visszavált a „Távoli zárolás függőben” állapotra.

    Ha az újbóli próbálkozás is sikertelen, forduljon a rendszergazdához. Ha eszközét megtalálja, és a Távoli zárolás funkció használata után szeretné feloldani a zárolását, egyszerűen adja meg a jelszavát.

További segítségre van szüksége? Forduljon a rendszergazdához. Az elérhetőségét keresse meg a [Vállalati portál webhelyén](http://portal.manage.microsoft.com).




<!--HONumber=Nov16_HO1-->


