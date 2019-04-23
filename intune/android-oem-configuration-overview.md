---
title: OEMConfig használata az Android Enterprise eszközökön a Microsoft Intune – Azure |} A Microsoft Docs
description: A Microsoft Intune segítségével kezelheti és OEMConfig az Android Enterprise rendszerű eszközök használata. Minden egyes lépést, beleértve a áttekintése, tekintse meg az előfeltételeket, a konfigurációs profil létrehozása az Intune-ban és támogatott OEMConfig alkalmazások listájának megtekintéséhez.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 022bbcf98a5e00888f33e22941515ca03c5f6995
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59901782"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Használhatja és kezelheti a Microsoft Intune-ban OEMConfig vállalati Android-eszköz

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A Microsoft Intune OEMConfig használatával adja hozzá, létrehozása és testreszabása a vállalati Android-eszköz OEM-specifikus beállításokat. OEMConfig általában szolgál, amely nem beépített részei az Intune-beállítások konfigurálása. Különböző OEM-ek különböző beállításokat tartalmazza. Így a rendelkezésre álló beállítások függ az OEM tartalma azok OEMConfig alkalmazásban.

Ez a funkció az alábbiakra vonatkozik:  

- Vállalati Android

Ez a cikk azt ismerteti, OEMConfig, mire, a szükséges előfeltételeket ismerteti, bemutatja, hogyan hozhat létre egy profilt és sorolja fel az támogatott OEMConfig alkalmazásokat az Intune-ban.

## <a name="overview"></a>Áttekintés

OEMConfig házirendek nincsenek eszközkonfigurációs szabályzat nagyon hasonlít egy speciális típusú [alkalmazáskonfigurációs szabályzat](app-configuration-policies-overview.md). OEMConfig rendszer által meghatározott standard a [AppConfig közösségi](https://www.appconfig.org/android-oemconfig/) (megnyílik egy másik webhely), amely lehetővé teszi, hogy számítógépgyártók (az eredeti berendezésgyártók) és a EMMs (enterprise mobility management) hozhat létre, és támogatja az OEM-specifikus szolgáltatások egy egységes módon. Hagyományosan EMMs, például az Intune-ban manuálisan hozhat létre az OEM-specifikus szolgáltatások támogatása után azok az OEM által vagyunk bevezetni. Ez a megközelítés duplikált erőfeszítések és a lassú bevezetési vezet.

OEMConfig az OEM létrehoz egy sémát, amely meghatározza az OEM-specifikus felügyeleti funkciókat. Az OEM a séma beágyazása egy alkalmazásba, és majd helyezi az alkalmazást a Google Play áruházból. A EMM beolvassa a sémát az alkalmazásból, és elérhetővé teszi a sémát a EMM felügyeleti konzolon. A konzol lehetővé teszi, hogy az Intune-rendszergazdák a beállítások konfigurálása a sémában.

A OEMConfig alkalmazás van telepítve az eszközön, ha azt a EMM felügyeleti konzolon konfigurált beállítások használatával felügyeli az eszközt. Az eszközön található beállítások futtatásukat az OEMConfig alkalmazás helyett a EMM által készített MDM-ügynökkel.

Amikor az OEM ad hozzá, és javítja a felügyeleti funkciók, az OEM frissíti az alkalmazást a Google Play áruházból is. A rendszergazdák kap az új funkciókról és a frissítések (beleértve a javítások) EMMs tartalmazza a frissítések várakozás nélkül.

> [!TIP]
> Használhatja OEMConfig csak olyan eszközökkel, amelyek támogatják ezt a szolgáltatást, és rendelkezik a megfelelő OEMConfig alkalmazással. Részletekért tekintse meg az OEM.

## <a name="before-you-begin"></a>Előkészületek

OEMConfig használatakor vegye figyelembe a következő információkat:

- Intune a OEMConfig app séma tesz elérhetővé, így a segítségével konfigurálhatja. Az Intune nem ellenőrzése, vagy módosítsa a sémát, az alkalmazás által biztosított. Így ha a séma helytelen, vagy pontatlan adatokat, majd ezeket az adatokat továbbra is megkap eszközökre. Ha a séma származó problémát észlel, forduljon az OEM útmutatást.
- Az Intune nem befolyásolja, vagy szabályozhatja az alkalmazás séma tartalma. Például az Intune nem szabályozhatják minden olyan karakterláncok, nyelvi, az engedélyezett műveletek és így tovább. Azt javasoljuk, hogy vegye fel a kapcsolatot az OEM a részletekért és az eszközeiket az OEMConfig kezelésére vonatkozó ajánlott eljárások.
- Bármikor OEM-ek frissítheti a támogatott funkciókkal és sémák, és töltse fel egy új alkalmazást a Google Play áruházból. Az Intune mindig szinkronizálja a legújabb verzióra a OEMConfig alkalmazás Google Play áruházból. Az Intune nem tartanak fenn a séma vagy az alkalmazás régebbi verzióját. Ha tapasztal verziót ütközések, javasoljuk, vegye fel a kapcsolatot az OEM további információt.
- Kell hozzárendelhet csak egy OEMConfig profilt egy eszközhöz. Ha több profil hozzá van rendelve, ugyanarra az eszközre, kiszámíthatatlan működést jelenhet meg. A OEMConfig modell eszközönként egy szabályzatban csak támogatja.

## <a name="prerequisites"></a>Előfeltételek

Az eszközök OEMConfig használatához győződjön meg az alábbi követelményekkel rendelkezik:

- Az Android Enterprise-eszköz regisztrálása az Intune-ban.
- OEMConfig alkalmazás az OEM által készített, és feltölti a Google Play áruházból. Ha nem a Google Play áruházból, további információért forduljon az OEM.
- Az Intune-rendszergazda rendelkezik szerepköralapú hozzáférés-vezérlés (RBAC) vonatkozó **mobilalkalmazások** és **DeviceConfigurations**. Ennek az az oka OEMConfig profilok győződjön meg arról, eszköz-konfigurációk kezelése az által kezelt alkalmazás konfigurációjának használatával.

## <a name="prepare-the-oemconfig-app"></a>A OEMConfig alkalmazás előkészítése

Győződjön meg arról, hogy az eszköz támogatja-e OEMConfig, a megfelelő OEMConfig alkalmazáshoz hozzáadott az Intune-hoz, és hogy az alkalmazás telepítve van az eszközön. Forduljon az OEM ezt az információt.

> [!TIP] 
> Az OEM OEMConfig alkalmazások kapcsolódnak. Ha például egy Sony OEMConfig az alkalmazás telepítve van az eszközön Zebra technológiák sem csinál.

1. Lekérheti a OEMConfig app a felügyelt Google Play Store. [Felügyelt Google Play-alkalmazások hozzáadása a vállalati Android-eszköz](apps-add-android-for-work.md) felsorolja azokat a lépéseket.
2. Egyes számítógépgyártók (OEM) lehetséges, hogy el olyan eszközöket, az előre telepített OEMConfig alkalmazással. Ha az alkalmazás nincs telepítve, használja az Intune-nal [hozzáadása és az alkalmazás üzembe helyezése az eszközök](apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>OEMConfig profil létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg az új profil leíró nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki **Android enterprise**.
    - **Profil típusa**: Válassza ki **OEMConfig**.

4. Válassza ki **társított alkalmazás**, és válasszon ki egy meglévő OEMConfig alkalmazást a korábban hozzáadott. Mindenképp válassza ki a megfelelő OEMConfig alkalmazást, még a szabályzat hozzárendelése az eszközökhöz.

    Ha nem látja a felsorolt alkalmazások, majd állítsa be a felügyelt Google Play, és -alkalmazások beszerzése a felügyelt Google Play áruházból. [Felügyelt Google Play-alkalmazások hozzáadása a vállalati Android-eszköz](apps-add-android-for-work.md) felsorolja azokat a lépéseket.

    > [!IMPORTANT]
    > Ha hozzáadott egy OEMConfig alkalmazást, és a Google Play áruházból szinkronizált, de nem szerepel egy **társított alkalmazás**, forduljon az Intune-ban üzembe helyezni az alkalmazást is. Lásd: [új alkalmazás felvételére](#supported-oemconfig-apps) (a jelen cikkben).

5. Válassza a **Configuration** (Konfigurálás) lapot.

    A konfigurációs séma az alkalmazás a beágyazott sablon JSON-szerkesztővel nyílik meg. A szerkesztőben testre szabhatja a sablont a különböző konfigurációs beállítások értékeit. 
    
    OEMConfig sémák nagy és összetett lehet, mivel a **JSON-sablon letöltése** gombot, amellyel elkezdheti a sablont egy fájlba. Konfigurálja a sablon fájlt egy tetszőleges szövegszerkesztőben, és másolja a tartalmat a Intune felügyeleti konzolba.

6. Válassza ki **OK** > **Hozzáadás** a módosítások mentéséhez. A házirend létrehozása és jelennek meg a listában.

Ügyeljen arra, hogy [rendelje hozzá a profilt](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).
    
 > [!NOTE]
 > Egy profil hozzárendelése az adott eszközön. A OEMConfig modell csak az eszközönként egy szabályzat támogatja.

A következő alkalommal ellenőrzi az eszköz konfigurációs frissítések, a OEMConfig alkalmazás megadott OEM-specifikus beállítások érvényesek.

## <a name="supported-oemconfig-apps"></a>Támogatott OEMConfig alkalmazások

Standard szintű alkalmazások képest, OEMConfig alkalmazások bontsa ki az összetettebb sémák támogatja a Google által felügyelt konfigurációk jogosultsággal. Az Intune jelenleg a következő OEMConfig alkalmazásokat támogatja:

-----------------

| OEM | Csomagazonosító |
| --- | --- |
| Samsung | com.samsung.android.knox.kpu |

-----------------

Kérjen új OEMConfig alkalmazás lesz bevezetve, e-mailben `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> OEMConfig alkalmazások előre telepített Intune előtt kell azok OEMConfig profilok is konfigurálhatók.

## <a name="next-steps"></a>További lépések

- [Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).
