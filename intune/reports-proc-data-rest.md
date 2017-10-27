---
title: "Adatok beolvasása az adattárház API-ból REST-ügyféllel"
description: "Adatok beolvasása az Intune-adattárházból RESTful API-val"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f1ffc07d87e98666a882415d63e11bd04bbd5461
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2017
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a>Adatok beolvasása az Intune-adattárház API-ból REST-ügyféllel

Az Intune-adatárház adatmodellje RESTful végpontokon keresztül érhető el. Ahhoz, hogy hozzáférjen az adatokhoz, az ügyfélnek az OAuth 2.0 protokollt használva igazolnia kell, hogy jogosult a Microsoft Azure Active Directory (Azure AD) használatára. A hozzáférés engedélyezéséhez először hozzon létre egy natív alkalmazást az Azure-ban, majd adjon annak engedélyeket a Microsoft Intune API használatára. Amikor a helyi ügyfél megkapja az engedélyt, a natív alkalmazáson keresztül fog tudni kommunikálni az adattárház-végpontokkal.

Egy ügyfél adatok az adattárház API-ból való beolvasására történő beállításához a következőket kell tennie:

1. Ügyfélalkalmazás létrehozása natív alkalmazásként az Azure-ban
3. Hozzáférés biztosítása az ügyfélalkalmazásnak a Microsoft Intune API-hoz
3. Helyi REST-ügyfél létrehozása az adatok beolvasásához

Az alábbi lépésekből megtudhatja, hogyan engedélyezheti és használja ügyfélként a Postman alkalmazást. A Postman alkalmazást gyakran használják API-kat használó REST-ügyfelek fejlesztésére és hibaelhárítására. A Postmannel kapcsolatban a [Postman](https://www.getpostman.com) webhelyén találhat további információkat. A témakör egy C# nyelvű kódmintát is tartalmaz. A példa azt mutatja be, hogyan lehet engedélyezni egy ügyfélprogramot, és beolvasni adatokat az API-ból.

## <a name="create-a-native-app-in-azure"></a>Natív alkalmazás létrehozása az Azure-ben

Hozzon létre egy natív alkalmazást az Azure-ben. Ez a natív alkalmazás az ügyfélalkalmazás. A helyi számítógépen futó ügyfélalkalmazás az Intune adattárház API-ra hivatkozik, amikor a helyi ügyfél bekéri a hitelesítési adatokat. 

1. Jelentkezzen be a bérlőhöz tartozó Azure Portalra. Válassza az **Azure Active Directory** > **Alkalmazásregisztrációk** lehetőséget az **Alkalmazásregisztrációk** panel megnyitásához.
2. Kattintson az **Új alkalmazásregisztráció** lehetőségre.
3. Gépelje be az alkalmazás adatait.
    1.  A **Név** mezőben adjon meg egy felhasználóbarát nevet, például azt, hogy „Intune-adattárházügyfél”.
    2.  Az **Alkalmazástípus** mezőben válassza a **Natív** lehetőséget.
    3.  Írjon be egy URL-címet a **Bejelentkezési URL-cím** mezőbe. A bejelentkezési URL-cím az adott forgatókönyvtől is függ, azonban ha a Postman alkalmazást tervezi használni, a következő címet írja be: `https://www.getpostman.com/oauth2/callback`. A visszahívásra az ügyfél-hitelesítési lépésben lesz szükség a Microsoft Azure AD-beli hitelesítéshez.
4.  Kattintson a **Létrehozás** gombra.

     ![Intune-adattárház API](media\reports-get_rest_data_client_overview.png)

5. Jegyezze fel az alkalmazás **Alkalmazásazonosítóját**. Az azonosítóra szükség lesz a következő szakaszban.
6. Ha a Postmant tervezi használni, adjon meg egy kulcsot. A kulcs lesz a titkos ügyfélkód a Microsoft Azure AD-beli hitelesítés során. A kulcs hozzáadása:
    1.  Az alkalmazáshoz tartozó Beállítások panelen kattintson a **Kulcsok** elemre az **API-hozzáférés** szakaszban.
    2.  A **Leírás** mezőbe írja be a kulcs nevét, például azt, hogy „Titkos ügyfélkód”.
    3.  Időtartamként válassza az **1 év** lehetőséget.
    4.  Kattintson a **Mentés**gombra. 
    5.  Másolja le a kulcs értékét. A kulcsok **Beállítások** paneljének bezárása után nem fogja tudni lekérni a kulcsot.

## <a name="grant-the-native-app-access-to-the-microsoft-intune-api"></a>Hozzáférés biztosítása a natív alkalmazásnak a Microsoft Intune API-hoz

Most már rendelkezik egy Azure-ban definiált alkalmazással. Gondoskodjon arról, hogy a natív alkalmazásból hozzá lehessen férni a Microsoft Intune API-hoz.

1.  Kattintson a natív alkalmazásra. Az alkalmazásnak Ön az **Intune-adattárházügyfél**, vagy ehhez hasonló nevet adott.
2.  A **Beállítások** panelen kattintson a **Szükséges engedélyek** lehetőségre.
3.  A **Szükséges engedélyek** panelen kattintson a **Hozzáadás** lehetőségre.
4.  Kattintson az **API kiválasztása** lehetőségre.
5.  Keressen rá a webalkalmazás nevére. Az alkalmazás neve **Microsoft Intune API**.
6.  Kattintson rá az alkalmazásra a listában.
7.  Kattintson a **Kiválasztás** lehetőségre.
8.  Jelölje be a **Delegált engedélyek** jelölőnégyzetet a **Get data warehouse information from Microsoft Intune** (Adattárház-információk beolvasása a Microsoft Intune-ból) lehetőség felvételéhez.

    ![Hozzáférés engedélyezése](media\reports-get_rest_data_client_access.png)

9.  Kattintson a **Kiválasztás** lehetőségre.
10.  Kattintson a **Kész** gombra.
11.  A Szükséges engedélyek panelen rákattinthat az **Engedélyek megadása** lehetőségre. Így az aktuális címtár minden fiókjának adható hozzáférés. Ezáltal elkerülhető, hogy a hozzájárulási párbeszédpanel a bérlő összes felhasználójánál megjelenjen. További információt az [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) (Alkalmazások integrációja az Azure Active Directory-val) című témakörben találhat.
12.  Kattintson az **Igen** gombra.

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a>Adatok beolvasása a Microsoft Intune API-ból a Postman alkalmazással

Az Intune-adattárház API-t használhatja olyan általános REST ügyfelekkel, mint például a Postman. A Postman információkat tud biztosítani az API szolgáltatásairól, a mögöttes OData-adatmodellről, és el tudja hárítani az API-erőforrásokkal létesített kapcsolatok hibáit. Ez a szakasz bemutatja, hogyan hozhat létre egy Auth2.0-jogkivonatot a helyi ügyfél számára. Az ügyfélnek az Azure AD-ben való hitelesítéshez és az API-erőforrásokhoz való hozzáféréshez lesz szüksége a jogkivonatra.

### <a name="information-you-will-need-to-make-the-call"></a>A híváshoz szükséges információk

A következők szükségesek REST-hívások a Postman alkalmazásból való végrehajtásához:

| Attribútum        | Leírás                                                                                                                                                                          | Példa                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Visszahívási URL     | Az alábbi címet adja meg az alkalmazás Beállítások oldalán visszahívási URL-címként.                                                                                                                              | https://www.getpostman.com/oauth2/Callback                                                    |
| Jogkivonat neve       | A karakterlánc, amellyel az ügyfél átadja a hitelesítő adatokat az Azure-alkalmazásnak. A folyamat során egy jogkivonat jön létre, mellyel az adattárház API-t hívhatja.                          | Tulajdonos                                                                                        |
| Hitelesítési URL-cím         | A hitelesítéshez használt URL-cím. | https://Login.microsoftonline.com/common/oauth2/Authorize?Resource=https://API.Manage.microsoft.com |
| Hozzáférési jogkivonat URL-címe | A jogkivonat megadásához használt URL-cím.                                                                                                                                              | https://Login.microsoftonline.com/common/oauth2/token |
| Ügyfél-azonosító        | Az Azure-beli natív alkalmazás létrehozásakor hozta létre és jegyezte fel.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Titkos ügyfélkód    | Akkor hozta létre és jegyezte fel, amikor felvett egy kulcsot az ügyfélalkalmazáshoz az Azure-ban.                                                                                              | JZoRZGPmN9xwsUnfX9UW877dkV5Fn/qQClhr7SuyMUQ =                                                  |
| Hatókör (nem kötelező) | Üres                                                                                                                                                                               | Ezt a mezőt üresen hagyhatja.                                                                     |
| Engedélyezési típus       | A jogkivonat egy engedélyezési kód.                                                                                                                                                  | Engedélyezési kód                                                                            |

A végpont szükséges. Ebben a példában a **dates** entitásból olvasunk be adatokat. A **dates** entitás formátuma a következő: `https://fef.{aus}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`. A bérlőkezelési URL-címet kell használnia. A bérlőkezelési URL-címet a webalkalmazás létrehozásakor használta.

### <a name="make-the-rest-call"></a>A REST-hívás végrehajtása

Ahhoz, hogy beszerezzen egy új hozzáférési jogkivonatot a Postman számára, meg kell adnia az Azure AD engedélyezési URL-címet, az ügyfél-azonosítót és a titkos ügyfélkódot. A Postman betölti az engedélyezési oldalt, melyen meg kell adnia a hitelesítő adatait.

#### <a name="add-the-information-used-to-request-the-token"></a>A jogkivonat kéréséhez szükséges információk

1.  Ha még nincs telepítve, töltse le a Postman alkalmazást. A Postman alkalmazást a [www.getpostman](https://www.getpostman.com) címről töltheti le.
2.  Nyissa meg a Postmant. Válassza ki a **GET** HTTP-műveletet.
3.  Illessze be a végpont URL-címét a címbe. Valahogy így kell kinéznie:  

    `https://fef.msua06.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  Válassza az **Authorization** (Engedélyezés) lapot, és a **Type** (Típus) listában válassza ki az **OAuth 2.0** lehetőséget.
5.  Kattintson az **Get New Access Token** (Új hozzáférési jogkivonat beszerzése) lehetőségre.
6.  Ellenőrizze, hogy hozzáadta-e már a visszahívási URL-címet (Callback URL) az Azure-beli alkalmazáshoz. A Callback URL (Visszahívási URL-cím) a következő: `https://www.getpostman.com/oauth2/callback`.
7.  A **Token Name** (Jogkivonat neve) mezőbe írja be a Bearer értéket.
8.  Adja meg az **Auth URL** (Hitelesítési URL-cím) értékét. Valahogy így kell kinéznie:  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com`
9.  Adja meg az **Access Token URL** (Hozzáférési jogkivonat URL-címe) értékét. Valahogy így kell kinéznie:  

     `https://login.microsoftonline.com/common/oauth2/token`

10. Adja meg a **Client ID** (Ügyfél-azonosító) értékét az Azure-ben létrehozott, `Intune Data Warehouse Client` nevű alkalmazásból. Valahogy így kell kinéznie:  

     `4184c61a-e324-4f51-83d7-022b6a81b991`

11. Adja meg a **Client Secret** (Titkos ügyfélkód) értékét, azaz az Azure-beli natív alkalmazás létrehozásakor kulcsként megadott értéket. Valahogy így kell kinéznie: 

     `F360R69M0MS72OB6YAqTyXO9MsXZx/OJTgAE2HB4k2k=`

12. Válassza az **Authorization Code** (Engedélyezési kód) lehetőséget, és jelölje be a Request access code locally (Hozzáférési jogkivonat kérése helyileg) jelölőnégyzetet.

13. Kattintson a **Request Token** (Jogkivonat kérése) elemre.

    ![A jogkivonat adatai](media\reports-postman_getnewtoken.png)

14. Adja meg a hitelesítő adatait az Active AD engedélyezési oldalán. A Postmanben most már szerepelni fog a `Bearer` nevű jogkivonat a meglévő jogkivonatok listáján.
16. Válassza ki a jogkivonatot. Az „Add token to” (Jogkivonat hozzáadása) elemnél válassza a **Header** (Fejléc) lehetőséget.
17. Kattintson a **Use Token** (Jogkivonat használata) elemre. A fejlécek listája tartalmazza az új engedélyezési kulcsértéket és a `Bearer <your-authorization-token>` értéket.

#### <a name="send-the-call-to-the-endpoint-using-postman"></a>Küldje el a hívást a végpontra a Postman alkalmazással.

1.  Kattintson a **Küldés** gombra.
2.  A visszaadott adatok a Postman-válasz törzsében jelennek meg.

    ![Postman 200OK](media\reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a>REST-ügyfél (C#) létrehozása az Intune-adattárház adatainak beolvasásához

Az alábbi minta egy egyszerű REST-ügyfelet tartalmaz. A kód a .Net-kódtár **httpClient** osztályát használja. Amikor az ügyfél Azure AD-beli hitelesítő adatokat kap, létrehoz egy GET REST hívást a dates entitás az adattárház API-ból való beolvasásához.

> [!Note]  
> Az alábbi kódminta elérhető a [GitHubon](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs). A kód legutóbbi változtatásai és frissítései a GitHub-tárházban érhetők el.

1.  Indítsa el a **Microsoft Visual Studiót**.
2.  Válassza a **Fájl** > **Új projekt** lehetőséget. Bontsa ki a **Visual C#** lehetőséget, és válassza a **Console App (.Net Framework)** (Konzolalkalmazás (.Net-keretrendszer)) lehetőséget. 
3.  A projektnek adja az ` IntuneDataWarehouseSamples` nevet, és tallózással válassza ki, hova szeretné azt menteni, majd kattintson az **OK** gombra.
4.  Kattintson a jobb gombbal a megoldás nevére a Megoldáskezelőben, majd válassza a **Manage NuGet Packages for Solution** (Megoldás NuGet-csomagjainak kezelése) lehetőséget. Kattintson a **Tallózás** elemre, majd írja a `Microsoft.IdentityModel.Clients.ActiveDirectory` szöveget a keresőmezőbe.
5. Válassza ki a csomagot, jelölje ki a **IntuneDataWarehouseSamples** projektet a „Manage Packages for Your Solution” (Megoldás csomagjainak kezelése) szakaszban, majd kattintson a **Telepítés** lehetőségre. 
6. Az **Elfogadom** elemre kattintva fogadja el a NuGet-csomag licencfeltételeit.
7. Nyissa meg a `Program.cs` fájlt a Megoldáskezelőben.

    ![A projekt a Visual Studióban](media\reports-get_rest_data_in.png)

8.  Írja felül a Program.cs fájlban található kódot az alábbi kóddal:  
    ```csharp
namespace IntuneDataWarehouseSamples
{
    using System;
    using System.Net.Http;
    using System.Net.Http.Headers;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    class Program
    {
     static void Main(string[] args)
  {
   /**
    * TODO: Replace the below values with your own.
    * emailAddress - The email address of the user that you will authenticate as.
    *
    * password  - The password for the above email address.
    *    This is inline only for simplicity in this sample. We do not 
    *    recommend storing passwords in plaintext.
    *
    * applicationId - The application ID of the native app that was created in AAD.
    *
    * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
    *      the Azure portal.
    * 
    * collectionName - The name of the warehouse entity collection you would like to 
    *      access.
    */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
    resource: "https://api.manage.microsoft.com/",
    clientId: applicationId,
    userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
  }
    }
    ```

9.  Frissítse a mintakódban található `TODO` elemeket.
10.  A **Ctrl + F5** billentyűkombinációval állítsa össze és futtassa az Intune.DataWarehouseAPIClient ügyfelet hibakeresési módban.

    ![JSON formátumban beolvasott dátumentitás.](media\reports-get_rest_data_output.png)

11.  Tekintse meg a kimenetet a konzolon. A kimenet JSON formátumban tartalmazza az Intune-bérlő **dates** entitásából kinyert adatokat.

## <a name="next-steps"></a>További lépések

Az engedélyezéssel, az API URL-címek szerkezetével és az OData-végpontokkal kapcsolatban az [Intune-adattárház API-végpontja](reports-api-url.md) című témakörben találhat további információkat. 

Az API-ban megtalálható adatentitásokkal kapcsolatban az Intune-adattárház adatmodelljében is tájékozódhat. További információ: [Az adattárház adatmodellje](reports-ref-data-model.md).