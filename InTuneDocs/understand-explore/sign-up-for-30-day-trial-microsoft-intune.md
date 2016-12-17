---
title: "Regisztráció a Microsoft Intune 30 napos próbaverziójára | Microsoft Docs"
description: "Regisztrálhat és beállíthat egy ingyenes, 30 napos Microsoft Intune próbaverziót."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: a65ead23e62870647245120d1663706fc46810ac


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Regisztráció a Microsoft Intune ingyenes próbaverziójára
Ez a cikk végigvezeti Önt az Intune próbaverziójára való regisztráció lépésein, és előkészít egy pár felhasználót a próbaverzióhoz, ezáltal továbbléphet majd a kapcsolódó próbaverzióhoz készült útmutatóra, amely ismerteti, hogy hogyan kezel mobileszközöket az Intune. <!---or app data when devices are not enrolled in Intune.--->

## <a name="assumptions"></a>Előfeltételek
Ez a regisztrációs cikk és az útmutató a próbaverzióhoz feltételezi, hogy a próbaverziót kizárólag kipróbálás céljából használja, és előfizetéskor tiszta környezettel szeretne kezdeni.

Annak érdekébe, hogy megkönnyítsük Önnek a próba első lépéseit, egy nagyon egyszerű környezetet állítunk be, amely csak Intune-t használ, és feltételezi, hogy az Intune lesz az eszközkezelés egyetlen módja (más néven a mobileszköz-kezelő szolgáltató). Az útmutató során a részletesebb technikai tartalomra is felhívjuk figyelmét, ha mélyebbre szeretne ásni.

Az előfizetéses verzió minden funkciója elérhető a próbaverzióban, az egyetlen különbség az, hogy a próbaverzióban legfeljebb 100 felhasználói fiókja lehet.

## <a name="sign-up-for-your-trial"></a>Regisztráció a próbaverzióra
Látogasson el az [Intune regisztrációs](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) oldalára, és töltse ki az űrlapot a próbaverzióra való regisztrációhoz.

Ha rendelkezik munkahelyi vagy iskolai fiókkal és azt szeretné használni az Intune próbaverziójához, akkor kövesse [ezeket a regisztrációs utasításokat](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1). Azonban ez a cikk és az útmutató a próbaverzióhoz feltételezi, hogy nem használ ilyen fiókokat.

> [!TIP]
> Ha az informatikai műveletek és a felhasználók túlnyomó része nem az Ön földrajzi helyén van, akkor érdemes a teljesítmény teszteléséhez az előbbi földrajzi helyét megadni a próbaverzióban.

### <a name="post-sign-up-considerations"></a>A regisztrációt követően megfontolandó szempontok
Amikor próbaverziót regisztrál, e-mailben elküldjük a fiókadatait a regisztráció során megadott e-mail címre. Az e-mail megerősíti, hogy a próbaverzió aktív.

A regisztrációs folyamat befejezését követően átirányítjuk egy oldalra, amelyen az Office 365 felügyeleti központja segítségével felhasználókat vehet fel, illetve licenceket rendelhet a felhasználókhoz. Amikor legközelebb bejelentkezik az Intune-ba, a rendszer automatikusan átirányítja az Intune felügyeleti konzoljára.

## <a name="keeping-the-admin-center-and-the-intune-administration-console-straight"></a>A felügyeleti központ és az Intune felügyeleti konzol egyenesen tartása
Az Intune-hoz két portált fog használni: az Office 365 felügyeleti központját ([portal.office.com](https://portal.office.com)) és az Intune felügyeleti konzolját ([manage.microsoft.com](https://manage.microsoft.com)).

Többnyire az Intune felügyeleti konzoljában fog dolgozni, amelyet alább láthat. Ezen az oldalon állíthatja be és kezelheti a csoportjait, szabályzatait, eszközeit és alkalmazásait.

![A Windows Intune felügyeleti konzolját bemutató kép](./media/sign-up/intune-admin-console.png)

Az Office 365 felügyeleti központban (amelyet alább láthat) hozzáadhatja és kezelheti a felhasználókat, illetve a fiók más aspektusait, ideértve a számlázást és a támogatást is.

![Az Office 365 felügyeleti központját bemutató kép](./media/sign-up/office-admin-center.png)

Az Office 365 felügyeleti központból átléphet az Intune felügyeleti konzoljába. A felügyeleti központok a bal oldali navigációs ablak utolsó eleme alatt találhatók. Válassza az **Intune** elemet az Intune felügyeleti konzoljának új ablakban való megnyitásához.

![A Windows Intune felügyeleti konzoljára mutató hivatkozást bemutató kép](./media/sign-up/link-to-intune.png)

Az Intune-ból az Office 365 felügyeleti központba való visszajutáshoz válassza a **Felhasználók hozzáadása** feladatot a Csoportok – áttekintés oldalon.

![Az Office 365 felügyeleti központra mutató hivatkozást bemutató kép](./media/sign-up/task-add-users.png)

## <a name="add-users"></a>Felhasználók hozzáadása
Mielőtt az Office 365 felügyeleti központból átlépne az Intune-ba, adjon hozzá egy pár felhasználót a próbafiókjához.

Az Office 365 felügyeleti központban hozzáadhat felhasználókat egyesével vagy tömegesen egy .csv-fájl feltöltésével. A próbaverzió beállításánál mindkettőt elvégezzük. A munkakörnyezetben viszont érdemes kihasználnia az Azure Active Directory felhasználói fiókok előnyeit, amelyekről további információt talál az [Első lépések útmutatónkban](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) és a jelen cikk [További lépések](#Next-steps) szakaszában.

### <a name="add-an-individual-user"></a>Egyéni felhasználó hozzáadása
1. Bármelyik lehetőséget választja a felhasználó hozzáadásához, nyisson meg egy űrlapot, amely lehetővé teszi a felhasználó létrehozását. Csak a csillaggal (\*) jelölt elemek szükségesek.
![A felhasználó hozzáadása gombbal elérhető lehetőségeket bemutató kép](./media/sign-up/add-user.png)


2.  A felhasználó hozzáadásakor utolsó lépésként küldjön e-mailt a felhasználónak, amely tartalmazza az ideiglenes Intune-jelszavát. A próbaverzióhoz használja a saját munkahelyi e-mail-címét, így megkapja a bejelentkezési információkat, és látja az e-mailt, amit a felhasználók kapnak. A teszteszköz regisztrációjához használhatja ezeket a felhasználói identitásokat.<br/>

 ![A felhasználó hozzáadása művelet utolsó lépését bemutató kép](./media/sign-up/new-user-2.png)

3. Ha rendszergazdai szerepkört szeretne hozzárendelni egy felhasználóhoz, miután létrehozta, akkor a szerepkör szerkesztéséhez az Office 365 felügyeleti központban válassza ki a felhasználók listájából a felhasználónevet, majd válassza a **Szerkesztés** lehetőséget a Szerepkör sorban a választható és a felhasználóhoz hozzárendelhető felhasználói szerepkörök listájának megtekintéséhez.

 ![A felhasználói szerepkörökkel kapcsolatos lehetőségeket bemutató kép](./media/sign-up/change-user-role.png)

### <a name="import-multiple-users"></a>Több felhasználó importálása
1. A több felhasználó importálását végző varázslót a **További** listában találja.

 ![A több felhasználó hozzáadásának lehetőségét bemutató kép](./media/sign-up/add-multiple-users.png)

2. A .csv-file helyes beállításához segítséget nyújthat, ha letölt egy sablon fájlt, amelyre feltöltheti a felhasználói adatait. Ha megszeretné tekinteni, hogy pontosan milyen típusú adatok szükségesek az egyes mezőkhöz, töltse le a fejléceket és minta felhasználói információkat tartalmazó .csv-fájlt.

 ![A tömeges regisztrációs varázsló első lépését bemutató kép](./media/sign-up/bulk-enroll-step-1.png)


3. A .csv-fájl létrehozása és mentése után válassza a **Tallózás** elemet a fájl kiválasztásához. Ellenőrizze, majd kattintson a **Tovább** gombra. A rendszer feltölti a felhasználóit és hozzáadja őket az aktív felhasználók listájához.

Most itt az idő, hogy áttérjünk az Intune felügyeleti konzoljára a felhasználók, az eszközeik és az alkalmazásaik kezelésének megkezdéséhez.

> [!NOTE]
> A felhasználói nem jelennek meg az Intune-ban, amíg nem regisztrálnak egy kezelendő eszközt.

## <a name="next-steps"></a>További lépések
Kipróbálási forgatókönyv: [Mobileszköz-kezelés kipróbálása a Microsoft Intune-ban](mobile-device-management-trial-guide-microsoft-intune.md)

Az Azure Active Directory felhasználói fiókok Intune-nal való használatával kapcsolatos további információk:
- [Identitáskövetelmények](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [A címtár-szinkronizálás követelményei](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Többtényezős hitelesítés követelményei](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

További információk [Az Intune és a System Center Configuration Manager együttes használatáról](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)



<!--HONumber=Dec16_HO2-->


