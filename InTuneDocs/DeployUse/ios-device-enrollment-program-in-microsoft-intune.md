---
# required metadata

title: Apple DEP-kezelés iOS-eszközökön a Microsoft Intune-nal | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# A készülékregisztrációs programban részt vevő vállalati iOS-eszközök regisztrálása
A Microsoft Intune-nal egy olyan regisztrációs profil telepíthető, amely a készülékregisztrációs programon (DEP) keresztül megvásárolt iOS-készülékeket vezeték nélkül regisztrálja. A regisztrációs csomag telepítősegéd-beállításokat is tartalmazhat az eszközhöz. A DEP programon keresztül regisztrált eszközök regisztrációját a felhasználók nem törölhetik.

## Apple DEP-kezelés iOS-eszközökön a Microsoft Intune-nal
Ahhoz, hogy a vállalat által birtokolt eszközöket az Apple eszközregisztrációs programjával (DEP) lehessen kezelni, a szervezetnek csatlakoznia kell az Apple DEP-hez, és a programon keresztül kell beszereznie az eszközöket. A folyamat részletei a következő webhelyen érhetők el:  [https://deploy.apple.com](https://deploy.apple.com). A program előnyei közé tartozik a beavatkozás nélküli beállítás anélkül, hogy az eszközöket csatlakoztatnia kellene egy számítógép USB-portjához.

A vállalat által birtokolt iOS-eszközöket csak egy Apple-től származó DEP-token birtokában regisztrálhatja a DEP programba. Ez a token lehetővé teszi, hogy az Intune szinkronizálja a DEP-ben résztvevő, vállalat által birtokolt eszközöket. A token ezen felül lehetővé teszi, hogy az Intune Regisztrációs profilokat töltsön fel az Apple-nek, és a feltöltött profilokhoz eszközöket rendeljen hozzá.

1.  **iOS-eszközök kezelése a Microsoft Intune-ban – első lépések**
    Az iOS DEP-eszközök regisztrálása előtt engedélyeznie kell az iOS-eszközök kezelését az Intune-hoz.

2.  **Titkosítási kulcs beszerzése**
    Rendszergazda felhasználóként nyissa meg a [Microsoft Intune felügyeleti konzolt](http://manage.microsoft.com), lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** lapra, és kattintson **Titkosítási kulcs letöltése** lehetőségre. Mentse a titkosítási kulcs fájlját (.pem) helyileg. A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.

      ![DEP-token frissítése](../media/dev-sa-ios-dep.png)

3.  **DEP-token beszerzése**
    Nyissa meg a [Device Enrollment Program portált](https://deploy.apple.com) (https://deploy.apple.com), és jelentkezzen be a vállalati Apple ID-val. A későbbiekben ezt az Apple ID-t kell használnia a DEP-token megújításához.

    1.  A [Device Enrollment Program portálon](https://deploy.apple.com) válassza a **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Servers** (Kiszolgálók kezelése) elemet, és kattintson az **Add MDM Server** (MDM-kiszolgáló felvétele) elemre..

    2.  Az **MDM Server Name** mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next**(Tovább) gombra. A kiszolgálónév az MDM-kiszolgáló azonosítására szolgál, tehát nem a Microsoft Intune-kiszolgáló URL-címe vagy neve.

    3.  Megnyílik az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanel. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem fájl feltöltéséhez, majd kattintson a **Next** (Tovább) gombra..

    4.  Az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanelen megjelenik a **Your Server Token** (Az Ön kiszolgálói jogkivonata) hivatkozás. Töltse le a kiszolgálói jogkivonatfájlt (.p7m) a számítógépére, és kattintson a **Done** (Kész) elemre..

    A tanúsítványfájl (.p7m) segítségével megbízhatósági kapcsolatot hozhat létre az Intune és az Apple DEP-kiszolgálói között.

4.  **A DEP-token hozzáadása az Intune-hoz**
    A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** lehetőségre, kattintson a **DEP-token feltöltése**. **Tallózás** lehetőségre, keresse meg a tanúsítványfájlt (.p7m), adja meg **Apple ID**-azonosítóját, és kattintson a **Feltöltés** gombra..

5.  **A vállalati eszközregisztrációs házirend felvétele**
    A [Microsoft Intune felügyeleti konzolon](http://manage.microsoft.com) lépjen a **Házirend** &gt; **Munkahelyi eszközök regisztrációja** oldalra, majd kattintson a **Hozzáadás** elemre. A DEP támogatásához adja meg az **Általános** adatokat, például a **Nevet** és a **Leírást**, adja meg, hogy a profilhoz hozzárendelt eszközök felhasználóhoz vagy csoporthoz tartozzanak-e, majd engedélyezze **A szabályzat DEP-beállításainak konfigurálása** beállítást. A **Beállítási asszisztens ablakai** területen adhatók meg az iOS-eszköz telepítése során konfigurált beállítások.

      ![A Beállítási asszisztens ablaktábla](../media/pol-sa-corp-enroll.png)

6.  **DEP-eszközök hozzárendelése kezelés céljából**
    Nyissa meg a [Device Enrollment Program portált](https://deploy.apple.com) (https://deploy.apple.com), és jelentkezzen be a vállalati Apple ID-val. Válassza a **Deployment Program** (Telepítési program) &gt; **Device Enrollment Program)** (Készülékregisztrációs program &gt; **Manage Devices** (Eszközök kezelése) lehetőséget. Adja meg, hogy miként fogja kiválasztani az eszközöket ( **Choose Devices**), adja meg az eszközinformációkat, és adja meg a részleteket az eszköz sorozatszáma ( **Serial Number**) vagy rendelésszáma ( **Order Number**) alapján, illetve CSV-fájl feltöltésével ( **Upload CSV File**). Ezután válassza az **Assign to Server** (Hozzárendelés kiszolgálóhoz) lehetőséget, válassza ki a Microsoft Intune-hoz megadott &lt;Kiszolgálónevet&gt;, majd kattintson az **OK** gombra..

7.  **DEP által felügyelt eszközök szinkronizálása**
    Rendszergazda felhasználóként nyissa meg a [Microsoft Intune felügyeleti konzolt](http://manage.microsoft.com), lépjen a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **iOS** &gt; **Készülékregisztrációs program** lapra, és kattintson a **Szinkronizálás** lehetőségre. A szolgáltatás elküld egy szinkronizálási kérelmet az Apple-nek. Ha meg szeretné tekinteni a DEP által felügyelt eszközöket a szinkronizálás után, nyissa meg a [Microsoft Intune felügyeleti konzoljának](http://manage.microsoft.com) **Csoportok** &gt; **Minden céges eszköz** területét. A **Céges eszközök** munkaterületen, a felügyelt eszközök **Állapot** területén mindaddig a „Nincs kapcsolat” szöveg látható, amíg be nem kapcsolták az adott eszközt, és nem futtatták a Beállítási asszisztenst az eszköz regisztrálásához.

    Az Apple elfogadható DEP-forgalomra vonatkozó feltételeinek teljesítése érdekében az Intune a következő korlátozásokat írja elő:
     -  Teljes DEP-szinkronizálás legfeljebb 7 naponként futtatható. Teljes szinkronizálás során az Intune minden Apple által hozzárendelt Intune-sorozatszámot frissít, függetlenül attól, hogy azt már korábban szinkronizálták-e, vagy sem. Ha az előző teljes szinkronizálástól számított 7 napon belül egy újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
     -  A szinkronizálási kérelmek elbírálása 10 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a Szinkronizálás gomb inaktív.

8.  **Eszközök terjesztése a felhasználóknak**
    Megkezdheti a vállalati tulajdonú eszközök terjesztését a felhasználóknak. Az iOS-eszközök bekapcsolásakor a rendszer regisztrálja az eszközöket az Intune-nal való felügyelet számára.



### További információ
[Felkészülés az eszközök regisztrálására](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


