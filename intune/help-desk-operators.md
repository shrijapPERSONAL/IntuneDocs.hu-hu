---
title: Ügyfélszolgálati hibaelhárítási portál
titlesuffix: Microsoft Intune
description: Az ügyfélszolgálat munkatársai a hibaelhárítási portál segítségével oldják meg a felhasználók műszaki problémáit.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 4150a513e909ccfd44db23eee9b5990d97d8d670
ms.sourcegitcommit: 91dc50d38be13c65e5d144d237d7c4358089f215
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2018
ms.locfileid: "36329875"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Segítségnyújtás a céges felhasználóknak a hibaelhárítási portál használatával

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A hibaelhárítási portál segítségével az ügyfélszolgálat munkatársai és az Intune-rendszergazdák felhasználói információkat tekinthetnek meg a felhasználói segítségkérések teljesítéséhez. Az ügyfélszolgálattal rendelkező cégek **Ügyfélszolgálat** jogosultságot oszthatnak ki egy felhasználói csoport részére. Az ügyfélszolgálati szerepkörrel rendelkezők a **Hibaelhárítás** panelt használhatják.

A **Hibaelhárítás** panelen megtalálhatók lesznek a felhasználói regisztrálással kapcsolatos problémák. A hiba adatai és a megoldáshoz javasolt lépések segítséget nyújtanak a rendszergazdának és az ügyfélszolgálati munkatársaknak a hibalehárításban. A rendszer nem jegyez fel minden regisztrálási hibát, és bizonyos hibáknál nem kínál fel megoldási javaslatokat.

Az ügyfélszolgálati szerepkör hozzárendeléséről a [Szerepköralapú hozzáférés-vezérlés (RBAC) az Intune-nal](/intune/role-based-access-control) című témakör nyújt további információt.

Ha egy felhasználó Intune-nal kapcsolatos műszaki problémával fordul az ügyfélszolgálathoz, az ügyfélszolgálat munkatársa megadja a felhasználó nevét. Az Intune hasznos adatokat jelenít meg, amelyek számos 1. szintű probléma megoldásában segíthetnek, mint például:

- Felhasználó állapota
- Hozzárendelések
- Megfelelőségi problémák
- Az eszköz nem található
- Az eszközön nem működnek a VPN- vagy Wi-Fi-beállítások
- Alkalmazástelepítési hiba

## <a name="to-review-troubleshooting-details"></a>A hibaelhárítási adatok ellenőrzése

A hibaelhárítási panelen a **Felhasználó kiválasztása** hivatkozással lehet megnézni a felhasználó adatait. A felhasználói adatok segítséget nyújtanak a felhasználók és eszközeik aktuális állapotának áttekintésében.  

1. Jelentkezzen be az [Azure Portal](https://portal.azure.com) webhelyre.
2. Válassza a **Minden szolgáltatás** > **Intune** lehetőséget. Az Intune a **Figyelés + felügyelet** szakaszban található.
3. Az **Intune** panelen válassza a **Hibaelhárítás** lehetőséget.
4. A felhasználó kiválasztásához kattintson a **Kijelölés** lehetőségre.
5. Jelöljön ki egy felhasználót a megfelelő név vagy e-mail cím beírásával. Kattintson a **Kiválasztás** lehetőségre. A felhasználóval kapcsolatos hibaelhárítási információ a Hibaelhárítás panelen jelenik meg. Az alábbi táblázat tartalmazza az információk leírását.

> [!Note]  
> A **Hibaelhárítás** panel a böngészőben a [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) címen is elérhető.

## <a name="areas-of-troubleshooting-dashboard"></a>A hibaelhárítási irányítópult területei

A **Hibaelhárítás** panel használatával felhasználói információkat tekinthet meg.

![](/intune/media/troubleshooting-dash.png)

| Terület | Név | Description |
| ---  | ---  | ---         |
| 1.   | Fiók állapota  | Az aktuális Intune-bérlő állapotát jeleníti meg, amely lehet **Aktív** vagy **Inaktív**.       |
| 2.   | Felhasználó kiválasztása  | Az aktuálisan kiválasztott felhasználó neve. Új felhasználó kiválasztásához kattintson a **Felhasználó váltása** lehetőségre.       |
| 3.   | Felhasználó állapota  | Megjeleníti a felhasználó Intune-licencének állapotát, az eszközök számát, az egyes eszközök megfelelőségét, az alkalmazások számát és az alkalmazások megfelelőségét.       |
| 4.   | Felhasználói adatok  | A listából kiválaszthatja a panelen megtekintendő információkat. <br>Az alábbiak közül választhat: <ul><li>Mobilalkalmazásokban<li>Alkalmazásvédelmi szabályzatok<li>Megfelelőségi szabályzatok<li> Konfigurációs szabályzatok</ul>      |
| 5.   | Csoporttagság  | Yadda       |

## <a name="mobile-apps-reference"></a>Mobilalkalmazások információi

Az eszközökön, vagy az Intune és az Azure Active Directory (AD) által kezelt felhasználói tulajdonú eszközökön futó alkalmazások.

### <a name="properties"></a>Tulajdonságok

A mobilalkalmazások tulajdonságai.

| Tulajdonság      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Név          | Az alkalmazás neve.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Operációs rendszer            | Az eszközön telepített operációs rendszer.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Típus          | Mindegyik alkalmazáshoz kiválaszthat egy hozzárendelési típust.  <br> **Elérhető** – A felhasználók a Céges portál alkalmazásban vagy webhelyen telepítik az alkalmazást.  <br> **Nem alkalmazható** – Az alkalmazás nincs telepítve, vagy nem jelenik meg a Céges portálon. <br> **Eltávolítás** – A rendszer eltávolítja az alkalmazást a kiválasztott csoportok eszközeiről.  <br> **Regisztrációval vagy anélkül is elérhető** – Az alkalmazás hozzárendelése olyan felhasználók csoportjaihoz, akik eszközei nincsenek regisztrálva az Intune-ban. |
| Utolsó módosítás | Az eszköztípus neve.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="devices"></a>Eszközök

Az Intune által, vagy az Intune vagy az Azure AD által kezelt felhasználók által kezelt eszközök.

| Tulajdonság           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Eszköz neve        | Az eszköztípus neve.                                                                                                     |
| Felügyeli         | A szabályzat módosítási idejének időbélyege.                                                                                              |
| Azure AD-összekapcsolási típus | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Tulajdonos          | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**.                                               |
| Intune-kompatibilis   | Az eszköztípus neve.                                                                                                     |
| Azure AD-kompatibilis | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Operációs rendszer                 | Az eszközön telepített operációs rendszer.                                                                                       |
| Operációs rendszer verziója         | Az eszköz operációs rendszerének verziószáma.                                                                                  |
| Legutóbbi bejelentkezés      | Az eszköztípus neve.                                                                                                     |

### <a name="app-protection-status"></a>Alkalmazásvédelem állapota

Az alkalmazásvédelmi szabályzat az Enterprise Mobility Solution- (EMS-) technológiával integrált mobilalkalmazásoknál érhető el. Ez biztosítja a vállalati adatok alapvető védelmét, amikor azokat különféle, például Office-os mobilalkalmazások töltik le. 

| Tulajdonság    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Állapot      | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**. |
| Alkalmazás neve    | Az alkalmazás neve                                                           |
| Eszköz neve | Az eszköztípus neve.                                                       |
| Eszköz típusa | Az eszköztípus neve.                                                       |
| Házirendek    | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**. |
| Legutóbbi szinkronizálás   | Időbélyeg, amely az eszköz Intune-nal való szinkronizálásának utolsó idejét mutatja.                   |

## <a name="app-protection-policies-reference"></a>Alkalmazásvédelmi szabályzatok információi

Az alkalmazásvédelmi szabályzat az EMS-technológiával integrált mobilalkalmazásoknál érhető el. Ez biztosítja a vállalati adatok alapvető védelmét, amikor azokat különféle, például Office-os mobilalkalmazások töltik le. 

### <a name="properties"></a>Tulajdonságok

A táblázat az Intune által kezelt eszközök alkalmazásvédelmi szabályzatainak állapotát mutatja be.

| Tulajdonság    | Description                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Név        | Az alkalmazás neve.                                                                                                        |
| Telepítve    | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Platform    | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**.                                               |
| Beléptetés  | Az eszköztípus neve.                                                                                                     |
| Legutóbbi frissítés | A szabályzat módosítási idejének időbélyege.                                                                                              |

### <a name="devices"></a>Eszközök

Az Intune által, vagy az Intune vagy az Azure AD által kezelt felhasználók által kezelt eszközök.

| Tulajdonság           | Szöveg                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Eszköz neve        | Az eszköztípus neve.                                                                                                     |
| Felügyeli         | A szabályzat módosítási idejének időbélyege.                                                                                              |
| Azure AD-összekapcsolási típus | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Tulajdonos          | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**.                                               |
| Intune-kompatibilis   | Az eszköztípus neve.                                                                                                     |
| Azure AD-kompatibilis | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Azure AD-kompatibilis | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Operációs rendszer                 | Az eszközön telepített operációs rendszer.                                                                                       |
| Operációs rendszer verziója         | Az eszköz operációs rendszerének verziószáma.                                                                                  |
| Legutóbbi bejelentkezés      | Az eszköztípus neve.                                                                                                     |

## <a name="compliance-policies-reference"></a>Megfelelőségi szabályzatok információi

Gondoskodik róla, hogy a vállalati alkalmazások és adatok elérésére használt eszközök megfeleljenek bizonyos szabályoknak, például használjanak PIN-kódot az eszközhöz való hozzáféréshez, illetve titkosítsák az eszközön tárolt adatokat.

### <a name="properties"></a>Tulajdonságok

A megfelelőségi szabályzatok tulajdonságai.

| Tulajdonság      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Hozzárendelés    | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Név          | Az alkalmazás neve.                                                                                                        |
| Operációs rendszer            | Az eszközön telepített operációs rendszer.                                                                                       |
| Szabályzattípus   | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**.                                               |
| Utolsó módosítás | Az eszköztípus neve.                                                                                                     |

### <a name="devices"></a>Eszközök

Az Intune által, vagy az Intune vagy az Azure AD által kezelt felhasználók által kezelt eszközök.

| Tulajdonság           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Eszköz neve        | Az eszköztípus neve.                                                                                                     |
| Felügyeli         | A szabályzat módosítási idejének időbélyege.                                                                                              |
| Azure AD-összekapcsolási típus | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Tulajdonos          | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**.                                               |
| Intune-kompatibilis   | Az eszköztípus neve.                                                                                                     |
| Azure AD-kompatibilis | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Operációs rendszer                 | Az eszközön telepített operációs rendszer.                                                                                       |
| Operációs rendszer verziója         | Az eszköz operációs rendszerének verziószáma.                                                                                  |
| Legutóbbi bejelentkezés      | Az eszköztípus neve.                                                                                                     |

### <a name="app-protection-policies"></a>Alkalmazásvédelmi szabályzatok

Az alkalmazásvédelmi szabályzat az EMS-technológiával integrált mobilalkalmazásoknál érhető el. Ez biztosítja a vállalati adatok alapvető védelmét, amikor azokat különféle, például Office-os mobilalkalmazások töltik le. 

| Tulajdonság    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Állapot      | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**. |
| Alkalmazás neve    | Az alkalmazás neve                                                           |
| Eszköz neve | Az eszköztípus neve.                                                       |
| Eszköz típusa | Az eszköztípus neve.                                                       |
| Házirendek    | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**. |
| Legutóbbi szinkronizálás   | Időbélyeg, amely az eszköz Intune-nal való szinkronizálásának utolsó idejét mutatja.                   |

## <a name="configuration-policies-reference"></a>Konfigurációs szabályzatok információi

Alkalmazásvédelmi szabályzat szállítóspecifikus konfigurációval rendelkező mobilalkalmazásoknál érhető el. 

### <a name="properties"></a>Tulajdonságok

A konfigurációs szabályzatok tulajdonságai.

| Tulajdonság      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Hozzárendelés    | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Név          | Az alkalmazás neve.                                                                                                        |
| Operációs rendszer            | Az eszközön telepített operációs rendszer.                                                                                       |
| Szabályzattípus   | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**.                                               |
| Utolsó módosítás | Az eszköztípus neve.                                                                                                     |

### <a name="devices"></a>Eszközök

Az Intune által, vagy az Intune vagy az Azure AD által kezelt felhasználók által kezelt eszközök.

| Tulajdonság           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Eszköz neve        | Az eszköztípus neve.                                                                                                     |
| Felügyeli         | A szabályzat módosítási idejének időbélyege.                                                                                              |
| Azure AD-összekapcsolási típus | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Tulajdonos          | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**.                                               |
| Intune-kompatibilis   | Az eszköztípus neve.                                                                                                     |
| Azure AD-kompatibilis | Az egyes felhasználók alkalmazásvédelmi alkalmazásainak állapota. Az alkalmazások lehetséges állapotai: **Bejelentkezett** és **Nem bejelentkezett**. |
| Operációs rendszer                 | Az eszközön telepített operációs rendszer.                                                                                       |
| Operációs rendszer verziója         | Az eszköz operációs rendszerének verziószáma.                                                                                  |
| Legutóbbi bejelentkezés      | Az eszköztípus neve.                                                                                                     |


### <a name="app-protection-policies"></a>Alkalmazásvédelmi szabályzatok

Az alkalmazásvédelmi szabályzat az EMS-technológiával integrált mobilalkalmazásoknál érhető el. Ez biztosítja a vállalati adatok alapvető védelmét, amikor azokat különféle, például Office-os mobilalkalmazások töltik le. 

| Tulajdonság    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Állapot      | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**. |
| Alkalmazás neve    | Az alkalmazás neve                                                           |
| Eszköz neve | Az eszköztípus neve.                                                       |
| Eszköz típusa | Az eszköztípus neve.                                                       |
| Házirendek    | Az eszköz tulajdonlástípusa. A típus lehet **Vállalati**, **Személyes** vagy **Ismeretlen**. |
| Legutóbbi szinkronizálás   | Időbélyeg, amely az eszköz Intune-nal való szinkronizálásának utolsó idejét mutatja.                   |

## <a name="collect-available-data-from-mobile-device"></a>Rendelkezésre álló adatok gyűjtése mobileszközön

A következő erőforrásokkal eszközadatokat gyűjthet a felhasználói eszközök hibáinak elhárításakor:
  - [Az iOS regisztrálási hibáinak elküldése a rendszergazdának](/intune-user-help/send-errors-to-your-it-admin-ios)
  - [A cég informatikai támogatási szolgálatának segítése az eszközproblémák megoldásában részletes naplózással](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
  - [Android-naplók elküldése a cég informatikai támogatási szolgálatának USB-kábelen keresztül](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Az Android diagnosztikai adatait tartalmazó naplófájlok elküldése e-mailben a rendszergazdának](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
  - [Az Android regisztrálási hibáinak elküldése a rendszergazdának](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>További lépések

Megismerkedhet a szerepköralapú adminisztrációval (RBAC), és hogy az miként használható szerepkörök definiálására a szervezet eszközein, a mobileszköz-kezelésben és az adatvédelmi feladatokban. További információt a [Szerepköralapú hozzáférés-vezérlés (RBAC) az Intune-nal](/intune/role-based-access-control) című témakörben talál.

Ismertető a Microsoft Intune esetleges ismert problémáiról. További információt [Az Intune ismert problémái](/intune/known-issues) című témakörben talál.

Megtudhatja, hogyan hozhat létre támogatási jegyeket, és hogyan kérhet segítséget, ha szüksége van rá. [Támogatás kérése](/intune/get-support).
