---
title: "A helyszíni Exchange-hez való e-mail-hozzáférés védelme | Microsoft Docs"
description: "Feltételes hozzáféréssel védheti és kezelheti a vállalati e-mailhez való hozzáférést a helyszíni Exchange-en."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 3098a301550413a982d3ce9664646f7dfc0b1d1f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/04/2017


---

# <a name="protect-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a>A helyszíni Exchange-hez és az örökölt dedikált Exchange Online-hoz való e-mail-hozzáférés védelme az Intune használatával

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A helyszíni Exchange-hez vagy az örökölt dedikált Exchange Online környezethez való e-mail-hozzáférés szabályozásához a Microsoft Intune-nal konfigurálhatja a feltételes hozzáférést.
Ha szeretné jobban megismerni a feltételes hozzáférés működését, olvassa el [Az e-mailek és az O365-szolgáltatások elérésének védelme](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) című cikket.

> [!NOTE]
> Ha dedikált Exchange Online-környezettel rendelkezik, és szeretné tudni, hogy az új vagy az örökölt konfiguráció tartozik-e hozzá, lépjen kapcsolatba a fiókkezelővel.

## <a name="before-you-begin"></a>Előkészületek

Mindenképpen ellenőrizze a következőket:

-   Az Exchange esetében **Exchange 2010-es vagy újabb verzió** szükséges. Az Exchange-kiszolgáló ügyfélelérési kiszolgálótömbjei (CAS) támogatottak.

-   [Az Intune helyszíni Exchange összekötőjét](intune-on-premises-exchange-connector.md) kell használnia, amely összeköti az Intune-t és a helyszíni Exchange-et. Ez lehetővé teszi az eszközök kezelését az Intune-konzolon keresztül.

    -   Az Intune-konzolon elérhető helyszíni Exchange-összekötő az adott Intune-bérlőhöz tartozik, és semmilyen más bérlővel nem használható. Gondoskodjon róla, hogy bérlője Exchange-összekötője **csak egy számítógépen** legyen telepítve.

        Az összekötőt letöltheti az Intune felügyeleti konzoljáról. A helyszíni Exchange-összekötő konfigurálásával kapcsolatos általános bemutató: [Az Exchange helyszíni összekötő konfigurálása helyszíni vagy üzemeltetett Exchange használatához](intune-on-premises-exchange-connector.md).

    -   Az összekötő bármely gépen telepíthető, amennyiben az képes az Exchange-kiszolgálóval való kommunikációra.

    -   Ez az összekötő támogatja az **Exchange CAS-környezetet**. Az összekötőt elvileg közvetlenül az Exchange CAS-kiszolgálón is telepítheti. Ez azonban nem ajánlott, mivel megnöveli a kiszolgáló terheltségét. Az összekötőt úgy kell konfigurálni, hogy az kommunikáljon az Exchange CAS-kiszolgálók valamelyikével.

-   Az **Exchange ActiveSync** tanúsítványalapú hitelesítéssel vagy felhasználó által megadott hitelesítő adatokkal konfigurálandó.

### <a name="device-compliance-requirements"></a>Eszközmegfelelőségi követelmények

Ha feltételes hozzáférési szabályzatokat konfigurál és rendel hozzá felhasználókhoz, a felhasználók csak akkor csatlakozhatnak az e-mail-fiókjukhoz, ha a használt **eszköz** megfelel az alábbi feltételeknek:

-  Az Intune-ban **regisztrált**, vagy egy tartományhoz csatlakozó számítógépnek kell lennie.

-  **Regisztrálva van az Azure Active Directoryban**. Ezenkívül az ügyfél Exchange ActiveSync-azonosítójának regisztrálva kell lennie az Azure Active Directoryban.

  Az Azure Active Directory eszközregisztrációs szolgáltatása automatikusan aktiválódik az Intune-t és az Office 365-öt használó ügyfelek számára. Azok az ügyfelek, akik már telepítették az ADFS eszközregisztrációs szolgáltatását, nem fogják látni a regisztrált eszközöket a helyszíni Active Directoryban. **Ez nem érvényes a Windows rendszerű számítógépekre és a Windows Phone-eszközökre**.

-   **Meg kell felelnie** az eszközön telepített összes Intune-os megfelelőségi szabályzatnak.

### <a name="how-conditional-access-works-with-exchange-on-premises"></a>A helyszíni Exchange és a feltételes hozzáférés működése

A következő diagram azt a folyamatot mutatja be, amelyet a helyszíni Exchange-környezet feltételes hozzáférési szabályzatai használnak annak kiértékeléséhez, hogy engedélyezzék vagy letiltsák-e az eszközöket.

![Azon döntési pontokat bemutató diagram, amelyek segítségével a rendszer eldönti, hogy az eszköz hozzáférhessen-e a helyszíni Exchange-hez](../media/ConditionalAccess8-2.png)

Ha egy feltételes hozzáférési szabályzat nem teljesül, egy 10 perces időkeret áll rendelkezésre az eszköz blokkolása és aközött, hogy a felhasználó bejelentkezésekor az alábbi karanténüzenetek egyike jelenik meg:

- Ha az eszköz nincs regisztrálva az Intune-ban vagy az Azure Active Directoryban, megjelenik egy üzenet, amely leírja, hogyan kell telepíteni a Vállalati portál alkalmazást, regisztrálni az eszközt és aktiválni az e-mailt. Ez a folyamat hozzárendeli az eszköz Exchange ActiveSync-azonosítóját is az Azure Active Directoryban lévő eszközrekordhoz.

-   Ha az eszköz nem felel meg a feltételeknek, egy üzenet jelenik meg, amely a felhasználót az Intune Munkahelyi portál webhelyére vagy a Munkahelyi portál alkalmazásba irányítja, ahol további információt talál a problémáról és megoldásáról.

## <a name="support-for-mobile-devices"></a>A mobileszközök támogatása
A következők támogatottak:
-   Windows Phone 8.1 és újabb verziók.

-   Natív e-mail-alkalmazás iOS rendszerű eszközökön.

-   Exchange ActiveSync-alapú levelezési ügyfélprogramok, mint például a Gmail az Android 4-es vagy újabb verzióiban.
-   Exchange ActiveSync-alapú levelezési ügyfélprogramok **Android for Work** eszközökön: a **munka profilban** csak a **Gmail** és a **Nine Work** alkalmazás támogatott Android for Work-eszközökön. Ahhoz, hogy a feltételes hozzáférés működjön Android for Work rendszerű eszközökön, telepíteni kell egy e-mail-profit a Gmail vagy a Nine Work alkalmazáshoz, és ezeket az alkalmazásokat kötelező telepítésként kell telepíteni. 

> [!NOTE]
> A Microsoft Outlook alkalmazás Android- és iOS-verziója nem támogatott.

## <a name="support-for-pcs"></a>Számítógépek támogatása
A következők támogatottak:
-   A **Posta** alkalmazás a Windows 8.1-es és újabb verzióiban (ha számítógép az Intune-ban regisztrálva van).

##  <a name="configure-a-conditional-access-policy"></a>Feltételes hozzáférési házirend konfigurálása

1.  A [Microsoft Intune felügyeleti konzoljában](https://manage.microsoft.com) válassza a **Házirend** > **Feltételes hozzáférés** > **Helyszíni Exchange-házirend** elemet.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Konfigurálja a szabályzatot a szükséges beállításokkal: ![Képernyőkép a helyszíni Exchange-szabályzatról](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **A helyi Exchange-hez való hozzáférés letiltása a levelezőalkalmazásoknak, ha az eszköz nem kompatibilis vagy nincs regisztrálva a Microsoft Intune-ban:** Ha bejelöli ezt a beállítást, akkor blokkolva lesz a nem az Intune által felügyelt vagy a megfelelőségi szabályzatoknak nem megfelelő eszközök hozzáférése az Exchange-szolgáltatásokhoz.

  - **Alapértelmezett szabály felülbírálása – A regisztrált és megfelelő eszközök mindig hozzáférhetnek az Exchange-hez**: Ha ezt beállítást választja, az Intune-ban regisztrált azon eszközök, amelyek eleget tesznek a megfelelőségi szabályzatoknak, hozzáférhetnek az Exchange-hez.
  Ez a szabály felülírja az **alapértelmezett szabályt**. Ha tehát az **alapértelmezett szabály** úgy van beállítva, hogy blokkolja a hozzáférést, a megfelelőnek minősülő regisztrált eszközök továbbra is hozzáférhetnek az Exchange-hez.

  - **Megcélzott csoportok:** Válassza ki az Intune azon felhasználói csoportjait, amelyeknek regisztrálniuk kell az eszközüket az Intune-ban az Exchange eléréséhez.

  - **Kivétel alá eső csoportok:** Válassza ki az Intune azon felhasználói csoportjait, amelyek mentesülnek a feltételes hozzáférési szabályzat alól. A listán szereplő felhasználók mentesülnek akkor is, ha szerepelnek a **Megcélzott csoportok** listán.

  - **Platformkivételek:** Kattintson a **Szabály hozzáadása** lehetőségre olyan szabály konfigurálásához, amely meghatározza az adott mobileszközcsaládok és -modellek hozzáférési szintjeit. Mivel ezek az eszközök bármilyen típusúak lehetnek, olyan eszköztípusokat is konfigurálhat, amelyeket nem támogat az Intune.

  - **Alapértelmezett szabály:** A többi szabály alól mentes eszközökhöz kiválaszthatja, hogy engedélyezi-e az Exchange-hozzáférést, esetleg letiltja vagy karanténba helyezi az eszközt. Ha úgy állítja be a szabályt, hogy engedélyezze a hozzáférést, a megfelelőnek minősülő regisztrált eszközök automatikusan hozzáférést kapnak a levelezéshez (iOS, Windows és Samsung KNOX rendszerű eszközök esetén). A felhasználónak semmilyen teendője sincs az e-mail-fiókjával kapcsolatban.
      - A nem Samsung KNOX-alapú androidos eszközök esetén a felhasználók értesítést kapnak e-mailben az eszközeik karanténba helyezéséről. Az e-mailben található egy részletes útmutató arról, hogy a levelezéshez való hozzáférés előtt miként kell ellenőrizni az eszközök regisztrációját és megfelelőségét. Ha úgy állítja be a szabályt, hogy az engedélyezze a hozzáférést vagy karanténba helyezze az eszközt, egyetlen eszköz sem fog hozzáférni az Exchange-hez, függetlenül attól, hogy regisztrálták-e már őket az Intune-ban. Amennyiben nem szeretné, hogy ez a szabály vonatkozzon a megfelelőnek minősülő regisztrált eszközökre, válassza az **Alapértelmezett szabály felülbírálása** lehetőséget.
>[!TIP]
>Ha a levelezéshez való hozzáférést megelőzően minden eszközt blokkolni szeretne, válassza inkább a hozzáférést blokkoló szabályt vagy a karanténba helyezést kiváltó szabályt. Az alapértelmezett szabály az összes eszköztípusra érvényes, így hatással van a platformkivételként konfigurált és az Intune által nem támogatott eszköztípusokra is.

  - **Felhasználó értesítése:** Az Exchange által küldött értesítő e-mail mellett az Intune e-mailt küld, amely tartalmazza az eszköz feloldásának lépéseit. Az alapértelmezett üzenetet az igényeinek megfelelően módosíthatja. Ha a felhasználó eszköze le van tiltva az Intune által küldött, javítással kapcsolatos utasításokat tartalmazó értesítő e-mail megérkezése előtt (az e-mail a felhasználó Exchange-postaládájába kerül), akkor egy le nem tiltott eszközzel vagy más módon érheti el az Exchange-fiókot és tekintheti meg az üzenetet.
      - Ez különösen igaz olyankor, ha az **Alapértelmezett szabály** az eszközök blokkolására vagy karanténba helyezésére van beállítva. Ilyen esetben a végfelhasználónak meg kell nyitnia az alkalmazás-áruházat, le kell töltenie a Microsoft Vállalati portál alkalmazást, és regisztrálnia kell az eszközét. Ez egyaránt vonatkozik az iOS, a Windows és a Samsung KNOX rendszerű eszközökre. A nem Samsung KNOX-eszközök esetén a karanténba helyezett e-mailt el kell küldenie egy másodlagos e-mail fiókba. A felhasználónak át kell másolnia az e-mailt letiltott eszközére a regisztrációs és megfelelőségi folyamat befejezéséhez.
  > [!NOTE]
  > Meg kell adnia az értesítő e-mail elküldéséhez használt fiókot, hogy az Exchange elküldhesse az értesítő e-mailt.
  >
  > További információk: [A helyszíni Exchange-összekötő konfigurálása helyszíni vagy üzemeltetett Exchange használatához](intune-on-premises-exchange-connector.md).

3.  Ha elkészült, válassza a **Mentés** elemet.

-   Nem kell telepítenie a feltételes hozzáférési szabályzatot, az azonnal érvénybe lép.

-   Miután a felhasználó beállította az Exchange ActiveSync-profilt, az eszköz letiltása egytől három óráig tarthat (ha nem az Intune felügyeli).

-   Ha egy letiltott felhasználó ezután regisztrálja az eszközt az Intune-ban, és kijavítja a nem megfelelőséget, a rendszer két percen belül feloldja az e-mailek elérését.

-   Ha a felhasználó megszünteti az eszköz regisztrációját az Intune-ban, az eszköz letiltása egytől három óráig tarthat.

**Ha szeretne arra vonatkozó példákat megtekinteni, hogy hogyan konfigurálhat feltételes hozzáférési szabályzatot az eszközök hozzáférésének védelméhez, olvassa el az [e-mail-hozzáférés védelmét bemutató példák](restrict-email-access-example-scenarios.md) leírását.**

## <a name="next-steps"></a>További lépések
-   [A SharePoint Online-hoz való hozzáférés védelme](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [A Skype Vállalati online verzióhoz való hozzáférés védelme](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)

