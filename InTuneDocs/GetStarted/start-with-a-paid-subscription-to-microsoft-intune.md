---
title: "Az Intune rövid kezdési útmutatója | Microsoft Intune"
description: "Az Intune-előfizetés használatának megkezdéséhez szükséges követelmények és előfeltételek"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: aecd5f76e234835c38bf47d8de7e13034d683998


---


# Az Intune bemutatása
Ez a rövid útmutató végigvezeti a fizetős Microsoft Intune-előfizetés beállításának lépésein, így gyorsan és egyszerűen felügyelhetővé válnak a szervezete által használt mobileszközök és Windows rendszerű számítógépek. A lépéseket követheti sorrendben, vagy kihagyhatja azokat, amelyek nem érvényesek a környezetére vagy nem kapcsolódnak az üzleti igényeihez.

>[!NOTE]
>Ez a cikk az Intune különálló szolgáltatásként történő beállításával foglalkozik. Alternatív megoldásként, ha jelenleg a Microsoft System Center Configuration Manager használatával felügyeli a számítógépeket és a kiszolgálókat, [kiterjesztheti a Configuration Manager hatáskörét, hogy az a mobileszközöket is felügyelje](https://technet.microsoft.com/library/jj884158.aspx). Ezt úgy teheti meg, ha az Intune-t egy hibrid mobileszköz-felügyeleti (MDM) környezetben összekapcsolja a Configuration Managerrel.

A jelen rövid bevezető útmutatóban ismertetett lépések nagy része megegyezik az [Intune próbaverziójának útmutatójában](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) leírt lépésekkel. Azonban amikor a próbaverzió lejártával hozzákészül a mobileszközei felügyeletéhez, több további követelménynek is meg kell felelnie:

-   A helyi Active Directory-fiókok szinkronizálása az Intune szolgáltatással és az Azure Active Directory-val.

-   A nyilvános tartományi és DNS-szolgáltatási rekordok frissítése a tartományregisztrátornál.

-   Az Intune-funkciók testreszabása üzemi használatra.

>[!TIP]
>Ha legalább 150 licencet vásárolt a Microsoft Intune-hoz egy erre jogosult csomagban, használhatja a *FastTrack Center juttatást*, azt a szolgáltatást, amelyben a Microsoft szakértőivel együtt készítheti fel környezetét az Intune használatára. Lásd: [A Microsoft Intune szolgáltatási juttatás leírása](https://technet.microsoft.com/library/mt228265.aspx).


## Előkészületek
Ezt az útmutatót akkor használhatja, ha a szolgáltatás fizetős verziójára fizet elő, és készen áll az Intune telepítésére, valamint a meglévő hálózati infrastruktúra módosítására. Ezek a feladatok a belső és külső DNS-rekordok létrehozásától vagy frissítésétől egészen a meglévő Active Directory felhasználói fiókoknak az Azure Active Directory-ba történő szinkronizálásáig terjedhetnek. Az Intune mobileszköz-felügyeleti funkcióinak bármilyen kombinációja mellett dönt is, gondosan meg kell terveznie, hogy az Intune hogyan működjön együtt a meglévő hálózati összetevőkkel és szolgáltatásokkal. Az alábbi szempontokra különösen nagy hangsúlyt fektessen:

-   **A felhasználói identitás kezelése**: A legtöbb közép- és nagyvállalat esetében az Intune-felhasználók identitását úgy kezelheti a leghatékonyabban és legkényelmesebben, hogy az Azure Active Directory segítségével összekapcsolja a meglévő címtárszolgáltatásokat az Intune-nal. Ez különösen akkor célszerű, ha egyéb felhőalapú Microsoft-szolgáltatásokat, például Office 365-öt vagy Exchange Online-t is használ. A helyi Active Directory és az Azure Active Directory összekapcsolása, valamint az egyszeri bejelentkezéses felhasználói hitelesítés beállítása gyorsan és egyszerűen elvégezhető a meglévő felhasználói fiókok [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) használatával történő szinkronizálásával.

-   **A DNS-sel kapcsolatos szempontok:** Ha saját tartománynevét szeretné használni az Intune szolgáltatásba regisztráláskor kapott alapértelmezett onmicrosoft.com tartomány helyett, akkor néhány nyilvános DNS-rekordot frissítenie kell. A DNS-rekordok frissítése azért szükséges, hogy a mobileszközök megtalálhassák az Intune szolgáltatást, és annak ellenőrzéséhez, hogy az előfizetés megfelelően működik, és kezeli a szervezet által használt összes eszközt.

## A következőkre lesz szüksége
Készen áll a kezdésre? Ahhoz, hogy megkezdhesse az Intune fizetős verziójának használatát, a következők szükségesek:

### Egy Silverlight-kompatibilis webböngészővel rendelkező eszköz
Ez az Intune felügyeleti konzoljának eléréséhez szükséges, ahol kezelheti az eszközöket, az alkalmazásokat és a szabályzatokat. Szükség lesz egy webböngészőre is, amellyel hozzáfér a webes Intune Vállalati portálhoz akkor, amikor a mobileszközről nem fér hozzá a Vállalati portál alkalmazáshoz. A művelet egyszerűsítéséhez használja az Intune-felügyelethez használt böngésző adatvédelmi üzemmóddal kapcsolatos beállítását (az Internet Explorerben például válassza az **Eszközök** &gt; **InPrivate-böngészés** lehetőséget).

>[!TIP]
>Ezen követelmény miatt a Microsoft Edge böngésző nem támogatott az Intune felügyeleti konzoljának eléréséhez.


### Mobileszközök tanúsítványai
Ha iOS- vagy Windows Phone-eszközöket felügyel az Intune-nal, akkor tanúsítványokra és a tanúsítványokat lekérő fiókokra lesz szüksége. Android-eszközök kezeléséhez nincs szükség külön tanúsítványokra.

- A **Windows Phone 8.1** azon felhasználói számára, akik az Áruházból telepítik a Vállalati portál alkalmazást, nem szükséges tanúsítvány. [Symantec kódaláíró tanúsítvány](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) szükséges azonban a **Windows Phone 8.0** esetén, vagy ha a Vállalati portál alkalmazást az Intune szolgáltatással kívánja Windows Phone 8.1-eszközre telepíteni.

>[!NOTE]
>Ez a rövid útmutató azt feltételezi, hogy az Ön felhasználói az Áruházból származó Vállalati portál alkalmazást Windows Phone 8.1 vagy újabb rendszerű eszközön telepítik. A Windows Phone 8.0 támogatásával kapcsolatos információk: [Set up Windows Phone 8.0 management with Microsoft Intune](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune) (Windows Phone 8.0 rendszerű telefonok Microsoft Intune-beli felügyeletének beállítása).

- Ha a számítógépeket eszközként regisztrálja, vagy [telepíti a Microsoft Intune windowsos számítógépügyfelét](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune), akkor a **Windows rendszerű számítógépekhez** és **Windows RT-eszközökhöz** nincs szükség tanúsítványokra.

- Az **iOS** vagy a **Mac OS X** rendszerű eszközökhöz Apple Push Notification szolgáltatásbeli tanúsítványt kell igényelnie az Apple-től [Az iOS kezelésének beállítása a Microsoft Intune-nal](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) témakör 3. lépésében leírtak szerint.

## További lépések
Itt az ideje, hogy megismerkedjen az Intune rövid kezdési útmutatójával!

>[!div class="step-by-step"]
[**Bejelentkezés az Intune-ba** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)



<!--HONumber=Aug16_HO5-->


