---
title: "Felhasználók és eszközök összekapcsolásának felügyelete Windows rendszerű számítógépekhez | Microsoft Intune"
description: "Hogyan kapcsoljon össze egy felhasználót egy Intune felügyelte Windows rendszerű számítógéppel."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 39fec6a2ea8d8c0f4b6ea1460c76a8a6c652d614


---

# <a name="manage-user-device-linking-for-windows-pcs"></a>Felhasználók és eszközök összekapcsolásának felügyelete Windows rendszerű számítógépekhez
Mielőtt szoftvereket telepítene egy felhasználónak, a felhasználót egy számítógéphez kell kapcsolni. Egy felhasználót több számítógéphez is kapcsolhat, de minden gép csak egyetlen felhasználóhoz kapcsolható. A felhasználókat a rendszer automatikusan összekapcsolja azokkal a számítógépekkel, amelyeket a vállalati portálon keresztül regisztráltak az Intune-ban.

Felhasználók kapcsolása számítógépekhez:

1.  A [Microsoft Intune felügyeleti konzolon](https://manage.microsoft.com/) válassza a **Csoportok** &gt; **Minden eszköz** elemet (vagy egy másik csoportot, amely tartalmazza azt a számítógépet, amelyet egy felhasználóhoz szeretne kapcsolni).

2.  Jelölje ki a felhasználóval összekapcsolni kívánt számítógépet, majd válassza a **Felhasználó összekapcsolása** elemet.

    A **Felhasználó összekapcsolása** párbeszédpanel megjeleníti az elérhető felhasználók listáját a megjelenített nevükkel, a felhasználói azonosítójukkal és azon számítógépek számával, amelyekhez az egyes felhasználók jelenleg kapcsolva vannak. Ha a kijelölt számítógéphez már van felhasználó kapcsolva, akkor annak a felhasználónak a neve és felhasználói azonosítója megjelenik az **Aktuális felhasználó**területen. Ha a számítógép nincs felhasználóhoz kapcsolva, akkor az **Aktuális felhasználó** területen a **Nincs felhasználó**felirat jelenik meg.

3.  Tegye a következők valamelyikét:

    -   Ha azt szeretné, hogy a számítógép továbbra is az aktuális felhasználóhoz legyen kapcsolva (ha van ilyen), válassza a **Mégse** lehetőséget.

    -   Ha el szeretné távolítani az aktuális felhasználóval való kapcsolatot (ha van ilyen), válassza a **Kapcsolat eltávolítása**&gt; **OK** lehetőséget.

    -   Ha a számítógépet egy új felhasználóhoz szeretné kapcsolni, válasszon ki egy felhasználót a **Minden felhasználó** listában. Erősítse meg, hogy a felhasználói adatok helyesek, majd kattintson az **OK** gombra.

> [!TIP]
> Ha korlátozni szeretné végfelhasználókat abban, hogy önmagukat számítógépekkel kössék össze, engedélyezze **A felhasználók korlátozása abban, hogy önmagukat számítógépekhez csatolhassák** beállítást A **Microsoft Intune-ügynök beállításai** házirendben.

### <a name="see-also"></a>További információ

[A Windows rendszerű számítógépek Intune-szoftverügyféllel való felügyeletének általános feladatai](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


