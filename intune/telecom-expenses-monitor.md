---
title: Távközlésiköltség-kezelő szolgáltatások beállítása
titleSuffix: Microsoft Intune
description: Az Intune integrálása a Saaswedo távközlésiköltség-kezelő szolgáltatással.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 031db83302dfef8b99fc83ab7975e233c3eeb799
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57396862"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Távközlésiköltség-kezelő szolgáltatás beállítása az Intune-ban
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Az Intune segítségével kezelheti a vállalati tulajdonú mobileszközök adatforgalmából eredő távközlési költségeket. Ennek érdekében az Intune egy külső szoftverfejlesztő, a Saaswedo [Datalert távközlésiköltség-kezelő](http://datalert.biz/get-started) megoldásával van integrálva. A Datalert egy valós idejű távközlésiköltség-kezelő szoftver, amellyel a távközlési adathasználatot kezelheti. A szoftverrel elkerülheti az Intune által kezelt eszközök költséges és váratlan kerettúllépéseit adatfogyasztásnál és roaming esetén.

Az Intune és a Datalert integrációja lehetővé teszi, hogy központilag állítson be, figyeljen és alkalmazzon roaming- és belföldi adathasználati korlátokat. Automatikus riasztások jelzik, ha a fogyasztások túllépnek meghatározott küszöbértékeket. A szolgáltatás konfigurálásával különféle műveleteket alkalmazhat személyekre vagy végfelhasználói csoportokra, például letilthatja a roamingot vagy a küszöbérték átlépését. Az adathasználati és figyelési információkat biztosító jelentések a Datalert kezelőkonzolján érhetők el.

A következő ábra bemutatja, hogy milyen integráció áll fenn az Intune és a Datalert között.

  ![Az Intune és a Datalert integrációját bemutató ábra](./media/tem-datalert-intune-solution-diagram.png)

A Datalert szolgáltatásnak az Intune-nal való használatához beállításokat kell konfigurálnia a Datalert-konzolon és az Intune-ban. A kapcsolatot be kell kapcsolni a Datalert szolgáltatásban és az Intune-ban is. Ha a Datalert oldalán engedélyezve van a kapcsolat, az Intune oldalán viszont nincs, akkor az Intune fogadja ugyan a kommunikációt, de figyelmen kívül hagyja.

## <a name="supported-platforms"></a>Támogatott platformok

- Samsung KNOX
- iOS 8.0 és újabb verziók

## <a name="prerequisites"></a>Előfeltételek

- Microsoft Intune-előfizetés és az Azure Portalhoz való hozzáférés.
- Előfizetés a Datalert távközlésiköltség-kezelő szolgáltatásra

## <a name="list-of-telecom-expense-management-providers"></a>A távközlésiköltség-kezelő szolgáltatók listája

Az Intune jelenleg a következő távközlésiköltség-kezelő szolgáltatókkal képes együttműködni:

[Saaswedo Datalert távközlésiköltség-kezelő szolgáltatás](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Telepítse az integrált Intune és Datalert megoldást

Mielőtt hozzálát, győződjön meg róla, hogy van előfizetése az Intune-ra és a Datalert távközlésiköltség-kezelő szolgáltatásra.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>1. lépés: A Datalert szolgáltatás csatlakoztatása a Microsoft Intune-bA

1. Jelentkezzen be a Datalert felügyeleti konzolra a rendszergazdai hitelesítő adataival.

2. A Datalert felügyeleti konzolon váltson a **Settings** (Beállítások) lapra, majd az **MDM configuration** (MDM-konfiguráció) területre.

3. A lap alján válassza az **Unblock** (Feloldás) lehetőséget, amely lehetővé teszi a lapon szereplő beállítások módosítását.

4. Az **Intune / Datalert Connection** (Intune/Datalert kapcsolat) szakaszban a **Server MDM** (Kiszolgálói MDM) értékeként válassza a **Microsoft Intune** lehetőséget.    

5. **Azure AD domain** (Azure AD-tartomány) mezőben adja meg Azure-bérlőjének azonosítóját, majd válassza a **Connection** (Csatlakozás) gombot.

    Amikor a **Connection** (Csatlakozás) elemet választja, a Datalert szolgáltatás bejelentkezik az Intune-ba, hogy ellenőrizze, nincsenek-e meglévő kapcsolatok a Datalert és az Intune között. Néhány másodperc elteltével megjelenik a Microsoft bejelentkezési oldala, amelyet a Datalert Azure-beli hitelesítése követ.

6. A Microsoft hitelesítési oldalán válassza az **Elfogadás** lehetőséget. Ekkor megnyílik a Datalert **thank you** (köszönjük) lapja, amely néhány másodperc múlva bezárul. A Datalert ellenőrzi a kapcsolatot, majd az ellenőrzött elemek listája mellett zöld színű pipákat jelenít meg. Ha az ellenőrzés nem sikerül, egy vörös üzenet jelenik meg. Vegye fel a kapcsolatot a Datalert ügyfélszolgálatával.

    A következő képernyőfelvételen a zöld pipák láthatók, amelyek a csatlakozás sikere esetén jelennek meg.

   ![A Datalert sikeres csatlakozást jelző lapja](./media/tem-datalert-connection.png)

7. A **Datalert App / ADAL Consent** (Datalert alkalmazás / ADAL hozzájárulás) szakaszban a kapcsolót állítsa **On** (Be) állapotba. A Microsoft hitelesítési oldalán válassza az **Elfogadás** lehetőséget. Ekkor megnyílik a Datalert **thank you** (köszönjük) lapja, amely néhány másodperc múlva bezárul. A Datalert ellenőrzi a kapcsolatot, majd az ellenőrzött elemek listája mellett zöld színű pipákat jelenít meg. Ha az ellenőrzés nem sikerül, egy vörös üzenet jelenik meg. Vegye fel a kapcsolatot a Datalert ügyfélszolgálatával.    

    A következő képernyőfelvételen a zöld pipák láthatók, amelyek a csatlakozás sikere esetén jelennek meg.

   ![A Datalert sikeres csatlakozást jelző lapja](./media/tem-datalert-adal-consent.png)

8. Az **MDM Profiles management (optional)** (MDM profilok felügyelete (nem kötelező)) szakaszban állítsa a kapcsolót **On** (Be) állapotba, hogy engedélyezze a Datalertnek az Intune-ban rendelkezésre álló profilok olvasását a szabályzatok létrehozásához. A Microsoft hitelesítési oldalán válassza az **Elfogadás** lehetőséget. Ekkor megnyílik a Datalert **thank you** (köszönjük) lapja, amely néhány másodperc múlva bezárul. A Datalert ellenőrzi a kapcsolatot, majd az ellenőrzött elemek listája mellett zöld színű pipákat jelenít meg. Ha az ellenőrzés nem sikerül, egy vörös üzenet jelenik meg. Vegye fel a kapcsolatot a Datalert ügyfélszolgálatával.    

    A következő képernyőfelvételen a zöld pipák láthatók, amelyek a csatlakozás sikere esetén jelennek meg.

   ![A Datalert sikeres csatlakozást jelző lapja](./media/tem-datalert-mdm-profiles.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>2. lépés: Ellenőrizze, hogy a távközlésiköltség-kezelési funkciója-e aktív az Intune-ban

A fenti 1. lépés befejeződése után a kapcsolatnak elvben automatikusan engedélyezve kell lennie, és az Azure Portalon az **Aktív** kapcsolati állapotnak kell látszania. Ezek a lépések bemutatják, hogyan ellenőrizheti, **Aktív**-e az állapot.

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).

2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.

3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.

4. Az **Eszközkonfiguráció** panelen válassza a **Beállítás** > **Távközlési költségek kezelése** lehetőséget.

   Keresse meg a lap tetején látható **Aktív** kapcsolati állapotot.

   ![Az Intune oldala, rajta az Aktív állapotú Datalert-kapcsolattal](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>3. lépés: A Datalert alkalmazás telepítése a vállalat regisztrált eszközeire

Ha biztosítani szeretné, hogy a rendszer csak a vállalati tulajdonú vonalakról gyűjtsön adathasználati adatokat, két dolgot kell tennie:
- hozzon létre eszközkategóriákat az Intune-ban
- korlátozza a Datalert alkalmazást kizárólag vállalati tulajdonú telefonokra.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Az eszközkategóriák és a kategóriákhoz rendelt eszközcsoportok definiálása

A cég szükségleteitől függően hozzon létre legalább két eszközkategóriát (például Vállalati és Saját tulajdonú). Ezután hozzon létre dinamikus eszközcsoportokat minden kategóriához. Szükség esetén több kategóriát is létrehozhat a szervezet számára.

Amikor a felhasználók regisztrálják az eszközeiket, látják ezeket a kategóriákat. Attól függően, hogy a felhasználó melyik kategóriát választja, a regisztrált eszköz a megfelelő eszközcsoportba kerül. Az eszközkategóriák létrehozásának lépéseit az [Eszközök hozzárendelése csoportokhoz](device-group-mapping.md) című témakör ismerteti.

  ![Képernyőkép a Szabályzat hozzáadása panelről](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>A Datalert alkalmazás létrehozása az Intune-ban

Hozza létre a Datalert alkalmazást mindegyik platformhoz az Intune-ban, a következő lépésekkel. Az ismertetett lépésekben az iOS-t használjuk példaként.

1. Válassza az [Azure Portal](https://portal.azure.com) **Intune** paneljének **Ügyfélalkalmazások** elemét.

2. Az **Ügyfélalkalmazások** területen válassza a **Kezelés** > **Alkalmazások** elemet.

3. Vegyen fel egy alkalmazást a **Hozzáadás** gombra kattintva.

4. Válassza ki az alkalmazás típusát. iOS-esetében például az **iOS Store-alkalmazás** típust kell választani.

5. Keressen rá a Datalert alkalmazásra a **Keresés az App Store-ban** szolgáltatással. Ehhez írja be a **Datalert** nevet a keresőablakba.

6. Válassza ki a **Datalert** alkalmazást, és majd a **Kiválasztás** lehetőséget.

   ![Képernyőkép a Szabályzat hozzáadása panelről](./media/tem-select-app-from-apple-app-store.png)

7. Hozzon létre egy iOS-alkalmazást a hátralévő lépéseket követve.

   ![Képernyőkép a Szabályzat hozzáadása panelről](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>A Datalert alkalmazás hozzárendelése a vállalati eszközök csoportjához

1. Az **Ügyfélalkalmazások – Alkalmazások** panelen válassza ki az előző lépésben létrehozott Datalert iOS-alkalmazást.

2. Az **Alkalmazások** panelen válassza a **Kezelés** > **Hozzárendelések** elemet.

3. Válassza a **Csoport hozzáadása** lehetőséget, és válassza ki a vállalati tulajdonú eszközök csoportját a lépéseknek megfelelően.

4. Adja meg, hogy kötelező-e vagy sem az alkalmazás telepítése a csoport számára. A példa képernyőfelvételen kötelező a telepítés. Ez azt jelenti, hogy a felhasználó köteles telepíteni a Datalert alkalmazást azután, hogy regisztrálja az eszközét.

   ![Képernyőkép a Szabályzat hozzáadása panelről](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>4. lépés: Adja hozzá a Vállalati telefon-előfizetéseket a Datalert konzoljába

Mostanra úgy konfigurálta az Intune és a Datalert szolgáltatást, hogy tudjanak kommunikálni egymással. Most fel kell vennie a vállalati telefon-előfizetéseket a Datalert konzoljába, és meg kell határoznia, hogy milyen küszöbértékek érvényesek a honos hálózaton és a roaming során való használatra, és milyen intézkedés történik a megszegésük esetén. A vállalati telefon-előfizetéseket manuálisan is felveheti a Datalert konzoljába, vagy megvárhatja, hogy az eszköz Intune-regisztrációja után azok automatikusan fel legyenek véve.

A beállítások megadásához látogasson el a [Datalert setup for Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (A Datalert beállítása a Microsoft Intune-hoz, http://www.datalert.fr/microsoft-intune/intune-setup)) weblapra, és kövesse a beállítási varázsló lépéseit a **Settings** (Beállítások) lapon.

  ![Képernyőkép a Szabályzat hozzáadása panelről](./media/tem-add-phone-lines-to-datalert-console.png)


A Datalert szolgáltatás most már aktív, és megkezdi az adathasználat figyelését, valamint a mobil és roaming-adatforgalom letiltását azokon az eszközökön, amelyek túllépik a beállított használati korlátokat.

## <a name="client-enrollment-experience"></a>Ügyfél-regisztrációs folyamat
Az ügyfél-regisztrációs folyamattal kapcsolatosan az alábbi információkat ajánljuk figyelmébe:
-   [iOS-eszköz regisztrálása a távközlésiköltség-kezelőben](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [Android-eszköz regisztrálása a távközlésiköltség-kezelőben](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>A Datalert szolgáltatás kikapcsolása

Ha letiltja a Datalert szolgáltatást az Azure Portalon:

- A rendszer az eszközökön a használati korlátok korábbi túllépései miatt végrehajtott valamennyi műveletet visszavonja.
- A felhasználók számára ettől kezdve nincs letiltva az adathozzáférés és a roaming.
- Az Intune továbbra is fogadja a szolgáltatástól érkező jeleket, de figyelmen kívül hagyja őket.

**A szolgáltatás kikapcsolása**

1. Az Azure Portal **Távközlési költségek kezelése** paneljén válassza a **Letiltás** lehetőséget.

2. Kattintson a **Mentés** gombra.

## <a name="viewing-data-usage-and-roaming-reports"></a>Az adathasználati és roamingjelentések megtekintése

Az adathasználati jelentések jelenleg csak a Saaswedo Datalert kezelőkonzolján érhetők el.

Rövidesen közzétesszük a Datalert alkalmazás telepítését ismertető végfelhasználói útmutatót is.
