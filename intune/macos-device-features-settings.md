---
title: macOS eszközfunkció-beállítások a Microsoft Intune – Azure |} A Microsoft Docs
description: Tekintse meg a beállítások macOS-eszközök konfigurálhatja az AirPrint és testre szabhatja a bejelentkezési ablakban, a Microsoft Intune-ban power gomb megjelenítése vagy elrejtése. Tekintse meg a lépéseket a az IP-cím, elérési útja és portbeállítások az AirPrint-kiszolgáló a hálózaton. Az eszközkonfigurációs profil ezek a beállítások segítségével konfigurálhatja a macOS eszközök funkciói.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8997cb8f3e36367de06d6e5aa1c7c6971ee905a4
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896372"
---
# <a name="macos-device-feature-settings-in-intune"></a>macOS eszközfunkció-beállítások az Intune-ban

Az Intune beépített beállítások segítségével testre szabhatja a macOS-eszközök funkcióinak tartalmaz. Ez a cikk ezeket a beállításokat, és ismerteti az egyes beállítások funkciója. Azt is megjeleníti a lépéseket a az IP-cím, elérési útja és a terminál alkalmazással (emulátor) port az AirPrint-nyomtatókhoz.

Ez a funkció az alábbiakra vonatkozik:

- macOS

A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a beállításokat, hozzon létre egy szalagcím, válassza ki, hogy a felhasználók hogyan jelentkeznek be, az AirPrint-kiszolgáló, és felvenni.

Ezek a beállítások hozzá egy eszközkonfigurációs profilt az Intune-ban, és ezután hozzárendelt vagy a macOS-eszközökre telepített.

## <a name="before-you-begin"></a>Előkészületek

[A macOS-eszközkonfigurációs profil létrehozása](device-features-configure.md).

## <a name="airprint"></a>AirPrint

- **IP-cím**: Adja meg a nyomtató IPv4 vagy IPv6-címét. Ha állomásnevek nyomtatók azonosítására használ, a nyomtató a terminál alkalmazásban történő megpingelésével beszerezheti az IP-címet. [Az IP-cím és az elérési út](#get-the-ip-address-and-path) (a jelen cikkben) további információt talál.
- **Elérési út**: Adja meg a nyomtató elérési útját. Az elérési út általában `ipp/print` nyomtatók a hálózaton. [Az IP-cím és az elérési út](#get-the-ip-address-and-path) (a jelen cikkben) további információt talál.
- **Port** (az iOS 11.0-s és újabb verziók): Adja meg az AirPrint-célhely figyelőportja. Ha üresen hagyja ezt a tulajdonságot, az AirPrint az alapértelmezett portot használ.
- **A TLS** (az iOS 11.0-s és újabb verziók): Válassza ki **engedélyezése** AirPrint-kapcsolatok a Transport Layer Security (TLS) biztonságos.

**Adjon hozzá** az AirPrint-kiszolgáló. Számos AirPrint-kiszolgálókat is hozzáadhat.

- **Importálás** (nem kötelező): Emellett **importálás** egy vesszővel tagolt fájlt (.csv), amely tartalmazza az AirPrint-nyomtatókra listáját. Miután hozzáadta az AirPrint-nyomtatókra az Intune-ban, azt is megtehetjük, **exportálása** ebben a listában.

Válassza ki **OK** a beállítások mentéséhez.

## <a name="login-window"></a>Bejelentkezési ablak

### <a name="window-layout"></a>Ablak

- **További információ megjelenítése a menüsoron**: Ha a menüsávon az idő területen van jelölve, **engedélyezése** a gazdagép nevét és a macOS-verziókat mutatja. **Nincs konfigurálva** (alapértelmezett) nem jelenik meg ez az információ a menüsávon.
- **Banner**: Adjon meg egy üzenetet, amely a bejelentkezési az eszközön képernyő jelenik meg. Adja meg például a szervezet adatait, egy üdvözlő üzenet, a talált adatokat, és így tovább.
- **Válassza ki a bejelentkezési formátum**: Válassza ki, hogyan jelentkeznek be az eszközt. A választható lehetőségek:
  - **Rákérdezés a felhasználónév és jelszó** (alapértelmezett): A felhasználók beírjanak egy felhasználónevet és jelszót igényel.
  - **Minden felhasználó, jelszó kérése listában**: A felhasználónak a felhasználóneve a felhasználó listából ki, és adja meg a jelszavát kell. Is konfigurálhatja:

    - **A helyi felhasználók**: **Elrejtése** nem jelenik meg a helyi felhasználói fiókokat a felhasználók listájában, amelyek magukban foglalhatják a standard és a rendszergazdai fiókokat. Csak a hálózati és rendszerkövetelményeivel felhasználói fiókok jelennek meg. **Nincs konfigurálva** (alapértelmezett) a helyi felhasználói fiókok jelennek meg a felhasználók listájában.
    - **Mobil fiókok**: **Elrejtése** mobil fiókok nem jelenik meg a felhasználók listájában. **Nincs konfigurálva** (alapértelmezett) a mobil fiókok jelennek meg a felhasználók listájában. Előfordulhat, hogy a hálózati felhasználók szabályzatként jelenik meg néhány mobil fiókot.
    - **A hálózati felhasználók**: Válassza ki **megjelenítése** listázhatja a hálózati felhasználók a felhasználói listájában. **Nincs konfigurálva** (alapértelmezett) nem jelenik meg a hálózat felhasználói fiókokat a felhasználók listájában.
    - **Rendszergazda felhasználók**: **Elrejtése** nem jelenik meg a rendszergazda felhasználói fiókokat a felhasználók listájában. **Nincs konfigurálva** (alapértelmezett) jeleníti meg a rendszergazda felhasználói fiókokat a felhasználók listájában.
    - **Más felhasználók**: Válassza ki **megjelenítése** listához **más...**  felhasználók a felhasználói listájában. **Nincs konfigurálva** (alapértelmezett) nem jelenik meg a felhasználói fiókokat a felhasználók listájában.

### <a name="login-screen-power-settings"></a>Bejelentkezési képernyő energiaellátási beállítások

- **Leállítás gomb**: **Elrejtése** a leállítási gomb nem jelenik meg a bejelentkezési képernyőn. **Nincs konfigurálva** (alapértelmezett) jeleníti meg a Leállítás gombra.
- **Indítsa újra a gomb**: **Elrejtése** az újraindítás gomb nem jelenik meg a bejelentkezési képernyőn. **Nincs konfigurálva** (alapértelmezett) jeleníti meg az Újraindítás gombra.
- **Alvás gomb**: **Elrejtése** az Alvás gomb nem jelenik meg a bejelentkezési képernyőn. **Nincs konfigurálva** (alapértelmezett) az Alvás gomb látható.

### <a name="other"></a>Egyéb

- **Tiltsa le a felhasználói bejelentkezést konzolról**: **Tiltsa le** elrejti a macOS parancssori való bejelentkezéshez használt. Jellemző felhasználók **letiltása** ezt a beállítást. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi a speciális jelentkezzen be a macOS-parancssor használatával. Adja meg a konzol üzemmódban, hogy a felhasználóknak megadniuk `>console` a felhasználónév mezőben, majd a konzolablakban kell hitelesítenie.

### <a name="apple-menu"></a>Apple menü

Után a felhasználók bejelentkeznek az eszközök, hatással a következő beállításokat, azok felhasználásáról.

- **Tiltsa le a Leállítás le**: **Tiltsa le** megakadályozza, hogy a felhasználók kiválasztása a **leállítási** lehetőséget, miután a felhasználó bejelentkezik. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi a felhasználóknak, hogy a **leállítási** menüpont az eszközön.
- **Újraindítás letiltása**: **Tiltsa le** megakadályozza, hogy a felhasználók kiválasztása a **indítsa újra a** lehetőséget, miután a felhasználó bejelentkezik. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi a felhasználóknak, hogy a **indítsa újra a** menüpont az eszközön.
- **Kiemelt letiltása ki**: **Tiltsa le** megakadályozza, hogy a felhasználók kiválasztása a **kikapcsolásához** lehetőséget, miután a felhasználó bejelentkezik. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi a felhasználóknak, hogy a **kikapcsolásához** menüpont az eszközön.
- **Tiltsa le a Kijelentkezés** (macOS 10.13 és újabb verziók): **Tiltsa le** megakadályozza, hogy a felhasználók kiválasztása a **jelentkezzen ki** lehetőséget, miután a felhasználó bejelentkezik. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi a felhasználóknak, hogy a **Kijelentkezés** menüpont az eszközön.
- **Tiltsa le a zárolási képernyőn** (macOS 10.13 és újabb verziók): **Tiltsa le** megakadályozza, hogy a felhasználók kiválasztása a **zárolási képernyő** lehetőséget, miután a felhasználó bejelentkezik. **Nincs konfigurálva** (alapértelmezett) lehetővé teszi a felhasználóknak, hogy a **zárolási képernyő** menüpont az eszközön.

Válassza ki **OK** a beállítások mentéséhez.

## <a name="get-the-ip-address-and-path"></a>Az IP-cím és az elérési út

Az IP-címét a nyomtatót, az erőforrás elérési útja és a portot kell AirPrinter-kiszolgálók hozzáadásához. A következő lépések bemutatják, hogyan beolvasni ezeket az információkat.

1. Az azonos helyi hálózatra (alhálózatra), az AirPrint-nyomtatókra csatlakoztatott Mac számítógépen nyissa meg a **terminálon** (a **/Applications/Utilities**).
2. A Terminálszolgáltatások alkalmazásban írjon be `ippfind`, és válassza ki, adja meg.

    Megjegyzés: a nyomtató-információkat. Például előfordulhat, hogy vissza valami hasonló `ipp://myprinter.local.:631/ipp/port1`. Az első része a nyomtató neve. A második (`ipp/port1`) az erőforrás elérési útja.

3. A Terminalba írja be a `ping myprinter.local`, és válassza ki, adja meg.

   Megjegyzés: az IP-címet. Például előfordulhat, hogy vissza valami hasonló `PING myprinter.local (10.50.25.21)`.

4. IP-cím és az erőforrás elérési útja értéket használja. Ebben a példában az IP-cím van `10.50.25.21`, és az erőforrás-elérési út `/ipp/port1`.

## <a name="next-steps"></a>További lépések

- A megadott beállítások megjelenítéséhez [iOS](ios-device-features-settings.md) eszközök.
- [Ez a profil hozzárendelése](device-profile-assign.md) a csoportokhoz és [állapotát nyomon](device-profile-monitor.md).
