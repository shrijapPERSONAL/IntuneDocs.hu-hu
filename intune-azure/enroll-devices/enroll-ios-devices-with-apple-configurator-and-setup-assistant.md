---
title: "iOS-eszközök regisztrálása – az Apple Configurator és a Beállítási asszisztens"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Ismerje meg, hogyan regisztrálhatja a vállalat által birtokolt iOS-eszközöket az Apple Configurator és a Beállítási asszisztens használatával."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b2d2e4e0210526ff70b86526bd0b2e17bab0286b
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Az Intune támogatja a vállalat által birtokolt iOS-eszközöknek a Mac számítógépen futó [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) segítségével történő regisztrálását. Ez a folyamat visszaállítja az eszköz gyári beállításait és felkészíti a Beállítási asszisztens futtatására, amely telepíti a vállalat szabályzatait az eszköz új felhasználója számára.

>[!NOTE]
>Ezt a regisztrációs módszert nem lehet használni az [eszközregisztráció-kezelői](enroll-devices-using-device-enrollment-manager.md) módszerrel.

Az Apple Configuratorrel visszaállíthatja az iOS-eszközök gyári beállításait, és előkészítheti őket az új felhasználójuk általi használatra. Ehhez a módszerhez az iOS-eszközt egy Mac számítógéphez kell csatlakoztatni USB-kapcsolattal a vállalati regisztráció beállítása érdekében. A módszer emellett feltételezi, hogy Ön az Apple Configurator 2.0 verziót használja. Az iOS-eszközre alkalmazott szabályzatnak általában felhasználói affinitást kell tartalmaznia az Intune Céges portál alkalmazás használatának engedélyezése érdekében.

Az iOS-eszközök regisztrálásának további lehetőségeiről [Az iOS-eszközök regisztrálási módjának kiválasztása](choose-ios-enrollment-method.md) című témakörben olvashat.

## <a name="prerequisites"></a>Előfeltételek

Az iOS-eszközök regisztrációjának beállítása előtt teljesítse az alábbi előfeltételeket:

- [Tartományok beállítása](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Az MDM-szolgáltató beállítása](set-mdm-authority.md)
- [Csoportok létrehozása](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [A Céges portál konfigurálása](/intune-azure/manage-apps/company-portal-app.md)
- Felhasználói licencek hozzárendelése az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Apple MDM push-tanúsítvány beszerzése](get-an-apple-mdm-push-certificate.md)
- Az iOS-eszközökhöz való fizikai hozzáférés biztosítása
- Az eszközök sorozatszámának rendelkezésre állása – erről [az iOS-eszközök sorozatszámának megkeresését](https://support.apple.com//HT204308) ismertető cikk nyújt tájékoztatást.
- USB csatlakozókábelek előkészítése
- Gondoskodjon arról, hogy a Mac PC-n telepítve legyen az [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Configurator-sorozatszámok hozzáadása](add-apple-configurator-serial-numbers.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Apple Configurator-profil létrehozása az eszközökhöz

Egy eszközregisztrációs profil meghatározza az egy eszközcsoportra alkalmazott beállításokat. A következő lépésekkel hozhat létre eszközregisztrációs profilt az Apple Configurator eszközzel regisztrált iOS-eszközök számára.

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Apple-regisztráció** elemet.

3. **Az Apple Configurator regisztrációs beállításainak kezelése** területen válassza az **AC-profilok** elemet.

4. **Az Apple Configurator-regisztrációs profilok** panelen válassza a **Létrehozás** elemet.

5. A **Regisztrációs profil létrehozása** panelen adja meg a profil nevét és leírását.

6. A **Felhasználói affinitás** beállítással adja meg, hogy a profilt használó eszközök felhasználói affinitással vagy anélkül lesznek-e regisztrálva.

   - **Regisztrálás felhasználói affinitással** – Az eszközt egy felhasználóhoz kell társítani a kezdeti beállítás során, és így kaphat engedélyt a vállalati adatok és e-mailek elérésére. A felhasználói affinitást azoknál a DEP-pel felügyelt eszközöknél kell beállítani, amelyek felhasználók tulajdonában vannak, de a Céges portált kell rajtuk használni például az eszközök telepítéséhez.

   - **Regisztrálás felhasználói affinitás nélkül** – Az eszköz nem lesz felhasználóhoz társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.

7. A **Létrehozás** elemet választva mentse a profilt.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Sorozatszámok hozzárendelése az Apple Configurator-profilokhoz

A létrehozott Apple Configurator-profilokhoz hozzárendelheti az eszközök sorozatszámait. A sorozatszámokat előzőleg az [Apple Configurator-sorozatszámok hozzáadása](add-apple-configurator-serial-numbers.md) című témakörben leírtak alapján fel kell venni az Intune-ba.

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Sorozatszámok hozzárendelése Apple Configurator-profilokhoz

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az **Apple Configurator-regisztrációs profilok** panelen válassza ki azt a profilt, amelyikhez hozzá szeretné rendelni a sorozatszámokat.

3. A profil nevét viselő panelen válassza a **Sorozatszámok** > **Hozzárendelés** lehetőséget.

4. Jelölje ki a profilhoz rendelni kívánt sorozatszámokat, majd kattintson a **Hozzárendelés** gombra.

## <a name="export-the-profile-to-ios-devices"></a>Profil exportálása iOS-es eszközökre

Miután létrehozta a profilt, és hozzárendelte a sorozatszámokat, ki kell exportálnia a profilt az Intune-ból URL-ként vagy az alább ismertetett formátumban. Ezt követően manuálisan importálhatja egy Mac gépen az Apple Configuratorba, és utána azzal telepítheti az eszközökre.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Profil exportálása Setup Assistant-regisztrációval

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Az **Apple Configurator-regisztrációs profilok** panelen válassza ki az exportálandó profilt.

3. A profil panelén válassza a **Profil exportálása** lehetőséget.

4. Csatlakoztassa az iOS-eszközt, és másolja a profil URL-címét az [Apple Configuratorba](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12). A címet később fel kell töltenie az Apple Configurator eszközbe az iOS-eszközök által használt Intune profil meghatározásához.

  Az Apple Configurator 2 támogatásához módosítania kell a 2.0-s profil URL-címét. Ehhez a írja be a következő kód helyére:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    ezt a kódot:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Az itt következő eljárás keretében az Apple Configurator segítségével feltölti a profil URL-címét az Apple DEP szolgáltatásába, ezzel meghatározza az iOS-eszközök által használandó Intune-profilt.

5. Az Apple Configuratorral töltse fel a profil URL-címét az Apple DEP szolgáltatásba, ezzel meghatározza az iOS-eszközök által használandó Intune-profilt.


    1.  A Mac-számítógépen nyissa meg az **Apple Configurator 2** eszközt. A menüsávban válassza az **Apple Configurator 2**, majd a **Beállítások** elemet.

         > [!WARNING]
         > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. Az eszközön az **üdvözlőképernyőnek** kell látszania az eszköz csatlakoztatásakor.

    2. Válassza a **beállítások** paneljén a **Servers** (Kiszolgálók) elemét, majd a „+” szimbólumot választva indítsa el az MDM Server (MDM-kiszolgáló) varázslót. Kattintson a **Tovább** gombra.

    3. Írja be az iOS-eszközök regisztrálása a Beállítási asszisztens segítségével a Microsoft Intune-ban című cikk 6. lépésében megadott MDM-kiszolgáló nevét a **Name** (Név) és az **Enrollment URL** (Regisztrációs URL-cím) mezőbe. Az Enrollment URL (Regisztrációs URL-cím) mezőnél az Intune-ból exportált regisztrációs profil URL-címét adja meg. Kattintson a **Tovább** gombra.  

       Ha a rendszer figyelmezteti, hogy nincs ellenőrizve a kiszolgáló URL-címe, nyugodtan figyelmen kívül hagyhatja. Kattintson minden megjelenő oldalon a **Next** (Tovább) gombra, amíg be nem fejeződik a varázsló.

    4.  Az iOS-mobileszközöket csatlakoztassa a Mac számítógéphez egy USB-adapterrel.

        > [!WARNING]
        > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. A Beállítási asszisztens indításakor az eszközön az **üdvözlőképernyőnek** kell látszania.

    5.  Válassza a **Prepare** (Előkészítés) lehetőséget. A **Prepare iOS Device** (iOS-eszköz előkészítése) panelen válassza a **Manual** (Manuális) elemet, majd a **Next** (Tovább) gombot.

    6. Az **Enroll in MDM Server** (Regisztrálás MDM-kiszolgálón) panelen válassza ki a létrehozott kiszolgáló nevét, majd válassza a **Next** (Tovább) gombot.

    7. A **Supervise Devices** (Eszközök felügyelete) panelen válassza ki a felügyelet szintjét, majd válassza a **Next** (Tovább) gombot.

    8. A **Create an Organization** (Szervezet létrehozása) panelen válassza ki a szervezetet az **Organization** mezőben, vagy hozzon létre új szervezetet, majd válassza a **Next** gombot.

    9. A **Configure iOS Setup Assistant** (iOS-es Beállítási asszisztens konfigurálása) panelen válassza ki a felhasználó számára megjelenő lépéseket, majd válassza a **Prepare** (Előkészítés) gombot. Ha a rendszer kéri, végezzen hitelesítést a megbízhatósági beállítások frissítése érdekében.  

    10. Az iOS-eszköz előkészítésének befejezésekor válassza le az USB-kábelt.  

6.  **Eszközök terjesztése**:
    Az eszközök most már készen állnak a vállalati regisztrációra. Kapcsolja ki az eszközöket, és ossza ki őket a felhasználóknak. Amikor a felhasználók bekapcsolják az eszközüket, elindul a Beállítási asszisztens.

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>A Céges portál telepítése és használata a felhasználók által

A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez. Miután a felhasználók megkapják az eszközeiket, végre kell hajtaniuk az alább ismertetett további lépéseket a Beállítási asszisztens befejezéséhez és a Vállalati portál alkalmazás telepítéséhez.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>A vállalat által birtokolt iOS-eszközök regisztrálása felhasználói affinitás használatával

1. Amikor a felhasználók bekapcsolják az eszközüket, megjelenik a Beállítási asszisztens befejezését kérő üzenet. A telepítés során a rendszer kéri a felhasználóktól a hitelesítő adataik megadását. A felhasználóknak az Intune-előfizetésükhöz tartozó hitelesítő adataikat (vagyis az egyedi vagy egyszerű felhasználónevüket) kell megadniuk.

2. A telepítés során a rendszer kéri a felhasználóktól az Apple ID azonosítójuk megadását. Az Apple ID azonosítót azért kell megadni, hogy az eszköz telepíthesse a Vállalati portál alkalmazást. Az azonosítót a telepítés után, az iOS-beállítások menüben is megadhatják.

3. A telepítés befejezése után az iOS-eszközön telepíteni kell a Vállalati portál alkalmazását az App Store áruházból.

4. A felhasználó ekkor bejelentkezhet a Vállalati portál alkalmazásba az eszköz beállításakor megadott egyszerű felhasználónév használatával.

5. A bejelentkezés után a rendszer kéri a felhasználótól az eszköz regisztrálását. Ennek első lépése az eszköz azonosítása. Az alkalmazás megjeleníti azon iOS-eszközök listáját, amelyek már a vállalat tulajdonában vannak, és amelyek hozzá vannak rendelve a felhasználók Intune-fiókjához. A felhasználónak ki kell választania a megfelelő eszközt. Ha az eszköz még nincs regisztrálva a vállalatnál, a normál regisztrálási művelet folytatásához a felhasználó válassza az új eszköz lehetőséget.

6. A következő képernyőn a felhasználónak meg kell erősítenie az új eszköz sorozatszámát. A felhasználó a sorozatszámot megerősítő hivatkozásra koppintva indíthatja el a beállítási alkalmazást a sorozatszám ellenőrzéséhez. A felhasználónak ezután meg kell adnia a sorozatszám utolsó négy számjegyét a Céges portál alkalmazásban.

    Ez a lépés azt ellenőrzi, hogy az eszköz az Intune-ban regisztrált vállalati eszköz-e. Ha az eszközön található sorozatszám nem egyezik, nem a megfelelő eszköz választotta ki. A felhasználónak ekkor vissza kell lépnie az előző képernyőre, és ki kell választania egy másik eszközt.

7. A sorozatszám ellenőrzése után a Vállalati portál alkalmazás átirányítja a felhasználót a Vállalati portál webhelyre a regisztrálás véglegesítéséhez. Ekkor a webhely felkéri a felhasználót, hogy térjen vissza az alkalmazáshoz.

A regisztrálás ezzel befejeződött. Ezután a felhasználó az összes funkciójával együtt használhatja az eszközt.

