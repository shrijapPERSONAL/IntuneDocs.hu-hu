---
title: "Az Intune tesztelése és ellenőrzése | Microsoft Docs"
description: "Ez a cikk részletesen ismerteti azokat a szempontokat, amelyeket figyelembe kell venni az Intune kizárólag felhőalapú megoldásának tesztelésénél és ellenőrzésénél saját környezetben."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f3ba0c5a58132c9749fb8ad7e134d1323952a3de
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="intune-testing-and-validation"></a>Az Intune tesztelése és ellenőrzése

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A tesztelési fázisnak a megvalósítás során és azt követően kell megtörténnie. Ehhez tesztfiókokra, csoportokra és eszközökre lesz szükség, amelyekkel az előzetesen azonosított szükséges informatikai (rendszergazdai) és végfelhasználói (használatieset-) forgatókönyveket tudja tesztelni.

A tesztelési folyamatba ajánlatos bevonni az informatikai és a támogatási munkatársakat, így elkészíthető a támogatási dokumentáció, és biztosítható, hogy a támogatási munkatársak megfelelő támogatást tudjanak nyújtani a termékhez. Ha a használati esetek alapján egyes összetevők vagy forgatókönyvek nem működnek megfelelően, a szükséges változtatásokat a változtatás okának feltüntetésével dokumentálni érdemes.

## <a name="before-you-begin"></a>Előkészületek

Az alábbiakat javasoljuk dokumentálni:

-   **Tesztkritériumok:** a méréshez használt referenciapontokat adja meg.

-   **Szerkezeti összetevők:** legalább egy tesztkritériumban szerepelniük kell.

Ha egy adott szerkezeti összetevő nem szerepel legalább egy olyan tesztkritériumban, amely követelményhez vagy forgatókönyvhöz társul, érdemes megfontolni, valóban szükség van-e rá. Az alábbiak ugyancsak szükségesek:

-   **Fiókok:** ahhoz, hogy az összes használatieset-forgatókönyvet tesztelni lehessen, a teszthez használt tesztfiókoknak EMS- és Office 365-licenccel kell rendelkezniük.

-   **Eszközök:** ebben a fázisban olyan teszteszközöket ajánlatos használni, amelyeken szükség esetén vissza lehet állítani a gyári beállításokat, vagy törölni lehet róluk az adatokat.

-   **Integrálási összetevők:** szükség szerint telepíteni és konfigurálni kell az integrálási összetevőket (a tanúsítvány-összekötőt, az Intune szolgáltatások közötti összekötőt az üzemeltetett Exchange-hez, valamint az Intune helyszíni Exchange-összekötőt).

Az előre nem látható problémák elhárításához szerkezetátalakításokra lehet szükség. Minden szerkezeti változást teljes körűen dokumentálni kell a változás okának feltüntetésével. Az alábbi példa azt mutatja meg, mi indokolhat ilyen változást:

-   Kiderülhet, hogy nem teljesülnek az NDES (hálózati eszközök tanúsítványigénylési szolgáltatása) feltételei, mindemellett azonban legfelső szintű hitelesítésszolgáltatóval is konfigurálhatók a VPN- és a Wi-Fi profilok, és így is teljesíthetők ugyanezen feltételek NDES-megoldás nélkül is.

Előfordulhat, hogy a tesztelés és ellenőrzés során olyan problémák vagy kérdések merülnek fel, amelyek műszaki útmutatást vagy speciális hibaelhárítást tesznek szükségessé. Javasoljuk, hogy forduljon segítségért a Microsofthoz valamely támogatási csatornáján keresztül.

-   [Útmutató Intune-támogatás kéréséhez](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Általános hibaelhárítási tippek a Microsoft Intune-hoz](/intune-classic/troubleshoot/general-troubleshooting-tips-for-microsoft-intune).

-   [Hogyan kérhet támogatást a Microsoft Intune-hoz.]/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Kapcsolatfelvétel a Microsoft Intune telefonos tanácsadással](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Funkcionális ellenőrzési tesztelés

A funkcionális ellenőrzési tesztelés során minden egyes összetevő és konfiguráció tesztelésre kerül, melynek során megállapítható, hogy azok megfelelően működnek-e. Az alábbi táblázatban a funkcionális ellenőrzési tesztelésre látható példa.

![9. szakasz, 1. táblázat](../media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Használatieset-ellenőrzési tesztelés

A használatieset-ellenőrzési tesztelés a használati forgatókönyvek teljességének és működőképességének tesztelésére szolgál. A használatieset-forgatókönyveknek két típusa van: rendszergazdai és végfelhasználói.

### <a name="it-admin"></a>Rendszergazdai

A rendszergazdai ellenőrzési tesztelés célja annak ellenőrzése, hogy az eszközökre és a felhasználókra irányuló rendszergazdai tevékenységek megfelelően működnek-e. Az alábbiakban egy teljes körű rendszergazdai ellenőrzésre talál példát.

![9. szakasz, 2. táblázat](../media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Végfelhasználó

A végfelhasználói ellenőrzési tesztelés célja annak ellenőrzése, hogy a végfelhasználói élmény az elvárásoknak megfelelő-e, és hogy megfelelően jelenik-e meg minden felhasználói kommunikáció során. A végfelhasználói élmény ellenőrzése különösen is fontos, hiszen ennek elmaradása a bevezetési szakasz sikerét csökkentheti, és a támogatási segítségkérések számának megnövekedéséhez vezethet.

![9. szakasz, 3. táblázat](../media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>További lépések

Most, hogy elvégezte az Intune funkcionális és használatieset-forgatókönyveinek ellenőrzését és tesztelését, készen áll az Intune használatára éles környezetben. Bővebb információt a [További forrásokban](additional-resources.md) talál.

