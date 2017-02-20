---
title: "IOS-alkalmazások közötti adatátvitel kezelése | Intune az Azure-on – előzetes | Microsoft Docs"
description: "Azure-beli Intune – előzetes: Olvassa el ezt a témakört az iOS Megnyitás a követezőben funkciója használatának, valamint az alkalmazások közötti adatátvitel kezeléséhez szükséges mobilalkalmazás-kezelési szabályzatok megismeréséhez."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>iOS-alkalmazások közti adatátvitel kezelése 
## <a name="manage-ios-apps"></a>IOS-alkalmazások felügyelete
A vállalati adatok védelmébe tartozik annak biztosítása, hogy csak a vállalat által felügyelt alkalmazásokkal lehessen fájlokat átvinni.  Az iOS-alkalmazásokat az alábbi módokon felügyelheti:

-   Vállalati adatvesztés megakadályozása alkalmazásvédelmi szabályzatok konfigurálásával az alkalmazások számára. Az ilyen alkalmazásokat **szabályzattal felügyelt** alkalmazásoknak nevezzük.

-   Az **MDM-csatornán** keresztül is telepíthet és felügyelhet alkalmazásokat.  Ehhez az eszközöket az MDM-megoldásba kell regisztrálni. Ezek **házirenddel felügyelt** alkalmazások vagy más felügyelt alkalmazások is lehetnek.

Az iOS-eszközök **Megnyitási engedélyek felügyelete** szolgáltatásával a fájlátvitel az **MDM-csatornával** telepített alkalmazásokra korlátozható. A Megnyitási engedélyek felügyeletének korlátozásai a konfiguráció beállításaiban adhatók meg, és a mobileszköz-kezelési megoldás használatával telepíthetők.  Amikor a felhasználó telepíti a központilag telepített alkalmazást, a rendszer alkalmazza a beállított korlátozásokat.
##  <a name="using-app-protection-with-ios-apps"></a>Az alkalmazásvédelem használata iOS-alkalmazásokkal
Az alkalmazásvédelmi szabályzatok az iOS **Megnyitási engedélyek felügyelete** szolgáltatásával együtt használhatók a vállalati adatok védelméhez, a következő módokon:

-   **Alkalmazottak tulajdonában lévő, mobileszköz-kezelési megoldás által nem kezelt eszközök:** az alkalmazásvédelmi szabályzat beállításait beállíthatja a következőre: **Az alkalmazás átadhat adatokat házirend által felügyelt alkalmazásoknak**. Ha a végfelhasználó nem házirenddel felügyelt alkalmazásban nyit meg egy védett fájlt, a fájl nem olvasható.

-   **Az Intune által felügyelt eszközök:** az Intune-ban regisztrált eszközök esetén az alkalmazásvédelmi szabályzatokkal rendelkező és az Intune használatával telepített egyéb felügyelt iOS-alkalmazások közötti adatátvitel automatikusan engedélyezett. Az alkalmazásvédelmi szabályzatokkal rendelkező alkalmazások közötti adatátvitel engedélyezéséhez aktiválja **Az alkalmazás átadhat adatokat szabályzat által felügyelt alkalmazásoknak** beállítást. Az Intune-nal telepített alkalmazások között a **Megnyitási engedélyek felügyelete** funkcióval vezérelhető az adatátvitel.   

-   **Külső MDM-megoldás által felügyelt eszközök:** Az adatátvitel a felügyelt alkalmazásokra korlátozható az IOS **Megnyitási engedélyek felügyelete** funkciójával.
Annak biztosításához, hogy a harmadik féltől származó MDM megoldás segítségével központilag telepített alkalmazások is társítva legyenek az Intune-ban beállított alkalmazásvédelmi szabályzatokhoz, konfigurálnia kell a felhasználói UPN-beállítást, [A felhasználói UPN-beállítás konfigurálása](#configure-user-upn-setting) című cikkben ismertetett lépések szerint.  Ha az alkalmazásokat a felhasználói UPN-beállítással telepítik, akkor az alkalmazásvédelmi szabályzatok érvénybe lépnek az alkalmazásra vonatkozóan, amikor a végfelhasználó a munkahelyi fiókjával jelentkezik be.

> [!IMPORTANT]
> A felhasználói UPN-beállításra csak a külső MDM által felügyelt eszközökre telepített alkalmazások esetén van szükség.  Az Intune-nal felügyelt eszközök esetén erre a beállításra nincs szükség.

## <a name="configure-user-upn-setting"></a>A felhasználói UPN-beállítás konfigurálása
Erre a konfigurációra külső MDM-megoldás által felügyelt eszközök esetén van szükség. Az alább leírt eljárás egy általános módszer az UPN-beállítás és az eredményül kapott végfelhasználói élmény megvalósításához:


1.  Az Azure-portálon [konfiguráljon mobilalkalmazás-felügyeleti szabályzatot](app-protection-policies.md) iOS platformra. A vállalati igényeknek megfelelően konfigurálja a szabályzat beállításait, majd válassza ki az alkalmazásokat, amelyeknek ezzel a szabályzattal kell rendelkezniük.

2.  A felügyelni kívánt alkalmazásokat és az e-mail profilt telepítse **saját külső MDM-megoldásával** a 3. és 4. lépésekben leírt beállítások használatával.

3.  Az alkalmazást a következő alkalmazáskonfigurációs beállításokkal telepítse: key=IntuneMAMUPN, Value=<username@company.com> [például: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Telepítse a Megnyitási engedélyek felügyelete házirendet a regisztrált eszközökre.

### <a name="example-end-user-experience"></a>Végfelhasználói élmény példája

1.  A végfelhasználó telepíti a Microsoft Word alkalmazást az eszközre.

2.  A végfelhasználó elindítja a felügyelt natív levelezőalkalmazást az e-mailjei eléréséhez.

3.  A végfelhasználó megpróbál megnyitni egy dokumentumot egy natív e-mailből a Microsoft Word programban.

4.  A Word elindulásakor a rendszer felkéri a végfelhasználót, hogy jelentkezzen be a munkahelyi fiókjával.  Ennek a végfelhasználó által, kérésre megadott munkahelyi fióknak meg kell egyeznie a Microsoft Word alkalmazás számára az alkalmazás konfigurációs beállításaiban megadott fiókkal.

    > [!NOTE]
    > A végfelhasználó más személyes fiókokat is hozzáadhat a Wordhöz személyes munkájának elvégzéséhez, és az alkalmazásvédelmi szabályzatok nem vonatkoznak rá a Word alkalmazás személyes használatakor.

5.  Amikor a bejelentkezés sikeres, az alkalmazás házirend-beállításai érvénybe lépnek a Word alkalmazásnál.

6.  Mostantól az adatátvitel sikeres lesz, és a dokumentum vállalati identitásként van megjelölve az alkalmazásban. Ezenkívül a rendszer munkahelyi környezetben kezeli az adatokat, és ennek megfelelően alkalmazza a szabályzatbeállításokat.

### <a name="see-also"></a>További információ
[Mi az Intune alkalmazásvédelmi szabályzat?](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


