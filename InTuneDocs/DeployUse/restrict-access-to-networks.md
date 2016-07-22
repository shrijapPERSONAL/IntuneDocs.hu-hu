---
title: "Hálózati hozzáférés korlátozása a Cisco ISE használatával | Microsoft Intune"
description: "A Cisco ISE alkalmazást az Intune-nal együtt használva az eszközei regisztrálva lesznek az Intune-ban és megfelelnek a házirendeknek a Cisco ISE által kezelt Wi-Fi- és VPN-hálózatokra történő csatlakozáskor."
keywords: 
author: nbigman
manager: Arob98
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 9e90971a9997e65e98a8c55b24fb70a42da93702


---

# A Cisco ISE használata az Intune-nal
A Cisco ISE Intune-integrációja lehetővé teszi, hogy az Intune eszközregisztrációs és megfelelőségi állapotával hálózati házirendeket hozzon létre az ISE-környezetében. Ezekkel a házirendekkel meggyőződhet arról, hogy a céges hálózathoz csak azok az eszközök csatlakozhatnak, amelyeket az Intune kezel, illetve amelyek megfelelnek az Intune házirendjeinek. 

## Configuration

Az integráció engedélyezéséhez nincs szükség telepítésre az Intune-bérlőben. Csak engedélyt kell adnia a Cisco ISE-kiszolgálónak az Intune-bérlőhöz való hozzáféréshez, a telepítés többi lépése pedig már a Cisco ISE-kiszolgálón belül történik. Ez a cikk leírja, hogyan adhat engedélyt az ISE-kiszolgálónak az Intune-bérlőhöz való hozzáféréshez. 

### 1. lépés: A tanúsítványok kezelése
1. Az Azure Active Directory (AAD) konzolján exportálja a tanúsítványt. 

    #### Internet Explorer 11
        
    a. Futtassa rendszergazdaként az Internet Explorert, majd jelentkezzen be az AAD konzoljába.
  
    b. A címsorban kattintson a lakat ikonra, majd a **Tanúsítványok megtekintése** elemre
    
    c. A tanúsítvány tulajdonságai **Részletek** lapján válassza a **Másolás fájlba** lehetőséget.

    d. A **Tanúsítványexportáló varázsló** kezdőlapján kattintson a **Tovább** gombra. 

    e. Az **Exportfájlformátum** lapon hagyja meg az alapértelmezett **DER kódolású bináris x.509 (. CER)** lehetőséget, majd kattintson a **Tovább** gombra.  

    f. Az **Exportálandó fájl** lapon kattintson a **Tallózás** gombra, majd jelölje ki a helyet, ahova mentené szeretné a fájlt, és adjon meg egy fájlnevet. Bár olyan, mintha exportálná a fájlt, valójában elnevezi a fájlt, amelybe az exportált tanúsítványt menteni fogja. Kattintson a **Tovább** &gt; **Befejezés** gombra.

    #### Safari
    
    a. Jelentkezzen be az AAD konzoljába.

    b. Válassza a lakat ikon &gt;  **További információ** lehetőséget.
    
    c. Válassza a **Tanúsítvány megtekintése** &gt; **Részletek** lehetőséget.

    d. Válassza ki a tanúsítványt, majd kattintson az **Exportálás** elemre.  


    > [!IMPORTANT]
    > Ellenőrizze a tanúsítvány lejárati dátumát, mert a lejárta után újat kell exportálnia és importálnia.

    

2. Az ISE konzolról importálja az Intune-tanúsítványt (az exportált fájlt) a **Megbízható tanúsítványok** tárolójába.
3. Az ISE konzolon nyissa meg a **Felügyelet** > **Tanúsítványok** > **Rendszer tanúsítványai** ablakot.
4. Válassza ki az ISE-tanúsítványt, és kattintson az **Exportálás** elemre.
5. Egy szövegszerkesztőben szerkessze az alábbiak szerint az exportált tanúsítványt:
 - Törölje a ** -----BEGIN CERTIFICATE-----** sort
 - Törölje az ** -----END CERTIFICATE-----** sort
 - Ellenőrizze, hogy a teljes szöveg egy sorból áll-e

### 2. lépés: Hozzon létre egy ISE-alkalmazást az AAD-bérlőben
1. Az Azure Active Directory (AAD) konzolon válassza az **Alkalmazások** > **Alkalmazás hozzáadása** > **Saját szervezet által fejlesztett alkalmazás hozzáadása** lehetőséget.
2. Adja meg az alkalmazás nevét és URL-címét. Az URL-cím lehet például a vállalati webhely.
3. Töltse le az alkalmazásjegyzéket (egy JSON-fájl).
4. Szerkessze a JSON-alkalmazásjegyzéket. A **keyCredentials** nevű beállításnál adja meg értékként a tanúsítvány az 1. lépésben szerkesztett szövegét.
5. Mentse a fájlt névváltoztatás nélkül.
6. Adjon az alkalmazásnak engedélyt a Microsoft Graph-hoz és a Microsoft Intune API-hoz.
    1. A Microsoft Graph-hoz válassza a következőket
        - **Alkalmazásengedélyek**: Címtáradatok olvasása
        - **Delegált engedélyek**: 
            - Felhasználói adatok elérése bármikor
          - A felhasználók beléptetése
   2. A Microsoft Intune API-hoz az **Alkalmazásengedélyeknél** válassza **Az eszköz állapotának és megfelelőségének beolvasása az Intune-ról** lehetőséget.

7. Válassza a **Végpontok megtekintése** lehetőséget, és másolja le az alábbi értékeket az ISE-beállítások konfigurálásához:

|Az AAD-portál értéke|A hozzá tartozó mező az ISE-portálban|
|-------------------|---------------------------------|
|Microsoft Azure AD Graph API-végpont|Automatikus felderítés URL-címe|
|Oauth 2.0 Token-végpont|Jogkivonatot kibocsátó URL-cím|
|Frissítse a kódot az ügyfél-azonosítóval|Ügyfél-azonosító|


### 3. lépés: Az ISE-beállítások konfigurálása 
2. A ISE felügyeleti konzolján adja meg ezeket az értékeket: 
  - **Kiszolgáló típusa**: Mobile Device Manager
  - **Hitelesítés típusa**: OAuth – ügyfél hitelesítő adatai
  - **Automatikus felderítés**: Igen
  - **URL-cím automatikus felderítése**: Adja meg az 1. lépés értékét
  - **Ügyfél-azonosító**: Adja meg az 1. lépés értékét
  - **Jogkivonatot kibocsátó URL-cím**: Adja meg az 1. lépés értékét



## Az Intune-bérlő és a Cisco ISE-kiszolgáló által közösen kezelt adatok
Ez a táblázat felsorolja az Intune által kezelt eszközök az Intune-bérlő és a Cisco ISE-kiszolgáló által közösen kezelt adatait.

|Tulajdonság|  Leírás|
|---------------|------------------------------------------------------------|
|complianceState|   Igaz vagy hamis (karakterlánc), amely azt jelzi, hogy az eszköz megfelelő vagy nem megfelelő.|
|isManaged| Igaz vagy hamis, amely azt jelzi, hogy az ügyfelet az Intune kezeli-e.|
|macAddress|Az eszköz MAC-címe.|
|serialNumber|Az eszköz sorozatszáma. Csak iOS-eszközökre vonatkozik.|
|IMEI|Az IMEI (15 decimális számjegy: 14 hagyományos és egy ellenőrző számjegy) vagy IMEISV (16 számjegy) az eszköz származási helyéről, fajtájáról és sorozatszámáról tartalmaz adatokat. A IMEI/SV szerkezete a 3GPP TS 23.003 alapján van megszabva. Csak SIM-kártyával rendelkező eszközökre érvényes.|
|udid|A unique device identifier (eszköz egyedi azonosítója) egy 40 karakterből (betűkből és számokból) álló sorozat, amellyel csak iOS-eszközök rendelkeznek.|
|MEID|A mobilkészülék-azonosító szám egy olyan globálisan egyedi szám, amely egy CDMA-mobilállomás darabjait képes azonosítani. A számformátumot a 3GPP2 S. R0048-as jelentése definiálja, de tulajdonképpen egy IMEI-szám hexadecimális számjegyekkel. A MEID 56 bit hosszúságú (14 hexadecimális számjegy). Három mezőből áll: egy 8 bites területi kódból (RR), egy 24 bites gyártói kódból és egy 24 bites gyártói sorozatszámból.| 
|osVersion| Az eszközön futó operációs rendszer verziószáma.
|modell|Eszközmodell.
|gyártó|Az eszköz gyártója.
|azureDeviceId| Az eszköz azonosítója, amelyet azt követően kap, hogy csatlakozott a munkahelyi Azure Active Directoryhoz. A nem csatlakoztatott eszközök esetében ez egy üres GUID azonosító.|
|lastContactTimeUtc|Az eszköz utolsó, az Intune felügyeleti szolgáltatásba való bejelentkezésének dátuma és időpontja. 


## A felhasználói felületet

Amikor egy felhasználó egy nem regisztrált eszközről próbál meg hozzáférni az erőforrásokhoz, a rendszer egy ehhez hasonló regisztrálási kérelmet jelenít meg:

![Regisztrációs kérés – példa](../media/cisco-ise-user-iphone.png)

Ha a felhasználó úgy dönt, hogy regisztrál, akkor a rendszer átirányítja az Intune regisztrációs folyamatához. Az Intune felhasználói regisztrációját az alábbi témakörök ismertetik:

- [Android-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [iOS-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Mac OS X-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Windows-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-windows)</br> 

Emellett a [letölthető regisztrációs útmutatóval](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) egyéni útmutatást kaphat a felhasználói élményéhez.


### További információ

[Cisco Identity Services Engine Felügyeleti útmutató, 2.1-es kiadás](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)




<!--HONumber=Jul16_HO3-->


