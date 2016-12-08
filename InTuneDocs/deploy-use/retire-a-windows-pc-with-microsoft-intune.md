---
title: "Windows rendszerű számítógépek kivonása | Microsoft Intune"
description: "Az Intune által felügyelt Windows rendszerű számítógépek kivonása."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 19e8e2b6a7eaa3cf02e4296a6fd147baa1472b61


---

# <a name="retire-a-windows-pc"></a>Windows rendszerű számítógépek kivonása
A következő lépésekkel vonhatja ki az Intune által felügyelt számítógépeket.

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) válassza a **Csoportok** &gt; **Minden eszköz** elemet (vagy egy másik csoportot, amely tartalmazza azt a számítógépet, amelyet ki szeretne vonni).

2.  Jelölje ki a kivonni kívánt eszközöket, majd válassza a **Kivonás/Összes adat törlése** elemet.

Ha a számítógépet újból regisztrálni szeretné az Intune-ban, telepítse újra az szoftverügyfelet a számítógépen [A Windows rendszerű számítógépügyfél telepítése a Microsoft Intune-nal](install-the-windows-pc-client-with-microsoft-intune.md) című témakörben található információk segítségével.

Ha a számítógép nem tud csatlakozni az Intune-hoz, egy üzenet jelenik meg az **Irányítópult** munkaterületen.

A számítógép eltávolításakor:

-   A rendszer eltávolítja az Intune-felügyeletből és -leltárból, és a számítógéphez társított licenc ismét felhasználhatóvá válik. A Kivonás/Összes adat törlése elemre kattintva a rendszer eltávolítja az Intune ügyfélszoftvert, de az alkalmazások és az adatok megmaradnak a számítógépen. A kivonás nem hajt végre teljes törlést a számítógépen.

-   Az állapota már nem jelenik meg az Intune-konzolon.

-   Az Intune eltávolítja az szoftverügyfelet a számítógépről. Ha a számítógép nincs csatlakoztatva az Intune szolgáltatáshoz, a rendszer a számítógép következő csatlakozásakor távolítja el a szoftverügyfelet.

-   Megtörténik a Microsoft Intune Endpoint Protection eltávolítása a számítógépről. Ha a számítógépre telepítve van egy másik végponti alkalmazás, és le van tiltva, akkor az alkalmazás a Microsoft Intune Endpoint Protection eltávolítása után újból engedélyezhető a számítógépek védelmének biztosításához.

-   A rendszer eltávolít minden házirendet a számítógépről, és módosulnak a házirendek által beállított értékek.

-   A számítógép többé nem kap szoftver- vagy a kártevődefiníció-frissítéseket az Intune szolgáltatástól.

-   Konfigurációjuktól függően az eltávolított számítógépek a Windows Server Update Services, a Windows Update vagy a Microsoft Update használatával továbbra is kaphatnak frissítéseket.

    > [!IMPORTANT]
    > Ha az ügyfélszoftver egy csoportházirend-objektummal (GPO) lett telepítve, akkor az ügyfélszoftver eltávolítása előtt el kell távolítania a csoportházirend-objektumot (GPO), hogy megakadályozza a szoftver újratelepítését.

    Ha az ügyfél eltávolítása nem sikerült, további segítséget itt találhat: [Az Endpoint Protection hibáinak elhárítása](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune).

### <a name="see-also"></a>További információ

[A Windows rendszerű számítógépek Intune-szoftverügyféllel való felügyeletének általános feladatai](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


