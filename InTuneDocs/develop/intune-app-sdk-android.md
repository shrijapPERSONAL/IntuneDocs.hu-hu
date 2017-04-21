---
title: "A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek | Microsoft Docs"
description: "Az Androidhoz készült Microsoft Intune App SDK lehetővé teszi, hogy az Intune mobilalkalmazás-felügyeleti (MAM) funkcióját beépítse Android-alkalmazásaiba."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 17fa23f1d04e22a2cb10452fe3a9425f7482a6de
ms.lasthandoff: 04/14/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>A Microsoft Intune App SDK Androidon – útmutató fejlesztőknek

> [!NOTE]
> Kezdésként érdemes lehet elolvasni [Az Intune APP SDK áttekintése](intune-app-sdk.md) című cikket, amely ismerteti az SDK aktuálisan elérhető funkcióit, valamint az integrációval kapcsolatos előkészületeket a támogatott platformokon.

Az Androidhoz készült Microsoft Intune App SDK lehetővé teszi, hogy az Intune mobilalkalmazás-felügyeleti (MAM) funkcióját beépítse Android-alkalmazásaiba. A MAM-kompatibilis alkalmazás az, amelyik integrálva van az Intune App SDK-val. Mindez lehetővé teszi a rendszergazdák számára, hogy szabályzatokat telepítsenek a mobilalkalmazásra vonatkozóan, ha az Intune aktívan felügyeli az alkalmazást.

## <a name="whats-in-the-sdk"></a>Az SDK tartalma

Az Intune App SDK for Android egy szabványos androidos függvénytár, amely nem rendelkezik külső függőségekkel. Az SDK a következőket tartalmazza:  

* **Microsoft.Intune.MAM.SDK.jar**: Azok a felületek, amelyek ahhoz szükségesek, hogy a MAM engedélyezve legyen, és az Intune Munkahelyi portál alkalmazásával lehetséges legyen az együttműködés. Az alkalmazásoknak androidos függvénytárhivatkozásként kell megadniuk.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: A MAM azon alkalmazásokban való engedélyezéséhez szükséges felületek, amelyek az Android v4 támogatási függvénytárat használják. Az ezt a támogatást igénylő alkalmazásoknak közvetlenül kell hivatkozniuk a jar-fájlra.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: A MAM azon alkalmazásokban való engedélyezéséhez szükséges felületek, amelyek az Android v7 támogatási függvénytárat használják. Az ezt a támogatást igénylő alkalmazásoknak közvetlenül kell hivatkozniuk a jar-fájlra.

* **Az erőforrás-könyvtár**: Az SDK által alkalmazott erőforrások (például karakterláncok).

* **Microsoft.Intune.MAM.SDK.aar**: Az SDK-összetevők a Support.V4 és Support.V7 JAR-fájlok kivételével. Ez a fájl az egyes összetevők helyett használható, ha a buildelési rendszer támogatja az AAR-fájlokat.

* **AndroidManifest.xml**: A további belépési pontokra és a függvénytárra vonatkozó követelmények.

* **THIRDPARTYNOTICES. TXT**: A harmadik féltől származó és/vagy OSS kódnak az alkalmazásba fordítására vonatkozó tájékoztatás.

## <a name="requirements"></a>Követelmények

Az Intune App SDK egy lefordított androidos projekt. Ez azt jelenti, hogy jelentős mértékben független az alkalmazás által a minimális vagy a cél API-verzióhoz használt Android-verziótól. Az SDK az Android API 14 (Android 4.0 +) és az Android API 24 közötti verziókat támogatja.

Az androidos Intune App SDK-nak szüksége van a [Munkahelyi portál](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) alkalmazásra ahhoz, hogy lehetővé tegye a MAM-szabályzatok működését. Az eszközregisztráció nélküli MAM esetében a felhasználónak *nem* kell regisztrálnia az eszközt a Munkahelyi portál alkalmazással.


## <a name="how-the-intune-app-sdk-works"></a>Az Intune App SDK működése

###<a name="entry-points"></a>Belépési pontok

Az Intune App SDK az alkalmazás forráskódjának módosítását igényli az Intune alkalmazásfelügyeleti szabályzatainak engedélyezéséhez. Ez az androidos alaposztályok egyenértékű Intune-osztályokra való cseréjével történik. Utóbbiak nevében a `MAM` előtag szerepel. Az SDK-osztályok az androidos alaposztály és az alkalmazás saját származtatott verziója között helyezkednek el. A tevékenységek esetében ez például egy, az alábbihoz hasonló öröklési hierarchiát eredményez: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Amikor például az `AppSpecificActivity` interakcióba lép a szülőjével (például meghívja a következőt: `super.onCreate()`), a `MAMActivity` lesz a szülőosztály.

A szokásos androidos alkalmazások egyszeres móddal rendelkeznek, és a [Context](https://developer.android.com/reference/android/content/Context.html) objektumukon keresztül férhetnek hozza a rendszerhez. A beépített Intune App SDK-t tartalmazó alkalmazások viszont kettős móddal rendelkeznek. Ezek az alkalmazások a továbbiakban is a `Context` objektumon keresztül érik el a rendszert. Az Android a használt alapszintű `Activity` alapján biztosítja a `Context` objektumot, vagy a rendszer intelligensen multiplexel a rendszer korlátozott nézete, illetve az Android által biztosított `Context` között.

Ha a használt androidos [belépési pontot](https://developer.android.com/guide/components/fundamentals.html) felülírja annak MAM-megfelelője, a belépési pont életciklusának MAM-verzióját kell használni (a `MAMApplication` osztály kivételével).

Így például a `MAMActivity` származtatásakor az `onCreate` felülírása, illetve a `super.onCreate` metódus hívása helyett az `Activity` tevékenységnek felül kell írnia az `onMAMCreate` metódust, és meg kell hívnia a `super.onMAMCreate` metódust. Ez bizonyos esetekben lehetővé teszi, hogy az Intune korlátozza az `Activity` elindítását (többek között).


###<a name="sdk-permissions"></a>Az SDK engedélyei

Az Intune App SDK három [androidos rendszerengedélyt](https://developer.android.com/guide/topics/security/permissions.html) igényel azokhoz az alkalmazásokhoz, amelyekbe beépül:

* `android.permission.GET_ACCOUNTS` (kérése futásidőben történik, ha szükség van rá)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Az Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) a közvetített hitelesítés végrehajtásához igényli ezeket az engedélyeket. Ha az alkalmazás nem kapja meg ezeket az engedélyeket, vagy ha a felhasználó visszavonja ezeket az engedélyeket, akkor a közvetítőt igénylő hitelesítési folyamatok (a Munkahelyi portál alkalmazás) le lesznek tiltva.


###<a name="company-portal-app"></a>Vállalati portál alkalmazás

Miért van szükség a Munkahelyi portál alkalmazásra? Ha a Munkahelyi portál alkalmazás telepítve van az eszközre, és az Intune szolgáltatásból beolvasta a felhasználóra vonatkozó alkalmazáskorlátozási szabályzatokat, az SDK belépési pontjainak inicializálása aszinkron módon történik. Inicializálás csak akkor szükséges, amikor az Android először hozza létre a folyamatot. Az inicializálás során létrejön a kapcsolat a Munkahelyi portál alkalmazással, és a rendszer beolvassa az alkalmazáskorlátozási szabályzatot.  

> [!NOTE]
> Ha a Munkahelyi portál alkalmazás nincs telepítve az eszközre, az Intune használatát támogató alkalmazás működése nem változik meg, és az alkalmazás továbbra is úgy működik, mint a szokásos alkalmazások.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Az Intune App SDK integrálása

A korábban leírtaknak megfelelően az SDK az alkalmazás forráskódjának módosítását igényli ahhoz, hogy működni tudjanak alkalmazásfelügyeleti szabályzatok. A mobilalkalmazás-felügyeletnek az alkalmazásban való engedélyezéséhez a következő lépéseket kell elvégeznie.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Az osztályok, a metódusok és a tevékenységek lecserélése a MAM-kompatibilis megfelelőkre (kötelező)

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
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (csak akkor szükséges, ha a Binder létrehozása nem androidos felületdefiníciós nyelvű (AIDL) felületen történik) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Supp, vagy egyt.v4.jar**:

| Androidos osztály – Intune MAM | Intune App SDK-beli helyettesítése |
|--|--|
| Android.support.v4.App.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| Android.support.v4.App.TaskStackBuilder | MAMTaskStackBuilder
| Android.support.v4.Content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Supp, vagy egyt.v7.jar**:

|Androidos osztály | Intune App SDK-beli helyettesítése |
|--|--|
|Android.support.v7.App.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Ne feledje: ha a használt androidos [belépési pontot](https://developer.android.com/guide/components/fundamentals.html) felülírja annak MAM-megfelelője, a belépési pont életciklusának MAM-verzióját kell használni (a `MAMApplication` osztály kivételével).
>
>Így például a `MAMActivity` származtatásakor az `onCreate` felülírása, illetve a `super.onCreate` metódus hívása helyett az `Activity` tevékenységnek felül kell írnia az `onMAMCreate` metódust, és meg kell hívnia a `super.onMAMCreate` metódust. Ez bizonyos esetekben lehetővé teszi, hogy az Intune korlátozza az `Activity` elindítását (többek között).

#### <a name="pendingintent-classes-and-renamed-methods"></a>PendingIntent osztályok és átnevezett metódusok

A MAM egyik belépési pontjából történő származtatást követően a megszokott módon használhatja a `Context` szintet, például elindíthatja az `Activity` osztályokat, és használhatja a következőt is: `PackageManager`.  

A `PendingIntent` osztályok kivételt képeznek e szabály alól. Az ilyen osztályok meghívásakor módosítani kell az osztály nevét. A `PendingIntent.get*` helyett például a `MAMPendingIntent.get*` metódust kell használni. Az így létrejövő `PendingIntent` már szintén a megszokott módon használható.

Bizonyos esetekben az androidos osztályban rendelkezésre álló metódus végsőként van megjelölve a helyettesítő MAM-osztályban. Ebben az esetben a helyettesítő MAM-osztály egy hasonlóan elnevezett metódust biztosít (általában a `MAM` utótaggal), amelyet felül kell írni. Így például a `ContentProvider.query`felülírása helyett a `MAMContentProvider.queryMAM`. A Java-fordítónak érvényesítenie kell a végső korlátozásokat az eredeti metódus véletlen felülbírálásának elkerülése érdekében az egyenértékű MAM-metódus helyett.

###<a name="enable-features-that-require-app-participation"></a>Alkalmazás részvételét igénylő szolgáltatások engedélyezése

Egyes szabályzatokat az SDK önállóan nem tud megvalósítani. Az alkalmazás a saját működésének szabályozásával képes e funkciókat biztosítani. Ehhez több API-t használ, amelyek az alábbi `AppPolicy` felületen találhatók.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
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
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
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

### <a name="enable-it-control-over-app-saving-behavior"></a>Az alkalmazásbeli mentési működés rendszergazdai felügyeletének engedélyezése

Számos alkalmazás valósít meg olyan funkciókat, amelyek lehetővé teszik a felhasználó számára a fájlok helyi háttértárra vagy felhőbeli tárolószolgáltatásba való mentését. Az Intune App SDK segít a vállalati rendszergazdáknak az adatszivárgás elleni, a szervezetek igényei szerinti szabályzati korlátozások alkalmazásával.  A rendszergazda által beállítható egyik szabályzat arra vonatkozik, hogy a felhasználók menthetnek-e fájlokat nem felügyelt személyes adattárba. Ezek közé tartoznak a helyi mentési helyek, az SD-kártyák és a harmadik felek biztonsági mentési szolgáltatásai.

A funkció engedélyezéséhez alkalmazás részvételére van szükség. Ha az alkalmazás közvetlenül is lehetővé teszi a személyes vagy felhőbeli helyekre való mentést, ezt a funkciót meg kell valósítani ahhoz, hogy a vállalati rendszergazda szabályozhassa, engedélyezve van-e a mentés az adott helyre.   

Az alkalmazás a következő hívással megállapíthatja, hogy a szabályzat érvényesítve van-e. A hívás tudatja az alkalmazással, hogy az Intune aktuális rendszergazdája által használt szabályzatok engedélyezik-e a személyes adattárba történő mentést. Az alkalmazás ezt követően már képes érvényesíteni a szabályzatot, mivel az előző lépéssel megismerte a felhasználó számára az alkalmazás keretében rendelkezésre álló adattárat.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> A `MAMComponents.get(AppPolicy.class)` mindig nem null értékű alkalmazásszabályzatot ad vissza, akkor is, ha az eszközre vagy az alkalmazásra nem vonatkozik Intune-beli felügyeleti szabályzat.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>Annak lehetővé tétele, hogy az alkalmazás észlelhesse, szükség van-e a PIN-kódokra vonatkozó szabályzatra

Az Intune bizonyos alkalmazáskorlátozásai esetében beállíthatja, hogy az alkalmazás letiltsa egyes funkcióit, hogy ne ismétlődjenek az Intune App SDK-ban. Ha például az alkalmazásnak saját PIN-kódot kérő felhasználói felülete van, akkor esetleg érdemes lehet letiltani az SDK-nak azt a beállítását, amely felszólítja a felhasználót a PIN-kód megadására.

Az alkalmazás a következő hívást használja annak megállapítására, hogy az Intune PIN-kódokra vonatkozó szabályzata be van-e állítva PIN-kód kérésére az alkalmazás indításához:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>Regisztráció az SDK értesítéseire  

Az Intune App SDK lehetővé teszi, hogy az alkalmazás szabályozza bizonyos szabályzatok, például a szelektív törlési szabályzat működését, amikor a rendszergazda alkalmazza őket. Amikor a rendszergazda alkalmaz egy ilyen szabályzatot, az Intune szolgáltatás értesítést küld az SDK-nak.

Ehhez regisztrálnia kell az SDK által küldött értesítésekre: hozzon létre egy `MAMNotificationReceiver` osztályt, és regisztrálja a következővel: `MAMNotificationReceiverRegistry`. Ez a fogadó és az `App.onCreate` metódusban fogadni kívánt értesítés típusának megadásával történik, az itt látható példában bemutatott módon:

```
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

A `MAMNotificationReceiver` egyszerűen fogadja az értesítéseket az Intune szolgáltatástól. Az SDK bizonyos értesítéseket a többitől eltérő módon kezel. Más értesítések az alkalmazás részvételét is igénylik.

Az alkalmazásnak igaz vagy hamis értéket *kell visszaadnia* egy értesítésből. Hacsak nem volt sikertelen egy, az alkalmazás által az értesítés eredményének következtében megkísérelt művelet, mindig igaz értéket kell visszaadnia. Ez a hiba megjelenhet az Intune szolgáltatásnak küldött jelentésben. Jelentendő helyzet lehet például az az eset, amikor az alkalmazás nem törli a felhasználói adatokat, pedig a rendszergazda kezdeményezte a törlést.

A `MAMNotificationReceiver.onReceive` metódusban biztonságosan blokkolható, mivel a visszahívása nem a felhasználói felület szálán fut.

Az SDK a következő `MAMNotificationReceiver` felületet definiálja:

```
/**
 * The SDK is signaling that a WG event has occurred.
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

###<a name="types-of-notifications"></a>Az értesítések típusai

Ezeket az értesítéseket a rendszer az alkalmazásba küldi. Egyes értesítésekhez az alkalmazás részvételére is szükség van.

* **`WIPE_USER_DATA`**: Ezt az értesítést a rendszer egy `MAMUserNotification` osztályban küldi el. Az értesítés beérkezésekor az alkalmazásnak a `MAMUserNotification` osztály által átadott „vállalati” identitáshoz társított minden adatot törölnie kell. Az értesítést jelenleg az Intune szolgáltatás regisztrációjának törlésekor küldi a program. A regisztrációs folyamat során általában sor kerül a felhasználó elsődleges nevének megadására. Ha regisztrál erre az értesítésre, az alkalmazásnak kell gondoskodnia az összes felhasználói adat törléséről. Ha nem regisztrál, az alkalmazás az alapértelmezett szelektív törlési műveletet fogja elvégezni.

* **`WIPE_USER_AUXILIARY_DATA`**: Az alkalmazások akkor regisztrálhatnak erre az értesítésre, ha az a cél, hogy az Intune App SDK végrehajtsa az alapértelmezett szelektív törlést, de bizonyos kiegészítő adatokat is törölni kell.  

* **`REFRESH_POLICY`**: Ezt az értesítést a rendszer egy `MAMUserNotification` osztályban küldi el. Az értesítés fogadásakor a gyorsítótárban található összes Intune-szabályzatot érvényteleníteni és frissíteni kell. Általában az SDK kezeli ezt a feladatot. Ha azonban a szabályzatot perzisztens módon alkalmazzák, az alkalmazásnak kell kezelnie a feladatot.



### <a name="protection-of-backup-data"></a>A biztonsági mentési adatok védelme

Az Android Marshmallow (API 23) esetében az Android két módszert kínál az alkalmazásoknak az adataik biztonsági mentéséhez. Mindegyik lehetőség elérhető az alkalmazás számára, de különböző lépések végrehajtását igényli az Intune-adatvédelem megfelelő megvalósításához. A biztonsági mentési módszerek részletes ismertetését az [Android API útmutatójában](http://developer.android.com/guide/topics/data/backup.html) olvashatja el.

#### <a name="automatic-backup-for-apps"></a>Alkalmazások automatikus biztonsági mentése

Az Android az Android Marshmallow rendszerű eszközökön kezdte el kínálni az [automatikus teljes biztonsági mentést](https://developer.android.com/guide/topics/data/autobackup.html) az alkalmazásokhoz, függetlenül az alkalmazások cél API-jától. Ha az AndroidManifest.xml fájlban explicit módon false értékre állítja az `android:allowBackup` attribútumot, akkor az alkalmazás soha nem kerül fel az Android által végrehajtott biztonsági mentések várólistájára, és a „vállalati” adatok az alkalmazásban fognak maradni. Ebben az esetben nincs további teendő.

Alapértelmezés szerint az `android:allowBackup` attribútum még akkor is true értéket kap, ha az `android:allowBackup` nincs megadva a jegyzékfájlban. Ez azt jelenti, hogy az alkalmazások összes adatáról automatikus biztonsági másolat készül a felhasználó Google Drive-fiókjába, és ez olyan alapértelmezett működés, amely *adatszivárgási kockázatot* vet fel. Ezért az SDK az alább leírt módosításokat követeli meg az adatvédelem alkalmazásának garantálásához. Ha az alkalmazást Android Marshmallow rendszerű eszközökön szeretné futtatni, az ügyféladatok megfelelő védelme érdekében mindenképp kövesse ezeket az irányelveket.  

Ha nem hozott létre biztonsági mentési ügynököt, amely a `MAMBackupAgent` vagy a `MAMBackupAgentHelper` segítségével biztonsági másolatot készít az alkalmazásról, tervezze meg és állítsa be, hogy hogyan fogja az Automatikus biztonsági mentés feltölteni az alkalmazás adatait. Az Intune az Androidban elérhető [Automatikus biztonsági mentés](https://developer.android.com/guide/topics/data/autobackup.html) összes funkciójának használatát lehetővé teszi, ideértve azt is, hogy a felhasználó egyedi szabályokat határozhat meg egy XML-fájlban. Az adatok biztonságba helyezéséhez azonban el kell végeznie az alábbi lépéseket:

1. Az alapértelmezett `MAMBackupAgent` használatával az Intune szabályzatainak megfelelő, automatikus és teljes biztonsági másolatokat engedélyezhet. Vegye fel az `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` bejegyzést alkalmazásjegyzékbe.

2. Amikor eldönti, hogy az alkalmazásról milyen típusú teljes biztonsági másolat készüljön (szűretlen, szűrt, semmilyen), állítsa true vagy false értékre az `android:fullBackupContent` attribútumot, vagy állítson be egy XML-erőforrást az alkalmazásban. Az `android:fullBackupContent` attribútumban elhelyezett adatokat másolja egy `com.microsoft.intune.mam.FullBackupContent` nevű metaadatcímkébe.

    Ha például azt szeretné, hogy az alkalmazásról teljes biztonsági másolatok készüljenek az XML-fájlban található egyéni szabályoknak megfelelően, akkor adja meg a megfelelő erőforrást a jegyzékfájl `com.microsoft.intune.mam.FullBackupContent` metaadatcímkéjében a következők szerint:
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Kulcs/érték biztonsági mentése

A kulcs/érték biztonsági mentésének lehetősége minden API esetében elérhető, és a következőket használja: `BackupAgentHelper` és `BackupAgent`.

##### <a name="backupagenthelper"></a>BackupAgentHelper

A `BackupAgentHelper` megvalósítása jóval egyszerűbb, mint a `BackupAgent` osztályé, mind a natív androidos funkciókat, mind a MAM-integrációt tekintve. A `BackupAgentHelper` használatával a `FileBackupHelper` esetében teljes fájlokat, a `SharedPreferencesBackupHelper` esetében pedig megosztott preferenciákat regisztrálhat. Ha létrehozta a fájlokat vagy a preferenciákat, hozzá kell adni őket a `BackupAgentHelper` osztályhoz.

##### <a name="backupagent"></a>BackupAgent

A `BackupAgent` segítségével sokkal egyértelműbben adható meg, hogy mely adatokról készüljön biztonsági másolat. Ha azonban ezt a lehetőséget választja, nem fogja tudni élvezni az Android biztonsági mentési keretrendszerének előnyeit. Mivel a megvalósítás a fejlesztő felelőssége, további lépéseket kell tennie, hogy garantálja a megfelelő adatvédelmet a MAM-nál. Azáltal, hogy a munka nagyobb része a fejlesztőre hárul, itt a MAM-integrációnak nagyobb a jelentősége.

###### <a name="app-does-not-have-a-backup-agent"></a>Az alkalmazás nem rendelkezik biztonságimásolat-készítő ügynökkel

Ezek a fejlesztő lehetőségei, ha `android:allowBackup =true`.

####### <a name="full-backup-according-to-a-configuration-file"></a>Teljes biztonsági mentés konfigurációs fájl alapján

Adjon meg egy erőforrást a `com.microsoft.intune.mam.FullBackupContent` metaadat-kódcímke alatt a jegyzékfájlban. Például így:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Adja hozzá a következő attribútumot az `<application>` címkében: `android:fullBackupContent="@xml/my_scheme"`, ahol a `my_scheme` az alkalmazásbeli XML-erőforrás.

####### <a name="full-backup-without-exclusions"></a>Teljes biztonsági mentés kizárások nélkül

Adjon meg egy címkét a jegyzékfájlban, például: `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`.

Adja hozzá a következő attribútumot az `<application>` címkében: `android:fullBackupContent="true"`.

###### <a name="app-has-a-backup-agent"></a>Az alkalmazás rendelkezik biztonságimásolat-készítő ügynökkel

A `BackupAgent` és a `BackupAgentHelper` esetében kövesse az útmutató korábbi pontjaiban olvasható javaslatokat.

Fontolja meg az áttérést a `MAMDefaultFullBackupAgent` használatára, amely az Android Marshmallow esetében egyszerű biztonsági mentést tesz lehetővé.

##### <a name="before-your-backup"></a>A biztonsági mentés előtti teendők

Mielőtt megkezdené a biztonsági mentést, ellenőrizze, hogy van-e engedélye biztonsági másolatot készíteni a menteni tervezett fájlokról vagy adatpufferekről. A `MAMFileProtectionManager` és a `MAMDataProtectionManager` ehhez egy `isBackupAllowed` függvényt biztosít. Ha a fájlok vagy az adatpuffer biztonsági mentése nem engedélyezett, javasoljuk, hogy vonja ki őket a biztonsági mentésből.

Ha a biztonsági mentés egy pontján biztonsági másolatot szeretne készíteni az 1. lépésben ellenőrzött fájlokhoz tartozó identitásokról, a `backupMAMFileIdentity(BackupDataOutput data, File … files)` függvényt azokkal a fájlokkal kell meghívnia, amelyekből adatokat szeretne kinyerni. Ez a művelet automatikusan új biztonsági mentési entitásokat hoz létre, és a `BackupDataOutput` kimenetre írja őket. Ezeket az entitásokat automatikusan felhasználja a program a visszaállítás során.

#### <a name="azure-directory-authentication-library-setup"></a>Az Azure Directory Authentication Library (ADAL) beállítása  

Az SDK az ADAL-t hitelesítésre, illetve a feltételes indítási forgatókönyvek készítésére használja. Ezekhez a forgatókönyvekhez a fejlesztőnek meg kell adnia bizonyos beállításokat az Azure Active Directory (Azure AD) címtárban. A konfigurációs értékeket az SDK az `AndroidManifest` metaadatain keresztül közli.

Az alkalmazás konfigurálásához és a megfelelő hitelesítés engedélyezéséhez adja hozzá a következőket az `AndroidManifest` alkalmazás-csomópontjához. A konfigurációk némelyikére csak akkor van szükség, ha az alkalmazás általánosságban az ADAL-t használja a hitelesítésre. Ebben az esetben szükség lesz azokra a konkrét értékekre, amelyeket az alkalmazás az Azure AD-beli regisztrációhoz használt. Így a rendszer nem fogja kétszer felszólítani a felhasználókat a hitelesítésre, mivel az Azure AD két különálló regisztrációs értéket észlel: egyet az alkalmazásból, egyet pedig az SDK-ból.

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

A GUID-azonosítóknak nem kell kezdő vagy záró kapcsos zárójelet tartalmazniuk.

##### <a name="common-adal-configurations"></a>Általános ADAL-konfigurációk

Az alábbiak a fenti értékek általános beállításai.

###### <a name="app-does-not-integrate-adal"></a>Az alkalmazás nem integrálja az ADAL-t

* A szolgáltatót arra a kívánt környezetre kell beállítani, ahol az Azure AD-fiókokat konfigurálták.

* A SkipBroker igaz értékű kell, hogy legyen.

###### <a name="app-integrates-adal"></a>Az alkalmazás integrálja az ADAL-t

* A szolgáltatót arra a kívánt környezetre kell beállítani, ahol az Azure AD-fiókokat konfigurálták.

* Ügyfél-azonosítóként az alkalmazás ügyfél-azonosítóját kell beállítani.

* `NonBrokerRedirectURI` értékeként az alkalmazáshoz tartozó érvényes átirányítási URI-t kell beállítani, Vagy állítsa be a következőt érvényes Azure AD átirányítási URI-ként: `urn:ietf:wg:oauth:2.0:oob`.

* A SkipBroker attribútumot false értékre kell állítani (vagy ki kell hagyni).

* Be kell állítani, hogy az Azure AD elfogadja a közvetítő átirányítási URI-ját.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>Az alkalmazás integrálja az ADAL-t, de nem támogatja az Azure AD-hitelesítő alkalmazást

* A szolgáltatót arra a kívánt környezetre kell beállítani, ahol az Azure AD-fiókokat konfigurálták.

* Ügyfél-azonosítóként az alkalmazás ügyfél-azonosítóját kell beállítani.

* `NonBrokerRedirectURI` értékeként az alkalmazáshoz tartozó érvényes átirányítási URI-t kell beállítani, Vagy állítsa be a következőt érvényes Azure AD átirányítási URI-ként: `urn:ietf:wg:oauth:2.0:oob`.

#### <a name="logging-in-the-sdk"></a>Bejelentkezés az SDK-ba

A naplózás a `java.util.logging` keretrendszeren keresztül zajlik. A naplók fogadásához állítsa be a globális naplózást a [Java technikai útmutató](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Az alkalmazástól függően általában az `App.onCreate` a legjobb hely a naplózás indításához. Vegye figyelembe, hogy naplóüzenetek osztálynév szerinti kulccsal vannak ellátva, amely bizonyos esetekben el van rejtve.

###<a name="multi-identity"></a>Többszörös identitás

Az Intune SDK alapértelmezés szerint az alkalmazás egészére alkalmazza a szabályzatot. A MAM többszörös identitás szolgáltatásával engedélyezhető a szabályzatok identitásszintű alkalmazása. Ebből az alkalmazásnak jóval nagyobb részt kell vállalnia, mint a MAM többi funkciójából. Az alkalmazásnak tájékoztatnia kell az alkalmazás SDK-t, ha módosítani szándékozik az aktív identitást. Az SDK ezenfelül értesíti az alkalmazást, ha identitásváltás szükséges.

Jelenleg csak egy felügyelt identitás támogatott. Ha a felhasználó már regisztrálta az eszközt vagy az alkalmazást, az SDK ezt az identitást használja, és ezt tekinti az elsődleges felügyelt identitásnak. Az SDK az alkalmazás többi felhasználójával nem felügyeltként bánik, és nem korlátozza ezek szabályzatbeállításait.

Felhívjuk, hogy az identitás egyszerűen egy karakterláncként van definiálva. Az identitás karakterláncában a kis- és nagybetűk nincsenek megkülönböztetve. Az SDK nem feltétlenül olyan kis- és nagybetűkkel adja vissza a tőle kért identitásokat, mint ahogyan az az identitás beállításakor eredetileg meg volt adva.

####<a name="enabling-multi-identity"></a>Több identitás engedélyezése

Alapértelmezés szerint az összes alkalmazás egyszeres identitással rendelkező alkalmazásnak minősül. Az alkalmazások a következő, az Android-jegyzékfájlban elhelyezett metaadatokkal közölhetik, hogy képesek több identitás kezelésére.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>Az identitás beállítása

Az alkalmazás identitását a következő szinteken lehet beállítani:

1. Folyamat szintje

2. Context (általában `Activity`) szint

3. Szál szintje

A szál szintjén beállított identitás felülírja a Context szintjén beállított identitást, és a `Context` szinten beállított identitás felülírja a folyamat szintjén beállított identitást. A `Context` szinten beállított identitásokat a rendszer csak akkor használja, ha megfelelőek. A fájlok I/O-műveleteihez például nem tartozik `Context` szint. A `MAMPolicyManager` következő metódusai használhatók az identitás beállításához, illetve a korábban beállított identitásértékek beolvasásához.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
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
Az alkalmazás identitását úgy is törölheti, hogy null értékűre állítja. Az üres karakterlánc használható olyan identitásként, amelyre biztosan nem vonatkoznak korlátozások. Az identitást beállító összes metódus a ``` MAMIdentitySwitchResult``` használatával adja vissza az eredményértékeket. Négy értéket kaphat vissza:

* **SUCCEEDED**: Az identitásváltás sikeres volt.

* **NOT_ALLOWED**: Az identitásváltás nem engedélyezett. Ez akkor fordul elő, ha a felhasználó megpróbál egy olyan másik vállalati felhasználóra váltani, aki ugyanahhoz a vállalathoz tartozik, mint a beléptetett felhasználó. Ezenkívül akkor is előfordul, ha a felhasználó megpróbálja beállítani a felhasználói felület (`Context`) identitást, de az aktuális szálhoz egy másik identitás van beállítva.

* **CANCELLED**: A felhasználó megszakította az identitásváltást. Ez általában úgy történik, hogy megnyomja a Vissza gombot a PIN-kódot kérő, illetve hitelesítési üzenetnél.

* **FAILED**: Az identitásváltás ismeretlen okból nem sikerült.

A `Context` identitás beállítása esetén az eredmény aszinkron módon jelenik meg. Ha a `Context` az `Activity` osztálya, csak a feltételes indítást követően fogja megtudni, hogy az identitásváltás sikeres volt-e. A feltételes indítás során esetleg szükség lehet rá, hogy a felhasználó megadja PIN-kódját vagy teljes vállalati hitelesítő adatait. Az alkalmazásnak egy ```MAMSetUIIdentityCallback``` metódust kell alkalmaznia, hogy megkapja ezt az eredményt, de a null érték átadása is megengedett ennél a paraméternél.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

A tevékenységek identitását közvetlenül a `MAMActivity` metódusának segítségével, a ```MAMPolicyManager.setUIPolicyIdentity``` meghívása nélkül is beállíthatja. Ezt a következő metódussal hajthatja végre:

 ```public final void switchMAMIdentity(final String newIdentity);```

Az alkalmazások felül is írhatják a `MAMActivity` osztályra vonatkozó metódust, hogy értesítést kapjanak a tevékenység identitásának módosítására tett kísérletek eredményéről.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Előfordulhat, hogy az identitás módosítása után újból létre kell hozni a tevékenységet. Ebben az esetben a ```onSwitchMAMIdentityComplete``` visszahívása lesz elküldve a tevékenység új példányának.


####<a name="implicit-identity-changes"></a>Az identitás implicit megváltoztatása

Az alkalmazás identitásbeállítási képessége mellett a szálak vagy a környezetek identitása a MAM használatát támogató más alkalmazásból beérkező adatok alapján is módosítható. Ha például egy tevékenység elindítása egy másik MAM-alkalmazás által küldött `Intent` osztály alapján történik, akkor a rendszer a másik alkalmazásban, az `Intent` osztály beállításának pontján érvényes identitást fogja beállítani.

A szolgáltatások esetében a szál identitásának beállítása hasonlóan történik az `onStart` vagy az `onBind` hívás időtartamára. Átmenetileg a `Binder` hívásba érkező, az `onBind` hívásból visszaadott hívások is beállítják a szál identitását. A beérkező hívások a ```ContentProvider``` esetében is hasonlóképpen beállítják a szál identitását az időtartamukra vonatkozóan.

Ezenkívül a tevékenységekkel kapcsolatos felhasználói beavatkozások is előidézhetnek implicit identitásváltást. Ha a például egy felhasználó megszakítja az engedélyezési kérést a ```Resume``` művelet alatt, akkor az egy üres identitásra való implicit váltást eredményez.
Lehetőség van arra, hogy az alkalmazás értesüljön ezekről a változásokról, és bizonyos esetekben megtiltsa őket, ha szükséges. A ```MAMService``` és a ```MAMContentProvider``` a következő metódust teszi közzé, amelyet az alosztályok felülírhatnak:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
A ```MAMActivity``` esetében egy további paraméter is szerepel a metódusban:
```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
Az ```AppIdentitySwitchReason``` rész rögzíti az implicit váltás forrását. Ez a következő értékeket képes befogadni: ```CREATE```, ```RESUME_CANCELLED``` és ```NEW_INTENT```.  A ```RESUME_CANCELLED``` ok akkor használható, ha a tevékenység folytatása PIN-kódot kérő, hitelesítési vagy egyéb megfelelőségi felhasználói felület megjelenítését idézi elő, és a felhasználó megpróbál kilépni erről a felhasználói felületről, általában a Vissza gomb használatával.
Az ```AppIdentitySwitchResultCallback``` a következőképpen történik:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
Az ```AppIdentitySwitchResult``` lehet ```SUCCESS``` vagy ```FAILURE```.

Az összes implicit identitásváltás esetében az ```onMAMIdentitySwitchRequired``` metódust kell meghívni, kivéve azokat, amelyek a ```MAMService.onMAMBind``` által visszaadott `Binder` osztályon keresztül történtek. Ha az ok ```RESUME_CANCELLED```, az ```onMAMIdentitySwitchRequired``` alapértelmezett megvalósítása azonnal meghívja a következőt: ```reportIdentitySwitchResult(FAILURE)```, minden más esetben pedig a következőt: ```reportIdentitySwitchResult(SUCCESS)```.

A legtöbb alkalmazás esetében valószínűleg nem lesz szükség az identitásváltás más módon történő megakadályozására vagy késleltetésére. Ha azonban mégis erre van szükség, fontolja meg a következőket:

* Ha a rendszer meggátolja az identitásváltást, annak ugyanaz az eredménye, mintha a ```Receive``` megosztási beállításai megtiltották volna az adatok belépését.

* Ha egy szolgáltatás a főszálban fut, a ```reportIdentitySwitchResult``` hívását *kötelező* szinkron módon végrehajtani, ellenkező esetben leáll a felhasználói felület szála.

* Az ```Activity``` létrehozása esetében az ```onMAMIdentitySwitchRequired``` hívása megelőzi az ```onMAMCreate``` hívását. Ha az alkalmazásnak meg kell jelenítenie a felhasználói felületet annak megállapításához, hogy engedélyezhető-e az identitásváltás, akkor az adott felhasználói felületet egy másik tevékenység használatával kell megjeleníteni.

* Amikor egy ```Activity``` tevékenység az üres identitásra való váltást kéri (a következővel egyenértékű okkal: ```RESUME_CANCELLED```), akkor az alkalmazásnak módosítania kell a folytatott tevékenységet, hogy az adatok megjelenítése az adott identitásváltásnak megfelelően történjen. Ha ez nem lehetséges, az alkalmazásnak el kell utasítania a váltást, és újból fel kell szólítania a felhasználót a folytatáshoz használt identitásra vonatkozó szabályzatnak való megfelelésre (például meg kell jelenítenie a PIN-kód megadását kérő képernyőt).

> [!NOTE]
> A többszörös identitást támogató alkalmazások mindig fogadják a felügyelt és a nem felügyelt alkalmazásoktól érkező adatokat. Az alkalmazás feladata, hogy felügyelt módon kezelje a felügyelt identitásokból érkező adatokat. Ha a kért identitás felügyelt ```(MAMPolicyManager.getIsIdentityManaged)```, de az alkalmazás nem tudja használni ezt a fiókot (például azért, mert a fiókokat, például az e-mail-fiókokat először magában az alkalmazásban kell beállítani), akkor el kell utasítania az identitásváltást.

###<a name="file-protection"></a>Fájlvédelem

Amikor létrehozza a fájlokat, a rendszer identitást társít hozzájuk a szál és a folyamat identitása alapján. A rendszer ezt az identitást fogja használni a fájltitkosításhoz és a szelektív törléshez. A rendszer csak azokat a fájlokat titkosítja, amelyeknél az identitás szabályzata előírja a titkosítást. Az SDK alapértelmezett szelektív törlése csak azokat az identitáshoz tartozó fájlokat fogja törölni, amelyeknél törlést kértek. Az alkalmazás a ```MAMFileProtectionManager``` használatával kérdezheti le vagy módosíthatja a fájlok identitását.
```
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
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> A fájl identitásának címkézésénél az offline mód különbségnek számít. Vegye figyelembe a következőket:
> * Ha a Munkahelyi portál alkalmazás nincs telepítve, akkor a fájlok nem láthatók el identitáscímkével.
>
> * Ha telepítve van a Munkahelyi portál alkalmazás, de ha az alkalmazásra nem vonatkozik szabályzat, akkor a fájlok nem láthatók el identitáscímkével.
>
> * Amikor elérhetővé válik a fájlok identitáscímkézése, akkor a rendszer az összes korábban létrehozott fájlt személyesként (üres karakterláncú identitáshoz tartozó fájlként) fogja kezelni, kivéve, ha az alkalmazást korábban egyszeres identitást támogató alkalmazásként telepítették. Ebben az esetben a rendszer úgy kezeli a fájlokat, mintha a regisztrált felhasználóhoz tartoznának.

####<a name="data-protection"></a>Adatvédelem

A fájlok nem címkézhetők meg több identitáshoz tartozó fájlként. Azok az alkalmazások, amelyeknek ugyanabban a fájlban kell tárolniuk a különböző felhasználókhoz tartozó adatokat, manuálisan tehetik meg ezt a ```MAMDataProtectionManager``` által biztosított funkciókkal. Ez lehetővé teszi az alkalmazás számára az adatok titkosítását, illetve egy adott felhasználóhoz rendelését. A titkosított adatok lemezen, fájlban tárolhatók. Az identitáshoz tartozó adatokat lekérdezheti, és az adatokat visszafejtheti.

```
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
###<a name="content-providers"></a>Tartalomszolgáltatók

Ha az alkalmazás a ```ParcelFileDescriptor``` fájlleírótól különböző potenciális vállalati adatokat szolgáltat egy ```ContentProvider``` használatával, akkor az alkalmazásnak a ```MAMContentProvider``` ```isProvideContentAllowed(String)``` metódusát kell meghívnia a tartalom tulajdonosához tartozó ```UPN``` átadásával. Ha ez a függvény a false értéket adja vissza, akkor a tartalom nem adható vissza a hívónak. A tartalomszolgáltatón keresztül visszaadott fájlleírók kezelése automatikusan a fájl identitása alapján történik.

###<a name="selective-wipe"></a>Szelektív törlés

Ha egy alkalmazás regisztrál a ```WIPE_USER_DATA``` értesítésre, akkor nem veheti igénybe az SDK alapértelmezett szelektív törlési működését. A többszörös identitást támogató alkalmazások esetében ez nagyobb jelentőségű tényező lehet, mivel a MAM alapértelmezett szelektív törlése csak a törlendő identitásnak megfelelő fájlokat törli.

Ha többszörös identitást támogató alkalmazást fejleszt, regisztráljon a következőre: ```WIPE_USER_AUXILIARY_DATA```. Ez az értesítés lehetőséget kínál arra, hogy felhasználja az SDK alapértelmezett törlési funkcióját. Ez az értesítés közvetlenül az SDK alapértelmezett szelektív törlésének végrehajtása előtt jelenik meg. Vegye figyelembe, hogy az alkalmazások nem regisztrálhatnak egyszerre a ```WIPE_USER_DATA``` és a ```WIPE_USER_AUXILIARY_DATA``` értesítésre.

### <a name="known-platform-limitations"></a>Ismert platformkorlátozások

#### <a name="file-size-limitations"></a>Fájlméretre vonatkozó korlátozások

Az Android rendszerben a Dalvik végrehajtható fájlformátumra vonatkozó korlátozások problémává válhatnak ProGuard nélkül futó nagy méretű kódbázis esetében. Konkrétan a következő korlátozások léphetnek érvénybe:

* A mezőkre vonatkozó 65 ezer darabos korlát

* A metódusokra vonatkozó 65 ezer darabos korlát

Ha sok projektet von be, minden `android:package` megkapja az R egy példányát, ez pedig jelentősen növeli a mezők számát a kódtárak hozzáadása során. A következő javaslatok segíthetnek a korlátozás hatásának mérséklésében:

* Lehetőség szerint minden kódtárprojektnek azonos `android:package` csomagot kell használnia. Ez a működés során nem fog szórványos hibákat okozni, ez a probléma kizárólag a build elkészítése során jelentkezik. Emellett az Android SDK újabb verziói előre feldolgozzák a DEX-fájlokat a redundancia csökkentése érdekében. Ez még tovább csökkenti a mezőktől való távolságot.

* Használja az elérhető legújabb Android SDK buildet.

* Távolítsa el a felesleges és használaton kívüli kódtárakat (például `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>Szabályzatbetartatási korlátozások

**Képernyőfelvétel**: Az SDK nem tud új képernyőfelvétel-beállítási értéket kikényszeríteni azoknál az `Activity` osztályoknál, amelyeknél már lefutott az `Activity.onCreate`. Ez azt okozhatja, hogy lesz egy időszak, amikor az alkalmazásban már beállították a képernyőképek letiltását, de a felhasználó továbbra is készíthet képernyőképeket.

**Tartalomfeloldók**: Az átviteli vagy a fogadási szabályzat részben vagy teljesen blokkolhatja a tartalomfeloldóknak a más alkalmazások tartalomszolgáltatójának elérésére való használatát. Ennek következtében a `ContentResolver` metódusok null értéket fognak visszaadni, vagy hibára utaló értéket jelenítenek meg. (Az `openOutputStream` például a `FileNotFoundException` értéket váltja ki, ha blokkolva van.) Az alkalmazás a következő hívás segítségével képes ellenőrizni, hogy a szabályzat hibát okozott-e (vagy hibát fog-e okozni), amikor tartalomfeloldón keresztül próbál adatokat írni:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exportált szolgáltatások**: Az Intune App SDK részét képező `AndroidManifest.xml` fájl tartalmazza a következőt: `MAMNotificationReceiverService`. Ennek exportált szolgáltatásnak kell lennie, amely lehetővé teszi, hogy a Munkahelyi portál alkalmazás értesítéseket küldjön a kompatibilis alkalmazásoknak. A szolgáltatás megvizsgálja a hívót annak ellenőrzéséhez, hogy csak a Munkahelyi portál alkalmazás számára engedélyezett-e az értesítések küldése.

### <a name="android-best-practices"></a>Gyakorlati tanácsok az Android rendszerhez

Az Intune SDK fenntartja az Android API által biztosított szerződést, bár a szabályzatbeállítások következtében gyakrabban léphetnek fel hibaállapotok. Az alábbi androidos gyakorlati tanácsok csökkentik a hibák valószínűségét:

* Azok az androidos SDK-függvények, amelyek null értékkel térhetnek vissza, nagyobb valószínűséggel lesznek null értékűek. Hogy minél ritkábban forduljanak elő problémák, állítson be nullellenőrzéseket a megfelelő helyeken.

* Azoknál a problémáknál, amelyeknél lehetséges ellenőrzést végezni, használja az SDK API-kat az ellenőrzésre.

* Minden származtatott függvénynek meg kell hívnia a szülőosztálybeli verzióját.

* Kerülje az API-k nem egyértelmű módon való használatát. Az `Activity.startActivityForResult/onActivityResult` `requestCode` ellenőrzése nélküli használata például szokatlan működést eredményezhet.

