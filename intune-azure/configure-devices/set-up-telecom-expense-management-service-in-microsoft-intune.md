---
title: "Távközlésiköltség-kezelő szolgáltatások beállítása"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A Saaswedo távközlésiköltség-kezelő szolgáltatás konfigurálása az Intune-nal való integráláshoz."
keywords: Saaswedo
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 7edbba3a86213db71e41bd0d0de6c5d285025b8b
ms.lasthandoff: 03/17/2017

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Távközlésiköltség-kezelő szolgáltatások beállítása az Azure-os Intune előzetes verziójában
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune segítségével kezelheti a vállalati tulajdonú mobileszközök adatforgalmából eredő távközlési költségeket. Ennek lehetővé tétele érdekében az Intune egy külső szoftverfejlesztő, a Saaswedo Datalert távközlésiköltség-kezelő megoldásával van integrálva. A Datalert olyan valós idejű távközlésiköltség-kezelő szoftver, amely módot ad a távközlési adatok használatának kezelésére, valamint segít elkerülni az adathasználati és a roamingkeret költséges és váratlan túllépését az Intune által felügyelt eszközökön. 

Az Intune és a Datalert integrációja lehetővé teszi, hogy központilag állítson be, figyeljen és alkalmazzon roaming- és belföldi adathasználati korlátokat automatikus riasztások használatával abban az esetben, ha a korlátok túllépnek meghatározott küszöbértékeket. A szolgáltatás konfigurálásával különféle műveleteket alkalmazhat személyekre vagy végfelhasználói csoportokra, például letilthatja a roamingot, ha a felhasználók túllépik a küszöbértéket. Az adathasználati és figyelési információkat biztosító jelentések a Datalert kezelőkonzolján érhetők el.

A következő ábra bemutatja, hogy milyen integráció áll fenn az Intune és a Datalert között.

  ![Az Intune és a Datalert integrációját bemutató ábra](../media/tem-datalert-intune-solution-diagram.png)

A Datalert szolgáltatásnak az Intune-nal való használatához beállításokat kell konfigurálnia a Datalert-konzolon és az Intune-ban. A kapcsolatot be kell kapcsolni a Datalert szolgáltatásban és az Intune-ban is. Ha a Datalert oldalán engedélyezve van a kapcsolat, az Intune oldalán viszont nincs, akkor az Intune fogadja ugyan a kommunikációt, de figyelmen kívül hagyja.

## <a name="supported-platforms"></a>Támogatott platformok

- Samsung KNOX
- iOS 8.0 és újabb verziók

## <a name="prerequisites"></a>Előfeltételek

- Microsoft Intune-előfizetés, valamint hozzáférés (a jelenleg nyilvános előzetes verziójú) Azure Portalhoz.
- Előfizetés a Datalert távközlésiköltség-kezelő szolgáltatásra

## <a name="list-of-telecom-expense-management-providers"></a>A távközlésiköltség-kezelő szolgáltatók listája

Az Intune jelenleg a következő távközlésiköltség-kezelő szolgáltatókkal képes együttműködni:

[Saaswedo Datalert távközlésiköltség-kezelő szolgáltatás](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Telepítse az integrált Intune és Datalert megoldást

Mielőtt hozzálát, győződjön meg róla, hogy van előfizetése az Intune-ra és a Datalert távközlésiköltség-kezelő szolgáltatásra.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>1. lépés: A Datalert szolgáltatás csatlakoztatása a Microsoft Intune-hoz

1. Jelentkezzen be a Datalert felügyeleti konzolra a rendszergazdai hitelesítő adataival.

2. A Datalert felügyeleti konzolon váltson a **Settings** (Beállítások) lapra, majd az **MDM configuration** (MDM-konfiguráció) területre.

3. Válassza a **Unblock** (Tiltás feloldása) lehetőséget, hogy megadhassa a beállításokat a lapon.

4. **Server MDM** (Kiszolgálói MDM) esetén válassza a **Microsoft Intune** elemet.

5. **Azure AD domain** (Azure AD-tartomány) esetén adja meg Azure-bérlőjének azonosítóját, majd válassza a **Connection** (Csatlakozás) gombot.

    Amikor a **Connection** (Csatlakozás) elemet választja, a Datalert szolgáltatás bejelentkezik az Intune-ba, hogy ellenőrizze, nincsenek-e már meglévő kapcsolatok a Datalert és az Intune között. Néhány másodperc elteltével megjelenik a Microsoft bejelentkezési oldala, amelyet a Datalert Azure-beli hitelesítése követ.

6. A Microsoft hitelesítési oldalán válassza az **Elfogadás** lehetőséget. Ekkor megnyílik a Datalert „thank you” („köszönjük”) lapja, amely néhány másodperc múlva bezárul. A Datalert ellenőrzi a kapcsolatot, majd az ellenőrzött elemek listája mellett zöld színű pipákat jelenít meg. Sikertelen ellenőrzés esetén piros színű üzenet jelenik meg. Ebben az esetben forduljon segítségért a Datalert ügyfélszolgálatához.

    A következő képernyőfelvételen a zöld pipák láthatók, amelyek a csatlakozás sikere esetén jelennek meg.

  ![A Datalert sikeres csatlakozást jelző lapja](../media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>2. lépés: Annak ellenőrzése, hogy aktív-e az Intune távközlésiköltség-kezelési funkciója

A fenti 1. lépés befejeződése után a kapcsolatnak elvben automatikusan engedélyezve kell lennie, és az Azure Portalon az **Aktív** kapcsolati állapotnak kell látszania. Ezek a lépések bemutatják, hogyan ellenőrizheti, **Aktív**-e az állapot.

1. Jelentkezzen be az Azure Portalra.

2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

3. Az **Intune** panelen válassza az **Eszközkonfiguráció** lehetőséget.

4. Az **Eszközkonfiguráció** panelen válassza a **Beállítás** > **Távközlési költségek kezelése** lehetőséget. 

   Keresse meg a lap tetején látható **Aktív** kapcsolati állapotot.

  ![Az Azure Portal, rajta az Aktív állapotú Datalert-kapcsolattal](../media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>3. lépés: A Datalert alkalmazás telepítése a vállalat regisztrált eszközeire

Ahhoz, hogy biztosan csak vállalati tulajdonú előfizetésekre vonatkozó adathasználati adatokat gyűjtsön, eszközkategóriákat kell létrehoznia az Intune-ban, és a Datalert alkalmazást csak a vállalati telefonokhoz kell hozzárendelnie. Végezze el az alábbi részekben ismertetett lépéseket.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Az eszközkategóriák és a kategóriákhoz rendelt eszközcsoportok definiálása

A szervezet szükségleteitől függően létre kell hoznia legalább két eszközkategóriát (például Vállalati és Saját tulajdonú), és dinamikus eszközcsoportokat kell meghatároznia mindkét kategóriához. Szükség esetén több kategóriát is létrehozhat a szervezet számára. 

Amikor a felhasználók regisztrálják az eszközeiket, látják ezeket a kategóriákat. Attól függően, hogy a felhasználó melyik kategóriát választja, a regisztrált eszköz a megfelelő eszközcsoportba kerül. Az eszközkategóriák létrehozásának lépéseit az [Eszközök hozzárendelése csoportokhoz](https://docs.microsoft.com/intune-azure/enroll-devices/how-to-use-device-group-mapping) című témakör ismerteti.

  ![Képernyőfelvétel a Szabályzat hozzáadása panelről](../media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>A Datalert alkalmazás létrehozása az Intune-ban

Hozza létre a Datalert alkalmazást mindegyik platformhoz az Intune-ban, a következő lépésekkel. Az ismertetett lépésekben az iOS-t használjuk példaként.

1. Válassza az Azure Portal **Intune** paneljének **Alkalmazásfelügyelet** elemét.

2. Az **Alkalmazásfelügyelet** területen válassza a **Kezelés** > **Alkalmazások** elemet. 

3. Vegyen fel egy alkalmazást a **Hozzáadás** gombra kattintva.

4. Válassza ki az alkalmazás típusát. iOS-esetében például az **iOS Store-alkalmazás** típust kell választani.

5. Keressen rá a Datalert alkalmazásra a **Keresés az App Store-ban** szolgáltatással. Ehhez írja be a **Datalert** nevet a keresőablakba.

6. Válassza ki a **Datalert** alkalmazást, és válassza az **OK** gombot.

  ![Képernyőfelvétel a Szabályzat hozzáadása panelről](../media/tem-select-app-from-apple-app-store.png)

7. Hozzon létre egy iOS-alkalmazást a hátralévő lépéseket követve.

  ![Képernyőfelvétel a Szabályzat hozzáadása panelről](../media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>A Datalert alkalmazás hozzárendelése a vállalati eszközök csoportjához

1. Válassza ki az előző lépésben létrehozott Datalert iOS-alkalmazást.

2. Az **Alkalmazások** panelen lépjen a **Kezelés** > **Feladatok** területre. 

3. Válassza a **Csoportok kiválasztása** elemet, és válassza ki a vállalati tulajdonú eszközök csoportját a lépéseknek megfelelően.

4. Adja meg, hogy kötelező-e vagy sem az alkalmazás telepítése a csoport számára. A példa képernyőfelvételen kötelező a telepítés. Ez azt jelenti, hogy a felhasználó köteles telepíteni a Datalert alkalmazást azután, hogy regisztrálja az eszközét.

  ![Képernyőfelvétel a Szabályzat hozzáadása panelről](../media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>4. lépés: Vállalati telefon-előfizetések felvétele a Datalert konzoljába 

Mostanra úgy konfigurálta az Intune és a Datalert szolgáltatást, hogy tudjanak kommunikálni egymással. Most fel kell vennie a vállalati telefon-előfizetéseket a Datalert konzoljába, és meg kell határoznia, hogy milyen küszöbértékek érvényesek a honos hálózaton és a roaming során való használatra, és milyen intézkedés történik a megszegésük esetén. 

A beállítások megadásához látogasson el a [Datalert setup for Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (A Datalert beállítása a Microsoft Intune-hoz) weblapra (http://www.datalert.fr/microsoft-intune/intune-setup), és kövesse a beállítási varázsló lépéseit a **Settings** (Beállítások) lapon.

  ![Képernyőfelvétel a Szabályzat hozzáadása panelről](../media/tem-add-phone-lines-to-datalert-console.png)


A Datalert szolgáltatás most már aktív, és megkezdi az adathasználat figyelését, valamint a mobil és roaming-adatforgalom letiltását azokon az eszközökön, amelyek túllépik a beállított használati korlátokat.

## <a name="turning-off-the-datalert-service"></a>A Datalert szolgáltatás kikapcsolása

Ha letiltja a Datalert szolgáltatást az Azure Portalon:

- A rendszer az eszközökön a használati korlátok korábbi túllépései miatt végrehajtott valamennyi műveletet visszavonja.
- A felhasználók számára ettől kezdve nincs letiltva az adathozzáférés és a roaming.
- Az Intune továbbra is fogadja a szolgáltatástól érkező jeleket, de figyelmen kívül hagyja őket.

**A szolgáltatás kikapcsolása**

1. Az Azure Portal **Távközlési költségek kezelése** paneljén válassza a **Letiltás** lehetőséget.

2. Válassza a **Mentés** lehetőséget.

## <a name="viewing-data-usage-and-roaming-reports"></a>Az adathasználati és roamingjelentések megtekintése

Az adathasználati jelentések jelenleg csak a Saaswedo Datalert kezelőkonzolján érhetők el.

Rövidesen közzétesszük a Datalert alkalmazás telepítését ismertető végfelhasználói útmutatót is.

