---
title: "Apple DEP-tanúsítvány beszerzése az Intune-hoz"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: A cikk útmutatással szolgál az Apple-eszközöknek az Intune-ban történő kezeléséhez szükséges leküldéses MDM-tanúsítvány konfigurálásához és feltöltéséhez. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8edc42bb86e3856ac6568cc3c1acc5d757978e79
ms.lasthandoff: 02/18/2017

---

# <a name="get-an-apple-dep-certificate"></a>Apple DEP-tanúsítvány beszerzése

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A vállalat által birtokolt iOS-eszközöket csak egy, az Apple-től származó DEP-jogkivonat birtokában regisztrálhatja az Apple készülékregisztrációs programjában. Ez a jogkivonat lehetővé teszi, hogy az Intune szinkronizálja a DEP-ben résztvevő, vállalat által birtokolt eszközök adatait. A jogkivonat ezen felül lehetővé teszi, hogy az Intune regisztrációs profilokat töltsön fel az Apple számára, és a feltöltött profilokhoz eszközöket rendeljen hozzá.

Ahhoz, hogy a vállalat által birtokolt iOS-eszközöket a DEP segítségével lehessen kezelni, a szervezetnek csatlakoznia kell az Apple DEP-hez, és a programon keresztül kell beszereznie az eszközöket. A folyamat részletei a következő webhelyen érhetők el: https://deploy.apple.com. A program előnyei közé tartozik a beavatkozás nélküli beállítás, amelynek használata esetén az eszközöket nem kell csatlakoztatnia egy számítógép USB-portjához.

> [!NOTE]
> Ez a megjegyzés csak olyan Intune-ügyfelekre vonatkozik, akik migrálást végeztek az Intune felügyeleti konzoljáról az Azure Portalra. Ha az áttelepítés során törölte az Apple DEP-tokent az Intune felügyeleti konzolból, akkor előfordulhat, hogy a DEP-token vissza lett állítva az Intune-fiókjába. Ilyen esetben egyszerűen törölje a DEP-tokent az Azure Portalról.

## <a name="steps-to-get-the-apple-dep-certificate"></a>Az Apple DEP-tanúsítvány beszerzésének lépései
Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget. Válassza az Intune panelen az **Eszközök regisztrálása** > **Apple DEP-token** elemet, majd kövesse az Azure Portal számozott lépéseit (alább láthatók).

**1. lépés Töltsön le egy nyilvános kulcsú Intune-tanúsítványt (ez szükséges az Apple DEP-token létrehozásához).**<br>
Válassza a **Nyilvános kulcsú tanúsítvány letöltése** elemet, és mentse helyben a letöltött titkosításikulcs-fájlt (.pem). A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.

**2. lépés Töltsön le egy Apple DEP-tokent a megfelelő Apple-webhelyről.**<br>
Válassza a [DEP-token létrehozása az Apple-telepítőprogramokkal](https://deploy.apple.com) (https://deploy.apple.com) elemet, és jelentkezzen be vállalata Apple ID-jával. A későbbiekben ezt az Apple ID-t kell használnia a DEP-token megújításához.

   a.  A [Device Enrollment Program portálján](https://deploy.apple.com) válassza a **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Servers** (Kiszolgálók kezelése), majd az **Add MDM Server** (MDM-kiszolgáló felvétele) lehetőséget.

   b.  Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.

   c.  Megnyílik az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanel. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.

   d.  Az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanelen megjelenik a **Your Server Token** (Az Ön kiszolgálói jogkivonata) hivatkozás. Töltse le a kiszolgálói jogkivonatfájlt (.p7m) a számítógépre, majd válassza a **Done**(Kész) lehetőséget.

    This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.

**3. lépés Adja meg az Apple DEP-token létrehozásához használt Apple ID-t. Ez az azonosító használható az Apple DEP-token megújításához.**

**4. lépés Tallózással keresse meg a feltölteni kívánt Apple DEP-tokent. Az Intune automatikusan szinkronizál a DEP-fiókjával.**<br>
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével.

