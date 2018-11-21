---
title: Androidos eszközök regisztrálása az Intune-ban
titlesuffix: Microsoft Intune
description: Útmutató az Android-eszközök Intune-ban való regisztrálásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2b2b3ba5443cd95cd81bdca6d386ab95a2c831eb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190115"
---
# <a name="enroll-android-devices"></a>Androidos eszközök regisztrálása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune rendszergazdái az alábbi Android-eszközöket kezelhetik:
- Android-eszközök, beleértve a Samsung Knox Standard eszközöket is.
- Vállalati androidos eszközök, beleértve az [androidos munkahelyi profilos eszközöket](#enable-enrollment-of-android-for-work-devices) és az androidos kioszkos eszközöket is.

A Samsung KNOX Standard rendszerű eszközökön használható az Intune többfelhasználós felügyelete. Ez azt jelenti, hogy a végfelhasználók Azure AD-beli hitelesítő adataikkal jelentkezhetnek be az eszközökön. Az eszköz központilag felügyelt, függetlenül attól, hogy használatban van-e vagy sem. A bejelentkezett felhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.

## <a name="prerequisite"></a>Előfeltétel

A mobileszközök kezelésének előkészítéseként a **Microsoft Intune**-t kell beállítani mobileszköz-kezelő (MDM) szolgáltatóként. Erről [Az MDM-szolgáltató beállítása](mdm-authority-set.md) című cikk nyújt útmutatást. Ezt a beállítást csak egyszer, az Intune-nak a mobileszközök kezelésére való kezdeti beállítása során kell megadni.

## <a name="set-up-android-enrollment"></a>Az androidos eszközök regisztrálásának beállítása

Alapértelmezés szerint az Intune engedélyezi az Android és a Samsung Knox Standard rendszerű eszközök regisztrálását. Az előfeltételek teljesítését követően a rendszergazdáknak csupán [értesíteniük kell a felhasználókat arról, hogyan kell az eszközeiket regisztrálni](/intune-user-help/enroll-your-device-in-intune-android).

Miután a felhasználó elvégezte a regisztrálást, elkezdheti az eszközeik felügyeletét az Intune-ban, így többek között [megfelelőségi szabályzatokat rendelhet hozzájuk](compliance-policy-create-android.md) vagy [felügyelheti az alkalmazásokat](app-management.md).

Más felhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md)
- [Android-eszköz használata az Intune-nal](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Az androidos eszközök (vagy csak a személyes tulajdonban levők) regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című témakörben olvashat.

## <a name="set-up-android-enterprise-enrollment"></a>Vállalati Android-regisztráció beállítása

A vállalati Android Android-eszközökhöz készült funkciók és szolgáltatások együttese, amelyek elkülönítik a személyes alkalmazásokat és adatokat a munkahelyi alkalmazásokat és adatokat tartalmazó munkahelyi profiltól. Vállalati androidos eszközök lehetnek androidos munkahelyi profilos eszközöket és androidos kioszkos eszközök is. 

Mielőtt beállítaná a vállalati androidos eszközök regisztrációját, először [csatlakoztatnia kell a vállalati Androidot az Intune-hoz](connect-intune-android-enterprise.md). Ha ezzel a lépéssel végzett, az alábbi lehetőségek lesznek elérhetőek:

[Androidos munkahelyi profilos regisztrációk beállítása](android-work-profile-enroll.md)
[Androidos kioszkos regisztrációk beállítása](android-kiosk-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Végfelhasználói élmény Samsung Knox-eszköz regisztrálása során
A Samsung Knox-eszközök regisztrálása során több szempontot figyelembe kell venni:
-   Ha a szabályzatok nem követelnek PIN-kódot, az eszköznek akkor is egy legalább négyjegyű PIN-kódra lesz szüksége a regisztrációhoz. Ha az eszköznek nincs PIN-kódja, a felhasználónak létre kell hoznia egyet.
-   A Munkahelyi csatlakozás tanúsítványai (WPJ) esetében nincs felhasználói tevékenység.
-   A felhasználónak megjelennek a szolgáltatásregisztráció adatai, valamint az alkalmazás funkciói.
-   A felhasználónak megjelennek a Knox-regisztráció adatai, valamint a Knox funkciói.
-   Ha kényszerítve van egy titkosítási szabályzat, a felhasználóknak be kell állítaniuk egy legalább hat karakterből álló összetett jelszót az eszközön.
-   A vállalati erőforrás-hozzáférés szolgáltatásai által leküldött tanúsítványok esetében nincsenek további felhasználói telepítési kérések.
- Egyes régebbi Knox-eszközök további, vállalati erőforrás-hozzáféréshez használt tanúsítványokat kérhetnek a felhasználóktól.
- Ha egy Samsung Mini-eszköz nem tudja telepíteni a WPJ-t **A tanúsítvány nem található** vagy a **Nem sikerült regisztrálni az eszközt** hibák miatt, telepítse a Samsung-vezérlőprogramok legújabb frissítéseit.
