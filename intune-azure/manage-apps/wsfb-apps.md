---
title: "A Vállalati Windows Áruházból származó alkalmazások kezelése | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató a Vállalati Windows Áruházból származó alkalmazások Intune-ba való szinkronizálásához, és ezután azok hozzárendeléséhez és nyomon követéséhez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a57ac0e6cb29dbfc87bb09c04bb372228a1d72be
ms.openlocfilehash: 2acb58a8fc71ae7f2e0bce127e709a678faa27cb

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business"></a>A Vállalati Windows Áruházban vásárolt alkalmazások kezelése

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


A [Vállalati Windows Áruház](https://www.microsoft.com/business-store) az a hely, ahol alkalmazásokat vásárolhat a szervezete számára egyenként vagy nagyobb mennyiségben. Az áruházat a Microsoft Intune-nal összekapcsolva a mennyiségi licencszerződés keretében vásárolt alkalmazásokat az Intune-portálról kezelheti. Példa:
* Szinkronizálhatja az áruházban vásárolt alkalmazások listáját az Intune-nal.
* A szinkronizált alkalmazások megjelennek az Intune felügyeleti konzolján, és a többi alkalmazáshoz hasonlóan rendelheti hozzá őket.
* Az Intune felügyeleti konzolján nyomon követheti a szabad és a használatban lévő licencek számát.
* Ha nincs elegendő elérhető licenc, az Intune letiltja az alkalmazások központi telepítését.

## <a name="before-you-start"></a>Előkészületek
Mielőtt elkezdi a Vállalati Windows Áruházból származó alkalmazások szinkronizálását és telepítését, tekintse át a következő információkat:
* Az Intune-t kell beállítania mobileszköz-kezelő szolgáltatóként a szervezetben.
* Rendelkeznie kell fiókkal a Vállalati Windows Áruházban.
* Miután összekapcsolta a Vállalati Windows Áruház-fiókját az Intune-nal, később nem választhat hozzá másik fiókot.
* Az áruházban vásárolt alkalmazások manuálisan nem vehetők fel és nem törölhetők az Intune-ban. Az alkalmazások csak a Vállalati Windows Áruházzal szinkronizálhatók.
* Az Intune csak a Vállalati Windows Áruházban vásárolt, online licenccel rendelkező alkalmazásokat szinkronizálja.
* Az eszközök akkor használhatják ezt a funkciót, ha csatlakoztatva vannak az Active Directory Domain Serviceshez vagy egy munkahelyhez.
* A regisztrált eszközöknek a Windows 10 1511-es vagy újabb verzióját kell használniuk.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>A Vállalati Windows Áruház-fiók összekapcsolása az Intune-nal
Mielőtt engedélyezné a szinkronizálást az Intune-konzolon, konfigurálnia kell az áruházbeli fiókját az Intune használatára felügyeleti eszközként:
1. Ügyeljen arra, hogy a Vállalati Áruházba való bejelentkezéshez ugyanazt a bérlői fiókot használja, mint az Intune-ba való bejelentkezéshez.
2. A Vállalati Áruházban válassza a **Beállítások** > **Felügyeleti eszközök** lehetőséget.
3. A Felügyeleti eszközök lapon válassza a **Felügyeleti eszköz hozzáadása**, majd a **Microsoft Intune** lehetőséget.

> [!NOTE]
> Ha több felügyeleti eszközt is használ a Vállalati Windows Áruházbeli alkalmazások üzembe helyezésére, akkor korábban ezek közül csak egyet társíthatott a Vállalati Windows Áruházhoz. Mostantól több felügyeleti eszközzel is megteheti ezt (például az Intune-nal és a Configuration Managerrel).

Most már folytathatja a műveletet, és beállíthatja a szinkronizálást az Intune-konzolon.

## <a name="configure-synchronization"></a>A szinkronizálás konfigurálása

1. Jelentkezzen be az Azure Portal webhelyre.
2. Válassza a **További szolgáltatások** > **Egyéb** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Alkalmazások kezelése** lehetőséget.
1. A **Mobilalkalmazások** panelen válassza a **Beállítás** > **Vállalati Windows Áruház** lehetőséget.
2. Kattintson az **Engedélyezés** lehetőségre.
3. Ha még nem tette meg, kattintson a Vállalati Windows Áruházba való regisztráció hivatkozására és társítsa a fiókját a fentebb leírtaknak megfelelően.
5. A **Nyelv** legördülő listából válassza ki azt a nyelvet, amelyet a Vállalati Windows Áruházból származó alkalmazásoknak az Intune-portálon való megjelenítéséhez kíván használni. Az alkalmazások a végfelhasználó nyelvén lesznek telepítve (ha ez elérhető), függetlenül a megjelenítéshez választott nyelvtől.
6. Kattintson a **Szinkronizálás** lehetőségre a Windows Áruházból megvásárolt alkalmazások Intune-ba való felvevéséhez.

## <a name="synchronize-apps"></a>Az alkalmazások szinkronizálása

1. Az **Alkalmazások kezelése** tevékenységprofilon válassza a **Beállítás** > **Vállalati Windows Áruház** elemet.
2. Kattintson a **Szinkronizálás** lehetőségre a Windows Áruházból megvásárolt alkalmazások Intune-ba való felvételéhez.

## <a name="assign-apps"></a>Alkalmazások hozzárendelése

Az Áruházból származó alkalmazásokat ugyanúgy rendelheti hozzá, mint a többi Intune-alkalmazást. További információ: [How to assign apps to groups with Microsoft Intune](deploy-apps.md) (Alkalmazások hozzárendelése csoportokhoz a Microsoft Intune-nal). Az **Összes alkalmazás** oldal helyett azonban a **Licencelt alkalmazások** oldalról rendelheti hozzá az alkalmazásokat.

A Vállalati Windows Áruházból származó alkalmazások hozzárendelésekor az alkalmazást telepítő minden felhasználóhoz meg kell adnia egy-egy licencet. Ha felhasználja egy telepített alkalmazás összes elérhető licencét, akkor nem telepíthet több példányt. Végre kell hajtania a következő műveletek valamelyikét:
* Távolítsa el az alkalmazást néhány eszközről.
* Csökkentse az aktuális telepítés hatókörét annyi felhasználóra, ahány elérhető licenccel rendelkezik.
* Vásároljon további példányokat az alkalmazásból a Vállalati Windows Áruházban.

> [!Important]
> A telepített alkalmazásokhoz csak az a felhasználó férhet hozzá, aki eredetileg regisztrálta az eszközt. Más felhasználók nem férhetnek hozzá az alkalmazásokhoz.



<!--HONumber=Feb17_HO1-->

