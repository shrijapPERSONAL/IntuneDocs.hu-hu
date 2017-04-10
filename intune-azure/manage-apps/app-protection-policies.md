---
title: "Alkalmazásvédelmi szabályzatok létrehozása és telepítése"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: A felügyelt alkalmazások által használt céges adatok védelme Intune-os alkalmazásvédelmi szabályzatok segítségével."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 607598812a414843f1f33a00670a6a85b6687878
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-create-and-assign-app-protection-policies"></a>Alkalmazásvédelmi szabályzatok létrehozása és hozzárendelése

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Ha nem az Azure Portal előzetes programjában szereplő Intune szolgáltatást használja**, ez a témakör ismerteti az [alkalmazásvédelmi szabályzatok létrehozását](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) a klasszikus Intune-konzolon.

Az alkalmazásvédelmi szabályzatok alkalmazhatók a felügyelt és az Intune által nem felügyelt eszközökön futó alkalmazásokra is. Az alkalmazásvédelmi szabályzatok működésének és az Intune-os alkalmazásvédelmi szabályzatok által támogatott forgatókönyvek részletes ismertetését lásd: [A Microsoft Intune alkalmazásvédelmi szabályzatai](what-is-app-protection-policy.md).

##  <a name="create-an-app-protection-policy"></a>Alkalmazás védelmi szabályzat létrehozása
1.  Az **Alkalmazásfelügyelet** számítási feladatnál válassza a **Kezelés** > **Alkalmazásvédelmi szabályzatok** lehetőséget.

2.  Ekkor megnyílik az **Alkalmazásvédelmi szabályzatok** panel, amelyen új szabályzatokat hozhat létre, és szerkesztheti a meglévő szabályzatokat. Válassza a **Szabályzat hozzáadása** elemet.

  ![Képernyőfelvétel a Szabályzat hozzáadása panelről](../media/app-protection-add-policy.png)

3.  Írja be a szabályzat nevét, adjon meg egy rövid leírást, és válassza ki platform típusát az iOS- vagy Android-alapú szabályzat létrehozásához. Az egyes platformokon egynél több szabályzatot is beállíthat.

4.  Válassza az **Alkalmazások** elemet az **Alkalmazások panel** megnyitásához, ahol megjelenik a rendelkezésre álló alkalmazások listája. Egy vagy több alkalmazást is kijelölhet a listában a létrehozott szabályzattal való társításra. Ha kiválasztotta az alkalmazásokat, mentse őket az **Alkalmazások** panel alján található **Kiválasztás** gombbal.

    > [!IMPORTANT]
    > Legalább egy alkalmazást ki kell jelölnie a szabályzat létrehozásához.

5.  A **Szabályzat hozzáadása** panelen kattintson a **Kötelező beállítások konfigurálása** elemre a szabályzatbeállítási panel megnyitásához.

    A szabályzatbeállításoknak két kategóriájuk van, az **Adatáthelyezés** és a **Hozzáférés**.  Az adatáthelyezési szabályzatok az alkalmazások mindkét irányú adatátvitelére vonatkoznak. A hozzáférési szabályzatok meghatározzák, hogyan érheti el a végfelhasználó az alkalmazásokat munkahelyi környezetben.
    Használatuk megkönnyítése érdekében a szabályzatbeállításoknak alapértelmezett értékük van. Nem szükséges változtatnia, ha az alapértelmezett értékek megfelelnek az elvárásainak.

    > [!TIP]
    > A szabályzat beállításai csak akkor lépnek érvénybe, ha munkahelyi környezetben használják az alkalmazásokat.  Amikor a végfelhasználó az alkalmazást személyes feladatra használja, nem vonatkoznak rá a szabályzatok.



6.  A konfiguráció mentéséhez válassza az **OK** gombot. Ekkor visszakerül a **Szabályzat hozzáadása** panelbe. Válassza a **Létrehozás** lehetőséget a szabályzat létrehozásához és a beállítások mentéséhez.


Ha az előző eljárásban leírtak szerint hozta létre a szabályzatot, az a felhasználók számára ekkor még nincs telepítve. A szabályzatok életbe léptetéséről a következő, „Szabályzat telepítése a felhasználók számára” című szakasz nyújt tájékoztatást.

## <a name="deploy-a-policy-to-users"></a>Szabályzat telepítése a felhasználók számára

1.  A **Szabályzat** panelen válassza a **Felhasználói csoportok** elemet a **Felhasználói csoportok** panel megnyitásához. Válassza a **Felhasználói csoport hozzáadása** elemet a **Felhasználói csoportok** panelen a **Felhasználói csoport hozzáadása** panel megnyitásához.

  ![A kijelölt Felhasználói csoport hozzáadása menüpont a Felhasználói csoportok panelen – képernyőfelvétel](../media/app-protection-policy-add-users.png)

2.  A **Felhasználói csoport hozzáadása** panelen megjelenik a felhasználói csoportok listája. Ezen a listán az **Azure Active Directory**összes biztonsági csoportja szerepel. Válassza ki azokat a felhasználói csoportokat, amelyekhez hozzá szeretné rendelni a szabályzatot, és válassza a **Kiválasztás** elemet. A **Kiválasztás** elem választásával telepítheti a szabályzatot a felhasználók számára.
  ![Az Azure Active Directory-felhasználók listája a Felhasználói csoportok hozzáadása panelen – képernyőfelvétel](../media/azure-ad-user-group-list.png)

A szabályzat ezzel létrejött, és telepítve lett a felhasználók számára.

A szabályzat csak a Microsoft Intune-licenccel rendelkező felhasználókra érvényes. A kijelölt biztonsági csoport Microsoft Intune-licenc nélküli felhasználóira nem vonatkozik a szabályzat.

>[!IMPORTANT]
> Ha az Intune-ban és a Configuration Managerben kezeli az iOS- és Android-eszközöket, a szabályzatok csak a közvetlenül kijelölt csoport felhasználói esetében lépnek érvénybe. A csoportba ágyazott alárendelt csoportok tagjaira nem vonatkozik a szabályzat.

A végfelhasználók az App Store-ból vagy a Google Play áruházból tölthetik le az alkalmazásokat. További információkért lásd:
* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-android-apps.md)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-ios-apps.md)

##  <a name="change-existing-policies"></a>A meglévő szabályzatok módosítása
A meglévő szabályzatokat szerkesztheti, és alkalmazhatja azokat a megcélzott felhasználókra. Ha azonban a meglévő szabályzatok módosításakor a felhasználók már be voltak jelentkezve az alkalmazásokba, csak egy 8 órás időszak elteltével láthatják a változtatásokat.

A változtatások hatásának megfigyeléséhez a felhasználónak ki kell jelentkeznie az alkalmazásból, majd újból be kell jelentkeznie.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>A szabályzathoz társított alkalmazások listájának módosítása

1.  Az **Alkalmazásszabályzat** panelen válassza ki a módosítani kívánt szabályzatot. Ekkor megnyílik a kiválasztott szabályzat tulajdonságait tartalmazó panel.

2.  A szabályzat paneljén válassza a **Megcélzott alkalmazások** elemet az alkalmazások listájának megnyitásához.

3.  A listában eltávolíthat vagy hozzáadhat alkalmazásokat, és a **Mentés** ikont választva mentheti a módosításokat.

### <a name="to-change-the-list-of-user-groups"></a>A felhasználói csoportok listájának módosítása

1.  Az **Alkalmazásszabályzat** panelen válassza ki a módosítani kívánt szabályzatot. Ekkor megnyílik a kiválasztott szabályzat tulajdonságait tartalmazó panel.

2.  A szabályzat paneljén válassza a **Felhasználói csoportok** elemet a **Felhasználói csoport** panel megnyitásához. Itt láthatja azokat a felhasználói csoportokat, amelyekre érvényes a szabályzat.

3.  Ha a szabályzathoz új felhasználói csoportot szeretne felvenni, válassza a **Felhasználói csoport hozzáadása** elemet, és válasszon felhasználói csoportot. Válassza a **Kiválasztás** elemet, ha telepíteni szeretné a szabályzatot a kiválasztott csoport számára.

4.  Ha törölni szeretne egy felhasználócsoportot, jelölje ki. Ezután válassza a három pontot (...), végül a **Törlés** elemmel törölje a felhasználócsoportot.
  ![A Törlés elemet ábrázoló képernyőfelvétel](../media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>A szabályzatbeállítások módosítása

1.  Az **Alkalmazásszabályzat** panelen válassza ki a módosítani kívánt szabályzatot. Ekkor megnyílik a kiválasztott szabályzat tulajdonságait tartalmazó panel.


2.  Válassza a **Szabályzatbeállítások** elemet a **Szabályzatbeállítások** panel megnyitásához.

3.  Módosítsa a beállításokat, majd mentse a változtatásokat a **Mentés** ikonnal.

## <a name="policy-settings"></a>Szabályzatbeállítások
Az iOS és az Android szabályzatbeállításait tartalmazó lista megtekintéséhez válasszon a következő lehetőségek közül:

> [!div class="op_single_selector"]
- [iOS-szabályzatok](ios-app-protection-policy-settings.md)
- [Android-szabályzatok](android-app-protection-policy-settings.md)

## <a name="next-steps"></a>További lépések
[A megfelelőség és a felhasználói állapot figyelése](monitor-app-protection-policies-with-microsoft-intune.md)

### <a name="see-also"></a>További információ
* [Milyen hatással vannak az androidos alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-android-apps.md)
* [Milyen hatással vannak az iOS-es alkalmazásokra az alkalmazásvédelmi szabályzatok?](app-protection-enabled-ios-apps.md)

