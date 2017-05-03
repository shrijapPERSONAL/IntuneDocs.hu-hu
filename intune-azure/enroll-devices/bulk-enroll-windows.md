---
title: "Csoportos regisztráció Windows 10 esetén | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Csoportos regisztrációs csomag létrehozása a Microsoft Intune-hoz"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 4eab83b1f542a3ac663150c810667c644df8a0bd
ms.lasthandoff: 04/19/2017

---
# <a name="bulk-enrollment-for-windows-devices"></a>Windows-eszközök csoportos regisztrálása

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A rendszergazda nagy számú új Windows-eszközt csatlakoztathat az Azure Active Directoryhoz és az Intune-hoz. Ha az Azure AD-bérlőhöz csoportosan szeretne eszközöket regisztrálni, először a Windows Configuration Designer (WCD) alkalmazással létre kell hoznia egy kiépítési csomagot. Ha a kiépítési csomagokat céges tulajdonban lévő eszközökre alkalmazza, az eszközök az Azure AD-bérlőhöz lesznek csatlakoztatva, és regisztrálva lesznek az Intune-felügyeletben. Ha a csomagok alkalmazása megtörtént, az Azure AD-felhasználók bejelentkezhetnek.

Az Azure AD-felhasználók általános jogú felhasználók ezeken az eszközökön, és megkapják a hozzájuk rendelt Intune-szabályzatokat és a kötelező alkalmazásokat. Az önkiszolgáló és a Céges portált használó módszer jelenleg nincs támogatva.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Windows-eszközök csoportos regisztrációjának előfeltételei

Windows-eszközök csoportos regisztrálásához az alábbiak szükségesek:

- Windows 10 alkotói frissítést vagy későbbi változatot futtató eszközök
- [Windows-eszközök automatikus regisztrációja](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Kiépítési csomag létrehozása

1. Töltse le a [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) alkalmazást a Windows Áruházból.
![Képernyőkép az alkalmazás-áruházbeli Windows Configuration Designer alkalmazásról és leírásáról](media/bulk-enroll-store.png)

2. Nyissa meg a **Windows Configuration Designer** alkalmazást, és válassza a **Provision desktop devices** (asztali eszközök kiépítése) elemet.
![Képernyőkép a Provision desktop services kiválasztásáról a Windows Configuration Designer alkalmazásban](media/bulk-enroll-select.png)

3. Megnyílik egy **Új projekt** ablak, ahol az alábbiakat kell megadnia:
  - **Név** – A projekt neve
  - **Projektmappa** – A projekt mentési helye
  - **Leírás** – A projekt leírása (nem kötelező) ![Képernyőkép a név, a projektmappa és a leírás megadásáról a Windows Configuration Designer programban](media/bulk-enroll-name.png)

4.    Adjon meg egyedi neveket az eszközök számára. A név tartalmazhat sorozatszámot (%%SERIAL%%), vagy véletlenszerű karaktersorozatot. Lehetőség van termékkulcs megadására is, ha frissíti a Windows-kiadást, megosztott használatra konfigurálja az eszközt, és előre telepített szoftvert távolít el.
![Képernyőkép a név, a projektmappa és a leírás megadásáról a Windows Configuration Designer programban](media/bulk-enroll-device.png)

5.    Lehetőség van arra is, hogy beállítsa, mely Wi-Fi-hálózathoz csatlakozzanak az eszközök az első indításkor.  Ha ezt nem állítja be, az eszköz első indításakor vezetékes hálózati kapcsolatra lesz szükség.
![Képernyőkép a Windows Configuration Designer alkalmazásról a Wi-Fi engedélyezésével, többek között a hálózati SSID és a hálózattípusok konfigurálásával](media/bulk-enroll-network.png)

6.    Válassza a **Regisztrálás az Azure AD-ban** lehetőséget, adja meg a **Csoportos token lejárati idejét**, majd válassza a **Csoportos token beszerzése** elemet.
![Képernyőkép a név, a projektmappa és a leírás megadásáról a Windows Configuration Designer programban](media/bulk-enroll-account.png)

7. A csoportos token beszerzéséhez meg kell adnia az Azure AD-hez tartozó hitelesítő adatait.
![Képernyőkép a név, a projektmappa és a leírás megadásáról a Windows Configuration Designer programban](media/bulk-enroll-cred.png)

8.    Ha a **Csoportos token** sikeresen letöltődött, kattintson a **Tovább** gombra.

9. Lehetőség van **Alkalmazások hozzáadására** és **Tanúsítványok hozzáadására** is. A megadott alkalmazások és tanúsítványok ki lesznek építve az eszközön.

10. Ha szeretné, a kiépítési csomagot jelszóval is védheti.  Kattintson a **Létrehozás** gombra.
![Képernyőkép a név, a projektmappa és a leírás megadásáról a Windows Configuration Designer programban](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Eszközök üzembe helyezése

1. Keresse meg a kiépítési csomagot abban a mappában, amelyet az alkalmazásban **Projektmappaként** adott meg.

2. Válassza ki azt a módszert, amellyel a kiépítési csomagot szeretné alkalmazni az eszközre.  A kiépítési csomagot az alábbi módszerekkel lehet eszközre alkalmazni:
 - Másolja a kiépítési csomagot egy USB-meghajtóra, majd csatlakoztassa az USB-meghajtót ahhoz az eszközhöz, amelyet csoportosan szeretne regisztrálni, majd a kezdeti beállításnál alkalmazza a csomagot
 - Másolja a kiépítési csomagot egy hálózati meghajtóra, majd a kezdeti beállításnál alkalmazza a csomagot a csoportosan regisztrálni kívánt eszközre

 A kiépítési csomag használatának részletes leírását megtalálja a [Kiépítési csomag alkalmazása](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package) című témakörben.

3. A csomag alkalmazása után az eszköz 1 percen belül automatikusan újraindul.
 ![Képernyőkép a név, a projektmappa és a leírás megadásáról a Windows Configuration Designer programban](media/bulk-enroll-add.png)

4. Az újraindítás után az eszköz automatikusan csatlakozik az Azure Active Directoryhez, és regisztrál a Microsoft Intune-ban.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Windows-eszközök csoportos regisztrálásának hibaelhárítása

A kiépítés alapvetően új Windows-eszközök esetében használható. Kiépítési hibák esetén szükség lehet a gyári beállítások visszaállítására, vagy az eszköz helyreállítására rendszerindító lemezképről. Az alábbi példák egyes kiépítési hibákról adnak információt:

- Ha egy kiépítési csomaggal olyan Active Directory-tartományhoz vagy olyan Azure Active Directory-bérlőhöz próbál csatlakozni, amely nem hoz létre helyi fiókot, akkor az eszköz elérhetetlenné válhat, ha a tartományhoz való csatlakozás hálózati hiba miatt meghiúsul.
- A kiépítési csomag parancsfájljai rendszerkörnyezetben futnak, és bármilyen módosítást képesek elvégezni az eszköz fájlrendszerén és konfigurációján. Egy rosszindulatú vagy hibás parancsfájl azt eredményezheti, hogy az eszközt csak a rendszerkép alaphelyzetbe állításával vagy a gyári beállítások visszaállításával lehet helyreállítani.

