---
# required metadata

title: Eszközök kategorizálása eszközcsoport-leképezéssel a Microsoft Intune-ban | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Eszközök kategorizálása eszközcsoport-leképezéssel a Microsoft Intune-ban
A Microsoft Intune **eszközcsoport-leképezés** funkciója segítségével különböző Ön által meghatározott kategóriákba csoportosíthatja az eszközöket, megkönnyítve ezzel a felügyeletüket. 

Az eszközcsoport-leképezés funkció a következő munkafolyamatot használja:
1. Ön létrehozza a használni kívánt kategóriákhoz tartozó Intune-eszközcsoportokat.
2. Beállítja az eszközcsoport-leképezési szabályokat, amelyek segítségével a rendszer összepárosítja a kiválasztott kategóriákat a létrehozott eszközcsoportokkal.
3. Amikor a végfelhasználók regisztrálják eszközüket, csak az Ön által meghatározott kategóriák közül választhatnak. A kategória kiválasztását követően a rendszer automatikusan az Ön által létrehozott megfelelő eszközcsoporthoz adja a kérdéses eszközt.
4. Ezt követően az eszközcsoportok használatával leegyszerűsítheti a szabályzatok és az alkalmazások központi telepítését.

Kategóriák lehetnek például:
* Személyes eszközök
* Pénztári eszközök
* Bemutatóeszközök
* Értékesítés
* Könyvelés
* Manager

A kategóriákat tetszőlegesen választhatja meg.

## Az eszközcsoport-leképezések konfigurálása
1. Minden használni kívánt eszközcsoporthoz hozzon létre egy Intune-eszközcsoportot. A csoportok létrehozásával kapcsolatos további információért lásd: [Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)..
2. A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com) kattintson a **Felügyelet** elemre..
3. A **Felügyelet** munkaterületen bontsa ki a **Mobileszköz-kezelés** elemet, majd kattintson az **Eszközcsoport-leképezés** elemre..
4. Az **Eszközcsoport-leképezés** oldalon engedélyezze az eszközcsoport-leképezés funkciót.
5. Új leképezési szabály felvételéhez kattintson a **Hozzáadás** elemre.
6. Az **Eszközcsoport-leképezési szabály hozzáadása** párbeszédpanelen adja meg a létrehozni kívánt kategória nevét, majd a legördülő listából válassza ki azt az eszközgyűjteményt, amelyhez párosítani szeretné ezt a kategóriát. Ha elkészült, kattintson a **Hozzáadás** gombra.
7. Ha befejezte a kategóriák és a csoportok hozzáadását, kattintson a **Mentés** gombra..

Ezt követően amikor a felhasználók regisztrálják eszközüket, meg fog jelenni számukra az Ön által beállított kategóriák listája. A kategória kiválasztását és a regisztráció befejezését követően a rendszer a kiválasztott kategóriának megfelelő eszközcsoporthoz adja az eszközüket.

### További információ
[Csoportok használata felhasználók és eszközök kezelésére a Microsoft Intune-nal](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

<!--HONumber=May16_HO1-->


