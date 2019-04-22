---
title: Hogyan kérhet támogatást az Intune-hoz
titleSuffix: Microsoft Intune
description: A Microsoft Intune fizetős és próbaverziós előfizetéseihez online és telefonos segítséget kérhet.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/05/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf1e87d40459d194f2c4aa0ff702a137e45504ab
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59900111"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Hogyan kérhet támogatást az Intune-hoz

[!INCLUDE [azure_portal](./includes/note-for-both-portals.md)]

A Microsoft Intune-hoz a Microsoft globális műszaki, értékesítés előtti, számlázási és előfizetési támogatást nyújt. A támogatás interneten és telefonon is elérhető mind a fizetős, mind a próbaverziós előfizetésekhez. Az online műszaki támogatás angolul és japánul érhető el. Telefonos és online számlázási támogatás más nyelveken érhetők el.

Az Intune-rendszergazdaként, használhatja a **Súgó és támogatás** egy online támogatási jegy fájlba az Intune-hoz az Azure Portalról. Hozhat létre és kezelheti a támogatási incidensek, a fióknak rendelkeznie kell egy Azure Active Directory (Azure AD) szerepkör, amely tartalmazza a *művelet* **microsoft.office365.supportTickets/allEntities/allTasks**. További információ az Azure AD-szerepkörökhöz, és hozzon létre egy támogatási jegyet a szükséges engedélyeket: [rendszergazdai szerepkörök az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal). 

**Ismert problémák támogatási incidensei létrehozásához**

Ha a fiók rendelkezik a szükséges engedélyekkel, de nem sikerült hozzáférni a Súgó és támogatás, vagy hozzon létre vagy a támogatási incidensek kezelése, tekintse át a következő ismert problémák és megoldásaik:  
- A fiók elavult felhasználói jogkivonat. A probléma megoldásához jelentkezzen ki az összes aktív konzol, jelentkezzen be újra, és próbálja meg létrehozni vagy kezelni egy támogatási eseményt. 
- Több aktív munkamenet. Ha egynél több felhasználó vagy a munkamenet be van jelentkezve, jelentkezzen ki egy kivételével az összes konzolon. Ezt követően egyetlen aktív munkamenettel, próbálja meg létrehozása és kezelése egy támogatási eseményt.

Hozzáférési problémák megoldásához szükséges lehet további műveletek:
- Törölje a cookie-k az aktív böngésző-munkamenet, és próbálkozzon újra a létrehozásával és felügyeletével egy támogatási eseményt.
- Az InPrivate-böngészési munkamenet használatával jelentkezzen be az Intune-hoz, és megpróbál létrehozni, vagy a támogatási incidensek kezeléséhez.  

Ha a fenti megoldások nem segít, lépjen a [Microsoft 365 felügyeleti központban](https://admin.microsoft.com) , és hozzon létre egy támogatási jegyet onnan. Jelenleg dolgozunk a javítás késői nyáron használható. 



>[!IMPORTANT]  
> Ha olyan külső termékekhez szeretne műszaki támogatást igénybe venni, amelyek együttműködnek az Intune-nal (például a Saaswedo, a Cisco vagy a Lookout), akkor először forduljon ezeknek a termékeknek a szállítójához. Mielőtt megnyitja az Intune-nal kapcsolatos támogatási kérelmet, győződjön meg róla, hogy a másik terméket megfelelően konfigurálta.
>
> A Microsoft Intune hibaelhárítási problémáiról további információt az Intune dokumentációjának [hibaelhárítási szakaszában](help-desk-operators.md) találhat.




## <a name="help-and-support-experience"></a>Súgó és támogatás élmény
> [!TIP]   
> Egy új Súgó és támogatási élményt érhető el az összes bérlőre vonatkozóan. Ha nem látja az új felületet a bérlőben, törölje a böngésző gyorsítótárát, és frissítse az oldalt.

A Súgó és támogatás élmény az Intune-ban érhető el a [Microsoft 365-kezelési portál](http://devicemanagement.microsoft.com) és az összes a panelek (vagy lapok) alatt az Azure portalbeli Intune-ban. 

![Az Intune a többi panelen](./media/get-support/intune-blades.png)


Az új felületet hasonló a látható a [Microsoft 365 felügyeleti központban](https://admin.microsoft.com/), és lecseréli azokat az előző súgó, és felület támogatja. 

Súgó és támogatás elérésére használja a következő beállításokat:  
- **Eszköz kezelési irányítópult:**
   - Válassza ki bármelyik elérhető lehetőség **Súgó és támogatás**
   - Válassza ki a **?** a portál jobb felső sarkában található ikonra

- **Az Azure Portalon:**
   - Válassza ki **Súgó és támogatás** bármely Intune panel vagy lap

   Vagy válassza a **?** ikonra a jobb felső sarokban, vagy **súgó + támogatás** bármely helyről az Azure portal megnyílik a bal oldali navigációs panelről *súgó + támogatás* az Azure-hoz. A legjobb használhatóság érdekében használjon *Súgó és támogatás* az Intune panelen.  

Az új felhasználói felületre való hozzáférést kaphat a **segítségre van szüksége?** megtekintése, az eszköz felügyeleti irányítópulton a következő képen látható módon:  
![Az Eszközkezelés irányítópultja és a Segítségre szorul? oldal](./media/get-support/help-support-dashboard.png)

Ebben a nézetben a következő műveleteket végezheti el:

1. [Részletezheti](#specify-details-about-an-issue) az adott problémát, amellyel kapcsolatban segítségre szorul  
2. [Megtekintheti a környezetfüggő súgót](#view-context-sensitive-help) és azon kapcsolódó megoldásokat, amelyek az Ön által megadott részleteken alapulnak  
3. [Támogatást kérhet](#get-support) e-mailen vagy telefonon keresztül  
4. [Olyan támogatási eseteket tekinthet meg](#view-support-cases), amelyeket Ön nyitott korábban ezen új munkafolyam segítségével  

### <a name="specify-details-about-an-issue"></a>Adott probléma részletezése
A súgó megnyitásához, és támogatja az új felhasználói felület által támogatott helyről a **segítségre van szüksége?** lap megnyitásakor. Ezen az oldalon részletesen kifejtheti az adott problémát. Amikor elkezdi beírni a részleteket, a konzol olyan általános témákat dob fel, amelyek az Ön által használt kulcsszavakon alapulnak. Válasszon ki egy ajánlott lehetőség, vagy fejezze be a saját probléma leírása. Ha az Önt érintő problémát írja be, akkor kérdését a **Támogatás kérése** lehetőséget választva küldheti el. Miután elküldött egy lekérdezést, a konzol, amely segíthet a probléma megoldásához környezetfüggő adatokat adja vissza.

A következőkben példákat láthat a beküldhető kérdésekre:
  
- *Nem lehet visszaállítani az iOS eszközt*  
- *Nem lehet létrehozni feltételes hozzáférési szabályzatot*  

![Probléma kifejtése a Segítségre szorul? oldalon](./media/get-support/describe-the-issue.png)

### <a name="view-context-sensitive-help"></a>Környezetfüggő súgó megtekintése
Miután kiválasztotta a felkínált lehetőségek egyikét, vagy elküldte a saját kérését, a **Megoldások megtekintése** részben környezetfüggő találatok jelennek meg. Ezek a találatok tartalmazzák az Intune-hoz kapcsolódó önsegítő útmutatást, és az internetes keresés után megjelenített, a lekérdezési kritériumokon alapuló további találatokat is.  
![Találatok megtekintése](./media/get-support/view-results.png)

### <a name="get-support"></a>Támogatás kérése
A önsegítő vagy webes útmutatót a probléma elhárításához nem segít, ha a konzol használatával nyisson meg egy e-mail cím vagy telefonszám támogatási problémát.  
A **Segítségre szorul?** oldalon válassza ki a használni kívánt lehetőséget.  

- E-mailes kérés esetén adja meg e-mail-címét, és tetszőlegesen csatolmányokat is küldhet levelében. A kérés megnyitásához válassza a **Küldés** elemet.  

  ![E-mailes kérés](./media/get-support/email-support.png)
  
- Telefonos kéréshez adja meg telefonszámát. Esetlegesen megadhatja e-mail-címét is, és csatolmányokat fűzhet a levélhez. A kérés küldéséhez válassza a Visszahívás elemet.  

   ![Telefonos kérés](./media/get-support/phone-support.png)

### <a name="view-support-cases"></a>Támogatási esetek megtekintése
Az Előzmények gombra kattintva megtekintheti az Ön által létrehozott támogatási eseteket.  

![Támogatási esetek megtekintése](./media/get-support/view-support-tickets.png)

- Kizárólag az új munkafolyam használatával megnyitott támogatási esetek jeleníthetők meg e munkafolyamon belül. Ezek megtekintéséhez használja a Súgó, és támogatja a nézetet a kezelés konzolról vagy az Intune panelen az Azure Portalon. Ezeket az eseteket nyolcjegyű számok jelölik. A Microsoft 365 felügyeleti központjában is megtekinthetők az esetek.  

- Olyan esetekben, amikor nem használja az Intune-ban Súgó és támogatási élményt megnyitott nem változik. Ezek megtekintéséhez kell egy Súgó használatát, és támogatja, amely nem része az Intune felhasználói élményt, vagy kezelés irányítópult nézetet. Ezek az esetek **117**-tel vagy **118**-cal kezdődő, 15 jegyű számokkal vannak ellátva. Ezek megtekintéséhez:

    1. Az Intune rendszergazdai hitelesítő adataival jelentkezzen be az Azure-ba (<https://portal.azure.com>), majd válassza a *?* lehetőséget ikonra a portál jobb felső sarkában, majd a *Súgó + támogatás* lehetőség kiválasztásával lépjen tovább az [Azure Súgó + támogatás](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) oldalra.

    2. A **Súgó és támogatás** lapon megtekintheti a **legutóbbi támogatási kérelmek** listáját, és az egyes elemeket kijelölve további információt kaphat róluk.


## <a name="azure-help--support-experience"></a>Az Azure súgó + támogatás élmény
A következő információkat ismerteti az Azure Súgó és támogatási szolgáltatásokat, amelyek az Azure Portalon elérhető marad, a bal oldali navigációs ablak használatakor **súgó + támogatás**, vagy használja a **?** az Azure Portal jobb felső sarokban lévő beállítást. A január a 2019-es verziótól kezdve nem fér hozzá az Azure *súgó + támogatás* biztosít *Súgó és támogatás* az Intune-ban paneleken is található.  

### <a name="create-an-online-support-ticket"></a>Online támogatási jegy létrehozása

1. Az Intune rendszergazdai hitelesítő adataival jelentkezzen be az Azure Portalra (<https://portal.azure.com>), majd válassza a **?** lehetőséget ikonra a portál jobb felső sarkában, majd a **Súgó + támogatás** lehetőség kiválasztásával lépjen tovább az [Azure Súgó + támogatás](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) oldalra.

   ![A kérdőjel kapcsolat és a Súgó + támogatás hivatkozás kiemelésével képe](./media/azure-get-support.png)

2. Az Azure-beli **súgó + támogatás** lapon jelölje be **új támogatási kérelem**.

   ![Új kép támogatási kérelem hivatkozás kiemelésével a Súgó és támogatási oldal](media/azure-support-ticket-link.png)

3. Az a **alapjai** lapján, a legtöbb Intune kapcsolatos technikai támogatáskéréshez a következő lehetőségeket választhatja:
   - **Probléma típusa**: **Technikai**
   - **Előfizetés**: <*az előfizetés*>
   - **Szolgáltatás**: **A Microsoft Intune-ban**
   - **Probléma típusa**: A probléma típusaként válassza a legördülő menüből.
   - **A probléma altípus**: A legördülő menüből válassza ki a probléma altípusa.
   - **Tulajdonos**: Röviden ismertesse a problémát, kapcsolatban segítségre van szüksége.

   ![Az alapvető beállítások lapján a Súgó + támogatás – új támogatási kérelem lap képe](./media/get-support/help-new-support-case-basics.png)

   Válasszon **tovább: Megoldások** folytatásához.
4. Az a **megoldások** lapján, a javasolt lépéseket, amelyek segíthetnek megoldani a problémát egy jegyet a bejelentés nélkül. Ha továbbra is szeretné a támogatási kérelem létrehozása után a lépések között kattintson a **tovább: Részletek**.

   ![A megoldások lapja a Súgó + támogatás – új támogatási kérelem lap képe](./media/get-support/help-new-support-case-solutions.png)
5. Az a **részletek** fülre, adja meg a részleteket a problémát, a támogatási módszer, a kapcsolattartási adatokat, majd **tovább: Felülvizsgálat + létrehozás**.

   ![A részleteket tartalmazó lapot a a Súgó + támogatás – új támogatási kérelem lap képe](./media/get-support/help-new-support-case-details.png)
6. Tekintse át az adatokat, győződjön meg arról, hogy helyesen szerepel-e, és válassza a **létrehozás** a támogatási kérést szeretne beküldeni.

   ![A felülvizsgálat képe + lap létrehozása az új támogatási kérelem lap](./media/get-support/help-new-support-case-create.png)

<!--
  - **Support plan**: **Technical support - included** (for Intune technical issues, support is complimentary) or **Premier**
     >[!IMPORTANT]
     >- If you are a **Premier customer** and don't see **Support plan: Premier**, contact your Technical Account Manager for help linking your contract and tenant.
     >- Support for Intune, and for Intune when used with Configuration Manager, is free of charge. To review details of the Premier Support offering, see the [Description of Services](https://enterprise.microsoft.com/en-us/services/services-list/) documentation, section 5.3.3 "Advisory Services."

4. On the **Problem** blade, to make sure your request is addressed by the right subject matter expert for your problem, select the following options:

   - **Severity**
   - **Problem type**
   - **Category**

     These details also let us provide **Related help** that might solve your problem without filing a ticket.

     ![Screenshot of Azure portal help and support page with Problem items filled out and displaying solutions based on your problem](./media/support-need-solutions.png)

     To help the support team research and resolve your problem, enter the following information:
    
   - **Details**
   - **Date**
   - **Time**
   - **Supplemental data**

   Choose **Next**.

5. Provide **Contact information** for this support request. Microsoft support uses this information to contact you.
6. Choose **Create** to submit your support request.
-->
>[!IMPORTANT]
>Ha számlázással vagy előfizetéssel kérdése van, akkor új esetet nyithat kérhet támogatást a [Microsoft 365 felügyeleti központban](https://admin.microsoft.com/Support/SupportEntry.aspx).

### <a name="view-support-requests"></a>Támogatási kérelmek megtekintése
A támogatási kérelmeket az Azure Portalon tekintheti meg. Ehhez tegye a következőket:

1. Az Intune rendszergazdai hitelesítő adataival jelentkezzen be az Azure-ba (<https://portal.azure.com>), majd válassza a **?** lehetőséget ikonra a portál jobb felső sarkában, majd a **Súgó + támogatás** lehetőség kiválasztásával lépjen tovább az [Azure Súgó + támogatás](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) oldalra.

2. A **Súgó és támogatás** lapon megtekintheti a **legutóbbi támogatási kérelmek** listáját, és az egyes elemeket kijelölve további információt kaphat róluk.

## <a name="additional-resources"></a>További források
- [Számlázási és előfizetés-kezelési támogatás](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Mennyiségi licencelés](https://go.microsoft.com/fwlink/p/?LinkID=282015)
- [A Intune hibáinak elhárítása](help-desk-operators.md)
