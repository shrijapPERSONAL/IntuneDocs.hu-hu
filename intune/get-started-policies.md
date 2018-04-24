---
title: Bevezetés a Microsoft Intune szabályzatainak használatába
titlesuffix: ''
description: A szabályzatokkal megvédheti a vállalati adatait, és kezelheti a végfelhasználók által a céges erőforrásokhoz való hozzáféréshez használt eszközöket.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 661ef25085892e299e45156f27b3d9db959577d4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-with-creating-policies"></a>Szabályzatok létrehozása – első lépések

Az Intune használatának megkezdésekor az egyik legfőbb cél az eszközök regisztrálása, hogy biztosan megfeleljenek a vállalati szabályzatoknak. A megfelelőségi szabályzatok nem csak a speciális eszköztípusok, például vállalati tulajdonú kioszkgépek, hanem a személyes eszközök (saját eszközök használata), táblagépek és felhasználó nélküli eszközök kezelésében is segítenek.

![Megfelelőségi irányítópult kevés adattal](/intune/media/generic-compliance-dashboard.png)

Mobileszközök kezelése az alábbi területeken megfelelőségi szabályzatokkal:

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

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Válassza az **Eszközmegfelelőség** elemet.
4. Az **Eszközmegfelelőség** panelen válassza a **Szabályzatok** lehetőséget.
5. Válassza a **Szabályzat létrehozása** elemet, majd töltse ki a részleteket, például a **Név** és a **Leírás** mezőt. 
6. A **Platform** beállításaként válassza az **iOS** lehetőséget.
6. A **Beállítások** részben válassza a **Rendszerbiztonság** elemet, majd váltsa át a **Jelszó szükséges a mobileszközök feloldásához** beállítását a **Kötelező** lehetőségre. Más szabályokat is beállíthat, többek között a **Jelszó minimális hossza**, a **Jelszó kötelező típusa**  és a **Nem alfanumerikus karakterek száma a jelszóban** szabályt. Amikor befejezte a szabályzat beállítását, válassza az **OK** gombot.
7. Térjen vissza a **Szabályzat létrehozása** panelre, majd válassza a **Létrehozás** lehetőséget.
8. A szabályzat létrehozása után válassza a **Hozzárendelések** lehetőséget a tesztcsoporthoz való hozzárendeléséhez. Válassza ki a tesztcsoportot – amelynek tartalmaznia kell a tesztfelhasználót –, majd rendelje hozzá a szabályzatot ehhez a csoporthoz a **Mentés** gombra kattintva.
9. Várjon néhány percig, és a regisztrált eszköznek kérnie kell egy frissített jelszót, hogy továbbra is megfeleljen a vállalati házirendnek. Ezt manuálisan is ellenőrizheti az **iOS-hez készült céges portál alkalmazásban**, ha rákoppint az eszköz nevére, majd a **Szinkronizálás** gombra.

## <a name="next-steps"></a>További lépések

[Bevezetés az eszközök regisztrációjába](get-started-enroll.md) – Megismerheti a regisztrációt egy iOS-eszköz teljes regisztrációs folyamatának végigkövetésével.

## <a name="learn-more"></a>További információ

* [Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)
* [A feltételes hozzáférési szabályok szokásos használati módjai az Intune-ban](conditional-access-intune-common-ways-use.md)
