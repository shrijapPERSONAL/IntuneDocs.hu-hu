---
title: Intune-adattárház – módosítási napló
titleSuffix: Microsoft Intune
description: Ez a témakör biztosít a Microsoft Intune-adattárház API módosítások listája olvasható.
keywords: Intune-adattárház
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/11/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30f315f58a905e690a43ab3c44aee783bd0ef8c9
ms.sourcegitcommit: a2cd14c30949cef17bfc6576513e7660a8015669
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/15/2019
ms.locfileid: "59571807"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Az Intune-adattárház API módosítási naplója

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Maradjon naprakész az Intune-adattárház frissítéseivel kapcsolatban.

## <a name="1903-part-2"></a>1903 (2. rész)
_Kiadás dátuma: április 2019_

### <a name="beta-changes"></a>Bétaverzió módosítások

A következő táblázat felsorolja a legutóbbi eltávolított gyűjtemények és az Intune-adattárház a lecserélendő gyűjtemény.

|    Gyűjtemény                          |    Módosítás     |    További információ                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    mobileAppDeviceUserInstallStatus    |    Eltávolítva    |    Használat [mobileAppInstallStatusCounts](intune-data-warehouse-collections.md#mobileappinstallstatuscounts) helyette.                                                                                                                                                                                                                                                                     |
|    EnrollmentTypes                     |    Eltávolítva    |    Használat [deviceEnrollmentTypes](intune-data-warehouse-collections.md#deviceenrollmenttypes) helyette.                                                                                                                                                                                                                                                                                      |
|    mdmStatuses                         |    Eltávolítva    |    Használat [complianceStates](intune-data-warehouse-collections.md#compliancestates) helyette.                                                                                                                                                                                                                                                                                               |
|    workPlaceJoinStateTypes             |    Eltávolítva    |    Használja a `azureAdRegistered` tulajdonságot a [eszközök](intune-data-warehouse-collections.md#devices) és [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) gyűjtemények helyett.                                                                                                                                                                                                             |
|    clientRegistrationStateTypes        |    Eltávolítva    |    Használat [deviceRegistrationStates](intune-data-warehouse-collections.md#deviceregistrationstates) helyette.                                                                                                                                                                                                                                                                             |
|    currentUser                         |    Eltávolítva    |    Használja a [felhasználók](intune-data-warehouse-collections.md#users) gyűjtemény helyett.                                                                                                                                                                                                                                                                                                      |
|    mdmDeviceInventoryHistories         |    Eltávolítva    |    Sok tulajdonság redundáns volt, vagy lehet, hogy most már a található a [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) vagy [eszközök](intune-data-warehouse-collections.md#devices) gyűjteményeket. Bármely **mdmDeviceInventoryHistories** már nem érhetők el a következő két gyűjteményekhez még nem szereplő tulajdonságokat. A részleteket alább találja.    |

A következő táblázat felsorolja a régi tulajdonságokat korábban a **mdmDeviceInventoryHistories** adatgyűjtési és -módosítás/váltja fel. Szereplő tulajdonságokat **mdmDeviceInventoryHistories** , de nem szerepel a listán az alábbiakban el lettek távolítva.

|    Régi tulajdonság                |    Módosítás/cseréje                                                           |
|--------------------------------|---------------------------------------------------------------------------------|
|    CellularTechnology          |    az eszközök gyűjteményére cellularTechnology                                     |
|    deviceClientId              |    az eszközök gyűjteményét az eszközazonosító                                               |
|    deviceManufacturer          |    az eszközök gyűjteményére gyártója                                           |
|    deviceModel                 |    az eszközök gyűjteményére modell                                                  |
|    deviceName                  |    az eszközök gyűjteményére eszköznév                                             |
|    deviceOsPlatform            |    az eszközök gyűjteményére deviceTypeKey                                          |
|    deviceOsVersion             |    osVersion devicePropertyHistories gyűjteményben                              |
|    deviceType                  |    az eszközök gyűjteményét, deviceTypes gyűjtemény hivatkozó deviceTypeKey    |
|    encryptionState             |    az eszközök gyűjteményben encryptionState tulajdonság                           |
|    exchangeActiveSyncId        |    az eszközök gyűjteményben easDeviceId tulajdonság                               |
|    exchangeDeviceId            |    az eszközök gyűjteményére easDeviceId                                            |
|    IMEI                        |    imei-eszközök gyűjteményét az                                                   |
|    isSupervised                |    az eszközök gyűjteményben isSupervised tulajdonság                              |
|    jailBroken                  |    feltört devicePropertyHistories gyűjteményben                             |
|    MEID                        |    az eszközök gyűjteményben meid tulajdonság                                      |
|    oem                         |    az eszközök gyűjteményére gyártója                                           |
|    osName                      |    az eszközök gyűjteményét, deviceTypes gyűjtemény hivatkozó deviceTypeKey    |
|    phoneNumber                 |    az eszközök gyűjteményére telefonszám                                            |
|    platformType                |    az eszközök gyűjteményére modell                                                  |
|    A termék                     |    az eszközök gyűjteményére deviceTypeKey                                          |
|    ProductVersion              |    osVersion devicePropertyHistories gyűjteményben                              |
|    serialNumber                |    serialNumber eszközök gyűjtemény                                           |
|    storageFree                 |    az eszközök gyűjteményben freeStorageSpaceInBytes tulajdonság                   |
|    StorageTotal                |    az eszközök gyűjteményben totalStorageSpaceInBytes tulajdonság                |
|    SubscriberCarrierNetwork    |    az eszközök gyűjteményben subscriberCarrier tulajdonság                         |
|    wifimac                     |    az eszközök gyűjteményére wiFiMacAddress                                         |

A következő táblázatban található a tulajdonságainak módosításait a [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) gyűjtemény: 

|    Régi tulajdonság                  |    Módosítás/cseréje                                               |
|----------------------------------|---------------------------------------------------------------------|
|    CategoryId                    |    deviceCategoryKey, hivatkozó deviceCategories gyűjtemény       |
|    certExpirationDate            |    Eltávolítva                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    az eszközök gyűjteményére enrolledDateTime                           |
|    deviceTypeKey                 |    az eszközök gyűjteményére deviceTypeKey                              |
|    EasID                         |    az eszközök gyűjteményére easDeviceId                                |
|    EnrolledByUser                |    eszközök gyűjteményben szereplő felhasználói azonosító                                     |
|    enrollmentTypeKey             |    az eszközök gyűjteményére deviceEnrollmentTypeKey                    |
|    graphDeviceIsCompliant        |    Eltávolítva                                                          |
|    graphDeviceIsManaged          |    Eltávolítva                                                          |
|    LastContact                   |    az eszközök gyűjteményére lastSyncDateTime                           |
|    LastContactNotification       |    Eltávolítva                                                          |
|    lastContactWorkplaceJoin      |    Eltávolítva                                                          |
|    lastExchangeStatusUtc         |    Eltávolítva                                                          |
|    lastModifiedDateTimeUTC       |    Eltávolítva                                                          |
|    lastPolicyUpdateUtc           |    Eltávolítva                                                          |
|    managementAgentKey            |    managementStateKey                                               |
|    gyártó                  |    az eszközök gyűjteményére gyártója                               |
|    mdmStatusKey                  |    complianceStateKey, hivatkozó complianceStates gyűjtemény    |
|    modell                         |    az eszközök gyűjteményére modell                                      |
|    operációsrendszer-család                      |    eszközök gyűjteményét az operációs rendszer                            |
|    osRevisionNumber              |    eszközök gyűjteményét az osVersion                                  |
|    Processzorarchitektúra         |    Eltávolítva                                                          |
|    referenceId                   |    az eszközök gyűjteményére azureAdDeviceId                            |
|    serialNumber                  |    serialNumber eszközök gyűjtemény                               |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

A következő táblázatban található a tulajdonságainak módosításait a [eszközök](intune-data-warehouse-collections.md#devices) gyűjtemény: 

|    Régi tulajdonság                  |    Módosítás/cseréje                                               |
|----------------------------------|---------------------------------------------------------------------|
|    CategoryId                    |    deviceCategoryKey, hivatkozó deviceCategories gyűjtemény       |
|    certExpirationDate            |    Eltávolítva                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime                                                 |
|    easId                         |    easDeviceId                                                      |
|    EnrolledByUser                |    userId                                                           |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey                                          |
|    graphDeviceIsCompliant        |    Eltávolítva                                                          |
|    graphDeviceIsManaged          |    Eltávolítva                                                          |
|    LastContact                   |    lastSyncDateTime                                                 |
|    LastContactNotification       |    Eltávolítva                                                          |
|    lastContactWorkplaceJoin      |    Eltávolítva                                                          |
|    lastExchangeStatusUtc         |    Eltávolítva                                                          |
|    lastPolicyUpdateUtc           |    Eltávolítva                                                          |
|    mdmStatusKey                  |    complianceStateKey, hivatkozó complianceStates gyűjtemény    |
|    operációsrendszer-család                      |    operatingSystem                                                  |
|    Processzorarchitektúra         |    Eltávolítva                                                          |
|    referenceId                   |    azureAdDeviceId                                                  |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

A következő táblázatban található a tulajdonságainak módosításait a [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities) gyűjtemény: 

|    Régi tulajdonság         |    Módosítás/cseréje         |
|-------------------------|-------------------------------|
|    enrollmentTypeKey    |    deviceEnrollmentTypeKey    |

A következő táblázatban található a tulajdonságainak módosításait a [mamApplications](intune-data-warehouse-collections.md#mamapplications) gyűjtemény: 

|    Régi tulajdonság       |    Módosítás/cseréje    |
|-----------------------|--------------------------|
|    applicationKey     |    mamApplicationKey     |
|    applicationName    |    mamApplicationName    |
|    applicationId      |    mamApplicationId      |

A következő táblázatban található a tulajdonságainak módosításait a [mamApplicationInstances](intune-data-warehouse-collections.md#mamapplicationinstances) gyűjtemény: 

|    Régi tulajdonság     |    Módosítás/cseréje    |
|---------------------|--------------------------|
|    applicationId    |    mamApplicationId      |
|    deviceId         |    mamDeviceId           |
|    deviceType       |    mamDeviceType         |
|    deviceName       |    mamDeviceName         |

A következő táblázatban található a tulajdonságainak módosításait a [mamCheckins](intune-data-warehouse-collections.md#mamcheckins) gyűjtemény: 

|    Régi tulajdonság      |    Módosítás/cseréje    |
|----------------------|--------------------------|
|    applicationKey    |    mamApplicationKey     |

A következő táblázatban található a tulajdonságainak módosításait a [felhasználók](intune-data-warehouse-collections.md#users) gyűjtemény: 

|    Régi tulajdonság             |    Módosítás/cseréje    |
|-----------------------------|--------------------------|
|    startDateInclusiveUtc    |    Eltávolítva               |
|    endDateInclusiveUtc      |    Eltávolítva               |
|    IsCurrent                |    Eltávolítva               |

## <a name="1903"></a>1903
_Kiadás dátuma: 2019. március_

### <a name="v10-changes-reflecting-back-to-beta"></a>Vissza a bétaverzió tükröző 1.0-s verziójú módosítások
Ha az 1.0-s verziójú 1808 rendszerben bevezetett, az API alkalmazást jelentős módokon eltérő számú. A 1903 ezeket a módosításokat megjelennek a bétaverzió API be újra. Ha fontos a bétaverzió API-t használó jelentéseket, erősen ajánlott ezeket a jelentéseket átváltása 1.0-s verziójú parancsban történt használhatatlanná tévő elkerülése érdekében. Tekintse meg [API verzióinformációkat](reports-api-url.md) további információt az adattárház API-verziók és a visszamenőleges kompatibilitás. 

## <a name="1902"></a>1902 
_Released February 2019_

### <a name="power-bi-compliance-app"></a>A Power BI megfelelőségi alkalmazás 

A Power BI online-hoz az Intune-adattárház elérése a [(adatraktár) az Intune megfelelőségi](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) alkalmazást. A Power BI alkalmazással most már elérheti és megoszthatja az előre létrehozott jelentések beállítások nélkül, és a böngésző elhagyása nélkül. 

> [!NOTE]
> Nincsenek két további szűrőket is alkalmazhat az Intune megfelelőségi alkalmazást.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>További szűrők hozzáadása az Intune megfelelőségi alkalmazáshoz
1. Nyissa meg a [(adatraktár) az Intune megfelelőségi](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) a böngészők alkalmazást.
2. Kattintson a **nem megfelelő eszközök** válassza **nem megfelelő** a a **complianceStatus** szűrőt. 
3. Kattintson a **ismeretlen eszközök** válassza **még nem érhető el** a a **complianceStatus** szűrőt. 

## <a name="1812"></a>1812 
_Kiadás dátuma: 2018. December_

### <a name="enrollment-activities-collection-released-to-v10"></a>Regisztráció tevékenységek gyűjtemény nyilvánosan 1.0-s verzió 

A beléptetési aktivitást gyűjtemény már elérhető az 1.0-s verziója. Ez a gyűjtemény segítségével megismerheti a regisztrációs hiba mennyiségi és trendeket a környezetben. További információkért lásd: [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities), [enrollmentEventStatuses](intune-data-warehouse-collections.md#enrollmenteventstatuses), [enrollmentFailureCategories](intune-data-warehouse-collections.md#enrollmentfailurecategories), és [ enrollmentFailureReasons](intune-data-warehouse-collections.md#enrollmentfailurereasons).

## <a name="1808"></a>1808
_Kiadás dátuma: 2018. augusztus_

### <a name="v10-collections"></a>v1.0 gyűjtemények  

Most már használható az Intune Adattárház v1.0-ás verziója az `api-version=v1.0` lekérdezésparaméter megadásával. Az Adattárház gyűjteményeinek frissítései hozzáadó jellegűek, és nem okoznak fennakadást a meglévő forgatókönyvekben.

### <a name="enrollment-activities-collection-released-to-beta"></a>Regisztráció tevékenységek gyűjtemény béta általánosan elérhető

Az új `Enrollment Activities` gyűjtemény elérhető béta verzióban Ennek a gyűjteménynek a használatával megismerheti a regisztrálás előrehaladását, és megtekintheti a leggyakoribb hibákat. 


## <a name="1805"></a>1805
_Kiadás dátuma: 2018. május_

### <a name="correction-to-device-count-in-devices-collection"></a>Az **Eszközök** gyűjteményben megjelenő eszközszámmal kapcsolatos javítás 

Javítottuk az **Eszközök** gyűjteményt, amelyben így előfordulhat, hogy kevesebb eszköz fog megjelenni az `isDeleted` attribútum alapján történő szűrés esetén. Ez a csökkenés nem hiba, hanem a javítás eredménye. Az **Eszközök** csoportról bővebben az [Eszközök típusú entitások referenciája](reports-ref-devices.md) című témakörben olvashat. 


## <a name="1801"></a>1801
_Kiadás dátuma: 2018. január_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Alkalmazásalapú hitelesítés az Intune-adattárházban <!-- 1867540 -->

Beállíthat alkalmazásokat az Azure Active Directory (Azure AD) segítségével úgy, hogy hitelesítsék magukat az Intune-adattárházban. További információ: [Alkalmazásalapú hitelesítés az Intune-adattárházban](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Az Azure AD-beli és az Intune-beli hitelesítő adatokra vonatkozó követelmények <!-- 2077525 -->

- Már nincs szükség egy felhasználóhoz rendelt Intune-licencre, ha az Intune Data Warehouse-hoz szeretne hozzáférni (beleértve az API-t).
- Az Intune szerepkörének neve **Jelentések**ről **Intune Data Warehouse**-ra módosult. 

    További információ: [Az Azure AD-beli és az Intune-beli hitelesítő adatokra vonatkozó követelmények](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>Az OData-lekérdezés beállításai <!-- 2077711 -->

OData-lekérdezési paraméterként a következőt is használhatja: <code>$select</code>. A jelenlegi verzió a következő OData-lekérdezésparamétereket támogatja: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> és <code>$top</code>. További információt [Az OData-lekérdezés beállításai](reports-api-url.md#odata-query-options) című témakörben találhat.

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Új entitások az adattárház adatmodelljében <!-- 2077804 -->

 - A [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md) entitást hozzáadtuk. A **MobileAppDeviceUserInstallStatus** a mobilalkalmazás telepítési állapotát jelöli egy adott eszközre és felhasználóra vonatkozóan.
 - A [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate) entitást hozzáadtuk. A **MobileAppInstallState** entitás egy mobilalkalmazás telepítési állapotát jelöli, miután az hozzá lett rendelve egy eszközöket, felhasználókat vagy mindkettőt tartalmazó csoporthoz. 

## <a name="1710"></a>1710
_Kiadás dátuma: 2017. november_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Az aktuális felhasználó nevű új entitásgyűjtemény a jelenleg aktív felhasználói adatokra korlátozódik <!-- 1544273 -->

A **Felhasználók** entitásgyűjtemény a vállalaton belül hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználót tartalmazza. A rekordok között akkor is ott vannak az adatgyűjtési időszakon belüli felhasználói állapotok, ha a felhasználót azóta eltávolították. Például az elmúlt egy hónap során hozzáadhattak az Intune-hoz egy felhasználót, majd el is távolíthatták onnan. A felhasználó a jelentés időpontjában nincs jelen, de az adatok tartalmazzák a felhasználót és állapotát. Ekkor létrehozhat egy olyan jelentést, amely megjeleníti a felhasználó korábbi jelenlétének időtartamát az adatokban.

Ezzel szemben az új **Aktuális felhasználó** entitásgyűjtemény csak azokat a felhasználókat tartalmazza, akiket nem távolítottak el. Az **Aktuális felhasználó** entitásgyűjtemény csak a jelenleg aktív felhasználókat tartalmazza. Az **Aktuális felhasználó** entitásgyűjteménnyel kapcsolatban az [Aktuális felhasználó típusú entitás referenciája](reports-ref-current-user.md) oldalon talál további információkat.

## <a name="1709"></a>1709
_Kiadás dátuma: 2017. október_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Felhasználói eszközök társítási entitásgyűjteménye Intune-adattárház adatmodelljében <!-- 1187917 -->

A felhasználók és eszközök gyűjteményének társítását végző felhasználói eszköztársítási információ használatával jelentéseket és adatvizualizációkat hozhat létre. Az adatmodell a Power BI-fájlon (PBIX) keresztül érhető el az adattárház Intune-oldaláról az OData-végpont használatával vagy egyéni ügyfél létrehozásával. További információkért lásd: [Felhasználók és eszközök társítása](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Új entitások az adattárház adatmodelljében <!-- 1479526 --><!-- -->

 - Új entitás: [**UserDeviceAssociation**](reports-ref-user-device.md). A **UserDeviceAssociation** tartalmazza a szervezet felhasználói hozzárendeléseit. A felhasználók és eszközök gyűjteményének társítását végző felhasználói eszköztársítási információ használatával jelentéseket és adatvizualizációkat hozhat létre.  
 - Megjelent az [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) entitás. Az **IntuneManagementExtension** mobileszközökhöz készült entitásokat tartalmaz, amelyek többek között a verziószámot és a telepítési állapotot követik nyomon.

## <a name="next-steps"></a>További lépések
 - Heti összesítésben [olvashat az Intune újdonságairól](whats-new.md). Emellett tájékozódhat a jövőbeni változtatásokról, a szolgáltatással kapcsolatos fontos bejelentésekről és a korábbi verziókról is.
 - Tekintse meg [a Microsoft Intune blogját](https://go.microsoft.com/fwlink/?LinkID=273882).
