---
title: "iOS-alkalmazáskiépítési profilok a Microsoft Intune-ban"
titlesuffix: 
description: "Az Intune biztosítja az eszközöket, amelyek segítségével proaktív módon rendelhet hozzá új kiépítési profilt azokhoz az eszközökhöz, amelyeken hamarosan lejárnak az alkalmazások.”"
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7637dcb3aba4f46a3e97c8de47d974b46af27b47
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2018
---
# <a name="use-ios-mobile-provisioning-profiles-in-intune-to-prevent-your-apps-from-expiring"></a>Az Intune iOS-mobileszközös kiépítési profiljainak segítségével megakadályozhatja, hogy az alkalmazásai lejárjanak

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Bevezetés

Az iPhone-okhoz és iPadekhez rendelt Apple iOS üzletági alkalmazások beépített kiépítési profillal és a tanúsítvánnyal aláírt kóddal rendelkeznek. Az alkalmazás futtatásakor az iOS ellenőrzi az iOS-alkalmazás integritását, és érvényesíti a kiépítési profil által meghatározott szabályzatokat. A következő érvényesítések zajlanak le:

- **Telepítési fájl integritása** – Az iOS összehasonlítja az alkalmazás részleteit a vállalat aláírási tanúsítványának nyilvános kulcsával. Ha ezek eltérnek, akkor előfordulhat, hogy az alkalmazás tartalma módosult. Ebben az esetben a rendszer nem engedélyezi az alkalmazás futását.
- **Képességek érvényesítése** – Az iOS megkísérli kikényszeríteni az alkalmazásképességeket az alkalmazás telepítési (.ipa) fájljában tárolt vállalati kiépítési profilból (és nem az egyéni fejlesztői kiépítési profilokból).


Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában három évig érvényes. A kiépítési profil viszont egy év után lejár. Amíg a tanúsítvány még érvényes, az Intune biztosítja az eszközöket egy új kiépítési profil proaktív hozzárendelésére olyan eszközökhöz, amelyeken már majdnem lejáró alkalmazások vannak.
A tanúsítvány lejárata után újra regisztrálnia kell az alkalmazást egy új tanúsítvánnyal, és be kell ágyaznia egy új kiépítési profilt az új tanúsítvány kulcsával.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>iOS-beli mobilalkalmazás-kiépítési profilok létrehozása

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza az **Mobilalkalmazások** lehetőséget.
1.  A **Mobilalkalmazások** munkafolyamatban válassza a **Felügyelet** > **iOS-alkalmazáskiépítési profilok** elemet.
2.  A profilok listáját mutató panelen válassza a **Profil létrehozása** lehetőséget.
3. A **Profil létrehozása** panelen konfigurálja a következő értékeket:
    - **Név** – Adjon egy nevet a mobil kiépítési profilnak.
    - **Leírás** – Lehetősége van a házirend ismertetésének megadására.
    - **Profilfájl feltöltése** – Válassza az **Importálás** lehetőséget, majd egy Apple Mobile konfigurációs profilfájlt (**.mobileprovision** kiterjesztéssel), amelyet az Apple Developer webhelyről töltött le.
4. Ha elkészült, válassza a **Létrehozás** elemet.

## <a name="next-steps"></a>További lépések

A profilt rendelje hozzá a szükséges iOS-eszközökhöz. További információt az [Eszközprofilok hozzárendelése](device-profile-assign.md) című útmutató lépéseit használva talál.
