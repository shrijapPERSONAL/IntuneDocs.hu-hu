---
title: "Alkalmazások közvetlen telepítése Windows és Windows Phone rendszerre"
description: "A cikkből megtudhatja, hogyan írhatja alá az üzleti alkalmazásokat, hogy az Intune segítségével telepíthesse őket."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
ms.custom: intune-classic
ms.openlocfilehash: 2a8754d684896f2c945e11ed0fc2577114459069
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/15/2017
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Üzleti alkalmazások aláírása, hogy telepíteni lehessen őket Windows-eszközökre az Intune segítségével

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune-rendszergazdaként telepíthet üzleti alkalmazásokat (köztük a Munkahelyi portál alkalmazást) Windows és Windows 10 Mobile rendszerű eszközökre. Ahhoz, hogy .appx vagy .xap alkalmazásokat telepíthessen Windows 10 vagy a Windows 10 Mobile rendszerű eszközökre, vagy bármilyen üzleti alkalmazást telepíthessen Windows 8.1 vagy Windows Phone 8.1 rendszerű eszközökre, **be kell szereznie a Symantec vállalati mobil-kódaláíró tanúsítványt**. Az ilyen Windows-eszközökön csak a Symantec aláírásával ellátott alkalmazások minősülnek megbízhatónak. A Windows 10-alkalmazások és az „univerzális” alkalmazások esetében használhatja saját hitelesítésszolgáltatóját. Ez a tanúsítvány az alábbiakhoz szükséges:

-   A Munkahelyi portál aláírása, hogy telepíteni lehessen a Windows rendszerű számítógépekre, Windows 10 Mobile rendszerű eszközökre és a Windows Phone rendszerű eszközökre

-   A cég üzleti alkalmazásainak aláírása, hogy az Intune telepíthesse őket a Windows-eszközökre

Az alábbi lépésekkel beszerezheti a szükséges tanúsítványokat, és aláírhatja az alkalmazásokat. Regisztrálnia kell Microsoft-fejlesztőként, majd vásárolnia kell egy Symantec-tanúsítványt.


1. **Regisztrálás Microsoft-fejlesztőként**<br>
   [A Microsoft-fejlesztőként való regisztrálást](http://go.microsoft.com/fwlink/?LinkId=268442) azokkal a céges fiókadatokkal végezheti el, amelyeket bejelentkezéskor használt a céges fiók vásárlásakor. Ezt a kérelmet engedélyeznie kell egy vállalati tisztviselőnek ahhoz, hogy kódaláíró tanúsítványt kaphasson.

2. **Céges Symantec-tanúsítvány beszerzése**<br>
  Vásároljon tanúsítványt a [Symantec webhelyéről](http://go.microsoft.com/fwlink/?LinkId=268441) Symantec-azonosítója használatával. A tanúsítvány megvásárlása után a Microsoft-fejlesztőként való regisztráláskor kijelölt munkahelyi jóváhagyó kap egy e-mailt, amely a tanúsítványkérelem jóváhagyását kéri. A Symantec-tanúsítványra vonatkozó követelményekről a [Miért szükséges a Windows Phone-telefonok kezeléséhez Symantec-tanúsítvány?](https://technet.microsoft.com/library/dn764959.aspx#BKMK_Symantec) című részben talál további információkat. „Gyakori kérdések a Windows Phone rendszerű mobileszközök kezelésével kapcsolatban” szakaszban.

3.  **Tanúsítványok importálása**<br>
    Amint jóváhagyják a kérelmét, kapni fog egy e-mailt, amely a tanúsítványok importálására vonatkozó útmutatást tartalmaz. A tanúsítványok importálásához kövesse az e-mailben szereplő utasításokat.

4.  **Az importált tanúsítványok ellenőrzése**<br>
    A tanúsítványimportálás helyes voltának ellenőrzéséhez nyissa meg a **Tanúsítványkezelő** beépülő modult, kattintson a jobb gombbal a **Tanúsítványok** elemre, és válassza a **Tanúsítványok keresése** parancsot. A **Tartalmazza** mezőben adja meg a „Symantec” kifejezést, majd kattintson a **Keresés most**lehetőségre. Az eredmények között meg kell jelennie az importált tanúsítványoknak.

    ![A Symantec-tanúsítvány megkeresése](./media/wit.gif)

5. **Aláíró tanúsítvány exportálása**<br>
    Miután ellenőrizte, hogy telepítve vannak-e a tanúsítványok, exportálhatja a vállalati portál aláírásához szükséges PFX-fájlt. Válassza ki a Symantec-tanúsítványt, amelynek **Felhasználási célja** a „kód aláírása”. Kattintson jobb gombbal a kódaláíró tanúsítványra, majd válassza az **Exportálás** lehetőséget.

    ![Aláíró tanúsítvány exportálása](./media/wit-walk-cert2.gif)

    A **Tanúsítványexportáló varázslóban**válassza az **Igen, a titkos kulcs exportálását választom** lehetőséget, majd kattintson a **Tovább**gombra. Válassza ki a **Személyes információcsere - PKCS #12 (.PFX)** lehetőséget, majd jelölje be a **Minden tanúsítvány felvétele a tanúsítványláncba, ha lehetséges** jelölőnégyzetet. Fejezze be a varázslót. További tudnivalókért lásd: [Tanúsítvány exportálása a titkos kulccsal](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Az alkalmazás feltöltése az Intune-ba**<br>
    Töltse fel az alkalmazás aláírt fájlját és a kódaláíró tanúsítványt, így elérhetővé téve az alkalmazást a végfelhasználók számára.

    1.  Az Intune-portálon kattintson a **Felügyelet** &gt; **Windows Phone** lehetőségre.

    2.  Kattintson az **Aláírt alkalmazásfájl feltöltése** lehetőségre, és jelentkezzen be az Intune-rendszergazdai azonosítójával.

    3.  Adja hozzá az exportált tanúsítványfájlt (.pfx) a **Kódaláíró tanúsítvány** elemhez, és hozzon létre egy jelszót a tanúsítványhoz.

    4.  Fejezze be a varázslót.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Példa: A Munkahelyi portál alkalmazás letöltése, aláírása és telepítése Windows-eszközökre

A Windows-eszközökre (a Windows Phone-telefonokat és a Windows 10 Mobile rendszerű eszközöket is beleértve) az Intune-nal is telepítheti a Céges portál alkalmazást, nem kell a Microsoft Áruházból telepítenie. Ehhez le kell töltenie a Munkahelyi portál alkalmazást, és alá kell írnia a cég tanúsítványával.  Erre csak akkor van szükség, ha a felhasználók nem fogják igénybe venni a Vállalati portál alkalmazást, és Windows Phone 8.1-es telefonokra szeretné azt telepíteni.


1.  **A Vállalati portál alkalmazás letöltése**

    Ha az Intune segítségével szeretné telepíteni a Munkahelyi portál alkalmazást, töltse le a [Windows Phone 8.1 rendszerhez készült Microsoft Intune Munkahelyi portál alkalmazást](http://go.microsoft.com/fwlink/?LinkId=615799) a letöltőközpontból, és futtassa az önkicsomagoló (.exe) fájlt. Ez a fájl két fájlt tartalmaz:

    -   CompanyPortal.appx – a Windows Phone 8.1 rendszerhez készült vállalati portált telepítő alkalmazás

    -   WinPhoneCompanyPortal.ps1 – egy PowerShell-parancsprogram, amellyel aláírhatja a Vállalati portál alkalmazás fájlját, hogy az telepíthető legyen Windows Phone 8.1-es telefonokra

    Azt is megteheti, hogy letölti a Windows Phone 8.1-es vagy a Windows 10-es Céges portált (az offline licenccel rendelkező csomagot) a [Vállalati Microsoft Áruházból](http://businessstore.microsoft.com/). A Munkahelyi portál alkalmazást offline licenccel kell beszerezni, és az offline használatra megfelelő csomagot kell letölteni. A kínálatban a Windows 8 és a Windows Phone 8 platformra készültként megjelölt termékek valójában a 8.1-beli megfelelőjükre utalnak. Ennek az Intune-nal való végrehajtásáról bővebben [A Vállalati Microsoft Áruházban vásárolt alkalmazások kezelése](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune) című témakörben olvashat.

2.  **A Windows Phone SDK letöltése:** Töltse le a Windows Phone SDK 8.0-s verzióját] (http://go.microsoft.com/fwlink/?LinkId=615570), és telepítse a számítógépre. Az SDK az alkalmazásregisztrációs adatblokkok létrehozásához szükséges.

3.  **AETX-fájl létrehozása** Hozza létre az alkalmazásregisztrációs adatblokk .aetx kiterjesztésű fájlját a Symantec PFX-fájlból a Windows Phone SDK 8.0 részét képező AETGenerator.exe eszközzel. Az AETX-fájlok létrehozásával kapcsolatos útmutatást itt találja: [Alkalmazásregisztrációs adatblokk létrehozása a Windows Phone rendszerhez](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)

4.  **A Windows 8.1 rendszerhez készült Windows SDK letöltése** Töltse le és telepítse a [Windows Phone SDK-t](http://go.microsoft.com/fwlink/?LinkId=613525) (http://go.microsoft.com/fwlink/?LinkId=613525). Ügyeljen arra, hogy a Vállalati portál alkalmazás PowerShell-parancsprogramja az alapértelmezett telepítési helyet ( `${env:ProgramFiles(x86)}\Windows Kits\8.1`) használja. Ha máshová telepíti, meg kell adnia a helyet egy parancsmag-paraméterben.

5.  **Az alkalmazás kódjának aláírása a PowerShell használatával** A telepített Windows SDK-t és a Symantec Enterprise Mobile Code Signing Certificate tanúsítványt tartalmazó gazdagépről nyissa meg a **Windows PowerShell** alkalmazást rendszergazdaként, keresse meg a Sign-WinPhoneCompanyPortal.ps1 fájlt, és futtassa a parancsprogramot.

    **1. példa**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    Ebben a példában a CompanyPortal.appx fájl lesz aláírva a C:\temp\ mappában, így létrejön a CompanyPortalEnterpriseSigned.appx fájl. A program az 1234 PFX-jelszót használja, a gyártó azonosítóját pedig a PFX-fájlból olvassa be. Emellett beolvassa a vállalati azonosítót is a cert.aetx fájlból.

    **2. példa**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    Ebben a példában a CompanyPortal.appx fájl lesz aláírva a C:\temp\ mappában, így létrejön a CompanyPortalEnterpriseSigned.appx fájl. A program az 1234 PFX-jelszót, valamint a megadott gyártóazonosítót használja.

    **Paraméterek:**

    -   `-InputAppx` – a CompanyPortal.appx fájl helyi elérési útja aposztrófok között. Például: 'C:\temp\CompanyPortal.appx'.

    -   `-OutputAppx` – az aláírt Vállalati portál alkalmazás helyi elérési útja és fájlneve aposztrófok között. Például: 'C:\temp\CompanyPortalEnterpriseSigned.appx'.

    -   `-PfxFilePath` – a Symantec-tanúsítvány exportált PFX-fájljának helyi elérési útja és fájlneve. Például: 'C:\signing\cert.pfx'.

    -   `-PfxPassword` – a PFX-fájl aláírásához használt jelszó aposztrófok között. Például: '1234'.

    -   `-AetxPath` – a vállalati azonosító beolvasásához használt .aetx fájl helyi elérési útja, ha nincs megadva az EnterpriseId argumentum. Ezt az argumentumot vagy az EnterpriseId argumentumot kötelező megadni. Például: 'C:\signing\cert.aetx'.

    -   `-PublisherId` – a vállalat gyártóazonosítója. Ha nincs megadva, a program a Symantec Enterprise Mobile Code Signing Certificate tanúsítvány Subject (Tulajdonos) mezőjének értékét használja. Például: 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'.

    -   `-SdkPath` – a Windows 8.1-hez készült Windows SDK gyökérmappájának elérési útja. Ezt az argumentumot nem kötelező megadni, alapértelmezett értéke pedig ${env:ProgramFiles(x86)}\Windows Kits\8.1.

    -   `-EnterpriseId` – a vállalat azonosítója. Ezt az argumentumot vagy az AetxPath argumentumot kötelező megadni. Ha nincs megadva ez az argumentum, a program az AETX-fájlból olvassa be a vállalat azonosítóját. Például: 1000000001.

6.  Telepítse a Windows Phone 8.1-es Vállalati portál alkalmazást (SSP.appx). További útmutatást a [Windows Phone rendszerű üzletági (LOB) alkalmazások hozzáadása](lob-apps-windows-phone.md) ([klasszikus konzol](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune)) című témakörben talál.

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>A Symantec vállalati kódaláíró tanúsítvány megújítása

A Windows és Windows Phone rendszerű mobilalkalmazások telepítésére szolgáló Symantec-tanúsítványt rendszeresen meg kell újítani.

1.  Keressen a Symantec által küldött, megújításra vonatkozó e-mailt körülbelül két héttel a tanúsítvány lejárta előtt. Ez az e-mail tartalmazza a Symantec a vállalati tanúsítvány megújítására vonatkozó utasításait.

    A Symantec-tanúsítványokkal kapcsolatos további tudnivalókért keresse fel a [www.symantec.com](http://www.symantec.com) webhelyet, vagy hívja az 1-877-438-8776 vagy az 1-650-426-3400 telefonszámot.

2.  Nyissa meg a webhelyet (például: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)), és jelentkezzen be a tanúsítványhoz tartozó Symantec-gyártóazonosítóval és e-mail címmel. Fontos, hogy ugyanazon a számítógépen indítása el a megújítást, amelyen le fogja tölteni a tanúsítványt.

3.  Miután megkapta a jóváhagyást a megújításhoz és kifizette azt, töltse le a tanúsítványt.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>A frissített alkalmazások telepítése az üzleti alkalmazások számára

1.  Írja alá az üzleti alkalmazás legújabb verzióját.

2.  Nyissa meg az Intune-konzolt, majd a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows Phone** szakaszban kattintson az **Aláírt alkalmazás feltöltése** gombra.

3.  Töltse fel az imént aláírt Vállalati portál alkalmazást. Az újonnan aláírt SSP.xap fájlra és a Symantectől kapott új .PFX-fájlra, vagy az ezzel az új .PFX-fájllal létrehozott alkalmazásregisztrációs adatblokkra lesz szüksége.

4.  A feltöltés befejeződése után távolítsa el a vállalati portál régi verzióját a **Szoftverek**  munkaterületről.

5.  Írja alá az összes új és az esetlegesen frissített üzletági alkalmazásokat az új tanúsítvánnyal. A meglévő alkalmazásokat nem kell újra ellátni aláírással és újratelepíteni.

## <a name="manually-deploy-windows-10-company-portal-app"></a>A Windows 10-es Céges portál alkalmazás manuális telepítése
A Windows 10-es Céges portál alkalmazást akkor is telepítheti manuálisan, közvetlenül az Intune-ból, ha az Intune-t nem integrálta a Vállalati Microsoft Áruházzal.

 > [!NOTE]
 > Ha ezt a lehetőséget választja, manuális frissítést kell végrehajtania minden alkalommal, amikor új frissítés válik elérhetővé az alkalmazáshoz.

1. Jelentkezzen be [Vállalati Microsoft Áruház](https://www.microsoft.com/business-store) fiókjába, és szerezze be a Céges portál alkalmazás **offline licencű** verzióját.  
2. Miután beszerezte az alkalmazást, válassza ki a **Készlet** lapon.  
3. A **Platform** listából válassza ki a **Windows 10 minden eszközre** lehetőséget, majd válassza ki a megfelelő **architektúrát**, és töltse le az alkalmazást. Ehhez az alkalmazáshoz nincs szükség alkalmazás-licencfájlra.
![Kép a Windows 10 minden eszközre, X86 architektúrával csomag letöltési részleteiről](./media/Win10CP-all-devices.png)
4. Töltse le a „Szükséges keretrendszer” cím alatt található összes csomagot. Ezt az x86, az x64 és az ARM architektúrákkal kell elvégezni, összesen 9 csomaggal, ahogy az alábbi ábrán látható.

![Kép a letöltendő függőségi fájlokról ](./media/Win10CP-dependent-files.png)
5. Mielőtt feltöltené a Céges portál alkalmazást az Intune-ra, hozzon létre egy mappát (pl. C:&#92;Céges portál) a következőképpen felépített csomagokkal:
  1. Helyezze el a Céges portál csomagot a C:\Céges portál helyen. Ugyanitt hozzon létre egy Függőségek almappát is.  
  ![APPXBUN fájllal mentett Függőségek mappa képe](./media/Win10CP-Dependencies-save.png)
  2. Helyezze el a kilenc függőségcsomagot a Függőségek mappában.  
  Ha a függőségeket nem ebben a formátumban helyezi el, az Intune nem tudja majd felismerni és feltölteni őket a csomag feltöltésekor, így a folyamat sikertelen lesz a következő hiba miatt.  
  ![A szoftver telepítőjéhez tartozó Windows-alkalmazás nem található az alkalmazás mappájában. Továbbra is létrehozhatja és telepítheti az alkalmazást, de az nem fog futni addig, amíg hozzá nem adja a hiányzó Windows alkalmazás-függőséget.](./media/Win10CP-error-message.png)
6. Lépjen vissza az Intune-ba, és töltse fel a Céges portál alkalmazást új alkalmazásként. Telepítse szükséges alkalmazásként a kívánt felhasználói célcsoport számára.  

Itt talál további információkat arról, hogy az Intune miképpen kezeli az univerzális alkalmazások függőségeit: [appxbundle telepítése függőségekkel a Microsoft Intune MDM-en keresztül](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Hogyan frissítsem a Céges portált olyan felhasználói eszközökön, amelyeken telepítve vannak az áruházból származó régebbi alkalmazások?
Ha a felhasználók már telepítették az áruházból a Windows 8.1-es vagy a Windows Phone 8.1-es Céges portál alkalmazást, az eszközöknek automatikusan, saját vagy felhasználói beavatkozás nélkül is frissíteniük kell az új verzióra. Ha a frissítés elmarad, kérje meg a felhasználókat, hogy ellenőrizzék, engedélyezték-e az áruház-alkalmazások automatikus frissítését az eszközükön.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hogyan frissítsem a közvetlen telepítésű, Windows 8.1-es Céges portál alkalmazást Windows 10-es Céges portál alkalmazásra?
A javasolt áttelepítési út a Windows 8.1-es Céges portál alkalmazás telepítési műveletének átállítása az „Eltávolítás” lehetőségre, ami törli az alkalmazás telepítését. Miután ez megtörtént, a Windows 10-es Céges portál alkalmazás a fenti lehetőségek bármelyikével telepíthető lesz.  

Ha közvetlenül kell telepíteni az alkalmazást, és a Windows 8.1-es Céges portált a Symantec Tanúsítvány aláírása nélkül telepítette, a frissítéshez kövesse az Intune-on keresztül történő közvetlen telepítés fentebb leírt lépéseit.

Ha közvetlenül kell telepíteni az alkalmazást, és a Windows 8.1-es Céges portált a Symantec kódaláíró tanúsítvány aláírásával telepítette, kövesse az alábbi részben olvasható lépéseket.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hogyan frissítsem az aláírt és közvetlen telepítésű Windows Phone 8.1-es Céges portál alkalmazást vagy Windows 8.1-es Céges portál alkalmazást a Windows 10-es Céges portál alkalmazásra?
A javasolt áttelepítési út a Windows Phone 8.1-es Céges portál alkalmazás vagy a Windows 8.1-es Céges portál alkalmazás telepítési műveletének átállítása az „Eltávolítás” lehetőségre, ami törli az alkalmazás telepítését. Miután ez megtörtént, a Windows 10-es Céges portál alkalmazás a szokásos módon telepíthető.  

Ellenkező esetben a frissítési út betartásának biztosításához a Windows 10-es Céges portál alkalmazás frissítésére és aláírására van szükség.  

Az így aláírt és telepített Windows 10-es Céges portál alkalmazás esetében mindig meg kell ismételni ezt a folyamatot, ha az áruházban elérhetővé válik az alkalmazás új frissítése. Az alkalmazás nem frissül automatikusan az áruház frissítésekor.  

Itt ismertetjük az alkalmazás aláírásának és telepítésének ezt a módját:

1. Töltse le a Microsoft Intune Windows 10-es Céges portál alkalmazás aláírása parancsfájlt a [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) oldalról.  A parancsfájlhoz olyan gazdagépre van szükség, amelyen telepítve van a Windows 10-hez készült Windows SDK. A Windows 10-hez készült Windows SDK letöltéséhez látogasson el a [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) oldalra.
2. Töltse le a Windows 10-es Céges portál alkalmazást a Vállalati Microsoft Áruházból a fenti útmutató szerint.  
3. Futtassa a parancsfájlt azokkal a bemeneti paraméterekkel, amelyek a Windows 10-es Céges portál alkalmazás aláírásához használt parancsfájl fejlécén találhatók (alább kivonatolva). A függőségeket nem kell hozzáadni a parancsprogramhoz. Csak akkor van rájuk szükség, amikor éppen folyamatban van az alkalmazás feltöltése az Intune felügyeleti konzolra.

|Paraméter | Leírás|
| ------------- | ------------- |
|InputWin10AppxBundle |Az appxbundle forrásfájl elérési útja |
|OutputWin10AppxBundle |Az aláírt appxbundle fájl kimeneti útja.  Win81Appx A Windows 8.1 vagy Windows Phone 8.1 Céges portál (.APPX) fájl elérési útja.|
|PfxFilePath |A Symantec vállalati mobil-kódaláíró tanúsítvány (.PFX) fájl elérési útja. |
|PfxPassword| A Symantec vállalati mobil-kódaláíró tanúsítvány jelszava. |
|PublisherId |A vállalat gyártóazonosítója. Ha nincs megadva, a program a Symantec Enterprise Mobile Code Signing Certificate tanúsítvány Subject (Tulajdonos) mezőjének értékét használja.|
|SdkPath | A Windows 10-hez készült Windows SDK gyökérmappájának elérési útja. Ezt az argumentumot nem kötelező megadni, és az alapértelmezett értéke ${env:ProgramFiles(x86)}\Windows Kits\10|
A parancsfájl kimenete a futtatás végeztével a Windows 10-es Céges portál alkalmazás aláírt verziója lesz. Ekkor az Intune-on keresztül telepítheti az alkalmazás aláírt verzióját LOB-alkalmazásként, ami frissíteni fogja a jelenleg telepített verziókat erre a új alkalmazásra.  
