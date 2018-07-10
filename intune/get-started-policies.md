---
title: Kezdő lépések az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: A szabályzatokkal megvédheti a vállalati adatait, és kezelheti a végfelhasználók által a céges erőforrásokhoz való hozzáféréshez használt eszközöket. Valamint hozzárendelheti a szabályzatokat csoportokhoz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7fa1b596a1800971919cfc0ab3e94d2d16ec328
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271524"
---
# <a name="get-started-with-creating-policies"></a>Szabályzatok létrehozása – első lépések

Az Intune-szabályzatok nagyszerű módot kínálnak az eszközök regisztrálására és a vállalati szabályzatoknak való megfelelőségük biztosítására. A megfelelőségi szabályzatok a speciális eszköztípusok, például vállalati tulajdonú kioszkgépek és a személyes eszközök (saját eszközök használata), táblagépek és felhasználó nélküli eszközök kezelésében is segítenek.

![Megfelelőségi irányítópult kevés adattal](/intune/media/generic-compliance-dashboard.png)

A mobileszközök felügyelhetők megfelelőségi szabályzatokkal, beleértve a következőket:

* A felhasználó által az Intune-ban regisztrált eszközök számának szabályozása
* Eszközbeállítások, például eszközszintű titkosítás, jelszóhossz és kamerahasználat kezelése
* Alkalmazások, e-mail-profilok, VPN-profilok és egyebek távoli telepítése
* Eszközszintű feltételek kiértékelése a biztonsági megfelelőségi szabályzatokhoz

Megfelelőségi szabályzatok mindegyik platformhoz, például az iOS, az Android, a Windows és másokhoz is létrehozhatók. Ebben a gyakorlatban az iOS-t használjuk. IOS-eszközökhöz a következő szabályzatok érhetők el:

* PIN-kód vagy jelszó konfigurálása
* Eszköztitkosítás
* Feltört eszköz
* E-mail-profil
* Operációs rendszer minimális verziója
* Operációs rendszer maximális verziója

## <a name="create-a-policy"></a>Házirend létrehozása

1. Jelentkezzen be az [Azure portálra](https://portal.azure.com).
2. Kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
3. Válassza az **Eszközmegfelelőség** > **Szabályzatok** > **Szabályzat létrehozása** lehetőséget.
4. Adja meg a szabályzat **Név** és **Leírás** mezőiben az adatokat. 
5. A **Platform** beállításban válassza az **iOS** lehetőséget.
6. A **Beállítások** részben válassza a **Rendszerbiztonság** elemet, majd adja meg a **Jelszó szükséges a mobileszközök feloldásához** lehetőséghez a **Kötelező** beállítást. 

    Más szabályokat is beállíthat, például: 
    - **Jelszó minimális hossza**
    - **Kötelező jelszótípus**
    - **A jelszó nem alfanumerikus karaktereinek száma**
    
    Amikor befejezte a szabályzat beállítását, válassza az **OK** gombot.
  
7. Térjen vissza a **Szabályzat létrehozása** lehetőséghez, majd válassza a **Létrehozás** lehetőséget. Ezzel a lépéssel létrehozza a szabályzatot, és felveszi azt az **Eszközmegfelelőség** > **Szabályzatok** listára.
8. Válassza ki az új szabályzatot, majd válassza a **Hozzárendelések** lehetőséget. Belefoglalhat vagy kizárhat Azure Active Directory (AD) biztonsági csoportokat.
Meglévő Azure AD-biztonsági csoportjait a Kijelölt csoportok lehetőséget választva tekintheti meg. Kiválaszthatja, hogy mely csoportokra vonatkozzon a szabályzat, majd a **Mentés** elemre kattintva alkalmazhatja azt.

Az új vállalati szabályzatnak való megfelelés érdekében a regisztrált eszköz néhány perc múlva frissített jelszót kér. A frissítést manuálisan ellenőrizheti az **iOS-es céges portál alkalmazásban**. Nyissa meg a Céges portál alkalmazást, jelölje ki az eszköz nevét, majd válassza a **Szinkronizálás** lehetőséget.

> [!NOTE]
> A dinamikus eszközcsoportra alkalmazott új szabályzatoknak a csoportba tartozó összes eszközre történő alkalmazása akár nyolc órát is igénybe vehet.

## <a name="next-steps"></a>További lépések

[Bevezetés az eszközök regisztrációjába](get-started-enroll.md) – Megismerheti a regisztrációt egy iOS-eszköz teljes regisztrációs folyamatának végigkövetésével.

## <a name="learn-more"></a>További információ

* [Intune-eszközmegfelelőségi szabályzatok figyelése](compliance-policy-monitor.md)
* [A feltételes hozzáférési szabályok szokásos használati módjai az Intune-ban](conditional-access-intune-common-ways-use.md)
