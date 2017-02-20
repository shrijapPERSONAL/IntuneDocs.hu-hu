---
title: "iOS-eszközök regisztrálása – Készülékregisztrációs program | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató munkahelyi iOS-eszközök regisztrálásához a Készülékregisztrációs programmal."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: adb2fd27d7f2b3f0ef4dce6b26fcb20d74b69a00
ms.openlocfilehash: 2986e659d384eaa67b64af1ce3ae48a1ac81a600


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A Microsoft Intune-nal olyan regisztrációs profilt telepíthet, amely képes vezeték nélkül regisztrálni a készülékregisztrációs programon (DEP) keresztül vásárolt iOS-eszközöket. A profil olyan felügyeleti beállításokat tartalmaz, amelyeket eszközökre alkalmazhat. A regisztrációs csomag telepítősegéd-beállításokat is tartalmazhat az eszközhöz. A DEP programon keresztül regisztrált eszközök regisztrációját a felhasználók nem törölhetik.

>[!NOTE]
>Ezt a regisztrációs módszert nem lehet használni az [eszközregisztráció-kezelői](enroll-devices-using-device-enrollment-manager.md) módszerrel.

Ahhoz, hogy a vállalat által birtokolt eszközöket az Apple készülékregisztrációs programjával (DEP) lehessen kezelni, a szervezetnek csatlakoznia kell az Apple DEP-hez, és a programon keresztül kell beszereznie az eszközöket. A folyamat részletei a következő webhelyen érhetők el:  [https://deploy.apple.com](https://deploy.apple.com). A program előnyei közé tartozik a beavatkozás nélküli beállítás, amelynek használata esetén az eszközöket nem kell csatlakoztatnia egy számítógép USB-portjához.

A vállalat által birtokolt iOS-eszközöket csak egy az Apple-től származó [DEP-jogkivonat](get-apple-dep-token.md) birtokában regisztrálhatja a DEP programba. Ez a jogkivonat lehetővé teszi, hogy az Intune szinkronizálja a DEP-ben résztvevő, vállalat által birtokolt eszközök adatait. A token ezen felül lehetővé teszi, hogy az Intune Regisztrációs profilokat töltsön fel az Apple-nek, és a feltöltött profilokhoz eszközöket rendeljen hozzá.

Az iOS-eszközök regisztrálásának további módjairól [Az iOS-eszközök regisztrálási módjának kiválasztása](choose-ios-enrollment-method.md) című témakörben olvashat.

## <a name="prerequisites"></a>Előfeltételek

iOS-eszközök regisztrációjának indítása előtt végezze el az alábbiakat:

- [Tartományok beállítása](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Az MDM-szolgáltató beállítása](set-mdm-authority.md)
- [Csoportok létrehozása](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- Felhasználói licencek hozzárendelése az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Apple MDM push-tanúsítvány beszerzése](get-an-apple-mdm-push-certificate.md)
- [Apple DEP-token beszerzése](get-apple-dep-token.md)

## <a name="create-an-apple-dep-profile-for-devices"></a>Apple DEP-profil létrehozása az eszközökhöz

Egy eszközregisztrációs profil meghatározza az egy eszközcsoportra alkalmazott beállításokat. A következő lépésekkel hozhat létre eszközregisztrációs profilt a DEP eszközzel regisztrált iOS-eszközök számára.

1. Válassza az Azure Portalon a **További szolgáltatások** elemet, írja be az **Intune** nevet a szövegmezőbe, majd válassza az **Egyéb** > **Intune** elemet.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Apple-regisztráció** elemet.

3. Az **Apple Device Enrollment Program (DEP) beállításainak kezelése** területen válassza a **DEP-profilok** lehetőséget.

4. Az **Apple DEP-profilok** panelen válassza a **Létrehozás** lehetőséget.

5. A **Regisztrációs profil létrehozása** panelen adja meg a profil nevét és leírását.

6. A **Felhasználói affinitás** lehetőségnél adja meg, hogy a profilt használó eszközök felhasználói affinitással vagy anélkül lesznek-e regisztrálva.

 - **Regisztrálás felhasználói affinitással** – Az eszközt össze kell kapcsolni egy felhasználóval a kezdeti beállítás során, majd engedélyezhető számára a vállalati adatok és e-mailek elérése. A felhasználói affinitást a DEP programmal felügyelt olyan eszközöknél kell választani, amelyek felhasználók tulajdonában vannak, de a Munkahelyi portált kell rajtuk használni például az alkalmazások telepítéséhez. Ügyeljen rá, hogy a többtényezős hitelesítés (MFA) nem működik a regisztráció közben olyan DEP-eszközökön, amelyekre felhasználói affinitás érvényes. A regisztrációt követően az ilyen eszközökön is az elvárásoknak megfelelően működik az MFA.

    >[!NOTE]
    >A felhasználói affinitással rendelkező DEP funkció esetében a felhasználói jogkivonat kérelmezéséhez engedélyezni kell a WS-Trust 1.3 Username/Mixed végpontot.

 - **Regisztrálás felhasználói affinitás nélkül** – Az eszköz egyetlen felhasználóhoz sincs társítva. Ezt a kapcsolatot olyan eszközök esetén alkalmazza, amelyek a helyi felhasználói adatok nélkül hajtanak végre feladatokat. A felhasználói kapcsolatot igénylő alkalmazások, az üzletági alkalmazások telepítéséhez használt Munkahelyi portál alkalmazást is beleértve, nem fognak működni.

7. Válassza az **Eszközfelügyeleti beállítások** lehetőséget, konfigurálja az alábbi beállításokat, majd válassza a **Mentés** elemet:

    - **Felügyelt** – olyan felügyeleti mód, amely több felügyeleti funkciót engedélyez, és alapértelmezés szerint tiltja az Aktiválási zár funkciót. Ha a jelölőnégyzetet üresen hagyja, a felügyeleti lehetőségek korlátozva lesznek.

    - **Zárolt regisztráció** – (Felügyelt felügyeleti mód szükséges hozzá) Letiltja az iOS azon beállításait, amelyek lehetővé tennék a felügyeleti profil eltávolítását. Ha a jelölőnégyzetet üresen hagyja, lehetővé teszi a felügyeleti profil eltávolítását a Beállítások menüből. Ezt aktiválás közben lehet beállítani, és a gyári beállítások visszaállítása nélkül nem módosítható.

    - **Párosítás engedélyezése** – meghatározza, hogy az iOS-eszközök szinkronizálhatók-e a számítógéppel. Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja, tanúsítványt kell választania az **Apple Configurator-tanúsítványok** területen.

    - **Apple Configurator-tanúsítványok** – Ha az **Apple Configurator engedélyezése tanúsítvány szerint** lehetőséget választja a **Párosítás engedélyezése** területen, válassza ki az importálandó Apple Configurator-tanúsítványt.

8. Válassza a **Beállítási asszisztens beállításai** lehetőséget és konfigurálja az alábbi profilbeállításokat, majd válassza a **Mentés** gombot:

    - **Részleg neve** – Akkor jelenik meg, ha a felhasználó az aktiválás során az **About Configuration** (Konfiguráció névjegye) elemre koppint.

    - **Részleg telefonszáma** – Akkor jelenik meg, ha a felhasználó az aktiválás közben a Segítségre van szüksége? gombra kattint.
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
        - **Diagnosztikai adatok** – Ha bekapcsolja ezt a funkciót, a Beállítási asszisztens az aktiválás során kérni fogja ezt a szolgáltatást

9. A profilbeállítások mentéséhez a **Regisztrációs profil létrehozása** panelen válassza a **Létrehoz** lehetőséget.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Apple DEP-sorozatszám hozzárendelése MDM-kiszolgálóhoz

1. Nyissa meg a [Device Enrollment Program portált](https://deploy.apple.com) (https://deploy.apple.com), és jelentkezzen be a vállalati Apple ID-val. 

2. Válassza a **Deployment Program** (Telepítési program) &gt; **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Devices** (Eszközök kezelése) lehetőséget. 

3. Adja meg, hogy miként fogja kiválasztani az eszközöket ( **Choose Devices**), adja meg az eszközinformációkat, és adja meg a részleteket az eszköz sorozatszáma ( **Serial Number**) vagy rendelésszáma ( **Order Number**) alapján, illetve CSV-fájl feltöltésével ( **Upload CSV File**). 

4. Válassza az **Assign to Server** (Hozzárendelés kiszolgálóhoz) lehetőséget, válassza ki a Microsoft Intune-hoz megadott &lt;kiszolgálónevet&gt;, majd kattintson az **OK** gombra.

## <a name="synchronize-dep-managed-devices"></a>DEP által felügyelt eszközök szinkronizálása

1. Az Azure Portalon válassza az Intune panel **Eszközök regisztrálása** elemét, majd az **Apple-regisztráció** elemet.

2. Az **Apple Device Enrollment Program (DEP) beállításainak kezelése** területen válassza a **DEP-sorozatszámok** lehetőséget.

4. Az **Apple DEP-sorozatszámok** panelen válassza a **Szinkronizálás** lehetőséget.

5. A **Szinkronizálás** panelen válassza a **Szinkronizálási kérelem** lehetőséget. A folyamatjelző mutatja, hogy mennyi idő múlva lehetséges újabb szinkronizálási kérelmet indítani.

    Az Apple elfogadható DEP-forgalomra vonatkozó feltételeinek teljesítése érdekében az Intune a következő korlátozásokat írja elő:
     -  Teljes DEP-szinkronizálás legfeljebb hét naponként futtatható. A teljes szinkronizálás során az Intune frissíti az Apple által hozzárendelt összes Intune-sorozatszámot, függetlenül attól, hogy azokat korábban szinkronizálták-e. Ha az előző teljes szinkronizálástól számított hét napon belül újabb teljes szinkronizálást kísérel meg, az Intune csak a szolgáltatásban még nem szereplő sorozatszámokat frissíti.
     -  A szinkronizálási kérelmek elbírálása 10 percet vesz igénybe. Ez idő alatt, vagy amíg a kérelem ellenőrzése nem fejeződött be, a **Szinkronizálás** gomb inaktív.

>[!NOTE]
>DEP-sorozatszámokat az **Apple DEP-sorozatszámok** panelen is hozzá tud rendelni profilokhoz.

## <a name="distribute-devices-to-users"></a>Eszközök terjesztése a felhasználóknak

Most már megkezdheti a céges eszközök kiosztását a felhasználóknak. Az iOS-eszközök bekapcsolásakor a rendszer regisztrálja az eszközöket az Intune-nal való felügyelet számára.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>A Vállalati portál telepítése és használata a felhasználók által

A felhasználói affinitással konfigurált eszközökön telepítheti és futtathatja a Vállalati portál alkalmazást az alkalmazások letöltéséhez és az eszközök kezeléséhez. Miután a felhasználók megkapják az eszközeiket, végre kell hajtaniuk az alább ismertetett további lépéseket a Beállítási asszisztens befejezéséhez és a Vállalati portál alkalmazás telepítéséhez.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>A vállalat által birtokolt iOS-eszközök regisztrálása felhasználói affinitás használatával 

1. Amikor a felhasználók bekapcsolják az eszközüket, megjelenik a Beállítási asszisztens befejezését kérő üzenet. A telepítés során a rendszer kéri a felhasználóktól a hitelesítő adataik megadását. A felhasználóknak az Intune-előfizetésükhöz tartozó hitelesítő adataikat (vagyis az egyedi felhasználónevüket vagy az egyszerű felhasználónevüket) kell megadniuk.

2. A telepítés során a rendszer kéri a felhasználóktól az Apple ID azonosítójuk megadását. Az Apple ID azonosítót azért kell megadni, hogy az eszköz telepíthesse a Vállalati portál alkalmazást. Az azonosítót a telepítés után, az iOS-beállítások menüben is megadhatják.

3. A telepítés befejezése után a felhasználóknak telepíteniük kell a Vállalati portál alkalmazását az App Store áruházból.

4. A felhasználó ekkor bejelentkezhet a Vállalati portál alkalmazásba az eszköz beállításakor megadott egyszerű felhasználónév használatával.

5. A bejelentkezés után a rendszer kéri a felhasználótól az eszköz regisztrálását. Ennek első lépése az eszköz azonosítása. Az alkalmazás megjeleníti azon iOS-eszközök listáját, amelyek már a vállalat tulajdonában vannak, és amelyek hozzá vannak rendelve a felhasználók Intune-fiókjához. A felhasználónak ki kell választania a megfelelő eszközt. Ha az eszköz még nincs regisztrálva a vállalatnál, a normál regisztrálási művelet folytatásához a felhasználó válassza az új eszköz lehetőséget.

6. A következő képernyőn a felhasználónak meg kell erősítenie az új eszköz sorozatszámát. Ehhez a megjelenő hivatkozást kell kiválasztania. A hivatkozás a Beállítások alkalmazást indítja el, amelynek segítségével a felhasználó ellenőrizheti a sorozatszámot. A felhasználónak ezután meg kell adnia a sorozatszám utolsó négy számjegyét a Vállalati portál alkalmazásban.

   Ez a lépés azt ellenőrzi, hogy az eszköz az Intune-ban regisztrált vállalati eszköz-e. Ha az eszközön található sorozatszám nem egyezik, a felhasználó nem a megfelelő eszköz választotta ki. A felhasználónak ekkor vissza kell lépnie az előző képernyőre, és ki kell választania egy másik eszközt.

7. A sorozatszám ellenőrzése után a Vállalati portál alkalmazás átirányítja a felhasználót a Vállalati portál webhelyre a regisztrálás véglegesítéséhez. Ekkor a webhely felkéri a felhasználót, hogy térjen vissza az alkalmazáshoz.

A regisztrálás ezzel befejeződött. Ezután a felhasználó az összes funkciójával együtt használhatja az eszközt.



<!--HONumber=Feb17_HO1-->


