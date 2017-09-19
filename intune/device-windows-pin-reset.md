---
title: "Windows-eszközök PIN-kódjának alaphelyzetbe állítása az Intune-nal"
titlesuffix: Azure portal
description: "Útmutató az Intune használatához a Microsoft PIN-kód-átállítási szolgáltatásával (Microsoft PIN Reset Service) integrált Windows-eszközök PIN-kódjának alaphelyzetbe állítására.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: faf3e9b81f76755135f73f8753305d96d227ec14
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/15/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>A Microsoft PIN-kód-átállítási szolgáltatásával (Microsoft PIN Reset Service) integrált Windows-eszközök PIN-kódjának alaphelyzetbe állítása az Intune használatával

A Windows-eszközök PIN-kódját alaphelyzetbe állító funkció a Microsoft PIN-kód-átállítási szolgáltatásával (Microsoft PIN Reset Service) integrálva lehetővé teszi új PIN-kód generálását a Windows 10 mobil verzióját futtató eszközökhöz. Az eszközön a Windows 10 alkotói frissítésének vagy újabb verziónak kell futnia.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – támogatott a Windows 10 Creators Update vagy újabb verzióin (Azure AD-hoz csatlakozott)
- Windows Phone – nem támogatott
- iOS – nem támogatott
- macOS – nem támogatott
- Android – nem támogatott


## <a name="before-you-start"></a>Előkészületek

Ahhoz, hogy távolról alaphelyzetbe állíthassa a felügyelt Windows-eszközök PIN-kódját, be kell vezetnie a PIN-kód-átállítási szolgáltatást az Intune-bérlőnél, és konfigurálnia kell a felügyelt eszközöket. Mindez a következő lépésekben állítható be:

### <a name="connect-intune-with-the-pin-reset-service"></a>Kapcsolódjon az Intune-hoz a PIN-kód-átállítási szolgáltatással

1. Nyissa meg a [Microsoft PIN Reset Service integrációs webhelyét](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent), és jelentkezzen be az Intune-bérlő kezeléséhez használt bérlői rendszergazda fiókjával.
2. Bejelentkezés után az **Elfogadom** gombra kattintva járuljon hozzá, hogy a Microsoft PIN-kód-átállítási szolgáltatás hozzáférjen a fiókjához.<br>
![PIN Reset Service – engedélyek lap](./media/pin-reset-service-application.png)
3. Az Intune és a PIN-kód-átállítási szolgáltatás integrációját az Azure Portalon ellenőrizheti, a Vállalati alkalmazások -> Minden alkalmazás panelen, ahogyan az alábbi képen látható:<br>
![PIN reset service alkalmazás az Azure-ban](./media/pin-reset-service-home-screen.png)
4. Jelentkezzen be [ezen a webhelyen](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) az Intune bérlői rendszergazda hitelesítő adataival, és az **Elfogadom** gombra kattintva ezúttal is járuljon hozzá, hogy a szolgáltatás hozzáférjen a fiókjához.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Windows-eszközök konfigurálása a PIN-kód alaphelyzetbe állításához

A PIN-kód alaphelyzetbe állításának beállításához a felügyelt Windows-eszközökön engedélyeznie kell a funkciót egy [Intune Windows 10-es egyéni eszközszabályzat](custom-settings-windows-10.md) használatával. A szabályzat az alábbi Windows szabályzatkonfigurációs szolgáltató (CSP) segítségével konfigurálható:


- **Eszközök esetén** - **./Device/Vendor/MSFT/PassportForWork/*bérlőazonosító*/Policies/EnablePinRecovery**

A *bérlőazonosító* az Azure Active Directory címtár-azonosítójára hivatkozik, amelyet az Azure Active Directory **Tulajdonságok** lapjáról tudhat meg.

Állítsa ennek a CPS-nek az értékét **True**-ra.

## <a name="steps-to-reset-the-passcode"></a>A PIN-kód alaphelyzetbe állításának lépései

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök** panelen válassza a **Felügyelet** > **Minden eszköz** lehetőséget.
5. Válassza ki az eszközt, amelynek alaphelyzetbe kívánja állítani a PIN-kódját, majd az eszköz tulajdonságok paneljén válassza az **Új PIN-kód** lehetőséget.
6. A megerősítést kérő ablakban válassza az **Igen** lehetőséget. A PIN-kód létrejön, és a következő hét nap folyamán megtekinthető a portálon.

## <a name="next-steps"></a>További lépések

Ha a PIN-kód alaphelyzetbe állítása nem sikerül, akkor a portál egy hivatkozást kínál fel, amelyen további információkat érhet le.


