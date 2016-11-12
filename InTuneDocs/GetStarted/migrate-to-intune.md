---
title: "Áttérés az Intune-ra | Microsoft Intune"
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 8ebe9c29f4155a2aac39b502252f3225372d374f


---

# <a name="migrate-to-intune"></a>Áttérés az Intune-ra


A meglévő nagyvállalati mobilitási megoldásról az Intune-ra való áttérés a következő általános lépésekkel hajtható végre:

![Az Intune-ra való áttérés lépései](./media/migrate-intune-steps.png)

## <a name="notify-users"></a>A felhasználók értesítése

Amikor úgy véli, hogy az Intune próbaüzemi alkalmazása megfelelt a követelményeknek, tájékoztassa a felhasználókat arról, hogy hamarosan át kell telepíteni az eszközeiket az Intune-ba. E-mailek, használati utasítások és [poszterek](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) segítségével ismertetheti az elvárásokat, és bemutathatja a felhasználóknak a regisztrálás lépéseit, amelyeket végre kell hajtaniuk ahhoz, hogy továbbra is folyamatosan hozzáférjenek a vállalati erőforrásokhoz és alkalmazásokhoz. Győződjön meg arról, hogy a támogatási csapat felkészült a segítségnyújtásra, ha a felhasználók igénylik ezt az áttelepítési folyamat során.

## <a name="modify-your-existing-enterprise-mobility-management-solution"></a>A meglévő nagyvállalati mobilitási felügyeleti megoldás módosítása

Attól függően, hogyan szeretné kezelni a feltételes hozzáférési szabályzatokat a meglévő nagyvállalati mobilitási felügyeleti megoldás és az Intune között, előfordulhat, hogy le kell tiltania a meglévő feltételes hozzáférési szabályzatokat. A meglévő feltételes hozzáférési szabályzatokat letilthatja VAGY meghatározhatja úgy a hatókörüket, hogy ne vonatkozzanak az Intune-ba áttelepíteni kívánt felhasználókra vagy eszközökre.  Ne alkalmazza egyszerre az Intune és a meglévő vállalati mobilitási felügyeleti megoldás feltételes hozzáférési szabályzatait ugyanazokra a felhasználókra vagy eszközökre.

## <a name="enable-intune-conditional-access-policy-optional"></a>Az Intune feltételes hozzáférési szabályzatának engedélyezése (választható)

Ha úgy döntött, hogy azonnal érvénybe lépteti a feltételes hozzáférési szabályzatokat az áttelepítési időszakhoz megadott türelmi időszak nélkül, ebben a lépésben engedélyezze a feltételes hozzáférési szabályzatokat az Intune-ban.  Ügyeljen arra, hogy erről a döntésről pontos tájékoztatást adjon a felhasználóknak és a segélyszolgálati csapatnak.  Ha az eszközök nincsenek regisztrálva az Intune-ban, és nem felelnek meg az Intune szabályzatainak, a felhasználók nem tudják elérni a vállalati erőforrásokat, amíg nem regisztrálják az eszközüket az Intune-ban, és amíg az eszközök nem felelnek meg az Intune szabályzatainak.

## <a name="unenrolling-devices-from-your-existing-enterprise-mobility-management-solution"></a>Az eszközök regisztrációjának törlése a meglévő nagyvállalati mobilitási felügyeleti megoldásban

Az Intune-ba való regisztrálás előtt törölni kell az eszközök regisztrációját a meglévő vállalati mobilitási felügyeleti megoldásban. Azt javasoljuk, hogy a legjobb felhasználói élmény biztosításához tegye lehetővé a felhasználóknak, hogy saját maguk végezzék el az eszközeik regisztrációjának törlését.  Kövesse a megoldásszállító útmutatását a regisztráció megszüntetéséhez, hogy helyesen távolítsa el a felhasználókat és az eszközöket a platformról, mivel így biztosíthatja a lehető legkisebb fennakadást a végfelhasználók számára.

## <a name="enrolling-devices-in-intune"></a>Az eszközök regisztrálása az Intune-ban

Az áttéréshez beütemezett felhasználóknak késlekedés nélkül regisztrálniuk kell az eszközeiket az Intune-ban, hogy visszakapják a hozzáférésüket a vállalati erőforrásokhoz, e-mailekhez és alkalmazásokhoz, illetve hogy megakadályozzák a hozzáférés megszűnését. Ha feltételes hozzáférést konfigurált, és a felhasználók azt megelőzően próbálnak kapcsolódni a levelezéshez, hogy regisztrálták volna az eszközeiket az Intune-ban, akkor a hozzáférésük le lesz tiltva, és a regisztrálásra figyelmeztető e-mailt fognak kapni. Ez az e-mail segítséget nyújt számukra az eszköznek az Intune-ban történő regisztrálásához.  Másik lehetőségként a felhasználók az Intune Vállalati portál alkalmazását használhatják az eszköz regisztrálásához, vagy elvégezhetik ezt natív módon az operációs rendszerben (a Windows 8.1 és a Windows 10 Mobile esetében). A [Mit kell tudniuk a végfelhasználóknak az Intune használatáról?](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) című témakörben talál további útmutatást a regisztráláshoz az egyes platformok esetében.

## <a name="configure-intune-conditional-access-optional"></a>Az Intune feltételes hozzáférésének konfigurálása (választható)

Ha türelmi időszakot adott meg a feltételes hozzáférési szabályzat érvényesítéséhez, a türelmi időszak végfelhasználók számára előírt befejeződésekor engedélyezze a feltételes hozzáférési szabályzatokat az Intune-ban a szabályzatok érvénybe léptetéséhez. Ezzel azonnal érvénybe lép az a követelmény, hogy az összes eszköz megfeleljen az Intune feltételes hozzáférési szabályzatának.

## <a name="enroll-remaining-devices-and-users"></a>A fennmaradó eszközök és felhasználók regisztrálása

Miután engedélyezte a feltételes hozzáférést, a vállalati erőforrások eléréséhez az összes felhasználónak regisztrálnia kell az eszközét az Intune-ban, és az összes felhasználónak teljesítenie kell a szervezet megfelelőségi szabályzataiban előírt követelményeket. Ha a felhasználók áttérését fázisokra osztott regisztrációval oldotta meg (vagyis nem egyszerre), a fenti lépések végrehajtását addig ismételje, amíg az összes eszköz és felhasználó regisztrációja és kezelése az Intune hatálya alá nem kerül.

## <a name="retire-the-previous-enterprise-mobility-management-solution"></a>A korábbi nagyvállalati mobilitási felügyeleti megoldás kivonása

Miután megtörtént az összes felhasználó és eszköz áttelepítése az Intune-ba, és ellenőrizte is az áttelepítés sikerességét, kivonhatja a korábbi nagyvállalati mobilitási felügyeleti megoldást, illetve lemondhatja a szolgáltatást. Kövesse a megoldásszállító útmutatását, hogy megfelelően távolítsa el az infrastruktúra felesleges elemeit, és törölje a feleslegessé vált előfizetéseket és licenceket.

## <a name="additional-migration-resources"></a>További erőforrások az áttéréshez

További segítségre van szüksége az Intune-ra való áttéréshez? Szakértői segítséget is tudunk biztosítani ahhoz, hogy problémamentesen tudja végrehajtani az áttérést:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Microsoft Consulting Services tanácsadó szolgálat](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Technikai és nem technikai jellegű támogatás az Intune-hoz](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [A Microsoft Intune TechNet fóruma](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## <a name="get-a-downloadable-copy-of-this-guide"></a>A jelen útmutató letölthető példánya

A teljes útmutató letölthető a [TechNet Gallery](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387) webhelyről.



<!--HONumber=Nov16_HO2-->


