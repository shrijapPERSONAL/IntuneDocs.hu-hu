---
title: Alkalmazásvédelmi szabályzatok és a munkahelyi profilok Microsoft Intune - Azure-ban |} A Microsoft Docs
description: Az alkalmazásvédelmi szabályzatok használatára, vagy munkahelyi profilok személyes vagy vállalati BYOD-Android-eszköz Microsoft Intune-ban annak eldöntése során, tekintse meg az eltérések és és hátrányai. Hasonlítsa össze a különbségek és funkciónak, a regisztráció nélküli alkalmazásvédelmi szabályzatokat (alkalmazás-TUDJUK) és a munkahelyi profilok Android Enterprise.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6fd12432d07d1486e0943f88c0cf8b4536e651bc
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236500"
---
# <a name="application-protection-policies-and-work-profiles-on-android-enterprise-devices-in-intune"></a>Alkalmazásvédelmi szabályzatok és a munka alkalmazásprofilok a vállalati Android-eszköz Intune-ban

Számos szervezet rendszergazdák esetében merül fel erőforrásokat és a különböző eszközökön található adatok védelme. Az egyik kihívás védi az erőforrások a felhasználók számára személyes vállalati Android-eszköz, más néven a saját-eszközök használata (BYOD). A Microsoft Intune-saját-eszközök használata (BYOD) két Android üzembe helyezési forgatókönyvet támogatja:

- Regisztráció nélküli alkalmazásvédelmi szabályzatokat (alkalmazás-hogy)
- Vállalati androidos munkahelyi profilok

Az alkalmazás-azt, és az Androidos munkahelyi profil központi telepítési forgatókönyv az alábbi főbb szolgáltatásokat fontos a BYOD-környezetekhez:

1. **Védelem és a szervezet által kezelt adatok elkülönítése**: A két megoldás tartat be a szervezet által kezelt adatok adatveszteség-megelőzési (DLP) vezérlést szervezeti adatok védelme. Ezek a védelmi a védett adatok véletlen megosztása egy személyes alkalmazásba vagy a fiók a felhasználó például véletlen adatszivárgás megelőzése. Is szolgálnak annak biztosításához, hogy az adatok elérése eszköz kifogástalan állapotú, és nem sérült.

2. **A végfelhasználói adatvédelmi**: Alkalmazás-TUDJUK Android Enterprise munkahelyi profilokkal külön végfelhasználók számára az eszköz tartalmát, és a mobileszköz-felügyelet (MDM) rendszergazda felügyeli adatokat. Mindkét esetben a rendszergazdák szabályzatok, például csak PIN-kód hitelesítést a szervezet által felügyelt alkalmazások és identitások kényszerítése. IT-rendszergazdák nem tudnak olvasása, elérése és törlése a végfelhasználók által birtokolt vagy szabályozott adatokat.

Választotta-e alkalmazás-TUDJUK vagy az Android Enterprise munkahelyi profilok és az üzleti és függ a BYOD-telepítés szükséges. Ez a cikk célja, az segít eldönteni, hogy útmutatást nyújt.

## <a name="about-intune-app-protection-policies"></a>Tudnivalók az Intune alkalmazásvédelmi szabályzatai

Az Intune alkalmazásvédelmi szabályzatai (alkalmazás) a felhasználók számára megcélzott adatvédelmi szabályzatok. A szabályzatok érvényesek az alkalmazás szintjén adatvesztés ellen. Az Intune APP szükséges alkalmazásfejlesztők hozhatnak létre alkalmazásokat az alkalmazás-szolgáltatások engedélyezése.

Egyéni Android-alkalmazások engedélyezettek az alkalmazás több módon is:

1. **Belső Microsoft-alkalmazások natív módon integrálva**: Android és a egy kijelölt más Microsoft-alkalmazások, Microsoft Office-alkalmazásokat az Intune APP beépített kapható. Ezen Office-alkalmazások, például a Word, OneDrive, az Outlook és így tovább, nincs szükség semmilyen további testreszabási alkalmazni a házirendeket. Ezeket az alkalmazásokat a Google Play Store közvetlenül a végfelhasználók által telepíthető.

2. **Az Intune SDK-t használó fejlesztők által integrált alkalmazás buildek**: Alkalmazás a fejlesztők az Intune SDK integrálása forráskódjukat és újrafordítottuk alkalmazásaikat az Intune APP házirend funkciók támogatásához.

3. **Burkolt be, az Intune app wrapping tool használatával**: Egyes ügyfeleink fordítsa le az Android-alkalmazások (. APK-fájlt) forráskód való hozzáférés nélkül. A forráskódban nélkül a fejlesztői nem integrálható az Intune SDK. Az SDK-t, anélkül hogy az alkalmazás számára az alkalmazás-szabályzatok lehetővé teszik nem. A fejlesztőnek kell módosítása vagy a recode szabályzatok támogatásához az alkalmazás.

    Annak érdekében, az Intune tartalmaz a **App Wrapping Tool** meglévő Android-alkalmazások (APKs) eszközt, és létrehoz egy alkalmazást, amely felismeri az alkalmazás-szabályzatok.

    További információkért lásd: [üzleti alkalmazások alkalmazásvédelmi szabályzatokkal repare](apps-prepare-mobile-application-management.md).

Az alkalmazás engedélyezett alkalmazások listáját, olvassa el [felügyelt alkalmazások széles választékának mobilalkalmazás-védelmi szabályzatok](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="deployment-scenarios"></a>Központi telepítési forgatókönyvek

Ez a szakasz ismerteti az alkalmazás fontos jellemzőit – a Microsoft és az Android Enterprise munkahelyi profil központi telepítési forgatókönyv.

#### <a name="app-we"></a>APP-WE

Alkalmazás-azt (alkalmazásvédelmi szabályzatokat nem regisztrált) központi telepítés definiálja a szabályzatokat, az alkalmazásokat, nem az eszközökhöz. Ebben a forgatókönyvben az eszközök általában nem regisztrált vagy MDM-szolgáltatót, például az Intune által felügyelt. Alkalmazások és a szervezeti adatokhoz való hozzáférés védelme érdekében a rendszergazdák alkalmazás felügyelhető alkalmazásokat használ, és adatvédelmi szabályzatok vonatkoznak ezekre az alkalmazásokra.

Ez a funkció az alábbiakra vonatkozik:

- Android 4.4-es és újabb verziók

> [!TIP]
> További információkért lásd: [Mik azok az alkalmazásvédelmi szabályzatok?](app-protection-policy.md).

Alkalmazás-TUDJUK forgatókönyvek is, a végfelhasználók számára, aki szeretne saját eszközeiken csekély szervezeti tárhely, és nem szeretne regisztrálni a mobileszköz-kezelést. A rendszergazdák továbbra is szeretné megvédeni adatait. Ezek az eszközök nem felügyelt. Így közös mobileszköz-kezelési feladatok és szolgáltatások, például Wi-Fi, VPN eszköz és tanúsítványkezelés, nem a központi telepítési forgatókönyv részét.

#### <a name="android-enterprise-work-profiles"></a>Vállalati androidos munkahelyi profilok

Munkahelyi profilok a core Android Enterprise üzembehelyezési forgatókönyvben, és az egyetlen forgatókönyv BYOD megcélzó használati eseteket. A munkahelyi profil egy külön partíciót az Intune által kezelt Android operációs rendszer szintjén hozhatók létre.

Ez a funkció az alábbiakra vonatkozik:

- A Google Mobile Services Android 5.0 és újabb verziók eszközök

Munkahelyi profil az alábbi szolgáltatásokat tartalmazza:

- **A hagyományos MDM-funkciók**: Kulcs MDM-képességei, például a felügyelt Google Play használatával alkalmazáséletciklus-felügyeleten bármilyen Android Enterprise forgatókönyvhöz érhető el. A felügyelt Google Play telepíthet és frissíthet alkalmazásokat a felhasználó beavatkozása nélkül robusztus élményt nyújt. Informatikai alkalmazáskonfigurációs beállítások is küldhet a szervezeti alkalmazások. Emellett nincs szükség, hogy az ismeretlen forrásból történő telepítése a végfelhasználók számára. Más közös mobileszköz-kezelési tevékenységek, például a tanúsítványok, Wi-Fi és VPN-ek konfigurálása és az eszköz PIN-kódjának beállítása érhető el munkahelyi profilokkal rendelkező.

- **Munkahelyi profil határán DLP**: Például az alkalmazás-, hogy informatikai kényszerítheti az adatvédelmi szabályzatok. Munkahelyi profillal DLP-szabályzatok érvényesítése szintjén történik a munkahelyi profil, nem az alkalmazás szinten. Például másolja és illessze be védelmet az alkalmazásbeállításokat a alkalmazni, vagy kényszeríti ki a munkahelyi profil kikényszeríti a. Az alkalmazást helyezünk üzembe egy munkahelyi profilt, amikor a rendszergazdák szüneteltetheti másolja és illessze be a munkahelyi profil védelmet kikapcsolja ezt a házirendet, az alkalmazás szintjén.

## <a name="tips-to-optimize-the-work-profile-experience"></a>Tippek a munkahelyi profil optimalizálása élmény

### <a name="when-to-use-app-within-work-profiles"></a>Mikor érdemes használni az Alkalmazást munkahelyi profilokkal belül

Intune APP és a munkahelyi profil egymást egészítik, amelyek együtt vagy külön-külön is használhatók. Tekintve a két megoldás különböző rétegeken – alkalmazás az egyes alkalmazásokra rétegben a szabályzatok érvényesítését és munkahelyi profil a profil rétegben. A munkahelyi profilban szereplő alkalmazásokba egy szabályzattal felügyelt alkalmazások telepítéséhez érvényes és támogatott forgatókönyv. Alkalmazás használatához munkahelyi profillal, vagy kombinálja a DLP követelményeitől függ.

Munkahelyi profilok és az alkalmazás kiegészíteni egymás beállítások megadásával további lefedettség, ha egy profil nem felel meg a szervezet adatvédelmi követelményeit. Munkahelyi profilok például natív módon nem biztosítják egy alkalmazás egy nem megbízható felhőbeli tárhelyre mentés korlátozhatja, hogy szabályozza. Alkalmazás tartalmazza ezt a szolgáltatást. Dönthet úgy, hogy kizárólag a munkahelyi profil által biztosított DLP elegendő, és nem szeretné használni az Alkalmazást. Vagy előfordulhat, hogy a védelmet, a kettő kombinációjából van szüksége.

### <a name="suppress-app-policy-for-work-profiles"></a>Munkahelyi profilok alkalmazásszabályzat elrejtése

Támogatja az egyéni felhasználók, akik több eszköze – az alkalmazás nem felügyelt eszközökre van szükség lehet – hogy a forgatókönyv és a felügyelt eszközök munkahelyi profillal rendelkező. 

Például szüksége a végfelhasználók számára, hogy a munkahelyi alkalmazások megnyitásakor PIN-kód megadását. Az eszköztől függően a PIN-kód funkciók kezeli, alkalmazás vagy a munkahelyi profil. Az alkalmazás-alkalmazás kikényszeríti azt eszközök, a PIN-kód-indítási viselkedését. Munkahelyi profilos eszközök, az eszköz használata, vagy a munkahelyi profil kényszeríti ki az operációs rendszer PIN-kódot. Alkalmazásbeállítások érdekében ebben a forgatókönyvben a konfigurálása, így ezek nem alkalmazhatók *amikor* egy alkalmazást helyezünk üzembe egy munkahelyi profilt. Ha nem állítja be, ezzel a módszerrel, lekérdezi rendszer felszólítja a végfelhasználót PIN-kódot az eszközön, és újra az alkalmazás rétegben.

### <a name="control-multi-identity-behavior-in-work-profiles"></a>Szabályozhatja a többszörös identitás működését a munkahelyi profilokról

Office-alkalmazások, például az Outlookot és a onedrive vállalati verzió, a "többszörös identitást" viselkedés rendelkezik. Belül az alkalmazás egy példányát a végfelhasználó hozzáadhat több különböző fiókok kapcsolatok vagy felhőbeli tárolási helyek. Az alkalmazásból ezek a helyek lekért adatok külön vagy egyesített lehet. És a felhasználói környezet kapcsoló személyes identitások között is (user@outlook.com) és a szervezet identitásait (user@contoso.com).

Munkahelyi profilok használatakor érdemes ezt a viselkedést a többszörös identitás letiltása. Tiltsa le azt, ha az alkalmazás a munkahelyi profilban szereplő jelzéssel példányait csak konfigurálható egy szervezet identitással. Használja az engedélyezett fiókok alkalmazás konfigurációs beállítást Office Android-alkalmazások támogatásához.

További információkért lásd: [az Outlook iOS és Android-alkalmazás-konfigurációs beállítások telepítése](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="when-to-use-intune-app"></a>Mikor érdemes használni az Intune-alkalmazás

Nincsenek a nagyvállalati mobilitási számos forgatókönyv használata az Intune APP a legjobb javaslat.

#### <a name="older-devices-running-android-44-51-are-being-used"></a>Android 4.4-5.1 régebbi rendszerű vannak használatban.

Hivatalosan, minden olyan Android-eszköz 5.0-s vagy újabb a Google Mobile Services támogatja a munkahelyi profillal, és kezelhető, ezzel a módszerrel a jogosult. Azonban bizonyos Android 5.0-s és az egyes számítógépgyártók 5.1-es eszközök nem támogatják a munkahelyi profilokkal.

Ha verziókat, amelyek nem támogatják a munkahelyi profilokról, használja, és annak biztosítása érdekében a DLP a szervezeti adatok az eszközökön, az Intune APP-funkciók kell használnia.

#### <a name="no-mdm-no-enrollment-google-services-are-unavailable"></a>Nem MDM, nincs regisztrációs Google-szolgáltatások nem érhetők el.

Egyes ügyfelek nem szeretné semmilyen formáját Eszközfelügyelet munkahelyi profilok kezelése, beleértve a különböző okok miatt:

- Jogi tudnivalók és a felelősség korlátozására vonatkozó okok
- A konzisztencia, a felhasználói élmény
- Az Android-eszköz környezet magas heterogén
- Nem minden olyan Google-szolgáltatások kapcsolatait azért szükség a munkahelyi profil kezelése.

Ha például az ügyfelek vagy Kínában felhasználók nem használhatnak Android-eszközök kezelésének, mivel a Google-szolgáltatások le vannak tiltva. Ebben az esetben az Intune-alkalmazás használatával DLP.

## <a name="summary"></a>Összegzés

Az Intune-nal, mindkét alkalmazás – a Microsoft és az Android Enterprise munkahelyi profilokkal érhetők el az Android BYOD-program. Alkalmazás kiválasztása – hogy vagy a munkahelyi profilokkal attól függ, az üzleti és használati követelményei. Összefoglalva használja munkahelyi profillal, ha szüksége MDM-tevékenységek a kezelt eszközökön, például a tanúsítványok telepítése, app-leküldés és így tovább. Alkalmazás-, hogy ha nem szeretné, vagy nem tudja kezelni az eszközöket, és csak az Intune APP-kompatibilis alkalmazásokat használnak.

## <a name="next-steps"></a>További lépések
[Az alkalmazásvédelmi szabályzatok használatának megkezdéséhez](app-protection-policy.md), vagy [regisztrálni az eszközöket](android-enroll.md).
