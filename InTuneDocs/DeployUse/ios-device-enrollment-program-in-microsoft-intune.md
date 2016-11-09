---
title: "Apple DEP-kezelés iOS-eszközökön | Microsoft Intune"
description: "Olyan regisztrációs profil telepítése, amely az iOS készülékregisztrációs program (DEP) keretében vásárolt Apple-eszközök felügyelet céljából történő vezeték nélküli regisztrálására szolgál."
keywords: 
author: staciebarker
ms.author: stabar
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 1bc39e7e91b1511ffb99e92e569df0a7153cc06f


---

# <a name="enroll-corporateowned-device-enrollment-program-ios-devices"></a>A készülékregisztrációs programban részt vevő vállalati iOS-eszközök regisztrálása
A Microsoft Intune-nal olyan regisztrációs profilt telepíthet, amely képes vezeték nélkül regisztrálni a készülékregisztrációs programon (DEP) keresztül vásárolt iOS-eszközöket. A regisztrációs csomag telepítősegéd-beállításokat is tartalmazhat az eszközhöz. A DEP programon keresztül regisztrált eszközök regisztrációját a felhasználók nem törölhetik.

## <a name="apple-dep-management-for-ios-devices-with-microsoft-intune"></a>Apple DEP-kezelés iOS-eszközökön a Microsoft Intune-nal
Ahhoz, hogy a vállalat által birtokolt eszközöket az Apple készülékregisztrációs programjával (DEP) lehessen kezelni, a szervezetnek csatlakoznia kell az Apple DEP-hez, és a programon keresztül kell beszereznie az eszközöket. A folyamat részletei a következő webhelyen érhetők el:  [https://deploy.apple.com](https://deploy.apple.com). A program előnyei közé tartozik a beavatkozás nélküli beállítás, amelynek használata esetén az eszközöket nem kell csatlakoztatnia egy számítógép USB-portjához.

A vállalat által birtokolt iOS-eszközöket csak egy az Apple-től származó DEP-jogkivonat birtokában regisztrálhatja a DEP programba. Ez a jogkivonat lehetővé teszi, hogy az Intune szinkronizálja a DEP-ben résztvevő, vállalat által birtokolt eszközök adatait. A token ezen felül lehetővé teszi, hogy az Intune Regisztrációs profilokat töltsön fel az Apple-nek, és a feltöltött profilokhoz eszközöket rendeljen hozzá.

1.  **iOS-eszközök kezelésének megkezdése a Microsoft Intune-nal**</br>
    Az iOS DEP-eszközök regisztrálása előtt engedélyeznie kell az iOS-eszközök Intune-beli felügyeletét.

2.  **Titkosítási kulcs beszerzése**</br>
    Rendszergazda felhasználóként bejelentkezve nyissa meg a [Microsoft Intune felügyeleti konzolját](http://manage.microsoft.com), és a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** területen válassza a **Titkosítási kulcs letöltése** lehetőséget. Mentse a titkosítási kulcs fájlját (.pem) helyileg. A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.

      ![DEP-token frissítése](../media/dev-sa-ios-dep.png)

3.  **DEP-token beszerzése**</br>
    Nyissa meg a [Device Enrollment Program portálját](https://deploy.apple.com) (https://deploy.apple.com), és jelentkezzen be a vállalati Apple ID azonosítóval. A későbbiekben ezt az Apple ID-t kell használnia a DEP-jogkivonat megújításához.

    1.  A [Device Enrollment Program portálján](https://deploy.apple.com) válassza a **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Servers** (Kiszolgálók kezelése), majd az **Add MDM Server** (MDM-kiszolgáló felvétele) lehetőséget.

    2.  Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.

    3.  Megnyílik az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanel. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.

    4.  Az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanelen megjelenik a **Your Server Token** (Az Ön kiszolgálói jogkivonata) hivatkozás. Töltse le a kiszolgálói jogkivonatfájlt (.p7m) a számítógépre, majd válassza a **Done**(Kész) lehetőséget.

    A tanúsítványfájl (.p7m) segítségével megbízhatósági kapcsolatot hozhat létre az Intune és az Apple DEP-kiszolgálói között.

4.  **A DEP-token hozzáadása az Intune-hoz**</br>
    A [Microsoft Intune felügyeleti konzoljában](http://manage.microsoft.com) lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** lapra, majd válassza a **DEP-token feltöltése** lehetőséget. **Keresse meg** a tanúsítványfájlt (.p7m), adja meg **Apple ID azonosítóját**, majd válassza a **Feltöltés** lehetőséget.

5.  **A vállalati eszközregisztrációs szabályzat felvétele**</br>
    A [Microsoft Intune felügyeleti konzoljában](http://manage.microsoft.com) lépjen a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** lapra, majd válassza a **Hozzáadás** lehetőséget.

    Adja meg az **Általános** lapon található adatokat, például töltse ki a **Név** és a **Leírás** mezőt, valamint adja meg, hogy a profilhoz rendelt eszközök felhasználóhoz vagy csoporthoz tartozzanak-e.
      - **Rákérdezés a felhasználói affinitásra** – Az eszközt a kezdeti beállítás során össze kell kapcsolni egy felhasználóval, hogy az eszköz ezen a felhasználón keresztül hozzáférhessen a vállalati adatokhoz és e-mailekhez. A **felhasználói affinitást** a DEP programmal felügyelt olyan eszközöknél kell beállítani, amelyek felhasználók tulajdonában vannak, de munkahelyi portált kell rajtuk használni (azaz alkalmazásokat kell rájuk telepíteni).</br> **Megjegyzés:** A felhasználói affinitással rendelkező DEP-eszközök nem támogatják a többtényezős hitelesítést.

      > [!NOTE]
      > A felhasználói affinitással rendelkező DEP funkció esetében a felhasználói jogkivonat kérelmezéséhez engedélyezni kell a WS-Trust 1.3 Username/Mixed végpontot.

      - **Nincs megadva a felhasználói affinitás** – Az eszköz egyetlen felhasználóhoz sincs társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt munkahelyi portál alkalmazást is beleértve, nem fognak működni.

    Ezen kívül **Eszközöket rendelhet hozzá a következő csoporthoz** is. A csoport kijelöléséhez válassza a **Kijelölés...** lehetőséget.

    [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    Következő lépésként engedélyezze **A szabályzat DEP-beállításainak konfigurálása** beállítást a DEP támogatásához.

      ![A Beállítási asszisztens ablaktábla](../media/pol-sa-corp-enroll.png)

     A DEP által felügyelt eszközök számára a következő beállítások érhetőek el:

     - **Részleg** – Akkor jelenik meg, ha a felhasználó az aktiválás során az **About Configuration** (Konfiguráció névjegye) elemre koppint.
     - **Ügyfélszolgálat telefonszáma** – Akkor jelenik meg, ha a felhasználó az aktiválás közben a **Segítségre van szüksége?** gombra kattint.
     - **Előkészítés módja** – Ezt az aktiválás közben állítja be a rendszer, és az eszköz gyári beállításainak visszaállítása nélkül nem lehet módosítani:
        - **Felügyeletlen** – Korlátozott felügyeleti funkciók
        - **Felügyelt** – Több felügyeleti funkciót engedélyez, és alapértelmezés szerint letiltja az Aktiválási zár funkciót
     - **A regisztrálási profil rögzítése a következő eszközhöz** – Ezt aktiválás közben lehet beállítani, és a gyári beállítások visszaállítása nélkül nem módosítható.
        - **Letiltás** – Lehetővé teszi a felügyeleti profil eltávolítását a **Beállítások** menüből.
        - **Engedélyezés** – (Az **Előkészítés módja** = **Felügyelt** beállítás szükséges hozzá.) Letiltja az iOS azon beállításait, amelyek lehetővé tennék a felügyeleti profil eltávolítását.
     - **Beállítási asszisztens – Beállítások** – Ezeknek a beállításoknak a megadása nem kötelező, és az iOS **Beállítások** menüjében később is konfigurálhatók.
        - **PIN-kód** – PIN-kód kérése aktiváláskor. PIN-kód megadására mindig szükség van, kivéve, ha az eszköz biztonságát, illetve elérésének szabályozását valamilyen más módszer biztosítja (például teljes képernyős mód, amely egyetlen alkalmazás futtatására korlátozza az eszközt).
        - **Helyalapú szolgáltatások** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja a szolgáltatást.
        - **Visszaállítás** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során iCloud-alapú biztonsági mentést fog kérni.
        - **Apple ID** – Ha engedélyezte, az iOS kérni fogja a felhasználótól az Apple ID azonosítót, ha az azonosító megadása nélkül próbál alkalmazást telepíteni az Intune-ban. Az App Store-beli iOS-alkalmazások letöltéséhez Apple ID azonosító szükséges, az Intune által telepített alkalmazásokat is beleértve.
        - **Feltételek és kikötések** – Ha engedélyezte, a Beállítási asszisztens az aktiválás során arra fogja kérni a felhasználót, hogy fogadja el az Apple használati feltételeit.
        - **Touch ID** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Apple Pay** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Nagyítás** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Siri** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
        - **Diagnosztikai adatok küldése az Apple-nek** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást.
     -  **Az Apple Configurator további felügyeleti funkcióinak engedélyezése** – Állítsa a **Letiltás** beállításra, hogy megakadályozza a fájloknak az iTunesszal való szinkronizálását, illetve az Apple Configuratoron keresztüli felügyeletet. Javasoljuk, hogy állítsa a beállítást a **Letiltás** értékre, a további konfigurációkat exportálja az Apple Configuratorból, majd az Intune-on keresztül telepítse ezeket egyéni iOS-konfigurációs profilként ahelyett, hogy ezzel a beállítással engedélyezné a tanúsítvánnyal vagy anélkül történő manuális telepítést.
        - **Letiltás** – Megakadályozza, hogy az eszköz USB-kapcsolaton keresztül kommunikáljon (párosítás letiltása).
        - **Engedélyezés** – Engedélyezi az eszköz és bármely PC vagy Mac-számítógép közötti, USB-kapcsolaton keresztüli kommunikációt.
        - **Tanúsítvány megkövetelése** – Engedélyezi a regisztrációs profilba importált tanúsítvánnyal rendelkező Mac számítógépekkel való párosítást.

6.  **DEP-eszközök hozzárendelése kezelés céljából** – Nyissa meg a [Device Enrollment Program portált](https://deploy.apple.com) (https://deploy.apple.com), és jelentkezzen be a vállalati Apple ID-vel. Válassza a **Deployment Program** (Telepítési program) &gt; **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Devices** (Eszközök kezelése) lehetőséget. Adja meg, hogy miként fogja kiválasztani az eszközöket ( **Choose Devices**), adja meg az eszközinformációkat, és adja meg a részleteket az eszköz sorozatszáma ( **Serial Number**) vagy rendelésszáma ( **Order Number**) alapján, illetve CSV-fájl feltöltésével ( **Upload CSV File**). Ezután válassza az **Assign to Server** (Hozzárendelés kiszolgálóhoz) lehetőséget, válassza ki a Microsoft Intune-hoz megadott &lt;kiszolgálónevet&gt;, majd kattintson az **OK** gombra.

7.  **DEP által felügyelt eszközök szinkronizálása** – Rendszergazda felhasználóként bejelentkezve nyissa meg a [Microsoft Intune felügyeleti konzolját](http://manage.microsoft.com), és a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** területen válassza a **Szinkronizálás** lehetőséget. A szolgáltatás elküld egy szinkronizálási kérelmet az Apple-nek. Ha meg szeretné tekinteni a DEP által felügyelt eszközöket a szinkronizálás után, nyissa meg a [Microsoft Intune felügyeleti konzoljának](http://manage.microsoft.com) **Csoportok** &gt; **Minden eszköz** &gt; **Előre regisztrált vállalati eszközök** &gt; **iOS-sorozatszám szerint** menüpontját. Az **iOS-sorozatszám szerint** munkaterületen, a felügyelt eszközök **Állapot** mezőjében mindaddig a „Nincs kapcsolat” szöveg látható, amíg be nem kapcsolták az adott eszközt, és nem futtatták a Beállítási asszisztenst az eszköz regisztrálásához.

    Az Apple elfogadható DEP-forgalomra vonatkozó feltételeinek teljesítése érdekében az Intune a következő korlátozásokat írja elő:
     -  Teljes DEP-szinkronizálás legfeljebb hét naponként futtatható. A teljes szinkronizálás során az Intune frissíti az Apple által hozzárendelt összes Intune-sorozatszámot, függetlenül attól, hogy azokat korábban szinkronizálták-e. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
     -  A szinkronizálási kérelmek elbírálása 10 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.

8.  **Eszközök terjesztése a felhasználóknak** – Megkezdheti a vállalat által birtokolt eszközök terjesztését a felhasználóknak. Az iOS-eszközök bekapcsolásakor a rendszer regisztrálja az eszközöket az Intune-nal való felügyelet számára.

## <a name="changes-to-intune-group-assignments"></a>Változások az Intune csoport-hozzárendelésekben

Novembertől az eszközcsoport-kezelés az Azure Active Directoryba kerül át. Az Azure Active Directory-csoportokba költözés után a csoport-hozzárendelés nem jelenik meg a **Vállalati regisztrációs profil** beállításai között. Mivel ezek a módosítások több hónapig tartanak, lehet, hogy a változások nem lesznek azonnal láthatók. Az új portálra költözés után a dinamikus eszközcsoportok hozzárendelése a vállalati beléptetési profil neve alapján végezhető el. Ez a folyamat gondoskodik róla, hogy az eszközcsoportokhoz előzetesen hozzárendelt eszközök regisztrációja automatikusan megtörténjen, azaz a rendszer regisztrálja őket a megfelelő csoportban, és alkalmazza rájuk a szabályzatokat, illetve telepítse rájuk az alkalmazásokat. [További információk az Azure Active Directory-csoportokról](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)

### <a name="see-also"></a>További információ
[Az eszközök regisztrálásának előfeltételei](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO1-->


