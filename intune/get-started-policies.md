---
title: "Bevezetés a szabályzatok használatába"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 232ec25c34df5e71f70737ca5f0f8a2ef12a05f0
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2017
---
# <a name="getting-started-with-policies"></a>Bevezetés a szabályzatok használatába

Az Intune használatának megkezdésekor az egyik legfőbb cél az eszközök regisztrálása, hogy biztosan megfeleljenek a vállalati szabályzatoknak. A megfelelőségi szabályzatok nem csak a speciális eszköztípusok, például vállalati tulajdonú kioszkgépek, hanem a személyes eszközök (saját eszközök használata), táblagépek és felhasználó nélküli eszközök kezelésében is segítenek.

![Megfelelőségi irányítópult nagyon kevés adattal](/intune/media/generic-compliance-dashboard.png)

A megfelelőségi szabályzatok a következő felügyeleti képességeket biztosítják mobileszközökhöz:

* Az egyes felhasználók által regisztrálható eszközök számának korlátozása
* Eszközbeállítások (például eszközszintű titkosítás, jelszóhossz, kamerahasználat) kezelése
* alkalmazások, e-mail-profilok, VPN-profilok stb. távoli telepítése;
* Eszközszintű feltételek kiértékelése a biztonsági megfelelőségi szabályzatokhoz

Minden egyes platformhoz Ön hoz létre megfelelőségi szabályzatokat. Ezt a gyakorlatot iOS-en mutatjuk be. IOS-eszközökhöz a következő szabályzatok érhetők el:

* PIN-kód vagy jelszó konfigurálása
* Eszköztitkosítás
* Feltört eszköz
* E-mail profil
* Operációs rendszer minimális verziója
* Operációs rendszer maximális verziója

__Hogyan hozhatok létre szabályzatot?__

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Az **Erőforrások keresése** területen keresse meg az **Intune-t**.
3. Válassza az **Eszközmegfelelőség** elemet.
4. Az **Eszközmegfelelőség** panelen válassza a **Szabályzatok** lehetőséget.
5. Válassza a **Szabályzat létrehozása** elemet, majd töltse ki a részleteket, például a **Név** és a **Leírás** mezőt. A **Platform** beállításaként válassza az **iOS** lehetőséget.
6. A **Beállítások** részben válassza a **Rendszerbiztonság** elemet, majd váltsa át a **Jelszó szükséges a mobileszközök feloldásához** beállítását a **Kötelező** lehetőségre. Más szabályokat is beállíthat, többek között a **Jelszó minimális hossza**, a **Jelszó kötelező típusa**  és a **Nem alfanumerikus karakterek száma a jelszóban** szabályt. Amikor befejezte a szabályzat beállítását, válassza az **OK** gombot.
7. Térjen vissza a **Szabályzat létrehozása** panelre, majd válassza a **Létrehozás** lehetőséget.
8. A szabályzat létrehozása után válassza a **Hozzárendelések** lehetőséget a tesztcsoporthoz való hozzárendeléséhez. Válassza ki a tesztcsoportot – amelynek tartalmaznia kell a tesztfelhasználót –, majd rendelje hozzá a szabályzatot ehhez a csoporthoz a **Mentés** gombra kattintva.
9. Várjon néhány percig, és a regisztrált eszköznek kérnie kell egy frissített jelszót, hogy továbbra is megfeleljen a vállalati házirendnek. Ezt manuálisan is ellenőrizheti az **iOS-hez készült céges portál alkalmazásban**, ha rákoppint az eszköz nevére, majd a **Szinkronizálás** gombra.