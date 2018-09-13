---
title: Eszközszabályzatok, profilok és Q&A az Intune-nal – Azure | Microsoft Docs
description: Olvassa el a Microsoft Intune-ban használható különböző szabályzatokra és profilokra, többek között az eszközök konfigurációját, a céges erőforrások elérését, a feltételes hozzáférés engedélyezését és a vállalati eszközök regisztrálását lehetővé szabályzatokra vonatkozó információkat. A gyakori kérdésekre is választ kaphat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8a7a7405fe40d3568e736c244d9fcb308350709
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43318004"
---
# <a name="manage-settings-and-features-on-your-devices-with-intune-policies"></a>Az eszközök beállításainak és funkcióinak kezelése az Intune-házirendek használatával

A Microsoft Intune *-szabályzatok* a mobileszközök és a számítógépek funkcióit szabályozó beállítások csoportjai. A szabályzatokat sablonok használatával hozhatja létre, amelyek tartalmaznak ajánlott és egyéni beállításokat. Ezt követően telepítheti őket az eszköz- vagy felhasználócsoportokhoz.

## <a name="types-of-policies"></a>Szabályzatok típusai

Az Intune-szabályzatok két kategóriába sorolhatók: A használt kategória befolyásolja a szabályzat létrehozását és telepítését.

- **Konfigurációs szabályzatok:** Ezek általában az eszközök biztonsági beállításainak és szolgáltatásainak, többek között a vállalati erőforrások elérésének a kezelésére használhatók. Első lépések az [Intune-eszközprofilok](device-profiles.md) használatában.
- **Eszközmegfelelőségi szabályzatok:** Meghatározzák azokat a szabályokat és beállításokat, amelyeknek az eszköznek meg kell felelnie, hogy a feltételes hozzáférési szabályzatok szerint megfelelő legyen. A megfelelőségi szabályzatokkal a feltételes hozzáféréstől függetlenül is megfigyelheti és kijavíthatja az eszközök megfelelőséggel kapcsolatos hibáit. [Eszközmegfelelőségi szabályzatok – első lépések](device-compliance-get-started.md).
- **Feltételes hozzáférési szabályzatok:** Ezekkel a szabályzatokkal a megadott feltételek alapján biztosíthatja a levelezés és más szolgáltatások védelmét. A [Mi a feltételes hozzáférés](conditional-access.md) és [a feltételes hozzáférés használatának szokásos módjai](conditional-access-intune-common-ways-use.md) jó erőforrások a kezdéshez.
- **Vállalati eszközregisztrációs szabályzatok:** A vállalati eszközregisztrációs szabályzatokra vonatkozó információért lásd: [iOS-eszközök regisztrálása](ios-enroll.md).

## <a name="frequently-asked-questions-about-intune-policies"></a>A Microsoft Intune szabályzataival kapcsolatban gyakran felmerülő kérdések

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-being-deployed"></a>Mennyi időt vesz igénybe, hogy a mobileszközök megkapják a szabályzatot vagy az alkalmazásokat a telepítésük után?
Szabályzat vagy alkalmazás üzembe helyezésekor az Intune azonnal értesíti az eszközt arról, hogy be kell jelentkeznie az Intune szolgáltatásba. Ez a lépés általában öt percnél kevesebb időt vesz igénybe.

Ha az eszköz az első értesítés után nem jelentkezik be, hogy beszerezze a szabályzatot, az Intune három további kísérletet tesz.  Ha az eszköz kapcsolat nélküli állapotban van (például ki van kapcsolva, vagy nem kapcsolódik hálózathoz), előfordulhat, hogy nem kapja meg az értesítéseket. Ebben az esetben az eszköz az Intune szolgáltatásba való következő ütemezett bejelentkezéskor szerzi be a szabályzatot a következő módon:

| Platform | Bejelentkezési gyakoriság |
| --- | --- |
| iOS | 6 óránként | 
| Mac OS X | 6 óránként |
| Android | 8 óránként | 
| Windows Phone | 8 óránként | 
| Windows 8.1  | 8 óránként |  
| Eszközként regisztrált Windows 10 számítógépek | 8 óránként | 

Ha az eszköz nemrég lett regisztrálva, a bejelentkezés gyakoribb lesz, a következőképpen:

| Platform | Gyakoriság |
| --- | --- |
| iOS | 6 órán át 15 perceként, majd 6 óránként |  
| Mac OS X | 6 órán át 15 perceként, majd 6 óránként | 
| Android | 15 percen át 3 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Windows Phone | 15 percen át 5 percenként, majd 2 órán át 15 percenként, majd 8 óránként | 
| Eszközként regisztrált Windows-számítógépek | 30 percen át 3 percenként, majd 8 óránként | 

A felhasználók emellett a Céges portál alkalmazás megnyitásával bármikor jelentkezhetnek a szabályzat beszerzéséhez.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Milyen műveletek hatására küld az Intune azonnal értesítést egy eszközre?
Az eszközök akkor jelentkeznek be az Intune-ba, amikor bejelentkezési értesítést kapnak, vagy amikor a rendszeres ütemezésű bejelentkezés esedékessé válik.  Ha a művelet, például a törlés, a zárolás, a jelszó-visszaállítás, az alkalmazástelepítés, a profiltelepítés (Wi-Fi, VPN, e-mail stb.) vagy a szabályzattelepítés kifejezetten egy eszközre vagy felhasználóra vonatkozik, az Intune azonnal megpróbálja értesíteni az eszközt, hogy be kell jelentkeznie az Intune szolgáltatásba.

Az egyéb módosítások – például a kapcsolattartási adatok módosítása a céges portálon – nem indítják el az azonnali értesítések küldését az eszközök felé.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-are-applied"></a>Ha ugyanazon felhasználó vagy eszköz számára több szabályzat is települ, honnan tudható, hogy mely beállítások lesznek érvényben?
Ha kettő vagy több szabályzatot telepít ugyanazon felhasználó vagy eszköz számára, az alkalmazni kívánt beállítás értékelése az egyes beállítások szintjén történik:

- A megfelelőségi házirend-beállítások mindig prioritást élveznek a konfigurációs házirend-beállításokkal szemben.

- Ha egy beállítás több megfelelőségi szabályzatban is szerepel, akkor a szigorúbb megfelelőségi beállítás lesz érvényes.

- Ha egy konfigurációs szabályzatbeállítás ütközik egy másik konfigurációs szabályzatbeállítással, az ütközés az Intune-ban is megjelenik. Ezeket az ütközéseket manuálisan kell feloldani.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-applies-to-the-app"></a>Mi történik, ha a mobilalkalmazás-kezelési házirendek ütköznek egymással? Melyik vonatkozik az alkalmazásra?
Az ütközési értékek a MAM-szabályzatok legkorlátozóbb beállításai a számbeviteli mezők kivételével (ilyen például a PIN-kód bevitelével való próbálkozások száma az alaphelyzetbe állítás előtt).  A számbeviteli mezők értékei megegyeznek a – javasolt beállításokkal a konzolban létrehozható – MAM-szabályzatok értékeivel.

Akkor történik ütközés, ha két azonos házirend-beállítás van.  Például előfordulhat, hogy a másolás/beillesztés beállításra két megegyező MAM-házirendet konfigurált.  Ebben az esetben a másolás/beillesztés a legszigorúbb értékre lesz beállítva, a többi beállítás pedig a konfiguráltak szerint lesz alkalmazva.

Ha az alkalmazáshoz telepít és érvénybe léptet egy szabályzatot, majd egy másikat is telepít, akkor az első elsőbbséget élvez és érvényben marad. A második szabályzat ütközőként jelenik meg. Ha egyszerre telepíti őket, tehát nincs megelőző szabályzat, akkor mindkettő ütközést jelez. Minden ütközésnél a legszigorúbb beállítás lesz érvényes.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>Mi történik, ha az egyéni iOS-házirendek ütköznek?
Az Intune nem értékeli a konfigurációs Apple-fájlok vagy az Open Mobile Alliance egységes erőforrás-azonosítóra (OMA-URI) vonatkozó egyéni szabályzatainak tartalmát. Csak kézbesítési mechanizmusként funkcionál.

Ha egyéni szabályzatot telepít, erősítse meg, hogy a konfigurált beállítások nem ütköznek a megfelelőségi, konfigurációs vagy az egyéb egyéni szabályzatokkal. Ha egyéni szabályzatok tartalmaznak beállítási ütközést, akkor a beállítások alkalmazásának sorrendje véletlenszerű.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Mi történik, ha egy szabályzatot törölnek, vagy a szabályzat alkalmazhatatlanná válik?
Amikor töröl egy szabályzatot, vagy eltávolít egy olyan eszközt a csoportból, amelyen telepített szabályzat van, akkor a szabályzat és a beállítások a következő listákban szereplők szerint törlődnek az adott eszközről.

#### <a name="enrolled-devices"></a>Regisztrált eszközök

- Wi-Fi, VPN, tanúsítvány és e-mail profilok: Ezek a profilok az összes támogatott regisztrált eszközről el lesznek távolítva.
- Minden egyéb házirendtípus:
  - **Windows és Android rendszerű eszközök**: A beállítások nem törlődnek az eszközről.
  - **Windows Phone 8.1 rendszerű eszközök**: A következő beállítások törlődnek:
    - Jelszó szükséges a mobileszközök feloldásához
    - Egyszerű jelszavak engedélyezése
    - Jelszó minimális hossza
    - Kötelező jelszótípus
    - Jelszó lejárata (nap)
    - Jelszóelőzmények megjegyzése
    - Sikertelen bejelentkezések engedélyezett száma az eszköz törlése előtt
    - Tétlen percek száma, mielőtt az eszköz újból kéri a jelszót
    - Kötelező jelszótípus – megadandó karakterek minimális száma
    - Kamera használatának engedélyezése
    - Mobileszköz titkosításának kötelezővé tétele
    - Cserélhető tároló használatának engedélyezése
    - Webböngésző használatának engedélyezése
    - Alkalmazástároló használatának engedélyezése
    - Képernyőfelvétel-készítés használatának engedélyezése
    - Földrajzi hely meghatározásának engedélyezése
    - Microsoft-fiók használatának engedélyezése
    - Másolás és beillesztés használatának engedélyezése
    - Wi-Fi alapú internetmegosztás használatának engedélyezése
    - Wi-Fi elérési pontokhoz való automatikus csatlakozás engedélyezése
    - Wi-Fi elérési pontok jelentéskészítésének engedélyezése
    - Összes adat törlésének engedélyezése
    - Bluetooth használatának engedélyezése
    - NFC használatának engedélyezése
    - Wi-Fi használatának engedélyezése

  - **iOS**: Az összes beállítás törlődik, kivéve a következőket:
    - Hangroaming engedélyezése
    - Adatroaming engedélyezése
    - Automatikus szinkronizálás engedélyezése roaming közben

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Hol találhatok segítséget a szabályzatokkal kapcsolatos problémák elhárításához?

Lásd: [Szabályzatokkal kapcsolatos problémák elhárítása](troubleshoot-policies-in-microsoft-intune.md).
