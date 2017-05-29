mdm-authority-set---
# <a name="required-metadata"></a>required metadata

title: Android-eszközök regisztrálása az Intune-ban titleSuffix: "Intune az Azure-on – előzetes" description: "Intune az Azure-on – előzetes: A cikk bemutatja, hogyan lehet regisztrálni az androidos eszközöket az Azure-os Intune előzetes verziójában."
keywords: author: nathbarn ms.author: nathbarn manager: angrobe ms.date: 04/12/2017 ms.topic: article ms.prod: ms.service: microsoft-intune ms.technology: ms.assetid: f276d98c-b077-452a-8835-41919d674db5

# <a name="optional-metadata"></a>optional metadata

#<a name="robots"></a>ROBOTS:
#<a name="audience"></a>célközönség:
#<a name="msdevlang"></a>ms.devlang:
ms.reviewer: chrisbal ms.suite: ems
#<a name="mstgtpltfrm"></a>ms.tgt_pltfrm:
ms.custom: intune-azure

---

# <a name="enroll-android-devices"></a>Androidos eszközök regisztrálása

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Az Intune rendszergazdájaként az Intune-nal felügyelhet androidos eszközöket, beleértve a Samsung Knox Standard rendszerűeket is. Ezen túlmenően felügyelheti az [Android for Work-eszközök](#enable-enrollment-of-android-for-work-devices) munkahelyi profiljait is.

A Samsung KNOX Standard rendszerű eszközökön használható az Intune többfelhasználós felügyelete. Ilyenkor a felhasználók Azure AD-beli hitelesítő adataikkal jelentkezhetnek be és ki az eszközön, de az központi felügyelet alatt marad, akár használatban van, akár nem. A bejelentkezett végfelhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.

## <a name="prerequisite"></a>Előfeltétel

A mobileszközök kezelésének előkészítéseként a **Microsoft Intune**-t kell beállítani MDM-szolgáltatóként. Erről [Az MDM-szolgáltató beállítása](mdm-authority-set.md) című cikk nyújt útmutatást. Ezt a beállítást csak egyszer, az Intune-nak a mobileszközök kezelésére való kezdeti beállítása során kell megadni; előfordulhat tehát, hogy már megadta.

## <a name="set-up-android-enrollment"></a>Az androidos eszközök regisztrálásának beállítása

Alapértelmezés szerint az Intune engedélyezi az Android és a Samsung Knox Standard rendszerű eszközök regisztrálását.

Az androidos eszközök (vagy csak a személyes tulajdonban levők) regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md#set-device-type-restrictions) című témakörben olvashat.

Az egy felhasználó által regisztrálható eszközök számának korlátozásáról a [Regisztrált eszközök maximális számának beállítása](enrollment-restrictions-set.md#set-device-limit-restrictions) című témakörben olvashat.

Az eszközfelügyelethez a felhasználóknak le kell tölteniük a Google Play-ből az Intune Céges portál alkalmazást, majd azt megnyitva az útmutatás alapján regisztrálniuk kell az eszközt. Miután az androidos eszközök felügyelet alá kerülnek, számos más művelet mellett [megfelelőségi szabályzatokat rendelhet hozzájuk](compliance-policy-create-android.md), vagy [alkalmazásokat felügyelhet](app-management.md).

## <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work-eszközök regisztrálásának engedélyezése

Ha engedélyezni szeretné az [Android for Work támogatású](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) eszközök munkahelyi profiljának felügyeletét, létre kell hoznia egy Android for Work-kötést az Intune-hoz. Az Android for Worköt támogató, de korábban normál Android-eszközként regisztrált eszközök regisztrációját törölni kell, majd újra kell regisztrálni őket.

## <a name="add-android-for-work-binding-for-intune"></a>Android for Work-kötés létrehozása az Intune-ban

1. **Az Intune MDM beállítása**<br>
Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** állítja be [mobileszköz-kezelői szolgáltatóként](mdm-authority-set.md).

2. **Android for Work-kötés konfigurálása**<br>
   Az Intune rendszergazdájaként az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** elemet.

    1. Az **Intune** panelen válassza az **Eszközök beléptetése** > **Android for Work-regisztráció** elemet, majd kattintson a **Konfigurálás** elemre a Google Play Android for Work webhelyének megnyitásához. Ez egy új lapon nyílik meg a böngészőben.
  ![Képernyőkép az Android for Work-kötés konfigurálására mutató hivatkozásról](./media/android-work-bind.png)

    2. **Bejelentkezés a Google-fiókba**<br>
   A Google bejelentkezési oldalán lépjen be az adott bérlő összes Android for Work-alapú felügyeleti feladatához társítandó Google-fiókkal. Ezt a Google-fiókot használja a szervezet összes rendszergazdája az alkalmazások felügyeletére és közzétételére a Play for Work konzolon.

    3. **A szervezet adatainak megadása**<br>
   Az **Organization name** (Szervezet neve) mezőben adja meg a vállalat nevét. Az **Enterprise mobility management (EMM) provider** (Nagyvállalati mobileszköz-felügyeleti (EMM-) szolgáltató) mezőben a *Microsoft Intune* értéknek kell megjelennie. Fogadja el azAndroid for Work-szerződést, majd kattintson a **Confirm** (Jóváhagyás) gombra. Megtörténik a kérelem feldolgozása.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work-regisztrációs beállítások megadása
   Az Android for Work csak bizonyos Android-eszközökön támogatott. Az [Android for Workre vonatkozó követelményeket](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") megtalálja a Google webhelyén. Az Android for Worköt támogató eszközök mindegyike támogatja a hagyományos Android-alapú felügyeletet is.  Az Intune-ban megadhatja, hogyan történjen az Android for Worköt támogató eszközök felügyelete:

   - **Minden eszköz felügyelete Android-eszközként** – Minden Android-eszköz, az Android for Worköt támogatókat is beleértve, hagyományos Android-eszközként lesz regisztrálva.
   - **Minden támogatott eszköz felügyelete Android for Work-eszközként** – Az Android for Worköt támogató eszközök mindegyike Android for Work-eszközként lesz regisztrálva. Az Android for Worköt nem támogató eszközök hagyományos Android-eszközként lesznek regisztrálva.
   - **Csak a megadott csoportokban szereplő felhasználók támogatott eszközeinek felügyelete Android for Work-eszközként** – Az Android for Work-alapú felügyeletet beállíthatja a felhasználók egy korlátozott halmaza számára. Csak a kijelölt csoportok tagjai által regisztrált, Android for Worköt támogató eszközök lesznek Android for Work-eszközként lesz regisztrálva. Minden más eszköz Android-eszközként lesz regisztrálva. Ez főleg Android for Workös próbák során hasznos.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

A felhasználókat meg kell kérnie, hogy a Google Play-ből töltsék le az Intune Céges portál alkalmazást, és annak útmutatása alapján regisztrálják eszközeiket. Az alkalmazás végigvezeti a felhasználókat a beléptetési folyamaton, tájékoztatja őket arról, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

Hivatkozást is küldhet nekik az online regisztrációhoz: [Androidos eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)

Más végfelhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Android-eszköz használata az Intune-nal](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Az Android for Work rendszergazdai fiókja kötésének megszüntetése

Az Android for Work-regisztrációt és -felügyeletet ki is kapcsolhatja. Ha az Intune felügyeleti konzolon a **Leválasztás** gombra kattint, azzal megszünteti a regisztrált Android for Work eszközök regisztrációját, és felbontja az Android for Work-fiók és az Intune közötti kapcsolatot.

### <a name="how-to-unbind-an-android-for-work-account"></a>Android for Work fiók leválasztása

1. **Android for Work-kötés feloldása**<br>
   Az Intune rendszergazdájaként az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** elemet.  Az **Intune** panelen válassza az **Eszközök beléptetése** > **Android for Work-regisztráció** elemet, majd kattintson a **Leválasztás** elemre.

2. **Android for Work-kötés törlésének jóváhagyása**<br>
  A kötés törléséhez és az összes Android for Work-eszköz Intune-regisztrációjának megszüntetéséhez kattintson az **Igen** gombra.
