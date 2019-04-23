---
ms.openlocfilehash: fbfff91d2993becc99e2132285bef78d245ff50e
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61497940"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10-es eszközök automatikus regisztrációjának engedélyezése

Az automatikus regisztrálással a felhasználók úgy is regisztrálhatják Windows 10-es eszközeiket az Intune-ban, hogy munkahelyi fiókjukat hozzáadják a személyes tulajdonú eszközeiken, vagy ha céges tulajdonban lévő eszközeiket csatlakoztatják az Azure Active Directoryhoz. A háttérben a felhasználó eszköze regisztrálja magát és csatlakozik az Azure Active Directory-hoz. A regisztrációt követően az eszközt az Intune felügyeli.

**Előfeltételek**
- Azure Active Directory Premium-előfizetés ([próba-előfizetés](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-előfizetés


### <a name="configure-automatic-mdm-enrollment"></a>Az automatikus MDM-regisztráció konfigurálása

1. Jelentkezzen be a [Azure felügyeleti portálján](https://portal.azure.com) (https://manage.windowsazure.com) , és válassza ki **Azure Active Directory**.

   ![Az Azure Portal képernyőképe](../media/auto-enroll-azure-main.png)

2. Válassza a **Mobilitás (MDM és MAM)** elemet.

   ![Az Azure Portal képernyőképe](../media/auto-enroll-mdm.png)

3. Válassza a **Microsoft Intune** elemet.

   ![Az Azure Portal képernyőképe](../media/auto-enroll-intune.png)

4. Konfigurálja az **MDM-felhasználói hatókört**. Adja meg, hogy mely felhasználók eszközeit felügyelje a Microsoft Intune. E felhasználók Windows 10 rendszerű eszközeit a rendszer automatikusan belépteti a Microsoft Intune-felügyeletbe.

   - **Nincsenek**
   - **Néhány**
   - **Összes**

   ![Az Azure Portal képernyőképe](../media/auto-enroll-scope.png)

5. A következő URL-címekhez használja az alapértelmezett értékeket:
   - **MDM használati feltételeinek URL-címe**
   - **MDM-felderítési URL-cím**
   - **MDM megfelelőségi URL-címe**

6. Kattintson a **Mentés** gombra.

Alapértelmezés szerint a kétfaktoros hitelesítés nincs engedélyezve a szolgáltatáshoz. Ezzel együtt azonban az eszköz regisztrálásához ajánlatos kétfaktoros hitelesítést használni. Mielőtt kötelezővé tenné a kétfaktoros hitelesítést a szolgáltatáshoz, konfigurálnia kell egy kétfaktoros hitelesítési szolgáltatót az Azure Active Directoryban, a felhasználói fiókokat pedig többtényezős hitelesítéshez kell konfigurálnia. További információt az [Azure Multi-Factor Authentication-kiszolgáló – első lépések](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud) című témakörben talál.
