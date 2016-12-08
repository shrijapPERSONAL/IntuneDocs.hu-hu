---
title: "Az eszközbeállítások kezelése szabályzatokkal | Microsoft Intune"
description: "Az Intune segítségével szabályzatokat hozhat létre és telepíthet, amelyek vezérlik a beállításokat és a szolgáltatásokat a felügyelt regisztrált eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0238350139837a06a48d0bff7c53e4c39e07168c
ms.openlocfilehash: b2cba92c4cf75412b562267aef9d6a138f25952b


---

# <a name="manage-settings-and-features-on-your-devices-with-microsoft-intune-policies"></a>Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával
A Microsoft Intune*-szabályzatok* a mobileszközök és a számítógépek funkcióit szabályozó beállítások csoportjai. A szabályzatokat ajánlott vagy testreszabott beállításokat tartalmazó sablonok segítségével hozhatja létre, majd telepítheti őket az eszköz- vagy felhasználói csoportok számára.

## <a name="types-of-policies"></a>Szabályzatok típusai

Az Intune-szabályzatok két kategóriába sorolhatók: A használt kategória befolyásolja a szabályzat létrehozását és telepítését.


- **Konfigurációs szabályzatok:** Ezek általában az eszközök biztonsági beállításainak és szolgáltatásainak kezelésére használhatók. A témakörben található információk alapján megismerheti a szabályzatok létrehozását és telepítését, valamint a rendelkezésre álló beállításokat.
- **Eszközök megfelelőségi szabályzatai:** Ezek határozzák meg az eszközre vonatkozó szabályokat és beállításokat, amelyek ahhoz szükségesek, hogy az eszköz megfeleljen a feltételes hozzáférési szabályzatok előírásainak. A megfelelőségi szabályzatokkal a feltételes hozzáféréstől függetlenül is megfigyelheti és kijavíthatja az eszközök megfelelőséggel kapcsolatos hibáit.
A részleteket lásd: [Eszközmegfelelőségi szabályzatok a Microsoft Intune-ban](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Feltételes hozzáférési szabályzatok:** Ezekkel a szabályzatokkal a megadott feltételek alapján biztosíthatja a levelezés és más szolgáltatások védelmét.
A részleteket lásd: [Az e-mailek és az O365-szolgáltatások elérésének korlátozása a Microsoft Intune-ban](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Vállalati eszközregisztrációs szabályzatok:** a vállalati eszközregisztrációs szabályzatok létrehozásának részletes ismertetését lásd: [iOS- és Mac-eszközök kezelésének beállítása a Microsoft Intune-ban](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Erőforrás-hozzáférési szabályzatok**: Ezekkel a szabályzatokkal hozzáférést biztosíthat a felhasználóknak a munkájuk sikeres elvégzéséhez szükséges fájlokhoz és erőforrásokhoz, bárhol legyenek is.
A részleteket lásd: [A vállalati erőforrások hozzáférésének engedélyezése a Microsoft Intune-nal](enable-access-to-company-resources-with-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Az Intune-szabályzatok teljes listáját lásd: [A Microsoft Intune szabályzatainak ismertetése](microsoft-intune-policy-reference.md).

## <a name="create-a-configuration-policy"></a>Konfigurációs házirend létrehozása

1.  A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com/) válassza a **Házirend** &gt; **Konfigurációs szabályzatok** &gt; **Hozzáadás** lehetőséget.

2.  Válassza ki a kívánt szabályzatot, és válassza a hozzá ajánlott beállítások használatát (ha elérhető, a beállítások később módosíthatók), vagy hozzon létre egyéni szabályzatot a saját beállításaival.

    > [!TIP]
    > A megfelelő szabályzat kiválasztásához [A Microsoft Intune szabályzatainak ismertetése](microsoft-intune-policy-reference.md) témakörben talál segítséget.

3.  Amikor elkészült, válassza a **Házirend létrehozása** lehetőséget.

4.  A **Szabályzat létrehozása** lapon adja meg a szabályzat nevét, illetve igény szerint a leírását.

5.  Konfigurálja a kívánt szabályzatbeállításokat, majd válassza a **Szabályzat mentése** elemet.

    Ha segítségre van szüksége bármelyik házirend-beállítással kapcsolatban, válassza ki a házirendtípust a következő listából:

    - [iOS-eszközbeállítások](ios-policy-settings-in-microsoft-intune.md)
    - [Android-eszközbeállítások](android-policy-settings-in-microsoft-intune.md)
    - [Beállítások Android for Work eszközökhöz](android-for-work-policy-settings-in-microsoft-intune.md)
    - [Windows 8 és Windows 8.1 rendszerű eszközök beállításai](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Windows Phone 8.1 rendszerű eszközök beállításai](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Windows 10 rendszerű asztali és mobileszközök beállításai](windows-10-policy-settings-in-microsoft-intune.md)
    - [Windows Team-eszközök beállításai](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [A Windows-kiadás frissítésének beállításai](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Mac OS X-eszközbeállítások](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Az Exchange ActiveSync beállításai](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Használati feltételek szabályzatbeállításai](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Mobileszközök általános beállításai (örökölt)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  A megerősítő párbeszédpanelen válassza az **Igen** lehetőséget a házirend telepítéséhez, vagy a **Nem** lehetőséget, ha telepítés nélkül kívánja azt létrehozni.

Az új szabályzat megtekintéséhez és szerkesztéséhez keresse meg azt az egyes szabályzattípusok szakaszaiban a **Szabályzat** munkaterületen.

Ha olyan házirendet hoz létre, amely az ajánlott beállításokat alkalmazza, akkor az új házirend neve a sablon nevének, dátumának és időpontjának kombinációjából tevődik össze. Ha szerkeszti a szabályzatot, a neve módosul a szerkesztés dátumával és időpontjával.

A létrehozott szabályzatot általában telepíteni kell egy vagy több felhasználó- vagy eszközcsoportra.

> [!TIP]
> Nem minden házirendtípust kell telepíteni. A mobilalkalmazás-kezelési (MAM-) szabályzat például nem igényel telepítést. Ezt a házirendtípus egy alkalmazáshoz kell társítani, és ezután az alkalmazást kell telepíteni.

## <a name="deploy-a-configuration-policy"></a>Konfigurációs szabályzat telepítése

1.  A **Szabályzat** munkaterületen válassza ki a telepíteni kívánt szabályzatot, és kattintson a **Központi telepítés kezelése** elemre.

2.  A **Telepítések kezelése** párbeszédpanelen:

    -   A házirend telepítése – Válasszon ki egy vagy több olyan csoportot, amelynek telepíteni kívánja a házirendet, majd kattintson a **Hozzáadás** &gt; **OK** gombra.

    -   Ha a szabályzat telepítése nélkül kívánja bezárni a párbeszédpanelt, kattintson a **Mégse** gombra.

Ha egy már telepített házirendet választ ki, a házirendlista alsó részén további információkat láthat róla.

## <a name="manage-policies"></a>A szabályzatok kezelése

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) válassza a **Szabályzat**elemet, majd keresse meg és válassza ki a kezelni kívánt szabályzatot.

2.  Válasszon a következő lehetőségek közül:

- **Szerkesztés**: Megnyitja módosításra a kiválasztott szabályzat tulajdonságait.
- **Törlés**: Törli a kiválasztott szabályzatot.<br>Ha töröl egy házirendet, az minden olyan csoportból törlődik, ahol telepítve volt.
- **Központi telepítés kezelése**: Válassza ki azt a csoportot, amely számára telepíteni kívánja a szabályzatot, majd kattintson a **Hozzáadás** gombra.


## <a name="frequently-asked-questions-about-intune-policies"></a>A Microsoft Intune szabályzataival kapcsolatban gyakran felmerülő kérdések

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-deployed"></a>Mennyi időt vesz igénybe, hogy a mobileszközök megkapják a házirendet vagy az alkalmazásokat a telepítés után?
Egy házirend vagy alkalmazás telepítésekor az Intune megpróbálja értesíteni az eszközt, hogy jelentkezzen be az Intune-ba. Ez általában öt percnél kevesebb időt vesz igénybe.

Ha az eszköz az első értesítés után nem jelentkezik be, hogy beszerezze a szabályzatot, az Intune három további kísérletet tesz.  Ha az eszköz kapcsolat nélküli állapotban van (például ki van kapcsolva vagy nem kapcsolódik hálózathoz), előfordulhat, hogy nem kapja meg az értesítéseket. Ebben az esetben az eszköz az Intune szolgáltatásba való következő ütemezett bejelentkezéskor szerzi be a házirendet a következő módon:

- iOS és Mac OS X: 6 óránként.
- Android: 8 óránként.
- Windows Phone: 8 óránként.
- Eszközként regisztrált Windows 8.1 és Windows 10-számítógépek: 8 óránként.

Ha az eszköz nemrég lett regisztrálva, a bejelentkezés gyakoribb lesz, a következőképpen:

- iOS és Mac OS X: 6 órán át 15 percenként, majd 6 óránként.
- Android: 15 percen át 3 percenként, majd 2 órán át 15 percenként, majd 8 óránként.
- Windows Phone: 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként.
- Eszközként regisztrált Windows-számítógépek: 30 percen át 3 percenként, majd 8 óránként.

A felhasználók emellett a Vállalati Portál alkalmazás megnyitásával bármikor jelentkezhetnek a szabályzat beszerzéséhez.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Milyen műveletek hatására küld az Intune azonnal értesítést egy eszközre?
Az eszközök akkor jelentkeznek be az Intune-ba, amikor bejelentkezési értesítést kapnak, vagy amikor a rendszeres ütemezésű bejelentkezés esedékessé válik.  Ha a művelet, például a törlés, a zárolás, a jelszó-visszaállítás, az alkalmazástelepítés, a profiltelepítés (Wi-Fi, VPN, e-mail stb.) vagy a szabályzattelepítés kifejezetten egy eszközre vagy felhasználóra vonatkozik, az Intune azonnal megpróbálja értesíteni az eszközt, hogy be kell jelentkeznie az Intune szolgáltatásba a frissítések fogadásához.

Az egyéb módosítások – például a kapcsolattartási adatok módosítása a vállalati portálon – nem indítják el az azonnali értesítések küldését az eszközök felé.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Ha ugyanazon felhasználó vagy eszköz számára több házirend is települ, honnan tudható, hogy melyik beállítások lesznek érvényben?
Ha több szabályzatot telepít ugyanazon felhasználó vagy eszköz számára, az alkalmazni kívánt beállítás értékelése az egyes beállítások szintjén történik:

-   A megfelelőségi házirend-beállítások mindig prioritást élveznek a konfigurációs házirend-beállításokkal szemben.

-   Ha egy beállítás több megfelelőségi házirendben is szerepel, akkor a szigorúbb megfelelőségi beállítás lesz érvényes.

-   Ha egy konfigurációs szabályzatbeállítás ütközik egy másik konfigurációs szabályzatbeállítással, az ütközés az Intune-konzolon is megjelenik. Az ilyen ütközéseket manuálisan kell feloldani.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Mi történik, ha a mobilalkalmazás-kezelési házirendek ütköznek egymással? Melyik lesz érvényes az alkalmazásra?
Az ütközési értékek a MAM-szabályzatok legkorlátozóbb beállításai a számbeviteli mezők kivételével (ilyen például a PIN-kód beviteli próbálkozások száma az alaphelyzetbe állítás előtt).  A számbeviteli mezők értékei megegyeznek a – javasolt beállításokkal a konzolban létrehozható – MAM-házirendek értékeivel.

Akkor történik ütközés, ha két azonos házirend-beállítás van.  Például előfordulhat, hogy a másolás/beillesztés beállításra két megegyező MAM-házirendet konfigurált.  Ebben az esetben a másolás/beillesztés beállítás a legszigorúbb értékre lesz állítva, a többi beállítás pedig a konfiguráltak szerint lesz megadva.

Ha az alkalmazáshoz telepít és érvénybe léptet egy házirendet, majd egy másikat is telepít, akkor az első elsőbbséget élvez és érvényben marad, a második pedig ütközést jelez. Ha egyszerre telepíti őket, tehát nincs első szabályzat, akkor mindkettő ütközést jelez. Minden ütközésnél a legszigorúbb beállítás lesz érvényes.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>Mi történik, ha az egyéni iOS-házirendek ütköznek?
Az Intune nem értékeli a konfigurációs Apple-fájlok vagy az Open Mobile Alliance egységes erőforrás-azonosítóra (OMA-URI) vonatkozó egyéni szabályzatainak tartalmát. Csak kézbesítési mechanizmusként funkcionál.

Ha egyéni szabályzatot telepít, győződjön meg arról, hogy a konfigurált beállítások nem ütköznek a megfelelőségi, konfigurációs vagy az egyéb egyéni szabályzatokkal. A beállítási ütközést tartalmazó egyéni házirendekben a beállítások alkalmazásának sorrendje véletlenszerű.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Mi történik, ha egy szabályzatot törölnek, vagy a szabályzat alkalmazhatatlanná válik?
Amikor töröl egy házirendet, vagy eltávolít egy olyan eszközt a csoportból, amelyen a házirend telepítve volt, akkor a házirend és a beállítások a következő listákban összefoglaltak szerint törlődnek az adott eszközről.

#### <a name="enrolled-devices"></a>Regisztrált eszközök

- Wi-Fi, VPN, tanúsítvány és e-mail profilok: Ezek a profilok az összes támogatott regisztrált eszközről el lesznek távolítva.
- Minden egyéb házirendtípus:
    - **Windows és Android rendszerű eszközök**: A beállítások nem törlődnek az eszközről.
    - **Windows Phone 8.1 rendszerű eszközök**: A következő beállítások törlődnek:
        - Jelszó szükséges a mobileszközök feloldásához
        - Egyszerű jelszavak engedélyezése
        - Jelszó minimális hossza
        - Kötelező jelszótípus
        - Jelszó lejárata (nap)
        - Jelszóelőzmények megjegyzése
        - Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt
        - Tétlen percek száma, mielőtt az eszköz újból kéri a jelszót
        - Kötelező jelszótípus – megadandó karakterek minimális száma
        - Kamera használatának engedélyezése
        - Mobileszköz titkosításának kötelezővé tétele
        - Cserélhető tároló használatának engedélyezése
        - Webböngésző használatának engedélyezése
        - Alkalmazástároló használatának engedélyezése
        - Képernyőfelvétel-készítés használatának engedélyezése
        - Földrajzi hely meghatározásának engedélyezése
        - Microsoft-fiók használatának engedélyezése
        - Másolás és beillesztés használatának engedélyezése
        - Wi-Fi alapú internetmegosztás használatának engedélyezése
        - Wi-Fi elérési pontokhoz való automatikus csatlakozás engedélyezése
        - Wi-Fi elérési pontok jelentéskészítésének engedélyezése
        - Gyári beállítások visszaállításának engedélyezése
        - Bluetooth használatának engedélyezése
        - NFC használatának engedélyezése
        - Wi-Fi használatának engedélyezése

    - **iOS**: Az összes beállítás törlődik, kivéve a következőket:
        - Hangroaming használatának engedélyezése
        - Adatroaming használatának engedélyezése
        - Automatikus szinkronizálás engedélyezése roaming közben

#### <a name="windows-pcs-running-the-intune-client-software"></a>Az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek

- **Endpoint Protection-beállítások**: A beállítások visszaállnak az ajánlott értékekre. Az egyetlen kivétel a **Kapcsolódás a Microsoft Active Protection Service szolgáltatáshoz** beállítás, amelynek az alapértelmezett értéke **Nem**. A részleteket lásd: [Windows rendszerű számítógépek biztonságossá tétele a Microsoft Intune-hoz készült Endpoint Protection szolgáltatással](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Szoftverfrissítések beállításai**: A beállítások az operációs rendszer alapértelmezett állapotára állnak vissza. A részleteket lásd: [Windows rendszerű számítógépek naprakészen tartása szoftverfrissítésekkel a Microsoft Intune-ban](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **A Microsoft Intune Center beállításai**: Minden olyan támogatási kapcsolattartási adat törlődik a számítógépről, amelyet a szabályzat adott meg.
- **A Windows tűzfal beállításai**: A beállítások a számítógép operációs rendszerének alapértelmezett értékeire állnak vissza. A részleteket lásd: [Windows rendszerű számítógépek biztonságossá tétele a Microsoft Intune-hoz készült Endpoint Protection szolgáltatással](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).


### <a name="how-can-i-refresh-the-policies-on-a-device-to-ensure-that-they-are-current-applies-to-windows-pcs-running-the-intune-client-software-only"></a>Hogyan frissíthetők a szabályzatok az eszközökön a naprakész állapot biztosításához (csak az Intune ügyfélszoftvert futtató Windows rendszerű számítógépekre vonatkozik)?

1.  Bármely eszközcsoportban válassza ki azokat az eszközöket, amelyeknek a házirendjeit frissíteni kívánja, majd válassza a **Távoli feladatok** &gt; **Házirendek frissítése** lehetőségre.
2.  A feladat állapotának megtekintéséhez kattintson az Intune felügyeleti konzol jobb alsó sarkában lévő **Távoli feladatok** elemre.

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Hol találhatok segítséget a szabályzatokkal kapcsolatos problémák elhárításához?

Lásd a [Szabályzatokkal kapcsolatos problémák elhárítása a Microsoft Intune-ban](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune) témakört.



<!--HONumber=Nov16_HO1-->


