---
title: "Hálózati hozzáférés védelme a Cisco ISE használatával | Microsoft Docs"
description: "A Cisco ISE alkalmazást az Intune-nal együtt használva biztosíthatja, hogy eszközei regisztrálva legyenek az Intune-ban és eleget tegyenek a szabályzatoknak, mielőtt csatlakoznának a Cisco ISE által vezérelt hálózatokhoz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 9f34d54710f0ec662eecec85f7fa041061132a0d
ms.openlocfilehash: 8ef24e4d413662012f091c1be318d1d274e16439
ms.lasthandoff: 01/04/2017


---

# <a name="using-cisco-ise-with-microsoft-intune"></a>A Cisco ISE használata az Intune-nal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Cisco Identity Services Engine (ISE) Intune-integrációja lehetővé teszi, hogy az Intune eszközregisztrációs és megfelelőségi állapotával hálózati szabályzatokat hozzon létre az ISE-környezetében. Ezekkel a szabályzatokkal biztosíthatja, hogy a céges hálózathoz csak azok az eszközök csatlakozhassanak, amelyeket az Intune felügyel, és amelyek megfelelnek az Intune szabályzatainak.

## <a name="configuration-steps"></a>Konfigurációs lépés

Az integráció engedélyezéséhez nincs szükség telepítésre az Intune-bérlőben. A Cisco ISE-kiszolgáló számára engedélyezni kell a hozzáférést az Intune-bérlőhöz. Ezt követően a telepítés hátralévő része a Cisco ISE-kiszolgálón történik. A jelen cikk ismerteti, hogy hogyan adhat engedélyt az ISE-kiszolgálónak az Intune-bérlőhöz való hozzáféréshez.

### <a name="step-1-manage-the-certificates"></a>1. lépés: A tanúsítványok kezelése
Exportálja a tanúsítványt az Azure Active Directory (Azure AD) konzoljáról, majd importálja az ISE-konzol Megbízható tanúsítványok tárolójába:

#### <a name="internet-explorer-11"></a>Internet Explorer 11


   a. Futtassa rendszergazdaként az Internet Explorert, majd jelentkezzen be az Azure AD konzoljába.

   b. A címsorban kattintson a lakat ikonra, majd a **Tanúsítványok megtekintése** elemre.

   c. A tanúsítvány tulajdonságai **Részletek** lapján válassza a **Másolás fájlba** lehetőséget.

   d. A **Tanúsítványexportáló varázsló** kezdőlapján kattintson a **Tovább** gombra.

   e. Az **Exportfájlformátum** lapon hagyja meg az alapértelmezett **DER kódolású bináris x.509 (. CER)** lehetőséget, majd kattintson a **Tovább** gombra.  

   f. Az **Exportálandó fájl** lapon kattintson a **Tallózás** gombra, majd jelölje ki a helyet, ahova mentené szeretné a fájlt, és adjon meg egy fájlnevet. Bár úgy tűnik, mintha exportálná a fájlt, valójában elnevezi azt a fájlt, amelybe az exportált tanúsítványt menteni fogja. Kattintson a **Tovább** &gt; **Befejezés** gombra.

   g. Az ISE konzolról importálja az Intune-tanúsítványt (az exportált fájlt) a **Megbízható tanúsítványok** tárolójába.

#### <a name="safari"></a>Safari

 a. Jelentkezzen be az Azure AD konzoljába.

b. Válassza a lakat ikon &gt;  **További információ** lehetőséget.

   c. Válassza a **Tanúsítvány megtekintése** &gt; **Részletek** lehetőséget.

   d. Válassza ki a tanúsítványt, majd kattintson az **Exportálás** elemre. 

   e. Az ISE konzolról importálja az Intune-tanúsítványt (az exportált fájlt) a **Megbízható tanúsítványok** tárolójába.

> [!IMPORTANT]
>
> Ellenőrizze a tanúsítvány lejárati dátumát, mert a lejárta után újat kell exportálnia és importálnia.


### <a name="obtain-a-self-signed-cert-from-ise"></a>Önaláírt tanúsítvány létrehozása az ISE alkalmazásban 

1.  A ISE-konzolon válassza az **Administration** (Felügyelet) > **Certificates** (Tanúsítványok) > **System Certificates** (Rendszertanúsítványok) > **Generate Self Signed Certificate** (Önaláírt tanúsítvány létrehozása) elemet.  
2.       Exportálja az önaláírt tanúsítványt.
3. Egy szövegszerkesztőben szerkessze az alábbiak szerint az exportált tanúsítványt:

 - Törölje a ** -----BEGIN CERTIFICATE-----** sort
 - Törölje az ** -----END CERTIFICATE-----** sort
 
Ellenőrizze, hogy a teljes szöveg egy sorból áll-e


### <a name="step-2-create-an-app-for-ise-in-your-azure-ad-tenant"></a>2. lépés: Hozzon létre egy alkalmazást az ISE számára az AAD-bérlőben
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

### <a name="step-4-upload-the-self-signed-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad"></a>4. lépés: Töltse fel az önaláírt tanúsítványt az ISE-ből az Azure AD-ben létrehozott ISE-alkalmazásba
1.     A .cer X509 nyilvános tanúsítványfájlból szerezze be a base64-kódolású tanúsítvány-értéket és ujjlenyomatot. Ez a példa PowerShellt használ:
   
      
      $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()
 
    Tárolja el az értékeket a $base64Thumbprint, a $base64Value és a $keyid változókhoz, amelyeket a következő lépésben használ majd.
2.       Töltse fel a tanúsítványt a jegyzékfájlon keresztül. Jelentkezzen be az [Azure felügyeleti portálra](https://manage.windowsazure.com)
2.      Az Azure AD beépülő modulban keresse meg az X.509-es tanúsítvánnyal konfigurálni kívánt alkalmazást.
3.      Töltse le az alkalmazás jegyzékfájlját. 
5.      Az üres “KeyCredentials”: [], tulajdonságot cserélje le a következő JSON-kódra.  A KeyCredentials összetett típus; leírása az [Entitások és összetett típusok segédletben](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType) található.

 
    “keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2. 
     ], 
 
Példa:
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6.      Mentse az alkalmazás jegyzékfájlján végrehajtott módosítást.
7.      Töltse fel a módosított alkalmazásjegyzék-fájlt az Azure felügyeleti központon keresztül.
8.      Nem kötelező: Töltse le újra a jegyzékfájlt, hogy ellenőrizze, hogy a X-509-es tanúsítvány telepítve lett az alkalmazáson.

>[!NOTE]
>
> A KeyCredentials gyűjtemény, így több X.509-es tanúsítványt is feltölthet kulcsváltások esetére vagy biztonsági sérülés esetén törölhet tanúsítványokat.


### <a name="step-4-configure-ise-settings"></a>4. lépés: Az ISE-beállítások konfigurálása
A ISE felügyeleti konzolján adja meg ezeket az értékeket:
  - **Kiszolgáló típusa**: Mobile Device Manager
  - **Hitelesítés típusa**: OAuth – ügyfél hitelesítő adatai
  - **Automatikus felderítés**: Igen
  - **URL-cím automatikus felderítése**: *Adja meg az 1. lépésbeli értéket.*
  - **Ügyfél-azonosító**: *Adja meg az 1. lépésbeli értéket.*
  - **Jogkivonatot kibocsátó URL-cím**: *Adja meg az 1. lépésbeli értéket.*



## <a name="information-shared-between-your-intune-tenant-and-your-cisco-ise-server"></a>Az Intune-bérlő és a Cisco ISE-kiszolgáló által közösen kezelt adatok
Ez a táblázat felsorolja az Intune-bérlő és a Cisco ISE-kiszolgáló között megosztott adatokat az Intune által felügyelt eszközök esetében.

|Tulajdonság|    Leírás|
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


## <a name="user-experience"></a>A felhasználói felületet

Amikor egy felhasználó egy nem regisztrált eszközről próbál meg hozzáférni az erőforrásokhoz, a rendszer egy ehhez hasonló regisztrálási felszólítást jelenít meg:

![Regisztrációs kérés – példa](../media/cisco-ise-user-iphone.png)

Ha a felhasználó úgy dönt, hogy regisztrálja az eszközt, a rendszer átirányítja az Intune regisztrációs folyamatához. Az Intune felhasználói regisztrációját az alábbi témakörök ismertetik:

- [Android-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [iOS-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Mac OS X-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Windows-eszköz regisztrálása az Intune-ban](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Emellett a [letölthető regisztrációs útmutatóval](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) egyéni útmutatást kaphat a felhasználói élményéhez.


### <a name="see-also"></a>További információ

[Cisco Identity Services Engine Felügyeleti útmutató, 2.1-es kiadás](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)

