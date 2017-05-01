---
title: "Hová kerültek az Intune-funkciók az Azure-ban?"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Az Intune-funkciók helye az Azure-konzolon."
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 6a1dbb2c9d3810f19536fc709719767de923b519
ms.openlocfilehash: e5067631fc17fa375a3b263f9910936300e6f8e9
ms.lasthandoff: 04/18/2017


---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Hová kerültek az Intune-funkciók az Azure-ban?
Az Intune Azure Portalra való költöztetésekor éltünk a lehetőséggel, és logikusabban rendeztünk el néhány feladatot. Minden ilyen előrelépés azzal jár, hogy meg kell tanulni az új elrendezést. Ezért készítettük ezt az útmutatót azoknak, akik jól ismerik a klasszikus Intune-konzolt, és szeretnék megtudni, hogyan végezhetik el a feladatokat az Azure-beli Intune-ban. Ha a cikk nem foglalkozik az Ön által keresett funkcióval, írja meg a lap alján hozzászólásban, hogy pótolhassuk.
## <a name="quick-reference-guide"></a>Rövid összefoglaló útmutató
|Funkció |Elérés a klasszikus konzolon|Elérés az Azure-beli Intune-ban| |------------||---------------|---------------|
|Készülékregisztrációs program (DEP) |Felügyelet > Mobileszköz-kezelés > iOS és Mac OS X > Készülékregisztrációs program|[Eszközregisztráció > Apple-regisztráció > DEP-token](#where-did-apple-dep-go) |
|Készülékregisztrációs program (DEP)| Felügyelet > Mobileszköz-kezelés > iOS és Mac OS X >Készülékregisztrációs program |[Eszközregisztráció > Apple-regisztráció > Regisztrációs programbeli sorozatszámok](#where-did-apple-dep-go) |
|Regisztráció szabályai |Felügyelet > Mobileszköz-kezelés > Regisztráció szabályai|[Eszközregisztráció > Regisztrációs korlátozások](#where-did-enrollment-rules-go) |
|Csoportok iOS sorozatszám szerint|Csoportok > Minden eszköz > Előre regisztrált céges eszközök > iOS-sorozatszám szerint|[Eszközregisztráció > Apple-regisztráció > Regisztrációs programbeli sorozatszámok](#where-did-corporate-pre-enrolled-devices-go) |
|Csoportok iOS-sorozatszám szerint |Csoportok > Minden eszköz > Előre regisztrált céges eszközök > iOS-sorozatszám szerint| [Eszközregisztráció > Apple-regisztráció > AC-sorozatszámok](#where-did-corporate-pre-enrolled-devices-go)|
|Csoportok IMEI-szám szerint (minden platform)| Csoportok > Minden eszköz > Előre regisztrált céges eszközök > IMEI-szám szerint (minden platform) | [Eszközregisztráció > Céges készülékazonosítók](#by-imei-all-platforms)|
| Céges eszközregisztrációs profil| Szabályzat > Céges eszközregisztráció | [Eszközregisztráció > Apple-regisztráció > Regisztrációs programbeli profilok](#where-did-corporate-pre-enrolled-devices-go) |
| Céges eszközregisztrációs profil | Szabályzat > Céges eszközregisztráció | [Eszközregisztráció > Apple-regisztráció > AC-profilok](#where-did-corporate-pre-enrolled-devices-go) |
| Android for Work | Felügyelet > Mobileszköz-kezelés > Android for Work | Eszközregisztráció > Android for Work-regisztráció | | Feltételek és kikötések | Szabályzat > Feltételek és kikötések | Eszközregisztráció > Feltételek és kikötések |


## <a name="where-do-i-manage-groups"></a>Hol lehet a csoportokat kezelni?
Az Azure-beli Intune az [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) segítségével kezeli a csoportokat.

## <a name="where-did-enrollment-rules-go"></a>Hová tűntek a regisztrációs szabályok?
A klasszikus konzolon be lehetett állítani a modern windowsos és macOS-es, valamint mobileszközök MDM-regisztrációjára vonatkozó szabályokat:

![Klasszikus mobileszköz-regisztrációs szabályok képe](./media/ui-changes/01-classic-rules.png)

Ezek a szabályok kivétel nélkül vonatkoztak az Intune-fiók összes felhasználójára. Az Azure Portalon ezek a szabályok két szabályzattípusba (eszköztípus szerinti és eszközök száma szerinti korlátozások) lettek szétválasztva:

![Azure-os mobileszköz-regisztrációs korlátozások képe](./media/ui-changes/02-azure-enroll-restrictions.png)

Az eszközök száma szerinti alapértelmezett korlátozás megfelel a klasszikus konzolon a Regisztrált eszközök maximális száma szabálynak:

![Azure-os eszközszám-korlátozások képe](./media/ui-changes/03-azure-device-limit.png)

Az eszköztípus szerinti alapértelmezett korlátozás megfelel a klasszikus konzolon a platformkorlátozási szabálynak:

![Azure-os eszköztípus-korlátozások képe](./media/ui-changes/04-azure-platform-restrictions.png)

A személyes tulajdonú eszközök letiltásának vagy engedélyezésének képességét az eszköztípus szerinti korlátozások platformkonfigurációjában lehet kezelni:

![Azure-os személyes eszközletiltási beállítások képe](./media/ui-changes/05-azure-personal-block.png)

A további korlátozási képességek csak az Azure Portalon lesznek elérhetők.

## <a name="where-did-apple-dep-go"></a>Hová tűnt az Apple DEP?
A klasszikus konzolon az Intune-t integrálni lehetett az Apple készülékregisztrációs programjával, és manuálisan szinkronizálást kérni az Apple szolgáltatásával:

![Klasszikus DEP-token képe](./media/ui-changes/06-classic-dep-token.png)

Az Azure Portalon ugyanazokkal a lépésekkel lehet beállítani az Apple DEP-et, mint a klasszikus Intune-ban:

![Azure-os DEP-token képe](./media/ui-changes/07-azure-dep-token.png)

A klasszikus konzol **Szinkronizálás** lehetősége azonban a sorozatszám-kezelési munkafolyamatba került, hiszen a manuális szinkronizálás eredménye is ott mutatkozik meg:

![Azure-os DEP-szinkronizálás képe](./media/ui-changes/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Hová tűntek az előre regisztrált vállalati eszközök?
### <a name="by-ios-serial-number"></a>iOS-sorozatszám szerint
A klasszikus konzolon az iOS-es eszközöket az Apple készülékregisztrációs programjával (DEP) és az Apple Configurator eszközzel lehet regisztrálni. Mindkét módszerrel lehetséges a sorozatszám-alapú előzetes regisztráció, és mindkettőhöz speciális Céges eszközregisztrációs profilokat kell kiosztani. A regisztráció előtt a regisztrációs profilok kiosztását a **Előre regisztrált vállalati eszközök iOS-sorozatszám szerint** eszközcsoporttal lehet kezelni:

![Klasszikus Apple-sorozatszámok képe](./media/ui-changes/09-classic-apple-serials.png)

Az Apple DEP-pel és a Configurator eszközzel végzett regisztrációk sorozatszámai közös listán jelennek meg. A téves profilkiosztások (DEP-profil AC-sorozatszámhoz vagy fordítva) számának csökkentése érdekében az Azure Portalon két listába osztottuk szét a sorozatszámokat:

**DEP-sorozatszámok**
![Azure-os DEP-sorozatszámok képe](./media/ui-changes/10-azure-dep-serials.png)

**Apple Configurator-sorozatszámok**
![Azure-os Apple Configurator-sorozatszámok képe](./media/ui-changes/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>IMEI-szám szerint (minden platform)

A klasszikus konzolon előzetesen meg lehet adni azoknak az eszközöknek a sorozatszámát, amelyeket az Intune-regisztráció alkalmával céges tulajdonúként kell megjelölni:

![Klasszikus IMEI-számlista képe](./media/ui-changes/12-classic-corp-imei.png)

Az Azure-konzolon ugyanezeket az IMEI-számokat a Céges készülékazonosítók listába kell feltölteni vesszőkkel tagolt (CSV) fájlként. Az új portálon nem lehet manuálisan bevinni az IMEI-számokat:

![Azure-os IMEI-számlista képe](./media/ui-changes/13-azure-corp-imei.png)

Az Azure-beli Intune fel van készítve az IMEI mellett másféle azonosítók kezelésére is, de jelenleg csak az IMEI-számokat lehet előzetesen bevinni.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Hová tűntek a céges eszközregisztrációs profilok?
Ha az Apple DEP program keretében vagy az Apple Configurator eszközzel iOS-es eszközöket szeretne regisztrálni, meg kell adnia az eszköznek kiosztandó céges eszközregisztrációs profilt. A klasszikus konzolon ezeknek a profiloknak a létrehozása és kezelése egyetlen listában történt:

![Klasszikus eszközregisztrációs profilok képe](./media/ui-changes/14-classic-corp-profiles.png)

Ebben a listában láthatók az Apple DEP programmal használható (**DEP On** – DEP engedélyezve) és a csak az Apple Configurator eszközzel használható (**DEP Off** – DEP letiltva) profilok.

A két profiltípus keveredésének és az ebből fakadó téves profilkiosztásoknak (DEP-profil AC-sorozatszámhoz vagy fordítva) az elkerülése érdekében elkülönítettük (az Apple készülékregisztrációs programját és az Apple School Managert is támogató) DEP-profilok, illetve az Apple Configurator-profilok létrehozását és kezelését:

**DEP-profilok**
![Azure-os DEP-profilok képe](./media/ui-changes/15-azure-dep-profiles.png)

**Apple Configurator-profilok**
![Azure-os Apple Configurator-profilok képe](./media/ui-changes/16-azure-ac-profiles.png)

