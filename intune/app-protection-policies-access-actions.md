---
title: Szelektív adattörlés alkalmazásvédelmi szabályzatok hozzáférési műveleteivel
titleSuffix: Microsoft Intune
description: Útmutató az alkalmazásvédelmi szabályzatok hozzáférési műveleteivel végzett szelektív adattörléshez a Microsoft Intune-ban.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2cfd426a0ae7165a7aae60a90d104852fd834db6
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909116"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Szelektív adattörlés alkalmazásvédelmi szabályzatok hozzáférési műveleteivel az Intune-ban

Az Intune alkalmazásvédelmi szabályzatainak használatával olyan beállításokat konfigurálhat, amelyek megakadályozzák, hogy a felhasználók hozzáférjenek egy vállalati alkalmazáshoz vagy fiókhoz. Ezek a vállalat által meghatározott adatáttelepítési és hozzáférési követelményekre vonatkozó beállítások például a feltört eszközök vagy a minimális operációsrendszer-verzió kezelésére.
 
Ezekkel a beállításokkal egyértelműen megadható az összes vállalati adat törlése a felhasználó eszközéről mint a nem megfelelőség esetén végrehajtandó művelet. Bizonyos beállításokhoz több művelet is konfigurálható, például a hozzáférés tiltása és az adatok törlése bizonyos megadott értékek alapján.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Hozzáférési műveleteket használó alkalmazásvédelmi szabályzat létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget.  
    Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** lehetőséget.
4. Kattintson a **Szabályzat hozzáadása** lehetőségre (a meglévő szabályzatok is módosíthatók). 
5. Kattintson a **Kötelező beállítások konfigurálása** lehetőségre a szabályzathoz konfigurálható beállítások listájának megjelenítéséhez. 
6. A **Beállítások** panelen lefelé görgetve megtalálja a **Hozzáférési műveletek** című szakaszt és egy szerkeszthető táblázatot.

    ![Képernyőkép az Intune alkalmazásvédelmi hozzáférési műveleteiről](./media/apps-selective-wipe-access-actions01.png)

7. Válasszon egy **Beállítást**, és adjon meg egy **Értéket**, amelynek a felhasználónak meg kell felelnie ahhoz, hogy bejelentkezhessen a vállalati alkalmazásába. 
8. Válassza ki a **Műveletet**, amelyet akkor kell végrehajtani, ha a felhasználó nem felel meg a követelményeknek. Bizonyos esetekben egy beállításhoz több művelet is megadható. További információt az [Alkalmazásvédelmi szabályzatok létrehozása és hozzárendelése](app-protection-policies.md) című cikkben talál.

>[!NOTE]
> Az **Eszközmodell(ek)** beállítás használatához gépelje be a modellazonosítók pontosvesszővel tagolt felsorolását. 

## <a name="policy-settings"></a>Szabályzatbeállítások 

Az alkalmazásvédelmi szabályzatbeállítások táblázata a **Beállítás**, **Érték** és **Művelet** oszlopokból áll.

iOS rendszeren a következő beállításokhoz konfigurálhat műveleteket a **Beállítások** legördülő lista használatával:
-  PIN-kód-megadási kísérletek maximális száma
-  Offline türelmi időszak
-  Függetlenített/feltört eszközök
-  Operációs rendszer minimális verziója
-  Alkalmazás minimális verziója
-  SDK minimális verziója
-  Eszközmodell(ek)

Android rendszeren a következő beállításokhoz konfigurálhat műveleteket a **Beállítások** legördülő lista használatával:
-  PIN-kód-megadási kísérletek maximális száma
-  Offline türelmi időszak
-  Függetlenített/feltört eszközök
-  Operációs rendszer minimális verziója
-  Alkalmazás minimális verziója
-  Minimális javításverzió
-  Eszközgyártó(k)

A táblázat néhány sora alapértelmezés szerint ki lesz töltve az **Offline türelmi időszak** és a **PIN-kód-megadási kísérletek maximális száma** beállítások konfigurációjával, ha a **PIN-kód megkövetelése a hozzáféréshez** beállítás **Igen** értékre van beállítva.
 
A beállítások konfigurálásához válasszon egy beállítást a **Beállítás** oszlop alatti legördülő listából. A beállítás kiválasztása után szerkeszthetővé válik az **Érték** oszlop alatti szövegmező, ha kötelező megadni egy értéket. Használhatóvá válik a **Művelet** oszlop alatti legördülő lista is, amely a beállításhoz tartozó feltételesen végrehajtható műveleteket tartalmazza. 

A következő lista a leggyakoribb műveleteket sorolja fel:
-  **Hozzáférés letiltása** – Letiltja a végfelhasználó hozzáférését a vállalati alkalmazáshoz.
-  **Összes adat törlése** – Az összes vállalati adat törlése a végfelhasználó eszközéről.
-  **Figyelmeztetés** – Figyelmeztető üzenetet jelenít meg a végfelhasználó számára.

### <a name="additional-settings-and-actions"></a>További beállítások és műveletek 

Bizonyos beállítások, például az **Operációs rendszer minimális verziója**, a különféle verziószámok alapján minden lehetséges műveletet végrehajtásához konfigurálhatók. 

![Képernyőkép az Intune alkalmazásvédelmi hozzáférési műveleteiről – Operációs rendszer minimális verziója](./media/apps-selective-wipe-access-actions05.png)

Ha egy beállítás teljesen konfigurálva van, akkor a sor megjelenik a csak olvasható nézetben, de bármikor módosítható. Ezen kívül megjelenik egy sor, amelyben új érték választható ki a **Beállítás** oszlopban. Azok a már konfigurált beállítások, amelyekhez nem adható meg több művelet, nem lesznek kiválaszthatók a legördülő listában.

## <a name="next-steps"></a>További lépések

Az Intune alkalmazásvédelmi szabályzatairól a következő helyeken tájékozódhat bővebben:
- [Alkalmazásvédelmi szabályzatok létrehozása és hozzárendelése](app-protection-policies.md)
- [iOS-eszközök alkalmazásvédelmi szabályzatainak beállításai](app-protection-policy-settings-ios.md)
- [Android-eszközök alkalmazásvédelmi szabályzatainak beállításai a Microsoft Intune-ban](app-protection-policy-settings-android.md) 


