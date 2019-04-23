---
title: Külső hitelesítésszolgáltató igénybe vétele az SCEP használatával az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A Microsoft Intune-ban hozzáadhat egy szállítót vagy külső hitelesítésszolgáltatót (CA), amely tanúsítványokat ad ki mobileszközökre az SCEP protokoll használatával. Ebben az áttekintő cikkben egy Azure Active Directory (Azure AD) alkalmazás ad engedélyeket a Microsoft Intune-nak tanúsítványok hitelesítésére. Ezután az SCEP-kiszolgáló beállítása következik a tanúsítványok kiadásához, az alkalmazás azonosítója, a hitelesítési kulcs és az AAD-alkalmazás bérlőazonosítója alapján.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d042a160d016343c6e8374dff8f74560b9806014
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508483"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Partner hitelesítésszolgáltató hozzáadása az Intune-ban SCEP protokollal

A Microsoft Intune-ban hozzáadhat külső hitelesítésszolgáltatókat (CA). Ezek a hitelesítésszolgáltatók az Egyszerű tanúsítványigénylési protokoll (SCEP) használatával telepíthetnek tanúsítványokat mobileszközökre. Ez a funkció kiadhat új tanúsítványokat, és meg is újíthat tanúsítványokat Windows, iOS, Android és macOS rendszerű eszközökön.

A funkció használata két részből áll: a nyílt forráskódú API-val kapcsolatos és az Intune-rendszergazdai feladatokból.

**1. rész – Nyílt forráskódú API használata**  
A Microsoft létrehozott egy API-t, amely az Intune-nal integráltan hitelesíti a tanúsítványokat, küld értesítéseket a sikeres vagy sikertelen végrehajtásról, és SSL-t, pontosabban SSL-szoftvercsatornát használva kommunikál az Intune-nal.

Az API az [Intune SCEP API nyilvános GitHub-tárházban](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) érhető el, ahonnan letöltheti és felhasználhatja saját megoldásaiban. Ezt az API-t külső SCEP-kiszolgálókkal használva egyéni ellenőrző kérdéssel ellenőrizhető a tanúsítvány az Intune-ban az eszközre való telepítés előtt.

Az [Intune-integráció SCEP-felügyeleti megoldásról](scep-libraries-apis.md) szóló témakör részletesebben is leírja az API használatát, metódusait és az elkészített megoldások tesztelését.

**2. rész – Az alkalmazás és profil létrehozása**  
Azure Active Directory-alkalmazás használatakor az eszközökről érkező SCEP-kérelmek kezelésének jogosultságai az Intune-nak delegálhatók. Az Azure AD-alkalmazás a fejlesztő által létrehozott API-megoldásban használt alkalmazásazonosítót és hitelesítési kulcsot is tartalmazza. A rendszergazdák így SCEP-tanúsítványprofilokat hozhatnak létre és telepíthetnek az Intune használatával. Az eszközök telepítési állapotáról szóló jelentéseket is megtekintheti.

Ez a cikk rendszergazdai szempontból tekinti át ezt a funkciót, beleértve az Azure AD-alkalmazás létrehozását is.

## <a name="overview"></a>Áttekintés

A következő lépések áttekintést adnak a SCEP-tanúsítványok Intune-beli kiadásáról:

1. Az Intune-ban egy rendszergazda létrehoz egy SCEP-tanúsítványprofilt, majd a profil céljaként felhasználókat vagy eszközöket jelöl ki.
2. Az eszköz bejelentkezik az Intune-ba.
3. Az Intune létrehoz egy egyedi SCEP ellenőrző kérdést. További integritás-ellenőrző információkat is megad, például a várt tárgyat és SAN-t.
4. Az Intune az ellenőrző kérdést és az integritás-ellenőrző információkat is titkosítja és aláírja, majd az SCEP-kérelemmel együtt elküldi ezt az információt az eszköznek.
5. Az eszköz generál egy tanúsítvány-aláírási kérelmet (CSR) és egy nyilvános/titkos kulcspárt az eszközön az Intune-ból leküldött SCEP-tanúsítványprofil alapján.
6. A CSR és a titkosított/aláírt ellenőrző kérdés van elküldve a külső SCEP-kiszolgálói végponthoz.
7. Az SCEP-kiszolgáló elküldi a CSR-t és az ellenőrző kérdést az Intune-nak. Az Intune ekkor ellenőrzi az aláírást, visszafejti a tartalmat és összeveti a CSR-t az integritás-ellenőrző információval.
8. Az Intune választ küld az SCEP-kiszolgálónak, amelyben tudatja, hogy az ellenőrző kérdésen alapuló hitelesítés sikeres volt vagy sem.  
9. Ha az ellenőrző kérdésen alapuló hitelesítés sikeres, az SCEP-kiszolgáló kiadja a tanúsítványt az eszköznek.

Az alábbi diagram részletesen bemutatja a külső SCEP és az Intune integrációjának folyamatát:

![Külső hitelesítésszolgáltató SCEP-jének együttműködése a Microsoft Intune-nal](./media/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Külső hitelesítésszolgáltatóval való integráció beállítása

### <a name="validate-third-party-certification-authority"></a>Külső hitelesítésszolgáltató ellenőrzése

Külső hitelesítésszolgáltatók Intune-nal való integrálása előtt győződjön meg arról, hogy az igénybe vett hitelesítésszolgáltató támogatja az Intune-t. A [Külső hitelesítésszolgáltató partnerek](#third-party-certification-authority-partners) című szakasz (ebben a cikkben) tartalmazza ezek felsorolását. Alaposabban is tájékozódhat hitelesítésszolgáltatója útmutatója alapján. A hitelesítésszolgáltatók saját megvalósítási módjukra vonatkozó telepítési utasításokat is megadhatnak.

### <a name="authorize-communication-between-ca-and-intune"></a>A hitelesítésszolgáltató és az Intune közötti kommunikáció engedélyezése

Ahhoz, hogy egy külső SCEP-kiszolgáló egyéni kérdésen alapuló ellenőrzést végezhessen az Intune-nal, készítsen egy alkalmazást az Azure AD-ban. Ez az alkalmazás delegált jogosultságokat ad az Intune-nak az SCEP-kérelmek ellenőrzéséhez.

Ehhez mindenképpen rendelkeznie kell az Azure AD-alkalmazás regisztrálásához szükséges engedélyekkel. A lépéseket a [Szükséges engedélyek](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) című szakasz ismerteti.

**1. lépés: Az Azure AD-alkalmazás létrehozása**

1. Jelentkezzen be az [Azure Portalra](https://portal.azure.com).
2. Válassza az **Azure Active Directory** > **Alkalmazásregisztráció** > **Új alkalmazás regisztrálása** lehetőséget.
3. Adjon meg egy nevet és bejelentkezési URL-címet. Az Alkalmazástípus mezőben válassza a **Webalkalmazás / API** lehetőséget.
4. Kattintson a **Létrehozás** gombra.

Az [Alkalmazások integrálása az Azure Active Directory-val](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) című cikkben néhány útmutatást, köztük az URL-címre és a névre vonatkozó tanácsot talál az alkalmazás létrehozásához.

**2. lépés: Jogosultságok megadása**

Alkalmazása létrehozása után adja meg a Microsoft Intune API-nak a szükséges engedélyeket:

1. Azure AD-alkalmazásában nyissa meg a **Beállítások** > **Szükséges engedélyek** menüpontot.  
2. Válassza a **Hozzáadás** > **API kijelölése** lehetőséget, válassza ki a **Microsoft Intune API-t** > **Kiválasztás**.
3. A **Szükséges engedélyek** alatt válassza a **SCEP ellenőrző kérdés** > **Kiválasztás** lehetőséget.
4. A módosítások mentéséhez válassza a **Kész** gombot.

**3. lépés: Az Alkalmazásazonosító és hitelesítési kulcs beszerzése**

Ez után szerezze be Azure AD-alkalmazása azonosító- és kulcs-értékeit. A következő értékekre van szükség:

- Alkalmazásazonosító
- Hitelesítési kulcs
- Bérlőazonosító

**Az alkalmazásazonosító és a hitelesítési kulcs beszerzéséhez**:

1. Az Azure AD-ben jelölje ki új alkalmazását (**Alkalmazásregisztrációk**).
2. Másolja ki az **Alkalmazás azonosítóját**, és tárolja az alkalmazás kódjában.
3. Ez után generáljon hitelesítési kulcsot. Azure AD-alkalmazásában nyissa meg a **Beállítások** > **Kulcsok** menüt.
4. A **Jelszavak** alatt adjon meg egy leírást, és válassza ki a kulcs élettartamát. **Mentse** a változtatásokat. Másolja ki és mentse a megjelenő értéket.

    > [!IMPORTANT]
    > A kulcsot azonnal ki kell másolnia és mentenie, mert többé nem lesz látható. Ennek a kulcsnak az értékére szükség van a külső hitelesítésszolgáltató implementációjánál. Mindenképpen tekintse át az ő útmutatójukat az alkalmazásazonosító, a hitelesítési kulcs és a bérlőazonosító általuk kívánt konfigurálásáról.

A **bérlőazonosító** a fiók nevében lévő @ jel utáni szöveg. Ha a fiók neve például `admin@name.onmicrosoft.com`, akkor a bérlőazonosító **name.onmicrosoft.com**.

Az [Alkalmazásazonosító és hitelesítési kulcs beszerzése](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key) című szakasz felsorolja az értékek beszerzésének lépéseit, és további részleteket tartalmaz az Azure AD-alkalmazásokról.

### <a name="configure-and-deploy-a-scep-certificate-profile"></a>SCEP-tanúsítványprofil konfigurálása és telepítése
Rendszergazdaként hozzon létre egy felhasználóknak vagy eszközöknek szánt SCEP-tanúsítványprofilt. Ezt követően végezze el a profil hozzárendelését.

- [SCEP-tanúsítványprofil létrehozása](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [A tanúsítványprofil felhasználókhoz vagy eszközökhöz rendelése](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Tanúsítványok eltávolítása

Ha törli az eszköz regisztrációját vagy teljes tartalmát, a tanúsítványok törölve lesznek. A tanúsítványok nem lesznek visszavonva.

## <a name="third-party-certification-authority-partners"></a>Külső hitelesítésszolgáltató partnerek
Az alábbi külső hitelesítésszolgáltatók támogatják az Intune-t:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)
- [EJBCA GitHub nyílt forráskódú verzió](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)

Ha Ön a terméke Intune-nal való integrálása iránt érdeklődő külső hitelesítésszolgáltatót képvisel, tekintse át az API-val kapcsolatos útmutatót:

- [Intune SCEP API GitHub-tárház](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API útmutató külső hitelesítésszolgáltatóknak](scep-libraries-apis.md)

## <a name="see-also"></a>Lásd még:

- [Tanúsítványprofilok konfigurálása](certificates-scep-configure.md)
- [Intune SCEP API GitHub-tárház](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API útmutató külső hitelesítésszolgáltatóknak](scep-libraries-apis.md)
