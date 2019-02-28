---
title: Sablonok használata a Windows 10 rendszerű eszközökhöz a Microsoft Intune – Azure |} A Microsoft Docs
description: A Microsoft Intune felügyeleti sablonok használatával létre csoportokat a Windows 10 rendszerű eszközök beállításait. Eszközkonfigurációs profil található ezek a beállítások segítségével szabályozhatja az Office-alkalmazásokhoz, biztonságos, Internet Explorer szolgáltatásai, ki férhet hozzá a onedrive vállalati verzió, távoli asztali szolgáltatások használata, engedélyezze az automatikus lejátszás, beállítása energiagazdálkodási beállításokat, HTTP-nyomtatás, másik felhasználó használja bejelentkezési beállítások, és a vezérlő az eseménynapló méretét.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7b78cdc329e3d6f61dea49ddb28429c2f12d0d6
ms.sourcegitcommit: 95cc5f1e5e955acdff642191c174249465cc98bf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982232"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>A csoportházirend-beállítások konfigurálása a Microsoft Intune-ban Windows 10-sablonok használatával

A szervezet-eszközök kezelésekor érdemes hozzon létre egy csoportot, amelyek különféle eszközcsoportokra vonatkoznak. Például hogy több eszköz csoportot. GroupA, a hozzárendelni kívánt beállítások meghatározott készletét. GroupB, a hozzárendelni kívánt beállítások külön készletét. Azt is szeretné egy egyszerű nézet a konfigurálható beállítások.

Ez a feladat használatával hajthatja végre **felügyeleti sablonok** Microsoft Intune-ban. A felügyeleti sablonok akár több százszor is, hogy szolgáltatásokat az Internet Explorer, a Microsoft Office-alkalmazásokhoz, a távoli asztal beállításait tartalmazza, eléréséhez a onedrive-ba, használja a képjelszavak vagy jelentkezzen be a PIN-kódot, és több. Ezek a sablonok hasonló (GPO) csoportházirend-beállítások az Active Directory (AD), és [ADMX-biztonsági beállítások](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) (megnyílik egy másik Docs-webhely) használó XML. De a sablonok az Intune-ban, 100 %-os felhőalapú. Egy további egyszerű kínálnak lehetünk lépésig, adja meg a beállításokat, majd keresse meg a beállításokat, és szeretne.

**Felügyeleti sablonok** beépített Intune-ba, és nem igényel minden testre szabott elem, beleértve az OMA-URI-val. A mobileszköz-felügyelet (MDM) megoldás részeként használja ezeket a sablon beállításokat-nyújtani a Windows 10 rendszerű eszközök kezelése.

Ez a cikk felsorolja azokat a lépéseket a Windows 10-es eszközök sablon létrehozásához, és bemutatja, hogyan szűrheti a rendelkezésre álló beállítások a Microsoft Intune-ban. A sablon létrehozásakor egy eszközkonfigurációs profilt hoz létre. Ezután rendelje hozzá, vagy a szervezetében üzembe helyezi ezt a profilt a Windows 10-eszközökre.

> [!NOTE]
> Felügyeleti sablonok önálló eszközön támogatást élveznek. Azok jelenleg nem támogatottak a System Center Configuration Manager (SCCM) közösen kezelt eszközök.

## <a name="create-a-template"></a>Sablon létrehozása

1. Az a [az Azure portal](https://portal.azure.com), jelölje be **minden szolgáltatás** > szűréséhez **Intune** > Válassza ki **Intune**.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

    - **Név**: Adja meg a profil nevét.
    - **Description** (Leírás): Adja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
    - **Platform**: Válassza ki **Windows 10 és újabb**.
    - **Profil típusa**: Válassza ki **felügyeleti sablonok (előzetes verzió)**.

4. Kattintson a **Létrehozás** gombra. Jelölje ki az új ablakban **beállítások**. Minden beállítás szerepel a listán, és használhatja a, mielőtt és melletti nyíl további beállításokhoz:

    ![Minta beállítások listájának megtekintéséhez és az előző és Tovább gomb](./media/administrative-templates-windows/sample-settings-list-next-page.png)

5. Bármely beállítást. Válassza ki például **fájl letöltésének engedélyezése**. A beállítás részletes leírása jelenik meg. Válassza ki a **engedélyezése**, **letiltása**, vagy hagyja üresen a beállítást **nincs konfigurálva** (alapértelmezett). A részletes leírást is bemutatja, mi történik, ha úgy dönt, **engedélyezése**, **letiltása**, vagy **nincs konfigurálva**.
6. Válassza ki **OK** a módosítások mentéséhez.

Továbbra is haladjon végig a beállítások listájában, és konfigurálja a szükséges beállításokat a környezetében. Íme néhány példa:

- Használja a **VBA makró értesítési beállítások** kezelje a különböző Microsoft Office-alkalmazásokhoz, például a Word és Excel VBA makrók beállítás.
- Használja a **fájl letöltésének engedélyezése** beállítás engedélyezése vagy tiltása az Internet Explorer tölt le.
- Használja a **jelszó kérése, ha egy számítógép felébred (csatlakoztatva)** beállítás megkéri a felhasználót a jelszót, amikor az eszköz visszatér az alvó üzemmódból.
- Használja a **letölthető ActiveX-vezérlők aláíratlan** beállítás letiltása a felhasználók számára való letöltését aláíratlan ActiveX-vezérlők Internet Explorerből.
- Használja a **kapcsolja ki a rendszer-visszaállítási** beállítás engedélyezi vagy tiltja a rendszer-visszaállítás az eszközön.
- És még sok más...

## <a name="find-some-settings"></a>Egyes beállítások keresése

Nincsenek elérhető ezeket a sablonokat a beállítások több száz. Hogy könnyebben megtalálja a konkrét beállításokkal, beépített funkcióit használva:

- Válassza ki a sablonban a **beállítások**, **állapot**, vagy **elérési út** oszlopok rendezheti a listát. Jelölje be például a **elérési** oszlopban tekintheti meg az összes beállítás a `Microsoft Excel` elérési útja:

  ![Kattintson az elérési útját betűrendes rendezés](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- A sablon használatához a **keresési** mezővel találhatja meg a konkrét beállításokkal. Például keresse meg `copy`. Az összes beállítás `copy` jelennek meg:

  ![Kattintson az elérési útját betűrendes rendezés](./media/administrative-templates-windows/search-copy-settings.png)

  Egy másik példában keressen `microsoft word`. A Microsoft Word programban beállíthat beállításokról láthatja. Keresse meg `explorer` az Internet Explorer beállításainak megtekintéséhez is hozzáadhat a sablonhoz.

Ez a szolgáltatás [CSP-k a Windows házirend](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) (megnyílik egy másik Docs-webhely). A kriptográfiai szolgáltatók különböző kiadásai Windows, mint például a kezdőlap, Professional, Enterprise és így tovább működni. Tekintse meg, ha egy CSP-hez egy adott kiadásán működik, lépjen a [CSP-k a Windows házirend](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) (megnyílik egy másik Docs-webhely).

## <a name="next-steps"></a>További lépések

A sablon létrehozása, de azt nem csinál semmit még. Ezután [a sablon, más néven a profil hozzárendelése](device-profile-assign.md) és [állapotát nyomon](device-profile-monitor.md).
