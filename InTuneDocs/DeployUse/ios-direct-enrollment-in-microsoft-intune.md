---
# required metadata

title: iOS-eszközök közvetlen regisztrációja a Microsoft Intune-nal | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS-eszközök közvetlen regisztrálása az Apple Configurator használatával
Az Intune támogatja a vállalat által birtokolt iOS-eszközök Mac számítógépen futó [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) eszköz segítségével történő regisztrálását. Ez a folyamat nem állítja gyári alaphelyzetbe az eszközt, és az eszközt előre definiált szabályzattal regisztrálja. Ez a módszer azokon az eszközökön használható, amelyeken **Nincs megadva felhasználói affinitás**. A módszer használatához az iOS-eszközt USB-kapcsolaton egy Mac géphez kell csatlakoztatni a vállalati regisztráció beállítása érdekében. A vállalati portál alkalmazás nem támogatott a közvetlen módon regisztrált eszközökön. Ez az útmutató feltételezi, hogy az Apple Configurator 2.0 verzióját használja egy Mac-gépen.

1.  **Profil létrehozása az eszközökhöz**
    Egy eszközregisztrációs profil meghatározza az eszközökre alkalmazott beállításokat. Ha még nem tette meg, az Apple Configurator eszközzel regisztrált iOS-eszközökhöz hozzon létre egy eszközregisztrációs profilt.

    #### Profil létrehozása

    1.  A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) lépjen a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** elemre, majd kattintson a **Hozzáadás...** elemre..

        ![Eszközbeléptetési profil létrehozása oldal](../media/pol-sa-corp-enroll.png)

    2.  Adja meg az eszközprofilok részleteit:

        -   **Név** – Az eszközregisztrációs profil neve. A felhasználók számára nem látható.

        -   **Leírás** – Az eszközregisztrációs profil leírása. A felhasználók számára nem látható.

        -   **Felhasználói kapcsolat** – Meghatározza az eszközök regisztrációjának módját. A közvetlen regisztrációhoz válassza a **Nincs megadva a felhasználói affinitás** lehetőséget..

        -   **Előzetes eszközcsoport-hozzárendelés** – Minden, ezzel a profillal telepített eszköz kezdetben ehhez a csoporthoz fog tartozni. A regisztrálás után új csoportba sorolhatja az eszközöket.

    3.  Kattintson a **Profil mentése** lehetőségre a profil hozzáadásához.

2.  **iOS-eszközök hozzáadása az Apple Configuratorral való regisztrációhoz**
    A [Microsoft Intune felügyeleti konzolján](http://manage.microsoft.com) lépjen a **Csoportok** &gt; **Minden eszköz** &gt; **Előre regisztrált vállalati eszközök** &gt; **iOS-sorozatszám szerint** területre, majd kattintson az **Eszközök felvétele...** gombra..

    ![iOS beállítási asszisztens](../media/pol-SA-enroll-iOS-SetupAssistant.png)

      Két módon adhat hozzá eszközöket:

    -   **Sorozatszámokat tartalmazó CSV-fájl feltöltése** – Hozzon létre egy vesszővel elválasztott, kétoszlopos, fejléc nélküli értéklistát (.csv), amelyben maximum 5000 eszköz szerepel. A csv-fájl mérete nem haladja meg az 5 MB-ot.

        |||
        |-|-|
        |&lt;1. sorozatszám&gt;|&lt;1. eszköz részletei&gt;|
        |&lt;2. sorozatszám&gt;|&lt;2. eszköz részletei&gt;|
        Ez a .csv- fájl egy szövegszerkesztőben megtekintve így jelenik meg:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Eszközadatok kézi hozzáadása** – Adja meg legfeljebb öt eszköz sorozatszámát és eszközadatait, majd kattintson a **Next** (Tovább) gombra.

    > [!NOTE]
    > Ha a később el kell távolítania vállalati tulajdonú eszközöket az Intune kezeléséből, az eszköz regisztrációjának letiltásához el kell távolítania a sorozatszámát az Intune **Céges eszközök** csoportjából.  Ha az Intune vész-helyreállítási folyamatot hajt végre a sorozatszámok eltávolítása közben vagy az akörüli időszakban, győződjön meg arról, hogy a csoportban csak az aktív eszközök sorozatszámai szerepelnek.

3.  **Regisztrálni kívánt eszközök kiválasztása**
    Ellenőrizze a regisztrálni kívánt eszközöket. A már regisztrált vagy más módszerrel már regisztrált sorozatszámok nem importálhatók. A folytatáshoz kattintson a **Tovább** gombra.

4.  **Profil hozzárendelése**
    Adja meg a hozzáadott eszközökhöz hozzárendelendő profilt az elérhető profilok listájából, tekintse át a **Regisztrációs profil részleteit**(Kiszolgálók kezelése) elemet, és kattintson az **Befejezés**. A manuálisan hozzáadott eszközök bármilyen regisztrációs profilhoz hozzárendelhetők.

5.  **Az iOS-eszközökre telepíteni kívánt profil kiválasztása**
    A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) lépjen a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** lehetőségre, majd válassza ki a mobileszközökre telepítendő eszközprofilt. Ennek a profilnak egyeznie kell az előző lépésben a telepítéshez rendelt profillal. Kattintson az **Exportálás…** lehetőségre a tálcán. Kattintson a **Profil letöltése** elemre, és mentse a letöltött .mobileconfig fájlt.

6.  **A fájl átvitele**
    Másolja a letöltött .mobileconfig fájlt egy Mac számítógépre.
    > [!NOTE]
    > A regisztrációs profil URL-címe az exportálástól számított két hétig érvényes. Két hét után új regisztrációs profil URL-címet kell exportálnia az iOS-eszközök Beállítási asszisztenssel végzett regisztrálásához.
7.  **Az eszköz előkészítése az Apple Configuratorral**
    Az iOS-eszközök csatlakoznak a Mac számítógéphez, és regisztrálva vannak a mobileszköz-kezelésre.

    1.  A Mac számítógépen indítsa el az **Apple Configurator 2.0** alkalmazást..

    2.  Csatlakoztassa az iOS-eszközt a Mac számítógéphez egy USB-kábellel. Zárja be a **Fotók**, az **iTunes** és más alkalmazásokat, amelyek nyitva voltak az eszköz észlelésekor.

    3.  Az Apple Configuratorban kattintson egyszer a csatlakoztatott iOS-eszközre, majd kattintson az **Add** (Hozzáadás) gombra. Az eszközhöz adható lehetőségek a legördülő listában jelennek meg. Kattintson a **Profiles** (Profilok) gombra. .

    4.  A fájlkiválasztóval válassza ki az Intune-ból exportált .mobileconfig fájlt, majd kattintson az **Add** (Hozzáadás) gombra. Ezzel a profil hozzá lesz adva az eszközhöz.  Ha az eszköz **Felügyeletlen**, a telepítéshez az eszköz elfogadására van szükség.

8.  **A profil telepítése**
    Most már készen áll a profil telepítésére az iOS-eszközön. Az eszköz elvileg elvégezte a Beállítási asszisztens lépéseit, és készen áll a használatra.  Ha a regisztrációba alkalmazástelepítések tartoznak, az eszközhöz be kell állítani egy Apple ID-t, mert az alkalmazástelepítésekhez Apple ID-vel kell bejelentkezni az Apple Store áruházba.

    ###### Profilelfogadás felügyeletlen iOS-eszközök esetében

    1.  Oldja fel az iOS-eszköz zárolását.

    2.  A **Felügyeleti profil** **Profil telepítése** párbeszédpanelén koppintson a **Telepítés** gombra..

    3.  Adja meg az **Eszköz PIN-kódját** vagy az **Apple ID-t**, ha szükséges.

    4.  Fogadja el a **Figyelmeztetést**, és koppintson a **Telepítés** gombra..

    5.  Fogadja el a **Távoli figyelmeztetést**, és koppintson a **Megbízhatóság** gombra..

    6.  Amikor a **Profil telepítve** mező megerősíti, hogy a profil **Telepítve** van, kattintson a **Kész** gombra..

9. **Profil ellenőrzése**
    Az iOS-eszközön indítsa el a **Beállítások** alkalmazást, majd válassza az **Általános** &gt; **Eszközfelügyelet** &gt; **Felügyeleti profil** &gt; lehetőséget, és ellenőrizze, hogy a profiltelepítés szerepel-e a listában, valamint ellenőrizze az iOS-házirend korlátozásait és a telepített alkalmazásokat. A házirend-korlátozások és alkalmazások megjelenítése az eszközön akár 10 percet is igénybe vehet.

10. **Eszközök terjesztése**
    Az iOS-eszköz most már felügyelt, és regisztrálva van az Intune-nal.


### További információ
[Felkészülés az eszközök regisztrálására](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


