---
title: "Üzletági iOS-alkalmazások hozzáadása az Intune-hoz | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Intune az Azure-on – előzetes: Útmutató az üzletági iOS-alkalmazások az Intune-hoz való hozzáadásához."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: d8615611eb715da66b1cf0972b885fbccb12fe6a

---

# <a name="how-to-add-ios-line-of-business-lob-apps-to-intune"></a>Üzletági (LOB) iOS-alkalmazások hozzáadása az Intune-hoz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>1. lépés – A szoftvertelepítő fájl megadása

1. Jelentkezzen be az Azure Portal webhelyre.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az Intune panelen válassza az **Alkalmazások kezelése** lehetőséget.
4. A **Mobilalkalmazások** tevékenységprofilon válassza a Felügyelet > **Alkalmazások** elemet.
5. Az alkalmazások listája fölött válassza a **Hozzáadás** lehetőséget.
6. Az **Alkalmazás hozzáadása** panelen válassza a **Szoftvertelepítő fájl** elemet.
7. A **Telepítőfájl kiválasztása** panelen kattintson a Tallózás gombra, és keresse meg az (.ipa kiterjesztésű) iOS-alkalmazástelepítő fájlt, majd kattintson az **OK** gombra.

## <a name="step-2---configure-app-information"></a>2. lépés – Az alkalmazás adatainak konfigurálása

1. Az **Alkalmazás szerkesztése** panelen konfigurálja az alábbi adatokat. Amikor elkészült, kattintson a **Hozzáadás** lehetőségre. A választott alkalmazástól függően előfordulhat, hogy egyes értékek automatikusan ki vannak töltve a panelen:
    - **Alkalmazásnév** – Itt adhatja meg az alkalmazásnak a céges portálon megjelenő nevét. Ügyeljen arra, hogy a megadott alkalmazásnevek egyediek legyenek. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a vállalati portálon.
    - **Alkalmazás leírása** – Itt adhatja meg az alkalmazás leírását. amelyet meg szeretne jeleníteni a felhasználók számára a vállalati portálon.
    - **Kiadó** – Adja meg az alkalmazás kiadójának nevét.
    - **Alkalmazható eszköztípus** – Válassza ki, hogy az alkalmazás iPad-re, iPhone-ra vagy kompatibilis iPod-ra legyen telepíthető.
    - **Minimális operációsrendszer-verzió** – A listából kiválaszthatja az operációs rendszer legrégebbi olyan verzióját, amelyre az alkalmazás telepíthető. Ha az alkalmazást régebbi operációs rendszerű eszközhöz rendeli hozzá, nem fog települni.
    - **Kategória (nem kötelező)** – Választhat egyet vagy többet a beépített alkalmazáskategóriák közül, vagy megadhat egyénileg létrehozott kategóriát is. Ezzel megkönnyítheti a felhasználók számára az alkalmazás megkeresését a vállalati portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Munkahelyi portálon** – Ezzel a beállítással kiemelten jelenítheti meg az alkalmazást a céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím** – Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Adatvédelmi nyilatkozat URL-címe** – Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím fog megjelenni a felhasználók számára a vállalati portálon.
    - **Fejlesztő** – Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos** – Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például **HR-osztály**).
    - **Megjegyzések** – Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon feltöltése** – Itt töltheti fel az alkalmazáshoz hozzárendelni kívánt ikont. Ez az alkalmazásikon jelenik meg a vállalati portálon böngésző felhasználók számára.
2. Ha elkészült, az **Alkalmazás hozzáadása** panelen válassza a **Mentés** lehetőséget.

A létrehozott alkalmazás megjelenik az alkalmazáslistában, ahol hozzárendelheti a kívánt csoportokhoz. További segítségért lásd: [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps) (Alkalmazások hozzárendelése csoportokhoz).


<!--HONumber=Feb17_HO1-->

