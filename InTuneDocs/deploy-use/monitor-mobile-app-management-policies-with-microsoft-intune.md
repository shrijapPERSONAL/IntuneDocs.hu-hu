---
title: "MAM-szabályzatok figyelése a Microsoft Intune-nal | Microsoft Intune"
description: "Megtudhatja, hány felhasználóra érvényes a szabályzat, és lefúrással megjelenítheti a részleteket."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 487fe778bae73c2ac5564f90c21328932060f576


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Mobilalkalmazás-felügyeleti szabályzatok figyelése a Microsoft Intune-nal
Miután létrehozott egy mobilalkalmazás-kezelési (MAM) szabályzatot, és alkalmazta a felhasználókra, az [Azure Portalon](https://portal.azure.com) felügyelheti a megfelelési állapotot. Az Azure Portalon információkat talál a szabályzat által érintett felhasználókról, a megfelelési állapotokról, valamint a felhasználók által esetleg tapasztalt problémákról.
## <a name="summary-view"></a>Összesített nézet
Az **Intune mobilalkalmazás-kezelés** paneljén megtekintheti a megfelelési állapot összefoglalását:


![Az Intune mobilalkalmazás-kezelés panel Összefoglalás csempéje](../media/mam-azure-portal-user-status-summary.png)

-   **Felhasználók:** a szabályzathoz társított alkalmazásokat használó felhasználók száma a vállalatnál.

-   **HÁZIREND ÁLTAL KEZELT:** azon felhasználók száma, akik az alkalmazások közül legalább egyet már használtak a munkahelyi környezetben.

-   **NEM TALÁLHATÓ HÁZIREND:** azon felhasználók száma, akik használják ugyan a szabályzathoz társított alkalmazásokat, de akikre nem vonatkozik a beállított szabályzat. Érdemes megfontolni ezen felhasználók bevonását a szabályzat hatálya alá.

- **Megjelölt felhasználók:** a problémákat tapasztaló felhasználók száma. A rendszer jelenleg a **Megjelölt felhasználók** részben kizárólag a jailbreakelt eszközt használó felhasználókat jelöli meg.


## <a name="detailed-view"></a>Részletes nézet
Ha meg szeretné tekinteni az összefoglalás részleteit, válassza a **Felhasználó állapota** csempére vagy a **Megjelölt felhasználók** csempét.

### <a name="user-status"></a>Felhasználó állapota
Itt megkeresheti az adott felhasználókat, és ellenőrizheti a megfelelési állapotukat. Az **Alkalmazásjelentések** panelen a következő információk tekinthetők meg a kiválasztott felhasználóról:
- A felhasználói fiókhoz társított eszközök listája

- Az eszközön futó, MAM-szabályzat hatálya alá tartozó alkalmazások listája

- Állapot:

  - **Beadva:** a szabályzat települt a felhasználónál, és az alkalmazást legalább egyszer már használták a munkahelyi környezetben.

  - **Nincs beadva:** a szabályzat települt a felhasználónál, de az alkalmazást még egyszer sem használták a munkahelyi környezetben.

>[!NOTE]
> Ha a keresett felhasználó nem rendelkezik telepített MAM-szabályzattal, egy üzenetet fog látni, amely szerint a felhasználóra nem vonatkozik egyetlen alkalmazásszabályzat sem.

A felhasználóhoz tartozó jelentések megtekintéséhez kövesse az alábbi lépéseket:

1.  Felhasználó kiválasztásához kattintson az **Összefoglalás** csempére, vagy válassza a **FELHASZNÁLÓI ALKALMAZÁSJELENTÉSEK** elemet a **Beállítások** panelen:

    ![Alkalmazásjelentési lehetőség a Beállítások panelen](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. A megjelenő **Alkalmazásjelentések** panelen válassza a **Felhasználó kijelölése** lehetőséget, és keresse meg a kívánt Azure Active Directory-felhasználót.

    ![A Felhasználó kijelölése elem az Alkalmazásjelentések panelen](../media/mam-azure-portal-app-reporting-select-user.png)

3. Válassza ki a listából a felhasználót. Megjelennek a felhasználó megfelelési állapotára vonatkozó információk.

    ![Alkalmazásjelentési információk](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Megjelölt felhasználók
A részletes nézetben látható a hibaüzenet, annak az alkalmazásnak a neve, amelynek a használata közben fellépett a hiba, az eszközön futó platform, valamint egy időbélyegző.  

### <a name="see-also"></a>További információ
[iOS-alkalmazások közti adatátvitel kezelése](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Mi várható az Android-alkalmazás MAM-szabályzatok általi kezelésekor](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Mi várható az iOS-alkalmazás MAM-szabályzatok általi kezelésekor](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


