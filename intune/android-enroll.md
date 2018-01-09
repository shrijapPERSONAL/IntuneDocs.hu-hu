---
title: "Android-eszközök regisztrálása az Intune-ban | Microsoft Docs"
titlesuffix: Azure portal
description: "Útmutató az Android-eszközök Intune-ban való regisztrálásához."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 12/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ad018bdfa55b030f5d714017ae09f616ae2bf164
ms.sourcegitcommit: 9fabf1a8db53842f7b00762374de5b137158ee25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/22/2017
---
# <a name="enroll-android-devices"></a>Androidos eszközök regisztrálása

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Az Intune rendszergazdájaként kezelhet Android-eszközöket, beleértve a Samsung Knox Standard rendszerűeket is. Ezen túlmenően felügyelheti az [Android for Work-eszközök](#enable-enrollment-of-android-for-work-devices) munkahelyi profiljait is.

A Samsung KNOX Standard rendszerű eszközökön használható az Intune többfelhasználós felügyelete. Ez azt jelenti, hogy a végfelhasználók Azure AD-beli hitelesítő adataikkal jelentkezhetnek be az eszközökön. Az eszköz központilag felügyelt, függetlenül attól, hogy használatban van-e vagy sem. A bejelentkezett felhasználó hozzáfér az alkalmazásokhoz, és a rá érvényes szabályzatok is működnek. A felhasználói kijelentkezéskor az összes alkalmazásadat törlődik.

## <a name="prerequisite"></a>Előfeltétel

A mobileszközök kezelésének előkészítéseként a **Microsoft Intune**-t kell beállítani mobileszköz-kezelő (MDM) szolgáltatóként. Erről [Az MDM-szolgáltató beállítása](mdm-authority-set.md) című cikk nyújt útmutatást. Ezt a beállítást csak egyszer, az Intune-nak a mobileszközök kezelésére való kezdeti beállítása során kell megadni.

## <a name="set-up-android-enrollment"></a>Az androidos eszközök regisztrálásának beállítása

Alapértelmezés szerint az Intune engedélyezi az Android és a Samsung Knox Standard rendszerű eszközök regisztrálását.

Az androidos eszközök (vagy csak a személyes tulajdonban levők) regisztrálásának letiltásáról a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md) című témakörben olvashat.

Az eszközfelügyelet engedélyezéséhez a felhasználóknak regisztrálniuk kell eszközeiket úgy, hogy letöltik a Google Play Áruházból az Intune Céges portál alkalmazást, majd azt megnyitva követik kell az útmutatást. Miután az Android-eszközök felügyelet alá kerülnek, számos más művelet mellett [megfelelőségi szabályzatokat rendelhet hozzájuk](compliance-policy-create-android.md), vagy [alkalmazásokat felügyelhet](app-management.md).

## <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work-eszközök regisztrálásának engedélyezése

Ha engedélyezni szeretné az [Android for Work támogatású](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) eszközök munkahelyi profiljának felügyeletét, létre kell hoznia egy Android for Work-kötést az Intune-hoz. Az Android for Worköt támogató, de korábban normál Android-eszközként regisztrált eszközök regisztrációját törölni kell, majd újra kell regisztrálni őket.

Ha a [Készülékregisztráció-kezelővel](device-enrollment-manager-enroll.md) regisztrál Android for Work-eszközöket, akkor a fiókonként regisztrálható eszközök számának felső korlátja 10.

## <a name="add-android-for-work-binding-for-intune"></a>Android for Work-kötés létrehozása az Intune-ban

1. **Az Intune MDM beállítása**<br>
Ha még nem tette meg, készítse elő a mobileszköz-kezelést úgy, hogy a **Microsoft Intune-t** állítja be [mobileszköz-kezelői szolgáltatóként](mdm-authority-set.md).
2. **Android for Work-kötés konfigurálása**<br>
    Az Intune rendszergazdájaként az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** elemet.

   a. Az **Intune** panelen válassza az **Eszközök beléptetése** > **Android for Work-regisztráció** elemet, majd válassza a **Konfigurálás** elemet a Google Play Áruház Android for Work-webhelyének megnyitásához. A webhely egy új lapon nyílik meg a böngészőben.
   ![Képernyőkép az Android for Work-kötés konfigurálására mutató hivatkozásról](./media/android-work-bind.png)

   b. **Bejelentkezés a Google-fiókba**<br>
   A Google bejelentkezési oldalán lépjen be az adott bérlő összes Android for Work-alapú felügyeleti feladatához társítandó Google-fiókkal. Ezt a Google-fiókot osztják meg a vállalati rendszergazdák az alkalmazások Play for Work konzolon való felügyeletéhez és közzétételéhez.

   c. **A szervezet adatainak megadása**<br>
   Az **Organization name** (Szervezet neve) mezőben adja meg a vállalat nevét. Az **Enterprise mobility management (EMM) provider** (Nagyvállalati mobileszköz-felügyeleti (EMM-) szolgáltató) mezőben a **Microsoft Intune** értéknek kell megjelennie. Fogadja el az Android for Work-szerződést, majd válassza a **Confirm** (Jóváhagyás) gombot. Megtörténik a kérelem feldolgozása.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work-regisztrációs beállítások megadása
   Az Android for Work használata csak bizonyos Android-eszközökön támogatott. Az [Android for Workre vonatkozó követelményeket](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") megtalálja a Google webhelyén. Az Android for Worköt támogató eszközök mindegyike támogatja a hagyományos Android-alapú felügyeletet is. Az Intune-ban megadhatja, hogyan történjen az Android for Worköt támogató eszközök felügyelete:

   - **Minden eszköz felügyelete Android-eszközként**. Minden Android-eszköz, az Android for Worköt támogatókat is beleértve, hagyományos Android-eszközként lesz regisztrálva.
   - **Minden támogatott eszköz felügyelete Android for Work-eszközként**. Az Android for Worköt támogató eszközök mindegyike Android for Work-eszközként lesz regisztrálva. Az Android for Worköt nem támogató eszközök hagyományos Android-eszközként lesznek regisztrálva.
   - **Csak a megadott felhasználói csoportokban szereplő felhasználók támogatott eszközeinek felügyelete Android for Work-eszközként**. Az Android for Work-alapú felügyelet a megadott felhasználókra korlátozható. Csak a kijelölt csoportok tagjai által regisztrált, Android for Worköt támogató eszközök lesznek Android for Work-eszközként lesz regisztrálva. Minden más eszköz Android-eszközként lesz regisztrálva. Ez főleg Android for Workös próbák során hasznos.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>A Céges portál alkalmazás jóváhagyása a felügyelt Google Play Áruházban
Jóvá kell hagynia az Androidhoz készült Céges portál alkalmazást a felügyelt Google Play Áruházban annak érdekében, hogy az alkalmazás megkapja az automatikus frissítéseket. Ha nem hagyja jóvá a Céges portál alkalmazást, előfordulhat, hogy az nem fogja megkapni a Microsoft által kiadott fontos hibajavításokat és új funkciókat, és így idővel elavulttá válik.

Kövesse az alábbi lépéseket az Intune Céges portál alkalmazás jóváhagyásához:

1.  Töltse le a Céges portál alkalmazást a [felügyelt Google Play Áruházból](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Jelentkezzen be a felügyelt Google Play Áruházba ugyanazzal a Google-fiókkal, amelyet az Android for Work-kötés konfigurálásához használt.
3.  Kattintson a **Jóváhagyás** lehetőségre.  Ekkor megnyílik egy új párbeszédpanel.
4.  Tekintse át a párbeszédpanelen látható engedélyeket, majd kattintson a **Jóváhagyás** lehetőségre. Ezeknek az engedélyeknek a jóváhagyására azért van szükség, hogy a Céges portál alkalmazás kezelni tudja az eszközön lévő munkahelyi profilt.
5.  Válassza a **Jóváhagyás fenntartása, amikor az alkalmazás új engedélyeket kér** lehetőséget, majd kattintson a **Mentés** gombra.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>A felhasználók tájékoztatása arról, hogy miképpen regisztrálhatják az eszközeiket a vállalati erőforrások eléréséhez

A felhasználókat meg kell kérnie, hogy a Google Play Áruházból töltsék le az Intune Céges portál alkalmazást, és annak útmutatása alapján regisztrálják eszközeiket. Az alkalmazás végigvezeti a felhasználókat a beléptetési folyamaton, tájékoztatja őket arról, hogy mire számíthatnak, illetve hogy mit láthatnak a rendszergazdák az eszközeiken található dolgokból, és mit nem.

Hivatkozást is küldhet nekik az online regisztrációhoz: [Androidos eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)

Más felhasználói feladatokkal kapcsolatos további információkért tanulmányozza a következő cikkeket:

- [Információk végfelhasználóknak a Microsoft Intune használatáról](end-user-educate.md)
- [Android-eszköz használata az Intune-nal](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Az Android for Work rendszergazdai fiókja kötésének megszüntetése

Az Android for Work-regisztrációt és -felügyeletet ki is kapcsolhatja. Az Intune felügyeleti konzolján a **Kötés megszüntetése** lehetőséget választva minden regisztrált Android for Work-eszköz kötése megszűnik. Ez az Android for Work-fiók és az Intune között is megszünteti a kapcsolatot.

### <a name="to-unbind-an-android-for-work-account"></a>Android for Work-fiók kötésének megszüntetése

1. **Android for Work-kötés feloldása**<br>
    Az Intune rendszergazdájaként az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** elemet.  Az **Intune** panelen válassza az **Eszközök beléptetése** > **Android for Work-regisztráció** elemet, majd válassza a **Kötés megszüntetése** elemet.

2. **Android for Work-kötés törlésének jóváhagyása**<br>
  A kötés törléséhez és az összes Android for Work-eszköz Intune-regisztrációjának megszüntetéséhez válassza az **Igen** gombot.
