---
title: Hogyan kérhet támogatást az Intune-hoz
titlesuffix: Microsoft Intune
description: A Microsoft Intune fizetős és próbaverziós előfizetéseihez online és telefonos segítséget kérhet.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 2feb18f9c21929d803bbb3605842effa8f63d75d
ms.sourcegitcommit: 8019bdd8117806c6a3a73a8c6d40af1a3def6d90
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53247169"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Hogyan kérhet támogatást az Intune-hoz

[!INCLUDE [azure_portal](./includes/note-for-both-portals.md)]

A Microsoft Intune-hoz a Microsoft globális műszaki, értékesítés előtti, számlázási és előfizetési támogatást nyújt. A támogatás interneten és telefonon is elérhető mind a fizetős, mind a próbaverziós előfizetésekhez. Az online műszaki támogatás angolul és japánul érhető el. Telefonos és online számlázási támogatás más nyelveken érhetők el.

>[!IMPORTANT]
> Ha olyan külső termékekhez szeretne műszaki támogatást igénybe venni, amelyek együttműködnek az Intune-nal (például a Saaswedo, a Cisco vagy a Lookout), akkor először forduljon ezeknek a termékeknek a szállítójához. Mielőtt megnyitja az Intune-nal kapcsolatos támogatási kérelmet, győződjön meg róla, hogy a másik terméket megfelelően konfigurálta.
>
> A Microsoft Intune hibaelhárítási problémáiról további információt az Intune dokumentációjának [hibaelhárítási szakaszában](help-desk-operators.md) találhat.

Rendszergazdaként a **Súgó és támogatás** lehetőséggel online támogatási jegyet küldhet az Azure Portalbeli Intune-ról. Támogatási jegy létrehozásához a fiókjához a következő [rendszergazdai szerepköröket kell hozzárendelni az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)::

- Intune-rendszergazda
- Globális rendszergazda
- Szolgáltatás-rendszergazda  

## <a name="get-context-sensitive-help"></a>Környezetfüggő segítség
Jelentkezzen be az Azure Portalon, és nyissa meg az Intune-ban, miután kiválaszthatja **Súgó és támogatás** bármely Intune panelen az adott területre az Intune gyakori problémák megoldása megtekintése az Azure Portalon.

Ha a gyakran előforduló megoldás érdekében ne válassza **támogatási kérelem** hozhat létre egy új támogatási kérelmet, amely megnyitja a **alapjai** lapján az Azure *súgó + támogatás* lap. A támogatási jegy létrehozásához lépjen a következő folyamat *3. lépésére*, az [online támogatási jegy létrehozására](#create-an-online-support-ticket).

## <a name="create-an-online-support-ticket"></a>Online támogatási jegy létrehozása

1. Az Intune rendszergazdai hitelesítő adataival jelentkezzen be az Azure Portalra (<https://portal.azure.com>), majd válassza a **?** lehetőséget ikonra a portál jobb felső sarkában, majd a **Súgó + támogatás** lehetőség kiválasztásával lépjen tovább az [Azure Súgó + támogatás](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) oldalra.

   ![Képernyőkép az Azure Portal kérdőjellel jelölt súgó és támogatás hivatkozásáról, a Súgó + támogatás hivatkozás kiemelésével](./media/azure-get-support.png)

2. Az Azure-beli **súgó + támogatás** lapon jelölje be **új támogatási kérelem**.

   ![Képernyőkép az Azure Portal Súgó és támogatás oldaláról az Új támogatási kérelem hivatkozás kiemelésével](media/azure-support-ticket-link.png)

3. Az a **alapjai** lapján, a legtöbb Intune kapcsolatos technikai támogatáskéréshez a következő lehetőségeket választhatja:
   - **Probléma típusa**: **Technikai**
   - **Előfizetés**: <*az előfizetés*>
   - **Szolgáltatás**: **A Microsoft Intune-ban**
   - **Probléma típusa**: A probléma típusaként válassza a legördülő menüből.
   - **A probléma altípus**: A legördülő menüből válassza ki a probléma altípusa.
   - **Tulajdonos**: Röviden ismertesse a problémát, amely merülnek fel.

   ![Az alapvető beállítások lapján a Súgó + támogatás – új támogatási kérelem lap képernyőképe](./media/get-support/help-new-support-case-basics.png)

   Válasszon **tovább: Megoldások** folytatásához.
4. Az a **megoldások** lapján, a javasolt lépéseket, amelyek segíthetnek megoldani a problémát egy jegyet a bejelentés nélkül. Ha továbbra is szeretné a támogatási kérelem létrehozása után a lépések között kattintson a **tovább: Részletek**.

   ![A megoldások lapja a Súgó + támogatás – új támogatási kérelem lap képernyőképe](./media/get-support/help-new-support-case-solutions.png)
5. Az a **részletek** fülre, adja meg a részleteket a problémát, a támogatási módszer, a kapcsolattartási adatokat, majd **tovább: Felülvizsgálat + létrehozás**.

   ![A részleteket tartalmazó lapot a a Súgó + támogatás – új támogatási kérelem lap képernyőképe](./media/get-support/help-new-support-case-details.png)
6. Tekintse át az adatokat, ellenőrizze, hogy javítsa ki, és válassza a **létrehozás** a támogatási kérést szeretne beküldeni.

   ![Képernyőkép a felülvizsgálat + lap létrehozása a Súgó + támogatás – az új támogatási kérelem lap](./media/get-support/help-new-support-case-create.png)

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
>Ha számlázással vagy előfizetéssel kapcsolatos kérdése van, új esetet nyithat meg a segítségkéréshez az [Office felügyeleti központján](https://portal.office.com/Support/SupportEntry.aspx) keresztül.

## <a name="view-support-requests"></a>Támogatási kérelmek megtekintése
A támogatási kérelmeket az Azure Portalon tekintheti meg. Ehhez tegye a következőket:

1. Az Intune rendszergazdai hitelesítő adataival jelentkezzen be az Azure-ba (<https://portal.azure.com>), majd válassza a **?** lehetőséget ikonra a portál jobb felső sarkában, majd a **Súgó + támogatás** lehetőség kiválasztásával lépjen tovább az [Azure Súgó + támogatás](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) oldalra.

2. A **Súgó és támogatás** lapon megtekintheti a **legutóbbi támogatási kérelmek** listáját, és az egyes elemeket kijelölve további információt kaphat róluk.

## <a name="new-help-and-support-experience"></a>Új Súgó és támogatás felület
*A következő információk csak azokra az esetekre vonatkoznak, amikor Ön az eszközkezelési portált használja, és ha részt vesz az új Súgó és támogatás felület bevezetésében. A bevezetésben részt vevő felhasználókat véletlenszerűen választjuk ki az Intune elérhető bérlői közül.*  

Az Intune Súgó és támogatás felületét érintő frissítés olyan új felületet biztosít, amely a [Microsoft 365 Eszközkezelési portálon](http://devicemanagement.microsoft.com) áll rendelkezésre a bérlők bizonyos része (de nem mindegyikük) számára. Ez az új felület a [Microsoft 365 felügyeleti központjának](https://portal.office.com/AdminPortal/Home) felületéhez hasonlít, és a korábbi Súgó és támogatás felület helyébe lép, ha a hozzáféréshez az Eszközkezelési konzol bizonyos helyeit használja.  

Az Eszközkezelési portálon úgy férhet hozzá az új felülethez, ha a **Minden szolgáltatás** > **Eszközkezelés** részben található bármelyik panelen kiválasztja a **Súgó és támogatás** lehetőséget (kivételt képez ezalól a **Hibaelhárítás** panel). Ha a Súgó és támogatás felületéhez máshonnan, például a **Hibaelhárítás** panelről fér hozzá úgy, hogy a **?** lehetőséget választja a konzolszalag jobb felső sarkában, illetve ha a szolgáltatások bal oldali paneljéről választja a **Súgó és támogatás** lehetőséget, akkor az eredeti felülethez fér hozzá.  

Az új felületen hozzáférést kap a **Segítségre szorul?** nézethez, ahogyan azt a következő kép is szemlélteti:  
![Az Eszközkezelés irányítópultja és a Segítségre szorul? oldal](./media/get-support/help-support-dashboard.png)

Ebben a nézetben a következő műveleteket végezheti el:

1. [Részletezheti](#specify-details-about-an-issue) az adott problémát, amellyel kapcsolatban segítségre szorul  
2. [Megtekintheti a környezetfüggő súgót](#view-context-sensitive-help) és azon kapcsolódó megoldásokat, amelyek az Ön által megadott részleteken alapulnak  
3. [Támogatást kérhet](#get-support) e-mailen vagy telefonon keresztül  
4. [Olyan támogatási eseteket tekinthet meg](#view-support-cases), amelyeket Ön nyitott korábban ezen új munkafolyam segítségével  

### <a name="specify-details-about-an-issue"></a>Adott probléma részletezése
Ha az új felület által támogatott helyről nyitja meg a Súgó és támogatás felületet, akkor a **Segítségre szorul?**  oldal nyílik meg. Ezen az oldalon részletesen kifejtheti az adott problémát. Amikor elkezdi beírni a részleteket, a konzol olyan általános témákat dob fel, amelyek az Ön által használt kulcsszavakon alapulnak. Választhat a felkínált lehetőségek közül, vagy befejezheti az Önt érintő probléma kifejtését. Ha az Önt érintő problémát írja be, akkor kérdését a **Támogatás kérése** lehetőséget választva küldheti el. Miután elküldött egy lekérdezést, a konzol, amely segíthet a probléma megoldásához környezetfüggő adatokat adja vissza.

A következőkben példákat láthat a beküldhető kérdésekre:
  
- *Nem lehet visszaállítani az iOS eszközt*  
- *Nem lehet létrehozni feltételes hozzáférési szabályzatot*  

![Probléma kifejtése a Segítségre szorul? oldalon](./media/get-support/describe-the-issue.png)

### <a name="view-context-sensitive-help"></a>Környezetfüggő súgó megtekintése
Miután kiválasztotta a felkínált lehetőségek egyikét, vagy elküldte a saját kérését, a **Megoldások megtekintése** részben környezetfüggő találatok jelennek meg. Ezek a találatok tartalmazzák az Intune-hoz kapcsolódó önsegítő útmutatást, és az internetes keresés után megjelenített, a lekérdezési kritériumokon alapuló további találatokat is.  
![Találatok megtekintése](./media/get-support/view-results.png)

### <a name="get-support"></a>Támogatás kérése
Ha az önsegítő vagy a webalapú útmutatás nem segít a probléma megoldásában, a konzol használatával e-mailes vagy telefonos problémamegoldási kérést nyithat.  
A **Segítségre szorul?** oldalon válassza ki a használni kívánt lehetőséget.  

- E-mailes kérés esetén adja meg e-mail-címét, és tetszőlegesen csatolmányokat is küldhet levelében. A kérés megnyitásához válassza a **Küldés** elemet.  

  ![E-mailes kérés](./media/get-support/email-support.png)
  
- Telefonos kéréshez adja meg telefonszámát. Esetlegesen megadhatja e-mail-címét is, és csatolmányokat fűzhet a levélhez. A kérés küldéséhez válassza a Visszahívás elemet.  

   ![Telefonos kérés](./media/get-support/phone-support.png)

### <a name="view-support-cases"></a>Támogatási esetek megtekintése
Az Előzmények gombra kattintva megtekintheti az Ön által létrehozott támogatási eseteket.  

![Támogatási esetek megtekintése](./media/get-support/view-support-tickets.png)

- Kizárólag az új munkafolyam használatával megnyitott támogatási esetek jeleníthetők meg e munkafolyamon belül. A megtekintésükhöz válasszon olyan Súgó és támogatás nézetet az Eszközkezelés konzolon, amelyik már az új felület részét képezi. Ezeket az eseteket nyolcjegyű számok jelölik. A Microsoft 365 felügyeleti központjában is megtekinthetők az esetek.  

- Azok az esetek, amelyeket még azelőtt nyitott, hogy fiókját hozzáadtuk volna az új Súgó és támogatás felülethez, nem módosulnak. A megtekintésükhöz olyan Súgó és támogatás nézetet kell használnia, amelyik nem része az új felület bevezetésének. Ezek az esetek **117**-tel vagy **118**-cal kezdődő, 15 jegyű számokkal vannak ellátva.  Azon támogatási esetek megtekintéséhez, amelyeket még azelőtt nyitott, hogy fiókját hozzáadtuk volna az új felülethez, használja az Azure portalt. Ehhez tegye a következőket:

    1. Az Intune rendszergazdai hitelesítő adataival jelentkezzen be az Azure-ba (<https://portal.azure.com>), majd válassza a *?* lehetőséget ikonra a portál jobb felső sarkában, majd a *Súgó + támogatás* lehetőség kiválasztásával lépjen tovább az [Azure Súgó + támogatás](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview) oldalra.

    2. A **Súgó és támogatás** lapon megtekintheti a **legutóbbi támogatási kérelmek** listáját, és az egyes elemeket kijelölve további információt kaphat róluk.

## <a name="additional-resources"></a>További források
- [Kapcsolatfelvétel a Microsoft Intune telefonos tanácsadással](phone-support-contact.md)
- [Számlázási és előfizetés-kezelési támogatás](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Mennyiségi licencelés](http://go.microsoft.com/fwlink/p/?LinkID=282015)
- [A Intune hibáinak elhárítása](help-desk-operators.md)