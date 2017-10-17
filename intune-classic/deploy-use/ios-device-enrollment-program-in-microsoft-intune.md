---
title: "Apple DEP-felügyelet iOS-eszközökön"
description: "Olyan regisztrációs profil telepítése, amely az iOS készülékregisztrációs program (DEP) keretében vásárolt Apple-eszközök felügyelet céljából történő vezeték nélküli regisztrálására szolgál."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8ca8eaede9df070baf1f39023942a8b07c54b814
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2017
---
# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>A készülékregisztrációs programban részt vevő vállalati iOS-eszközök regisztrálása

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune-nal olyan regisztrációs profilt telepíthet, amely képes vezeték nélkül regisztrálni a készülékregisztrációs programon (DEP) keresztül vásárolt iOS-eszközöket. A regisztrációs csomag telepítősegéd-beállításokat is tartalmazhat az eszközhöz.

>[!NOTE]
>A DEP-regisztrációt nem lehet használni az [eszközregisztráció-kezelői](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) módszerrel.
>Ha a felhasználók a Céges portál alkalmazással regisztrálják iOS-es eszközeiket, az eszközök sorozatszámait pedig később importálják és egy DEP-profilhoz rendelik, akkor az eszközök Intune-regisztrációja megszűnik.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-dep-management"></a>iOS-es eszközök Apple DEP-felügyelettel való regisztrálásának előfeltételei

- [APNs-tanúsítvány telepítése](set-up-ios-and-mac-management-with-microsoft-intune.md)

- A szervezetnek csatlakoznia kell az Apple DEP-hez, és az eszközöket ezen program keretében kell beszerezniük. A folyamat részletei a következő webhelyen érhetők el:  [https://deploy.apple.com](https://deploy.apple.com). A program előnyei közé tartozik a beavatkozás nélküli beállítás, amelynek használata esetén az eszközöket nem kell csatlakoztatnia egy számítógép USB-portjához.

- A vállalat által birtokolt iOS-eszközöket csak egy az Apple-től származó DEP-jogkivonat birtokában regisztrálhatja a DEP programba. Ez a jogkivonat lehetővé teszi, hogy az Intune szinkronizálja a DEP-ben résztvevő, vállalat által birtokolt eszközök adatait. A token ezen felül lehetővé teszi, hogy az Intune Regisztrációs profilokat töltsön fel az Apple-nek, és a feltöltött profilokhoz eszközöket rendeljen hozzá.

## <a name="steps-to-enroll-ios-devices-by-using-apple-dep-management"></a>iOS-es eszközök Apple DEP-felügyelettel való regisztrálásának menete

Az alábbi lépések azt ismertetik, hogyan lehet azonnal regisztrálni az iOS-es eszközöket az Apple DEP-felügyelettel. Ahogyan az eszközök bekerülnek a céghez, majd kikerülnek onnan, bizonyos alább leírt lépéseket – például a sorozatszámok felvételét és eltávolítását – valószínűleg többször el kell majd végezni.

### <a name="get-an-encryption-key"></a>Titkosítási kulcs beszerzése

1. Rendszergazda felhasználóként bejelentkezve nyissa meg a [Microsoft Intune felügyeleti konzolját](https://manage.microsoft.com), és a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** területen válassza a **Titkosítási kulcs letöltése** lehetőséget.

2. Mentse a titkosítási kulcs fájlját (.pem) helyileg. A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.

![DEP-token frissítése](../media/dev-sa-ios-dep.png)

### <a name="get-a-device-enrollment-program-token"></a>DEP-token beszerzése

1. Nyissa meg a [Device Enrollment Program portálját](https://deploy.apple.com) (https://deploy.apple.com), és jelentkezzen be a vállalati Apple ID azonosítóval. A későbbiekben ezt az Apple ID-t kell használnia a DEP-jogkivonat megújításához.

2.  A Device Enrollment Program portálján válassza a **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Servers** (Kiszolgálók kezelése), majd az **Add MDM Server** (MDM-kiszolgáló felvétele) lehetőséget.

3.  Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.

4.  Megnyílik az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanel. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.

5.  Az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanelen megjelenik a **Your Server Token** (Az Ön kiszolgálói jogkivonata) hivatkozás. Töltse le a kiszolgálói jogkivonatfájlt (.p7m) a számítógépre, majd válassza a **Done**(Kész) lehetőséget.

   A tanúsítványfájl (.p7m) segítségével megbízhatósági kapcsolatot hozhat létre az Intune és az Apple DEP-kiszolgálói között.

### <a name="add-the-dep-token-to-intune"></a>A DEP-token hozzáadása az Intune-hoz

1. A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** lapra.

2. Válassza a **DEP-token feltöltése** lehetőséget. **Keresse meg** a tanúsítványfájlt (.p7m), adja meg **Apple ID azonosítóját**, majd válassza a **Feltöltés** lehetőséget.

### <a name="add-the-corporate-device-enrollment-policy"></a>A vállalati eszközregisztrációs házirend felvétele

1. A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) lépjen a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** lapra, majd válassza a **Hozzáadás** lehetőséget.

2. Adja meg az **Általános** lapon található adatokat, például töltse ki a **Név** és a **Leírás** mezőt, valamint adja meg, hogy a profilhoz rendelt eszközök felhasználóhoz vagy csoporthoz tartozzanak-e:

   - **Rákérdezés a felhasználói affinitásra** – Az eszközt a kezdeti beállítás során össze kell kapcsolni egy felhasználóval, hogy az eszköz ezen a felhasználón keresztül hozzáférhessen a vállalati adatokhoz és e-mailekhez. A **felhasználói affinitást** a DEP programmal felügyelt olyan eszközöknél kell beállítani, amelyek felhasználók tulajdonában vannak, de munkahelyi portált kell rajtuk használni (azaz alkalmazásokat kell rájuk telepíteni). A többtényezős hitelesítés (MFA) nem működik a regisztráció közben olyan DEP-eszközökön, amelyekre felhasználói affinitás érvényes. A regisztrációt követően az ilyen eszközökön is az elvárásoknak megfelelően működik az MFA. Az első bejelentkezéskor jelszómódosításra kötelezett új felhasználók nem kaphatnak értesítést a DEP-eszközökön történő regisztráció során. Ezen túlmenően a lejárt jelszavú felhasználók nem kapnak értesítést a jelszó visszaállításáról a DEP-regisztráció során, és a jelszó visszaállítását egy másik eszközről kell végrehajtaniuk.

    >[!NOTE]
    >A felhasználói affinitással rendelkező DEP funkció esetében a felhasználói jogkivonat kérelmezéséhez engedélyezni kell a [WS-Trust 1.3 Username/Mixed végpontot](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints). [További információ a WS-Trust 1.3-ról](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

   - **Nincs megadva a felhasználói affinitás** – Az eszköz egyetlen felhasználóhoz sincs társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt munkahelyi portál alkalmazást is beleértve, nem fognak működni.

   Ezen kívül **Eszközöket rendelhet hozzá a következő csoporthoz** is. A csoport kijelöléséhez válassza a **Kijelölés...** lehetőséget.

   > [!Important]
   > A csoport-hozzárendelések az Intune-ból az Azure Active Directory-ba kerülnek át. Az Intune-fiók vonatkozó frissítése után az **Eszközök hozzárendelése ehhez a csoporthoz** nem jelenik meg többé. [További információ](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

3. Engedélyezze **A szabályzat DEP-beállításainak konfigurálása** beállítást a DEP támogatásához.

      ![A Beállítási asszisztens ablaktábla](../media/pol-sa-corp-enroll.png)

   A DEP által felügyelt eszközök számára a következő beállítások érhetőek el:

   - **Részleg** – Akkor jelenik meg, ha a felhasználó az aktiválás során az **About Configuration** (Konfiguráció névjegye) elemre koppint.
   - **Ügyfélszolgálat telefonszáma** – Akkor jelenik meg, ha a felhasználó az aktiválás közben a **Segítségre van szüksége?** gombra kattint.
   - **Előkészítés módja** – Ezt az aktiválás közben állítja be a rendszer, és az eszköz gyári beállításainak visszaállítása nélkül nem lehet módosítani:
       - **Felügyeletlen** – Korlátozott felügyeleti funkciók
       - **Felügyelt** – Több felügyeleti funkciót engedélyez, és alapértelmezés szerint letiltja az Aktiválási zár funkciót
   - **A regisztrálási profil rögzítése a következő eszközhöz** – Ezt aktiválás közben lehet beállítani, és a gyári beállítások visszaállítása nélkül nem módosítható.
       - **Letiltás** – Lehetővé teszi a felügyeleti profil eltávolítását a **Beállítások** menüből.
       - **Engedélyezés** – (Az **Előkészítés módja** = **Felügyelt** beállítás szükséges hozzá.) Letiltja a felügyeleti profil eltávolítására szolgáló menüpontot az iOS-beállításokban
   - **Beállítási asszisztens – Beállítások** – Ezeknek a beállításoknak a megadása nem kötelező, és az iOS **Beállítások** menüjében később is konfigurálhatók.
        - **PIN-kód** – PIN-kód kérése aktiváláskor. PIN-kód megadására mindig szükség van, kivéve, ha az eszköz biztonságát, illetve elérésének szabályozását valamilyen más módszer biztosítja (például teljes képernyős mód, amely egyetlen alkalmazás futtatására korlátozza az eszközt)
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

### <a name="assign-the-profile-to-devices"></a>A profil hozzárendelése eszközökhöz

1. A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) lépjen a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** lapra, majd válassza a **Hozzárendelés** lehetőséget.

2. Válassza ki, hogy mely eszközökhöz szeretné hozzárendelni a létrehozott profilt. Választhatja a **Minden eszköz** lehetőséget, vagy jelölje ki a kívánt eszközöket, majd válassza a **Hozzáadás** elemet.

> [!Important]
> Jelenleg az Intune-ban megadhat egy „alapértelmezett” eszközregisztrációs profilt, és amikor új sorozatszámokat szinkronizál az Apple DEP szolgáltatással, akkor azok automatikusan ehhez a profilhoz lesznek hozzárendelve. Onnantól kezdve, hogy a közeljövőben a bérlője az új Azure Portalra lesz migrálva, nem fog tudni alapértelmezett profilt megadni és ahhoz sorozatszámokat automatikusan hozzárendelni. Ehelyett a sorozatszámokat egy adott profilhoz kell hozzárendelnie. [További információ](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <a name="assign-dep-devices-for-management"></a>DEP-eszközök hozzárendelése kezelés céljából

1. Nyissa meg a [Device Enrollment Program portált](https://deploy.apple.com) (https://deploy.apple.com), és jelentkezzen be a vállalati Apple ID-val.

2. Válassza a **Deployment Program** (Telepítési program) &gt; **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Devices** (Eszközök kezelése) lehetőséget.

3. Adja meg, hogy miként fogja kiválasztani az eszközöket ( **Choose Devices**), adja meg az eszközinformációkat, és adja meg a részleteket az eszköz sorozatszáma ( **Serial Number**) vagy rendelésszáma ( **Order Number**) alapján, illetve CSV-fájl feltöltésével ( **Upload CSV File**).

4. Válassza az **Assign to Server** (Hozzárendelés kiszolgálóhoz) lehetőséget, válassza ki a Microsoft Intune-hoz megadott &lt;kiszolgálónevet&gt;, majd kattintson az **OK** gombra.

### <a name="synchronize-dep-managed-devices"></a>DEP által felügyelt eszközök szinkronizálása

Ez a lépés szinkronizálja az eszközöket az Apple DEP szolgáltatással, és lehetővé teszi, hogy az eszközök megjelenjenek az Intune-konzolon.

1. Rendszergazda felhasználóként bejelentkezve nyissa meg a [Microsoft Intune felügyeleti konzolját](https://manage.microsoft.com), és a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** területen válassza a **Szinkronizálás** lehetőséget. A szolgáltatás elküld egy szinkronizálási kérelmet az Apple-nek.

2. Ha meg szeretné tekinteni a DEP által felügyelt eszközöket a szinkronizálás után, nyissa meg a [Microsoft Intune felügyeleti konzoljának](https://manage.microsoft.com) **Csoportok** &gt; **Minden eszköz** &gt; **Előre regisztrált vállalati eszközök** &gt; **iOS-sorozatszám szerint** menüpontját. Az **iOS-sorozatszám szerint** munkaterületen, a felügyelt eszközök **Állapot** mezőjében mindaddig a „Nincs kapcsolat” szöveg látható, amíg be nem kapcsolták az adott eszközt, és nem futtatták a Beállítási asszisztenst az eszköz regisztrálásához.

   Az Apple elfogadható DEP-forgalomra vonatkozó feltételeinek teljesítése érdekében az Intune a következő korlátozásokat írja elő:

   - Teljes DEP-szinkronizálás legfeljebb hét naponként futtatható. A teljes szinkronizálás során az Intune frissíti az Apple által hozzárendelt összes Intune-sorozatszámot, függetlenül attól, hogy azokat korábban szinkronizálták-e. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.

   - A szinkronizálási kérelmek elbírálása 10 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.

### <a name="distribute-devices-to-users"></a>Eszközök terjesztése a felhasználóknak

Megkezdheti a vállalati tulajdonú eszközök terjesztését a felhasználóknak. Az iOS-eszközök bekapcsolásakor a rendszer regisztrálja az eszközöket az Intune-nal való felügyelet számára. A felhasználói eszközkorlát a DEP-pel kezelt eszközökre érvényes.

>[!NOTE]
>Ha egy felhasználó DEP-eszközt próbál regisztrálni, miközben már elérte az eszközkorlátját, a regisztráció figyelmeztetés nélkül meghiúsul.

## <a name="changes-to-intune-group-assignments"></a>Változások az Intune csoport-hozzárendelésekben

2017 áprilisától az eszközcsoport-kezelés az Azure Active Directoryba kerül át. Az Azure Active Directory-csoportokba költözés után a csoport-hozzárendelés nem jelenik meg a vállalati beléptetési profil beállításai között. Mivel ezek a módosítások több hónapig tartanak, lehet, hogy a változások nem lesznek azonnal láthatók. Az új portálra költözés után a dinamikus eszközcsoportok hozzárendelése a vállalati beléptetési profil neve alapján végezhető el.

A migrálás után a rendszer a vállalati eszközregisztrációs profilok által előre hozzárendelt összes Intune-beli eszközcsoporthoz létrehoz egy megfelelő dinamikus eszközcsoportot az AAD-ben a vállalati eszközregisztrációs profil neve alapján. Az új profilnevek formátuma *EnrollmentProfile:&lt;a társított profil neve&gt;*. Ez a folyamat gondoskodik róla, hogy az eszközcsoportokhoz előzetesen hozzárendelt eszközök regisztrációja automatikusan megtörténjen, azaz a rendszer regisztrálja őket a megfelelő csoportban, és alkalmazza rájuk a szabályzatokat, illetve telepítse rájuk az alkalmazásokat.

Ez az automatikus csoportlétrehozás csak egyszer zajlik le, a csoportok migrálásakor. A migráció után az Intune-rendszergazdáknak kell létrehozniuk a csoportokat az Azure Portalon. A [Changes to Automatic Grouping for Corporate Pre-enrolled iOS Devices](https://blogs.technet.microsoft.com/intunesupport/2017/04/19/changes-to-automatic-grouping-for-corporate-pre-enrolled-ios-devices/) (Az automatikus csoportosítás változásai az előre regisztrált céges iOS-es eszközök esetében) című blogbejegyzésben olvashat részleteket arról, hogy ez milyen hatással van a céges tulajdonú iOS-es eszközök regisztrációjára.

Figyelmébe ajánljuk még a [További információk az Azure Active Directory-csoportokról](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/) című témakört.

### <a name="see-also"></a>További információ
[Az eszközök regisztrálásának előfeltételei](prerequisites-for-enrollment.md)
