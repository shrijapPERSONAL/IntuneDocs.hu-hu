---
title: Eszközkorlátozásokra vonatkozó beállítások a Microsoft Intune-ban macOS esetén
titlesuffix: ''
description: A cikk tájékoztatást nyújt az Intune azon beállításairól, amelyekkel szabályozhatók az eszközbeállítások, illetve a funkciók köre a macOS rendszerű eszközökön.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 51b1df246c23f2e1571b3bccc3f4f26ae91e26dd
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52178352"
---
# <a name="microsoft-intune-macos-device-restriction-settings"></a>A Microsoft Intune macOS-eszközkorlátozásokra vonatkozó beállításai

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A cikk bemutatja a Microsoft Intune olyan eszközkorlátozásokra vonatkozó beállításait, melyek konfigurálhatók macOS rendszerű eszközökhöz.

## <a name="password"></a>Jelszó
-   **Jelszó** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
    -   **Megkövetelt jelszótípus** – Megadja, hogy a jelszó csak numerikus lehet-e, vagy alfanumerikusnak kell lennie (azaz betűket és számokat is tartalmaznia kell). Ezt a beállítást csak a Mac OS X 10.10.3-as és újabb verziói támogatják.
    -   **Nem alfanumerikus karakterek száma a jelszóban** – Megadja, hogy hány speciális karakternek (**0** - **4**) kell szerepelnie a jelszóban.<br>A speciális karakterek olyan szimbólumok, mint például a „**?**”.
    -   **Jelszó minimális hossza** – Megadja a felhasználó által beállítandó jelszó minimális hosszát (**4** és **16** karakter között).
    -   **Egyszerű jelszavak** – Az egyszerű jelszavak (például a **0000** vagy az**1234**) használatának engedélyezése.
    -   **Jelszó kérése legfeljebb ennyi perccel a képernyőzárolás után** – Megadja, hogy a számítógépnek mennyi ideig kell inaktívnak lennie ahhoz, hogy bekapcsoljon a jelszavas zárolás.
    -   **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – Meghatározza, hogy a számítógépnek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.
    -   **Jelszó lejárata (napokban)** – Megadja, hogy hány nap elteltével kötelező a felhasználónak módosítania a jelszót (**1** **255** nap).
    -   **Korábbi jelszavak újbóli használatának tiltása** – Meghatározza, hogy hány korábbi jelszó ne legyen újra felhasználható (**1** - **24**).

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

- A **Letiltott alkalmazások** listája – Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyeknek a telepítése és futtatása nincs engedélyezve a felhasználók számára. A rendszer nem akadályozza meg, hogy a felhasználók tiltott alkalmazásokat telepítsenek, de ilyen esetben értesítést küld Önnek.
- A **Jóváhagyott alkalmazások** listája – Azokat az alkalmazásokat tartalmazza, amelyeknek a telepítése engedélyezve van a felhasználók számára. A felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek. A rendszer nem akadályozza meg, hogy a felhasználók az engedélyezési listán nem szereplő alkalmazásokat telepítsenek, de ilyen esetben értesítést küld Önnek.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet, igény szerint az alkalmazás kiadóját, valamint az alkalmazás csomagazonosítóját (például *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Jelöletlen e-mail-tartományok

Az **E-mail-tartomány URL-címe** mezőben adjon a listához egy vagy több URL-címet. Ha a felhasználó nem a konfigurált tartományok egyikéből kap e-mailt, a MacOS-es Mail alkalmazásban ez az e-mail nem megbízhatóként jelenik meg.

