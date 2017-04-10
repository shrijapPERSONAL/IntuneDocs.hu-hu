---
title: "Feltételes hozzáférési szabályzat helyszíni Exchange esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk bemutatja, hogyan lehet feltételes hozzáférési szabályzatot konfigurálni a helyszíni Exchange-hez és régi Dedikált Exchange Online-hoz az Intune-nal."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: a9edd882e2cf0fb7abf50002e9f1e8dfd5634fe1
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Feltételes hozzáférési szabályzat létrehozása a helyszíni Exchange-hez és a régi Dedikált Exchange Online-hoz az Azure-os Microsoft Intune előzetes verziójával


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ez a témakör végigvezeti azokon a lépéseken, amelyekkel az eszköz megfelelőségén alapuló feltételes hozzáférés konfigurálható az Exchange-hez.

Ha dedikált Exchange Online-környezettel rendelkezik, és szeretné tudni, hogy az új vagy az örökölt konfiguráció tartozik-e hozzá, lépjen kapcsolatba a fiókkezelővel. A helyszíni Exchange-hez vagy az örökölt dedikált Exchange Online környezethez való e-mail hozzáférés szabályozásához az Intune-ban konfiguráljon feltételes hozzáférést a helyszíni Exchange-hez.

## <a name="prerequisites"></a>Előfeltételek

**Mielőtt** konfigurálja a feltételes hozzáférést, ellenőrizze a következőket:

- Az Exchange esetében **Exchange 2010-es vagy újabb verzió** szükséges. Az Exchange-kiszolgáló ügyfél-hozzáférési kiszolgálótömbje (CAS) nem támogatott.
- Az **Exchange Active Sync helyszíni Exchange-összekötőt** kell használni, ez kapcsolja össze az Intune-t a helyszíni Microsoft Exchange-dzsel. További részletek az összekötőről: <link>

  - Az Intune-konzolon elérhető helyszíni Exchange-összekötő az Intune-bérlőjéhez tartozik, és semmilyen más bérlővel nem használható. Gondoskodjon róla, hogy bérlője Exchange-összekötője **csak egy számítógépen** legyen telepítve.

Ezt az összekötőt az Intune felügyeleti konzoljáról kell letölteni. A helyszíni Exchange-összekötő konfigurálásainak lépéseiről lásd: <link to new topic>

Az összekötő bármely gépre telepíthető, amennyiben az képes az Exchange-kiszolgálóval való kommunikációra.

- Ez az összekötő támogatja az **Exchange CAS-környezetet**. Ha szeretné, technikailag az is megoldható, hogy közvetlenül az Exchange CAS-kiszolgálóra telepítse az összetevőt, ez azonban nem javasolt, mert növeli a kiszolgálót érő terhelést. Az összekötőt úgy kell konfigurálni, hogy az kommunikáljon az Exchange CAS-kiszolgálók valamelyikével.
- Az **Exchange ActiveSync** tanúsítványalapú hitelesítéssel vagy felhasználó által megadott hitelesítő adatokkal konfigurálandó.

Amikor feltételes hozzáférési szabályzatokat konfigurál és rendel hozzá felhasználókhoz, a felhasználók csak akkor csatlakozhatnak az e-mail fiókjukhoz, ha a használt **eszköz**:

- **Regisztrálva** van az Intune-ban, vagy olyan számítógép, amely csatlakoztatva van egy tartományhoz.
- **Regisztrálva van az Azure Active Directoryban**. Ezenkívül az ügyfél Exchange ActiveSync-azonosítójának regisztrálva kell lennie az Azure Active Directoryban.

Az AAD DRS szolgáltatás automatikusan aktiválódik az Intune-t és az Office 365-öt használó ügyfelek számára. Azok az ügyfelek, akik már telepítették az ADFS eszközregisztrációs szolgáltatását, nem fogják látni a regisztrált eszközöket a helyszíni Active Directoryban. **Ez nem érvényes a Windows rendszerű számítógépekre és a Windows Phone-eszközökre**.

- **Megfelel** az Intune minden olyan megfelelőségi szabályzatának, amely érvényes az eszközre.

Ha az eszköz nem felel meg a feltételes hozzáférés beállításainak, a felhasználó a következő üzenetek valamelyikét kapja bejelentkezéskor:

- Ha az eszköz nincs regisztrálva az Intune-ban vagy az Azure Active Directoryban, megjelenik egy üzenet, amely leírja, hogyan kell telepíteni a Munkahelyi portál alkalmazást, regisztrálni az eszközt és aktiválni az e-mailt. Ez a folyamat hozzárendeli az eszköz Exchange ActiveSync-azonosítóját is az Azure Active Directoryban lévő eszközrekordhoz.
- Ha az eszköz nem felel meg a feltételeknek, egy üzenet jelenik meg, amely a felhasználót az Intune Munkahelyi portál webhelyére vagy a Munkahelyi portál alkalmazásba irányítja, ahol további információt talál a problémáról és megoldásáról.

## <a name="support-for-mobile-devices"></a>A mobileszközök támogatása

- Windows Phone 8.1 és újabb verziók
- Natív e-mail alkalmazás iOS rendszerű eszközökön.
- EAS levelezési ügyfélprogramok, mint például a Gmail az Android 4-es vagy újabb verzióiban.
- EAS levelezési ügyfélprogramok **Android for Work** eszközökön: a **munka profilban** csak a **Gmail** és a **Nine Work** alkalmazások támogatottak Android for Work eszközökön. Ahhoz, hogy a feltételes hozzáférés működjön Android for Work rendszerű eszközökön, telepíteni kell egy email-profilt a Gmail vagy a Nine Work alkalmazáshoz, és ezeket az alkalmazásokat kötelező telepítésként kell központilag telepíteni.

>[!NOTE]
>A Microsoft Outlook alkalmazás Android- és iOS-verziója nem támogatott.

> Az Android for Work a következő néhány hónap során lesz biztosítva az Intune-bérlők számára.

Az Android for Work támogatási helyzetével kapcsolatban olvassa el az [Újdonságok a Microsoft Intune-ban](https://docs.microsoft.com/en-us/intune/whats-new/whats-new-archive#october-2016) című cikk 2016 októberi kiadásában az Android for Workről szóló bejelentést.

## <a name="support-for-pcs"></a>Számítógépek támogatása

A **Posta** alkalmazás a Windows 8.1-es és újabb verzióiban (az Intune-ban regisztrálva)


## <a name="configure-exchange-on-premises-access"></a>A helyszíni Exchange-hozzáférés konfigurálása

1. Nyissa meg a Helyszíni panelt az Azure Portal **Feltételes hozzáférés** elemére kattintva.
2. A **Helyszíni** panelen látható a feltételes hozzáférési szabályzat állapota, és az, hogy mely eszközökre van hatással.
3. Válassza a **Kezelés** terület **Helyszíni Exchange-hozzáférés** elemét.
4. Engedélyezze a helyszíni Exchange hozzáférés-vezérlését az **Helyszíni Exchange-hozzáférés** panel **Igen** elemét választva.

  >[!NOTE]
  >Ha nem konfigurálta az Exchange Active Sync helyszíni összekötőt, ez a beállítás nem érhető el.  Először telepítenie és konfigurálnia kell ezt az összekötőt, csak azt követően aktiválhatja a feltételes hozzáférést a helyszíni Exchange-hez. További részletek [A helyszíni Intune Exchange Connector telepítése](install-intune-on-premises-exchange-connector.md) című cikkben olvashatók.

5. A **Hozzárendelés** beállításnál válassza a **Tartalmazott csoportok** lehetőséget.  Használja azt a biztonsági felhasználócsoportot, amelynek feltételes hozzáférést szeretne előírni.  Ez megköveteli a felhasználóktól, hogy regisztrálják az eszközüket az Intune-ban, és megfeleljenek a megfelelőségi profiloknak.
6. Ha ki szeretne zárni bizonyos felhasználócsoportokat, akkor válassza a **Kizárt csoportok** lehetőséget, majd egy olyan felhasználócsoportot, amelyet mentesíteni szeretne a kötelező eszközregisztráció és a feltételeknek való megfelelés alól.
7. Válassza a **Beállítások** terület **Felhasználói értesítések** elemét, és módosítsa az alapértelmezett e-mail szövegét. Ezt az üzenetet küldi el a rendszer a felhasználóknak, ha egy a feltételeknek nem megfelelő eszközzel próbálják meg elérni a helyszíni Exchange-et. Az üzenetsablon egy jelölőnyelvet használ.  Amint beírja az üzenetet, azt is követheti, hogy mit fog látni a címzett. A jelölőnyelvekről ez a [Wikipedia-cikk](https://en.wikipedia.org/wiki/Markup_language) nyújt tájékoztatást.
8. Az **Exchange ActiveSync speciális hozzáférési beállításai** panelen adja meg a következő két lépésben ismertetett módon az Intune által nem kezelt eszközökre vonatkozó alapértelmezett globális hozzáférési szabályt, illetve a platformszintű szabályokat.
9. Választhat, hogy engedélyezi vagy letiltja az Exchange elérését az olyan eszközök számára, amelyekre nem vonatkoznak feltételes hozzáférési vagy egyéb szabályok.
  - Ha itt a hozzáférés engedélyezését állítja be, azonnal minden eszköz hozzáfér a helyszíni Exchange-hez.  A **Tartalmazott csoportokban** foglalt felhasználók eszközeinek hozzáférését letiltja a rendszer, ha a kiértékelés során nem felelnek meg a megfelelőségi szabályzatoknak, vagy nincsenek regisztrálva az Intune-ban.
  - Ha ezt a beállítást a hozzáférés letiltására állítja be, akkor a rendszer kezdetben azonnal megakadályoz minden eszközt a helyszíni Exchange elérésében.  A **Tartalmazott csoportokban** foglalt eszközök felhasználói viszont hozzáférést kapnak, ha az eszközük regisztrálva van az Intune-ban, és a kiértékeléskor megfelel a feltételeknek. A nem Samsung KNOX Standard rendszerű androidos eszközöket mindig letiltja, mert az ilyen eszközök nem támogatják ezt a beállítást.
10. Válassza az **Eszközplatform-kivételek** terület **Hozzáadás** gombját a platformok megadásához. Ha a **Nem felügyelt eszközhozzáférés** beállítása **Letiltva**, a regisztrált és a feltételeknek megfelelő eszközök akkor is hozzáférést kapnak, ha a platformkivétel letiltja őket. Mentse a beállításokat az **OK** gombra kattintva.
11. Mentse a feltételes hozzáférési szabályzatot a **Helyszíni** panel **Mentés** gombjára kattintva.

