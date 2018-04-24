---
title: Alkalmazásvédelmi szabályzatok létrehozása és telepítése
titleSuffix: Microsoft Intune
description: A Microsoft Intune alkalmazásvédelmi szabályzatainak létrehozása és hozzárendelése.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ffe409e376ec2d15c537fb6ac258e5b3b71cdf2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Alkalmazásvédelmi szabályzatok létrehozása és hozzárendelése

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az alábbiakban azt ismertetjük, hogyan hozhat létre és rendelhet hozzá a Microsoft Intune-ban alkalmazásvédelmi szabályzatokat a felhasználók számára. A témakör a meglévő szabályzatok módosítását is ismerteti.

## <a name="before-you-begin"></a>Előkészületek

Ha a klasszikus Intune-portálon használható utasításokat keres, tekintse meg az [alkalmazásvédelmi szabályzatok létrehozását](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) ismertető cikket.

Az alkalmazásvédelmi szabályzatok alkalmazhatók a felügyelt és az Intune által nem felügyelt eszközökön futó alkalmazásokra is. Az alkalmazásvédelmi szabályzatok működésének és az Intune-os alkalmazásvédelmi szabályzatok által támogatott forgatókönyvek részletes ismertetését lásd: [A Microsoft Intune alkalmazásvédelmi szabályzatai](app-protection-policy.md).

Amennyiben az MAM által támogatott alkalmazások listáját keresi, lásd az [MAM alkalmazáslistáját](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

##  <a name="create-an-app-protection-policy"></a>Alkalmazásvédelmi szabályzat létrehozása
1. A **Mobilalkalmazások** munkafolyamatban a **Kezelés** szakaszban válassza az **Alkalmazásvédelmi szabályzatok** lehetőséget. Ekkor megnyílik az **Alkalmazásvédelmi szabályzatok** panel, amelyen új szabályzatokat hozhat létre, és szerkesztheti a meglévőket.
2. Válassza a **Szabályzat hozzáadása** elemet.

   ![Képernyőfelvétel a Szabályzat hozzáadása panelről](./media/app-protection-add-policy.png)

3. Írja be a szabályzat nevét, adjon meg egy rövid leírást, és válassza ki a szabályzat platformtípusát. Igény esetén platformonként egynél több szabályzatot is beállíthat.

4. Válassza az **Alkalmazások** elemet az **Alkalmazások panel** megnyitásához, ahol megjelenik a rendelkezésre álló alkalmazások listája. Egy vagy több alkalmazást is kijelölhet a listában a létrehozott szabályzattal való társításra.
5. Az alkalmazások kijelölése után a mentéshez válassza a **Kiválasztás** lehetőséget.

    > [!IMPORTANT]
    > Legalább egy alkalmazást ki kell jelölnie a szabályzat létrehozásához.

6. A **Beállítások** megnyitásához a **Szabályzat hozzáadása** panelen válassza a **Kötelező beállítások konfigurálása** elemet.

   A szabályzatbeállításoknak két kategóriájuk van, az **Adatáthelyezés** és a **Hozzáférés**.  Az adatáthelyezési szabályzatok az alkalmazások kimenő és bemenő adatforgalmára vonatkoznak. A hozzáférési szabályzatok a végfelhasználóknak az alkalmazásokhoz való hozzáférését határozzák meg munkahelyi környezetben.
   Használatuk megkönnyítése érdekében a szabályzatbeállításoknak alapértelmezett értékük van. Ha az alapértelmezett értékek megfelelnek az elvárásainak, nem szükséges változtatnia.

   > [!TIP]
   > A szabályzat beállításai csak akkor lépnek érvénybe, ha munkahelyi környezetben használják az alkalmazásokat. Ha a végfelhasználók az alkalmazást személyes célra használják, nem vonatkoznak rájuk a ezek szabályzatok.

7. A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Szabályzat hozzáadása** panelre. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.
8. A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Szabályzat hozzáadása** panelre.
9. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.

Ha az előző eljárásban leírtak szerint hozta létre a szabályzatot, az a felhasználók számára ekkor még nincs telepítve. A szabályzatok életbe léptetéséről a [Szabályzat telepítése a felhasználók számára](app-protection-policies.md#deploy-a-policy-to-users) című szakasz nyújt tájékoztatást.

## <a name="deploy-a-policy-to-users"></a>Szabályzat telepítése a felhasználók számára


1. Jelöljön ki egy szabályzatot az **Alkalmazásvédelmi szabályzatok** panelen.

1. A **Szabályzat** panelen válassza a **Hozzárendelések** elemet, amely megnyitja az **Intune App Protection – Hozzárendelések** panelt. A **Hozzárendelések** panelen válassza a **Belefoglalandó csoportok kijelölése** lehetőséget a **Belefoglalandó csoportok kijelölése** panel megnyitásához.

   ![Képernyőkép a Hozzárendelések panelről a Belefoglalandó csoportok kijelölése menüpont kiemelésével](./media/app-protection-policy-add-users.png)

2.  A **Felhasználói csoport hozzáadása** panelen megjelenik a felhasználói csoportok listája. Ezen a listán az **Azure Active Directory**összes biztonsági csoportja szerepel. Válassza ki azokat a felhasználói csoportokat, amelyekhez hozzá szeretné rendelni a szabályzatot, és válassza a **Kiválasztás** elemet. A **Kiválasztás** elem választásával telepítheti a szabályzatot a felhasználók számára.

    ![Képernyőkép: Az Azure Active Directory-felhasználók listája a Felhasználói csoportok hozzáadása panelen](./media/azure-ad-user-group-list.png)

A szabályzat ezzel létrejött, és telepítve lett a felhasználók számára.

A szabályzat csak a Microsoft Intune-licenccel rendelkező felhasználókra érvényes. A kijelölt biztonsági csoporthoz tartozó, Intune-licenccel nem rendelkező felhasználókra a szabályzat nem vonatkozik.

>[!IMPORTANT]
> Ha az Intune-ban és a Configuration Managerben kezeli az eszközöket, a szabályzat csak a kijelölt csoport közvetlen felhasználói esetében lép érvénybe. A csoportba ágyazott alárendelt csoportok tagjaira a szabályzat nem vonatkozik.

A végfelhasználók az App Store-ból vagy a Google Play áruházból tölthetik le az alkalmazásokat. További információkért lásd:
* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-android.md)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>A meglévő szabályzatok módosítása
A meglévő szabályzatokat szerkesztheti, és alkalmazhatja azokat a megcélzott felhasználókra. Ha azonban a meglévő szabályzatok módosításakor a felhasználók már be voltak jelentkezve az alkalmazásokba, csak egy 8 órás időszak elteltével láthatják a változtatásokat.

A változtatások hatásának érzékeléséhez a felhasználónak ki kell jelentkeznie az alkalmazásból, majd újból be kell jelentkeznie.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>A szabályzathoz társított alkalmazások listájának módosítása

1.  Az **Alkalmazásvédelmi szabályzatok** panelen a módosítani kívánt szabályzat kijelölésével megnyílik egy külön a kiválasztott szabályzathoz tartozó panel.

2.  Az alkalmazások listájának megnyitásához a szabályzat paneljén válassza a **Megcélzott alkalmazások** elemet.

3.  A listában eltávolíthat vagy hozzáadhat alkalmazásokat, és a **Mentés** ikont választva mentheti a módosításokat.

### <a name="to-change-the-list-of-user-groups"></a>A felhasználói csoportok listájának módosítása


1.  Az **Alkalmazásvédelmi szabályzatok** panelen a módosítani kívánt szabályzat kijelölésével megnyílik a kiválasztott szabályzathoz tartozó panel.

2.  A szabályzat paneljén a **Hozzárendelések** választásával nyissa meg az **Intune App Protection - Hozzárendelések** panelt, amelyen megjelenik azoknak a felhasználói csoportoknak a listája, amelyekre a szabályzat jelenleg érvényes.

3.  Új felhasználói csoportot úgy adhat hozzá a szabályzathoz, hogy a **Belefoglalás** lapon a **befoglalandó csoportok kijelölése** lehetőséget választja, majd kiválasztja a felhasználói csoportot. Válassza a **Kiválasztás** elemet, ha telepíteni szeretné a szabályzatot a kiválasztott csoport számára.

4.  Felhasználói csoportot úgy törölhet, hogy a **Kizárás** lapon a **Kizárandó csoportok kijelölése** lehetőséget választja, majd kiválasztja a felhasználói csoportot. A felhasználói csoport eltávolításához válassza a **Kiválasztás** lehetőséget.

### <a name="to-change-policy-settings"></a>A szabályzatbeállítások módosítása

1.  Az **Alkalmazásvédelmi szabályzatok** panelen a módosítani kívánt szabályzat kijelölésével megnyílik egy külön a kiválasztott szabályzathoz tartozó panel.

2.  Válassza a **Szabályzatbeállítások** elemet a **Szabályzatbeállítások** panel megnyitásához.

3.  Módosítsa a beállításokat, majd mentse a változtatásokat a **Mentés** ikonnal.

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Eszközkezelési állapottól függő alkalmazásvédelmi szabályzatok
Gyakori a szervezetekben, hogy a felhasználóknak engedélyezett mind a mobileszköz-kezelés (MDM) által felügyelt eszközök használata, mind pedig a nem felügyelt, csak az Intune alkalmazásvédelmi szabályzatok által védett eszközök használata, ideértve például a BYOD eszközöket.

Mivel az Intune alkalmazásvédelmi szabályzatok a felhasználói identitáshoz vannak társítva, a felhasználók védelmi beállításait a rendszer hagyományosan alkalmazza mind a regisztrált (MDM által felügyelt), mind pedig a regisztrálatlan (MDM nélküli) eszközökre. Emiatt lehetővé tettük annak megadását, hogy az Intune alkalmazásvédelmi szabályzatot az Intune-ban regisztrált vagy regisztrálatlan iOS- és Android-eszközökre kívánja-e alkalmazni. Használhat egy külön védelmi szabályzatot a nem felügyelt eszközökre szigorú adatveszteség-megelőzési (DLP) beállításokkal, illetve egy külön védelmi szabályzatot az MDM által felügyelt eszközökre kevésbé szigorú DLP-beállításokkal. 

Ezeknek a szabályzatoknak a létrehozásához lépjen a **Mobilalkalmazások** > **Alkalmazásvédelmi szabályzatok** területre az Intune-konzolon, és válassza a **Szabályzat hozzáadása** lehetőséget. Másik lehetőségként egy meglévő alkalmazásvédelmi szabályzatot is szerkeszthet. Ha az alkalmazásvédelmi szabályzatot a felügyelt és a felügyeletlen eszközökre egyaránt alkalmazni szeretné, akkor győződjön meg róla, hogy a **Target to all app types** (Alkalmazás minden alkalmazástípusra) beállításnál az **Igen** lehetőség van kiválasztva (mely az alapértelmezett érték). Ha a szabályzatot az eszközkezelési állapottól függően szeretné alkalmazni, állítsa a **Target to all app types** beállítást a **Nem** értékre. 

> [!NOTE]
> Ha kifejezetten iOS-eszközökre vonatkozó támogatási információkat keres az alkalmazásvédelmi szabályzatok eszközkezelési állapottól függő alkalmazásáról, lásd: [MAM-alapú védelmi szabályzatok alkalmazása eszközkezelési állapot alapján](whats-new.md#mam-protection-policies-targeted-based-on-management-state----1665993---).

## <a name="policy-settings"></a>Szabályzatbeállítások
Az iOS és az Android szabályzatbeállításait tartalmazó lista megtekintéséhez válasszon a következő hivatkozások közül:

- [iOS-szabályzatok](app-protection-policy-settings-ios.md)
- [Android-szabályzatok](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>További lépések
[A megfelelőség és a felhasználói állapot figyelése](app-protection-policies-monitor.md)

### <a name="see-also"></a>Lásd még:
* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-android.md)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-apps-ios.md)
