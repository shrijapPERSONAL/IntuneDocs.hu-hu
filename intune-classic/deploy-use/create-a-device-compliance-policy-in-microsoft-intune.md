---
title: "Eszközmegfelelőségi szabályzat létrehozása | Microsoft Docs"
description: "Létrehozhat egy megfelelőségi szabályzatot a vállalati adatokhoz hozzáférő mobileszközök és számítógépek biztonságossá tételéhez."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5336dac0-a2cc-4cd4-8511-67e4f95bd700
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 21875001129da8f5ca01869fa69960f18ae28c56
ms.lasthandoff: 12/10/2016


---

# <a name="create-a-device-compliance-policy-in-microsoft-intune"></a>Eszközmegfelelőségi szabályzat létrehozása a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ez a témakör egy olyan eszközmegfelelőségi szabályzat létrehozásának lépéseit írja le, amelyet az eszközöknek be kell tartaniuk ahhoz, hogy megfelelőnek lehessen tekinteni őket.

##  <a name="step-1-add-a-new-policy"></a>1. lépés: Az új szabályzat hozzáadása
  A [Microsoft Intune felügyeleti konzolján](https://manage.microsoft.com) válassza a **Házirend** &gt; **Megfelelőségi házirendek** &gt; **Hozzáadás** lehetőséget.

  ![A megfelelőségi szabályzat oldalának tetején található menü Hozzáadás pontját megjelenítő képernyőkép az Intune felügyeleti konzolon](./media/intune-sa-3a-add-compliance-policy.png)

##  <a name="step-2--configure-settings"></a>2 lépés: Beállítások konfigurálása
A **Házirend létrehozása** lapon engedélyezze a kívánt beállításokat:
  -   Rendszerbiztonsági beállítások, például jelszó és titkosítás.
  -   Eszközállapot-beállítások, például az, hogy az eszköz függetlenítve van-e vagy fel van-e törve, illetve hogy az eszközt megfelelő állapotúként jelentette-e a Windows eszközállapot-igazolási szolgáltatása.
  -   Eszköztulajdonság-beállítások, mint például az operációs rendszer szükséges minimális, illetve engedélyezett maximális verziója.
![A Szabályzat létrehozása lap Általános lapja](./media/intune-sa-3b-create-policy.png)


##  <a name="step-3-save-the-policy"></a>3. lépés: A szabályzat mentése
Ha elkészült, válassza a **Házirend mentése** elemet.

Lehetősége van közvetlenül a mentés után telepíteni a szabályzatot, vagy telepítheti később is. Az új szabályzat a **Házirend** munkaterület **Megfelelőségi házirendek** csomópontjában jelenik meg.

##  <a name="step-4-set-the-compliance-status-validity-period"></a>4. lépés: A szabályzat érvényességi idejének beállítása
Azon időpont megadásához, amely előtt az eszköznek be kell jelentkeznie, hogy ne váljon nem megfelelővé, lépjen a megfelelőségi szabályzat beállításaiba, és frissítse a beállítását. Az alapértelmezett érték 30 nap.

![Megfelelőségi szabályzat beállításának lehetősége a szabályzat menüsoron](../media/mdm-compliance-policy-settings.png)

![Megfelelőségi szabályzat párbeszédpanel](../media/mdm-ca-compliance-status-validity-period.png)

## <a name="supported-policy-settings"></a>Támogatott szabályzatbeállítások
Az alábbi táblázat felsorolja a megfelelőségi szabályzatok egyes beállításait, illetve azt, hogy ezek a beállítások mely platformokon támogatottak.

-------------
|Beállítás|iOS|Android|Windows|
|-----|----|-----|-----|
|Jelszó szükséges a mobileszközök feloldásához|iOS 6 és újabb verziók|Android 4.0 és újabb verziók <br>Samsung KNOX szabvány 4.0 és újabb|Windows Phone 8.1 és újabb verziók|
|Egyszerű jelszavak engedélyezése|iOS 6 és újabb verziók|Nem támogatott|Windows Phone 8.1 és újabb verziók|
|Jelszó minimális hossza|iOS 6 és újabb verziók| Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb| Windows Phone 8.1 és újabb verziók<br>Windows 8.1|
|Kötelező jelszótípus|iOS 6 és újabb verziók|Nem érhető el|Windows Phone 8.1 és újabb verziók <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Karakterkészletek minimális száma:|iOS 6 és újabb verziók|Nem érhető el|Windows Phone 8.1 és újabb verziók <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Jelszó minősége|Nem érhető el|Android 4.0 és újabb verziók <br>Samsung KNOX szabvány 4.0 és újabb|Nem érhető el|
|Tétlen percek száma, mielőtt az eszköz újból kéri a jelszót|iOS 6 és újabb verziók|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb|Windows Phone 8.1 és újabb verziók<br>Windows RT és Windows RT 8.1<br>Windows 8.1|
|Jelszó lejárata (nap)|iOS 6 és újabb verziók|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb|Windows Phone 8.1 és újabb verziók<br>Windows RT és Windows RT 8.1<br>Windows 8.1|
|Jelszóelőzmények megjegyzése|iOS 6 és újabb verziók|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb|Windows Phone 8.1 és újabb verziók<br>Windows RT és Windows RT 8.1<br>Windows 8.1|
|Korábbi jelszavak újbóli használatának tiltása|iOS 6 és újabb verziók|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb|Windows Phone 8.1 és újabb verziók<br>Windows RT és Windows RT 8.1<br>Windows 8.1|
|Jelszó kérése, amikor az eszköz visszatér inaktív állapotból| Nem érhető el| Nem érhető el|Windows 10 mobil verzió|
|Mobileszköz titkosításának kötelezővé tétele|Nem alkalmazható|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb|Windows Phone 8.1 és újabb verziók<br> Windows 8.1|
|Annak megkövetelése, hogy a jelentett eszközök kifogástalan állapotúak legyenek| Nem érhető el| Nem érhető el|Windows <br>Windows 10 mobil verzió|
|Az eszköz nem lehet függetlenített vagy feltört eszköz|iOS 6 és újabb verziók|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb|Nem érhető el|
|Csak az Intune által felügyelt e-mail fiók használható|iOS 6 és újabb verziók|Nem érhető el| Nem érhető el|
|Az Intune-ban felügyelni kívánt levelezési profil kiválasztása|iOS 6 és újabb verziók|Nem érhető el| Nem érhető el|
|Az operációs rendszer szükséges minimális verziója|iOS 6 és újabb verziók|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb| Windows Phone 8.1 és újabb verziók<br>Windows 8.1|
|Az operációs rendszer szükséges maximális verziója|iOS 6 és újabb verziók|Android 4.0 és újabb verziók<br>Samsung KNOX szabvány 4.0 és újabb|Windows Phone 8.1 és újabb verziók<br>Windows 8.1|

Az egyes platformokon támogatott megfelelőségi beállításokkal kapcsolatos bővebb információkért válasszon az alábbi lehetőségek közül:
> [!div class="op_single_selector"]
- [Megfelelőségi szabályzat beállításai iOS-eszközökhöz](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Android-eszközökhöz](android-compliance-policy-settings-in-microsoft-intune.md)
- [Megfelelőségi szabályzat beállításai Windows- és Windows Phone-eszközökhöz](windows-compliance-policy-settings-in-microsoft-intune.md)


## <a name="next-steps"></a>További lépések
[Megfelelőségi szabályzat érvénybe léptetése és figyelése](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>További információ
[Bevezetés az eszközmegfelelőségi szabályzatokba](introduction-to-device-compliance-policies-in-microsoft-intune.md)

