---
title: "Apple DEP-tanúsítvány beszerzése az Intune-hoz | Intune az Azure-on – előzetes | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: c740dedebdc4afd909a8c38447f698c2724de5a1

---

# <a name="get-an-apple-dep-certificate"></a>Apple DEP-tanúsítvány beszerzése 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A vállalat által birtokolt iOS-eszközöket csak egy az Apple-től származó DEP-jogkivonat birtokában regisztrálhatja a DEP programba. Ez a jogkivonat lehetővé teszi, hogy az Intune szinkronizálja a DEP-ben résztvevő, vállalat által birtokolt eszközök adatait. A token ezen felül lehetővé teszi, hogy az Intune Regisztrációs profilokat töltsön fel az Apple-nek, és a feltöltött profilokhoz eszközöket rendeljen hozzá.

Ahhoz, hogy a vállalat által birtokolt eszközöket az Apple készülékregisztrációs programjával (DEP) lehessen kezelni, a szervezetnek csatlakoznia kell az Apple DEP-hez, és a programon keresztül kell beszereznie az eszközöket. A folyamat részletei a következő webhelyen érhetők el: https://deploy.apple.com. A program előnyei közé tartozik a beavatkozás nélküli beállítás, amelynek használata esetén az eszközöket nem kell csatlakoztatnia egy számítógép USB-portjához.

> [!NOTE]
> Csak akkor olvassa el ezt a megjegyzést, ha Ön olyan ügyfelünk, akit áttelepítettünk az Intune felügyeleti konzoljáról az Azure Portalra. Ha az áttelepítés során törölte az Apple DEP-tokent az Intune felügyeleti konzolból, akkor előfordulhat, hogy a DEP-token vissza lett állítva az Intune-fiókjába. Ilyen esetben egyszerűen törölje a DEP-tokent az Azure Portalról. 

**Az Apple DEP-tanúsítvány beszerzése**</br>
Válassza az Azure Portalon a **További szolgáltatások** elemet, írja be az **Intune** nevet a szövegmezőbe, majd válassza az **Egyéb** > **Intune** elemet. Válassza az Intune panelen az **Eszközök regisztrálása** > **Apple DEP-token** elemet, majd kövesse az Azure Portal számozott lépéseit (alább láthatók).

**1. lépés Töltsön le egy nyilvános kulcsú Intune-tanúsítványt (ez szükséges az Apple DEP-token létrehozásához).**<br>
Válassza a **Nyilvános kulcsú tanúsítvány letöltése** elemet, és mentse helyben a letöltött titkosításikulcs-fájlt (.pem). A .pem fájllal megbízhatósági kapcsolati tanúsítványt kérhet az Apple Device Enrollment Program portálról.

**2. lépés Töltsön le egy Apple DEP-tokent a megfelelő Apple-webhelyről.**<br>
Válassza a [DEP-token létrehozása az Apple-telepítőprogramokkal](https://deploy.apple.com) (https://deploy.apple.com) elemet, és jelentkezzen be vállalata Apple ID-jával. A későbbiekben ezt az Apple ID-t kell használnia a DEP-token megújításához.

   1.  A [Device Enrollment Program portálján](https://deploy.apple.com) válassza a **Device Enrollment Program** (Készülékregisztrációs program) &gt; **Manage Servers** (Kiszolgálók kezelése), majd az **Add MDM Server** (MDM-kiszolgáló felvétele) lehetőséget.

   2.  Az **MDM Server Name** (MDM-kiszolgáló neve) mezőben adja meg az MDM-kiszolgáló nevét, majd kattintson a **Next** (Tovább) gombra. A kiszolgálónév Önnek segít a mobileszköz-felügyeleti (MDM-) kiszolgáló azonosításában, nem ez a Microsoft Intune-kiszolgáló URL-címe vagy neve.

   3.  Megnyílik az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanel. Kattintson a **Choose File…** (Fájl kiválasztása…) elemre a .pem-fájl feltöltéséhez, majd válassza a **Next** (Tovább) lehetőséget.

   4.  Az **Add &lt;Kiszolgálónév&gt;** (<Kiszolgálónév> hozzáadása) párbeszédpanelen megjelenik a **Your Server Token** (Az Ön kiszolgálói jogkivonata) hivatkozás. Töltse le a kiszolgálói jogkivonatfájlt (.p7m) a számítógépre, majd válassza a **Done**(Kész) lehetőséget.

    A tanúsítványfájl (.p7m) segítségével megbízhatósági kapcsolatot hozhat létre az Intune és az Apple DEP-kiszolgálói között.

**3. lépés Adja meg az Apple DEP-token létrehozásához használt Apple ID-t. Ez az azonosító használható az Apple DEP-token megújításához.**

**4. lépés Tallózással keresse meg a feltölteni kívánt Apple DEP-tokent. Az Intune automatikusan szinkronizál a DEP-fiókjával.**<br>
Keresse meg a tanúsítványfájlt (.pem), majd kattintson a **Megnyitás** gombra, és válassza a **Feltöltés** elemet. A leküldéses tanúsítvány lehetővé teszi, hogy az Intune regisztrálja és felügyelje az iOS-eszközöket a szabályzatoknak a regisztrált mobileszközökre való leküldésével.



<!--HONumber=Feb17_HO1-->


