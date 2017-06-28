---
title: "A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek"
description: "Az Androidhoz készült Microsoft Intune App SDK lehetővé teszi, hogy az Intune mobilalkalmazás-felügyeleti (MAM) funkcióját beépítse Android-alkalmazásaiba."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: b5ad9cc6c03712090398cacb3d4bb653deb1d2a4
ms.openlocfilehash: 7dfcc0bf8f3da1e600df59927db6e78ec2021e0f
ms.contentlocale: hu-hu
ms.lasthandoff: 06/12/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek

> [!NOTE]
> Kezdésként érdemes lehet elolvasni [Az Intune APP SDK áttekintése](app-sdk.md) című cikket, amely ismerteti az SDK aktuálisan elérhető funkcióit, valamint az integrációval kapcsolatos előkészületeket a támogatott platformokon.

Az Androidhoz készült Microsoft Intune App SDK révén Intune-os alkalmazásvédelmi szabályzatokat (más néven **APP**- vagy MAM-szabályzatokat) építhet be natív Android-alkalmazásába. Intune-kompatibilisnek az Intune App SDK-val integrált alkalmazásokat nevezzük. A rendszergazdák egyszerűen telepíthetnek alkalmazásvédelmi szabályzatokat az Intune-kompatibilis alkalmazáshoz, ha az Intune aktívan felügyeli az alkalmazást.


## <a name="whats-in-the-sdk"></a>Az SDK tartalma

Az Intune App SDK-ban a következő fájlok találhatók:  

* **Microsoft.Intune.MAM.SDK.aar**: Az SDK-összetevők a Support.V4 és Support.V7 JAR-fájlok kivételével. Ez a fájl az egyes összetevők helyett használható, ha a buildelési rendszer támogatja az AAR-fájlokat.
* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: A MAM azon alkalmazásokban való engedélyezéséhez szükséges felületek, amelyek az Android v4 támogatási függvénytárat használják. Az ezt a támogatást igénylő alkalmazásoknak közvetlenül kell hivatkozniuk a jar-fájlra.
* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: A MAM azon alkalmazásokban való engedélyezéséhez szükséges felületek, amelyek az Android v7 támogatási függvénytárat használják. Az ezt a támogatást igénylő alkalmazásoknak közvetlenül kell hivatkozniuk a jar-fájlra.
* **proguard.txt**: azokat a ProGuard-szabályokat tartalmazza, amelyek a ProGuarddal való buildeléshez szükségesek.
* **CHANGELOG.txt**: Az egyes SDK-verziók változásait sorolja fel.
* **THIRDPARTYNOTICES. TXT**: A harmadik féltől származó és/vagy OSS kódnak az alkalmazásba fordítására vonatkozó tájékoztatás.

Ha a buildelőrendszer nem támogatja az AAR-fájlokat, a Microsoft.Intune.MAM.SDK.aar helyett használja az alábbiakat.
* **Microsoft.Intune.MAM.SDK.jar**: a MAM, valamint az Intune Céges portál alkalmazással való együttműködés lehetővé tételéhez szükséges interfészek. Az alkalmazásoknak androidos függvénytár-hivatkozásként kell megadniuk ezt a fájlt.
* **A res könyvtár**: Az SDK által alkalmazott erőforrások (például karakterláncok).
* **AndroidManifest.xml**: A további belépési pontokra és a függvénytárra vonatkozó követelmények.


## <a name="requirements"></a>Követelmények

Az Intune App SDK egy lefordított androidos projekt. Ez azt jelenti, hogy jelentős mértékben független az alkalmazás által a minimális vagy a cél API-verzióhoz használt Android-verziótól. Az SDK az Android API 14 (Android 4.0+) és az Android API 25 (Android 7.1) közötti verziókat támogatja.



### <a name="company-portal-app"></a>Vállalati portál alkalmazás
Az androidos Intune App SDK a [Céges portál](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) alkalmazással teszi lehetővé az alkalmazásvédelmi szabályzatok működését. A Céges portál az Intune szolgáltatástól kéri le az alkalmazásvédelmi szabályzatokat. Az alkalmazás az inicializáláskor betölti a Céges portálról a szabályzatot és a betartatásához szükséges kódot.

> [!NOTE]
> Ha a Céges portál alkalmazás nincs telepítve az eszközre, akkor az Intune-kompatibilis alkalmazás ugyanúgy működik, mint az általános, az Intune alkalmazásvédelmi szabályzatait nem támogató alkalmazások.

Az eszközregisztráció nélküli alkalmazásvédelem esetében a felhasználónak _**nem**_ kell regisztrálnia az eszközt a Céges portál alkalmazással.

## <a name="sdk-integration"></a>SDK-integráció

### <a name="build-integration"></a>Buildintegráció

Az Intune App SDK for Android egy szabványos, külső függőségek nélküli androidos függvénytár. A **Microsoft.Intune.MAM.SDK.jar**-ban megvannak mind az alkalmazásvédelmi szabályzatok használatát lehetővé tevő interfészek, mind pedig a Microsoft Intune Céges portál alkalmazással való együttműködéshez szükséges kód.

A **Microsoft.Intune.MAM.SDK.jar** -t androidos függvénytár-hivatkozásként kell megadni. Ehhez nyissa meg az alkalmazásprojektet az Android Studióban, válassza a **File > New > New module** (Fájl > Új > Új modul), majd az **Import .JAR/.AAR Package** (.JAR-/.AAR-csomag importálása) elemet. Jelölje ki a Microsoft.Intune.MAM.SDK.aar nevű androidos archívumcsomagot.

A **Microsoft.Intune.MAM.SDK.Support.v4** és a **Microsoft.Intune.MAM.SDK.Support.v7** rendre az `android.support.v4` és az `android.support.v7` Intune-os variánsát tartalmazza. Ezek nem kerültek bele a Microsoft.Intune.MAM.SDK.aar-ba, hogy az alkalmazásoknak ne legyen muszáj tartalmazni a támogatási kódtárakat. Ezek nem is androidos kódtárprojektek, hanem szabványos JAR-fájlok.

#### <a name="proguard"></a>ProGuard

Ha a buildfolyamatnak része a [ProGuard](http://proguard.sourceforge.net/) (vagy bármelyik másik zsugorítási/rejtjelezési mechanizmus), az Intune SDK osztályait ki kell zárni. A ProGuard esetében ez az SDK-hoz tartozó proguard.txt-ben lévő szabályok felvételével oldható meg.

Az Azure Active Directory Authentication Libraries (ADAL) szolgáltatásnak saját ProGuard-korlátozásai lehetnek. Ha az Ön alkalmazása az ADAL-lal van integrálva, ezen korlátozások tekintetében az ADAL dokumentációja a mérvadó.

### <a name="entry-points"></a>Belépési pontok
======= Az Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) a közvetített hitelesítés végrehajtásához igényli ezeket az engedélyeket. Ha az alkalmazás nem kapja meg ezeket az engedélyeket, vagy ha a felhasználó visszavonja ezeket az engedélyeket, akkor a közvetítőt igénylő hitelesítési folyamatok (a Munkahelyi portál alkalmazás) le lesznek tiltva.

Az Intune App SDK az alkalmazás forráskódjának módosítását igényli az Intune alkalmazásvédelmi szabályzatainak engedélyezéséhez. Ez az androidos alaposztályok egyenértékű Intune-osztályokra való cseréjével történik. Utóbbiak nevében a **MAM** előtag szerepel. Az SDK-osztályok az androidos alaposztály és az alkalmazás saját származtatott verziója között helyezkednek el. A tevékenységek esetében ez például egy, az alábbihoz hasonló öröklési hierarchiát eredményez: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Amikor például az `AppSpecificActivity` interakcióba lép a szülőjével (például meghívja a következőt: `super.onCreate()`), a `MAMActivity` lesz a szülőosztály.

Az androidos alkalmazások általában egyszeres módban működnek, és a [**Context**](https://developer.android.com/reference/android/content/Context.html) objektumukon keresztül férhetnek hozza a rendszerhez. Az Intune App SDK-t integráló alkalmazások viszont kettős módban működhetnek. Ezek az alkalmazások a továbbiakban is a `Context` objektumon keresztül érik el a rendszert. Az Android a használt alapszintű `Activity` alapján biztosítja a `Context` objektumot, vagy a rendszer intelligensen multiplexel a rendszer korlátozott nézete, illetve az Android által biztosított `Context` között.


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a>Az osztályok, a metódusok és a tevékenységek lecserélése a MAM-kompatibilis megfelelőkre

Az androidos alaposztályokat a MAM-megfelelőjükkel kell helyettesíteni. Ehhez az alábbi táblázatban felsorolt osztályok összes példányát le kell cserélni az Intune App SDK-beli megfelelőjükre.

| Androidos alaposztály | Intune App SDK-beli helyettesítése |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | MAMPendingIntent (a megjegyzéseket lásd alább) |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (csak akkor szükséges, ha a Binder létrehozása nem androidos interfészdefiníciós nyelvű (AIDL-) interfészből történik) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Support.v4.jar:

| Androidos osztály Intune MAM | Intune App SDK-beli helyettesítése |
|--|--|
| Android.support.v4.App.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| Android.support.v4.App.TaskStackBuilder | MAMTaskStackBuilder
| Android.support.v4.Content.FileProvider | MAMFileProvider

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Support.v7.jar:

|Androidos osztály | Intune App SDK-beli helyettesítése |
|--|--|
|Android.support.v7.App.ActionBarActivity | MAMActionBarActivity |


### <a name="renamed-methods"></a>Átnevezett metódusok
A MAM egyik belépési pontjából történő származtatást követően a megszokott módon használhatja a `Context` szintet, például elindíthatja az `Activity`-osztályokat, és használhatja a `PackageManager` eszközt is.

Sok esetben az androidos osztályban rendelkezésre álló metódus végsőként van megjelölve a helyettesítő MAM-osztályban. Ebben az esetben a helyettesítő MAM-osztály egy hasonlóan elnevezett metódust biztosít (általában a `MAM` utótaggal), amelyet felül kell írni. Így például a `MAMActivity` származtatásakor az `onCreate()` felülírása, illetve a `super.onCreate()` metódus hívása helyett az `Activity` tevékenységnek felül kell írnia az `onMAMCreate()` metódust, és meg kell hívnia a `super.onMAMCreate()` metódust. A Java-fordítónak érvényesítenie kell a végső korlátozásokat az eredeti metódus véletlen felülbírálásának elkerülése érdekében az egyenértékű MAM-metódus helyett.

### <a name="pendingintent"></a>PendingIntent
A `PendingIntent.get*` helyett például a `MAMPendingIntent.get*` metódust kell használni. Az így létrejövő `PendingIntent` már szintén a megszokott módon használható.

### <a name="manifest-replacements"></a>Cserék a jegyzékben
Ne feledje, hogy a fenti osztálycserék egy részét a jegyzékfájlban és a Java-kódban is el kell végezni. Különösen fontos:
* a jegyzékfájlban szereplő `android.support.v4.content.FileProvider`-hivatkozásokat le kell cserélni erre: `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.


## <a name="sdk-permissions"></a>Az SDK engedélyei

Az Intune App SDK három [androidos rendszerengedélyt](https://developer.android.com/guide/topics/security/permissions.html) igényel azokhoz az alkalmazásokhoz, amelyekbe beépül:

* `android.permission.GET_ACCOUNTS` (kérése futásidőben történik, ha szükség van rá)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Az Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) a közvetített hitelesítés végrehajtásához igényli ezeket az engedélyeket. Ha az alkalmazás nem kapja meg ezeket az engedélyeket, vagy ha a felhasználó visszavonja ezeket az engedélyeket, akkor a közvetítőt igénylő hitelesítési folyamatok (a Munkahelyi portál alkalmazás) le lesznek tiltva.

## <a name="logging"></a>Naplózás

A naplózott adatok maximális hasznossága érdekében a naplózást célszerű korán inicializálni. Erre az `Application.onMAMCreate()` a legalkalmasabb hely.

Ha az alkalmazásban MSM-naplókat szeretne fogadni, hozzon létre [Java-kezelőt](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html), és vegye fel a `MAMLogHandlerWrapper`-be. Ez minden naplóüzenetre meghívja a `publish()` metódust az alkalmazás kezelőjén.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a>Alkalmazás részvételét igénylő szolgáltatások engedélyezése

Az SDK számos alkalmazásvédelmi szabályzatot nem tud önállóan implementálni. Az alkalmazás a saját működésének szabályozásával képes e funkciókat biztosítani. Ehhez több API-t használ, amelyek az alábbi `AppPolicy` felületen találhatók.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}

```

> [!NOTE]
> A `MAMComponents.get(AppPolicy.class)` mindig nem null értékű alkalmazásszabályzatot ad vissza – akkor is, ha az eszközre vagy az alkalmazásra nem vonatkozik Intune-beli felügyeleti szabályzat.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Példa: annak megállapítása, hogy az alkalmazáshoz szükséges-e PIN-kód

Ha az alkalmazásnak saját felhasználói PIN-kódkezelő funkciója van, akkor azt célszerű letiltani, ha a rendszergazda úgy állította be az SDK-t, hogy az kérjen alkalmazás-PIN-kódot. Az alábbi metódust meghívva állapíthatja meg, hogy a rendszergazda telepített-e alkalmazás-PIN-szabályzatot az alkalmazáshoz az aktuális végfelhasználónál:

```java
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Példa: az elsődleges Intune-felhasználó meghatározása

Az egyszerű felhasználónevet (**UPN**) az AppPolicy-ban elérhető API-kon felül a `MAMUserInfo` interfészben definiált `getPrimaryUser()` API is elérhetővé teszi. Az UPN-t az alábbi kódot meghívva kérheti le:

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

Alább a MAMUserInfo interfész teljes definiálása olvasható:

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Példa: annak megállapítása, hogy engedélyezve van-e az eszközre vagy a felhőbeli tárhelyre való mentés

Számos alkalmazás valósít meg olyan funkciókat, amelyek lehetővé teszik a végfelhasználó számára fájlok mentését helyi háttértárra vagy felhőbeli tárolószolgáltatásba. Az Intune App SDK lehetővé teszi a rendszergazdáknak az adatszivárgás ellen a szervezet igényei szerinti szabályzatkorlátozások alkalmazásával történő védekezést.  A rendszergazda által beállítható szabályzatok egyike arra vonatkozik, hogy a felhasználók menthetnek-e fájlokat nem felügyelt személyes adattárba. Ide tartoznak a helyi mentési helyek, az SD-kártyák és a harmadik felek biztonsági mentési szolgáltatásai.

**A funkció engedélyezéséhez az alkalmazás részvételére van szükség.** Ha az alkalmazás lehetővé teszi a személyes vagy a felhőbeli helyekre való mentést közvetlenül az alkalmazásból, ezt a funkciót meg kell valósítani annak biztosításához, hogy a rendszergazda szabályozhassa, engedélyezve van-e a mentés az adott helyre. Az alábbi API lehetővé teszi, hogy az alkalmazás megállapítsa, hogy a személyes tárolóba való mentés engedélyezve van-e az aktuális Intune-rendszergazda szabályzata szerint. Az alkalmazás ekkor érvényesítheti a házirendet, mivel meg tudja állapítani, hogy elérhető-e személyes adattár a felhasználó számára az alkalmazáson keresztül.  

Az alábbi hívással állapíthatja meg, hogy a szabályzat be van-e tartatva:

```java
MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

...ahol a `service` az alábbi SaveLocation értékek valamelyike:


    * SaveLocation.ONEDRIVE_FOR_BUSINESS
    * SaveLocation.LOCAL
    * SaveLocation.OTHER

Korábban ugyanezen **AppPolicy** osztály `getIsSaveToPersonalAllowed()` függvényével lehetett megállapítani, hogy az adott felhasználó szabályzata engedélyezi-e a mentést különféle helyekre. Ez a függvény mostanra **elavult**, és nem szabad használni. Az alábbi kód egyenértékű a `getIsSaveToPersonalAllowed()` függvénnyel:

```java

MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> A `SaveLocation.OTHER` akkor használatos, ha a szóban forgó hely nem szerepel a **SaveLocations** enumerációban.


## <a name="register-for-notifications-from-the-sdk"></a>Regisztráció az SDK értesítéseire

### <a name="overview"></a>Áttekintés
Az Intune App SDK lehetővé teszi, hogy az alkalmazás szabályozza bizonyos szabályzatok, például a szelektív törlési szabályzat működését, ha a rendszergazda telepítette őket. Amikor a rendszergazda alkalmaz egy ilyen szabályzatot, az Intune szolgáltatás értesítést küld az SDK-nak.

Ehhez regisztrálnia kell az SDK által küldött értesítésekre: hozzon létre egy `MAMNotificationReceiver` osztályt, és regisztrálja a következővel: `MAMNotificationReceiverRegistry`. Ez a fogadó és az `App.onCreate` metódusban fogadni kívánt értesítés típusának megadásával történik, az alábbi példában látható módon:

```java
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
        .registerReceiver(
            new ToastNotificationReceiver(),
            MAMNotificationType.WIPE_USER_DATA);
    }
```

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

A `MAMNotificationReceiver` fogadja az értesítéseket az Intune szolgáltatástól. Egyes értesítéseket közvetlenül az SDK kezel, míg mások az alkalmazás részvételét igénylik. Az alkalmazásnak igaz vagy hamis értéket **kell** visszaadnia az értesítésekből. Hacsak valamely, általa az értesítés eredményeként megkísérelt művelet sikertelen nem volt, mindig igaz értéket kell visszaadjon.

* Ez a hiba megjelenhet az Intune szolgáltatásnak küldött jelentésben. Jelentendő helyzet lehet például az olyan eset, amikor az alkalmazás nem törli a felhasználói adatokat, miután a rendszergazda kezdeményezte a törlést.

>[!NOTE]
> A `MAMNotificationReceiver.onReceive` metódusban biztonságosan blokkolható, mivel a visszahívása nem a felhasználói felület szálán fut.

Alább látható az SDK-ban ily módon definiált `MAMNotificationReceiver` interfész:

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

### <a name="types-of-notifications"></a>Az értesítések típusai

A következő értesítéseket küldi a program az alkalmazásnak, és némelyikük igényelheti az alkalmazás részvételét:

* **WIPE_USER_DATA**: ezt az értesítést a rendszer egy `MAMUserNotification` osztályban küldi el. Az értesítés beérkezésekor az alkalmazásnak a `MAMUserNotification` osztály által átadott „vállalati” identitáshoz társított összes adatot törölnie kell. Az értesítést jelenleg az APP-WE szolgáltatásba való beléptetés megszüntetésekor küldi a program. A regisztrációs folyamat során általában sor kerül a felhasználó elsődleges nevének megadására. Ha regisztrál erre az értesítésre, az alkalmazásnak kell gondoskodnia az összes felhasználói adat törléséről. Ha nem regisztrál, az alapértelmezett szelektív törlési viselkedés érvényesül.

* **WIPE_USER_AUXILIARY_DATA**: Az alkalmazások akkor regisztrálhatnak erre az értesítésre, ha az cél, hogy az Intune App SDK hajtsa végre az alapértelmezett szelektív törlést, de bizonyos kiegészítő adatokat is törölni kell.

* **REFRESH_POLICY**: Ezt az értesítést a rendszer egy `MAMUserNotification` osztályban küldi el. Az értesítés fogadásakor a gyorsítótárban található összes Intune-szabályzatot érvényteleníteni és frissíteni kell. Ezt általában az SDK kezeli, azonban az alkalmazásnak kell kezelnie, ha a szabályzat valamilyen állandó módon van használva.

* **REFRESH_POLICY**: Ezt az értesítést a rendszer egy `MAMUserNotification` osztályban küldi el, és tájékoztatja az alkalmazást, hogy éppen elhagyni készül a felügyeletet. Felügyelet nélkül az alkalmazás nem fogja tudni olvasni a titkosított fájlokat, a MAMDataProtectionManagerrel titkosított adatokat, kezelni a titkosított vágólapot, vagy bármilyen más módon részt venni a felügyelt alkalmazások ökoszisztémájában.


> [!NOTE]
> Az alkalmazások nem regisztrálhatnak egyszerre a `WIPE_USER_DATA` és a `WIPE_USER_AUXILIARY_DATA` értesítésre.


## <a name="configure-azure-active-directory-authentication-library-adal"></a>Az Azure Active Directory Authentication Library (ADAL) konfigurálása (nem kötelező)

Először olvassa el a [GitHub ADAL-kódtárában](https://github.com/AzureAD/azure-activedirectory-library-for-android) található ADAL-integrációs irányelveket.

Az SDK a hitelesítési és feltételes indítási forgatókönyvekhez az [ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)-ra támaszkodik, amely a [hitelesítéshez](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-scenarios/) megköveteli, hogy az alkalmazásokat az [Azure Active Directoryval](https://azure.microsoft.com/en-us/documentation/articles/active-directory-whatis/) konfigurálják. A konfigurációs értékeket az SDK az AndroidManifest metaadatain keresztül közli.

Az alkalmazás konfigurálásához és a megfelelő hitelesítés engedélyezéséhez vegye fel a következőket az AndroidManifest.xml-be. Ezen konfigurációk némelyike csak akkor szükséges, ha az alkalmazás általánosan az ADAL-t használja hitelesítéshez. Ebben az esetben azokra a konkrét értékekre is szüksége lesz, amelyekkel az alkalmazás az AAD-ben regisztrálja magát. Így lehet biztosítani, hogy a rendszer ne kérje kétszer a felhasználó hitelesítését. Az AAD ugyanis két különböző regisztrációs értéket ismer fel: egyet az alkalmazásból, egyet pedig az SDK-ból.

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a>ADAL-metaadatok

* **Authority:** az éppen használatban lévő AAD-szolgáltató. Ha meg van adva, akkor azt a saját környezetet kell használni, amelyben az AAD-fiókokat konfigurálták. Ha ez az érték hiányzik, a rendszer egy Intune-beli alapértelmezett értéket használ.

* **ClientID:** a használni kívánt AAD ClientID azonosító. Ha regisztrálva van az Azure AD-ben, akkor az alkalmazás saját ClientID-jét kell használni. Ha ez az érték hiányzik, a rendszer egy Intune-beli alapértelmezett értéket használ.

* **NonBrokerRedirectURI:** a közvetítő nélküli esetekben használandó AAD átirányítási URI. Ha nincs megadva, a rendszer az alapértelmezett `urn:ietf:wg:oauth:2.0:oob` értéket használja. Ez a legtöbb alkalmazáshoz megfelelő.

* **SkipBroker:** akkor használatos, ha a ClientID nincs a közvetítő átirányítási URI-jának használatára konfigurálva. Az alapértelmezett érték a „false” (hamis).
    * **Az ADAL-t nem integráló** és **az eszközszintű közvetített hitelesítésben/SSO-ban részt venni nem kívánó** alkalmazások esetében kell „true” (igaz) értékre állítani. Ilyen esetben az egyetlen használatos átirányítási URI a NonBrokerRedirectURI lesz.

    * Az eszközszintű SSO-közvetítést támogató alkalmazások esetében a „false” értéket kell használni. Ilyenkor az SDK választ közvetítőt a [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) eredménye és a NonBrokerRedirectURI közül a közvetítő rendszerbeli elérhetősége alapján. A közvetítő forrása a legtöbbször a Céges portál alkalmazás vagy az Azure Authenticator alkalmazás lesz.

### <a name="common-adal-configurations"></a>Általános ADAL-konfigurációk

A következőkben az alkalmazások ADAL-konfigurációjának gyakori eseteit mutatjuk be. Keresse meg az alkalmazásához illő esetet, és állítsa be az ADAL (fent ismertetett) metaadat-paramétereit a megfelelő értékekre.

1. **Az alkalmazás nem integrálja az ADAL-t:**

    | Szükséges ADAL-paraméter | Érték |
    |--|--|
    | Authority | Az a környezet, amelyben az AAD-fiókokat konfigurálták |
    | SkipBroker | Igaz |

2. **Az alkalmazás integrálja az ADAL-t:**

    |Szükséges ADAL-paraméter| Érték |
    |--|--|
    | Authority | Az a környezet, amelyben az AAD-fiókokat konfigurálták |
    | ClientID | Az alkalmazás ClientID azonosítója (az Azure AD állítja elő az alkalmazás regisztrálásakor) |
    | NonBrokerRedirectURI | Az alkalmazás érvényes átirányítási URI-ja, vagy alapértelmezés szerint `urn:ietf:wg:oauth:2.0:oob`. <br><br> Ezt az értéket mindenképpen elfogadható átirányítási URI-ként kell beállítani az alkalmazás ClientID azonosítójához.
    | SkipBroker | Hamis |


3. **Az alkalmazás integrálja az ADAL-t, de nem támogatja a közvetített hitelesítést/eszközszintű SSO-t:**

    |Szükséges ADAL-paraméter| Érték |
    |--|--|
    | Authority | Az a környezet, amelyben az AAD-fiókokat konfigurálták |
    | ClientID | Az alkalmazás ClientID azonosítója (az Azure AD állítja elő az alkalmazás regisztrálásakor) |
    | NonBrokerRedirectURI | Az alkalmazás érvényes átirányítási URI-ja, vagy alapértelmezés szerint `urn:ietf:wg:oauth:2.0:oob`. <br><br> Ezt az értéket mindenképpen elfogadható átirányítási URI-ként kell beállítani az alkalmazás ClientID azonosítójához.
    | SkipBroker | **True** |

## <a name="app-protection-policy-without-device-enrollment"></a>Eszközregisztráció nélküli alkalmazásvédelmi szabályzat

### <a name="overview"></a>Áttekintés
Az Intune APP-WE vagy MAM-WE néven is ismert eszközbeléptetés nélküli alkalmazásvédelmi szabályzata lehetővé teszi, hogy az Intune anélkül is felügyelhesse az alkalmazásokat, hogy az eszközök az Intune MDM-re regisztrálva lennének. Az APP-WE működik eszközbeléptetéssel és anélkül is. A Céges portál alkalmazást továbbra is telepíteni kell az eszközre, de a felhasználónak nem kell bejelentkeznie a Céges portálba és beléptetnie az eszközt.

> [!NOTE]
> Az összes alkalmazásnak támogatnia kell az alkalmazásvédelmi szabályzatok eszközbeléptetés nélküli használatát.

### <a name="workflow"></a>Munkafolyamat

Ha egy alkalmazás új felhasználói fiókot hoz létre, azt regisztrálnia kell felügyeletre az Intune App SDK-val. Az SDK kezeli az alkalmazás APP-WE szolgáltatásba való beléptetésének részleteit; szükség esetén a megfelelő időközönként újból megpróbálkozik a beléptetéssel, ha az sikertelen.

Az alkalmazás az Intune App SDK-tól kérdezheti le a regisztrált felhasználók állapotát is, amikor azt próbálja megállapítani, hogy az illetőt el kell-e tiltani a vállalati tartalom elérésétől. Több fiókot is lehet felügyeletre regisztrálni, de jelenleg egyszerre csak egy lehet aktívan beléptetve az APP-WE szolgáltatásba, és így az alkalmazásban is egyszerre csak egy fiók kaphat alkalmazásvédelmi szabályzatot.

Az alkalmazásnak visszahívás útján kell megszereznie a megfelelő hozzáférési jogkivonatot az Azure Active Directory Authentication Librarytől (ADAL) az SDK nevében. Az alapfeltevés az, hogy az alkalmazás már az ADAL-lal hitelesíti a felhasználókat és szerzi be a saját hozzáférési jogkivonatát.

Amikor az alkalmazás teljesen eltávolít egy fiókot, meg kell szüntetnie annak regisztrációját, így jelezve, hogy a továbbiakban az adott felhasználóra nem kell szabályzatot alkalmazni. Ha a felhasználó be volt léptetve a MAM-szolgáltatásba, akkor a beléptetés megszűnik, az alkalmazás pedig törlődik.


### <a name="overview-of-app-requirements"></a>Az alkalmazások követelményeinek áttekintése

Az APP-WE-integráció implementálásához az alkalmazásnak a felhasználói fiókot regisztrálnia kell a MAM SDK-val:

1. Az alkalmazásnak _kötelező_ a `MAMServiceAuthenticationCallback` interfész egy példányát implementálni és regisztrálni. A visszahívási példányt az alkalmazás életciklusának lehető legkorábbi pontján kell regisztrálni (jellemzően az alkalmazás osztályának `onMAMCreate()` metódusában).

2. Felhasználói fiók létrejötte és a felhasználó sikeres ADAL-bejelentkezése után alkalmazásnak _kötelező_ meghívni a `registerAccountForMAM()` metódust.

3. Felhasználói fiók teljes eltávolítása után az alkalmazásnak az `unregisterAccountForMAM()` metódussal kell eltávolítania a fiókot az Intune-felügyeletből.

    > [!NOTE]
    > Ha egy felhasználó átmenetileg kijelentkezik az alkalmazásból, akkor nincs szükség az `unregisterAccountForMAM()` meghívására, mert előfordulhat, hogy ez törlést kezdeményez, és eltávolítja a felhasználó céges adatait.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Az összes szükséges hitelesítési és regisztrációs API a `MAMEnrollmentManager` interfészben található. `MAMEnrollmentManager`-hivatkozást az alábbi módon lehet szerezni:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

A visszaadott `MAMEnrollmentManager`-példány garantáltan nem null értékű. Az API-metódusok között vannak **hitelesítésre** és **fiókregisztrációra** használatosak.

> [!NOTE]
> A `MAMEnrollmentManager` bizonyos API-metódusai hamarosan el fognak évülni. Az érthetőség kedvéért az alábbi kódmintában csak a releváns metódusok és eredménykódok szerepelnek.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Fiókhitelesítés

Ez a szakasz a `MAMEnrollmentManager` hitelesítési API-metódusait és azok használatát ismerteti.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. Az alkalmazásnak a `MAMServiceAuthenticationCallback` interfész implementálásával kell biztosítania, hogy az SDK kérhessen ADAL-jogkivonatot az adott felhasználóhoz és erőforrás-azonosítóhoz. A `MAMEnrollmentManager` számára annak `registerAuthenticationCallback()` metódusát meghívva kell biztosítani a visszahívási példányt. Az alkalmazás életciklusának már nagyon korai szakaszában is szükség lehet jogkivonatra a beléptetési újrapróbálkozásokhoz vagy az alkalmazásvédelmi szabályzat frissítésének kereséséhez, így a visszahívást ideálisan az alkalmazás `MAMApplication` alosztályának `onMAMCreate()` metódusában érdemes regisztrálni.

2. A kért erőforrás-azonosítóra szóló hozzáférési jogkivonatot az `acquireToken()` metódusnak kell beszereznie az adott felhasználó számára. Ha ez nem sikerül, a metódusnak null értéket kell visszaadnia.

3. Ha az alkalmazás nem tud jogkivonatot biztosítani, amikor az SDK meghívja az `acquireToken()` metódust – például mert a csendes hitelesítés sikertelen és éppen nem lehet felhasználói felületet megjeleníteni –, később az `updateToken()` metódust meghívva teheti ezt meg. Az `updateToken()` metódusnak az `acquireToken()` korábbi meghívásakor használt UPN-t, AAD-azonosítót és erőforrás-ID kell átadni a végül beszerzett jogkivonattal együtt. Az alkalmazásnak a lehető leghamarabb meg kell hívnia ezt a metódust, miután a megadott visszahívás a null értéket adta.

> [!NOTE]
> Az SDK rendszeres időközönként megpróbálja az `acquireToken()` meghívásával megszerezni a jogkivonatot, így az `updateToken()` meghívása szigorúan véve nem szükséges, ugyanakkor ajánlott, mert elősegítheti a beléptetések és az alkalmazásvédelmiszabályzat-ellenőrzések mielőbbi befejezését.


### <a name="account-registration"></a>Fiókregisztráció

Ez a szakasz a `MAMEnrollmentManager` fiókregisztrációs API-metódusait és azok használatát ismerteti.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. A fiókokat az alkalmazásnak a `registerAccountForMAM()` metódust meghívva kell regisztrálnia a felügyelet alá. A felhasználói fiókot egyszerű felhasználóneve (UPN) és AAD-s felhasználói azonosítója is azonosítja. A beléptetési adatoknak a felhasználó AAD-bérlőjéhez társításához a bérlőazonosító is szükséges. Az SDK megpróbálhatja az adott felhasználó számára beléptetni az alkalmazást a MAM-szolgáltatásba. Ha a beléptetés sikertelen, akkor rendszeres időközönként újra fog próbálkozni vele, amíg a fiók regisztrációja meg nem szűnik. Az újrapróbálkozások időköze általában 12–24 óra. Az SDK aszinkron módon, értesítések útján közli a beléptetési kísérletek állapotát.

2. Mivel AAD-hitelesítésre van szükség, a felhasználói fiókot a legjobb akkor regisztrálni, amikor már bejelentkezett az alkalmazásba, és az ADAL-hitelesítés is megtörtént.
    * Az ADAL-hitelesítési hívás az [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) objektum részeként adja vissza a felhasználó AAD-azonosítóját és bérlőazonosítóját. A bérlőazonosító az `AuthenticationResult.getTenantID()` metódusból származik.
    * A felhasználóval kapcsolatos adatok egy, az `AuthenticationResult.getUserInfo()` metódusból származó, `UserInfo` típusú alobjektumban találhatók meg, az AAD-beli felhasználót pedig ebből az objektumból lehet lekérni a `UserInfo.getUserId()` metódussal.

3. A fiókok Intune-felügyeleti regisztrációját az alkalmazásnak az `unregisterAccountForMAM()` metódust meghívva kell megszüntetnie. Ha a fiók sikeresen be lett léptetve, és felügyelt fiók lett, az SDK fogja megszüntetni a beléptetését és törölni az adatait. A rendszeres időközönkénti beléptetési próbálkozások abbamaradnak. Az SDK aszinkron módon, értesítések útján közli a beléptetés-megszüntetési kérések állapotát.

### <a name="important-implementation-notes"></a>Fontos megjegyzések az implementálással kapcsolatban

#### <a name="authentication"></a>Hitelesítés

* Amikor az alkalmazás meghívja a `registerAccountForMAM()` metódust, kis idővel utána visszahívást kaphat egy másik szálon a `MAMServiceAuthenticationCallback` interfészén. Ideális esetben az alkalmazás már a fiók regisztrálása előtt beszerezte saját jogkivonatát az ADAL-tól, ezzel meggyorsítva a **MAMService-jogkivonat** beszerzését. Ha az alkalmazás a visszahívásból érvényes jogkivonatot ad vissza, a beléptetés folytatódik, és az alkalmazás egy értesítésben kapja meg a végeredményt.

* Ha az alkalmazás nem ad vissza érvényes AAD-jogkivonatot, a beléptetés végeredménye `AUTHENTICATION_NEEDED` lesz. Ha az alkalmazás ezt az eredményt kapja meg értesítésben, akkor a **MAMService-jogkivonat** beszerzésével, valamint az `updateToken()` metódust meghívva az ismételt kezdeményezéssel meggyorsíthatja a beléptetési folyamatot. Ez _nem_ szigorú követelmény, hiszen az SDK szabályos időközönként újrapróbálkozik a beléptetéssel, és a visszahívással próbálja beszerezni a jogkivonatot.

* Az alkalmazás regisztrált `MAMServiceAuthenticationCallback` interfésze is meg lesz hívva az alkalmazásvédelmi szabályzatok frissítéseinek rendszeres kereséséhez szükséges jogkivonat beszerzése céljából. Ha az alkalmazás kérésre nem tudja biztosítani a kért jogkivonatot, akkor nem fog értesítést kapni, de meg kell próbálnia jogkivonatot beszerezni, és a legközelebbi alkalmas időpontban meghívni az `updateToken()` metódust a beléptetési folyamat meggyorsítása érdekében. A visszahívás akkor is meg lesz hívva a következő beléptetési kísérletnél, ha nincs jogkivonat.

#### <a name="registration"></a>Regisztráció

* Az egyszerűség kedvéért a regisztrációs metódusok idempotensek. A `registerAccountForMAM()` például csak akkor regisztrálja a fiókot és próbálja meg beléptetni az alkalmazást, ha a fiók még nincs regisztrálva, az `unregisterAccountForMAM()` pedig csak akkor törli a fiók regisztrációját, ha az az adott időpontban regisztrálva van. Az ismételt hívások hatástalanok lesznek, így ezeket a metódusokat következmény nélkül meg lehet hívni többször is. Ezenfelül a metódusok meghívása nem feltétlenül vált ki eredménnyel kapcsolatos értesítést, tehát amennyiben a `registerAccountForMAM` metódust egy már regisztrált identitáshoz hívják meg, akkor az identitás nem feltétlenül kap újabb értesítést. Lehetnek olyan értesítések is, amelyek nem kapcsolódnak ezen metódusok meghívásához, mivel az SDK rendszeres időközönként próbálkozik beléptetésekkel a háttérben, az Intune szolgáltatástól érkező törlési kérések pedig kiválthatnak beléptetés-visszavonásokat.

* A regisztrációs metódusokat tetszőleges számú különböző identitáshoz meg lehet hívni, de jelenleg egyszerre csak egy felhasználói fiókot lehet sikeresen beléptetni. Ha több, az Intune-hoz licencelt és alkalmazásvédelmi szabályzattal célzott felhasználói fiókot regisztrálnak egyszerre vagy csaknem egy időben, akkor nem lehet előre tudni, hogy melyik nyeri a versenyt.

* Végül a `MAMEnrollmentManager` interfésztől lehet lekérdezni, hogy egy bizonyos fiók regisztrálva van-e, és a `getRegisteredAccountStatus` metódussal lehet lekérni az aktuális állapotát. Ha a megadott fiók nincs regisztrálva, a metódus a **null** értéket adja vissza. Ha a fiók regisztrálva van, a metódus a `MAMEnrollmentManager.Result` enumeráció valamely elemével jelzi a fiók állapotát.

### <a name="result-and-status-codes"></a>Eredmény- és állapotkódok

A fiók az első regisztráció során `PENDING` állapotban kerül be a rendszerbe, jelezvén, hogy a MAM-szolgáltatásba való kezdeti beléptetési kísérlet még nem fejeződött be. A beléptetési kísérlet befejezése után egy értesítés jön létre az alábbi táblázatban felsorolt eredménykódok valamelyikével. Ezenkívül a `getRegisteredAccountStatus()` metódus visszaadja a fiók állapotát, hogy az alkalmazás bármikor el tudja dönteni, hogy letiltsa-e az adott felhasználó hozzáférését a vállalati tartalomhoz. Ha a beléptetési kísérlet sikertelen, a fiók állapota idővel változhat, amint az SDK a háttérben tovább próbálkozik a beléptetéssel.

|Eredménykód | Magyarázat |
| -- | -- |
|AUTHORIZATION_NEEDED | Ez az eredmény azt jelzi, hogy az alkalmazás regisztrált `MAMServiceAuthenticationCallback`-példánya nem szolgáltatott jogkivonatot, vagy az érvénytelen volt.  Az alkalmazásnak be kell szereznie egy jogkivonatot, és lehetőség szerint meg kell hívnia az `updateToken()` metódust. |
| NOT_LICENSED | A felhasználónak nincs Intune-licence, vagy sikertelen volt az Intune MAM-szolgáltatáshoz való kapcsolódás.  Az alkalmazásnak nem felügyelt (normál) állapotban kell tovább futnia, a felhasználót pedig nem kell blokkolni.  Amennyiben később a felhasználónak lesz licence, az SDK rendszeresen próbálkozik a beléptetéssel. |
| ENROLLMENT_SUCCEEDED | A beléptetési kísérlet sikeres volt, vagy a felhasználó már korábban be lett léptetve.  Sikeres beléptetés esetén ezt az értesítést megelőzően egy szabályzatfrissítési értesítést is küld a rendszer.  A vállalati adatokhoz való hozzáférést engedélyezni kell. |
| ENROLLMENT_FAILED | A beléptetési kísérlet sikertelen volt.  A további részletek az eszköznaplókban találhatók.  Az alkalmazás ebben az állapotban nem engedélyezheti a vállalati tartalomhoz való hozzáférést, hiszen korábban megállapította, hogy a felhasználónak van Intune-licence.|
| WRONG_USER | Egy eszközön minden alkalmazást csak egy felhasználó léptethet be a MAM-szolgáltatásba.  Másik felhasználó csak akkor hajthat végre sikeres beléptetést, ha előbb az összes beléptetett alkalmazás beléptetését megszüntetik.  Ellenkező esetben ezt az alkalmazást is csak az elsődleges felhasználó léptetheti be.  Ez az ellenőrzés a licencellenőrzés után zajlik le, tehát a felhasználó céges adatokhoz való hozzáférését az alkalmazás sikeres beléptetéséig tiltani kell.|
| UNENROLLMENT_SUCCEEDED | A beléptetés megszüntetése sikeres volt.|
| UNENROLLMENT_FAILED | A beléptetés-megszüntetési kérés sikeres volt.  A további részletek az eszköznaplókban találhatók. |
| PENDING | A felhasználó első beléptetési kísérlete folyamatban van.  Az alkalmazás a beléptetés eredményének ismertté válásáig letilthatja a vállalati adatokhoz való hozzáférést, de nem köteles így tenni. |
| COMPANY_PORTAL_REQUIRED | A felhasználónak van Intune-licence, de az alkalmazást nem lehet beléptetni, amíg a Céges portál alkalmazás nincs telepítve az eszközre. Az Intune App SDK megpróbálja megtagadni az alkalmazáshoz való hozzáférést az adott felhasználótól, és felszólítani a Céges portál alkalmazás telepítésére (részletek alább). |


### <a name="company-portal-requirement-prompt-override-optional"></a>A Céges portál követelményére való figyelmeztetés felülbírálása (nem kötelező)

`COMPANY_PORTAL_REQUIRED` eredmény esetén az SDK letiltja az ahhoz az identitáshoz kapcsolódó tevékenységeket, amelynek a beléptetése a kérés tárgya volt. Az SDK ezen tevékenységekre válaszul egy, a Céges portál alkalmazás letöltését kérő üzenetet jelenít meg. Ha ezt a saját alkalmazásában szeretné elkerülni, a tevékenységek implementálhatják a `MAMActivity.onMAMCompanyPortalRequired` metódust.

Ennek meghívása még az előtt történik, hogy az SDK megjelenítené az alapértelmezett letiltó felhasználói felületet. Ha az alkalmazás módosítja a tevékenység identitását, vagy törli a beléptetést megkísérlő felhasználó regisztrációját, az SDK nem fogja letiltani a tevékenységet. Ebben az esetben az alkalmazás feladata a vállalati adatszivárgás megakadályozása.

### <a name="notifications"></a>Értesítések

Egy új `MAMNotification`-típust vezettünk be, amely a beléptetési kérés befejezéséről tájékoztatja az alkalmazást.  A `MAMEnrollmentNotification` értesítés fogadása a `MAMNotificationReceiver` interfészen keresztül történik, a [Regisztráció az SDK értesítéseire](#register-for-notifications-from-the-sdk) című szakaszban leírtak szerint.

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

A `getEnrollmentResult()` metódus a beléptetési kérés eredményét adja vissza.  Mivel a `MAMEnrollmentNotification` a `MAMUserNotification` kiterjesztése, a beléptetési kérés által érintett felhasználó identitása is elérhető. Az alkalmazásnak ezen értesítések fogadásához a [Regisztráció az SDK értesítéseire](#Register-for-notifications-from-the-SDK) című szakaszban leírtaknak megfelelően implementálnia kell a `MAMNotificationReceiver` interfészt.

A regisztrált felhasználói fiók állapota beléptetési értesítés fogadásakor megváltozhat, de bizonyos esetekben ez nem történik meg (ha például az `AUTHORIZATION_NEEDED` értesítés egy konkrétabb eredménykód, mondjuk a `WRONG_USER` után érkezik, akkor a fiók állapota továbbra is a konkrétabb eredményt fogja tükrözni).


## <a name="protecting-backup-data"></a>Biztonságimásolat-adatok védelme

Az Android Marshmallow (API 23) esetében az Android két módszert kínál az alkalmazásoknak az adataik biztonsági mentéséhez. Mindegyik lehetőség elérhető az alkalmazás számára, de különböző lépések végrehajtását igényli az Intune-adatvédelem megfelelő megvalósításához. Az alábbi táblázatban áttekintheti a megfelelő adatvédelmi működéshez szükséges műveleteket.  A biztonsági mentési módszerek részletes ismertetését az [Android API útmutatójában](http://developer.android.com/guide/topics/data/backup.html) olvashatja el.

### <a name="auto-backup-for-apps"></a>Alkalmazások automatikus biztonsági mentése

Az Android az Android Marshmallow rendszerű eszközökre telepített alkalmazásokhoz kezdte el kínálni a Google Drive-ra történő [automatikus teljes biztonsági mentést](https://developer.android.com/guide/topics/data/autobackup.html), függetlenül az alkalmazások cél API-jától. Ha az AndroidManifest.xml fájlban explicit módon **false** értékűre állítja az `android:allowBackup` attribútumot, akkor az alkalmazás soha nem kerül az Android által végrehajtott biztonsági mentések várólistájára, és a „vállalati” adatok megmaradnak az alkalmazásban. Ebben az esetben nincs további teendő.

Alapértelmezés szerint azonban az `android:allowBackup` attribútum true értékű még akkor is, ha az `android:allowBackup` nincs megadva a jegyzékfájlban. Ez azt jelenti, hogy az alkalmazások összes adatáról automatikus biztonsági másolat készül a felhasználó Google Drive-fiókjába, és ez olyan alapértelmezett működés, amely **adatszivárgási kockázatot** vet fel. Ezért az SDK az alább leírt módosításokat követeli meg az adatvédelem alkalmazásának biztosításához.  Fontos követnie az alábbi az irányelveket az ügyféladatok megfelelő védelme érdekében, ha az alkalmazást Android Marshmallow rendszerű eszközökön szeretné futtatni.  

Az Intune lehetővé teszi az Android összes elérhető [automatikus biztonsági mentési funkciójának](https://developer.android.com/guide/topics/data/autobackup.html) használatát, beleértve az egyéni szabályok definiálását XML-ben, de az adatok védelme érdekében követnie kell az alábbi lépéseket:

1. Ha az alkalmazás **nem** saját BackupAgentet használ, az alapértelmezett MAMBackupAgent használatával engedélyezheti az Intune szabályzatainak megfelelő automatikus teljes biztonsági mentéseket. Ebben az esetben figyelmen kívül hagyhatja a jegyzékfájl `android:fullBackupOnly` attribútumát, mert az a Microsoft biztonságimásolat-készítő ügynökére nem érvényes. Helyezze el az alábbi kódrészletet az alkalmazás jegyzékfájljában:

    ```xml
android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```

2. **[nem kötelező]** Amennyiben saját BackupAgent implementálása mellett döntött, mindenképpen a MAMBackupAgent vagy a MAMBackupAgentHelper osztályt kell használnia. Lásd a következő szakaszokat. Fontolja meg az áttérést az Intune (az 1. lépésben ismertetett) **MAMDefaultFullBackupAgent** osztályának használatára, amely egyszerű biztonsági mentést tesz lehetővé Android M-en és újabb rendszereken.

3. Amikor eldönti, hogy az alkalmazásról milyen típusú teljes biztonsági mentés készüljön (szűretlen, szűrt, semmilyen), az `android:fullBackupContent` attribútumot be kell állítania igaz vagy hamis értékűre vagy egy XML-erőforrásra az alkalmazásban.

4. Minden, az `android:fullBackupContent` attribútumban elhelyezett adatot _**kötelező**_ egy `com.microsoft.intune.mam.FullBackupContent` nevű metaadatcímkébe másolni.

    **1. példa:** ha azt szeretné, hogy az alkalmazás kizárás nélkül mindenről teljes biztonsági másolatot készítsen, állítsa mind az `android:fullBackupContent` attribútumot, mind a `com.microsoft.intune.mam.FullBackupContent` metaadatcímkét **true** állapotra:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **2. példa:** ha azt szeretné, hogy az alkalmazás a saját egyéni BackupAgentjét használja, és lemond az Intune-szabályzatoknak megfelelő, automatikus teljes biztonsági mentésekről, az attribútumot és a metaadatcímkét is **false** értékre kell állítani:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **3. példa:** Ha azt szeretné, hogy az alkalmazásról teljes biztonsági mentések készüljenek egy XML-fájlban definiált egyéni szabályoknak megfelelően, akkor az attribútumot és a metaadatcímkét ugyanarra az XML-erőforrásra állítsa be:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a>Kulcs/érték biztonsági mentés

A [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) (Kulcs/érték biztonsági mentés) lehetőség minden 8-as vagy újabb verziójú API számára elérhető, és az [Android Backup Service](https://developer.android.com/google/backup/index.html) szolgáltatásba tölti fel az adatokat, felhasználónként legfeljebb 5 MB-nyit. A Key/Value Backup használata esetén **BackupAgentHelper** vagy **BackupAgent** osztályt kell használni.

### <a name="backupagenthelper"></a>BackupAgentHelper

A BackupAgentHelper osztályt mind a natív androidos funkciókat, mind az Intune MAM-integrációt tekintve jóval egyszerűbb implementálni, mint a BackupAgentet. A BackupAgentHelper lehetővé teszi, hogy a fejlesztő teljes fájlokat és közös beállításokat regisztráljon rendre egy **FileBackupHelper** és egy **SharedPreferencesBackupHelper** osztályban, amelyek ezután létrehozáskor hozzáadódnak a BackupAgentHelper osztályhoz. Az alábbi lépéseket követve használhat BackupAgentHelper osztályt az Intune MAM-szolgáltatással:

1. Ha többidentitásos biztonsági mentést szeretne használni a BackupAgentHelper osztállyal, kövesse az [Extending BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper) (A BackupAgentHelper kiterjesztése) című angol nyelvű Android-útmutatót.

2. Osztályával terjessze ki a BackupAgentHelper, a FileBackupHelper és a SharedPreferencesBackupHelper osztályok MAM-os megfelelőjét.

|Androidos osztály | MAM-os megfelelő |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Ezen irányelvek betartása elősegíti a sikeres, többidentitásos biztonsági mentést és visszaállítást.

### <a name="backupagent"></a>BackupAgent

A BackupAgent segítségével sokkal egyértelműbben adható meg, hogy mely adatokról készüljön biztonsági mentés. Mivel az implementálás nagyrészt a fejlesztő felelőssége, több lépésre van szükség az Intune megfelelő adatvédelmének biztosításához. Azáltal, hogy a munka nagyobb része a fejlesztőre hárul, az Intune-integráció itt valamivel több jelentőséggel bír.

**MAM-integráció:**

1. Gondosan tanulmányozza át a [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) (Kulcs/érték biztonsági mentés) és főleg az [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) (A BackupAgent kiterjesztése) című Android-útmutatókat annak érdekében, hogy a BackupAgent-implementáció biztosan megfeleljen az androidos irányelveknek.

2. Osztályával terjessze ki a `MAMBackupAgent` osztályt.

**Többidentitásos biztonsági mentés:**

1. A biztonsági mentés megkezdése előtt ellenőrizze, hogy **a rendszergazda valóban engedélyezte-e** a szóban forgó fájlok vagy adatpufferek biztonsági mentését többidentitásos környezetben. Erre a célra szolgál a `MAMFileProtectionManager` és `MAMDataProtectionManager` osztályokban szereplő `isBackupAllowed` függvény. Ha valamely fájl vagy adatpuffer biztonsági mentése nem engedélyezett, azt ne vonja be a biztonsági mentésbe.

2. Ha a biztonsági mentés egy pontján biztonsági másolatot szeretne készíteni az 1. lépésben ellenőrzött fájlokhoz tartozó identitásokról, a `backupMAMFileIdentity(BackupDataOutput data, File … files)` függvényt kell meghívnia azokkal a fájlokkal, amelyekből adatokat szeretne kinyerni. Ez a művelet automatikusan új biztonsági mentési entitásokat hoz létre, és a `BackupDataOutput` kimenetre írja azokat. Ezeket az entitásokat automatikusan felhasználja a program a visszaállítás során.

**Többidentitásos visszaállítás:**

Az adatok biztonsági mentésével kapcsolatos Android-útmutatóban meg van adva egy általános algoritmus az alkalmazásadatok visszaállításához, az [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) (A BackupAgent kiterjesztése) című szakaszban pedig kódminta is található. A sikeres, többidentitásos visszaállítás érdekében kötelező a kódmintában megadott általános struktúrát követni, különös tekintettel az alábbiakra:

1.  A biztonsági mentési entitásokon egy `while(data.readNextHeader())`* ciklussal kell végighaladni.

2.  Ha a `data.getKey()`* nem egyezik meg az `onBackup`-ba írt kulccsal, akkor meg kell hívni a `data.skipEntityData()`* függvényt. Enélkül előfordulhat, hogy a visszaállítások nem járnak sikerrel.

3.  Kerülje a visszatérést a biztonsági mentési entitások `while(data.readNextHeader())`* szerkezetben való feldolgozása során, mert elveszhetnek az automatikusan kiírt entitások.

* A `data` helyére az alkalmazásnak a visszaállításkor átadott **BackupDataInput** helyi változónevét kell behelyettesíteni.

## <a name="multi-identity-optional"></a>Több identitás használata (nem kötelező)

### <a name="overview"></a>Áttekintés
Az Intune App SDK alapértelmezés szerint az alkalmazás egészére alkalmazza a szabályzatot. A többszörös identitás az Intune-alkalmazásvédelem választható funkciója, amelynek engedélyezése esetén a szabályzatok identitásonként alkalmazhatók. Ez a többi alkalmazásvédelmi funkciónál jelentősen nagyobb mértékű közreműködést igényel az alkalmazástól.

Az alkalmazásnak _kötelező_ tájékoztatnia az SDK-t, amikor módosítani készül az aktív identitást, és az SDK is értesíti az alkalmazást, amikor szükség van az identitás megváltoztatására. Ha a felhasználó már beléptette az eszközt vagy az alkalmazást, az SDK regisztrálja ezt az identitást, és ezt tekinti az Intune-ban felügyelt elsődleges identitásnak. Az alkalmazás többi felhasználójával nem felügyeltként bánik, szabályzatbeállításaik korlátlanok.

> [!NOTE]
> Jelenleg eszközönként csak egy Intune által felügyelt identitás támogatott.

Felhívjuk, hogy az identitás egyszerűen egy karakterláncként van definiálva. Az identitásokban **nem számítanak különbözőnek a kis- és a nagybetűk**, és az SDK nem feltétlen olyan kis- és nagybetűkkel adja vissza a tőle kért identitásokat, mint ahogyan az az identitás beállításakor eredetileg meg volt adva.


### <a name="enabling-multi-identity"></a>Több identitás használatának engedélyezése

Alapértelmezés szerint az összes alkalmazás egyszeres identitással rendelkező alkalmazásnak minősül. Az AndroidManifest.xml-ben elhelyezett alábbi metaadatokkal lehet jelezni, hogy egy alkalmazás képes több identitás kezelésére.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>Az identitás beállítása

A fejlesztők (csökkenő prioritási sorrendben) a következő szinteken állíthatják be az alkalmazás identitását:

  1. Szál szintje
  2. Környezet (általában tevékenység) szintje
  3. Folyamat szintje

A szál szintjén beállított identitás felülírja a környezet szintjén beállított identitást, mely utóbbi felülírja a folyamat szintjén beállított identitást. Környezet szintjén beállított identitást csak megfelelő társított helyzetekben használnak. A fájl-I/O-műveleteknek például nincs társított környezetük. A `MAMPolicyManager` következő metódusaival lehet beállítani az identitást, illetve beolvasni a korábban beállított identitásértékeket.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

  /**
   * Get the currently applicable app policy. Same as
   * MAMComponents.get(AppPolicy.class). This method does
   * not take the context identity into account.
   */
  public static AppPolicy getPolicy();

  /**
   * Get the currently applicable app policy, taking the context
   * identity into account.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);

  ```

>[!NOTE]
> Az alkalmazás identitását null értékre állítva törölheti.
>
> Az üres karakterlánc használható olyan identitásként, amelyre biztosan nem vonatkozik alkalmazásvédelmi szabályzat.

#### <a name="results"></a>Eredmény
Az identitást beállító összes metódus a `MAMIdentitySwitchResult` objektummal adja vissza az eredményértékeket. Négy visszaadható érték van:

| Visszatérési érték | Forgatókönyv |
|--|--|
| SUCCEEDED | Az identitásváltás sikeres volt. |
| NOT_ALLOWED | Az identitásváltás nem engedélyezett. <br><br>Ez akkor fordul elő, amikor valaki egy másik, a beléptetett felhasználóval egyazon szervezethez tartozó felügyelt felhasználóra próbál átváltani; vagy ha valaki a Felhasználói felület (Környezet) identitást próbálja beállítani, amikor egy másik identitás van beállítva az aktuális szálhoz. |
| CANCELLED | A felhasználó megszakította az identitásváltást. Ez általában úgy történik, hogy megnyomja a Vissza gombot egy PIN-kódot kérő vagy hitelesítési üzenetnél. |
| FAILED | Az identitásváltás ismeretlen okból nem sikerült.|


Környezet identitás beállítása esetén az eredmény aszinkron módon jelenik meg. Ha a Környezet egy tevékenység, akkor az SDK mindaddig nem tudja, hogy sikeres volt-e az identitásváltás, amíg feltételes indítás történik – itt ugyanis a felhasználónak meg kell adnia a PIN-kódját vagy vállalati hitelesítő adatait. Az alkalmazásnak az elvárások szerint egy `MAMSetUIIdentityCallback` interfészt implementálva kell fogadnia ezt az eredményt, bár ennél a paraméternél a null érték átadása is megengedett.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

A tevékenységek identitását közvetlenül a `MAMActivity` egy metódusával, a `MAMPolicyManager.setUIPolicyIdentity` meghívása nélkül is beállíthatja. A metódus az alábbi:

```java
     public final void switchMAMIdentity(final String newIdentity);
```

Az `MAMActivity` osztály metódusát felül is lehet bírálni, ha azt szeretné, hogy az alkalmazás értesítést kapjon a tevékenység identitásának módosítására tett kísérletek eredményéről.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> Előfordulhat, hogy az identitásváltás után újból létre kell hozni a tevékenységet. Ebben az esetben a `onSwitchMAMIdentityComplete` visszahívása lesz elküldve a tevékenység új példányának.


### <a name="implicit-identity-changes"></a>Az identitás implicit megváltoztatása

Az alkalmazás identitásbeállítási képessége mellett a szálak és a környezetek identitása megváltoztatható a más, alkalmazásvédelmi szabályzattal ellátott Intune-kompatibilis alkalmazásból beérkező adatok alapján is.

#### <a name="examples"></a>Példák

  1. Ha például egy tevékenység egy másik MAM-alkalmazás által küldött `Intent` alapján indul el, akkor a tevékenység identitása a másik alkalmazásban az `Intent` elküldésekor érvényes identitás alapján lesz beállítva.

  2.  A szolgáltatások esetében a szál identitása hasonlóan lesz beállítva az `onStart`- vagy az `onBind`-hívások időtartamára. Átmenetileg a `Binder`-be érkező, az `onBind` által visszaadott hívások is beállítják a szál identitását.

  3. A beérkező hívások a `ContentProvider` esetében is hasonlóképpen beállítják a szál identitását az időtartamukra vonatkozóan.


  Ezenkívül a tevékenységekkel kapcsolatos felhasználói beavatkozások is előidézhetnek implicit identitásváltást.

  **Példa:** ha egy felhasználó a `Resume` művelet közben megszakítja az engedélyezési kérést, akkor implicit módon üres identitásra való váltást eredményez.

  Lehetőség van arra, hogy az alkalmazás értesüljön ezekről a váltásokról, és szükség esetén megtiltsa őket. A `MAMService` és a `MAMContentProvider` a következő, az alosztályok által felülbírálható metódust teszi elérhetővé:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  A `MAMActivity` osztályban a metódusnak még egy paramétere van:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * Az `AppIdentitySwitchReason` rögzíti az implicit váltás forrását, és a következő értékeket tudja fogadni: `CREATE`, `RESUME_CANCELLED` és `NEW_INTENT`.  A `RESUME_CANCELLED` ok akkor használható, amikor a tevékenység folytatása PIN-kódot kérő, hitelesítési vagy egyéb megfelelőségi felhasználói felület megjelenítését idézi elő, és a felhasználó megpróbál kilépni erről a felhasználói felületről, általában a Vissza gomb használatával.


  * Az `AppIdentitySwitchResultCallback` a következőképpen történik:

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    Az ```AppIdentitySwitchResult``` értéke vagy SUCCESS, vagy FAILURE.

Az `onMAMIdentitySwitchRequired` metódus hívandó az összes implicit identitásváltás esetében, kivéve azokat, amelyek a `MAMService.onMAMBind` által visszaadott Binderen keresztül történtek. Az `onMAMIdentitySwitchRequired` alapértelmezett implementációi a következő metódusokat hívják meg azonnal:

*  `reportIdentitySwitchResult(FAILURE)` – ha az ok RESUME_CANCELLED.

*  `reportIdentitySwitchResult(SUCCESS)` – minden más esetben.

  Nem valószínű, hogy az alkalmazások többségének másképpen kell blokkolnia vagy késleltetnie az identitásváltást, de ha mégis erre van szükség, akkor a következő szempontokat kell figyelembe venni:

  * Az identitásváltás blokkolásakor az eredmény ugyanaz lesz, mint amikor a `Receive` megosztási beállítások tiltják le az adatok beérkezését.

  * Ha egy szolgáltatás a főszálon fut, a `reportIdentitySwitchResult` hívását **kötelező** szinkron módon végrehajtani, ellenkező esetben a felhasználói felület szála leáll.

  * **Tevékenység** létrehozásakor az `onMAMIdentitySwitchRequired` hívása megelőzi az `onMAMCreate` hívását. Ha az alkalmazásnak felhasználói felületet kell megjelenítenie annak megállapításához, hogy engedélyezhető-e az identitásváltás, akkor az adott felhasználói felületet *egy másik* tevékenységgel kell megjeleníteni.

  * Amikor egy **tevékenységben** az üres identitásra való váltás oka RESUME_CANCELLED, akkor az alkalmazásnak módosítania kell a folytatott tevékenységet, hogy az adatmegjelenítés az adott identitásváltásnak megfelelő legyen.  Ha ez nem lehetséges, az alkalmazásnak el kell utasítania a váltást, és újból kérnie kell a felhasználót a folytatáshoz használt identitás szabályzatának teljesítésére (például a PIN-kód megadását kérő képernyőt megjelenítve).

    > [!NOTE]
    > A többszörös identitást támogató alkalmazások mindig fogadják a felügyelt és a nem felügyelt alkalmazásoktól érkező adatokat. Az alkalmazás feladata, hogy felügyelt módon kezelje a felügyelt identitásokból érkező adatokat.

  Ha a kért identitás felügyelt (ezt a `MAMPolicyManager.getIsIdentityManaged` metódussal lehet ellenőrizni), de az alkalmazás nem tudja használni a fiókot (például mert a fiókokat, így az e-mail-fiókokat először be kell állítani az alkalmazásban), akkor el kell utasítania az identitásváltást.



  ### <a name="file-protection"></a>Fájlvédelem

  Amikor létrehozza a fájlokat, a rendszer identitást társít hozzájuk a szál és a folyamat identitása alapján. Ez az identitás lesz használva a fájltitkosításhoz és a szelektív törléshez is. Csak azok a fájlok lesznek titkosítva, amelyek identitása felügyelt, és szabályzata előírja a titkosítást. Az SDK alapértelmezett szelektív törlése csak azokat a felügyelt identitáshoz tartozó fájlokat fogja törölni, amelyekre törlést kértek. Az alkalmazás a `MAMFileProtectionManager` osztállyal kérdezheti le vagy módosíthatja a fájlok identitását.

  ```java
    public final class MAMFileProtectionManager {

        /**
         * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
         * future protection changes.
         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
         */
        public static void protect(final File file, final String identity) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File or directory to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```

A fájl identitásának címkézésénél az offline mód különbségnek számít. A következő szempontokat kell figyelembe venni:

  * Ha a Céges portál nincs telepítve, akkor a fájlok nem láthatók el identitáscímkével.

  * Ha a Céges portál telepítve van, de az alkalmazásra nem vonatkozik Intune MAM-szabályzat, akkor a fájlokat nem lehet megbízhatóan ellátni identitáscímkével.

  * Amikor elérhetővé válik a fájlok identitáscímkézése, akkor az összes korábban létrehozott fájl személyesként/nem felügyeltként (az üres karakterláncú identitáshoz tartozó fájlként) lesz kezelve, kivéve, ha az alkalmazás korábban egyidentitásos felügyelt alkalmazásként lett telepítve: ebben az esetben a fájlok a beléptetett felhasználóhoz tartozó fájlokként lesznek kezelve.

### <a name="directory-protection"></a>Könyvtárvédelem

A könyvtárakat is a fájlok védelmére szolgáló `protect` metódussal lehet védeni. Ne feledje, hogy a könyvtárvédelem rekurzívan érvényes a könyvtárban lévő összes fájlra és alkönyvtárra, illetve a benne létrehozott új fájlokra. Emiatt az igen nagy méretű könyvtárak esetében a `protect` hívás hosszabb ideig tarthat. Éppen ezért a sok fájlt tartalmazó könyvtárakra védelmet alkalmazó alkalmazásoknak érdemes a `protect` hívást aszinkron módon, háttérszálon futtatni.

### <a name="data-protection"></a>Adatvédelem

A fájlok nem címkézhetők meg több identitáshoz tartozó fájlként. Azok az alkalmazások, amelyeknek egy fájlban kell tárolniuk különböző felhasználók adatait, manuálisan tehetik meg ezt a `MAMDataProtectionManager` által biztosított szolgáltatásokkal. Ez lehetővé teszi az alkalmazás számára az adatok titkosítását és hozzákötését egy adott felhasználóhoz. A titkosított adatok lemezen, fájlban tárolhatók. Az identitáshoz tartozó adatokat lekérdezheti, és az adatokat visszafejtheti.

A `MAMDataProtectionManager` osztályt hasznosító alkalmazásoknak fogadót kell implementálniuk a `MANAGEMENT_REMOVED` értesítéshez. Az értesítés lefutása után az ezen osztállyal védett pufferek nem lesznek olvashatóak, ha a fájltitkosítást a pufferek védett állapotában kapcsolták be. Az alkalmazás úgy tudja megoldani ezt a problémát, ha az értesítés időtartama alatt az összes pufferen meghívja a MAMDataProtectionManager.unprotect metódust. Ne feledje, hogy az értesítés időtartama alatt a protect metódust is biztonságosan meg lehet hívni, ha az identitásadatokat meg szeretnék őrizni – a titkosítás ez idő alatt garantáltan le van tiltva.

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}

```

### <a name="content-providers"></a>Tartalomszolgáltatók

Ha az alkalmazás a **ParcelFileDescriptor** elemtől különböző vállalati adatokat szolgáltat egy **ContentProvider** objektumon keresztül, akkor az alkalmazásnak a `MAMContentProvider` osztály `isProvideContentAllowed(String)` metódusát meghívva kell átadnia a tartalomtulajdonos identitás UPN-jét (egyszerű felhasználónevét). Ha ez a függvény hamis értéket ad vissza, akkor a tartalom *nem* adható vissza a hívónak. A tartalomszolgáltatón keresztül visszaadott fájlleírók kezelése automatikusan a fájl identitása alapján történik.

### <a name="selective-wipe"></a>Szelektív törlés

Ha egy alkalmazás regisztrál a `WIPE_USER_DATA` értesítésre, akkor nem veheti igénybe az SDK alapértelmezett szelektív törlési funkcióját. A többidentitásos alkalmazások esetében ez nagyobb jelentőségű tényező lehet, mivel a MAM alapértelmezett szelektív törlése csak a törlendő identitáshoz tartozó fájlokat fogja törölni.

Ha a többidentitásos alkalmazás szeretné végrehajtatni a MAM alapértelmezett szelektív törlését, _**és**_ ezenfelül saját törlési műveleteit is végre szeretné hajtani, akkor célszerű feliratkoznia a `WIPE_USER_AUXILIARY_DATA` értesítésekre. Ezt az értesítést az SDK közvetlenül azelőtt küldi el, hogy végrehajtaná a MAM alapértelmezett szelektív törlési műveletét. Egyazon alkamazásnak nem szabad mind a WIPE_USER_DATA, mind a WIPE_USER_AUXILIARY_DATA értesítésre feliratkoznia.


## <a name="style-customization-optional"></a>Stílus testreszabása (nem kötelező)

A MAM SDK-ban létrehozott nézetek megjelenését testre lehet szabni, hogy jobban illeszkedjenek az SDK-t integráló alkalmazáshoz. Meg lehet szabni az elsődleges, a másodlagos és a háttérszínt, valamint az alkalmazás emblémájának méretét. Ez a testreszabás nem kötelező. Ha nincs konfigurálva egyéni stílus, a rendszer az alapértelmezéseket használja.


### <a name="how-to-customize"></a>A testreszabás menete
Ha módosítani szeretné az Intune MAM-nézeteinek stílusát, először készítsen stílus-felülíró XML-fájlt. Ezt helyezze el az alkalmazás „/res/xml” könyvtárában, és adjon neki tetszőleges nevet. Az alábbi példa bemutatja a fájl szükséges formátumát.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>

```

Az alkalmazásban már meglévő erőforrásokat kell újrahasználnia, tehát például a zöld színt a colors.xml fájlban kell definiálni, és itt hivatkozni, de a „#0000ff” hexa színkódot itt nem használhatja. Az alkalmazásembléma legfeljebb 110 dip (dp) méretű lehet. Kisebb emblémát is megadhat, de az optimális megjelenés érdekében érdemes kihasználni a maximális méretet. Ha túllépi a 110 dipes határt, a képet a rendszer lekicsinyíti, amitől valószínűleg homályos lesz.

Alább felsoroljuk az összes megengedett stílusattribútumot, az általuk szabályozott felületi elemeket, XML-attribútumnevüket és a hozzájuk várt erőforrástípusokat.

|Stílusattribútum | Érintett felületi elem | Attribútumelem neve | Várt erőforrástípus |
| -- | -- | -- | -- |
| Háttérszín | A PIN-kódot bekérő képernyő háttérszíne <Br>A PIN-kód mezőjének kitöltőszíne | background_color | Szín |
| Előtérszín | Előtérbeli szöveg színe <br> A PIN-kód mezőjének szegélyszíne alapértelmezett állapotban <br> A PIN-kód mezőjébe beírt (akár rejtjelezett) karakterek színe| foreground_color | Szín|
| Kiemelőszín | A PIN-kód mezőjének szegélyszíne kiemelt állapotban <br> Hivatkozások |accent_color | Szín |
| Alkalmazás emblémája | Az Intune PIN-kódot bekérő képernyőjén megjelenő nagy ikon | logo_image | Rajzolható |

## <a name="limitations"></a>Korlátozások

### <a name="file-size-limitations"></a>Fájlméretre vonatkozó korlátozások

A [ProGuard](http://proguard.sourceforge.net/) nélkül futó nagyméretű kódbázis esetén a Dalvik végrehajtható fájlformátum korlátozásai problémát jelenthetnek. Konkrétan a következő korlátozások fordulhatnak elő:

1.  A mezőkre vonatkozó 65 KB-os korlát.
2.  A metódusokra vonatkozó 65 KB-os korlát.



### <a name="policy-enforcement-limitations"></a>Szabályzatbetartatási korlátozások

* **Képernyőfelvétel**: Az SDK nem tud új képernyőfelvétel-beállítási értéket kikényszeríteni azon tevékenységeknél, amelyeknél már lefutott az Activity.onCreate. Ez olyan időszakot eredményezhet, amikor az alkalmazás a képernyőfelvételek letiltására lett konfigurálva, de továbbra is lehet képernyőfelvételt készíteni.

* **Tartalomfeloldók használata**: Az „átvitel vagy fogadás” Intune-szabályzat részben vagy teljesen blokkolhatja más alkalmazások tartalomszolgáltatójának tartalomfeloldóval történő elérését. Ennek következtében a ContentResolver metódusok null vagy hibaértéket fognak visszaadni (például az `openOutputStream` a `FileNotFoundException` kivételhibát fogja okozni, ha blokkolva van). Az alkalmazás a következő hívással állapíthatja meg, hogy a tartalomfeloldón keresztüli adatírás sikertelenségét házirend okozta (vagy hogy egy házirend ilyen hibát okozna):

    ```java
    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI);
    ```

### <a name="exported-services"></a>Exportált szolgáltatások

 Az Intune App SDK-ban szereplő AndroidManifest.xml fájlban szerepel a **MAMNotificationReceiverService** szolgáltatás, amelynek exportált szolgáltatásnak kell lennie ahhoz, hogy a Céges portál értesítéseket küldhessen a kompatibilis alkalmazásoknak. A szolgáltatás ellenőrzi a hívót annak ellenőrzéséhez, hogy csak a vállalati portál számára engedélyezett-e az értesítések küldése.



## <a name="expectations-of-the-sdk-consumer"></a>Az SDK-használók elvárásai

Az Intune SDK fenntartja az Android API által biztosított szerződést, bár a szabályzatok betartatása miatt gyakrabban léphetnek fel hibaállapotok. Az alábbi androidos gyakorlati tanácsok csökkentik a hibák valószínűségét:

* Azon androidos SDK-függvények, amelyek null értékkel is visszatérhetnek, nagyobb valószínűséggel lesznek null értékűek.  A problémák minimalizálása érdekében biztosítsa, hogy a megfelelő helyeken legyenek null-ellenőrzések.

* A lekérdezhető funkciókat a MAM-os helyettesítő API-kkal kell lekérdezni.

* Minden származtatott függvénynek meg kell hívnia a szülőosztálybeli verzióját.

* Kerülje az API-k nem egyértelmű módon való használatát. Így például az `Activity.startActivityForResult` requestCode ellenőrzése nélküli használata működésbeli furcsaságokat idézhet elő.

## <a name="recommended-android-best-practices"></a>Ajánlott gyakorlati tanácsok Androidon

* Lehetőség szerint minden kódtárprojektnek azonos android:package csomagot kell használnia. Ez nem fog szórványos hibákat jelenteni futásidőben, mivel ez a probléma pusztán a buildelés során áll fenn. Az Intune App SDK újabb verziói ki fognak küszöbölni bizonyos párhuzamosságokat.

* Mindig az elérhető legújabb Android SDK buildelőeszközeit használja.

* Távolítsa el a felesleges és használaton kívüli kódtárakat (pl. android.support.v4)

