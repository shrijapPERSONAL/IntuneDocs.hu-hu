---
title: "PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal"
titleSuffix: Intune on Azure
description: "PKCS-tanúsítványok létrehozása és hozzárendelése az Intune-nal.\""
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b72c4899debb0bbb7cb755327606cad1e239c611
ms.sourcegitcommit: 6d5c919286b0e285f709d9b918624b927f99f979
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/11/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>PKCS-tanúsítványok konfigurálása és kezelése az Intune-nal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>Követelmények

A PKCS-tanúsítványok Intune-nal történő használatához a következő infrastruktúrával kell rendelkeznie:

* Meglévő, konfigurált Active Directory tartományi szolgáltatások (AD DS) tartomány.
 
  Ha további információra van szüksége az AD DS telepítéséről és konfigurálásáról, tekintse meg az [Az AD DS tervezése és kialakítása](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) című cikket.

* Meglévő, konfigurált vállalati hitelesítésszolgáltató (CA).

  Ha további információra van szüksége az Active Directory tanúsítványszolgáltatások (AD CS) telepítéséről és konfigurálásáról, tekintse meg a [Lépésenkénti útmutató az Active Directory tanúsítványszolgáltatásokhoz](https://technet.microsoft.com/library/cc772393) című cikket.

  > [!WARNING]
  > Az Intune követelményei szerint az AD CS-t vállalati hitelesítésszolgáltatóval, és nem önálló hitelesítésszolgáltatóval kell futtatni.

* Vállalati hitelesítésszolgáltatóhoz kapcsolódó ügyfél.
* Vállalati hitelesítésszolgáltatótól származó főtanúsítvány exportált másolata.
* Az Intune-portálról letöltött Microsoft Intune Tanúsítvány-összekötő (NDESConnectorSetup.exe).
* A Microsoft Intune Tanúsítvány-összekötő (NDESConnectorSetup.exe) üzemeltetésére alkalmas Windows Server.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól

VPN-, WiFi- és egyéb erőforrással történő hitelesítéshez minden eszköz esetében fő vagy köztes hitelesítésszolgáltatói tanúsítványra van szükség. Az alábbi lépések ismertetik a szükséges tanúsítvány beszerzését a vállalati hitelesítésszolgáltatótól.

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyisson meg rendszergazdaként egy parancssort.
3. Exportálja a hitelesítésszolgáltatói főtanúsítványt egy olyan helyre, ahol később hozzáférhet.

   Példa:

   `certutil -ca.cert certnew.cer`

   További információkárt lásd: [Certutil-feladatok a tanúsítványok kezeléséhez](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).


## <a name="configure-certificate-templates-on-the-certification-authority"></a>Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál

1. Jelentkezzen be a vállalati hitelesítésszolgáltatóhoz egy rendszergazdai jogosultságokkal rendelkező fiókkal.
2. Nyissa meg a **Hitelesítésszolgáltató** konzolt.
3. Kattintson a jobb gombbal a **Tanúsítványsablonok** elemre, majd kattintson a **Kezelés** parancsra.
4. Keresse meg a **Felhasználói** tanúsítványsablont, kattintson rá a jobb gombbal, majd kattintson a **Sablon duplikálása** elemre. Ekkor megnyílik az **Új sablon tulajdonságai** ablak.
5. A **Kompatibilitás** lapon
   * Állítsa a **Hitelesítésszolgáltató** beállítást **Windows Server 2008 R2** értékre.
   * Állítsa a **Tanúsítvány kezdeményezettje** beállítást **Windows 7 / Server 2008 R2** értékre.
6. Az **Általános** lapon:
   * Állítsa a **Sablon megjelenítendő neve** beállítást egy aktuális névre.

   > [!WARNING]
   > A **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*. Jegyezze meg a sablon nevét későbbi használatra.

7. A **Kérelmek kezelése** lapon jelölje be **A titkos kulcs exportálható** jelölőnégyzetet.
8. A **Titkosítás** lapon győződjön meg róla, hogy a **Minimális kulcshossz** értéke 2048.
9. A **Tulajdonos neve** lapon kattintson **A kérelem fogja tartalmazni** választógombra.
10. A **Bővítmények** lapon ellenőrizze, hogy az **Alkalmazás-szabályzatok** alatt láthatóak-e a következő elemek: Titkosított fájlrendszer, Biztonságos e-mail, Ügyfél-hitelesítés.
    
      > [!IMPORTANT]
      > iOS- és macOS-tanúsítványsablonok esetében a **Kiterjesztések** lapon módosítsa a **Kulcshasználat** beállítást, és ügyeljen rá, hogy **Az aláírás igazolja az eredetet** jelölőnégyzet ne legyen bejelölve.

11. A **Biztonság** lapon vegye fel annak a kiszolgálónak a fiókját, amelyen telepíti a Microsoft Intune Tanúsítvány-összekötőt.
    * Adja meg a fiók számára az **Olvasás** és **Beléptetés** engedélyeket.
12. A tanúsítvány mentéséhez kattintson az **Alkalmaz**, majd az **OK** elemre.
13. Zárja be a **Tanúsítvány-sablonok konzolt**.
14. A **Hitelesítésszolgáltató** konzolon kattintson a jobb gombbal a **Tanúsítványsablonok**, az **Új**, majd a **Kiállítandó tanúsítványsablon** elemekre.
    * Válassza ki az iménti lépésekben létrehozott sablont, majd kattintson az **OK** elemre.
15. Ahhoz, hogy a kiszolgáló az Intune-ban regisztrált eszközök és felhasználók nevében kezelhesse a tanúsítványokat, kövesse az alábbi lépéseket:

    a. Kattintson a jobb gombbal a hitelesítésszolgáltatóra, majd kattintson a **Tulajdonságok** elemre.

    b. A biztonság lapon vegye fel annak a kiszolgálónak a fiókját, amelyen futtatja a Microsoft Intune Tanúsítvány-összekötőt.
      * A fiók számára adja meg a **Tanúsítványok kiadása és kezelése** és a **Tanúsítványkérés** engedélyeket.
16. Jelentkezzen ki a vállalati hitelesítésszolgáltatóból.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>A Microsoft Intune Tanúsítvány-összekötő letöltése, telepítése és konfigurálása

![ConnectorDownload][ConnectorDownload]

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
2. Az **Intune** panelen válassza az **Eszközök konfigurálása** lehetőséget. 
3. Válassza az **Eszközök konfigurálása** panel **Hitelesítésszolgáltató** elemét. 
4. Kattintson a **Hozzáadás** gombra, és válassza az **Összekötő letöltése** lehetőséget. Mentse a letöltést egy olyan helyre, ahol hozzá tud férni a kiszolgálón, amelyre telepíteni fogja. 
5.  Jelentkezzen be azon a kiszolgálón, amelyen telepíteni fogja a Microsoft Intune Tanúsítvány-összekötőt.
6.  Futtassa a telepítőt, és fogadja el az alapértelmezett helyet. A telepítő az összekötőt a C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe helyen telepíti.
    1. A Telepítőbeállítás oldalon kattintson a **PFX terjesztése**, majd a **Tovább** elemre.
    2. Kattintson a **Telepítés** elemre, és várjon, amíg a telepítés befejeződik.
    3. A Befejezés lapon jelölje be az **Intune-összekötő indítása** feliratú jelölőnégyzetet, majd kattintson a **Befejezés** elemre.
7.  Az NDES-összekötő ablaknak ekkor a **Regisztráció** lapra kell nyílnia. Az Intune-hoz való kapcsolódás engedélyezéséhez kattintson a **Bejelentkezés** elemre, és adjon meg egy rendszergazdai engedélyekkel rendelkező fiókot.
8.  A **Speciális** lapon kijelölve hagyhatja a **Use this computer's SYSTEM account (default)** (A számítógép SYSTEM fiókjának használata (alapértelmezett)) feliratú választógombot.
9.  Kattintson az **Alkalmaz**, majd a **Bezárás** elemre.
10. Most pedig lépjen vissza az Azure Portalra. Néhány percen belül meg kell jelennie egy zöld pipajelnek és az **Aktív** szónak a **Kapcsolat állapota** területen, ha megnyitja az **Intune** > **Eszközkonfiguráció** > **Hitelesítésszolgáltató** lapot. Ez a megerősítés jelzi, hogy az összekötő kiszolgáló kapcsolatba tud lépni az Intune-nal.


## <a name="create-a-device-configuration-profile"></a>Eszközkonfigurációs profil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Nyissa meg az **Intune**, majd az **Eszközkonfiguráció**, és végül a **Profilok** lapot, majd kattintson a **Profil létrehozása** elemre.

   ![NavigateIntune][NavigateIntune]

3. Adja meg az alábbi adatokat:
   * **Név** a profil számára
   * Igény szerint hozzáadhat egy leírást
   * **Platform**, amelyen telepíteni kell a profilt
   * A **Profiltípust** állítsa **Megbízható tanúsítványra**
4. Nyissa meg a **Beállítások** lapot, és adja meg a korábban exportált hitelesítésszolgáltatói főtanúsítvány .cer fájlját.

   > [!NOTE]
   > A **3. lépésben** választott Platformtól függően lehetősége lehet **Céltárolót** választani a tanúsítvány számára.

   ![ProfileSettings][ProfileSettings]

5. A profil mentéséhez kattintson az **OK**, majd a **Létrehozás** elemre.
6. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS-tanúsítványprofil létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Nyissa meg az **Intune**, majd az **Eszközkonfiguráció**, és végül a **Profilok** lapot, majd kattintson a **Profil létrehozása** elemre.
3. Adja meg az alábbi adatokat:
   * **Név** a profil számára
   * Igény szerint hozzáadhat egy leírást
   * **Platform**, amelyen telepíteni kell a profilt
   * A **Profiltípust** állítsa **PKCS-tanúsítványra**
4. Nyissa meg a **Beállítások** lapot, és adja meg a következő adatokat:
   * **Megújítási küszöb (%)** – Az ajánlott érték 20%.
   * **Tanúsítvány érvényességi időtartama** – ha nem módosította a tanúsítványsablont, akkor a megadott beállítás egy év.
   * **Hitelesítésszolgáltató** – Ez a beállítás a vállalati hitelesítésszolgáltató belső teljes tartományneve (FQDN).
   * **Hitelesítésszolgáltató neve** – Ez a beállítás a vállalati hitelesítésszolgáltató neve, ami nem feltétlenül azonos az előző elemmel.
   * **Tanúsítványsablon neve** – Ez a beállítás a korábban létrehozott sablon neve. Emlékeztető: a **Sablon neve** alapértelmezés szerint ugyanaz, mint a **Sablon megjelenítendő neve**, *szóköz nélkül*.
   * **Tulajdonos nevének formátuma** – Ennél a beállításnál, ha nincs eltérő követelmény, a **Köznapi nevet** adja meg.
   * **Tulajdonos alternatív neve** – Ennél a beállításnál, ha nincs eltérő követelmény, az **Egyszerű felhasználónevet (UPN)** adja meg.
   * **Kibővített kulcshasználat** – Amíg a fenti, **Tanúsítványsablonok konfigurálása a hitelesítésszolgáltatónál** szakasz 10. lépésében ismertetett alapértelmezett beállításokat használja, a következő **Előre meghatározott értékeket** adja meg a kijelölési mezőből:
      * **Általános felhasználás**
      * **Ügyfél-hitelesítés**
      * **Biztonságos e-mail**
   * **Főtanúsítvány** – (Androidos profilokhoz) Ez a beállítás a fenti [Főtanúsítvány exportálása a vállalati hitelesítésszolgáltatótól](#export-the-root-certificate-from-the-enterprise-ca) szakasz 3. lépésében exportált .cer fájl.

5. A profil mentéséhez kattintson az **OK**, majd a **Létrehozás** elemre.
6. Az új profil egy vagy több eszközhöz történő hozzárendeléséhez lásd: [Microsoft Intune-eszközprofilok hozzárendelése](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Nyissa meg az Intune oldalt az Azure Portalon, és hozzon létre egy új profilt egy megbízható tanúsítványhoz"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Hozzon létre egy profilt, és töltsön fel egy megbízható tanúsítványt"
[ConnectorDownload]: ./media/certificates-download-connector.png "Töltse le a tanúsítvány-összekötőt az Azure Portalról"  
