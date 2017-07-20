---
title: "Az Intune tesztelése és ellenőrzése"
description: "Egy kizárólag felhőalapú Intune-beli megoldás a környezetben történő tesztelésekor és érvényesítésekor megfontolandó szempontok."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: ddeb71c6a678ff42b5075d65c2bb4e0d89ae47f1
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2017
---
# <a name="intune-testing-and-validation"></a>Az Intune tesztelése és ellenőrzése

A tesztelési fázisra a megvalósítási fázis alatt és azután kerül sor. Az összes előzetesen azonosított szükséges informatikai (rendszergazdai) és végfelhasználói (használatieset-) forgatókönyv teszteléséhez tesztfiókokra, -csoportokra és -eszközökre van szükség.

A tesztelési folyamatba ajánlatos bevonni az informatikai és a támogatási munkatársakat, így elkészíthető a támogatási dokumentáció, és biztosítható, hogy a támogatási munkatársak megfelelő támogatást tudjanak nyújtani a termékhez. Ha a használati esetek alapján egyes összetevők vagy forgatókönyvek nem működnek megfelelően, a szükséges változtatásokat a változtatás okának feltüntetésével dokumentálni érdemes.

## <a name="before-you-begin"></a>Előkészületek

Ajánlott dokumentálni a következőket:

-   **Tesztkritériumok:** a méréshez használt referenciapontokat adja meg.

-   **Szerkezeti összetevők:** legalább egy tesztkritériumban szerepelniük kell.

Ha egy adott szerkezeti összetevő nem szerepel legalább egy olyan tesztkritériumban, amely követelményhez vagy forgatókönyvhöz társul, érdemes megfontolni, valóban szükség van-e rá. Az alábbiak ugyancsak szükségesek:

-   **Fiókok:** ahhoz, hogy az összes használatieset-forgatókönyvet tesztelni lehessen, a tesztfiókoknak EMS- és Office 365-licenccel kell rendelkezniük.

-   **Eszközök:** törölhető vagy a gyári beállításokra visszaállítható teszteszközök.

-   **Integrálási összetevők:** szükség szerint telepíteni és konfigurálni kell az integrálási összetevőket (a tanúsítvány-összekötőt, az Intune szolgáltatások közötti összekötőt az üzemeltetett Exchange-hez, valamint az Intune helyszíni Exchange-összekötőt).

Az előre nem látható problémák elhárításához szerkezetátalakításokra lehet szükség. Minden szerkezeti változást teljes körűen dokumentálni kell a változás okának feltüntetésével. Az alábbi példa azt mutatja meg, mi indokolhat ilyen változást:

<blockquote>Kiderülhet, hogy nem teljesülnek az NDES (hálózati eszközök tanúsítványigénylési szolgáltatása) feltételei, mindemellett azonban legfelső szintű hitelesítésszolgáltatóval is konfigurálhatók a VPN- és a Wi-Fi profilok, és így is teljesíthetők ugyanezen feltételek NDES-megoldás nélkül is.</blockquote>

Előfordulhat, hogy a tesztelés és ellenőrzés során olyan problémák vagy kérdések merülnek fel, amelyek műszaki útmutatást vagy speciális hibaelhárítást tesznek szükségessé. Javasoljuk, hogy forduljon segítségért a Microsofthoz valamely támogatási csatornáján keresztül.

-   [Útmutató Intune-támogatás kéréséhez](get-support.md)

-   [Kapcsolatfelvétel a Microsoft Intune telefonos tanácsadással](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Funkcionális ellenőrzési tesztelés

A funkcionális ellenőrzési tesztelés során minden egyes összetevő és konfiguráció tesztelésre kerül, melynek során megállapítható, hogy azok megfelelően működnek-e. Az alábbi táblázatban a funkcionális ellenőrzési tesztelésre látható példa.

![9. szakasz, 1. táblázat](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Használatieset-ellenőrzési tesztelés

A használatieset-ellenőrzési tesztelés a használati forgatókönyvek teljességének és működőképességének tesztelésére szolgál. A használatieset-forgatókönyveknek két típusa van: rendszergazdai és végfelhasználói.

### <a name="it-admin"></a>Rendszergazdai

A rendszergazdai ellenőrzési tesztelés célja annak ellenőrzése, hogy az eszközökre és a felhasználókra irányuló rendszergazdai tevékenységek megfelelően működnek-e. Az alábbiakban egy teljes körű rendszergazdai ellenőrzésre talál példát.

![9. szakasz, 2. táblázat](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Végfelhasználó

A végfelhasználói ellenőrzési tesztelés célja annak ellenőrzése, hogy a végfelhasználói élmény az elvárásoknak megfelelő-e, és hogy megfelelően jelenik-e meg minden felhasználói kommunikáció során. Fontos ellenőrizni, hogy megfelelő-e a végfelhasználói élmény. Ennek elmaradása a bevezetési szakasz sikerét csökkentheti, és a támogatási segítségkérések számának megnövekedéséhez vezethet.

![9. szakasz, 3. táblázat](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>További lépések

Most, hogy elvégezte az Intune funkcionális és használatieset-forgatókönyveinek ellenőrzését és tesztelését, készen áll az [Intune használatára éles környezetben](planning-guide-rollout-plan.md).

További tervezési sablonokért és információkért lásd a [további erőforrásokat](planning-guide-resources.md).
