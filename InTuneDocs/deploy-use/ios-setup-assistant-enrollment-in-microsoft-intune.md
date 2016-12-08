---
title: "IOS-eszközök regisztrálása a Beállítási asszisztenssel | Microsoft Intune"
description: "A vállalat tulajdonában lévő iOS-eszközök regisztrálása az Apple Configurator eszköz segítségével a gyári beállítások visszaállításhoz és az eszköznek a Beállítási asszisztens futtatására való felkészítéséhez"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: ea6a4732e747dccf9c42732c06bd1b8cdf20e91f


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens segítségével
Az Intune támogatja a vállalat által birtokolt iOS-eszközöknek a Mac számítógépen futó [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) segítségével történő regisztrálását. Ez a folyamat visszaállítja az eszköz gyári beállításait, és felkészíti az eszközt a Beállítási asszisztens futtatására, amely telepíti a vállalat szabályzatait az eszköz új felhasználója számára.

## <a name="setup-assistant-enrollment-for-ios-devices-with-microsoft-intune"></a>iOS-eszközök Beállítási asszisztenssel végzett regisztrációja a Microsoft Intune-nal
Az Apple Configuratorrel visszaállíthatja az iOS-eszközök gyári beállításait, és előkészítheti őket az új felhasználójuk általi használatra. Ehhez a módszerhez az iOS-eszközt egy Mac számítógéphez kell csatlakoztatni USB-kapcsolattal a vállalati regisztráció beállítása érdekében. A módszer emellett feltételezi, hogy Ön az Apple Configurator 2.0 verziót használja. Az iOS-eszközre alkalmazott szabályzatnak általában **felhasználói affinitást** kell tartalmaznia az Intune Vállalati portál alkalmazás használatának engedélyezése érdekében.

**Előfeltételek**
* [iOS-regisztráció engedélyezése](set-up-ios-and-mac-management-with-microsoft-intune.md) APNs tanúsítvány telepítésével
* Fizikai hozzáférés iOS-eszközökhöz – Az eszközöket úgy kell visszaállítani a gyári beállításokra, hogy ne legyen rájuk érvényes a jelszavas védelem.
* Az eszközök sorozatszáma – erről [Az iOS-eszközök sorozatszámának megkeresését](https://support.apple.com/en-us/HT204308) ismertető cikk nyújt tájékoztatást.
* USB csatlakozókábelek
* Az [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)-s verzióját futtató Mac számítógép


1.  **Mobileszköz-csoport létrehozása** (nem kötelező):
    Ha vállalatának mobileszköz-csoportokra van szüksége az eszközök kezeléséhez, hozza létre ezeket a csoportokat. Erről részletesebben a [Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) című cikk nyújt tájékoztatást.

2.  **Profil létrehozása az eszközökhöz**:
    Egy eszközregisztrációs profil meghatározza az egy eszközcsoportra alkalmazott beállításokat. A következő lépésekkel hozhat létre eszközregisztrációs profilt az Apple Configurator eszközzel regisztrált iOS-eszközök számára.

    1.  A [Microsoft Intune felügyeleti konzoljában](http://manage.microsoft.com) lépjen a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** lapra, majd válassza a **Hozzáadás** lehetőséget.
    ![Eszközbeléptetési profil létrehozása](../media/pol-sa-corp-enroll.png)

    2.  Adja meg az eszközprofilok részleteit:

        -   **Név** – Az eszközbeléptetési profil neve (nem látják a felhasználók).

        -   **Leírás** – Az eszközbeléptetési profil leírása (nem látják a felhasználók).

        -   **Regisztráció részletei** – Meghatározza az eszközök regisztrációjának módját.

            -   **Rákérdezés a felhasználói affinitásra** – Az eszközt össze kell kapcsolni egy felhasználóval a kezdeti beállítás során, majd engedélyezhető számára a vállalati adatok és e-mailek elérése. A **felhasználói affinitást** a DEP programmal felügyelt olyan eszközöknél kell beállítani, amelyek felhasználók tulajdonában vannak, de a Munkahelyi portált kell rajtuk használni például az eszközök telepítéséhez.

            -   **Nincs megadva a felhasználói affinitás** – Az eszköz egyetlen felhasználóhoz sincs társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.

        -   **Előzetes eszközcsoport-hozzárendelés** – Minden, ezzel a profillal telepített eszköz kezdetben ehhez a csoporthoz fog tartozni. A regisztrálás után új csoportba sorolhatja az eszközöket.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

        -  **Device Enrollment Program** – Az Apple Device Enrollment Program (DEP) nem használható a Beállítási asszisztenssel végzett regisztrációhoz. Ellenőrizze, hogy a váltógomb **ki** értékre van-e állítva.

    3.  Profil hozzáadásához válassza a **Profil mentése** lehetőséget.

3.  **iOS-eszközök regisztrálása a Beállítási asszisztenssel**:
    A [Microsoft Intune felügyeleti konzolján](http://manage.microsoft.com) lépjen a **Csoportok** &gt; **Minden eszköz** &gt; **Minden céges eszköz** &gt; **Minden eszköz** területre, majd kattintson az **Eszközök felvétele** gombra. Két módon adhat hozzá eszközöket:

    ![Eszközök felvétele párbeszédablak](../media/pol-SA-enroll-iOS-SetupAssistant.png)

    -   **Sorozatszámokat tartalmazó CSV-fájl feltöltése** – Hozzon létre egy vesszővel tagolt, kétoszlopos, fejléc nélküli értéklistát (.csv), amelyben legfeljebb 5000 eszköz szerepel. A csv-fájl mérete nem haladja meg az 5 MB-ot.

        |||
        |-|-|
        |&lt;1. sorozatszám&gt;|&lt;1. eszköz részletei&gt;|
        |&lt;2. sorozatszám&gt;|&lt;2. eszköz részletei&gt;|
        Ez a .csv- fájl így jelenik meg egy szövegszerkesztőben:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Eszközadatok kézi hozzáadása** &mdash; Adja meg legfeljebb tizenöt eszköz sorozatszámát és eszközadatait.

    > [!NOTE]
    > Ha a később el kell távolítania vállalati tulajdonú eszközöket az Intune kezeléséből, az eszköz regisztrációjának letiltásához el kell távolítania az eszköz gyári számát az Intune-ból az **Előre regisztrált vállalati eszközök** elemcsoportban található **iOS-sorozatszám szerint** eszközcsoportot használva. Ha az Intune vészhelyreállítási folyamatot hajt végre a sorozatszámok eltávolítása közben vagy ahhoz közeli időpontban, győződjön meg arról, hogy a csoportban csak az aktív eszközök sorozatszámai szerepelnek.

    Kattintson a **Tovább** gombra.

4.  **A regisztrálni kívánt eszközök kiválasztása**:
    Ellenőrizze a regisztrálni kívánt eszközöket. A már regisztrált vagy más módszerrel már regisztrált sorozatszámok nem importálhatók. A folytatáshoz válassza a **Tovább** gombot.

5.  **Profil hozzárendelése**:
    Adja meg a hozzáadott eszközökhöz hozzárendelendő profilt az elérhető profilok listájából, tekintse át a **Regisztrációs profil részleteit** elemet, és válassza a **Befejezés** gombot. A manuálisan hozzáadott eszközök bármilyen regisztrációs profilhoz hozzárendelhetők.

6.  **Az iOS-eszközökre telepíteni kívánt profil exportálása**:
    A [Microsoft Intune felügyeleti konzolban](http://manage.microsoft.com) válassza a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** lehetőséget, majd válassza ki a mobileszközökre telepítendő eszközprofilt. A tálcán válassza az **Exportálás** lehetőséget. Másolja ki és mentse el a **Profil URL-címét**. A címet később fel kell töltenie az Apple Configurator eszközbe az iOS-eszközök által használt Intune profil meghatározásához.
    Az Apple Configurator 2 támogatásához módosítania kell a 2.0-s profil URL-címét. Ehhez a írja be a következő kód helyére:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    ezt a kódot:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Az itt következő eljárás keretében az Apple Configurator segítségével feltölti a profil URL-címét az Apple DEP szolgáltatásába, ezzel meghatározza az iOS-eszközök által használandó Intune-profilt.



7.  **Az eszköz előkészítése az Apple Configuratorral**:
    Az iOS-eszközök csatlakoznak a Mac számítógéphez, és regisztrálva vannak a mobileszköz-kezelésre.

    1.  A Mac-számítógépen nyissa meg az **Apple Configurator 2** eszközt. A menüsávban válassza az **Apple Configurator 2**, majd a **Beállítások** elemet.

         > [!WARNING]
         > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. Az eszközön az **üdvözlőképernyőnek** kell látszania az eszköz csatlakoztatásakor.

    2. Válassza a beállítások paneljén a **Servers** (Kiszolgálók) elemét, majd az MDM Server wizard (MDM-kiszolgáló varázsló) elindításához válassza a „+” szimbólumot. Kattintson a **Tovább** gombra.

    3. Írja be az iOS-eszközök regisztrálása a Beállítási asszisztens segítségével a Microsoft Intune-ban című cikk 6. lépésében megadott MDM-kiszolgáló nevét a **Name** (Név) és az **Enrollment URL** (Regisztrációs URL-cím) mezőbe. Az Enrollment URL (Regisztrációs URL-cím) mezőnél az Intune-ból exportált regisztrációs profil URL-címét adja meg. Kattintson a **Tovább** gombra.  

       Ha a rendszer figyelmezteti, hogy nincs ellenőrizve a kiszolgáló URL-címe, nyugodtan figyelmen kívül hagyhatja. Kattintson minden megjelenő oldalon a **Next** (Tovább) gombra, amíg be nem fejeződik a varázsló.

    4.  Az iOS-mobileszközöket csatlakoztassa a Mac számítógéphez egy USB-adapterrel.

        > [!WARNING]
        > Az eszközökön vissza kell állítani a gyári beállításokat a regisztrációs folyamat során. Az ajánlott eljárás szerint állítsa alaphelyzetbe az eszközt, és kapcsolja be. A Beállítási asszisztens indításakor az eszközön az **üdvözlőképernyőnek** kell látszania.

    5.  Válassza a **Prepare** (Előkészítés) lehetőséget. A Prepare iOS Device (iOS-eszköz előkészítése) panelen válassza a **Manual** (Manuális) elemet, majd a **Next** (Tovább) gombot.

    6. Az Enroll in MDM Server (Regisztrálás MDM-kiszolgálón) panelen válassza ki a létrehozott kiszolgáló nevét, majd válassza a **Next** (Tovább) gombot.

    7. A Supervise Devices (Eszközök felügyelete) panelen válassza ki a felügyelet szintjét, majd válassza a **Next** (Tovább) gombot.

    8. A Create an Organization (Szervezet létrehozása) panelen válassza ki a szervezetet az **Organization** mezőben, vagy hozzon létre új szervezetet, majd válassza a **Next** (Tovább) gombot.

    9. A Configure iOS Setup Assistant (iOS-alapú Beállítási asszisztens konfigurálása) panelen válassza ki a felhasználó számára megjelenő lépéseket, majd válassza a **Prepare** (Előkészítés) gombot. Ha a rendszer kéri, végezzen hitelesítést a megbízhatósági beállítások frissítése érdekében.  

    10. Az iOS-eszköz előkészítésének befejezésekor válassza le az USB-kábelt.  

8.  **Eszközök terjesztése**:
    Az eszközök most már készen állnak a vállalati regisztrációra. Kapcsolja ki az eszközöket, és ossza ki őket a felhasználóknak. Amikor a felhasználók bekapcsolják az eszközüket, elindul a Beállítási asszisztens.



### <a name="see-also"></a>További információ
[Az eszközök regisztrálásának előfeltételei](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO2-->


