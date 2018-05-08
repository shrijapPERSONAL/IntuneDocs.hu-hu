---
title: PKCS-tanúsítványok használata az Azure-beli Microsoft Intune-nal | Micrososft Docs
description: 'Nyíltkulcsú titkosításiszabvány- (PKCS-) tanúsítványok hozzáadása vagy létrehozása a Microsoft Intune-nal a következő lépésekben: gyökértanúsítvány exportálása, tanúsítványsablon konfigurálása, Microsoft Intune Tanúsítvány-összekötő letöltése és telepítése, eszközkonfigurációs profil létrehozása, PKCS-tanúsítványprofil létrehozása az Azure-ban és a saját hitelesítésszolgáltatónál'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61a190be2b4685030438988dab0d0134a8fa9f9b
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2018
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-tanúsítványok konfigurálása és használata az Intune-nal

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A tanúsítványok az olyan céges forrásokhoz történő hozzáférés hitelesítését és biztonságossá tételét szolgálják, mint a VPN és a saját WiFi hálózat. Ez a cikk a PKCS-tanúsítványok exportálását, majd Intune-profilhoz történő hozzáadását ismerteti. 

## <a name="requirements"></a>Követelmények

A PKCS-tanúsítványok Intune-beli használata előtt ellenőrizze, hogy rendelkezik-e az alábbi infrastruktúrával:

* Meglévő, konfigurált Active Directory tartományi szolgáltatások (AD DS) tartomány.
 
  Az AD DS telepítéséről és konfigurálásáról [Az AD DS tervezése és előkészítése](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) című témakörben talál további információt.

* Meglévő, konfigurált vállalati hitelesítésszolgáltató (CA).

  Az Active Directory tanúsítványszolgáltatások (AD CS) telepítéséről és konfigurálásáról a [Lépésenkénti útmutató az Active Directory tanúsítványszolgáltatásokhoz](https://technet.microsoft.com/library/cc772393) című témakörben talál további információt.

  > [!WARNING]
  > Az Intune követelményei szerint az AD CS-t vállalati hitelesítésszolgáltatóval, és nem önálló hitelesítésszolgáltatóval kell futtatni.

* Vállalati hitelesítésszolgáltatóhoz kapcsolódó ügyfél.
* Vállalati hitelesítésszolgáltatótól származó főtanúsítvány exportált másolata.
* Az Intune-portálról letöltött Microsoft Intune Tanúsítvány-összekötő (NDESConnectorSetup.exe).
* Microsoft Intune Tanúsítvány-összekötő (NDESConnectorSetup.exe) üzemeltetésére alkalmas Windows Server.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól

VPN-, WiFi- és egyéb erőforrással történő hitelesítéshez minden eszköz esetében fő vagy köztes hitelesítésszolgáltatói tanúsítványra van szükség. Az alábbi lépések ismertetik a szükséges tanúsítvány beszerzését a vállalati hitelesítésszolgáltatótól.

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyisson meg rendszergazdaként egy parancssort.
3. Exportálja a hitelesítésszolgáltatói főtanúsítványt (.cer) egy olyan helyre, ahol később hozzáférhet.

   Például:

4. Ha a varázsló befejeződött, még mielőtt bezárná, kattintson **Launch the Certificate Connector UI**(Certificate Connector felhasználói felületének indítása) lehetőségre.

   `certutil -ca.cert certnew.cer`

   További információkárt lásd: [Certutil-feladatok a tanúsítványok kezeléséhez](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyissa meg a **Hitelesítésszolgáltató** konzolt, majd kattintson a jobb gombbal a **Tanúsítványsablonok** elemre, és válassza a **Kezelés** lehetőséget.
3. Keresse meg a **Felhasználói** tanúsítványsablont, kattintson rá a jobb gombbal, majd válassza a **Sablon duplikálása** elemet. Ekkor megnyílik az **Új sablon tulajdonságai** terület.
4. A **Kompatibilitás** lapon: 
   * Állítsa a **Hitelesítésszolgáltató** beállítást **Windows Server 2008 R2** értékre.
   * Állítsa a **Tanúsítvány kezdeményezettje** beállítást **Windows 7 / Server 2008 R2** értékre.
5. Az **Általános** lapon:
   * Állítsa a **Sablon megjelenítendő neve** beállítást egy aktuális névre.

   > [!WARNING]
   > A **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*. Jegyezze fel a sablon nevét, mert később szüksége lesz rá.

6. A **Kérelmek kezelése** lapon válassza **A titkos kulcs exportálható** beállítást.
7. A **Titkosítás** lapon ellenőrizze, hogy a **Minimális kulcshossz** értéke 2048.
8. A **Tulajdonos neve** lapon válassza a **Kérelemben megadva** lehetőséget.
9. A **Bővítmények** lapon ellenőrizze, hogy az **Alkalmazásszabályzatok** területen láthatók-e a következő elemek: Titkosított fájlrendszer, Biztonságos e-mail, Ügyfél-hitelesítés.
    
      > [!IMPORTANT]
      > iOS-tanúsítványsablonok esetén a **Kiterjesztések** lapon frissítse a **Kulcshasználat** beállítást, és ügyeljen rá, hogy **Az aláírás igazolja az eredetet** jelölőnégyzet ne legyen bejelölve.

10. A **Biztonság** lapon vegye fel annak a kiszolgálónak a fiókját, amelyen telepíti a Microsoft Intune Tanúsítvány-összekötőt.
    * Adja meg a fiók számára az **Olvasás** és **Beléptetés** engedélyeket.
11. A tanúsítvány mentéséhez kattintson az **Alkalmaz**, majd az **OK** elemre.
12. Zárja be a **Tanúsítvány-sablonok konzolt**.
13. A **Hitelesítésszolgáltató** konzolon kattintson a jobb gombbal a **Tanúsítványsablonok**, az **Új**, majd a **Kiállítandó tanúsítványsablon** elemekre.
    * Válassza ki az iménti lépésekben létrehozott sablont, majd kattintson az **OK** elemre.
14. Ahhoz, hogy a kiszolgáló az Intune-ban regisztrált eszközök és felhasználók nevében kezelhesse a tanúsítványokat, kövesse az alábbi lépéseket:

    a. Kattintson a jobb gombbal a hitelesítésszolgáltatóra, majd kattintson a **Tulajdonságok** elemre.

    b. A biztonság lapon vegye fel annak a kiszolgálónak a fiókját, amelyen futtatja a Microsoft Intune Tanúsítvány-összekötőt.
      * A fiók számára adja meg a **Tanúsítványok kiadása és kezelése** és a **Tanúsítványkérés** engedélyeket.
15. Jelentkezzen ki a vállalati hitelesítésszolgáltatóból.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>A Microsoft Intune Tanúsítvány-összekötő letöltése, telepítése és konfigurálása

![ConnectorDownload][ConnectorDownload]

1. Az [Azure Portalon](https://portal.azure.com) válassza a **Minden szolgáltatás** lehetőséget, és szűrjön az **Intune**-ra. Kattintson a **Microsoft Intune** elemre, majd válassza az **Eszközkonfiguráció** lehetőséget. 
2. Kattintson a **Hitelesítésszolgáltató**, majd a **Hozzáadás** elemre, és válassza a **Töltse le a tanúsítvány-összekötő fájlját** lehetőséget. Mentse a letöltést egy olyan helyre, amelyhez hozzá tud férni a telepítéshez használt kiszolgálón. 
3. Jelentkezzen be ezen a kiszolgálón, és futtassa a telepítőt: 

    1. Fogadja el az alapértelmezett helyet. A telepítő az összekötőt a `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe` helyen telepíti.
    2. A Telepítőbeállítás oldalon kattintson a **PFX terjesztése**, majd a **Tovább** elemre.
    3. Indítsa el a **telepítést**, és várja meg, amíg befejeződik.
    4. Ha elkészült, jelölje be az **Intune-összekötő indítása** feliratú jelölőnégyzetet, majd kattintson a **Befejezés** elemre.

4. Az NDES-összekötő ablaknak ekkor a **Regisztráció** lapra kell nyílnia. Az Intune-hoz való kapcsolódás engedélyezéséhez kattintson a **Bejelentkezés** elemre, és adjon meg egy globális rendszergazdai engedélyekkel rendelkező fiókot.
5. A **Speciális** lapon kijelölve hagyhatja a **Use this computer's SYSTEM account (default)** (A számítógép SYSTEM fiókjának használata (alapértelmezett)) feliratú választógombot.
6. Kattintson az **Alkalmaz**, majd a **Bezárás** gombra.
7. Lépjen vissza az Azure Portalra (**Intune** > **Eszközkonfiguráció** > **Hitelesítésszolgáltató**). Néhány perc elteltével egy zöld pipajel jelenik meg, és a **Kapcsolat állapota** területen az **Aktív** szó látható. Az összekötő kiszolgáló mostantól kapcsolatba tud lépni az Intune-nal.

## <a name="create-a-device-configuration-profile"></a>Eszközkonfigurációs profil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Nyissa meg az **Intune**, majd az **Eszközkonfiguráció**, és végül a **Profilok** lapot, majd kattintson a **Profil létrehozása** elemre.

   ![NavigateIntune][NavigateIntune]

3. Adja meg a következő tulajdonságokat:
   * **Név** a profil számára
   * Igény szerint hozzáadhat egy leírást
   * **Platform**, amelyen telepíteni kell a profilt
   * A **Profiltípust** állítsa **Megbízható tanúsítványra**

4. Nyissa meg a **Beállítások** lapot, és adja meg a korábban exportált hitelesítésszolgáltatói főtanúsítvány .cer fájlját.

   > [!NOTE]
   > A **3. lépésben** választott platformtól függően lehetősége lehet **Céltárolót** választani a tanúsítvány számára.

   ![ProfileSettings][ProfileSettings]

5. A profil mentéséhez kattintson az **OK**, majd a **Létrehozás** elemre.
6. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS-tanúsítványprofil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Nyissa meg az **Intune**, majd az **Eszközkonfiguráció**, és végül a **Profilok** lapot, majd kattintson a **Profil létrehozása** elemre.
3. Adja meg a következő tulajdonságokat:
   * **Név** a profil számára
   * Igény szerint hozzáadhat egy leírást
   * **Platform**, amelyen telepíteni kell a profilt
   * A **Profiltípust** állítsa **PKCS-tanúsítványra**
4. Nyissa meg a **Beállítások** lapot, és adja meg a következő tulajdonságokat:
   * **Megújítási küszöb (%)** – Az ajánlott érték 20%.
   * **Tanúsítvány érvényességi időtartama** – Ha nem módosította a tanúsítványsablont, akkor a megadott beállítás valószínűleg egy év.
   * **Hitelesítésszolgáltató** – A vállalati hitelesítésszolgáltató belső teljes tartományneve (FQDN).
   * **Hitelesítésszolgáltató neve** – A vállalati hitelesítésszolgáltató neve, ami nem feltétlenül azonos az előző elemmel.
   * **Tanúsítványsablon neve** – A korábban létrehozott sablon neve. Emlékeztető: a **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*.
   * **Tulajdonos nevének formátuma** – Ennél a beállításnál, ha nincs eltérő követelmény, a **Köznapi nevet** adja meg.
   * **Tulajdonos alternatív neve** – Ennél a beállításnál, ha nincs eltérő követelmény, az **Egyszerű felhasználónevet (UPN)** adja meg.
   * **Kibővített kulcshasználat** – Ha a jelen cikk [Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál](#configure-certificate-templates-on-the-certification-authority) szakaszának 10. lépésében ismertetett alapértelmezett beállításokat használta, adja meg a következő **Előre meghatározott értékeket** a kijelölt területről:
      * **Általános felhasználás**
      * **Ügyfél-hitelesítés**
      * **Biztonságos e-mail**
   * **Főtanúsítvány** – (Androidos profilokhoz) A jelen cikk [Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól](#export-the-root-certificate-from-the-enterprise-ca) szakaszának 3. lépésében exportált .cer fájl.

5. A profil mentéséhez kattintson az **OK**, majd a **Létrehozás** elemre.
6. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Nyissa meg az Intune oldalt az Azure Portalon, és hozzon létre egy új profilt egy megbízható tanúsítványhoz"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Hozzon létre egy profilt, és töltsön fel egy megbízható tanúsítványt"
[ConnectorDownload]: ./media/certificates-download-connector.png "Töltse le a tanúsítvány-összekötőt az Azure Portalról"  
