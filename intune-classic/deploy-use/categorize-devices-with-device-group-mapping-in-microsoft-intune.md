---
title: "Eszközök kategorizálása eszközcsoport-leképezéssel | Microsoft Docs"
description: "A Microsoft Intune eszközcsoport-leképezés funkciója segítségével különböző Ön által meghatározott kategóriákba csoportosíthatja az eszközöket, megkönnyítve ezzel a felügyeletüket."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 618827ed6baf7a9dec6aef804f19bcbca08ed39f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017

---

# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a>Eszközök kategorizálása eszközcsoport-leképezéssel a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune **eszközcsoport-leképezés** funkciója segítségével a különböző, Ön által meghatározott kategóriákon alapuló csoportokhoz adhatja hozzá az eszközöket, megkönnyítve ezzel a felügyeletüket. 

Az eszközcsoport-leképezés funkció a következő munkafolyamatot használja:
1. Hozzon létre kategóriákat, amelyek közül a felhasználók választani fognak az eszközük regisztrálásakor
2. Ön a használni kívánt kategóriákhoz tartozó csoportokat hozza létre (vagy a meglévő csoportokat használja). Az Ön által használt Intune-verziótól függően ezek Intune- vagy Azure Active Directory biztonsági csoportok lesznek.
2. Beállíthatja a szabályokat, amelyek segítségével a rendszer összepárosítja a kiválasztott kategóriákat a létrehozott eszközcsoportokkal.
3. Amikor a végfelhasználók regisztrálják eszközüket, csak az Ön által meghatározott kategórialistából választhatnak. A kategória kiválasztását követően a rendszer automatikusan az Ön által létrehozott megfelelő csoporthoz adja a kérdéses eszközt. Ha az eszköz már regisztrálva van, a Vállalati portál alkalmazás következő használatakor a végfelhasználónak választani kell egy kategóriát.
4. Ezután szabályzatokat és alkalmazásokat telepíthet ezekre a csoportokra.

Bármilyen tetszés szerinti eszközkategóriát létrehozhat, például:
* Pénztári eszközök
* Bemutatóeszközök
* Értékesítés
* Könyvelés
* Manager

## <a name="important-information-about-a-change-in-group-management-for-intune"></a>Fontos információk az Intune csoportfelügyeletét érintő változással kapcsolatban

A visszajelzéseik alapján folyamatosan dolgozunk azon, hogy az Enterprise Mobility + Security egységes csoportosítást és célcsoport-kezelést kínáljon. Ezért hamarosan Azure Active Directory-alapú biztonsági csoportokká alakítjuk át az Intune-csoportokat. A módosítás után többé nem fog tudni létrehozni csoportokat az Intune használatával, helyette az Azure-portálon alakítja ki majd azokat. Erre a módosításra fokozatosan fog sor kerülni, és erről, valamint az ütemezésről [ebben a témakörben](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) olvashat bővebben.

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a>Melyik eljárást kell használni ebből a témakörből az eszközcsoport-leképezés konfiguráláshoz?

Az Azure Active Directory-alapú biztonsági csoportok fokozatos megvalósítása miatt az [Intune felügyeleti konzolján](https://manage.microsoft.com) meg kell nyitni a **Csoportok** munkaterületet a használni kívánt eljárás azonosításához:

-  Ha az Azure-portálra mutató hivatkozás jelenik meg, már nem Intune-csoportokat használ. Kövesse az alábbi [Eszközcsoport-leképezés konfigurálása Azure Active Directory-csoportokra](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) című eljárást.
-  Ha nem lát Azure-portálra mutató hivatkozást, akkor még mindig Intune-csoportokat használ. Kövesse az alábbi [Eszközcsoport-leképezés konfigurálása Intune-csoportokra](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) című eljárást.

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a>Eszközcsoport-leképezés konfigurálása Intune-csoportokra
1. Minden használni kívánt eszközkategóriához hozzon létre egy Intune-eszközcsoportot vagy azonosítson egy meglévő csoportot. A csoportok létrehozásával kapcsolatban további információt a [Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) című témakörben találhat.
2. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza a **Felügyelet** elemet.
3. A **Felügyelet** munkaterületen bontsa ki a **Mobileszköz-kezelés** csomópontot, majd válassza az **Eszközcsoport-leképezés** elemet.
4. Az **Eszközcsoport-leképezés** oldalon engedélyezze az eszközcsoport-leképezés funkciót.
5. Új leképezési szabály felvételéhez válassza a **Hozzáadás** elemet.
6. Az **Eszközcsoport-leképezési szabály hozzáadása** párbeszédpanelen adja meg a létrehozni kívánt kategória nevét, majd a legördülő listából válassza ki azt az eszközgyűjteményt, amelyhez párosítani szeretné ezt a kategóriát. Ha elkészült, válassza a **Hozzáadás** gombot.
7. Ha befejezte a kategóriák és a csoportok hozzáadását, válassza a **Mentés** gombot.



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a>Eszközcsoport-leképezés konfigurálása Azure Active Directory-csoportokra

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a>1. lépés - Eszközkategóriák létrehozása az Intune felügyeleti konzolján
1. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza a **Felügyelet** elemet.
3. A **Felügyelet** munkaterületen bontsa ki a **Mobileszköz-kezelés** csomópontot, majd válassza az **Eszközkategóriák** elemet.
4. Az **Eszközkategóriák** lapon látni fog egy listát, ahol elvégezheti az eszközkategóriák konfigurálását: 
- Adjon meg egy nevet, amelyet a **Hozzáadás** elemre kattintva új eszközkategóriaként vehet fel.
- Emellett lehetőség van kategóriák kiválasztására és **Törlésére**.

Azure Active Directory biztonsági csoportok létrehozásakor az eszközkategória nevét fogja használni a 2. lépésben.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2. lépés - Azure Active Directory biztonsági csoportok létrehozása

Ebben a lépésben az eszközkategória és az eszközkategória-név alapján dinamikus csoportokat fog létrehozni az Azure-portálon.

A folytatáshoz tekintse meg a [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) (Speciális szabályok létrehozása attribútumok használatával) című témakört az Azure Active Directory dokumentációjában.
Az ebben a témakörben ismertetett információk alapján hozzon létre speciális szabállyal egy eszközcsoportot a **deviceCategory** attribútum segítségével.
Például (**device.deviceCategory -eq** "<*az Intune felügyeleti konzolján lekért eszközkategória-név*>")


## <a name="after-you-configure-device-groups"></a>Az eszközcsoportok konfigurálása után

Amikor a felhasználók regisztrálják eszközüket, meg fog jelenni számukra az Ön által beállított kategóriák listája. A kategória kiválasztását és a regisztráció befejezését követően a rendszer a kiválasztott kategóriának megfelelő Intune eszközcsoporthoz vagy Active Directory biztonsági csoporthoz adja az eszközüket.

### <a name="see-also"></a>További információ
[Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

