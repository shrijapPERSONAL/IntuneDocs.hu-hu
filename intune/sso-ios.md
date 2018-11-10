---
title: Egyszeri bejelentkezési lehetőség hozzáadása iOS-eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: A Microsoft Intune-ban létrehozhatja, konfigurálhatja vagy engedélyezheti az iOS-eszközök számára az egyszeri bejelentkezést (single sign-on, SSO) a jelszavas hitelesítés helyett, amikor a vállalat erőforrásaihoz és adataihoz szeretnének hozzáférni. Az egyszeri bejelentkezés használatához hozzon létre egy eszközkonfigurációs profilt, adja meg az egyszerű felhasználónevet, az eszköz azonosítóját, az alkalmazásokat, valamint a felhasználó és az eszköz hitelesítéséhez használt tanúsítványt.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1add113222c2aa7eaea10679c329e877b1a136f
ms.sourcegitcommit: 437eaf364c3b8a38d294397310c770ea4d8a8015
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49992009"
---
# <a name="use-single-sign-on-ios-device-in-microsoft-intune"></a>Egyszeri bejelentkezést alkalmazó iOS eszközök használata a Microsoft Intune-ban

A legtöbb üzletviteli alkalmazás biztonsági célokból megkövetel bizonyos szintű felhasználóhitelesítést. A hitelesítéshez a felhasználónak sok esetben többször is meg kell adnia ugyanazokat a hitelesítő adatokat, ez pedig zavaró lehet. A felhasználói élmény javítása érdekében a fejlesztők létrehozhatnak egyszeri bejelentkezést (SSO) támogató alkalmazásokat, amelyek kevesebbszer kérik meg a felhasználót a hitelesítő adatok megadására.

Ebből a cikkből megtudhatja, hogyan engedélyezheti az egyszeri bejelentkezést iOS-eszközök számára egy eszközkonfigurációs profillal a Microsoft Intune-ban.

## <a name="before-you-begin"></a>Előkészületek

Szüksége lesz egy alkalmazásra, amely úgy lett megírva, hogy a felhasználói hitelesítő adatok tárát az iOS-eszköz egyszeri bejelentkezéses adatcsomagjában keresse.

## <a name="create-the-sso-profile"></a>Az SSO-profil létrehozása

1. Az [Azure Portalon](https://portal.azure.com) kattintson az **Összes szolgáltatás** lehetőségre, szűrjön az **Intune-ra**, és válassza ki a **Microsoft Intune** elemet.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg az alábbi beállításokat:

    - **Név**: Adja meg a profil nevét, például: `ios sso profile`.
    - **Leírás**: Adjon meg egy olyan kulcsszavakat tartalmazó leírást, amelyekkel könnyebben megtalálhatja a profilt a listában.
    - **Platform**: Válassza az **iOS** lehetőséget.
    - **Profil típusa**: Válassza az **Eszközfunkciók** lehetőséget.

4. Válassza az **Egyszeri bejelentkezés** lehetőséget.

    ![Egyszeri bejelentkezés panel](./media/sso-blade.png)

5. Adja meg a következő beállításokat: 

    - **Felhasználónév attribútum az AAD-ből**: Az Intune minden felhasználónál ezt az attribútumot keresi az Azure AD-ben. Az Intune ezt követően kitölti a megfelelő mezőt (például az egyszerű felhasználónevet), mielőtt létrehozná az eszközre telepítendő XML-adatcsomagot. A választható lehetőségek:
    
        - **Egyszerű felhasználónév**: Az egyszerű felhasználónevet (UPN-t) a rendszer a következőképpen elemzi:

            ![Felhasználónév attribútum](media/User-name-attribute.png)

            Szükség esetén felülírhatja a tartományt is, ha beírja a kívánt tartománynevet a **Tartomány** szövegmezőbe.

            Előfordulhat például, hogy a Contoso cégnek több régióban is van irodája, például Európában, Ázsiában és Észak-Amerikában. Tegyük fel, hogy az ázsiai felhasználóknak az egyszeri bejelentkezéses adatcsomagot kell használniuk, és az alkalmazás a következő formátumú egyszerű felhasználónevet (UPN-t) igényli: `username@asia.contoso.com`. Ilyen esetben, ha az **Egyszerű felhasználónév** lehetőséget választja, akkor az egyes felhasználók tartományát a rendszer alapértelmezés szerint az Azure AD-ból keresi ki, és a tartomány lehet egyszerűen *contoso.com*. Ezért az ázsiai felhasználóknak létrehozhatja külön ezt az adatcsomagot, és felülírhatja a tartományt az *asia.contoso.com* értékkel. Így a végfelhasználó egyszerű felhasználóneve username@contoso.com helyett username@asia.contoso.com lesz.

        - **Intune-eszközazonosító**: Az Intune automatikusan kiválasztja az Intune-eszközazonosítót. 

            Az alkalmazásoknak alapértelmezés szerint csak az eszközazonosítóra van szükségük. De ha az alkalmazás a tartományt *is* használja az eszközazonosító mellett, akkor megadhatja a tartományt a **Tartomány** szövegmezőben.

            > [!NOTE]
            > Alapértelmezett esetben hagyja a tartományt üresen, ha eszközazonosítót használ.

    - **Tartomány**: Az URL-cím tartományt jelölő része.
    
    - **Az egyszeri bejelentkezést használó URL-előtagok**: **Adja hozzá** a cég bármelyik olyan URL-címét, amely egyszeri bejelentkezéses felhasználó-hitelesítést igényel. 

        Ha egy felhasználó csatlakozik ezen webhelyekhez, az iOS-eszköz az egyszeri bejelentkezés hitelesítő adatait használja, és a felhasználónak nem kell hitelesítő adatokat megadnia. Ha azonban engedélyezte a többtényezős hitelesítést, a felhasználónak meg kell adnia a hitelesítés második tényezőjét.

        > [!NOTE]
        > Ezeknek az URL-címeknek érvényes formátumú teljes tartományneveknek kell lenniük. Az Apple a következő formátumot írja elő az URL-címekhez: `http://<yourURL.domain>`.

        Az URL-egyeztetési mintáknak `http://` vagy `https://` előtaggal kell kezdődniük. A rendszer egyszerű, sztringalapú egyeztetést végez, ezért a `http://www.contoso.com/` URL-előtag nem felel meg a `http://www.contoso.com:80/` címnek. iOS 10.0-s vagy újabb rendszereken megteheti, hogy egyetlen helyettesítő \* karaktert használ az összes egyező érték megadásához. Például a `http://*.contoso.com/` minta illeszkedik mind a `http://store.contoso.com/`, mind pedig a `http://www.contoso.com` címre.

        A `http://.com` és a `https://.com` minta pedig illeszkedik az összes HTTP, illetve HTTPS előtagú URL-címre.
    
    - **Az egyszeri bejelentkezést használó alkalmazások**: **Adjon hozzá** olyan alkalmazásokat a végfelhasználók eszközeihez, amelyek használhatnak egyszeri bejelentkezést. 

        Az `AppIdentifierMatches` tömbnek olyan sztringeket kell tartalmaznia, amelyek illeszkednek az alkalmazásköteg azonosítóira. Ezek a sztringek lehetnek pontos egyezések (például: `com.contoso.myapp`), illetve meghatározhatnak előtag-egyeztetést is a kötegazonosítóhoz a \* helyettesítő karakter segítségével. A helyettesítő karakternek egy pont karakter (.) után kell állnia, és csak egyszer szerepelhet az értékben, a sztring végén (például: `com.contoso.*`). A helyettesítő karakter használatakor az összes olyan alkalmazás hozzáférést kap a fiókhoz, amelynek a kötegazonosítója a megadott előtaggal kezdődik.

        Az **Alkalmazásnév** elemnél megadhat egy felhasználóbarát nevet, amely alapján könnyebben felismeri a kötegazonosítót.
    
    - **Hitelesítőadat-megújítási tanúsítvány**: Ha a hitelesítéshez (jelszó helyett) tanúsítványokat használ, válassza ki azt az SCEP- vagy PFX-tanúsítványt, amely hitelesítési tanúsítványként van telepítve a felhasználó számára. Ez jellemzően ugyanaz a tanúsítvány, amelyet más profilokhoz is kioszt a végfelhasználónak, ideértve például a VPN-t, a vezeték nélküli hálózatokat és a levelezést.

6. A módosítások mentéséhez és a profil létrehozásához válassza az **OK** > **OK** > **Létrehozás** lehetőséget. A létrehozott profil megjelenik az **Eszközkonfiguráció – Profilok** listában. 

## <a name="next-steps"></a>További lépések

Az eszközfunkciók konfigurálásáról bővebben [Az eszközfunkció-beállítások konfigurálása a Microsoft Intune-ban](device-features-configure.md) című témakörben olvashat.

[Rendelje hozzá ezt a profilt](device-profile-assign.md) iOS-eszközeihez.
