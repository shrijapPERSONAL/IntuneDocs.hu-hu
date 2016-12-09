---
title: "Alkalmazások közvetlen telepítése Windows és Windows Phone rendszerre | Microsoft Intune"
description: "A cikkből megtudhatja, hogyan írhatja alá az üzleti alkalmazásokat, hogy az Intune segítségével telepíthesse őket."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 938e3a1914f379d115bf24ebd7d990f6e1d319a9


---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Üzleti alkalmazások aláírása, hogy telepíteni lehessen őket Windows-eszközökre az Intune segítségével

Intune-rendszergazdaként telepíthet üzleti alkalmazásokat (köztük a Munkahelyi portál alkalmazást) Windows és Windows 10 Mobile rendszerű eszközökre. Ahhoz, hogy .appx vagy .xap alkalmazásokat telepíthessen Windows 10 vagy a Windows 10 Mobile rendszerű eszközökre, vagy bármilyen üzleti alkalmazást telepíthessen Windows 8.1 vagy Windows Phone 8.1 rendszerű eszközökre, **be kell szereznie a Symantec vállalati mobil-kódaláíró tanúsítványt**. Az ilyen Windows-eszközökön csak a Symantec aláírásával ellátott alkalmazások minősülnek megbízhatónak. A Windows 10-alkalmazások és az „univerzális” alkalmazások esetében használhatja saját hitelesítésszolgáltatóját. Ez a tanúsítvány az alábbiakhoz szükséges:

-   A Munkahelyi portál aláírása, hogy telepíteni lehessen a Windows rendszerű számítógépekre, Windows 10 Mobile rendszerű eszközökre és a Windows Phone rendszerű eszközökre

-   A cég üzleti alkalmazásainak aláírása, hogy az Intune telepíthesse őket a Windows-eszközökre

Az alábbi lépésekkel beszerezheti a szükséges tanúsítványokat, és aláírhatja az alkalmazásokat. Szüksége lesz egy fiókra a Windows Phone-fejlesztői központhoz, majd vásárolnia kell egy Symantec-tanúsítványt.


1. **Csatlakozás a Windows Phone-fejlesztői központhoz**<br>
   A munkahelyi fiók megvásárlásához bejelentkezéskor a céges fiókadatok megadásával csatlakozzon a [Windows Phone-fejlesztői központhoz](http://go.microsoft.com/fwlink/?LinkId=268442) . Ezt a kérelmet engedélyeznie kell egy vállalati tisztviselőnek ahhoz, hogy kódaláíró tanúsítványt kaphasson.

2. **Céges Symantec-tanúsítvány beszerzése**<br>
  Vásároljon tanúsítványt a [Symantec webhelyéről](http://go.microsoft.com/fwlink/?LinkId=268441) Symantec-azonosítója használatával. A tanúsítvány megvásárlása után a Windows Phone-fejlesztői központban regisztrált fiókjában kijelölt munkahelyi jóváhagyó kap egy e-mailt, amely a tanúsítványkérelem jóváhagyását kéri. A Symantec-tanúsítványra vonatkozó követelményekről a [Miért szükséges a Windows Phone-telefonok kezeléséhez Symantec-tanúsítvány?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) című részben talál további információkat. „Gyakori kérdések a Windows Phone rendszerű mobileszközök kezelésével kapcsolatban” szakaszban.

3.  **Tanúsítványok importálása**<br>
    Amint jóváhagyják a kérelmét, kapni fog egy e-mailt, amely a tanúsítványok importálására vonatkozó útmutatást tartalmaz. A tanúsítványok importálásához kövesse az e-mailben szereplő utasításokat.

4.  **Az importált tanúsítványok ellenőrzése**<br>
    A tanúsítványimportálás helyes voltának ellenőrzéséhez nyissa meg a **Tanúsítványkezelő** beépülő modult, kattintson a jobb gombbal a **Tanúsítványok** elemre, és válassza a **Tanúsítványok keresése** parancsot. A **Tartalmazza** mezőben adja meg a „Symantec” kifejezést, majd kattintson a **Keresés most**lehetőségre. Az eredmények között meg kell jelennie az importált tanúsítványoknak.

    ![A Symantec-tanúsítvány megkeresése](./media/wit.gif)

5. **Aláíró tanúsítvány exportálása**<br>
    Miután ellenőrizte, hogy telepítve vannak-e a tanúsítványok, exportálhatja a Munkahelyi portál aláírásához szükséges PFX-fájlt. Válassza ki azt a Symantec-tanúsítványt, amelynek **Felhasználási célja** a következő: „kód aláírása”. Kattintson jobb gombbal a kódaláíró tanúsítványra, majd válassza az **Exportálás** lehetőséget.

    ![Aláíró tanúsítvány exportálása](./media/wit-walk-cert2.gif)

    A **Tanúsítványexportáló varázslóban**válassza az **Igen, a titkos kulcs exportálását választom** lehetőséget, majd kattintson a **Tovább**gombra. Válassza ki a **Személyes információcsere - PKCS #12 (*.PFX)** lehetőséget, majd jelölje be a **Minden tanúsítvány felvétele a tanúsítványláncba, ha lehetséges** jelölőnégyzetet. Fejezze be a varázslót. További tudnivalókért lásd: [Tanúsítvány exportálása a titkos kulccsal](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Az alkalmazás feltöltése az Intune-ba**<br>
    Töltse fel az alkalmazás aláírt fájlját és a kódaláíró tanúsítványt, így elérhetővé téve az alkalmazást a végfelhasználók számára.

    1.  Az [Intune felügyeleti konzoljában](http://manage.microsoft.com) válassza a **Felügyelet** &gt; **Windows Phone** lehetőséget.

    2.  Kattintson az **Aláírt alkalmazásfájl feltöltése** lehetőségre, és jelentkezzen be az Intune-rendszergazdai azonosítójával.

    3.  Adja hozzá az exportált tanúsítványfájlt (.pfx) a **Kódaláíró tanúsítvány** elemhez, és hozzon létre egy jelszót a tanúsítványhoz.

    4.  Fejezze be a varázslót.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Példa: A Munkahelyi portál alkalmazás letöltése, aláírása és telepítése Windows-eszközökre

A Windows-eszközökre (a Windows Phone és a Windows 10 Mobile rendszerű eszközöket is beleértve) az Intune-nal is telepítheti a Munkahelyi portál alkalmazást, nem kell a Windows Áruházból telepítenie. Ehhez le kell töltenie a Munkahelyi portál alkalmazást, és alá kell írnia a cég tanúsítványával.  Erre csak akkor van szükség, ha a felhasználók nem fogják igénybe venni a Vállalati portál alkalmazást, és Windows Phone 8.1-es telefonokra szeretné azt telepíteni.


1.  **A Vállalati portál alkalmazás letöltése**

    Ha az Intune segítségével szeretné telepíteni a Munkahelyi portál alkalmazást, töltse le a [Windows Phone 8.1 rendszerhez készült Microsoft Intune Munkahelyi portál alkalmazást](http://go.microsoft.com/fwlink/?LinkId=615799) a letöltőközpontból, és futtassa az önkicsomagoló (.exe) fájlt. Ez a fájl két fájlt tartalmaz:

    -   CompanyPortal.appx – a Windows Phone 8.1 rendszerhez készült vállalati portált telepítő alkalmazás

    -   WinPhoneCompanyPortal.ps1 – egy PowerShell-parancsprogram, amellyel aláírhatja a Vállalati portál alkalmazás fájlját, hogy az telepíthető legyen Windows Phone 8.1-es telefonokra

    Azt is megteheti, hogy letölti a Windows Phone 8.1 vagy a Windows 10 Munkahelyi portált (az offline licenccel rendelkező csomagot) a [Vállalati Windows Áruházból](http://businessstore.microsoft.com/). A Munkahelyi portál alkalmazást offline licenccel kell beszerezni, és az offline használatra megfelelő csomagot kell letölteni. A kínálatban a Windows 8 és a Windows Phone 8 platformra készültként megjelölt termékek valójában a 8.1-beli megfelelőjükre utalnak. Ennek Intune-nal való végrehajtásáról bővebben [A Vállalati Windows Áruházban vásárolt alkalmazások kezelése](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) című témakörben olvashat.

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

6.  Telepítse a Windows Phone 8.1-es Vállalati portál alkalmazást (SSP.appx). További útmutatást az [Alkalmazások telepítése a Microsoft Intune-ban](deploy-apps-in-microsoft-intune.md) című témakörben találhat.

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>A Symantec vállalati kódaláíró tanúsítvány megújítása

A Windows és Windows Phone rendszerű mobilalkalmazások telepítésére szolgáló Symantec-tanúsítványt rendszeresen meg kell újítani.

1.  Keressen a Symantec által küldött, megújításra vonatkozó e-mailt körülbelül két héttel a tanúsítvány lejárta előtt. Ez az e-mail tartalmazza a Symantec a vállalati tanúsítvány megújítására vonatkozó utasításait.

    A Symantec-tanúsítványokkal kapcsolatos további tudnivalókért keresse fel a [www.symantec.com](http://www.symantec.com) webhelyet, vagy hívja az 1-877-438-8776 vagy az 1-650-426-3400 telefonszámot.

2.  Nyissa meg a webhelyet (például: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)), és jelentkezzen be a tanúsítványhoz tartozó Symantec-gyártóazonosítóval és e-mail címmel. Fontos, hogy ugyanazon a számítógépen indítása el a megújítást, amelyen le fogja tölteni a tanúsítványt.

3.  Miután megkapta a jóváhagyást a megújításhoz és kifizette azt, töltse le a tanúsítványt.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>A frissített alkalmazások telepítése az üzleti alkalmazások számára

1.  Írja alá az üzleti alkalmazás legújabb verzióját.

2.  Nyissa meg az [Intune felügyeleti konzolját](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com), majd a **Felügyelet** &gt; **Mobileszköz-kezelés** &gt; **Windows Phone** lapot, és kattintson az **Aláírt alkalmazás feltöltése** elemre.

3.  Töltse fel az imént aláírt Vállalati portál alkalmazást. Az újonnan aláírt SSP.xap fájlra és a Symantectől kapott új .PFX-fájlra, vagy az ezzel az új .PFX-fájllal létrehozott alkalmazásregisztrációs adatblokkra lesz szüksége.

4.  A feltöltés befejeződése után távolítsa el a vállalati portál régi verzióját a **Szoftverek**  munkaterületről.

5.  Írja alá az összes új és az esetlegesen frissített üzletági alkalmazásokat az új tanúsítvánnyal. A meglévő alkalmazásokat nem kell újra ellátni aláírással és újratelepíteni.



<!--HONumber=Dec16_HO2-->


