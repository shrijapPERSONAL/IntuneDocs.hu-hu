---
title: "Alkalmazáslétesítési profilok| Microsoft Intune"
description: "Az Intune biztosítja az eszközöket, amelyek segítségével proaktív módon telepíthet új létesítési profilt azokra az eszközökre, amelyeken hamarosan lejárnak az alkalmazások."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 409433dbe5ca777b33b21a2655e15cde8003b4a2
ms.openlocfilehash: d67b26b23e65d4a144c1efda1494de1df94cc33c


---

# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Az iOS-mobileszközös létesítésiprofil-szabályzatok segítségével megakadályozhatja, hogy az alkalmazásai lejárjanak


Az iPhone-okra és iPadekre telepített Apple iOS üzletági alkalmazások beépített létesítési profillal és a tanúsítvánnyal aláírt kóddal rendelkeznek. Az alkalmazás futtatásakor az iOS ellenőrzi az iOS-alkalmazás integritását, és érvényesíti a létesítési profil által meghatározott szabályzatokat. A következő érvényesítések zajlanak le:

- **Telepítési fájl integritása** – Az iOS összehasonlítja az alkalmazás részleteit a vállalat aláírási tanúsítványának nyilvános kulcsával. Ha ezek eltérnek, akkor előfordulhat, hogy az alkalmazás tartalma módosult. Ebben az esetben a rendszer nem engedélyezi az alkalmazás futását.
- **Képességek érvényesítése** – Az iOS megkísérli kikényszeríteni az alkalmazásképességeket az alkalmazás telepítési (.ipa) fájljában tárolt vállalati létesítési profilból (és nem az egyéni fejlesztői létesítési profilokból).


Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában három évig érvényes. A létesítési profil viszont egy év után lejár. Amíg a tanúsítvány még érvényes, az Intune biztosítja az eszközöket egy új létesítési profil proaktív telepítéséhez olyan eszközökre, amelyeken már majdnem lejáró alkalmazások vannak.
A tanúsítvány lejárata után újra regisztrálnia kell az alkalmazást egy új tanúsítvánnyal, és be kell ágyaznia egy új létesítési profilt az új tanúsítvány kulcsával.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>Az üzletági alkalmazás lejáratának megállapítása

1. A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza az **Alkalmazások**  >  **Alkalmazások** elemet.
2. Az alkalmazás lejárati dátumának megtekintéséhez nézze meg az alkalmazások listáján a **Lejárat dátuma** oszlopot. A **Szűrők** legördülő listán is beállíthatja a **Lejárt/Hamarosan lejár** szűrőt, így csak azokat az alkalmazásokat fogja látni, amelyek esetében intézkedésre van szükség.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>iOS-mobileszközös létesítésiprofil-házirendek létrehozása


1. A [Microsoft Intune felügyeleti konzolban](https://manage.microsoft.com) válassza a **Házirend** > **Áttekintés** > **Házirend hozzáadása** lehetőséget.
2. Az **Új házirend létrehozása** párbeszédpanelen válassza az **iOS** > **Mobileszközös kiépítési profil szabályzata** elemet, majd válassza a **Házirend létrehozása** lehetőséget.
3. Az **Általános** lapon adja meg a következő beállításokat:
    - **Név** – Adjon egy nevet a mobil létesítési profilnak.
    - **Leírás** – Lehetősége van a házirend ismertetésének megadására.
    - **Konfigurációs profilfájl** – Kattintson az **Importálás** lehetőségre, majd válasszon egy Apple Mobile konfigurációs profilfájlt (**.mobileprovision** kiterjesztéssel), amelyet az Apple Developer webhelyről töltött le.
4. Ha elkészült, válassza a **Házirend mentése** elemet.
5. Majd telepítse a házirendet a szükséges iOS-eszközökre. További információk: [Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).



<!--HONumber=Dec16_HO2-->


