---

title: "A PC-ügyfélszoftver telepítése | Microsoft Intune"
description: "Ezzel az útmutatóval beállíthatja a Windows rendszerű számítógépeinek a Microsoft Intune-ügyfélszoftverrel való kezelését."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 738b6bedcefbfd8bf0fa7bde5b86c79293af527e
ms.openlocfilehash: 7d239a80ed68d39b2a7179a45178ba6ae11c5423


---

# <a name="install-the-intune-software-client-on-windows-pcs"></a>Az Intune-szoftverügyfél telepítése Windows rendszerű számítógépekre
A Windows rendszerű számítógépek az Intune-ügyfélszoftver telepítésével regisztrálhatók. Az Intune-ügyfélszoftver a következő módokon telepíthető:

- Manuális telepítéssel
- Csoportházirenddel telepített
- Lemezkép részeként történő telepítéssel
- Felhasználók általi telepítéssel

Az először letöltött Intune-szoftverügyfél tartalmazza azt a szoftvert, amely ahhoz szükséges, hogy a számítógépet regisztrálja az Intune-felügyeletben. A számítógép regisztrálása után az Intune-szoftverügyfél letölti a számítógép felügyeletéhez szükséges teljes ügyfélszoftvert.

Ezekkel a letöltésekkel minimalizálható a számítógép Intune-ban való regisztrálásához szükséges idő. Emellett azt is biztosítja, hogy a második letöltést követően az ügyfél a legfrissebb szoftverrel rendelkezzen.

## <a name="download-the-intune-client-software"></a>Az Intune-ügyfélszoftver letöltése

A maguk a felhasználók által végzett telepítés esetét kivéve valamennyi módszerhez le kell tölteni a szoftvert ahhoz, hogy központilag lehessen telepíteni.

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) kattintson a **Felügyelet** &gt; **Ügyfélszoftver letöltése** lehetőségre.

  ![Az Intune-számítógépügyfél letöltése](../media/pc-sa-client-download.png)

2.  Az **Ügyfélszoftver letöltése** oldalon kattintson az **Ügyfélszoftver letöltése** elemre. Ezt követően mentse a szoftvert tartalmazó **Microsoft_Intune_Setup.zip** csomagot a hálózat egy biztonságos helyére.

    > [!NOTE]
    > A Intune ügyfélszoftverének telepítőcsomagja tartalmazza a fiókja adatait. Ha jogosulatlan felhasználók férnek hozzá a telepítőcsomaghoz, a beágyazott tanúsítvány által jelölt fiókhoz számítógépeket regisztrálhatnak, és hozzáférhetnek a vállalat erőforrásaihoz.

3.  Bontsa ki a telepítőcsomag tartalmát a biztonságos helyre a hálózaton.

    > [!IMPORTANT]
    > Ne nevezze át vagy távolítsa el a kibontott **ACCOUNTCERT** fájlt, különben az ügyfélszoftver telepítése sikertelen lesz.

## <a name="deploy-the-client-software-manually"></a>Ügyfélszoftver manuális telepítése

Keresse meg a számítógépen azt a mappát, ahol az ügyfélszoftver telepítési fájljai találhatók. Futtassa a **Microsoft_Intune_Setup.exe** fájlt az ügyfélszoftver telepítéséhez.

    > [!NOTE]
    > The status of the installation is displayed when you hover over the icon in the taskbar on the client computer.

## <a name="deploy-the-client-software-by-using-group-policy"></a>Az ügyfélszoftver telepítése Csoportházirenddel

1.  A **Microsoft_Intune_Setup.exe** és a **MicrosoftIntune.accountcert** fájlt tartalmazó mappában futtassa a következő parancsot a 32 bites és 64 bites számítógépekhez készült Windows Installer-alapú telepítőprogramok kibontásához:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  Másolja a **Microsoft_Intune_x86.msi** fájlt, a **Microsoft_Intune_x64.msi** fájlt és a **MicrosoftIntune.accountcert** fájlt egy olyan hálózati helyre, amely minden olyan számítógép számára elérhető, amelyre telepíteni kívánja az ügyfélszoftvert.

    > [!IMPORTANT]
    > A fájlokat ne válassza szét vagy nevezze át, különben az ügyfélszoftver telepítése sikertelen lesz.

3.  A Csoportházirenddel telepítse a szoftvert a hálózaton lévő számítógépekre.

    A Csoportházirend szoftverek automatikus telepítésére való használatával kapcsolatban a Windows Server dokumentációjában találhat további információkat.

## <a name="deploy-the-client-software-as-part-of-an-image"></a>Egy lemezkép részeként telepítse az ügyfélszoftvert
Az Intune ügyfélszoftverét az alábbi eljárás alapján egy operációsrendszer-kép részeként is telepítheti a számítógépekre:

1.  Az ügyfél telepítési fájljait, a **Microsoft_Intune_Setup.exe** és a **MicrosoftIntune.accountcert** fájlt másolja a **%Systemdrive%\Temp\Microsoft_Intune_Setup** mappába a referencia-számítógépen.

2.  Hozzon létre egy **WindowsIntuneEnrollPending** nevű bejegyzést a beállításjegyzékben a következő parancs hozzáadásával a **SetupComplete.cmd** parancsfájlhoz:

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  A következő parancs a **setupcomplete.cmd** parancsfájlhoz való hozzáadásával futtassa a regisztrációs csomagot a /PrepareEnroll parancssori argumentummal:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > A **SetupComplete.cmd** parancsfájl lehetővé teszi, hogy a Windows telepítő módosításokat végezzen a rendszeren egy felhasználó bejelentkezése előtt. A **/PrepareEnroll** parancssori argumentum előkészíti a célzott számítógépet a Windows telepítő befejeződése után az Intune-ban való automatikus regisztráláshoz.

4.  Helyezze a **SetupComplete.cmd** fájlt a **%Windir%\Setup\Scripts** mappába a referencia-számítógépen.

5.  Rögzítsen egy rendszerképet a referencia-számítógépről, majd telepítse azt a célként megadott számítógépekre.

Amikor a célszámítógép a Windows telepítő befejezése után újraindul, létrejön a **WindowsIntuneEnrollPending** beállításkulcs. A regisztrálási csomag ellenőrzi, hogy regisztrálva van-e a számítógép. Ha a számítógép regisztrálva van, nem szükséges további művelet. Ha a számítógép nincs regisztrálva, a regisztrálási csomag létrehoz egy automatikus Microsoft Intune-regisztrálási feladatot.

Amikor a következő ütemezett időpontban lefut az automatikus regisztrálási feladat, ellenőrzi, hogy létezik-e a **MicrosoftIntuneEnrollPending** beállításkulcs, és megkísérli regisztrálni a célszámítógépet az Intune szolgáltatásban. Ha a regisztráció bármilyen okból nem sikerül, a rendszer ismét megkísérli a regisztrációt a feladat következő futtatásakor. A próbálkozások egy hónapon keresztül ismétlődnek.

Ha a regisztráció sikeres, vagy ha letelik az egy hónap (amelyik előbb megtörténik), törlődik a célszámítógépről az automatikus Intune-regisztrálási feladat, a **WindowsIntuneEnrollPending** beállításkulcs és a fióktanúsítvány.

## <a name="instruct-users-to-selfenroll"></a>A felhasználók felkérése önálló regisztrálásra

Az Intune-ügyfélszoftver a [Munkahelyi portál webhelyen](http://portal.manage.microsoft.com) telepíthető. Ha a portál észleli, hogy az eszköz egy Windows rendszerű számítógép, a rendszer megkéri a felhasználót, hogy regisztrálja a számítógépet az Intune-szoftverügyfél letöltésével. A letöltést követően a felhasználók a szoftver telepítésével vonhatják be a felügyelet alá a számítógépet.

![Az Intune-portál kéri a felhasználót, hogy töltse le az Intune-szoftverügyfelet](../media/software-client-download.png)

## <a name="monitor-and-validate-successful-client-deployment"></a>A sikeres ügyféltelepítés figyelése és ellenőrzése
A következő eljárások egyikével figyelheti és ellenőrizheti az ügyfél sikeres telepítését.

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a>A kliensszoftver telepítésének ellenőrzése a Microsoft Intune felügyeleti konzolon

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) kattintson a **Csoportok** &gt; **Minden eszköz** &gt; **Minden számítógép** lehetőségre.

2.  A listában keresse meg az Intune szolgáltatással kommunikáló számítógépeket, vagy a **Keresés az eszközök között** mezőben megadva a számítógép nevét (vagy annak bármely részét) kereshet meg egy adott kezelt számítógépet.

3.  Vizsgálja meg a számítógép állapotát a konzol alsó ablaktábláján. Hárítsa el az esetleges hibákat.

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a>Az összes regisztrált számítógépet megjelenítő számítógépkészlet-jelentés létrehozása

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) kattintson a **Jelentések** &gt; **Számítógépleltár-jelentések** elemre.

2.  Az **Új jelentés létrehozása** lapon az összes mezőben hagyja meg az alapértelmezett értéket (kivéve ha szűrőket kíván alkalmazni), majd kattintson a **Jelentés megtekintése**lehetőségre.

3.  Ekkor egy új ablakban megjelenik a **Számítógépleltár-jelentés** lap, melyen az összes, az Intune szolgáltatásban sikeresen regisztrált számítógép látható.

    > [!TIP]
    > A jelentés bármely oszlopának fejlécére kattintva a lista az adott oszlop tartalma szerint rendezhető.


### <a name="see-also"></a>További információ
[Windows rendszerű számítógépek felügyelete a Microsoft Intune-nal](manage-windows-pcs-with-microsoft-intune.md)
[Az ügyfél beállításának hibaelhárítása](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


