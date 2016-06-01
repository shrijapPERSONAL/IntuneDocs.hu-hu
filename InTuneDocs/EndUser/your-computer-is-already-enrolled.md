---
# required metadata

title: A számítógépe már be van léptetve | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Számítógépe már be van léptetve
Ez a lap azért jelent meg, mert az Intune ügyfélszoftver telepítőjét futtatta. A szoftver azonban már telepítve van a számítógépen, és a telepítés nem folytatható.

Ez az alábbi okokból fordulhat elő:

-   Az ügyfélszoftvert korábban már telepítették, és a telepítő újra futott.

-   A telepítőt azt követően futtatták a számítógépen, hogy egy informatikai rendszergazda kivonta az eszközt az Intune-ból. Az eszköz kivonását követően több órába is beletelhet, mire megtörténik az ügyfélszoftver eltávolítása a számítógépről.

-   A telepítő az ügyfélszoftver közelmúltbeli sikertelen telepítését vagy eltávolítását észlelte.

## Amit a telepítő a számítógépre telepít
A telepítő az Intune ügyfélszoftvert telepíti. A telepítés befejezése után az ügyfélszoftver továbbra is fut a háttérben, ahol beállítja a számítógépet az Intune-nal való használatra. A folyamat eltarthat egy ideig, és az alábbiakból áll:

-   A számítógép regisztrálása az Intune-ban

-   Leltár küldése a számítógép hardveréről és a telepített szoftverekről

-   Az Intune-házirend beállítása, beleértve az Endpoint Protection telepítését (ha be van állítva)

-   Az Intune Center telepítése

Az Intune Centert telepítés után a vállalati portál eléréséhez használhatja, ahol számítógépét a munkahelyi fiókjához társíthatja.

## Microsoft Intune Center
Az Intune Center alkalmazásként települ a számítógépén, miután a számítógép sikeresen telepítette az ügyfélszoftvert, és regisztrálta a számítógépet az Intune-ban. Az Intune Center a következőkre használható:

-   **Alkalmazások beszerzése a vállalati portálról**: Az informatikai rendszergazda által üzembe helyezett alkalmazások megkeresése és telepítése. Amikor először bejelentkezik a vállalati portálra egy újonnan regisztrált számítógépen, lehetősége lesz a munkahelyi fiókját az adott számítógéppel társítania.

-   **Szoftverfrissítések keresése**: Az Intune-rendszergazda által telepített szoftverfrissítések keresése.

-   **A számítógép Endpoint Protection-vizsgálatának elindítása**: Elindíthatja a kártevő szoftverek keresését a számítógépen.

-   **Távsegítség kérése**: Ez a beállítás csak akkor érhető el, ha számítógépei operációs rendszere támogatja a távsegítséget.

## Annak ellenőrzése, hogy az ügyfélszoftver telepítve van-e vagy el lett távolítva.
**Annak ellenőrzése, hogy ügyfél telepítve van-e:**
Az Intune ügyfélszoftver telepítése akkor van kész, amikor az alábbi alkalmazások elérhetők a számítógépen:

-   **Intune Center**

-   **Intune Endpoint Protection** (ha az Endpoint Protectiont engedélyezte az informatikai rendszergazda)

Ha ismeri a Feladatkezelő használatát, megkeresheti az Intune ügyfélszolgáltatást, amelynek futnia kell:

-   **OmcSvc**

**Annak ellenőrzése, hogy ügyfél el lett-e távolítva:**
Miután befejeződött az Intune ügyfélszoftver eltávolítása a számítógépről, az ügyféllel telepített alkalmazások – beleértve az Intune Centert is – eltávolítása is megtörténik.

Az **OmcSvc** nevű Intune-ügyfélszolgáltatás törlődik.

## Az ügyfélszoftver eltávolítása a számítógépről
Alapértelmezés szerint néhány órával azt követően, hogy a rendszergazda kivonja a számítógépet az Intune felügyeleti konzolról, megtörténik az Intune eltávolítása.

Ha kézzel szeretné eltávolítani az Intune ügyfélszoftvert a számítógépekről, az alábbi lépések segítségével kényszerítheti az eltávolítást:

1.  A számítógépen nyisson meg egy parancssort rendszergazdai módban.

2.  Nyissa meg a **%programfiles%\Microsoft\OnlineManagement\Common** mappát.

3.  Futtassa a következő parancsot: **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**

Ez a művelet ütemezi az ügyfélszoftver eltávolítását.



<!--HONumber=May16_HO1-->


