---
title: Wi-Fi-beállítások Windows 10-es eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Wi-Fi-konfigurációs profil hozzáadása vagy létrehozása a Wi-Fi-beállítások használatával Windows 10 és újabb rendszerű eszközökön a Microsoft Intune-ban. Konfigurálhat alapszintű vagy nagyvállalati szintű beállításokat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0045c7eeaf3c53b8309d3bebe9f60da79337b487
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392855"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Wi-Fi-beállítások hozzáadása Windows 10 és újabb rendszerű eszközökhöz az Intune-ban

Adott Wi-Fi-beállításokkal rendelkező profilt hozhat létre, majd ezt a profilt üzembe helyezheti a Windows 10-es vagy újabb eszközökön. A Microsoft Intune számos szolgáltatást nyújt, beleértve a hálózaton való hitelesítést, az előmegosztott kulcsok használatát és egyebeket.

Ez a cikk ezeket a beállításokat ismerteti.

## <a name="before-you-begin"></a>Előkészületek

[Eszközprofil létrehozása](device-profile-create.md).

## <a name="basic-profile"></a>Alapszintű profil

- **Wi-Fi típusa**: Válassza a **Basic** (Egyszerű) lehetőséget. 

- **Wi-Fi neve (SSID)**: Rövid a szolgáltatáskészlet-azonosító. Ez az érték a valódi neve a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált **kapcsolatnevet** látják, amikor kiválasztják a kapcsolatot.

- **Kapcsolat neve**: Adjon meg egy felhasználóbarát nevet a Wi-Fi-kapcsolat. Az ide beírt szöveg a felhasználók számára megjelenő név, amikor a rendelkezésre álló kapcsolatokat böngészik az eszközeiken.

- **Automatikus csatlakozás, ha hatótávolságon belül van**: Amikor **Igen**, eszközök automatikus csatlakozás, ha a hálózat hatótávolságon belül. Ha a beállítás **Nem**, akkor az eszközök nem csatlakoznak automatikusan.

  - **Előnyben részesített hálózathoz csatlakozni, ha elérhető**: Ha az eszközök számos előnyben részesített hálózathoz, majd válassza ki **Igen** használatához az előnyben részesített hálózathoz. Válassza a **Nem** beállítást, hogy az ebben a konfigurációs profilban lévő Wi-Fi-hálózatot használják.

    Tegyük fel, hogy létrehozott egy **ContosoCorp** nevű Wi-Fi-hálózatot, és a **ContosoCorp** hálózatot használja ebben a konfigurációs profilban. Elérhető távolságban van egy **ContosoGuest** nevű Wi-Fi-hálózat is. Azt szeretné, hogy ha céges eszközei hatókörön belül vannak, automatikusan a **ContosoCorphoz** csatlakozzanak. Ebben az esetben állítsa a **Lehetőség szerint csatlakozás egy előnyben részesített hálózathoz** tulajdonságot **Nem** értékre.

  - **Ehhez a hálózathoz csatlakozni, akkor is, ha nem sugározza az SSID**: Válasszon **Igen** a konfigurációs profilok automatikusan csatlakoznak a hálózathoz, még akkor is, ha a hálózat el van rejtve (azaz, SSID nyilvánosan nem küldhetők). Válassza a **Nem** beállítást, ha nem szeretné, hogy ez a konfigurációs profil a rejtett hálózathoz csatlakozzon.

- **Mért kapcsolathoz megadott korlátot**: A rendszergazdák kiválaszthatják, hogy a hálózati forgalom forgalmi díjas. Alkalmazások ezt követően ennek a beállításnak az alapján módosíthatják a hálózati forgalommal kapcsolatos viselkedésüket. A választható lehetőségek:

  - **Korlátlan**: Default (Alapértelmezett): A rendszer nem méri a kapcsolatot, és nincs korlátozva a forgalom.
  - **Rögzített**: Használja ezt a beállítást, ha a hálózat úgy van konfigurálva, és a rögzített korlátja a hálózati forgalom. A korlát elérése után a hálózati hozzáférés le van tiltva.
  - **Változó**: Használja ezt a beállítást, ha a hálózati forgalom számlázása az bájt (költség / bájt).

- **Vezeték nélküli biztonság típusa**: Adja meg az eszközök hálózaton való hitelesítésére használt biztonsági protokollt. A következő lehetőségek közül:
  - **Nyissa meg a (nincs hitelesítés)**: Csak akkor használja ezt a beállítást, ha a hálózat nem biztonságos.
  - **WPA/WPA2-Personal**: Egy biztonságos lehetőséget, és a Wi-Fi kapcsolat gyakran használják. A további biztonság érdekében előre megosztott kulcsot vagy hálózati kulcsot is megadhat. 

    - **Előre megosztott kulcs** (PSK): Választható. Akkor jelenik meg, ha a **WPA/WPA2 (személyes)** biztonsági típust választja. A cég hálózatának beállítása vagy konfigurálása során a rendszer egy jelszót vagy egy hálózati kulcsot is konfigurál. Adja meg ezt a jelszót vagy hálózati kulcsot a PSK értékeként. 8–64 karakter közötti hosszúságú karakterláncot adjon meg. Ha a jelszó vagy a hálózati kulcs 64 karakterből áll, akkor hexadecimális karakteret adjon meg.
    
      > [!NOTE]
      > A Wi-Fi-profil mentésekor a PSK megadott értéke nem jelenik meg biztonsági okokból. Az előre megosztott kulcs vízjele továbbra is **Nincs konfigurálva** értéket mutat annak ellenére, hogy a PSK el van mentve a profilban. A PSK módosításához adjon meg egy új kulcsot, majd mentse a profilt. Ha a PSK mentésekor szerkeszti a szabályzatot, a PSK-t pedig üresen hagyja, továbbra is a meglévő PSK lesz használatban.

- **Céges proxybeállítások**: Választható a proxybeállításokat a szervezeten belül. A választható lehetőségek:
  - **Nincs**: Semmilyen proxybeállítás nincs konfigurálva.
  - **Manuálisan konfigurálnia a**: Adja meg a **proxykiszolgáló IP-cím** és a hozzá tartozó **portszám**.
  - **Automatikusan konfigurálhatja**: Adja meg a proxy automatikus konfigurációs (PAC) parancsfájl mutató URL-CÍMÉT. Például írja be a következőt: `http://proxy.contoso.com/proxy.pac`.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="enterprise-profile"></a>Vállalati profil

- **Wi-Fi típusa**: Válasszon **vállalati**. 

- **Wi-Fi neve (SSID)**: Rövid a szolgáltatáskészlet-azonosító. Ez az érték a valódi neve a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált **kapcsolatnevet** látják, amikor kiválasztják a kapcsolatot.

- **Kapcsolat neve**: Adjon meg egy felhasználóbarát nevet a Wi-Fi-kapcsolat. Az ide beírt szöveg a felhasználók számára megjelenő név, amikor a rendelkezésre álló kapcsolatokat böngészik az eszközeiken.

- **Automatikus csatlakozás, ha hatótávolságon belül van**: Amikor **Igen**, eszközök automatikus csatlakozás, ha a hálózat hatótávolságon belül. Ha a beállítás **Nem**, akkor az eszközök nem csatlakoznak automatikusan.
  - **Előnyben részesített hálózathoz csatlakozni, ha elérhető**: Ha az eszközök számos előnyben részesített hálózathoz, majd válassza ki **Igen** használatához az előnyben részesített hálózathoz. Válassza a **Nem** beállítást, hogy az ebben a konfigurációs profilban lévő Wi-Fi-hálózatot használják.

    Tegyük fel, hogy létrehozott egy **ContosoCorp** nevű Wi-Fi-hálózatot, és a **ContosoCorp** hálózatot használja ebben a konfigurációs profilban. Elérhető távolságban van egy **ContosoGuest** nevű Wi-Fi-hálózat is. Azt szeretné, hogy ha céges eszközei hatókörön belül vannak, automatikusan a **ContosoCorphoz** csatlakozzanak. Ebben az esetben állítsa a **Lehetőség szerint csatlakozás egy előnyben részesített hálózathoz** tulajdonságot **Nem** értékre.

  - **Ehhez a hálózathoz csatlakozni, akkor is, ha nem sugározza az SSID**: Válasszon **Igen** a konfigurációs profilok automatikusan csatlakoznak a hálózathoz, még akkor is, ha a hálózat el van rejtve (azaz, SSID nyilvánosan nem küldhetők). Válassza a **Nem** beállítást, ha nem szeretné, hogy ez a konfigurációs profil a rejtett hálózathoz csatlakozzon.

- **Mért kapcsolathoz megadott korlátot**: A rendszergazdák kiválaszthatják, hogy a hálózati forgalom forgalmi díjas. Alkalmazások ezt követően ennek a beállításnak az alapján módosíthatják a hálózati forgalommal kapcsolatos viselkedésüket. A választható lehetőségek:

  - **Korlátlan**: Default (Alapértelmezett): A rendszer nem méri a kapcsolatot, és nincs korlátozva a forgalom.
  - **Rögzített**: Használja ezt a beállítást, ha a hálózat úgy van konfigurálva, és a rögzített korlátja a hálózati forgalom. A korlát elérése után a hálózati hozzáférés le van tiltva.
  - **Változó**: Használja ezt a beállítást, ha a hálózati forgalmat a rangsorolt / bájt.

- **Egyszeri bejelentkezés (SSO)**: Egyszeri bejelentkezés (SSO), ahol számítógép megosztott hitelesítő adatokat, és a Wi-Fi hálózati bejelentkezés konfigurálását teszi lehetővé. A következő lehetőségek közül:
  - **Tiltsa le**: Egyszeri bejelentkezés viselkedésének letiltja. A felhasználónak külön kell hitelesítenie magát a hálózaton.
  - **Az eszköz felhasználó előtt engedélyezze**: Egyszeri bejelentkezés használatával hitelesíti a hálózathoz, a felhasználói bejelentkezési folyamat előtt.
  - **Engedélyezi az eszközre való felhasználó után**: Egyszeri bejelentkezés használatával közvetlenül a felhasználói bejelentkezési folyamat befejezése után a hálózati hitelesítést.
  - **Maximális idő az időkorlát lejárta előtt hitelesítést**: Adja meg a hitelesítést a hálózathoz, 1 – 120 másodperc időszakát (másodpercben) maximális számát.
  - **Adatkérés a felhasználónak a további hitelesítő adatok lehetővé teszik Windows**: Választás **Igen** lehetővé teszi a Windows rendszer kéri a felhasználótól a további hitelesítő adatokat, ha a hitelesítési módszer szükséges. A **Nem** beállítás elrejti ezeket a kéréseket.

- **Engedélyezze a páros főkulcs (PMK) gyorsítótárazását**: Válassza ki **Igen** a PMK-t a hitelesítéshez használt gyorsítótárazásához. Ez a gyorsítótárazás általában gyorsabb hálózati hitelesítést tesz lehetővé. A **Nem** beállítással megkövetelheti a hitelesítési kézfogást a Wi-Fi-hálózathoz való minden kapcsolódáskor.

  - **Maximális idő a PMK gyorsítótárban tárolt**: A páros főkulcs (PMK) tárolja a gyorsítótárban, az 5 – 1440 perc percek számát adja meg.
  - **Maximális száma a gyorsítótárban tárolt PMKs**: Adja meg az 1 – 255 a gyorsítótárban tárolt kulcsok.

- **Üzem előtti hitelesítés engedélyezése**: Előhitelesítés lehetővé teszi, hogy a profil csatlakozás előtt a hálózat a profilban található összes hozzáférési pontok hitelesítéséhez. Ha a felhasználók illetve az eszközök mozognak a hozzáférési pontok között, az előhitelesítés meggyorsítja az újracsatlakozást. **Igen** beállítással a profil a hálózat összes hatótávolságon belüli hozzáférési pontján hitelesíti magát. **Nem** beállítással a felhasználónak vagy eszköznek minden hozzáférési ponton külön kell hitelesítenie.

  - **Előhitelesítési kísérletek maximális száma**: Adja meg a megpróbálja preauthenticate, 1 – 16-tól.

- **EAP-típus**: Válassza ki az Extensible Authentication Protocol (EAP) biztonságos vezeték nélküli kapcsolatok hitelesítéséhez. A választható lehetőségek:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Védett EAP** (PEAP)

    **EAP-TLS, EAP-TTLS és PEAP további beállításai**:
    
    > [!NOTE]
    > EAP-típusok használata esetén jelenleg csak az SCEP-tanúsítványprofilok támogatottak. A PKCS-tanúsítványprofilok nem támogatottak. Amikor egy felhasználótól tanúsítvány megadását kérik, mindenképpen SCEP-tanúsítványt kell választani.

      - **Kiszolgáló megbízhatósága**  

        **Tanúsítvány-kiszolgálók nevei**: Használata **EAP-TLS**, **EAP-TTLS**, vagy **PEAP** EAP-típusok. Adjon meg egy vagy több, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a felhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.  

        **Kiszolgálói érvényesítéshez használandó főtanúsítványok**: Használata **EAP-TLS**, **EAP-TTLS**, vagy **PEAP** EAP-típusok. Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt.  

        **Identitásadatok védelme (külső identitás)**: Használata **PEAP** EAP-típus. Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.  

      - **Ügyfél-hitelesítés**

        **Ügyféltanúsítvány a hitelesítéshez használandó ügyféltanúsítványt (identitástanúsítványt)**: Használata **EAP-TLS** EAP-típus. Válassza ki a kapcsolat hitelesítéséhez használni kívánt tanúsítványprofilt.

        **Hitelesítési módszer**: Használata **EAP-TTLS** EAP-típus. Válassza ki a kapcsolat hitelesítési módszerét:  

          - **Tanúsítványok**: Jelölje be az ügyféltanúsítványt, amely a kiszolgálónak az identitás tanúsítványaként.
          - **Felhasználónév és jelszó**: Adjon meg egy **nem EAP-módszer (belső identitás)** hitelesítési módszert. A választható lehetőségek:

            - **Titkosítatlan jelszó (PAP)**
            - **Kérdés-kézfogás (CHAP)**
            - **Microsoft CHAP (MS-CHAP)**
            - **Microsoft CHAP 2-es verzió (MS-CHAP v2)**

        **Identitásadatok védelme (külső identitás)**: Használata **EAP-TTLS** EAP-típus. Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

- **Céges proxybeállítások**: Választható a proxybeállításokat a szervezeten belül. A választható lehetőségek:
  - **Nincs**: Semmilyen proxybeállítás nincs konfigurálva.
  - **Manuálisan konfigurálnia a**: Adja meg a **proxykiszolgáló IP-cím** és a hozzá tartozó **portszám**.
  - **Automatikusan konfigurálhatja**: Adja meg a proxy (PAC) automatikus konfigurációs parancsfájl mutató URL-CÍMÉT. Például írja be a következőt: `http://proxy.contoso.com/proxy.pac`.

- **Meg kell felelnie a a Federal Information feldolgozása Standard (FIPS) hogy a Wi-Fi profil kényszerített**: Válasszon **Igen** az FIPS 140-2 szabvány szerinti érvényességének ellenőrzése közben. Ennek a szabványnak a betartása kötelező az összes Egyesült Államokbeli Szövetségi kormányzati szerv részére, ahol titkosításon alapuló biztonsági rendszereket használnak a digitálisan tárolt bizalmas, de nem titkos minősítésű információk tárolására. Válassza a **Nem** lehetőséget, ha nem szeretne FIPS-megfelelőséget.

A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget. Ekkor létrejön a profil, és megjelenik a profilok listájában.

## <a name="use-an-imported-settings-file"></a>Importált beállításfájl használata

Az Intune-ban nem elérhető összes beállításhoz exportálhatja a Wi-Fi-beállításokat egy másik windowsos eszközből. Az exportálás az összes beállítást tartalmazó XML-fájlt hoz létre. Ez után importálja ezt a fájlt az Intune-ba, és használja Wi-Fi-profilként. Lásd: [Wi-Fi-beállítások exportálása és importálása Windows rendszerű eszközökhöz](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>További lépések

A profil létrejön, de egyelőre nem csinál semmit. A következő lépés a [profil hozzárendelése](device-profile-assign.md).

## <a name="more-resources"></a>További források

- A [Windows 8.1](wi-fi-settings-import-windows-8-1.md) rendszerhez rendelkezésre álló beállítások megtekintése.
- [Wi-Fi-beállítások áttekintése](wi-fi-settings-configure.md), beleértve más platformokat is
