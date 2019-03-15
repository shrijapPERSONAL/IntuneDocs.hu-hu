---
title: Androidos eszközök regisztrálása az Intune-ban
titlesuffix: Microsoft Intune
description: Útmutató az Android-eszközök Intune-ban való regisztrálásához.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/31/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 486b5295d6ab4241cae90ef6ce0274fc93e0085e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57393241"
---
# <a name="enroll-android-devices"></a>Androidos eszközök regisztrálása

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune rendszergazdái az alábbi Android-eszközöket kezelhetik:
- Android-eszközök, beleértve a Samsung Knox Standard eszközöket is.
- Android Enterprise-eszközök, többek között:
    - **Vállalati munkahelyi profilos eszközök Android**: Személyes eszközök vállalati adatok elérésére vonatkozó engedélyt kaphatnak. Rendszergazdái kezelhetik a munkahelyi fiókok, alkalmazások és adatok. Személyes adatok az eszközön tárolt munkahelyi adatoktól és a rendszergazdák nem szabályozza a személyes beállításokat és adatokat. 
    - **Android Enterprise dedikált eszközök**: Vállalat által birtokolt, egyetlen eszközöket, például a digitális aláírási nyomtatás jegyet, vagy a szoftverleltár-kezelő. A rendszergazdák alkalmazások és webes hivatkozások egy adott körére korlátozzák az eszköz használatát. Ez azt is megakadályozza, hogy a felhasználók más alkalmazásokat adjanak az eszközhöz, vagy más műveleteket hajtsanak végre rajta.
    - **Android Enterprise teljes körűen felügyelt eszközök**: Vállalat által birtokolt, egyetlen felhasználói eszközök használt kizárólag a munkahelyi és személyes nem használja. A rendszergazdák a teljes eszköz kezelése és nem érhető el a munkahelyi profilok házirend-vezérlők kényszerítésére. 

## <a name="prerequisite"></a>Előfeltétel

A mobileszközök kezelésének előkészítéseként a **Microsoft Intune**-t kell beállítani mobileszköz-kezelő (MDM) szolgáltatóként. Erről [Az MDM-szolgáltató beállítása](mdm-authority-set.md) című cikk nyújt útmutatást. Ezt a beállítást csak egyszer, az Intune-nak a mobileszközök kezelésére való kezdeti beállítása során kell megadni.

## <a name="set-up-android-enrollment"></a>Az androidos eszközök regisztrálásának beállítása

Alapértelmezés szerint az Intune engedélyezi az Android és a Samsung Knox Standard rendszerű eszközök regisztrálását. Az előfeltételek teljesítését követően a rendszergazdáknak csupán [értesíteniük kell a felhasználókat arról, hogyan kell az eszközeiket regisztrálni](/intune-user-help/enroll-your-device-in-intune-android).

Miután a felhasználó elvégezte a regisztrálást, elkezdheti az eszközeik felügyeletét az Intune-ban, így többek között [megfelelőségi szabályzatokat rendelhet hozzájuk](compliance-policy-create-android.md) vagy [felügyelheti az alkalmazásokat](app-management.md).

Más felhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md)
- [Android-eszköz használata az Intune-nal](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Az androidos eszközök (vagy csak a személyes tulajdonban levők) regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című témakörben olvashat.

## <a name="set-up-android-enterprise-enrollment"></a>Az Android vállalati regisztrációjának beállítása

Android Enterprise tanúsítványigénylési beállításokat, amelyek biztosítható a felhasználók a legtöbb naprakészen tartását és védelmét a funkciók készletét kínálja. Androidos vállalati eszközregisztrációs lehetőségek közé tartozik a munkahelyi profilt, teljes körűen felügyelt, dedikált eszközök.

- [Android Enterprise munkahelyi profil regisztrációk beállítása](android-work-profile-enroll.md)
- [Dedikált Android Enterprise eszközregisztrációk beállítása](android-kiosk-enroll.md)
- [Állítsa be a teljes körűen felügyelt Android Enterprise-regisztrációk](android-fully-managed-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Végfelhasználói élmény Samsung Knox-eszköz regisztrálása során

Samsung Knox Standard-eszközökön az Intune többfelhasználós felügyelet támogatottak. Ez azt jelenti, hogy a végfelhasználók Azure AD-beli hitelesítő adataikkal jelentkezhetnek be az eszközökön. Az eszköz központilag felügyelt, függetlenül attól, hogy használatban van-e vagy sem. A bejelentkezett felhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. Amikor a felhasználók kijelentkezés összes alkalmazásadat törlődik.

A Samsung Knox-eszközök regisztrálása során több szempontot figyelembe kell venni:
-   Ha a szabályzatok nem követelnek PIN-kódot, az eszköznek akkor is egy legalább négyjegyű PIN-kódra lesz szüksége a regisztrációhoz. Ha az eszköznek nincs PIN-kódja, a felhasználónak létre kell hoznia egyet.
-   A Munkahelyi csatlakozás tanúsítványai (WPJ) esetében nincs felhasználói tevékenység.
-   A felhasználónak megjelennek a szolgáltatásregisztráció adatai, valamint az alkalmazás funkciói.
-   A felhasználónak megjelennek a Knox-regisztráció adatai, valamint a Knox funkciói.
-   Ha kényszerítve van egy titkosítási szabályzat, a felhasználóknak be kell állítaniuk egy legalább hat karakterből álló összetett jelszót az eszközön.
-   A vállalati erőforrás-hozzáférés szolgáltatásai által leküldött tanúsítványok esetében nincsenek további felhasználói telepítési kérések.
- Egyes régebbi Knox-eszközök további, vállalati erőforrás-hozzáféréshez használt tanúsítványokat kérhetnek a felhasználóktól.
- Ha egy Samsung Mini-eszköz nem tudja telepíteni a WPJ-t **A tanúsítvány nem található** vagy a **Nem sikerült regisztrálni az eszközt** hibák miatt, telepítse a Samsung-vezérlőprogramok legújabb frissítéseit.

## <a name="next-steps"></a>További lépések

- [Android Enterprise munkahelyi profil regisztrációk beállítása](android-work-profile-enroll.md)
- [Dedikált Android Enterprise eszközregisztrációk beállítása](android-kiosk-enroll.md)
- [Állítsa be a teljes körűen felügyelt Android Enterprise-regisztrációk](android-fully-managed-enroll.md)
