---
title: "Bevezetés a szabályzatok használatába"
titlesuffix: Azure portal
description: "Szabályzatok létrehozásával megakadályozhatja a felhasználókat abban, hogy olyan dolgokat hajtsanak végre az eszközeikkel, amelyekre nincs felhatalmazásuk."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ea5fe13f7361b968f3158a617275cd08daedac1c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2018
---
# <a name="get-started-with-policies"></a>Bevezetés a szabályzatok használatába

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
* E-mail-profil
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

## <a name="next-steps"></a>További lépések

[Bevezetés az eszközök regisztrációjába](get-started-enroll.md) – Megismerheti a regisztrációt egy iOS-eszköz teljes regisztrációs folyamatának végigkövetésével.

## <a name="learn-more"></a>További információ

* [Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)
* [A feltételes hozzáférési szabályok szokásos használati módjai az Intune-ban](conditional-access-intune-common-ways-use.md)
