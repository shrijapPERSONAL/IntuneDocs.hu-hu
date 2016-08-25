---
title: "Hálózati hozzáférés korlátozása a Cisco ISE használatával | Microsoft Intune"
description: "A Cisco ISE alkalmazást az Intune-nal együtt használva biztosíthatja, hogy eszközei regisztrálva legyenek az Intune-ban és eleget tegyenek a szabályzatoknak, mielőtt csatlakoznának a Cisco ISE által vezérelt hálózatokhoz."
keywords: 
author: nbigman
manager: angrobe
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ede9c4db136eb0498cad6d196488d03768741328
ms.openlocfilehash: 382dd93a5aec7415e5fb738f3068820e36d8ae06


---

# A Cisco ISE használata az Intune-nal
A Cisco Identity Services Engine (ISE) Intune-integrációja lehetővé teszi, hogy az Intune eszközregisztrációs és megfelelőségi állapotával hálózati szabályzatokat hozzon létre az ISE-környezetében. Ezekkel a szabályzatokkal biztosíthatja, hogy a céges hálózathoz csak azok az eszközök csatlakozhassanak, amelyeket az Intune felügyel, és amelyek megfelelnek az Intune szabályzatainak.

## Konfigurációs lépés

Az integráció engedélyezéséhez nincs szükség telepítésre az Intune-bérlőben. A Cisco ISE-kiszolgáló számára engedélyezni kell a hozzáférést az Intune-bérlőhöz. Ezt követően a telepítés hátralévő része a Cisco ISE-kiszolgálón történik. A jelen cikk ismerteti, hogy hogyan adhat engedélyt az ISE-kiszolgálónak az Intune-bérlőhöz való hozzáféréshez.

### 1. lépés: A tanúsítványok kezelése
1. Az Azure Active Directory (Azure AD) konzolján exportálja a tanúsítványt.

    #### Internet Explorer 11


    a. Futtassa rendszergazdaként az Internet Explorert, majd jelentkezzen be az Azure AD konzoljába.

    b. A címsorban kattintson a lakat ikonra, majd a **Tanúsítványok megtekintése** elemre.

    c. A tanúsítvány tulajdonságai **Részletek** lapján válassza a **Másolás fájlba** lehetőséget.

    d. A **Tanúsítványexportáló varázsló** kezdőlapján kattintson a **Tovább** gombra.

    e. Az **Exportfájlformátum** lapon hagyja meg az alapértelmezett **DER kódolású bináris x.509 (. CER)** lehetőséget, majd kattintson a **Tovább** gombra.  

    f. Az **Exportálandó fájl** lapon kattintson a **Tallózás** gombra, majd jelölje ki a helyet, ahova mentené szeretné a fájlt, és adjon meg egy fájlnevet. Bár úgy tűnik, mintha exportálná a fájlt, valójában elnevezi azt a fájlt, amelybe az exportált tanúsítványt menteni fogja. Kattintson a **Tovább** &gt; **Befejezés** gombra.

    #### Safari

    a. Jelentkezzen be az Azure AD konzoljába.

    b. Válassza a lakat ikon &gt;  **További információ** lehetőséget.

    c. Válassza a **Tanúsítvány megtekintése** &gt; **Részletek** lehetőséget.

    d. Válassza ki a tanúsítványt, majd kattintson az **Exportálás** elemre.  

    > [!IMPORTANT]
    > Ellenőrizze a tanúsítvány lejárati dátumát, mert a lejárta után újat kell exportálnia és importálnia.


2. Az ISE konzolról importálja az Intune-tanúsítványt (az exportált fájlt) a **Megbízható tanúsítványok** tárolójába.
### Önaláírt tanúsítvány létrehozása az ISE alkalmazásban 
1.  A ISE-konzolon válassza az **Administration** (Felügyelet) > **Certificates** (Tanúsítványok) > **System Certificates** (Rendszertanúsítványok) > **Generate Self Signed Certificate** (Önaláírt tanúsítvány létrehozása) elemet.  
2.       Exportálja az önaláírt tanúsítványt.
3. Egy szövegszerkesztőben szerkessze az exportált tanúsítványt [megjegyzés]: <> Inkább nem tennék pontot e két állítás végére; szerintem összezavarhatja az olvasót.
 - Törölje a ** -----BEGIN CERTIFICATE-----** sort
 - Törölje az ** -----END CERTIFICATE-----** sort
 
Ellenőrizze, hogy a teljes szöveg egy sorból áll-e


### 2. lépés: Hozzon létre egy alkalmazást az ISE számára az AAD-bérlőben
1. Az Azure AD konzolján válassza az **Alkalmazások** > **Alkalmazás hozzáadása** > **Saját szervezet által fejlesztett alkalmazás hozzáadása** lehetőséget.
2. Adja meg az alkalmazás nevét és URL-címét. Az URL-cím lehet például a vállalati webhely.
3. Töltse le az alkalmazásjegyzéket (egy JSON-fájl).
4. Szerkessze a JSON-alkalmazásjegyzéket. A **keyCredentials** nevű beállításnál adja meg értékként a tanúsítvány az 1. lépésben szerkesztett szövegét.
5. Mentse a fájlt névváltoztatás nélkül.
6. Adjon az alkalmazásnak engedélyt a Microsoft Graph-hoz és a Microsoft Intune API-hoz.

 a. A Microsoft Graph-hoz válassza a következőket:
    - **Alkalmazásengedélyek**: Címtáradatok olvasása
    - **Delegált engedélyek**:
        - Felhasználói adatok elérése bármikor
        - A felhasználók beléptetése

 b. A Microsoft Intune API-hoz az **Alkalmazásengedélyeknél** válassza **Az eszköz állapotának és megfelelőségének beolvasása az Intune-ról** lehetőséget.

7. Válassza a **Végpontok megtekintése** lehetőséget, és másolja le az alábbi értékeket az ISE-beállítások konfigurálásához:

|Érték az Azure AD-portálon|A hozzá tartozó mező az ISE-portálban|
|-------------------|---------------------------------|
|Microsoft Azure AD Graph API-végpont|Automatikus felderítés URL-címe|
|Oauth 2.0 Token-végpont|Jogkivonatot kibocsátó URL-cím|
|Frissítse a kódot az ügyfél-azonosítóval|Ügyfél-azonosító|


### 3. lépés: Az ISE-beállítások konfigurálása
A ISE felügyeleti konzolján adja meg ezeket az értékeket:
  - **Kiszolgáló típusa**: Mobile Device Manager
  - **Hitelesítés típusa**: OAuth – ügyfél hitelesítő adatai
  - **Automatikus felderítés**: Igen
  - **URL-cím automatikus felderítése**: *Adja meg az 1. lépésbeli értéket.*
  - **Ügyfél-azonosító**: *Adja meg az 1. lépésbeli értéket.*
  - **Jogkivonatot kibocsátó URL-cím**: *Adja meg az 1. lépésbeli értéket.*



## Az Intune-bérlő és a Cisco ISE-kiszolgáló által közösen kezelt adatok
Ez a táblázat felsorolja az Intune-bérlő és a Cisco ISE-kiszolgáló között megosztott adatokat az Intune által felügyelt eszközök esetében.

|Tulajdonság|  Leírás|
|---------------|------------------------------------------------------------|
|complianceState|Az „igaz” vagy a „hamis” karakterlánc, amely azt jelzi, hogy az eszköz megfelelő vagy nem megfelelő.|
|isManaged|Az „igaz” vagy a „hamis” karakterlánc, amely azt jelzi, hogy az ügyfelet az Intune kezeli-e.|
|macAddress|Az eszköz MAC-címe.|
|serialNumber|Az eszköz sorozatszáma. Csak iOS-eszközökre vonatkozik.|
|IMEI|Az IMEI (15 decimális számjegy: 14 számjegy és egy ellenőrző számjegy) vagy IMEISV (16 számjegy) az eszköz származási helyéről, fajtájáról és sorozatszámáról tartalmaz adatokat. A szám szerkezetének meghatározását a 3GPP TS 23.003 tartalmazza. Csak SIM-kártyával rendelkező eszközökre érvényes.|
|udid|A egyedi eszközazonosító egy 40 karakterből (betűkből és számokból) álló sorozat. Csak az iOS-rendszerű eszközök rendelkeznek ilyennel.|
|MEID|A mobilkészülék-azonosító egy olyan globálisan egyedi szám, amely egy CDMA-mobilállomás fizikai készülékét azonosítja. A szám formátumát a 3GPP2 S. R0048 azonosítójú jelentése határozza meg. Gyakorlatilag úgy tekinthető, mint egy IMEI, amelynek számjegyei hexadecimálisak. A MEID 56 bit hosszúságú (14 hexadecimális számjegy). Három mezőből áll: egy 8 bites területi kódból (RR), egy 24 bites gyártói kódból és egy 24 bites gyártói sorozatszámból.|
|osVersion|Az eszközön futó operációs rendszer verziószáma.
|modell|Az eszköz modellje.
|gyártó|Az eszköz gyártója.
|azureDeviceId|Az eszköz azonosítója, amelyet azt követően kap, hogy csatlakozott a munkahelyi Azure AD-hoz. A nem csatlakoztatott eszközök esetében ez egy üres GUID azonosító.|
|lastContactTimeUtc|Az eszköz utolsó, az Intune felügyeleti szolgáltatásba való bejelentkezésének dátuma és időpontja.


## A felhasználói felületet

Amikor egy felhasználó egy nem regisztrált eszközről próbál meg hozzáférni az erőforrásokhoz, a rendszer egy ehhez hasonló regisztrálási felszólítást jelenít meg:

![Regisztrációs kérés – példa](../media/cisco-ise-user-iphone.png)

Ha a felhasználó úgy dönt, hogy regisztrálja az eszközt, a rendszer átirányítja az Intune regisztrációs folyamatához. Az Intune felhasználói regisztrációját az alábbi témakörök ismertetik:

- [Android-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [iOS-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Mac OS X-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Windows-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Emellett a [letölthető regisztrációs útmutatóval](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) egyéni útmutatást kaphat a felhasználói élményéhez.


### További információ

[Cisco Identity Services Engine Felügyeleti útmutató, 2.1-es kiadás](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)



<!--HONumber=Aug16_HO3-->


